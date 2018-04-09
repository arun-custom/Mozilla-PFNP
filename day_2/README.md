# Programming for Non Programmers

## JavaScript Review

- We will take some time to review basic JS from last class.

## Objects

##### Object Notation

```
var myObject = {
	firstName: "Arun",
	lastName: "Sood",
	role: "Instructor"
};
```

##### Accessing Objects

```
myObject.firstName

myObject.lastName

myObject.role
```

##### Objects can have multiple data types

```
var myObject = {
	firstName: "Arun",
	lastName: "Sood",
	sayName: function() {
		alert(this.firstName + " " + this.lastName);
	}
};
```

##### `this` keyword

- `this` refers to the current object scope.
- In the case of `myObject` above, the current scope is `myObject`.
- I could have simply referred to it by `myObject`, but `this` is very DRY.

## Introduction to DOM Manipulation

- One of the most powerful features of JS is its ability to alter the DOM.
- You can respond to events on elements, set HTML dynamically, and perform animations.

## Selecting Elements

- Like CSS, if you want to perform some action on an element you first have to select it.
- We did this in CSS through selectors such as IDs, classes, and pseudo-selectors.
- JavaScript gives us an easy way to select elements based on the same paradigm.

##### getElementById()

```
document.getElementById("my-div");
```

##### getElementsByClassName()

```
document.getElementsByClassName("my-div");
```

##### getElementsByTagName()

```
document.getElementsByTagName("my-div");
```

##### querySelector()

```
document.querySelector("#my-div");
```

##### querySelectorAll()

```
document.querySelectorAll("#my-div.my-class");
```

## Handling Events

- There are many events you may want to respond to with JS including clicks, mouseovers, focuses, etc.
- Events can be listened for and responded to using `addEventListener`.

```
document
.getElementById("my-div")
.addEventListener("click", function() {
	alert("Click worked!");
});
```

- If you need to handle an event that occurs on many elements you will need to attach event listeners to each element individually.
- This can be done by binding the event to a class. Let's take this example:

##### index.html

```
<div class="my-div"></div>
<div class="my-div"></div>
<div class="my-div"></div>
```

##### app.js

```
var myElements = document.getElementsByClassName("my-div");

for (var i = 0; i < myElements.length; i++) {
	myElements[i].addEventListener("click", function() {
		alert("Click worked!");
	});
}
```

## innerHTML

- When you need to replace the HTML inside of an element you can use the `innerHTML` property.

```
document.getElementById("my-div").innerHTML = "<span>New HTML here</span>";
```

## Dynamically Altering Attributes

- There are many reasons why you may want to alter HTML attributes on the fly with JS.
- Changing inline CSS properties is the most common reason to alter attributes. This can be done with the `style` attribute.
- There are "getter" and "setter" methods available to work with attributes:

Getter

```javascript
div.getAttribute("id");
```
Setter

```javascript
div.setAttribute("style", "background-color: red;");
```

## Dealing with Classes

- In JavaScript you will often need to dynamically change HTML class attributes.
- This may be for animation work or for basic stylistic changes.
- There are a few methods you can use to accomplish this:

Add a class:

```javascript
div.classList.add("anotherclass");
```

Remove a class:

```javascript
div.classList.remove("foo");
```

Toggle a class:

```javascript
div.classList.toggle("visible");
```

Check if element already contains a class:

```javascript
div.classList.contains("foo");
```

## Style Switcher Lab

