Version History
----

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

**v.2.0.0**
* **Mixin deleted:** @mixin grayscale($percent).
* **Minor fixed:** @mixin x-horizontal-navbar() -> Link width and height adjustable.
* **Minor fixed:** @mixin x-menu-button() -> Border option added.
* **Minor fixed:** Edited all of the descriptions in the library.
* **Major fixed:** All mixins and functions prefix "x" was added.

**v.1.7.1**
* **Minor fixed:** @mixin font-select() -> Will alert "$baseFontName" value is not entered.

**v.1.7.0**
* **Mixin added:** Add Triangle.

**v.1.6.1**
* **Minor change:** 480px removed to grid system.
* **Minor change:** *$padding* added variable grid system.
* **Improvement:** @mixin media-query(), has been made more convenient.
* **Error fixed:** 16 columns grid system bug fixed.
* **Minor fixed:** @mixin h-navbar() and @mixin v-navbar(): The name confusion was fixed.
* **Minor change:** "12columnsGrid" file name changed to "grid12".
* **Minor change:** "16columnsGrid" file name changed to "grid16".

**v.1.6.0**
* **Mixin added:** Add Menu Button.

**v.1.5.3**
* **Minor fixed:** Grid and normalize extension changed to ".scss"
* **Minor fixed:** CSS Reset was included in the grid system.
* **Minor fixed:** Font path changed. (../fonts/).
* **Minor fixed:** Add the icon font, sample code changed.
* **Minor fixed:** Tools folder was deleted and the contents were moved to the main index.

**v.1.5.2**
* **Minor fixed:** %affix change name to %affix-top, %affix-bottom
* **Minor fixed:** normalize.css bug fixed.

**v.1.5.1**
* **Tool added:** 12 Columns Responsive Grid System.
* **Tool added:** 16 Columns Responsive Grid System.
* **Tool added:** Reset CSS.

**v.1.5.0**
* **Helper added:** Clearfix.
* **Helper added:** Affix.

**v.1.4.2**
* **Minor fixed:** @mixin h-navigation-bar() name changed to h-navbar()
* **Minor fixed:** @mixin v-navigation-bar() name changed to v-navbar()
* **ReadMe:** More understandable.

**v.1.4.1**
* **Minor fixed:** Improvements were made.

**v.1.4.0**
* **Mixin added:** Font Selector.

**v.1.3.1**
* **Minor fixed:** Font path.
* **License added:** Font Avesome.
* **ReadMe:** Improved.

**v.1.3.0**
* **Mixin added:** Button to add animation.
* **Mixin added:** Add Font Icon.

**v.1.2.1**
* **Minor fixed:** @mixin prefix($property, $args...)
	* Rewritten DRY.
* **Mixin deprecated:** @mixin grayscale($percent)
	* Instead of Image Filter use.

**v.1.2.0**
* **Mixin added:** Tooltip.
* **Mixin added:** Box Shadow.
* **Mixin added:** Gradients.
* **Mixin added:** Image Filter.

**v.1.1.0**
* **Mixin added:** Horizontal Navigation Bar.
* **Mixin added:** Vertical Navigation Bar.
* **Mixin added:** Dropdown.

**v.1.0.0**
* First version.