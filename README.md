# Sass Mixins CSS Framework - (Mixins Library)
**Agile CSS coding library.**
![cross-browser-support](https://cloud.githubusercontent.com/assets/6649597/14314265/d9f64a76-fbfe-11e5-8ffd-4faa6f652447.jpg)


Version 1.1.0
----

1.1.0


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
* @param $fontPx: Font Size.
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
* **Mixin Name:** @prefix($property, $value)

**Parameter Descriptions:**
* @param $property: Css property name. Ex. "transition", "border-radius"...
* @param $value: For the selected attribute values. Ex. ".3s", "15px"...

**Usage:**
```scss
.box {
	Width: 300px;
	height: 300px;
	@include prefix(border-radius, 5px);
}
```


##### `» Responsive Media Selector.`
* **Mixin Name:** @media($media)

**Parameter Descriptions:**
* @param $media: $cellphone, $smartphone, $tablet, $desktop, $largeScreen or "nil" when full screen.

**Usage:**
```scss
nav[data=main-menu] {
	@include media($desktop) {
		display: none;
	}
}
```


##### `» Alternate Responsive Media Selector.`
This selective media can be entered in any desired resolution.
* **Mixin Name:** @media-query($minMax, $width, $eWidth: 0)

**Parameter Descriptions:**
* @param $minMax: min or max. (min-width, max-width)
* @param $width, $eWidth: $cellphoneSize, $smartphoneSize, $tabletSize, $desktopSize, $largeScreenSize, $fullScreenSize
* @param $eWidth: Any screen resolution size.

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


##### `» Setting The Alpha Channel For Items. Support Cross Browser.`
* **Mixin Name:** @opacity($opacity: .85)

**Parameter Descriptions:**
* @param $opacity: 0..1

**Usage:**
```scss
a:hover {
	@include opacity(.7)
}
```


##### `» Set Border Radius.`
* **Mixin Name:** @border-radius($radius)

**Parameter Descriptions:**
* @param $radius: You know that ;)

**Usage:**
```scss
div.box {
	@include border-radius(15px)
}
```


##### `» Set Shorthand Animation.`
* **Tip:** You can use this feature with keyframes
* **Mixin Name:** @animation($args...)

**Parameter Descriptions:**
* @param $args: {
          	Animation name,
            Duration,
            Timing function,
            Delay,
            Iteration count,
            Direction
          }

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


##### `» Animation Creator.`
* **Mixin Name:** @keyframes($animationName)
* **Tip:** [See those for features][anim]

**Parameter Descriptions:**
* @param $animationName: Name of the animation. You can put any name.

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


##### `» Transition.`
* **Mixin Name:** @transition($args...)

**Parameter Descriptions:**
* @param $args: {
            Property,
            Duration,
            Timing function,
            Delay
          }

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
» header.navbar slowly change color to adding .navbg-black class.


##### `» 2D Transforms.`
* **Mixin Name:** @transform2d($method)
* **Tip:** [See at examples](http://www.w3schools.com/css/css3_2dtransforms.asp)

**Parameter Descriptions:**
* @param $method: Method name.
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


##### `» 3D Transforms.`
* **Mixin Name:** @transform3d($method)

**Parameter Descriptions:**
* @param $method: Method name.
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


##### `» Change The Color of All Images to Black and White.`
* **Mixin Name:** @grayscale($value)
* **Tip:** 0..100, 100 full gray.
* **Warning:** IE not supported.

**Parameter Descriptions:**
* @param $value: Percent.

**Usage:**
```scss
img.poster {
	@include grayscale(20%);
}
```


##### `» Horizontal Navigation Bar.`
* **Mixin Name:** @h-navigation-bar(
                    $width: 200px,
                    $bgColor: #f1f1f1,
                    $textColor: #000,
                    $hoverBgColor: #555,
                    $hoverTextColor: white,
                    $activeLinkBgColor: #4CAF50,
                    $activeLinkTextColor: white,
                    $isFullHeight: false)

**Parameter Descriptions:**
* @param $width: Navigation bar width. Default size: 200px. Tip: Percentage value enterable.
* @param bgColor: Navigation bar background color. Default color: #f1f1f1.
* @param textColor: Link text color. Default color: #000.
* @param $hoverBgColor: Link hover background color. Default color: #555.
* @param $hoverTextColor: Link hover text color. Default color: #fff.
* @param $activeLinkBgColor: Active link background color. Default color: #4CAF50.
* @param $activeLinkTextColor: Active link text color. Default color: #fff.
* @param $isFullHeight: Full height navigation bar. Default value: false.

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


##### `» Vertical Navigation Bar.`
* **Mixin Name:** @mixin v-navigation-bar(
                    $bgColor: #333,
                    $textColor: white,
                    $hoverBgColor: #111,
                    $activeLinkBgColor: #4CAF50,
                    $isDivider: false,
                    $dividerColor: #bbb)
**Parameter Descriptions:**
* @param $bgColor: Navigation bar background color. Default color: #333.
* @param $textColor: Link text color. Default color: #fff.
* @param $hoverBgColor: Link hover background color. Default color: #111.
* @param $activeLinkBgColor: Active link background color. Default color: #4CAF50.
* @param $isDivider: Divider inserts links. Default value: false.
* @param $dividerColor: Dividers color. Default color: #bbb.

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


##### `» Vertical Navigation Bar.`
* **Mixin Name:** @mixin dropdown(
                  	$btnBgColor: #4CAF50,
                  	$btnTextColor: white,
                  	$contentWidth: 160px,
                  	$linkTextColor: black,
                  	$linkHoverBgColor: #f1f1f1)
**Parameter Descriptions:**
* @param $btnBgColor: Dropdown button background color. Default color: #4CAF50.
* @param $btnTextColor: Button text color. Default color: #fff.
* @param $contentWidth: Dropdown content width. Default value: 160px.
* @param $linkTextColor: Link text color. Default color: #000.
* @param $linkHoverBgColor: Link hover background color. Default color: #f1f1f1.

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


Version History
----

**v.1.0.0**
* First version.

**v.1.1.0**
* **Mixin added:** Horizontal Navigation Bar.
* **Mixin added:** Vertical Navigation Bar.
* **Mixin added:** Dropdown.


License
----

[MIT](https://github.com/ozbilgic/sass-mixin-css-framework/blob/master/LICENSE) 2016 - XCODE


[anim]:<http://www.w3schools.com/cssref/css_animatable.asp>