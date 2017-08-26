Slatebox Raphael
===============

This repository includes our custom raphael code.

1. `npm install`
2. `./node_modules/.bin/webpack --no-deps`
3. Modify `raphael.no-deps.js`...

from:

```
(function webpackUniversalModuleDefinition(root, factory) {
  if(typeof exports === 'object' && typeof module === 'object')
    module.exports = factory(require("eve"));
  else if(typeof define === 'function' && define.amd)
    define(["eve"], factory);
  else if(typeof exports === 'object')
    exports["Raphael"] = factory(require("eve"));
  else
    root["Raphael"] = factory(root["eve"]);
})(this, function(__WEBPACK_EXTERNAL_MODULE_2__) {
```

to

```
(function webpackUniversalModuleDefinition(root, factory) {
    root["Raphael"] = factory(root["eve"]);
})(window, function(__WEBPACK_EXTERNAL_MODULE_2__) {
```

4. `cp ./raphael.no-deps.js PATH_TO_SLATEBOX_REPO/packages/client/slatebox/lib/raphael/raphael.no-deps.js`