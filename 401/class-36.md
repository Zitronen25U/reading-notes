# ES6 and React

- introduces many changes to JS

- CONST vs Let

## Arrow Functions

- The arrow function expression syntax is a shorter way of creating a function expression

```js
let func = (a) => {} // parentheses optional with one parameter
let func = (a, b, c) => {} // parentheses required with multiple parameters
```

## Template Literal

- template literal is using the backticks to allow var's declared in strings

## implicit returns

- the word return is implied in the arrow functin and can be ommitted

```js
let func = (a, b, c) => a + b + c 
```

## Inheritance

- extends keywork creates a subclass

```js
class Inheritance extends Func {
  constructor(a, b, c) {
    super(a, b)

    this.c = c
  }

  getProduct() {
    return this.a * this.b * this.c
  }
}

let y = new Inheritance(3, 4, 5)
```

## Callbacks

- Promises represent the completion of an asynchronous function

- They can be used as an alternative to chaining functions

```js

// ES6 Callback

function doSecond() {
  console.log('Do second.')
}

function doFirst(callback) {
  setTimeout(function () {
    console.log('Do first.')

    callback()
  }, 500)
}

doFirst(doSecond)

```

```js
// ES6 Promise

function makeRequest(method, url) {
  return new Promise((resolve, reject) => {
    let request = new XMLHttpRequest()

    request.open(method, url)
    request.onload = resolve
    request.onerror = reject
    request.send()
  })
}

makeRequest('GET', 'https://url.json')
  .then((event) => {
    console.log(event.target.response)
  })
  .catch((err) => {
    throw new Error(err)
  })


```