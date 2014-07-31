[![Build Status](https://secure.travis-ci.org/rolandwalker/window-end-visible.png?branch=master)](http://travis-ci.org/rolandwalker/window-end-visible)

# Overview

Find the last visible point in an Emacs window.

 * [Quickstart](#quickstart)
 * [Explanation](#explanation)
 * [Compatibility and Requirements](#compatibility-and-requirements)

## Quickstart

```elisp
(require 'window-end-visible)
 
;; open a buffer larger than the window
 
;; may return nil
(pos-visible-in-window-p (window-end))
 
;; always returns t
(pos-visible-in-window-p (window-end-visible))
```

## Explanation

`window-end-visible.el` has no user-level interface, and is only
useful when programming Emacs Lisp.

This library provides the function `window-end-visible`, which
works around a limitation of `window-end`, at a speed penalty.

The issue this function solves is that the following is not true
as might be expected:

```elisp
(pos-visible-in-window-p (window-end))
```

`window-end-visible` returns the "true" window end: the last
visible position in the window, verified by testing with
`pos-visible-in-window-p`.

The speed penalty of `window-end-visible` over `window-end` varies
depending on your configuration.  For example, [tabbar.el](https://github.com/dholm/tabbar) makes
calling `pos-visible-in-window-p` quite expensive.

## Compatibility and Requirements

	GNU Emacs version 24.4-devel     : yes, at the time of writing
	GNU Emacs version 24.3           : yes
	GNU Emacs version 23.3           : yes
	GNU Emacs version 22.2           : yes, with some limitations
	GNU Emacs version 21.x and lower : unknown

No external dependencies
