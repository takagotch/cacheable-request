### cacheable-request
---
https://github.com/lukechilds/cacheable-request

```
npm install cacheable-request

npm install @keyv/redis
```

```js
const http = require('http');
const CacheableRequest = require('cacheable-request');
const req = http.request('http://example.com', cb);
req.end();
const cacheableRequest = new CacheableRequest(http.request);
const cacheReq = cacheableRequest('http://example.com', cb);
cacheReq.on('request', req => req.end());
const cacheableRequest = new CacheableRequest(https.request);
const cacheableRequest = new CacheableRequest(electron.net);

const cacheableRequest = new CacheableRequest(http.request, 'redis://user:pass@localhost:6379');

const storageAdapter = new Map();
const storageAdapter = require('./my-storage-adapter');
const QuickLRU = require('quick-lru');
const storageAdapter = new QuickLRU({ maxSize: 1000 });
const cacheableRequest = new CacheableRequest(http.request, storageAdapter);

cacheableRequest('example.com', cb)
  .on('error', err => {
    if(err instanceof CacheableRequest.CacheError){
      handleCacheError(err);
    } else if (err instanceof CacheableRequest.RequestError){
      handleRequestError(err);
    }
  })
  .on('request', req => {
    req.on('error', handleRequestError);
    req.end();
  }); 
```

```
```


