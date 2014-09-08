springerpe.github.io
====================

This the Springer Platform Engineering Team official blog: http://springerpe.github.io

It is based Jekyll (template based web edition engine), hosted in GitHub using GitHub pages.

Setup Environment
---------------

You need to have installed ruby and jekyll to work with this page. The best option is just have RVM installed: http://rvm.io/

To setup the environment with RVM:

```
# Install RVM: http://rvm.io/
\curl -sSL https://get.rvm.io | bash -s stable

# Setup the right version or ruby
rvm install 1.9.3

# create a new gemset 
rvm gemset use 1.9.3@jekyll --create

# Install all the dependencies
bundle install 
```

Adding new posts
------------------

 1. Edit the posts or add new posts in `\_posts/`
 2. Add images in images
 3. Check how you see it with: `jekyll serve` and go to http://0.0.0.0:4000
 4. Add everything with git and push the changes
 5. Check the results in http://springerpe.github.io


Adding a new author
-------------------

You must edit the \_config.yml file to add the new author. 


Documentation
-------------

More information about jekyll template language and github pages here:

 * Github Jekyll pages: https://help.github.com/articles/using-jekyll-with-pages
 * Jekyll official page http://jekyllrb.com/
 * Jekyll template guide: http://jekyllrb.com/docs/templates/
 * Markdown language reference: http://daringfireball.net/projects/markdown/


About images
------------

Unless required, try to keep images small, to make the downloading quicker. The recomendation is:

 * Max 600px width
 * png with ~70% quality
 * optipng run

You can use these commandline tools:

 * `convert file.jpg file.png`
 * `convert -resize 600 file.png file.png`
 * `pngquant -s 1 -v *.png`
 * `optipng file.png`
 
TODO: Create rake task to automate image optimization.
