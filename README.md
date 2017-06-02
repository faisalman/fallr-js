# Fallr.js

Fancy modal box jQuery plugin

## Usage

```html
<!-- include the required CSS -->
<link rel="stylesheet" type="text/css" href="jquery-fallr-2.0.css" />
                
<!-- include any version of jQuery before including plugin -->
<script type="text/javascript" src="jquery-1.7.1.min.js"></script>

<!-- include the plugin -->
<script type="text/javascript" src="jquery-fallr-2.0.min.js"></script>
```

## General API

```js
$.fallr.[method]([,options:Object] [,callback:function]);
```

### Methods

* show : create and show message box, for example:
```js
$.fallr.show({content: 'hello world!'}, function(){ console.log('message box appears'); });
```

* hide : hide current active message box, for example:
```js
$.fallr.hide(function(){ console.log('message box disappears'); });
```

* resize : resize the width/height of current active message box, for example:
```js
$.fallr.resize({width: '500px', height: '400px'});
```

* set : set default options that will be used for every message box instance in the page, for example:
```js
$.fallr.set({duration: 1000, useOverlay: true});
```

* blink : make the current active message box blinking
```js
$.fallr.blink();
```

* shake : make the current active message box shaking
```js
$.fallr.shake();
```

### Options

```js
buttons         : {
    button1 : {
        text    : 'OK',                 // default button text
        danger  : false,                // button color
        onclick : function () {         // default button function 
            $.fallr.hide(); 
        }
    }
},
icon            : 'check',          // [string] icon displayed
content         : 'Hello',          // [string] fallr content
position        : 'top',            // [string] top/center/bottom
closeKey        : true,             // [bool] whether to close fallr with ESC key
closeOverlay    : false,            // [bool] whether to close fallr on overlay click
useOverlay      : true,             // [bool] whether overlay should be shown
autoclose       : false,            // [int] autoclose duration in miliseconds, false to disable
easingDuration  : 300,              // [int] animation duration
easingIn        : 'swing',          // [string] easing type when appear
easingOut       : 'swing',          // [string] easing type when disappear
height          : 'auto',           // [string] css value for exact height
width           : '360px',          // [string] css value for exact width
zIndex          : 100,              // [int] set z-index
bound           : window,           // [string/object] jQuery selector for costum boundary
afterHide       : function () {},   // [function] after hide callback, can be overrided by parameter
afterShow       : function () {}    // [function] after show callback, can be overrided by parameter
```

### Custom Icon

There are some predefined icons name you can use already: `at, bars, book, calendar, photo, chart, chat, check, clock, gear, document, error, folder, heart, help, home, info, key, lamp, left, magnifier, mail, minus, pen, pin, plus, quote, reload, right, star, tag, trash, unlock, up, user, window, config`.

To define another custom icon class name you have to edit the CSS file, then add a CSS class with `.ficon-` prefix like this:

```css
.ficon-twitter {
    background-image: url('img/twitter.png');
}
```

The image format must be a PNG/GIF/JPG with recommended size 32x32 px. In the example above we can see that the twitter icon file is inside `/img` folder relative to the CSS file, then you can use it as:

```js
$.fallr.show({icon : 'twitter', content: '<p>Hi there, see my new icon!</p>'});
```

## Credits

* CSS3 Github buttons by Nicolas Gallagher
* Iconic icon set by somerandomdude

## License

Dual licensed under GPLv2 & MIT

Copyright © 2011-2014 Faisal Salman <<f@faisalman.com>>

Permission is hereby granted, free of charge, to any person obtaining a copy of 
this software and associated documentation files (the "Software"), to deal in 
the Software without restriction, including without limitation the rights to use, 
copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the 
Software, and to permit persons to whom the Software is furnished to do so, 
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all 
copies or substantial portions of the Software.