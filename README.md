# XCODE Agile CSS Mixin Framework v.2.0.1
### Agile and Smart CSS coding library.


![Cross-Browser-Support](https://cloud.githubusercontent.com/assets/6649597/14348854/c04152a0-fcc7-11e5-9e5f-035d3a683d85.png)


Version
----

2.0.1


Usage
----
It is sufficient to include in your project.

```css
...
@import "xcode.css.mixin.fw";
...
```


Features
----
* **Functions »**

Description | Feature
------------ | -------------
» [Pixel converts the "em" format.](#-pixel-converts-the-em-format) | <ul><li>**@function x-convert_em()**</li><li>*Stated "px" is "em" that converts the format.*</li></ul>

* **Mixins »**

Description | Feature
------------ | -------------
» [CSS3 Prefix Adding.](#-css3-prefix-adding) | <ul><li>**@mixin x-prefix()**</li><li>*It adds support for browser features.*</li></ul>
» [Responsive Media Selector.](#-responsive-media-selector) | <ul><li>**@mixin x-media()**</li><li>*Add code for the specific screen resolutions.*</li></ul>
» [Alternate Responsive Media Selector.](#-alternate-responsive-media-selector) | <ul><li>**@mixin x-media-query()**</li><li>*Add code for different screen resolutions.*</li></ul>
» [Setting The Alpha Channel For Items. Support Cross Browser.](#-setting-the-alpha-channel-for-items) | <ul><li>**@mixin x-opacity()**</li><li>*It adds an alpha channel to the elements.*</li></ul>
» [Set Border Radius.](#-set-border-radius) | <ul><li>**@mixin x-border-radius()**</li><li>*Adds border radius.*</li></ul>
» [Set Shorthand Animation.](#-set-shorthand-animation) | <ul><li>**@mixin x-animation()**</li><li>*It allows you to enter a name and animation features.*</li></ul>
» [Animation Creator.](#-animation-creator) | <ul><li>**@mixin x-keyframes()**</li><li>*It allows us to define a new animation.*</li></ul>
» [Transition.](#-transition) | <ul><li>**@mixin x-transition()**</li><li>*Transitions allows you to change property values smoothly (from one value to another), over a given duration.*</li></ul>
» [2D Transforms.](#-2d-transforms) | <ul><li>**@mixin x-transform2d()**</li><li>*Transforms allow you to translate, rotate, scale, and skew elements.*</li></ul>
» [3D Transforms.](#-3d-transforms) | <ul><li>**@mixin x-transform3d()**</li><li>*Allows you to format your elements using 3D transformations.*</li></ul>
» [Change Input Placeholder Attributes.](#-change-input-placeholder-attributes) | <ul><li>**@mixin x-change-input-placeholder()**</li><li>*Use to change the input placeholders properties.*</li></ul>
» [Horizontal Navigation Bar.](#-horizontal-navigation-bar) | <ul><li>**@mixin x-horizontal-navbar()**</li><li>*Use it to add a horizontal menu.*</li></ul>
» [Vertical Navigation Bar.](#-vertical-navigation-bar) | <ul><li>**@mixin x-vertical-navbar()**</li><li>*Use it to add a vertical menu.*</li></ul>
» [Dropdown.](#-dropdown) | <ul><li>**@mixin x-dropdown()**</li><li>*Add drop-down.*</li></ul>
» [Tooltip.](#-tooltip) | <ul><li>**@mixin x-tooltip()**</li><li>*Add tooltip.*</li></ul>
» [Box Shadow.](#-box-shadow) | <ul><li>**@mixin x-box-shadow()**</li><li>*Add box shadow.*</li></ul>
» [Gradients.](#-gradients) | <ul><li>**@mixin x-gradient()**</li><li>*Add gradient.*</li></ul>
» [Image Filters.](#-image-filters) | <ul><li>**@mixin x-image-filter()**</li><li>*Use it to add effects or filter to images.*</li></ul>
» [Button animation.](#-button-animation) | <ul><li>**@mixin x-button-animation()**</li><li>*Create animated buttons.*</li></ul>
» [Font Icon.](#-font-icon) | <ul><li>**@mixin x-icon()**</li><li>*Add icon in the color and size you want. There are 693 icons.*</li></ul>
» [Font Selector.](#-font-selector) | <ul><li>**@mixin x-font()**</li><li>*Use practical way to add fonts to the elements.*</li></ul>
» [Menu Button.](#-menu-button) | <ul><li>**@mixin x-menu-button()**</li><li>*Add menu button for mobile views.*</li></ul>
» [Triangle.](#-triangle) | <ul><li>**@mixin x-triangle()**</li><li>*To add any element of the triangle.*</li></ul>

* **Helpers »**

Description | Feature
------------ | -------------
» [Clearfix.](#-clearfix) | <ul><li>**%x-clearfix**</li><li>*A quick way to clean areas that are used to float.*</li></ul>
» [Affix.](#-affix) | <ul><li>**%x-affix-top, %x-affix-bottom**</li><li>*Top or bottom to add a fixed area.*</li></ul>


Functions
----

##### `» Pixel converts the "em" format.`
* **Warning:** Specify the base font size before use. ($baseFontPixel default size 14px.)
* **Function Name:** @function x-convert_em($fontPx)

**Parameter Descriptions:**
* @param **$fontPx:** *Font Size.*
* @return em

**Usage:**
* SCSS:
```scss
p {
	font-size: x-convert_em(14px);
}
```


Mixins
----

##### `» CSS3 Prefix Adding.`
* **Mixin Name:** @mixin x-prefix($property, $args...)

**Parameter Descriptions:**
* @param **$property:** *Css property name. Ex. "transition", "border-radius"...*
* @param **$args:** *For the selected attribute values. Ex. "color .3s", "15px"...*

**Usage:**
* SCSS:
```scss
.box {
	Width: 300px;
	height: 300px;
	@include x-prefix("border-radius", 5px);
}
```


----
##### `» Responsive Media Selector.`
* **Mixin Name:** @mixin x-media($media)

**Parameter Descriptions:**
* @param **($media)** *Can take values:*
	* **$cellphone:** *Default size 320px.*
	* **$smartphone:** *Default size 480px.*
	* **$tablet:** *Default size 768px.*
	* **$desktop:** *Default size 992px.*
	* **$largeScreen:** *Default size 1200px.*
	* **null:** *When full screen. >1200px.*

**Usage:**
* SCSS:
```scss
nav[data="main-menu"] {
	@include x-media($desktop) {
		display: none;
	}
}
```


----
##### `» Alternate Responsive Media Selector.`
* This selective media can be entered in any desired resolution.
* **Mixin Name:** @mixin x-media-query($minMax: "max", $width)

**Parameter Descriptions:**
* @param **$minMax:** *min or max. Default value: "max". (min-width, max-width)*
* @param **($width)** *Can take values:*
	* **$cellphoneSize:** *Default size 320px.*
	* **$smartphoneSize:** *Default size 480px.*
	* **$tabletSize:** *Default size 768px.*
	* **$desktopSize:** *Default size 992px.*
	* **$largeScreenSize:** *Default size 1200px.*
	* **$fullScreenSize:** *>1200px.*
	* *Or any screen resolution size.*

**Usage:**
* SCSS:
```scss
nav.nav-content {
	@include x-media-query("min", $desktop) {
		display: none;
	}
}

h1.caption {
	@include x-media-query(300px) {
		font-size: 20%;
	}
}
```


----
##### `» Setting The Alpha Channel For Items.`
* **Mixin Name:** @mixin x-opacity($opacity: .85)

**Parameter Descriptions:**
* @param **$opacity:** *0..1*

**Usage:**
* SCSS:
```scss
a:hover {
	@include x-opacity(.7);
}
```


----
##### `» Set Border Radius.`
* **Mixin Name:** @mixin x-border-radius($radius)

**Parameter Descriptions:**
* @param **$radius:** *You know that ;)*

**Usage:**
* SCSS:
```scss
div.box {
	@include x-border-radius(15px);
}
```


----
##### `» Set Shorthand Animation.`
* **Tip:** *You can use this feature with keyframes*
* **Mixin Name:** @mixin x-animation($args...)

**Parameter Descriptions:**
* @param **$args:**
	* Animation name,
	* Duration,
	* Timing function,
	* Delay,
	* Iteration count,
	* Direction

**Usage:**
* SCSS:
```scss
div.anim {
	width: 100px;
	height: 100px;
	position: relative;
	background-color: red;

	@include x-animation('example 4s 3 alternate');
}
```


----
##### `» Animation Creator.`
* **Mixin Name:** @mixin x-keyframes($animationName)
* **Tip:** *[See those for features.][anim]*

**Parameter Descriptions:**
* @param **$animationName:** *Name of the animation. You can put any name.*

**Usage:**
* SCSS:
```scss
@include x-keyframes(example) {
	0%   {background-color: red; left:0px; top:0px;}
	25%  {background-color: yellow; left:200px; top:0px;}
	50%  {background-color: blue; left:200px; top:200px;}
	75%  {background-color: green; left:0px; top:200px;}
	100% {background-color: red; left:0px; top:0px;}
}

div.anim {
	width: 100px;
	height: 100px;
	position: relative;
	background-color: red;

	@include x-animation('example 4s 3 alternate');
}
```


----
##### `» Transition.`
* **Mixin Name:** @transition($args...)

**Parameter Descriptions:**
* @param **$args:**
	* Property,
	* Duration,
	* Timing function,
	* Delay

**Usage 1:**
* SCSS:
```scss
a {
	color: gray;
	@include x-transition(color .3s ease);

	&:hover {
		color: black;
	}
}
```
**Usage 2:**
* SCSS:
```scss
header.navbar {
	min-height: 60px;
	position: fixed;
	margin: 0 auto;

	@include x-transition(.4s);
}

.navbg-black {
	background-color: #000 !important;
}
```
* *header.navbar slowly change color to adding .navbg-black class.*


----
##### `» 2D Transforms.`
* **Mixin Name:** @mixin x-transform2d($method)
* **Tip:** *[See at examples](http://www.w3schools.com/css/css3_2dtransforms.asp)*

**Parameter Descriptions:**
* @param **$method:** Method name.
* Methods:
	* translate(x,y), translateX(n), translateY(n),
	* rotate(angle),
	* scale(x,y), scaleX(n), scaleY(n),
	* skew(x-angle, y-angle), skewX(angle), skewY(angle),
	* matrix(n,n,n,n,n,n)


**Usage:**
* SCSS:
```scss
div.rotate {
	@include x-transform2d(rotate(20deg));
}
```


----
##### `» 3D Transforms.`
* **Mixin Name:** @mixin transform3d($method)

**Parameter Descriptions:**
* @param **$method:** Method name.
* Methods:
	* translate3d(x,y,z), translateX(x), translateY(y), translateZ(z),
	* rotate3d(x,y,z,angle), rotateX(angle), rotateY(angle), rotateZ(angle),
	* scale3d(x,y,z), scaleX(x), scaleY(y), scaleY(z),
	* matrix3d(n,n,n,n,n,n,n,n,n,n,n,n,n,n,n,n),
	* perspective(n)

**Usage:**
* SCSS:
```scss
div.rotate {
	@include x-transform3d(rotateZ(90deg));
}
```


----
##### `» Change Input Placeholder Attributes.`
* **Mixin Name:** @mixin x-change-input-placeholder()
* Supported placeholder styles:
	* font
	* color
	* background
	* word-spacing
	* letter-spacing
	* text-decoration
	* vertical-align
	* text-transform
	* line-height
	* text-indent
	* opacity

**Usage:**
* SCSS:
```scss
input[type="email"] {
	@include x-change-input-placeholder() {
		color: orange;
	}
}
```


----
##### `» Vertical Navigation Bar.`
* **Mixin Name:** @mixin x-vertical-navbar(
	* **$width:** 100%,
	* **$bgColor:** #f1f1f1,
	* **$textColor:** #000,
	* **$textAlign:** left,
	* **$hoverBgColor:** #555,
	* **$hoverTextColor:** white,
	* **$activeLinkBgColor:** #4CAF50,
	* **$activeLinkTextColor:** white,
	* **$linkPadding:** 8px 0 8px 16px,
	* **$isFullHeight:** false,
	* **$isBorderRadius:** false,
  * **$radius:** 5px,
  * **$isBorder:** false,
  * **$borderSize:** 1px,
  * **$borderColor:** #d2d2d2,
  * **$isBoxShadow:** false,
  * **$shadowColor:** rgba(0, 0, 0, 0.2))

**Parameter Descriptions:**
* @param **$width:** *Navigation bar width. Default size: 100%.* **Tip:** *Percentage value enterable.*
* @param **$bgColor:** *Navigation bar background color. Default color: #f1f1f1.*
* @param **$textColor:** *Link text color. Default color: #000.*
* @param **$textAlign:** *Link text align. Default value: left.*
* @param **$hoverBgColor:** *Link hover background color. Default color: #555.*
* @param **$hoverTextColor:** *Link hover text color. Default color: #fff.*
* @param **$activeLinkBgColor:** *Active link background color. Default color: #4CAF50.*
* @param **$activeLinkTextColor:** *Active link text color. Default color: #fff.*
* @param **$linkPadding:** *Link paddind. Default value: 8px 0 8px 16px. [top, right, bottom, left].*
* @param **$isFullHeight:** *Full height navigation bar. Default value: false.*
* @param **$isBorderRadius:** *Navigation bar border radius. Default value: false.*
* @param **$radius:** *Border radius value. Default value: 5px.*
* @param **$isBorder:** *Navigation bar border adding. Default value: false.*
* @param **$borderSize:** *Border Size. Default value: 1px.*
* @param **$borderColor:** *Border Color. Default color: #d2d2d2.*
* @param **$isBoxShadow:** *Navigation bar shadow. Default value: false.*
* @param **$shadowColor:** *Shadow color. Default color: rgba(0, 0, 0, 0.2).*

**Usage 1:**
* SCSS:
```scss
#nav {
	@include x-vertical-navbar(300px);
}
```
* HTML:
```html
<div id="nav">
	<ul>
		<li><a class="active" href="#home">Home</a></li>
		<li><a href="#news">News</a></li>
		<li><a href="#contact">Contact</a></li>
		<li><a href="#about">About</a></li>
	</ul>
</div>
```

**Usage 2:**
* SCSS:
```scss
#nav {
	@include x-vertical-navbar($width:150px, $isFullHeight:true);
}
```
* HTML:
```html
<div id="nav">
	<ul>
		<li><a class="active" href="#home">Home</a></li>
		<li><a href="#news">News</a></li>
		<li><a href="#contact">Contact</a></li>
		<li><a href="#about">About</a></li>
	</ul>
</div>
```


----
##### `» Horizontal Navigation Bar.`
* **Mixin Name:** @mixin x-horizontal-navbar(
	* **$bgColor:** #333,
	* **$textColor:** white,
	* **$hoverBgColor:** #111,
	* **$activeLinkBgColor:** #4CAF50,
	* **$isDivider:** false,
	* **$dividerColor:** #bbb)

**Parameter Descriptions:**
* @param **$bgColor:** *Navigation bar background color. Default color: #333.*
* @param **$textColor:** *Link text color. Default color: #fff.*
* @param **$hoverBgColor:** *Link hover background color. Default color: #111.*
* @param **$activeLinkBgColor:** *Active link background color. Default color: #4CAF50.*
* @param **$isDivider:** *Divider inserts links. Default value: false.*
* @param **$dividerColor:** *Dividers color. Default color: #bbb.*

**Usage:**
* SCSS:
```scss
#nav {
	@include x-horizontal-navbar($isDivider:true);
}
```
* HTML:
```html
<div id="nav">
	<ul>
		<li><a class="active" href="#home">Home</a></li>
		<li><a href="#news">News</a></li>
		<li><a href="#contact">Contact</a></li>
		<li style="float:right"><a href="#about">About</a></li> <!-- right link element -->
	</ul>
</div>
```


----
##### `» Dropdown.`
* **Mixin Name:** @mixin x-dropdown(
	*	**$btnBgColor:** #4CAF50,
	*	**$btnTextColor:** white,
	*	**$contentWidth:** 160px,
	*	**$linkTextColor:** black,
	*	**$linkHoverBgColor:** #f1f1f1)

**Parameter Descriptions:**
* @param **$btnBgColor:** *Dropdown button background color. Default color: #4CAF50.*
* @param **$btnTextColor:** *Button text color. Default color: #fff.*
* @param **$contentWidth:** *Dropdown content width. Default value: 160px.*
* @param **$linkTextColor:** *Link text color. Default color: #000.*
* @param **$linkHoverBgColor:** *Link hover background color. Default color: #f1f1f1.*

**Usage:**
* SCSS:
```scss
#drop {
	 @include x-dropdown();
}
```
* HTML:
```html
<div id="drop">
	<div class="dropdown">
		<button class="dropbtn">Dropdown</button>
		<div class="dropdown-content">
			<a href="#">Link 1</a>
			<a href="#">Link 2</a>
			<a href="#">Link 3</a>
		</div>
	</div>
</div>
```


----
##### `» Tooltip.`
* **Mixin Name:** @mixin x-tooltip(
	*	**$position:** top,
	*	**$bgColor:** #000,
	*	**$textColor:** #fff,
	*	**$height:** 5px)

**Parameter Descriptions:**
* @param **$position:** *Tooltip position. Values(top, bottom, left, right). Default value: top.*
* @param **$bgColor:** *Tooltip background color. Default color: #000.*
* @param **$textColor:** *Tooltip text color. Default color: #fff.*
* @param **$height:** *Tooltip height. Default value: 5px.*

**Usage:**
* SCSS:
```scss
#tooltip {
	@include x-tooltip(bottom, $height: 10px);
}
```
* HTML:
```html
<div id="tooltip">
	<div class="tooltip">Hover over me
		<span class="tooltiptext">Tooltip text</span>
	</div>
</div>
```


----
##### `» Box Shadow.`
* **Mixin Name:** @mixin x-box-shadow($args...)

**Parameter Descriptions:**
* @param **$args:** *Values(Horizontal shadow, Vertical shadow, Blur, Shadow color)*

**Usage:**
* SCSS:
```scss
.box {
	width: 300px;
	height: 200px;
	@include x-box-shadow(0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19));
}
```
* HTML:
```html
<div class="box"></div>
```


----
##### `» Gradients.`
* **Mixin Name:** @mixin x-gradient($type: linear, $style: diagonal, $args...)
* **Tip:** *[See at examples.](http://www.w3schools.com/css/css3_gradients.asp)*

**Parameter Descriptions:**
* @param **$type:** *Values(linear or radial). Default value: linear.*
* @param **$style:** *Values(top-bottom, left-right, diagonal or angle). Default value: diagonal.*
* @param **$angle:** *Degree.* **Tip:** *Enter this value if selected style: angle. Default value: 45deg.*
* @param **$args:** *Color-stop#1, Color-stop#2...*

**Usage 1:**
* SCSS:
```scss
.grad {
	Width: 300px;
	height: 150px;
	@include x-gradient($args: #000, #fff);
}
```
* HTML:
```html
<div class="grad"></div>
```

**Usage 2:**
* SCSS:
```scss
.grad {
	Width: 300px;
	height: 150px;
	@include x-gradient($style: angle, $angle: -90deg, $args: #000, #fff);
}
```
* HTML:
```html
<div class="grad"></div>
```


----
##### `» Image Filters.`
* **Mixin Name:** @mixin x-image-filter($filterType: grayscale, $args...)
* **Warning:** IE not supported. EDGE supported.

**Parameter Descriptions:**
* @params **$filterType:** Filter type. Default value: grayscale.
	* **Filters can be applied:**
		* **blur:** *Applies a blur effect to the image. A larger value will create more blur. Argument value (px).*
		* **brightness:** *Adjusts the brightness of the image. Argument value (%).*
		* **contrast:** *Adjusts the contrast of the image. Argument value (%).*
		* **drop-shadow:** *Applies a drop shadow effect to the image. Argument value (h-shadow, v-shadow, blur, spread, color).*
		* **grayscale:** *Converts the image to grayscale.  Argument value (%).*
		* **hue-rotate:** *Applies a hue rotation on the image. Argument value (deg).*
		* **invert:** *Inverts the samples in the image. Argument value (%).*
		* **opacity:** *Sets the opacity level for the image. Argument value (%).*
		* **saturate:** *Saturates the image. Argument value (%).*
		* **sepia:** *Converts the image to sepia. Argument value (%).*
		* **url:** *The url() function takes the location of an XML file that specifies an SVG filter, and may include an anchor to a specific filter element.*
			* **Example:** *url(svg-url#element-id)*

**Usage 1:**
* SCSS:
```scss
.filter {
	@include x-image-filter(blur, 5px);
}
```
* HTML:
```html
<div class="filter>
	<img src="image.jpg">
</div>
```

**Usage 2:**
* SCSS:
```scss
#nav ul li a {
	@include x-image-filter($args: 100%);
	@include x-transition(.3s);

	&:hover {
  	@include x-image-filter($args: 0);
  }
}
```
* HTML:
```html
<div id="nav">
	<ul>
		<li><a href="#"><img src="link1.jpg"></a></li>
		<li><a href="#"><img src="link2.jpg"></a></li>
	</ul>
</div>
```


----
##### `» Button animation.`
* **Mixin Name:** @mixin x-button-animation($content: '»')
* **Tip:** *You can use icon fonts.*

**Parameter Descriptions:**
* @params **$content:** *Icon will appear when hovering over the button. Default value: '»'.*

**Usage:**
* SCSS:
```scss
.button {
	display: inline-block;
	border-radius: 4px;
	background-color: #555555;
	border: none;
	color: #FFFFFF;
	text-align: center;
	font-size: 28px;
	padding: 25px;
	width: 200px;
	cursor: pointer;
	margin: 5px;

	@include x-button-animation();
}
```
* HTML:
```html
<button class="button">
	<span>Hover</span>
</button>
```


----
##### `» Font Icon.`
* **Mixin Name:** @mixin x-icon(
	* $icon,
	* $direction: right,
	* $size: 14px,
	* $color: #000,
	* $padding: 0)
* **Tip:** *[See icon list.](https://fortawesome.github.io/Font-Awesome/icons/)*

**Parameter Descriptions:**
* @param **$icon:** *Icon name. Tip: See for icon list ($f-*)*
* @param **$direction:** *Icon direction. Default value: right.*
* @param **$size:** *Icon Size. Default size: 14px.*
* @param **$color:** *Icon color. Default color: #111.*
* @param **$padding:** *Icon padding. Default value: 0px.*

**Usage:**
* SCSS:
```scss
.chart {
	color: white;
	@include x-font('m', 20px);

	i {
		@include x-icon($f-bar-chart, $color: white);
	}
}
```
* HTML:
```html
<div class="chart">
  The Chart &nbsp;
  <i></i>
</div>
```


----
##### `» Font Selector.`
* **Mixin Name:** @mixin x-font(
	* $fontType: 'r',
	* $size: $baseFontPixel,
	* $spacing: 0.5px,
	* $fontName: $baseFontName)
* **Note:** Before use, enter the value of **$baseFontName.**
* **Warning:** Use this when you import the fonts to your project:
* CSS:
```css
@font-face {
	font-family: RobotoThin;
	src: url(font/roboto_thin.woff);
}
```
**Parameter Descriptions:**
* @param **$fontType:** *Values('t', 'l', 'r', 'm', 's', 'b')*
	* t: Thin.
	* l: Light.
	* r: Regular.
	* m: Medium.
	* s: Semibold.
	* b: Bold.
* @param **$size:** *Font size. Default value: Base font size.*
* @param **$spacing:** *Letter spacing. Default value: -0.5px.*
* @param **$fontName:** *Font name. Default value: Base font name.*

**Usage:**
* SCSS:
```scss
.caption {
	@include x-font('m', 18px);
}
```
* HTML:
```html
<p class="caption">This is a caption.</p>
```


----
##### `» Menu Button.`
* **Mixin Name:** @mixin x-menu-button(
	* **$color:** $white,
	* **$position:** right,
	* **$radius:** 2px,
	* **$thickness:** 3px,
	* **$width:** 30px,
	* **$isBorder:** false,
  * **$borderColor:** #222,
  * **$isBorderRadius:** false,
  * **$borderRadius:** 3px)

**Parameter Descriptions:**
* @param **$color:** *Line color. Default color: #fff.*
* @param **$position:** *Menu button position. Default value: right.*
* @param **$radius:** *Line border radius. Default value: 2px.*
* @param **$thickness:** *Line thickness. Default value: 3px.*
* @param **$width:** *Line width. Default value: 30px.*
* @param **$isBorder:** *Menu button border. Default value: false.*
* @param **$borderColor:** *Border color. Default color: #222.*
* @param **$isBorderRadius:** *Menu button border radius. Default value: false.*
* @param **$borderRadius:** *Border radius. Default value: 3px.*

**Usage:**
* SCSS:
```scss
#menu-btn {
	@include x-menu-button($radius:0);
}

//Paste this is class main CSS file.
.menu-active {
	a span {
		background-color: transparent !important;

		&:before, &:after {
			top: 0px !important;
			background-color: #fff !important;
		}

		//If the position of the button is left, change in the plus with the minus.
		&:before {@include x-transform2d(rotate(45deg))}
		&:after {@include x-transform2d(rotate(-45deg))}
	}
}
```

* HTML:
```html
<nav>
	<ul>
		<li><a class="active" href="#">Home</a></li>
		<li><a href="#">News</a></li>
		<li><a href="#">Contact</a></li>
		<li id="menu-btn">
			<a href="#">
				<span></span>
			</a>
		</li>
	</ul>
</nav>
```

* JAVASCRIPT(JQUERY):
```js
$("#menu-btn").click(function() {
	$(this).toggleClass("menu-active");
	return false;
});
```


----
##### `» Triangle.`
* **Mixin Name:** @mixin x-triangle(
	* **$color:** #111,
	* **$direction:** up,
	* **$position:** center,
	* **$indent:** 8px,
	* **$size:** 10px)

**Parameter Descriptions:**
* @param **$color:** *Triangle color. Default color: #111.*
* @param **$direction:** *Triangle direction. Values: {up, down, left, right}*
* @param **$position:** *Triangle position. Default value: center.* **Tip:** *Value can be specified in "px".*
* @param **$indent:** *Triangle indentation. Default value: 8px.*
* @param **$size:** *Triangle size. Default size: 10px.*

**Usage:**
* SCSS:
```scss
.triangle {
	position: relative;
	width: 150px;
	padding: 10px 20px;
	background-color: #813efa;
	text-align: center;
	color: $white;
	font-size: 20px;

	@include x-border-radius(5px);
	@include x-triangle(#813efa, right);
}
```

* HTML:
```html
<div class="triangle">
	Triangle
</div>
```


Helpers
----
##### `» Clearfix.`
* **Helper Name:** %x-clearfix

**Usage:**
* SCSS:
```scss
.container {
	background-color: #f1f1f1;
	@extend %x-clearfix;
}

.wrapper {
	width: 300px;
	height: 200px;
	float: left;
	background-color: #222;
	margin: 10px;
}
```
* HTML:
```html
<div class="container">
	<div class="wrapper"></div>
	<div class="wrapper"></div>
</div>
```


----
##### `» Affix.`
* Helper Name: %x-affix-top, %x-affix-bottom

**Usage:**
* SCSS:
```scss
.bottom-menu {
	height: 200px;
	@extend %x-affix-bottom;
}
```
* HTML:
```html
<div class="bottom-menu"></div>
```


Tools
----
##### `» 12 Columns Responsive Grid System.`
> 12 column grid system that is fully compatible with the `xcode` library.

**Usage:**
* *Use main layout adding:*
```erb
...
<%= stylesheet_link_tag :grid12 %>
...
```


----
##### `» 16 Columns Responsive Grid System.`
> 16 column grid system that is fully compatible with the `xcode` library.

**Usage:**
* *Use main layout adding:*
```erb
...
<%= stylesheet_link_tag :grid16 %>
...
```


----
##### `» Reset CSS.`
> Structured according to these libraries css reset. **Tip:** *This is already attached to the grid system.*


Version History
----

**v.1.0.0**
* First version.

**v.1.1.0**
* **Mixin added:** Horizontal Navigation Bar.
* **Mixin added:** Vertical Navigation Bar.
* **Mixin added:** Dropdown.

**v.1.2.0**
* **Mixin added:** Tooltip.
* **Mixin added:** Box Shadow.
* **Mixin added:** Gradients.
* **Mixin added:** Image Filter.

**v.1.2.1**
* **Minor fixed:** @mixin x-prefix($property, $args...)
	* Rewritten DRY.
* **Mixin deprecated:** @mixin grayscale($percent)
	* Instead of Image Filter use.

**v.1.3.0**
* **Mixin added:** Button to add animation.
* **Mixin added:** Font Icon.

**v.1.3.1**
* **Minor fixed:** Font path.
* **License added:** Font Avesome.
* **ReadMe:** Improved.

**v.1.4.0**
* **Mixin added:** Font Selector.

**v.1.4.1**
* **Minor fixed:** Improvements were made.

**v.1.4.2**
* **Minor fixed:** @mixin h-navigation-bar() name changed to h-navbar()
* **Minor fixed:** @mixin v-navigation-bar() name changed to v-navbar()
* **ReadMe:** More understandable.

**v.1.5.0**
* **Helper added:** Clearfix.
* **Helper added:** Affix.

**v.1.5.1**
* **Tool added:** 12 Columns Responsive Grid System.
* **Tool added:** 16 Columns Responsive Grid System.
* **Tool added:** Reset CSS.

**v.1.5.2**
* **Minor fixed:** %affix change name to %affix-top, %affix-bottom
* **Minor fixed:** normalize.css bug fixed.

**v.1.5.3**
* **Minor fixed:** Grid and normalize extension changed to ".scss"
* **Minor fixed:** CSS Reset was included in the grid system.
* **Minor fixed:** Font path changed. (../fonts/).
* **Minor fixed:** Add the icon font, sample code changed.
* **Minor fixed:** Tools folder was deleted and the contents were moved to the main index.

**v.1.6.0**
* **Mixin added:** Menu Button.

**v.1.6.1**
* **Minor change:** 480px removed to grid system.
* **Minor change:** *$padding* added variable grid system.
* **Improvement:** @mixin x-media-query(), has been made more convenient.
* **Error fixed:** 16 columns grid system bug fixed.
* **Minor fixed:** @mixin h-navbar() and @mixin v-navbar(): The name confusion was fixed.
* **Minor change:** "12columnsGrid" file name changed to "grid12".
* **Minor change:** "16columnsGrid" file name changed to "grid16".

**v.1.7.0**
* **Mixin added:** Triangle.

**v.1.7.1**
* **Minor fixed:** @mixin x-font() -> Will alert "$baseFontName" value is not entered.

**v.2.0.0**
* **Mixin deleted:** @mixin grayscale($percent).
* **Minor fixed:** @mixin x-horizontal-navbar() -> Link width and height adjustable.
* **Minor fixed:** @mixin x-menu-button() -> Border option added.
* **Minor fixed:** Edited all of the descriptions in the library.
* **Major fixed:** All mixins and functions prefix "x" was added.

**v.2.0.1**
* **Minor fixed:** @mixin x-media-query() -> Variable is $minMax adding default value "max".
* **Mixin changed:** @mixin x-vertical-navbar() ->
  * **Default value changed:** $width: 200px change to $width: 100%.
  * **New variable added:** $textAlign. Values(left, center, right). Default value: left.
  * **New variable added:** $linkPadding. Values(top, right, bottom, left). Default value: 8px 0 8px 16px.
  * **New variable added:** $isBorderRadius. Values(true or false). Default value: false.
  * **New variable added:** $radius. Default value: 5px.
  * **New variable added:** $isBorder. Values(true or false). Default value: false.
  * **New variable added:** $borderSize. Default value: 1px.
  * **New variable added:** $borderColor. Default color: #d2d2d2.
  * **New variable added:** $isBoxShadow. Values(true or false). Default value: false.
  * **New variable added:** $shadowColor. Default color: rgba(0, 0, 0, 0.2).
  * **Class fixed:** This .active class change it. Adding "!important ".
* **Mixin changed:** @mixin x-horizontal-navbar() ->
  * **New variable added:** $isCenter. Default value: false.
  * **Class fixed:** This .active class change it. Adding "!important ".
* **Minor fixed and changed:** @mixin x-menu-button() ->
  * **Class fixed:** This .menu-active class changed.Change in the plus with the minus.
  * **New variable added:** $isBorderRadius. Values(true or false). Default value: false.
  * **New variable added:** $borderRadius. Default value: 3px.
* **Minor fixed:** @mixin x-triangle() -> Added browser support feature.


Author
----
Levent Özbilgiç - XCODE


License
----

* [MIT](https://github.com/ozbilgic/sass-mixin-css-framework/blob/master/LICENSE) 2016 - XCODE
* [Font Avesome](https://fortawesome.github.io/Font-Awesome/license/)
* [Bootstrap](https://github.com/twbs/bootstrap/blob/master/LICENSE)
* [Normalize.css](https://github.com/necolas/normalize.css/blob/master/LICENSE.md)


[anim]:<http://www.w3schools.com/cssref/css_animatable.asp>