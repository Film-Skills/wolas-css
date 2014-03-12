WOLASCSS
=========

A CSS framework for all WOLAS based products and services. This framework includes a responsive grid system, form and input styling, basic typography, table styles, a card system, and an icon font.

## Basics

Base classes and default settings that make up WOLASCSS. Also contains instructions on how to make changes to the CSS styles.

### HTML and Body Styles

These basic styles define the 100% width and height for the grids, as well as the default body font.

```
// Reset body width, height, margin and padding for the grid.
html, body {
	width: 100%;
	height: 100%;
	padding: 0;
	margin: 0;

	// Set some basic body fonts, just in case
	font-family: 'open_sansregular', 'Helvetica Neue', Helvetica, Arial, Sans-Serif;
	font-size: 14px;
	line-height: 1.6em;
}
// Add padding for the nav, because it is fixed.
body {
	padding-top: 55px;
}
```

### Utility Classes

These classes are .hide and .clearfix. .hide stops an element from showing on the page and .clearfix is used after floated elements to allow the elements after them to align correctly.

```
// Utility classes for common functionality.
.hide { display: none; }
.clearfix { clear: both; }
```
	
### Border-Box Model

See the article http://www.paulirish.com/2012/box-sizing-border-box-ftw/ to see what the border-box model for CSS is. Basically it makes it so borders and padding do not affect the overall width of an element as they usually do. The width stays content and it puts the padding and the border inside the element, so to speak.

```
/* 
 * Apply the border-box model to all elements to fix padding and border issues.
 * http://www.paulirish.com/2012/box-sizing-border-box-ftw/
 */

*, *:after, *:before {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
```

### SASS and Compass

WOLASCSS is built using SASS, which is a CSS extension language which adds features like variables, nesting, and mixins to CSS, which makes it a lot easier to code and manage. Check it out at http://sass-lang.com/. We then use Compass, which is a library of SASS mixins already built like darken and tone etc., as well as a CSS reset. Compass also watches the project directory for CSS changes and then compiles the CSS into a minified, concatenated single CSS file from multiple files.

You must open the project folder in cmd and then run the command compass watch . to watch the directory for CSS changes. If you don't do this the css will not be built, so your changes won't work. Compass requires ruby, rubygems and the compass gem. See the compass website for more details http://compass-style.org/.

### How to Change & Version
The following is a step by step process on how to make changes to WOLAS-CSS.

1. Make sure you have ruby installed on your computer and if on Windows added to the PATH variable. It should be installed by default on Mac but for on Windows read this article: [Ruby on Windows](http://www.martin-brennan.com/install-ruby-and-rubygems-on-windows/)
2. Navigate to your wolas-css project directory using the command line.
3. If you don't have the `compass` gem installed, run `gem install compass` [Compass](http://compass-style.org/)
4. Once done, run the command `compass watch .` . That makes compass watch the current directory for CSS changes.
5. Make changes in the CSS partials in the scss folder or make new partials and include them in style.scss
6. Once done press `Ctrl+C` in the command window to stop compass watch
7. You can then commit + push

The versions are located on Amazon S3 and delivered through a CloudFront URL from https://d1ldb0f4tbur5g.cloudfront.net/css/wolascss/#.#.#/css/screen.css where #.#.# is the semantic version number. The demo pages can also be accessed from the same URL e.g. the base page is at https://d1ldb0f4tbur5g.cloudfront.net/css/wolascss/#.#.#/base.html. If a new version needs to be made, a new folder with the latest version number must be made in the css/wolascss folder in the cdn.wolas.com.au bucket on S3.
