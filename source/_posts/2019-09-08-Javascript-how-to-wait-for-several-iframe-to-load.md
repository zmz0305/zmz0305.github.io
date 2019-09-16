---
title: Javascript - how to wait for several iframe to load
date: 2019-09-08 22:46:44
tags:
    - Javascript
    - HTML
    - async
categories:
    - Dev_general
cover: /img/javascript.png
---
# Javascript - how to wait for several iframe to load
A while ago, I had a testing situation that after a page is loaded, I need to wait for the 3 iframes inside the page to load before testing something else. After some google efforts, I find that iframe can attach a `load` event handler, and we can setup some callback on the `load` event to accomplish the wait.

``` javascript
document.getElementById('my_iframe').onload = function() {
    doSomething();
}
```

However, I couldn't find anything that can be easily used to wait for all 3 iframes to load, so it's time to improvise :)

There is an [`async`](https://caolan.github.io/async/v3/) library that could be used to conveniently make async code into serial code. I used the `async.parallel` function to block and wait for all 3 iframes to finish loading in parallel.
``` Javascript
import parallel from 'async/parallel';
let iframes = findAll('iframe') // iframes is an array of iframe elements
let subscribeToLoadEvent = function (index, timeout_miliseconds, callback) {
  iframes[index].addEventListener("load", function () {
    callback(null, index) // checkout the async documentation above for how this callback is used
  })
};

await parallel([
  (callback) => subscribeToLoadEvent(0, 1000, callback),
  (callback) => subscribeToLoadEvent(1, 1000, callback),
  (callback) => subscribeToLoadEvent(2, 1000, callback),
])
```

Hope this helps :)
