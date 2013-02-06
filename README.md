Brauhaus.js
===========
A library for homebrew beer calculations using Node.js or a web browser. Features:

 * BeerXML import / export
 * Calculate OG, FG, IBU, ABV, and color
 * Automatically generated recipe instructions
 * Estimate recipe cost based on ingredients
 * Color to RGB conversions, CSS color support, etc

[![Build Status](https://travis-ci.org/danielgtaylor/brauhausjs.png)](https://travis-ci.org/danielgtaylor/brauhausjs)

Installation
------------
You can install Brauhaus.js using `npm`:

```bash
npm install brauhaus
```

Quick Example (browser)
-----------------------
Here is an example of how to use the library in a browser. Be sure to copy the `lib/Brauhaus.min.js` file onto the web server. This example assumes it is accessible via `/scripts/Brauhaus.min.js`:

```html
<script type="text/javascript" src="/scripts/brauhaus.min.js"></script>
<script type="text/javascript">
    var r = new Brauhaus.Recipe({
        name: 'My test brew',
        description: 'A new test beer using Brauhaus.js!',
        batchSize: 20.0,
        boilSize: 10.0
    });

    r.add('fermentable', {
        name: 'Extra pale liquid extract',
        color: 2.5,
        weight: 4.2,
        yield: 78.0
    });

    r.calculate();

    console.log('Original Gravity: ' + r.og.toFixed(3));
    console.log('Alcohol: ' + r.abv + ' by volume');
</script>
```

Quick Example (Node.js CoffeeScript)
------------------------------------
Here is an example of how to use the library from CoffeeScript:

```coffeescript
{Recipe} = require 'brauhaus'

r = new Recipe
    name: 'My test brew'
    description: 'A new test beer using Brauhaus.js!'
    batchSize: 20.0
    boilSize: 10.0

r.add 'fermentable',
    name: 'Extra pale liquid extract'
    color: 2.5
    weight: 4.2
    yield: 78.0

r.calculate()

console.log "Original Gravity: #{ r.og.toFixed 3 }"
console.log "Alcohol: #{ r.abv }% by volume"
```

Quick Example (Node.js Javascript)
----------------------------------
Here is an example of how to use the library form Javascript:

```javascript
Recipe = require('brauhaus').Recipe

var r = new Recipe({
    name: 'My test brew',
    description: 'A new test beer using Brauhaus.js!',
    batchSize: 20.0,
    boilSize: 10.0
});

r.add('fermentable', {
    name: 'Extra pale liquid extract',
    color: 2.5,
    weight: 4.2,
    yield: 78.0
});

r.calculate();

console.log('Original Gravity: ' + r.og.toFixed(3));
console.log('Alcohol: ' + r.abv + ' by volume');
```

Reference
---------
Coming soon...

License
-------
Copyright (c) 2013 Daniel G. Taylor

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
