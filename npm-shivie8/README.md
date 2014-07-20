# shivIE8 1.0.0

Minimal HTML5 element shiv for IE8. Forked from [html5shiv](https://github.com/aFarkas/html5shiv).
Only 347 bytes uncompressed, 265 bytes compressed!

This is a vastly simplified fork of [html5shiv](https://github.com/aFarkas/html5shiv) that focuses only on supporting HTML5 elements for IE8 (supported natively by IE9). IE8 is still prevalent enough that many can't afford to ignore it and many frameworks explicitly advertise support for IE8. Many frameworks (like [React](https://github.com/facebook/react)) do not include the HTML5 elements shiv for IE8.

IE Quirks and IE6+ are also supported by this shiv. FireFox 3+ and Safari 4+ have no inherent issues with HTML5 elements when used with the shiv stylesheet below.

*IE8 is the last of a plagued breed, due to the extremely limited scope and simplicity of this workaround, expect this to be the last and final release... unless an issue is discovered.*

## Use this stylesheet

This script does NOT attach a stylesheet with default styles for HTML5 elements. Instead, copy the CSS below and put it at the top of your base/reset stylesheet, customize as you please.

```
article,aside,dialog,figcaption,figure,footer,header,hgroup,main,nav,section {
  display: block;
}
mark {
  background: #FFFF00; color: #000000;
}
template {
  display:none;
}
```
## Use as module

Shivs `document` on require, call `shivIEDocumentElements(otherDocument)` if necessary.

```
// npm install shivie8
// bower install --save shivie8
var shivIEDocumentElements = require('shivie8');
shivIEDocumentElements(document);
```

## Template danger

`<template>` is not reliable as its content is always evaluated by IE8. Reading from its `innerHTML` is also **unsafe** in IE8 due to insufficient escaping, white-space is also not correctly preserved. User supplied data in `template` is likely susceptible to XSS, use `<script type="text/plain">` instead.
