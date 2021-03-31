# Class 13 Reading Notes

## Sending Form Data

### Client/Server architecture

- at its most basic, the web uses a client/server architecture that can be summarized as follows

- client sends a request to a server, using HTTP

- server answers with the same protocol

- HTML form on a web page is nothing more than a convenient user-freindly way to configure HTTP request to send data to a server

### On the client side: defining how to send the data

- the ```html<form>``` element defines how data will be sent

- all of its attributes are designed to let you configure the request to be send when a user hits submit

- the two most important attributes are
  - ***action***
  - ***method***

### The Action Attribute

- the action defines where the data gets sent. its val must be a valid realative or absolute URL.

- if attribute isn't provided, the data will be sent to the URL of the page containing the form - Current page --

In this example, the data is sent to an absolute URL — https://example.com:

```js
<form action="https://example.com">
```

Here, we use a relative URL — the data is sent to a different URL on the same origin:

```js 
<form action="/somewhere_else">
```

When specified with no attributes, as below, the <form> data is sent to the same page that the form is present on:

```js
<form> 
```

### The Method Attribute

- the method defines how the data is sent

- HTTP
- get
- post

### The Get Method

- method used by the browser to ask the server to send back a given request

```js
form action="http://www.foo.com" method="GET">
  <div>
    <label for="say">What greeting do you want to say?</label>
    <input name="say" id="say" value="Hi">
  </div>
  <div>
    <label for="to">Who do you want to say it to?</label>
    <input name="to" id="to" value="Mom">
  </div>
  <div>
    <button>Send my greetings</button>
  </div>
</form>
```

- get here has been used, you will see www.foo.com/?say=Hi&to=Mom appear

- has a series of values
  - say
  - to

### The POST Method

- a little different

- browser uses to talk to server when asking for a respons that takes into account the data provided in the body of the HTTP request

``` js
<form action="http://www.foo.com" method="POST">
  <div>
    <label for="say">What greeting do you want to say?</label>
    <input name="say" id="say" value="Hi">
  </div>
  <div>
    <label for="to">Who do you want to say it to?</label>
    <input name="to" id="to" value="Mom">
  </div>
  <div>
    <button>Send my greetings</button>
  </div>
</form>
```

### Viewing HTTP Requests

- never displayed to user

- to see:

1. Open the developer tools.
2. Select "Network"
3. Select "All"
4. Select "foo.com" in the "Name" tab
5. Select "Headers"

### On the server side: retrieving the data

- whichever HTTP method you choose, the server receives a string that will be parsed in order to get the data as key/valu pairs

### Example: Raw PHP

- PHP offers some global objects to access the data. 

- if you've used POST, the following example just takes the data and siplays it to the user

```js
<?php
  // The global $_POST variable allows you to access the data sent with the POST method by name
  // To access the data sent with the GET method, you can use $_GET
  $say = htmlspecialchars($_POST['say']);
  $to  = htmlspecialchars($_POST['to']);

  echo  $say, ' ', $to;
?>
```

### Security Issues

- Each time you send data to a server, you need to consider security. HTML forms are by far the most common server attack vectors (places where attacks can occur).

- The problems never come from the HTML forms themselves — they come from how the server handles data.

### How to prevent security isses???

- NEVER TRUST YOUR USERS

