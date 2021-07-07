**Note:** Concepts and usage of Web Workers
**Date:** 07.07.2021
**Tags:** #programming, #webapi, #javascript 

<hr>

**Creating a web worker 👷**

A worker is an object created using a constructor (e.g. `Worker()`) that runs a named JS file containing code that will be executed in a seperate thread.

**Usage**

You can run pretty much any code using the standard JS set of functions and Web APIs.
Web workers cannot modify the DOM nor some properties of the `window` object.
Workers may spawn new workers (as long as those are hosted within the same origin), furthermore they may use network I/O browser apis.


**Communication with web workers**
Data is sent between workers and the main thread using the `postMessage()` method. To respond to a message use `onmessage` event handler.
Data is being copied rather than shared.


