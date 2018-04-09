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