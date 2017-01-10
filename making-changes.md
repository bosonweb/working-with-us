# Making Changes

Each Theme we build is built on top of [Startline](https://github.com/ninefortyone/startline). 

Startline  acts as a starting point for themes that use both [Twitter Bootstrap](http://getbootstrap.com/) and [Font Awesome](http://fontawesome.io/). It also comes bundled with the [HTML5 Shiv](https://github.com/aFarkas/html5shiv) and [Respond.js](https://github.com/scottjehl/Respond) utilities.

Therefore all markup and CSS should be written inline with [Twitter Bootstrap's guidelines](http://getbootstrap.com/css/). In addition to this, any JavaScript should be written in [jQuery](https://jquery.com/) and all icons should be from the [Font Awesome library](http://fontawesome.io/icons/)

The CSS is written using Sass. You must use Sass when editing the stylesheets.

Once the Theme is installed, edit the Sass files within the `scss/` directory and run the Sass watch command

```
$ cd wp-content/themes/startline
$ sass --watch scss/main.scss:css/main.min.css
```

Any changes you make to the Sass files thereafter are automatically written to the Theme's CSS files.
