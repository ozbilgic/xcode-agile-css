# Sass Mixins CSS Framework - (Mixins Library)
**Agile CSS coding library.**


### Version
---
1.0.0


### Functions
---
##### `» Pixel converts the "em" format.`
* **Warning:** Specify the base font size before use. ($baseFontPixel, Default size 16px.)
* **Function Name:** @convert_em($fontPx)

**Parameter Descriptions:**
* $fontPx = Font Size.

**Usage:**
```scss
p {
	font-size: convert_em(14px);
}
```


### Mixins
---
##### `» CSS3 Prefix Adding.`
* **Mixins Name:** @prefix($property, $value)

**Parameter Descriptions:**
* $property: Css property name. Ex. "transition, "border-radius"...
* $value: For the selected attribute values. Ex. ".3s", "15px"...

**Usage:**
```scss
.box {
	Width: 300px;
	height: 300px;
	@include prefix(border-radius, 5px);
}
```


##### `» Responsive Media Selector.`
* **Mixins Name:** @media($media)

**Parameter Descriptions:**
* $media = "$cellphone", "$smartphone", "$tablet", "$desktop", "$largeScreen" or "nil" when full screen.

**Usage:**
```scss
nav[data=main-menu] {
	@include media(desktop) {
		display: none;
	}
}
```


##### `» Alternate Responsive Media Selector.`
This selective media can be entered in any desired resolution.
* **Mixins Name:** @mediaQuery($minMax, $width, $eWidth: 0)

**Parameter Descriptions:**
* $minMax = min or max. (min-width, max-width)
* $width, $eWidth = $cellphoneSize, $smartphoneSize, $tabletSize, $desktopSize, $largeScreenSize, $fullScreenSize
* $eWidth = Any screen resolution size.

**Usage:**
```scss
nav.nav-content {
	@include mediaQuery(min, $desktop) {
		display: none;
	}
}

h1.caption {
	@include mediaQuery(max, nil, 300px) {
		font-size: 20%;
	}
}
```


##### `» Setting The Alpha Channel For Items. Support Cross Browser.`
* **Mixins Name:** @opacity($opacity: .85)

**Parameter Descriptions:**
* $opacity = 0..1

**Usage:**
```scss
a:hover {
	@include opacity(.7)
}
```


##### `» Set Border Radius.`
* **Mixins Name:** @border-radius($radius)

**Parameter Descriptions:**
* $radius = You know that ;)

**Usage:**
```scss
div.box {
	@include border-radius(15px)
}
```


##### `» Set Shorthand Animation.`
* **Tip:** You can use this feature with keyframes
* **Mixins Name:** @animation($args...)

**Parameter Descriptions:**
* $args = {
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
* **Mixins Name:** keyframes($animationName)
* **Tip:** [See those for features](Link: http://www.w3schools.com/cssref/css_animatable.asp)

**Parameter Descriptions:**
* $animationName = Name of the animation. You can put any name.

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
* **Mixins Name:** @transition($args...)

**Parameter Descriptions:**
* $args = {
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
header.navbar slowly change color to adding .navbg-black class.


##### `» 2D Transforms.`
* **Mixin Name:** transform2d($method)
* **Tip:** See at  examples (Link: http://www.w3schools.com/css/css3_2dtransforms.asp)

**Parameter Descriptions:**
* $method = Method name.
* Method List {
                translate(x,y), translateX(n), translateY(n),
                rotate(angle),
                scale(x,y), scaleX(n), scaleY(n),
                skew(x-angle, y-angle), skewX(angle), skewY(angle),
                matrix(n,n,n,n,n,n)
              }

**Usage:**
```scss
div.rotate {
	transform2d(rotate(20deg));
}
```


##### `» 3D Transforms.`
* **Mixin Name:** transform3d($method)

**Parameter Descriptions:**
* $method = Method name.
* Method List {
                translate3d(x,y,z), translateX(x), translateY(y), translateZ(z),
                rotate3d(x,y,z,angle), rotateX(angle), rotateY(angle), rotateZ(angle),
                scale3d(x,y,z), scaleX(x), scaleY(y), scaleY(z),
                matrix3d(n,n,n,n,n,n,n,n,n,n,n,n,n,n,n,n),
                perspective(n)
              }

**Usage:**
```scss
div.rotate {
	transform3d(rotateZ(90deg));
}
```


##### `» Change Input Placeholder Attributes.`
* **Mixins Name:** changeInputPlaceholder()
* Supported placeholder styles: {
      font
      color
      background
      word-spacing
      letter-spacing
      text-decoration
      vertical-align
      text-transform
      line-height
      text-indent
      opacity
  }

**Usage:**
```scss
input[type="email"] {
	@include changeInputPlaceholder() {
		color: orange;
	}
}
```


##### `» Change The Color of All Images to Black and White.`
* **Mixins Name:** grayscale($value)
* **Tip:** 0..100, 100 full gray.
* **Warning:** IE not supported.

**Parameter Descriptions:**
* $value = Percent.

**Usage:**
```scss
img.poster {
	@include grayscale(20%);
}
```


License
----

[MIT](https://github.com/ozbilgic/sass-mixin-css-framework/blob/master/LICENSE)