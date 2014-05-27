springerpe.github.io
====================

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
