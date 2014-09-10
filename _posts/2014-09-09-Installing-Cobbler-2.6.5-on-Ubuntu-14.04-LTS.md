---
author: josef
date: 2014-09-09
title: 'Installing Cobbler 2.6.5 on Ubuntu 14.04 LTS'
category: tech
layout: post
image: 
  feature: DevOpsDaysLogo.png
published: true
tags: ops tools packaging
comments: true
share: true
---

Last week people from three different teams and two locations met in the Dordrecht office for a [hackathon](http://en.wikipedia.org/wiki/Hackathon) with the modest objective of "Provisioning the Future".
My new colleague Jorja has written an excellent post about her experiences during her first [visit in Dordrecht]({{ site.baseurl }}/process/2014/09/08/jorja-visits-dordrecht.html).

Bare-metal Provisioning
-----------------------

Although we have considered multiple tools for our bare-metal provisioning process, we ultimately decided to use [Cobbler](http://www.cobblerd.org/).
Since we ran into several problems during the installation of the latest version on Ubuntu 14.04, I thought it's worth sharing our experiences and used workarounds.

How to install Cobbler 2.6.5 on Ubuntu 14.04 LTS
=====================================

Ubuntu 14.04 is shipped with [Cobbler 2.4.1](http://www.cobblerd.org/posts/2014/02/03/cobbler_2.4.1_released.html), but since the Cobbler project is quite active in the last few month, we decided to use the latest packages provided by cobberd.org.
I am not sure, when the project started to create Debian/Ubuntu packages, but the [documentation]("http://www.cobblerd.org/manuals/2.6.0/2/2/4_-_Debian_and_Ubuntu.html") is not in place yet.

Adding the repository in Ubuntu:

```
wget -qO - http://download.opensuse.org/repositories/home:/libertas-ict:/cobbler26/xUbuntu_14.04/Release.key | sudo apt-key add -
sudo add-apt-repository "deb http://download.opensuse.org/repositories/home:/libertas-ict:/cobbler26/xUbuntu_14.04/ ./"
```

Installing Cobbler:
```
sudo apt-get update
sudo apt-get install cobbler
```

Workaround 1: Installing addional required packages
-----------------------------------------------

Startup error "ImportError: No module named urlgrabber":

```
sudo apt-get install python-urlgrabber
```

Apache error "Invalid command 'WSGIScriptAliasMatch": 

```
sudo apt-get install libapache2-mod-wsgi
```

And finally installing the missing Django package, fixing error "ImportError: No module named django.core.handlers.wsgi":

```
sudo apt-get install python-django
```

I have created a [pull request](https://github.com/cobbler/cobbler/pull/1207) that adds these runtime dependencies to the Debian build. The request is still pending, but I hope that it will fix this problem for future releases.

*Update: Pull request was already accepted and merged.*

Workaround 2: Fixing Apache configuration
------------------------------------

Background: Debian is changing the [Apache2 directory structure for the next version](https://wiki.debian.org/Apache/PackagingFor24), but since [Ubuntu 14.04 LTS is based on Debian unstable](https://wiki.ubuntu.com/LTS) it is already using the new structure. Please see the created [github issue](https://github.com/cobbler/cobbler/issues/1208) for the current status.

```
# moving the config to correct directory 
mv /etc/apache2/conf.d/cobbler.conf /etc/apache2/conf-available/
mv /etc/apache2/conf.d/cobbler_web.conf /etc/apache2/conf-available/
# ... and enable the cobbler config
cd /etc/apache2/conf-enabled
ln -s ../conf-available/cobbler.conf .
ln -s ../conf-available/cobbler_web.conf .
```

Workaround 3: Loading required Apache modules
----------------------------------------------

This step is also required on [openSUSE](http://www.cobblerd.org/manuals/2.6.0/2/2/3_-_openSUSE.html) at the moment, should be IMHO done during the package installation:

```
a2enmod proxy
a2enmod proxy_http
```

Workaround 4: Generating Django SECRET_KEY
------------------------------------------
According to [this issue]("https://github.com/cobbler/cobbler/issues/546") this should only be required, when installing from source. I have not checked the details, so this might be caused by the missing packages during the installation process.
This workaround is based on a solution posted on [Stack Overflow](http://stackoverflow.com/questions/15782837/sed-to-replace-secret-key-in-django-settings-file-introduces-garbage):
```
SECRET_KEY=$(python -c 'import re;from random import choice; import sys; sys.stdout.write(re.escape("".join([choice("abcdefghijklmnopqrstuvwxyz0123456789^&*(-_=+)") for i in range(100)])))')
sudo sed --in-place "s/^SECRET_KEY = .*/SECRET_KEY = '${SECRET_KEY}'/" /usr/share/cobbler/web/settings.py
```

Finally: Basic configuration
-------------------

Replacing 127.0.0.1 in the cobbler settings file with the actual IP:

```
IP_ETH0=`ifconfig eth0 | grep 'inet addr:' | cut -d":" -f2 | cut -d" " -f1`
sudo sed -i "s/127\.0\.0\.1/${IP_ETH0}/" /etc/cobbler/settings
```

Restart cobblerd and apache2 and enjoy your new cobbler server:

```
sudo service apache2 restart
sudo service cobblerd restart
```

Epilogue
--------

Altogether none of this problems was really a big deal, but still it took us some time to figure out the details.
So we decided to spent even a bit more to write this blog post, with the indentation that it might be useful for others who are facing the same issues. And of course we are happy to contribute a bit back to the cobbler project, since it is (or will become) an important and central component of our provisioning toolchain.
