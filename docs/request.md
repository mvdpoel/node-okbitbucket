# Global





* * *

### Request() 

Performs requests on GitHub API.



### setOption(name, value) 

Change an option value.

**Parameters**

**name**: `String`, The option name

**value**: `Object`, The value

**Returns**: `Request`, The current object instance


### getOption(name, defaultValue) 

Get an option value.

**Parameters**

**name**: , string  The option name

**defaultValue**: , Get an option value.

**Returns**: , mixed  The option value


### get(apiPath, params, options, then) 

Send a GET request

**Parameters**

**apiPath**: , Send a GET request

**params**: , Send a GET request

**options**: , Send a GET request

**then**: `msg:&#39;&#39;`, (err, body{})



### post(apiPath, params, options, then) 

Send a POST request

**Parameters**

**apiPath**: , Send a POST request

**params**: , Send a POST request

**options**: , Send a POST request

**then**: `msg:&#39;&#39;`, (err, body{})



### send(apiPath, params, httpMethod, options, then) 

Send a request to the server, receive a response,
decode the response and returns an associative array

**Parameters**

**apiPath**: `String`, Request API path

**params**: `Object`, params

**httpMethod**: `String`, HTTP method to use

**options**: `Object`, reconfigure the request for this call only

**then**: `msg:&#39;&#39;`, (err, body{})



### doSend(apiPath, params, httpMethod, then) 

Send a request to the server, receive a response

**Parameters**

**apiPath**: `String`, Request API path

**params**: `Object`, params

**httpMethod**: `String`, HTTP method to use

**then**: , (err, body'')




* * *










