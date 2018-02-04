Slatebox Raphael
===============

This repository includes our custom raphael code.

1. `brew install bower`
2. `bower install`
3. `npm install`
4. `./node_modules/.bin/webpack`
5. Modify `raphael.js`...

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
})(this, function() {
```

to

```
(function webpackUniversalModuleDefinition(root, factory) {
    root["Raphael"] = factory(root["eve"]);
})(window, function() {
```

4. `cp ./raphael.js PATH_TO_SLATEBOX_REPO/packages/slatebox/lib/client/raphael/raphael.js`