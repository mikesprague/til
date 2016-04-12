# jQuery 3.0 New Loop Syntax

jQuery 3 introduces new syntax for looping over DOM elements of a jQuery
collection using the for...of loop. This new change is more in line with what's
present in other language and technologies, and is part of the ECMA 6
specification.

## Standard loop syntax prior to jQuery 3.0

```javascript

var divElements = $( "div" );

for ( var i = 0; i < divElements.length; i++ ) {
  divElements[i].addClass( "class-name" );
}
```

## Loop syntax available with jQuery 3.0

```javascript

var divElements = $( "div" );

for ( var el of divElements ) {
  el.addClass( "class-name" );
}
```

### Additional Notes

With this new syntax you get the DOM element, instead of a jQuery collection.

As such, you don’t need to use index to get the element because you already
have direct access to it.
