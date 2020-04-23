# React
### Starting with react
#### `create-react-app`
Command to create you react project.
#### `ReactDOM.render()`
HTML are render in we page with the use of this function.
### What is JSX
JSX allows us to write HTML elements in JavaScript and place them in the DOM.
### React Components
We can create Two types of component in react
#### Class component
```javascript
    class Car extends React.Component {
        render() {
            return <p>This is Class component</p>;
        }
    }
```
#### Functional component
```javascript
    function Car() {
        return <p>This is functional component<p>;
    }
```
### Constructor in React
```javascript
    class Car extends React.Component {
        constructor() {
            super();
            this.state = {color: "yello"};
        }
        render() {
            return <h2>This is {this.state.color} color</h2>;
        }
    }
```
#### `super()` 
It executes the parent component's constructor method and all the method of parent component.
### `props` in React
props are arguments passed into React components.
```javascript
    <InputField type="text" />;
```
```javascript
    class InputField extends React.Component {
        render() {
            return <input type={this.props.type} />
        }
    }
```
