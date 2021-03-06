# nw-vue-devtools

[![Build Status](https://travis-ci.org/nwutils/nw-vue-devtools.svg?branch=master)](https://travis-ci.org/nwutils/nw-vue-devtools) [![npm version](https://img.shields.io/npm/v/nw-vue-devtools.svg)](https://www.npmjs.com/package/nw-vue-devtools) [![MIT license](https://img.shields.io/github/license/mashape/apistatus.svg)](https://github.com/TheJaredWilcurt/nw-vue-devtools/blob/master/LICENSE)

* * *

# DEPRECATION NOTICE

We are no longer able to automate building from the Vue-DevTools source anymore due to their adoption of Yarn. When Yarn innevitably dies after npm 7 or 8, and they switch back to npm, we may be able to get the automation working again. But until then, there is an alternative that downloads directly from the Chrome Webstore a prebuilt version, then modifies it for NW.js. I recommend using that:

* https://github.com/DimPaDev/nw-vue-devtools-prebuilt


* * *


This is a devDependency for adding Vue-DevTools into NW.js.

![screenshot](https://user-images.githubusercontent.com/4629794/42295950-a94531c2-7fbd-11e8-8d22-bf67ba35509c.png)



## Prerequisites:

You must have Git, Node, and npm installed globally.



## Instructions

1. `npm install --save-dev nw-vue-devtools`
1. Add this to your `package.json`:
    ```js
    "chromium-args": "--load-extension='./node_modules/nw-vue-devtools/extension'",
    ```
1. Vue.js must be in use in your app, and cannot be minified (`vue.js` not `vue.min.js`).

You may need to add `Vue.config.devtools = true;` to your `main.js` file.

If you are using `nwjs-builder-phoenix` then add in `"chromium-args"` to your `package.json` `build.strippedProperties` array ([more info](https://github.com/evshiron/nwjs-builder-phoenix/blob/master/docs/Options.md#build---buildconfig)).



## How it works:

This dependency will run an npm script that:

* Clones down the latest source code for [Vue-DevTools](https://github.com/vuejs/vue-devtools) `master` branch.
* Installs the dependencies for Vue-DevTools.
* Builds the source code for Vue-DevTools.
* Places the built version in `node_modules/nw-vue-devtools/extension`.
* Tries to recover from past failures on future re-runs.
* Skips everything if the extension had already been built successfully.



* * *



## See Also:

* [nw-vue-devtools-prebuilt](https://github.com/DimPaDev/nw-vue-devtools-prebuilt) - Downloads the CRX file from the Chrome Store, unzips and modifies it for use in NW.js. May be a better option for some.



* * *



## In Use

This package is used by:

* https://github.com/nwutils/nw-vue-devtools/network/dependents
