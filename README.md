# Sass Mixins CSS Framework - (Mixins Library)
### Agile and Smart CSS coding library.


![Cross-Browser-Support](https://cloud.githubusercontent.com/assets/6649597/14348854/c04152a0-fcc7-11e5-9e5f-035d3a683d85.png)


Version
----

1.4.1


Usage
----
It is sufficient to include in your project.

```css
...
@import "xcode.css.mixins.fw";
...
```


Functions
----

##### `» Pixel converts the "em" format.`
* **Warning:** Specify the base font size before use. ($baseFontPixel default size 16px.)
* **Function Name:** @convert_em($fontPx)

**Parameter Descriptions:**
* @param **$fontPx:** *Font Size.*
* @return em

**Usage:**
```scss
p {
	font-size: convert_em(14px);
}
```


Mixins
----

##### `» CSS3 Prefix Adding.`
* **Mixin Name:** @prefix($property, $args...)

**Parameter Descriptions:**
* @param **$property:** *Css property name. Ex. "transition", "border-radius"...*
* @param **$args:** *For the selected attribute values. Ex. "color .3s", "15px"...*

**Usage:**
```scss
.box {
	Width: 300px;
	height: 300px;
	@include prefix(border-radius, 5px);
}
```


----
##### `» Responsive Media Selector.`
* **Mixin Name:** @media($media)

**Parameter Descriptions:**
* @param **$media:**
	* **$cellphone:** *Default size 320px.*
	* **$smartphone:** *Default size 480px.*
	* **$tablet:** *Default size 768px.*
	* **$desktop:** *Default size 992px.*
	* **$largeScreen:** *Default size 1200px.*
	* **nil:** *When full screen. >1200px.*

**Usage:**
```scss
nav[data="main-menu"] {
	@include media($desktop) {
		display: none;
	}
}
```


----
##### `» Alternate Responsive Media Selector.`
This selective media can be entered in any desired resolution.
* **Mixin Name:** @media-query($minMax, $width, $eWidth: 0)

**Parameter Descriptions:**
* @param **$minMax:** *min or max. (min-width, max-width)*
* @param **$width, $eWidth:**
	* **$cellphoneSize:** *Default size 320px.*
	* **$smartphoneSize:** *Default size 480px.*
	* **$tabletSize:** *Default size 768px.*
	* **$desktopSize:** *Default size 992px.*
	* **$largeScreenSize:** *Default size 1200px.*
	* **$fullScreenSize:** *>1200px.*
* @param **$eWidth:** *Any screen resolution size.*

**Usage:**
```scss
nav.nav-content {
	@include media-query(min, $desktop) {
		display: none;
	}
}

h1.caption {
	@include media-query(max, nil, 300px) {
		font-size: 20%;
	}
}
```


----
##### `» Setting The Alpha Channel For Items. Support Cross Browser.`
* **Mixin Name:** @opacity($opacity: .85)

**Parameter Descriptions:**
* @param **$opacity:** *0..1*

**Usage:**
```scss
a:hover {
	@include opacity(.7)
}
```


----
##### `» Set Border Radius.`
* **Mixin Name:** @border-radius($radius)

**Parameter Descriptions:**
* @param **$radius:** *You know that ;)*

**Usage:**
```scss
div.box {
	@include border-radius(15px)
}
```


----
##### `» Set Shorthand Animation.`
* **Tip:** *You can use this feature with keyframes*
* **Mixin Name:** @animation($args...)

**Parameter Descriptions:**
* @param **$args:** *{
          	Animation name,
            Duration,
            Timing function,
            Delay,
            Iteration count,
            Direction
          }*

**Usage:**
```scss
div.anim {
	width: 100px;
	height: 100px;
	position: relative;
	background-color: red;
	@include animation('example 4s 3 alternate');
}
```


----
##### `» Animation Creator.`
* **Mixin Name:** @keyframes($animationName)
* **Tip:** *[See those for features][anim]*

**Parameter Descriptions:**
* @param **$animationName:** *Name of the animation. You can put any name.*

**Usage:**
```scss
@include keyframes(example) {
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
	@include animation('example 4s 3 alternate');
}
```


----
##### `» Transition.`
* **Mixin Name:** @transition($args...)

**Parameter Descriptions:**
* @param **$args:** *{
            Property,
            Duration,
            Timing function,
            Delay
          }*

