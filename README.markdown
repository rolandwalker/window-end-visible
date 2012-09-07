Overview
========
Find the last visible point in an Emacs window.

window-end-visible
------------------
Window-end-visible.el has no user-level interface, and is only
useful when programming Emacs Lisp.

This library provides the function `window-end-visible`, which
works around a limitation of `window-end`, at a speed penalty.

The issue this function solves is that the following is not true
as might be expected:

	(pos-visible-in-window-p (window-end))

`window-end-visible` returns the "true" window end: the last
visible position in the window, verified by testing with
`pos-visible-in-window-p`.

The speed penalty of `window-end-visible` over `window-end` varies
depending on your configuration.  For example, tabbar.el makes
calling `pos-visible-in-window-p` quite expensive.

Compatibility and Requirements
------------------------------
Tested on GNU Emacs versions 23.3 and 24.1

No external dependencies

