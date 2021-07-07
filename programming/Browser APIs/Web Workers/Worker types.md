**Note:** Worker types
**Date:** 07.07.2021
**Tags:** #programming, #webapi, #javascript 

<hr>

**Worker types**
- **Dedicated workers** are workers that are utilized by a single script. This context is represended by [DedicatedWorkerGlobalScope](https://developer.mozilla.org/en-US/docs/Web/API/DedicatedWorkerGlobalScope)
- **Shared workers** are workers that can be utilized by multiple scripts running in different windows, IFrames etc. as long as they are in the same domain as the worker. Must communicate via an active port.
- **[[Service workers]]** act as proxy servers between web apps, the browser and the network (when available). They are aintended, among other things, to enable the creation of effective offline experiences, intercept network requests and take actions based on whether the network is available. They will alsoallow access tu push notifications and backgroud sync APIs.