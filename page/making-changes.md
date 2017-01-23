 - [Initial set up from ZIP](https://github.com/ninefortyone/working-with-us/blob/master/page/set-up-zip.md)
 - [Initial set up with Bitbucket](https://github.com/ninefortyone/working-with-us/blob/master/page/set-up-bitbucket.md)
 - [Making changes](https://github.com/ninefortyone/working-with-us/blob/master/page/making-changes.md)

# Making Changes

Each Theme we build is built on top of [Startline](https://github.com/ninefortyone/startline). When the project is handed over to you the Theme will be under a different name, but it's important to know its foundation. *With this is mind, any code examples in this document that reference `startline` will need to be replaced with the name of the theme you're working with.*

We base our WordPress Themes off of Startline as it acts as a starting point for themes that use both [Twitter Bootstrap](http://getbootstrap.com/) and [Font Awesome](http://fontawesome.io/). It also comes bundled with the [HTML5 Shiv](https://github.com/aFarkas/html5shiv) and [Respond.js](https://github.com/scottjehl/Respond) utilities. Therefore it saves us a bunch of work upfront :godmode:

Therefore all markup and CSS should be written inline with [Twitter Bootstrap's guidelines](http://getbootstrap.com/css/). In addition to this, any JavaScript should be written in [jQuery](https://jquery.com/) and all icons should be from the [Font Awesome library](http://fontawesome.io/icons/)

The CSS is written using Sass. You **must use Sass** when editing the stylesheets.

Once the [Theme is installed](https://github.com/ninefortyone/working-with-us/blob/master/set-up.md), edit the Sass files within the `wp-content/themes/startline/scss/` directory and run the Sass watch command:

```
$ cd wp-content/themes/startline
$ sass --watch scss/main.scss:css/main.min.css
```

Any changes you make to the Sass files thereafter are *automatically* written to the Theme's CSS directory `wp-content/themes/startline/css/`. Just refresh your browser as usual and you'll see your changes.

## A more detailed look

Within the Theme, you'll notice we've laid out the structure already.

Your working directories are:

`scss/` - All CSS files.

`js/` - All JavaScript files.

`img/` - All image assets.

Directories you don't need to modify are:

`css/` - Only the `$ sass --watch` command should write to this directory.

`fonts/` - Only the `$ sass --watch` command should write to this directory.

`node_modules/` - Only the `$ npm` command should write to this directory.

**If you're making changes to a ZIP archive, please keep a list of the Sass, JavaScript and image files you've changed. We'll need this list to be able to depoy the changes to our staging server for review.**

## Making changes to Twitter Bootstrap core

If you need to make changes to the core of Bootstrap (let's say you wanted to adjust the media query width for `screen-xs` from 480px to 500px) then you do so in `wp-content/themes/startline/scss/main.scss`. 

At the top of this file you'll see a section (`//== Overrides`) where you can override variables before Bootstrap is loaded.

```css
//
// Bootstrap
// --------------------------------------------------

//== Overrides
$icon-font-path: "../node_modules/bootstrap-sass/assets/fonts/bootstrap/";

//== Import
@import "../node_modules/bootstrap-sass/assets/stylesheets/bootstrap";

...
```

You would then add the variable to the `//== Overrides` section like this:

```css
//
// Bootstrap
// --------------------------------------------------

//== Overrides
$icon-font-path: "../node_modules/bootstrap-sass/assets/fonts/bootstrap/";

// Changing the default value of $screen-xs.
$screen-xs: 500px;

//== Import
@import "../node_modules/bootstrap-sass/assets/stylesheets/bootstrap";

...
```

Then as soon you save `main.scss`, Bootstrap is recompiled with it's core variables changed.

A full list of the Bootstrap variables that can be overwritten are found in `wp-content/themes/startline/node_modules/bootstrap-sass/assets/stylesheets/bootstrap/_variables.scss`
