# What is Threes

Threes (pronounce "Threez") stands for "Simple Semantic Styles". It is a very simple Sass partial file you can @import in your main .scss styles file.

If you do not like semantic CSS styles, this is not for you! Indeed, Threes aims at splitting styles in an extreme way making your HTML markup heavier than you may be used to.

#### Example for creating a 1px border on a div, your markup looks like this:

`<div class="bd bd-1 color1-bd">My content</div>`

This means:

* __bd__: apply border to the element
* __bd-1__: `border-width` is 1px
* __color1-bd__: `border-color` is the one of the first color defined in Threes config

And you can combine it with your other existing classes.

If you have a `footer` class, you can write:

`<div class="footer bd bd-1 color1-bd">My content</div>`


### Requirements

* have basic knowledge with Sass
* be "semantic-styles minded"


# Installation

## With modman

Into your Magento installation directory:

`modman clone https://github.com/herveguetin/Herve_Threes.git`

(running modman init may be required)

## Other

Just download the archive and install as usual.

# Configuration

## Defining colors

Threes allows you to use as many colors as you like. On Sass compile, your colors will be converted in text color, border color and background color.

To define your colors:

* Edit _threes.scss
* In `$threes_colors` variable, add your color codes in a Sass list way
* Each color will then be named color1, color2, color3, etc... in the compiled CSS file

#### Example

Let's say your `$threes_colors` is like this:

	$threes_colors: (
		#333333, // color1
		#666666 // color2, etc
	);

You then have defined 2 colors. Threes will generate the following css classes:

	.color1-tx { color: #333333; }
	.color1-bd { border-color: #333333; }
	.color1-bg { background-color: #333333; }
	.color2-tx { color: #666666; }
	.color2-bd { border-color: #666666; }
	.color2-bg { background-color: #666666; }

## Defining margins, paddings, borders and font sizes

Threes allows you to create ranges of margins, paddings, borders and font sizes. For each of those, you can define a minimum value, a maximum value and a step.

Configuration principle is similar for all of them.

#### Example to define your margins

Uncomment the following lines

	$threes_marginMin: 5;
	$threes_marginMax: 50;
	$threes_marginStep: 5;

This means: create margin classes from 5px to 50px, each 5px.

Then, on Sass compile, this will create:

	.mg-5 { margin: 5px; }
	.mg-5-t { margin-top: 5px; }
	.mg-5-r { margin-right: 5px; }
	.mg-5-b { margin-bottom: 5px; }
	.mg-5-l { margin-left: 5px; }
	
	.mg-10 { margin: 510px; }
	.mg-10-t { margin-top: 10px; }
	.mg-10-r { margin-right: 10px; }
	.mg-10-b { margin-bottom: 10px; }
	.mg-10-l { margin-left: 10px; }

... same thing every 5px up to 50px.

#### Example to define your font sizes

This is the same as explained above for the margins.

	$threes_fontSizeMin: 8;
	$threes_fontSizeMax: 18;
	$threes_fontSizeStep: 2;
	
This means: create font-size classes from 8px to 18px, each 2px.

Then, on Sass compile, this will create:

	.ft-sz-8 { font-size: 8px; }
	.ft-sz-10 { font-size: 10px; }

... same thing every 2px up to 18px.

# Going further

Threes comes with a bunch of CSS tool-classes in order to set `position`, `float`, `display`, `visibility`, `overflow`, typographic styles, ...

You are then very welcomed to read thru the `_threes.scss` file to see how they work!