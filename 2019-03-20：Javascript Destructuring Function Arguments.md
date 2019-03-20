## One of ECMAScript6 features is object destructuring.  
### If you aren't familiar with JavaScript destructuring, 
### it basically provides a shorter syntax for extracting an object key's value without the dot notation mess:

```
// A javascript object
const myObject = { x: 1, y: 2 };

// Destructuring
const { x, y } = myObject;
// x is 1, y is 2
```

### The basic syntax for destructuring is fairly simple,
### but using destructuring with function arguments can be a bit more difficult 
### when those argument values should have default values.  
### The following is a function with arguments having default values:
```
function myFunction(text = "", line = 0, truncate = 100) {

    // With default values, we can avoid a bunch of:
    text = text || "";
    line = line || 0;
    truncate = truncate || 100;
}
```
### Regardless of language, 
### if a function takes more than 3 parameters, 
### it's probably best to pass in an object name options or config that contains possible key/values; 
### the equivalent would look like:
```
function myFunction(config) {

}

// Usage
myFunction({
    text: "Some value",
    line: 0,
    truncate: 100
})
```
### What if you want to use destructuring in JavaScript function arguments though?
### The following function signature would become:
```
function myFunction({ text, line, truncate }) {

}
```
### If you want to define default values in the function configuration, you'd use the following:
```
function myFunction({ 
  text = "", 
  line = 0, 
  truncate = 100 
} = {}) {
 // Even if the passed in object is missing a given key, the default is used!
}
```
### Setting a default with `= {}` is important, with no default the following example would throw an error:
```
TypeError: Cannot destructure property `key` of 'undefined' or 'null'
```
### Destructuring is an awesome language feature but can lead to confusion and even errors.
### Hopefully the basics provided in this guide can help you to navigate using JavaScript destructuring with functions!

## Apply with React.js
### It is useful for readability and make components more concise

### Example without desctructuring syntax
```
const Input = props => {
  return (
    <div className={props.wrapClass}>
      <label 
        htmlFor={props.id} 
        className={props.labelClass}
      >
        {props.label}
      </label>
      <input 
        type={props.type} 
        id={props.id} 
        placeholder={props.placeholder}
        value={props.value}
        onChange={(e) => props.onchange(e.target.value)}
        className={props.inputClass} />
    </div>
  )
}

class App extends Component {
  state = {
    name: ""
  }
  changeName = newName => {
    this.setState({ name: newName })
  }
  render() {
    return (
      <div>
        <Input 
          type="text" 
          id="name" 
          label="Name" 
          placeholder="Enter your name" 
          value={this.state.name} 
          onChange={changeName}
          labelClass="form-label"
          inputClass="form-input"
          wrapClass="form-input-wrap"
        />
        <p>Hello {this.state.name}</p>
      </div>
    );
  }
}
```
### Example with desctructuring syntax, Hell yeah~!
```
function Input ({id, label, onChange, labelClass, inputClass, wrapClass, ...props}) {
  return (
    <div className={wrapClass}>
      <label 
        htmlFor={id}
        className={labelClass}
      >
        {label}
      </label>
      <input 
        id={id}
        {...props}
        onChange={(e) => onChange(e.target.value)}
        className={inputClass} />
    </div>
  )
}
```
