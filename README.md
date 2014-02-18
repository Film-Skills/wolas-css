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
