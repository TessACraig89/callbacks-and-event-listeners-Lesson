# Callbacks and Event Listeners

# Building an Interactive App In The Browser

## Lesson Objectives

1. Execute Javascript in a web page
1. The DOM
1. Select Elements from the DOM
1. Execute code on a click event
1. Use callbacks with click events
1. Understand anonymous functions
1. Use `debugger`

## Execute Javascript in a web page

```html
    <script type="text/javascript" src="app.js"></script>
```

You can link a JS page to HTML using a script tag in HTML. The script tag should go at the bottom of the page, right before the closing </body> tag so it loads after the HTML. 

## The DOM

The DOM or Document Object Model is how the browswer internally models what needs to be rendered. When we talk about accessing attributes, changing attributes, adding event listeners, etc. this all happens by use of the DOM. Therefore, when we talk about it we would say "Select an element from the DOM", not "Select an element from the page". Don't worry about *how* the browser models the DOM, just know that it does. 

## Selecting elements from the DOM 
Three ways:

```javascript
document.getElementByID('someId');
document.getElementsByClassName('someClass');
document.getElementsByTagName('div');
```

**Watch out:** note the plural on elements for class and tag! Because they return multiple elements. Since they return multiple elements, the results have to be treated differently than the result of 'getElementById'.

## Execute code on a click event

```javascript
// Select an element
let logInButton = document.getElementById('logInButton');

// Add Event Listener
logInButton.addEventListener("click", (event) => {
  // Do something to the event here like:
  event.target.setAttribute("style", "color:indigo");
  logInUser();
})
```

### Callbacks

1. Callbacks are functions, in a specific role in the way that a contestant could be an athlete in a specific role. 
1. The roll of callbacks are that they are passed to other functions as an arguement. 
1. They can be either anonymous functions, or named functions. 
1. Anonymous functions are just functions without names. They never get assigned to variables!

Anonymous: 

```javascript
logInButton.addEventListener("click", () => {
  alert("HI, I'M IN A CALLBACK FUNCTION");
})
```

Named:

```javascript
logInButton.addEventListener("click", throwConfetti)
```

**Watch out:** You can't use arguments in a callback! Because an argument has to go in parentheses, and parentheses automatically INVOKE our functions! If we want to call a callback with arguments, you must wrap it in an anonymous function like this: 

```javascript
logInButton.addEventListener("click", () => {
  throwConfetti("CONGRATS!!!!");
})
```
## More on Anonymous Functions

Let's look at anonymous functions for a minute outside of event listeners. They are very simple. Let's write two functions, one anonymous, one named that console.log "HELLO WORLD" and call them:

Named:
```javascript

const sayHelloWorld = () => {
  console.log("HELLO WORLD");
}

sayHelloWorld();
```

Anonymous: 

```javascript
(() => {
	console.log("HELLO WORLD");
})();
```

Since it isn't named, we can't envoke it like we normally would by putting parens () after the name. 

But we can just wrap the whole thing in parens () and then put parens () at the end. This is called a self invoking funciton. 

Use of these are rare until we start getting fancy with front end frameworks in Unit 3.

## Debugger

`debugger` is a JS keyword that "stops the show" and allows you to interact with your code from that point in your code. You use this in the `console` tab in your Chrome Dev Tools. 

Check out the [documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/debugger)

