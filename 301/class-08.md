# Class 08 Reading Notes!

## SuperAgent

- SuperAgent is a light-weight progressive ajax API crafted for flexibility, and a low learning curve after being frustrated with many existing API's.

- works with node.js

### Request Basics

```js
 request
   .get('/search')
   .then(res => {
      // res.body, res.headers, res.status
   })
   .catch(err => {
      // err.message, err.response
   });
```

- could use HTTP

```js
request('GET', '/search').then(success, failure);
```

- old style but lame style

```js
request('GET', '/search').end(function(err, res){
  if (res.ok) {}
});
```

### Setting Header Fields

- simple, invoke .set()

```js
 request
   .get('/search')
   .set('API-Key', 'foobar')
   .set('Accept', 'application/json')
   .then(callback);
```

### Get Requests

- .query() method accepts objects

### Setting the Content-Type

- .set() will set the content type

### Serializing request body

- will serialize json files

```js
request.serialize['application/xml'] = function (obj) {
    return 'string generated from obj';
};

// going forward, all requests with a Content-type of
// 'application/xml' will be automatically serialized
```

### Retrying requests

- .retry() method will auto retry requests

### Setting Accept

- similart to .type()
- set the accept header via the short hand method .accept()

## RegExr

### LOL THE LINK WAS BROKEN AND BLOCKED BY AN ACCOUNT SIGN UP

- no