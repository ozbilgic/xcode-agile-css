#Sass Mixins CSS Framework - (Mixins Library)
####Smart and agile CSS coding library.


##Functions:
	» Pixel converts the "em" format.
		- @function convert_em($fontPx)

##Mixins:
	» CSS3 Prefix Adding.
		- @mixin prefix($property, $value)

	» Responsive Media Selector.
		- @mixin media($media)

	» Alternate Responsive Media Selector.
		- @mixin mediaQuery($minMax, $width, $eWidth: 0)

	» Setting The Alpha Channel For Items. Support Cross Browser.
		- @mixin opacity($opacity: .85)

	» Set Border Radius.
		- @mixin border-radius($radius)

	» Set Shorthand Animation.
		- @mixin animation($args...)

	» Animation Creator.
		- @mixin keyframes($animationName)

	» Transition.
		- @mixin transition($args...)

	» 2D Transforms.
		- @mixin transform2d($method)

	» 3D Transforms.
		- @mixin transform3d($method)

	» Change Input Placeholder Attributes.
		- @mixin changeInputPlaceholder()

	» Change The Color of All Images to Black and White.
		- @mixin grayscale($value)