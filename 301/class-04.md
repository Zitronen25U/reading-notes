# Reading Notes for Class 04

## Fomrs

- HTML elements work differently thatn DOM elements in REACT

- elements naturally keep some internal state in REACT

### EXAMPLE 

```js
<form>
  <label>
    Name:
    <input type="text" name="name" />
  </label>
  <input type="submit" value="Submit" />
</form>
```

- this form accepts a single name

- in normal HTML, it browses to a new page when the user hits submit.

- in React, it is achieved with **CONTROLLED COMPONENTS**

### Controlled Components

- in HTML, normal form inputs

 ```js
  <input><textarea><select>
  ```

- these maintain their own state and update it based on user4 input

- in React, mutable state is kept in the state property components and only updated with **setState()**

- we combine the 2 by making the React state be the "single source of truth"

### EXAMPLE

```js
class NameForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {value: ''};

    this.handleChange = this.handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }

  handleChange(event) {
    this.setState({value: event.target.value});
  }

  handleSubmit(event) {
    alert('A name was submitted: ' + this.state.value);
    event.preventDefault();
  }

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          Name:
          <input type="text" value={this.state.value} onChange={this.handleChange} />
        </label>
        <input type="submit" value="Submit" />
      </form>
    );
  }
}
```

- this example will log the name of the previous form that was noted above

- since the value attrib is set on our form, the display value will always be this.state.value

- since handleChange will run on every key press, the displayed value will update as the user types

### The textarea Tag

- in HTML, <textarea> element defines its text by its children

```js
<textarea>
  Hello there, this is some text in a text area
</textarea>
```

- in REACT it uses a value attribute instead

- a form that uses <textaread> can be written very similary to a form that uses a single line input

```js
class EssayForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      value: 'Please write an essay about your favorite DOM element.'
    };

    this.handleChange = this.handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }

  handleChange(event) {
    this.setState({value: event.target.value});
  }

  handleSubmit(event) {
    alert('An essay was submitted: ' + this.state.value);
    event.preventDefault();
  }

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          Essay:
          <textarea value={this.state.value} onChange={this.handleChange} />
        </label>
        <input type="submit" value="Submit" />
      </form>
    );
  }
}
```

- this.stat.value is initialized in the constructor, so the text area starts off with some text

### The Select Tag

- in html <select> creats a drop down list

```js
<select>
  <option value="grapefruit">Grapefruit</option>
  <option value="lime">Lime</option>
  <option selected value="coconut">Coconut</option>
  <option value="mango">Mango</option>
</select>
```

- in React, instead of using selected value, uses a value attribute on the root select tag

```js
class FlavorForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {value: 'coconut'};

    this.handleChange = this.handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }

  handleChange(event) {
    this.setState({value: event.target.value});
  }

  handleSubmit(event) {
    alert('Your favorite flavor is: ' + this.state.value);
    event.preventDefault();
  }

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          Pick your favorite flavor:
          <select value={this.state.value} onChange={this.handleChange}>
            <option value="grapefruit">Grapefruit</option>
            <option value="lime">Lime</option>
            <option value="coconut">Coconut</option>
            <option value="mango">Mango</option>
          </select>
        </label>
        <input type="submit" value="Submit" />
      </form>
    );
  }
}
```

- makes it so <input type = "text">, <textarea>, and <select> all work similarly.

- each accepts a value attribute that you can use for a controlled pair

### The File Input Tag

- in HTML, using <input type="file"> lets the user choose one or more files from their device to be uploaded to a server or manipulated by js

- is a read-only value

- an **uncontrolled** component in React

### Handling Multiple Inputs

- when you need to handle multiple controlled input elements, you can add a **name** attribute to each element

- can choose what function to use based off of the name

```js
event.target.name
```

### Controlled Input Null Value

- specifying the value prop on a controlled component = prevent user from changing the input unless you desire so

- if value is specified, but the input is still editable, you may have accidently set value to undefined or null

### Alternatives to controlled components

- you may want to use uncontrolled components because you need to write an event handler for every way your data changes along the pipeline

## React Bootsrap, Forms

- this seems so much easier than inputing all of this data on my own.

[Return!](/class301main.md)
