neo-pager
===============
jQuery based plugin that can be use for creating web-sections (pages) and possibility to scroll or jump through pages

Plugin that enable you to create web page sections and it will auto create dots (if set in options) for navigation.
- It support scroll animations.
- You can use custom buttons, menu buttons or any type of page notification, to achive that you can
use supported pager plugin methods.
- You can disable the dots and use your custom navigation.
- Pages can be with any height
- You can control the scroll up or down offset
- It will auto connect dots with pages and vise-versa
- It is fully responsive
For more about the plugin construction see the explanation parts below.

Table of contents
=================

  * [neo-pager](#neo-pager)
  * [Table of contents](#table-of-contents)
  * [Installation](#installation)
  * [HTML structure](#html-structure)
  * [Example CSS](#example-css)
  * [Options](#options)
  * [How to create](#how-to-create)
  * [Demo](#demo)
  * [Live preview](#live-preview)
  
Installation
============

Include JavaScript file 'neo.pager.js' into your HTML file (head tag)
```
<script type="text/javascript" src="relative-or-absolute-path\neo.pager.js"></script>
```
or include the mini version of the plugin
```
<script type="text/javascript" src="relative-or-absolute-path\neo.pager.min.js"></script>
```
You can use default css integrated into the plugin or you can define your own

HTML structure
==============

- To show hint on dot you need to add attribute: data-hint-text
- To show text by dots you need to add attribute: data-dot-text

```
<div id="pager-holder">
<div class="block1 height-block page" data-hint-text="Some help text"></div>
<div class="block2 height-block page" data-dot-text="Page 2"></div>
<div class="block3 height-block page"></div>
<div class="block4 height-block page"></div>
<div class="block5 height-block page"></div>
<div class="block6 height-block page"></div>
</div>
```
	
Example CSS
===========

If you want to style the dots and hint this is the best way how to do it!
- In this example the id's and classes names are the plugin default.
	
```
#dot-holder {
	position: fixed;
	right: 30px;
	top: 100px;
	width: 30px;
}
#dot-holder .page-nav-dot {
	list-style-type: none;
}
#dot-holder .page-nav-dot span {
	display: inline-block;
	position: relative;
	width: 12px;
	height: 12px;
	border-radius: 50%;
	background: white;
	margin: 10px;
	cursor: pointer;
	box-shadow: 1px 1px 1px rgba(0,0,0,0.1) inset, 1px 1px 1px rgba(255,255,255,0.3);
	border: 1px solid silver;
}
#dot-holder .page-nav-dot span:hover {
	background: #00aeef;
}
#dot-holder .page-nav-dot span.page-nav-dot-current:after {
	content: '';
	width: 8px;
	height: 8px;
	position: absolute;
	top: 1px;
	left: 1px;
	border-radius: 50%;
	background: #00aeef;
	background: -moz-linear-gradient(top, #00aeef 0%, #0095CC 47%, #00aeef 100%);
	background: -webkit-gradient(linear, left top, left bottom, color-stop(0%,#00aeef), color-stop(47%,#0095CC), color-stop(100%,#00aeef));
	background: -webkit-linear-gradient(top, #00aeef 0%,#0095CC 47%,#00aeef 100%);
	background: -o-linear-gradient(top, #00aeef 0%,#0095CC 47%,#00aeef 100%);
	background: -ms-linear-gradient(top, #00aeef 0%,#0095CC 47%,#00aeef 100%);
	background: linear-gradient(top, #00aeef 0%,#0095CC 47%,#00aeef 100%);
	filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#00aeef', endColorstr='#00aeef',GradientType=0 );
}
#dot-holder.page-nav-dot {
	margin: 5px 0px;
}
.hint--page:after {
  background-color: #0095CC;
  text-shadow: 0 -1px 0px #00aeef; 
  text-transform: capitalize;
}
.hint--page.hint--top:before {
  border-top-color: #0095CC; 
  text-transform: capitalize;
}
.hint--page.hint--bottom:before {
  border-bottom-color: #0095CC; 
  text-transform: capitalize;
}
.hint--page.hint--left:before {
  border-left-color: #0095CC; 
  text-transform: capitalize;
}
.hint--page.hint--right:before {
  border-right-color: #0095CC; 
  text-transform: capitalize;
}
```
	
Options
=======

```
pageClass: "page", // class selector for all pages
parentDotId: "dot-holder", // id of the dot holder
activeDotClass: "page-nav-dot-current", // current active dot
dotOutAnimClass: "", // used to animate the dot hide
dotInAnimClass: "", // used to animate the dot show
dotClass: "page-nav-dot", // the main dot holder class,
dotSelectionVisible: true, // doe's dot selection bar is visible
dotAnimSpeed: 500, // if no animate class is used
dotDelay: 100, // if no animate class is used
pageFactorUp: 0.1, // how we recognize the current page (0.5 = half page, values from 0..1)
pageFactorDown: 0.9, // how we recognize the current page (0.5 = half page, values from 0..1)
autoScrollPages: false, // if true it will auto scroll to next current page
pageScrollSpeed: 1000, // animation of page scroll
onDotHide: null, // event after dot animation hide finish
onDotShow: null, // event after dot animation show finish
onPageIn: null, // event when page become active
onPageOut: null, // event when page become inactive
onScroll: null, // event on page scroll
onAutoScrollStart: null, // event after auto scroll start
onAutoScrollEnd: null, // event after auto scroll end
useDefaultCss: false, // if true, plugin css will be auto created
hintClass: "hint--left hint--rounded hint--page", // classes that describe hint side position, how hint will be shown, and hint style
addHintStyle: true // if true it will auto generate hint css classes and styles
```

How to create
=============

To create the pager you do it like this: (by the first html example structure)
```
// without all default options
$("#pager-holder").neo_pager();

// with auto scroll enabled and default css
$("#pager-holder").neo_pager({
	autoScrollPages: true,
	useDefaultCss: true
});
```

Demo
====
You will find a basic example of this component in [base](/examples/base) folder of this git repository

Live preview
============
This website is part of a project and represent one page scroll website made with this component

http://esbe.youboost.it/