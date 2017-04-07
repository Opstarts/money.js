
# money.js / fx()

[![Build Status](https://travis-ci.org/ducdigital/money.js.svg?branch=master)](https://travis-ci.org/ducdigital/money.js)

This is a fork of **[money.js](http://openexchangerates.github.io/money.js/)**.

It was fork to merge several PR that important but was ignored by the author of money.js.
For detailed change log, please scroll down to the Changelog section.

## Quick Examples:

```javascript
// Simple syntax:
fx.convert(1000, {from: "GBP", to: "HKD"});

// Method chaining:
fx(1.99).from("USD").to("AED");

// Basic parsing:
fx("$1.99 HKD").to("EUR");

// Default parameters:
fx(5318008).convert();

// Supports nodeJS / AMD:
var fx = require('money');
require(["money"], function(fx) { /* ... */ });
```

## Additional features:

- New instance of money.js. `fx.factory()`
```javascript
var fx = require('money');
var newFxInstance = fx.factory();

console.log(fx === newFxInstance) // false
```

- Get rate between currencies `fx.getRate(to, from)`
```javascript
var fx = require('money');
fx.rates = { 'USD': 1, 'EUR': 0.5, 'GBP': 0.4 };

console.log(fx.getRate('EUR', 'GBP')); // 0.8
```

## Changelog
**0.3**
* Factory for money.js. Allow create multiple instance of money.js in the same app. Thanks @starsirius: (https://github.com/starsirius/money.js/commit/a736a83912d7f62f360f8d623c785f148e8f50d4)
* Proper error message instead of showing `fx error`. Thanks @sliptree:  (https://github.com/sliptree/money.js/commit/c76476456f1acef18c0b2441d36de3f55ae3650b)
* Unit test. Inpired by (@PierrickP)(https://github.com/PierrickP/money.js/commit/b2b5e32b2b0cbf13a334e4590b3ac2356c545b89)
* Expose `fx.getRate(to, from)` allow getting rate from any 2 currencies. Inspired by (@thewarpaint): (https://github.com/thewarpaint/money.js/commit/85eed2df55c3022ac6fe7fe83911ecf2a2b8a25d)
* Fix small bug cause value not passed to `getRate()`

**0.2**
* Now maintained by Open Exchange Rates
* Improved documentation

**0.1.3** - Fixed typo in nodeJS module definition

**0.1.2** - Strengthened up module definition similar to accounting.js

**0.1.1** - Added fallback when base rate is not in rates object (e.g. `"USD": 1`) to avoid errors

**0.1.0** - Added license; bumped version

**0.0.2**
* Adds basic parsing to `fx()`, so that you can pass a formatted string, like so: `fx("$1.99 HKD").to("GBP")`
* Some cleanup and improved comments and docs

**0.0.1** - First release
