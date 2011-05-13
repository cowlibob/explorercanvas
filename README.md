Please do not ask for help in the comments section below, as you won't get help here. In the case you found a bug or have a enhancement proposal, please [create an issue](http://code.google.com/p/explorercanvas/issues/list), or if you need help about using the library, please go and read the [mailing list](http://groups.google.com/group/google-excanvas).

Include the script
=============

The excanvas.js file must be included in the page before any occurrences of canvas elements in the markup. This is due to limitations in IE and we need to do our magic before IE sees any instance of `<canvas>` in the markup. It is recommended to put it in the head.

	<head>
		<!--[if IE]><script src="excanvas.js"></script><![endif]-->
	</head>

Dynamically created elements
======================

If you have created your canvas element dynamically it will not have the `getContext` method added to the element. To get it working you need to call `initElement` on the `G_vmlCanvasManager` object.

	var el = document.createElement('canvas');
	G_vmlCanvasManager.initElement(el);
	var ctx = el.getContext('2d');

Thats it. Now you can use the [HTML5 spec for Canvas](http://www.whatwg.org/specs/web-apps/current-work/multipage/the-canvas-element.html) as your reference.