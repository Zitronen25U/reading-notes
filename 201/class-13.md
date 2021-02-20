# The past, present, and future of local storage

## Cookies

- Cookies are included with every HTTP request, thereby slowing down your web application by needlessly transmitting the same data over and over
- Cookies are included with every HTTP request, thereby sending data unencrypted over the internet
- 4 KB of data limit.
  - can slow down your application

### What we want

- a lot of storage space 
- on the client end
- persists beyond a page refresh
- isn't transmitted to the server

## Introducint HTML5 Storage

- can be referred as local storage or DOM storage
- its a way for we pages to store named key/value pairs within the client web browser
- data persists even if you navigate away from the web page


### Detect if your browser supports it

> function supports_html5_storage() {
  try {
    return 'localStorage' in window && window['localStorage'] !== null;
  } catch (e) {
    return false;
  }
}

## Using HTML storage

- can store data with a named key, an d then you can retrieve that data with the same key. 

### EXAMPLE

> interface Storage {
  getter any getItem(in DOMString key);
  setter creator void setItem(in DOMString key, in any data);
};

