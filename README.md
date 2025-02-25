![Async Logo](https://raw.githubusercontent.com/caolan/async/master/logo/async-logo_readme.jpg)

[![Build Status via Travis CI](https://travis-ci.org/caolan/async.svg?branch=master)](https://travis-ci.org/caolan/async)
[![Build Status via Azure Pipelines](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master)
[![NPM version](https://img.shields.io/npm/v/async.svg)](https://www.npmjs.com/package/async)
[![Coverage Status](https://coveralls.io/repos/caolan/async/badge.svg?branch=master)](https://coveralls.io/r/caolan/async?branch=master)
[![Join the chat at https://gitter.im/caolan/async](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/caolan/async?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![jsDelivr Hits](https://data.jsdelivr.com/v1/package/npm/async/badge?style=rounded)](https://www.jsdelivr.com/package/npm/async)

<!--
|Linux|Windows|MacOS|
|-|-|-|
|[![Linux Build Status](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master&jobName=Linux&configuration=Linux%20node_10_x)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master) | [![Windows Build Status](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master&jobName=Windows&configuration=Windows%20node_10_x)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master) | [![MacOS Build Status](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master&jobName=OSX&configuration=OSX%20node_10_x)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master)| -->

Async is a utility module which provides straight-forward, powerful functions for working with [asynchronous JavaScript](http://caolan.github.io/async/v3/global.html). Although originally designed for use with [Node.js](https://nodejs.org/) and installable via `npm i async`, it can also be used directly in the browser.  A ESM/MJS version is included in the main `async` package that should automatically be used with compatible bundlers such as Webpack and Rollup.

A pure ESM version of Async is available as [`async-es`](https://www.npmjs.com/package/async-es).

For Documentation, visit <https://caolan.github.io/async/>

*For Async v1.5.x documentation, go [HERE](https://github.com/caolan/async/blob/v1.5.2/README.md)*


```javascript
// for use with Node-style callbacks...
var async = require("async");

var obj = {dev: "/dev.json", test: "/test.json", prod: "/prod.json"};
var configs = {};

async.forEachOf(obj, (value, key, callback) => {
    fs.readFile(__dirname + value, "utf8", (err, data) => {
        if (err) return callback(err);
        try {
            configs[key] = JSON.parse(data);
        } catch (e) {
            return callback(e);
        }
        callback();
    });
}, err => {
    if (err) console.error(err.message);
    // configs is now a map of JSON data
    doSomethingWith(configs);
});
```

```javascript
var async = require("async");

// ...or ES2017 async functions
async.mapLimit(urls, 5, async function(url) {
    const response = await fetch(url)
    return response.body
}, (err, results) => {
    if (err) throw err
    // results is now an array of the response bodies
    console.log(results)
})
```

Auto-commit on 2025-02-22 17:22:18 | rand=75842

Auto-commit on 2025-02-22 17:34:18 | rand=96032

Auto-commit on 2025-02-22 17:46:24 | rand=24666

Auto-commit on 2025-02-24 14:01:12 | rand=18402

Auto-commit on 2025-02-24 14:13:13 | rand=98471

Auto-commit on 2025-02-24 14:25:13 | rand=47517

Auto-commit on 2025-02-24 14:37:21 | rand=93840

Auto-commit on 2025-02-24 14:49:28 | rand=93132

Auto-commit on 2025-02-24 15:01:28 | rand=52055

Auto-commit on 2025-02-24 15:13:35 | rand=39769

Auto-commit on 2025-02-24 15:25:39 | rand=58271

Auto-commit on 2025-02-24 15:37:48 | rand=94367

Auto-commit on 2025-02-24 15:49:57 | rand=5732

Auto-commit on 2025-02-24 16:02:07 | rand=44679

Auto-commit on 2025-02-24 16:14:06 | rand=20338

Auto-commit on 2025-02-24 16:26:03 | rand=24949

Auto-commit on 2025-02-24 16:38:10 | rand=80087

Auto-commit on 2025-02-24 16:50:14 | rand=515

Auto-commit on 2025-02-24 18:02:28 | rand=78841

Auto-commit on 2025-02-24 18:14:28 | rand=62262

Auto-commit on 2025-02-24 18:26:34 | rand=35521

Auto-commit on 2025-02-24 18:38:40 | rand=78242

Auto-commit on 2025-02-24 18:50:47 | rand=16104

Auto-commit on 2025-02-24 19:02:51 | rand=56446

Auto-commit on 2025-02-24 19:15:00 | rand=55604

Auto-commit on 2025-02-24 19:27:06 | rand=48592

Auto-commit on 2025-02-24 19:39:03 | rand=39529

Auto-commit on 2025-02-24 19:51:05 | rand=67853

Auto-commit on 2025-02-24 20:03:09 | rand=30545

Auto-commit on 2025-02-24 20:15:15 | rand=52843

Auto-commit on 2025-02-24 20:27:19 | rand=57561

Auto-commit on 2025-02-24 20:39:22 | rand=59161

Auto-commit on 2025-02-24 20:51:22 | rand=38518

Auto-commit on 2025-02-25 12:25:06 | rand=86127

Auto-commit on 2025-02-25 12:37:05 | rand=30090

Auto-commit on 2025-02-25 12:49:13 | rand=29559