**Usage 1:**
```scss
a {
	color: gray;
	@include transition(color .3s ease);

	&:hover {
		color: black;
	}
}
```
**Usage 2:**
```scss
header.navbar {
	min-height: 60px;
	position: fixed;
	margin: 0 auto;
	@include transition(.4s);
}

.navbg-black {
	background-color: #000 !important;
}
```
* *header.navbar slowly change color to adding .navbg-black class.*


----
##### `» 2D Transforms.`
* **Mixin Name:** @transform2d($method)
* **Tip:** *[See at examples](http://www.w3schools.com/css/css3_2dtransforms.asp)*

**Parameter Descriptions:**
* @param **$method:** Method name.
* Method List
	* translate(x,y), translateX(n), translateY(n),
	* rotate(angle),
	* scale(x,y), scaleX(n), scaleY(n),
	* skew(x-angle, y-angle), skewX(angle), skewY(angle),
	* matrix(n,n,n,n,n,n)


**Usage:**
```scss
div.rotate {
	@include transform2d(rotate(20deg));
}
```


----
##### `» 3D Transforms.`
* **Mixin Name:** @transform3d($method)

**Parameter Descriptions:**
* @param **$method:** Method name.
* Method List
	* translate3d(x,y,z), translateX(x), translateY(y), translateZ(z),
	* rotate3d(x,y,z,angle), rotateX(angle), rotateY(angle), rotateZ(angle),
	* scale3d(x,y,z), scaleX(x), scaleY(y), scaleY(z),
	* matrix3d(n,n,n,n,n,n,n,n,n,n,n,n,n,n,n,n),
	* perspective(n)

**Usage:**
```scss
div.rotate {
	@include transform3d(rotateZ(90deg));
}
```


----
##### `» Change Input Placeholder Attributes.`
* **Mixin Name:** @change-input-placeholder()
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
```scss
input[type="email"] {
	@include change-input-placeholder() {
		color: orange;
	}
}
```


----
##### `» Change The Color of All Images to Black and White. - DEPRECATED`
* **Note:** Instead of Image Filter use.
* **Mixin Name:** @grayscale($value)
* **Tip:** *0..100, 100 full gray.*
* **Warning:** IE not supported.

**Parameter Descriptions:**
* @param **$value:** *Percent.*

**Usage:**
```scss
img.poster {
	@include grayscale(20%);
}
```


----
##### `» Horizontal Navigation Bar.`
* **Mixin Name:** @h-navigation-bar(
	* **$width:** 200px,
	* **$bgColor:** #f1f1f1,
	* **$textColor:** #000,
	* **$hoverBgColor:** #555,
	* **$hoverTextColor:** white,
	* **$activeLinkBgColor:** #4CAF50,
	* **$activeLinkTextColor:** white,
	* **$isFullHeight:** false)

**Parameter Descriptions:**
* @param **$width:** *Navigation bar width. Default size: 200px.* **Tip:** *Percentage value enterable.*
* @param **$bgColor:** *Navigation bar background color. Default color: #f1f1f1.*
* @param **$textColor:** *Link text color. Default color: #000.*
* @param **$hoverBgColor:** *Link hover background color. Default color: #555.*
* @param **$hoverTextColor:** *Link hover text color. Default color: #fff.*
* @param **$activeLinkBgColor:** *Active link background color. Default color: #4CAF50.*
* @param **$activeLinkTextColor:** *Active link text color. Default color: #fff.*
* @param **$isFullHeight:** *Full height navigation bar. Default value: false.*

**Usage 1:**
```scss
#nav {
	@include h-navigation-bar(300px);
}

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
```scss
#nav {
	@include h-navigation-bar($width:150px, $isFullHeight:true);
}

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
##### `» Vertical Navigation Bar.`
* **Mixin Name:** @mixin v-navigation-bar(
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
```scss
#nav {
	@include v-navigation-bar($isDivider:true);
}

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
* **Mixin Name:** @mixin dropdown(
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
```scss
#drop {
	 @include dropdown();
}

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
* **Mixin Name:** @mixin tooltip(
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
```scss
#tooltip {
	@include tooltip(bottom, $height: 10px);
}

<div id="tooltip">
	<div class="tooltip">Hover over me
		<span class="tooltiptext">Tooltip text</span>
	</div>
</div>
```


----
##### `» Box Shadow.`
* **Mixin Name:** @mixin box-shadow($args...)

**Parameter Descriptions:**
* @param **$args:** *Values(Horizontal shadow, Vertical shadow, Blur, Shadow color)*

**Usage:**
```scss
.box {
	width: 300px;
	height: 200px;
	@include box-shadow(0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19));
}

<div class="box"></div>
```


----
##### `» Gradients.`
* **Mixin Name:** @mixin gradient($type: linear, $style: diagonal, $args...)
* **Tip:** *[See at examples.](http://www.w3schools.com/css/css3_gradients.asp)*

**Parameter Descriptions:**
* @param **$type:** *Values(linear or radial). Default value: linear.*
* @param **$style:** *Values(top-bottom, left-right, diagonal or angle). Default value: diagonal.*
* @param **$angle:** *Degree.* **Tip:** *Enter this value if selected style: angle. Default value: 45deg.*
* @param **$args:** *Color-stop#1, Color-stop#2...*

**Usage 1:**
```scss
.grad {
	Width: 300px;
	height: 150px;
	@include gradient($args: #000, #fff);
}

<div class="grad"></div>
```

**Usage 2:**
```scss
.grad {
	Width: 300px;
	height: 150px;
	@include gradient($style: angle, $angle: -90deg, $args: #000, #fff);
}

<div class="grad"></div>
```


----
##### `» Image Filter.`
* **Mixin Name:** @mixin image-filter($filterType: grayscale, $args...)
* **Warning:** IE not supported.

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
```scss
.filter {
	@include image-filter(blur, 5px);
}

<div class="filter>
	<img src="image.jpg">
</div>
```

**Usage 2:**
```scss
#nav ul li a {
	@include image-filter($args: 100%);
	@include transition(.3s);

	&:hover {
  	@include image-filter($args: 0);
  }
}

<div id="nav">
	<ul>
		<li><a href="#"><img src="link1.jpg"></a></li>
		<li><a href="#"><img src="link2.jpg"></a></li>
	</ul>
</div>
```


----
##### `» Button to add animation.`
* **Mixin Name:** @mixin add-button-animation($content: '»')

**Parameter Descriptions:**
* @params **$content:** *Icon will appear when hovering over the button. Default value: '»'.*

**Usage:**
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

	@include add-button-animation();
}

<button class="button">
	<span>Hover</span>
</button>
```


----
##### `» Add Font Icon.`
* **Mixin Name:** @mixin add-font-icon($icon, $direction: right, $size: 14px, $color: #000 $padding: 0)
* **Tip:** *[Icon list.](https://fortawesome.github.io/Font-Awesome/icons/)*

**Parameter Descriptions:**
* @param **$icon:** *Icon name. Tip: See for icon list ($f-*)*
* @param **$direction:** *Icon direction. Default value: right.*
* @param **$size:** *Icon Size. Default size: 14px.*
* @param **$color:** *Icon color. Default color: #111.*
* @param **$padding:** *Icon padding. Default value: 0px.*

**Usage 1:**
```scss
i {
	@include add-font-icon($f-bar-chart, $color: black);
}

<i>The Chart &nbsp;</i>
```

**Usage 2:**
```scss
i.home {
	@include add-font-icon($f-home, $padding: 10px);
}

<i class="home">Home</i>
```


----
##### `» Font Selector.`
* **Mixin Name:** @mixin font-select($fontType: 'r', $size: $baseFontPixel, $spacing: 0.5px, $fontName: $baseFontName)
* **Note:** Before use, enter the value of **$baseFontName.**
* **Warning:** Use this when you import the fonts to your project:
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
```scss
.caption {
	@include font-select('m', 18px);
}

<p class="caption">This is caption.</p>
```


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
* **Minor fixed:** @mixin prefix($property, $args...)
	* Rewritten DRY.
* **Mixin deprecated:** @mixin grayscale($percent)
	* Instead of Image Filter use.

**v.1.3.0**
* **Mixin added:** Button to add animation.
* **Mixin added:** Add Font Icon.

**v.1.3.1**
* **Minor fixed:** Font path.
* **License added:** Font Avesome.
* **Readme:** Improved.

**v.1.4.0**
* **Mixin added:** Font Selector.

**v.1.4.1**
* **Minor fixed:** Improvements were made.


Author
----
Levent Özbilgiç - XCODE


License
----

* [MIT](https://github.com/ozbilgic/sass-mixin-css-framework/blob/master/LICENSE) 2016 - XCODE
* [Font Avesome](https://fortawesome.github.io/Font-Awesome/license/)


[anim]:<http://www.w3schools.com/cssref/css_animatable.asp>