- [Please refer to the project linked here](https://github.com/arun-projects/Style-Switcher)

## Score Keeper Lab

- [Please refer to the project linked here](https://github.com/arun-projects/Score-Keeper)

## Responsive Development with CSS3 Media Queries

- Media queries allow you to apply and remove CSS styling based on the screen dimensions.
- This is important to create truly mobile-friendly layouts.
- To use it you have to specify screen resolution thresholds.
- Let's try an example where we want to show a div where the screen size is larger than 700 pixels:

HTML

```
<div id="my-div"></div>
```

CSS

```
@media(min-width: 700px) {
	#my-div {
		width:400px;
		height:400px;
		border:#000 1px solid;
	}
}
```

- Now where the screen size is below 700 pixels:

CSS

```
@media(max-width: 700px) {
	#my-div {
		width:400px;
		height:400px;
		border:#000 1px solid;
	}
}
```

- You can also combine these values to select a range:

```
@media(min-width: 700px) and (max-width: 900px) {
	#my-div {
		width:400px;
		height:400px;
		border:#000 1px solid;
	}
}
```

## CSS Animations with JavaScript

- CSS animations are handled by the native browser code.
- This means that instead of JavaScript dynamically changing `style` attributes over a period of time, the animation is performed graphically via the C++ or Java code that runs the browser.
- CSS animations are often coupled with JavaScript event handlers to trigger them upon request.

## The `transition` Property

- CSS animations are handled usually by slowly going from one state to another.
- Think of a div for example that upon hover increases its width. A CSS transition essentially makes the process go in slow motion.
- As a result, we can use transitions to animate between many different states.
- Let's take a look at the syntax:

```
transition: property duration easing;
```

- The property here is the specific CSS property you want to animate. This can be a width, height, color, etc.
- If you want to animate across many properties at the same time you can simply specify `all` instead of an actual property name.
- The duration is the length of the animation. It is specified in seconds.
- The easing is the character of the animation. It allows the animation to look more natural by changing its speed of execution dynamically throughout the duration. Here are the allowed values:
	- ease (default)
	- linear
	- ease-in
	- ease-out
	- ease-in-out
	- cubic-bezier(n,n,n,n)

## Transition Fallbacks

- It is also important to note that transitions are relatively new. As a result, certain older browsers may have limited support.
- To reduce the chance of a transition failure, developers normally add "fallbacks" for older browsers.
- These are usually vendor prefixes:

```
transition: width 1s linear;
-webkit-transition: width 1s linear;
-moz-transition: width 1s linear;
-o-transition: width 1s linear;
```

- It is good practice to always put these in when you use transitions.

## The `transform` Property

- Transforms allow you to temporarily change or warp elements to create neat effects.
- Let's take a look at the syntax:

```
transform: transform-function;
```

- This property makes use of transform "functions" that accomplish the effects.
- Here is a list of commonly-used transform functions:
	- translate
	- rotate
	- scale
- A more exhaustive list can be found [here](https://developer.mozilla.org/en-US/docs/Web/CSS/transform).
- Let's say that we wanted to rotate an element upon hover:

```
#my-div {
	width: 200px;
	height: 200px;
	border:#000 1px solid;
	background-color:#900;
}

#my-div:hover {
	transform: rotate(180deg);
}
```

- As you can see, the div rotates instantly. How do you think we can animate the rotation instead?

## CSS Keyframes

- Keyframes allow you to perform complex animations using CSS alone.
- The idea is that instead of transitioning an element from one state to another slowly, you are specifying style attributes that must be accomplished during stops along the animation.
- Here is the syntax:

```
div {
	width:100px;
	height:200px;
	background-color:red;
	-webkit-animation:identifier 5s ease-in-out infinite;
	animation:identifier 5s ease-in-out infinite;
}

@-webkit-keyframes identifier {
	0% {
		top:200px;
	}

	25% {
		top:50px;
	}

	75% {
		left:100px;
	}

	100% {
		top:0;
	}
}

@keyframes identifier {
	0% {
		top:200px;
	}

	25% {
		top:50px;
	}

	75% {
		left:100px;
	}

	100% {
		top:0;
	}
}
```

## Keyframes Exercise

- Try out some of the keyframes along with a transform function.
- One idea may be to rotate a div during a keyframe animation.
- Observe what happens as the div is transformed. Is this what you expected? Why or why not?
- **Bonus:** Now take things a step further and integrate keyframes with JavaScript.
	- Bind a click event to a button that adds a class to the div.
	- Your class should play a keyframe animation of its own.
	- Use at least one transform function in your keyframe.

## Animate.css

- Animate.css is a library that packages a number of useful animations that can be accessed via classes.
- You can read about it here: https://daneden.github.io/animate.css
- Let's practice some of these animations with JavaScript event handling.