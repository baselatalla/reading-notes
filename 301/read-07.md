# Roy Fielding

Who write the first web servers, that sent documents across the internet… and then he did a ton of research explaining why the web works the way it does. His name is on the specification for the protocol that is used to get pages from servers to your browser like HTTP.

## HTTP :

The Hypertext Transfer Protocol (HTTP) is an application layer protocol for distributed, collaborative, hypermedia information systems.HTTP is the foundation of data communication for the World Wide Web, where hypertext documents include hyperlinks to other resources that the user can easily access.

That first part tells the browser what protocol to use. That stuff you type in there is one of the most important breakthroughs in the history of computing .it is capable of describing the location of something anywhere in the world from anywhere in the world. It's the foundation of the web. it its like GPS coordinates for knowledge and information..

## REST

Representational state transfer (REST) is a software architectural style which uses a subset of HTTPز It is commonly used to create interactive applications that use Web services. A Web service that follows these guidelines is called RESTful.

Such a Web service must provide its Web resources in a textual representation and allow them to be read and modified with a stateless protocol and a predefined set of operations. This approach allows interoperability between the computer systems on the Internet that provide these services

REST provides a definition of a “resource”, which is what those things point to.


# SuperAgent


SuperAgent is light-weight progressive ajax API crafted for flexibility, readability, and a low learning curve after being frustrated with many of the existing request APIs. It also works with Node.js!

` request .post(‘/api/pet’) .send({ name: ‘Manny’, species: ‘cat’ }) .set(‘X-API-Key’, ‘foobar’) .set(‘Accept’, ‘application/json’) .then(res => { alert(‘yay got ‘ + JSON.stringify(res.body)); });`

### Test documentation

The following test documentation was generated with Mocha’s “doc” reporter, and directly reflects the test suite. This provides an additional source of documentation.

### Request basics
A request can be initiated by invoking the appropriate method on the request object, then calling .then() (or .end() or await) to send the request. For example a simple GET request:

request .get('/search') .then(res => { // res.body, res.headers, res.status }) .catch(err => { // err.message, err.response });

HTTP method may also be passed as a string:

request('GET', '/search').then(success, failure);

Old-style callbacks are also supported, but not recommended. Instead of .then() you can call .end():

request('GET', '/search').end(function(err, res){ if (res.ok) {} });

Absolute URLs can be used. In web browsers absolute URLs work only if the server implements CORS.

DELETE, HEAD, PATCH, POST, and PUT requests can also be used, simply change the method name:

request .head('/favicon.ico') .then(res => { });

DELETE can be also called as .del() for compatibility with old IE where delete is a reserved word.

The HTTP method defaults to GET, so if you wish, the following is valid:

` request(‘/search’, (err, res) => { });`

## Setting header fields Setting header fields is simple, invoke .set() with a field name and value:

` request .get(‘/search’) .set(‘API-Key’, ‘foobar’) .set(‘Accept’, ‘application/json’) .then(callback);`

### GET requests


The .query() method accepts objects, which when used with the GET method will form a query-string. The following will produce the path /search?query=Manny&range=1..5&order=desc

HEAD requests
You can also use the .query() method for HEAD requests. The following will produce the path /users?email=joe@smith.com.

Setting the Content-Type
The obvious solution is to use the .set() method:

` request.post(‘/user’) .set(‘Content-Type’, ‘application/json’)`

### Serializing request body


SuperAgent will automatically serialize JSON and forms. You can setup automatic serialization for other types as well:

request.serialize['application/xml'] = function (obj) { return 'string generated from obj'; }; // going forward, all requests with a Content-type of // 'application/xml' will be automatically serialized



### Retrying requests
When given the .retry() method, SuperAgent will automatically retry requests, if they fail in a way that is transient or could be due to a flaky Internet connection.

This method has two optional arguments: number of retries (default 1) and a callback. It calls callback(err, res) before each retry. The callback may return true/false to control whether the request should be retried (but the maximum number of retries is always applied).

### Setting Accept

In a similar fashion to the .type() method it is also possible to set the Accept header via the short hand method .accept(). Which references request.types as well allowing you to specify either the full canonicalized MIME type name as type/subtype, or the extension suffix form as “xml”, “json”, “png”, etc. for convenience:

` request.get(‘/user’) .accept(‘application/json’) request.get(‘/user’) .accept(‘json’) request.post(‘/user’) .accept(‘png’)`