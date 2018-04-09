# Programming for Non Programmers

## Warmup Activity

- Imagine someone open up their browser and types in `https://facebook.com` and hits enter.
- Visualize what happens between the moment that request is made and the page is shown on the screen.
- Be as creative as possible! Come up with an analogy!

## Overview of the Web

- What is back end vs front end code? Where do they run?
- What is an HTTP request, and what is the expected response?

![Request-Response Cycle](img/request_response.png)

## Introduction to HTML and CSS

##### HTML and CSS

- HTML and CSS work together to create the front end structure and design.
- Front end frameworks and the grid system.

##### Tags:

- Tags allow you to set up your document's structure.
- Attributes allow you to add additional information to a tag.
- Attributes also allow you to bridge the gap between HTML and CSS.

##### Div:

- Divs are like empty rectangles.
- They help organize content on the page.

```html
<div class="margin-top-20 logo">
    My Text Inside
</div>
```

##### Input:

- Inputs allow users to enter data to be saved to a database.
- They come in different forms to facilitate the specific data entry type.

```html
<input type="text" class="form-control" />
```

##### Select list:

- Select lists allow users to select options from a dropdown menu.

```html
<select>
    <option value="USA">United States</option>
</select>
```

##### Button:

- Buttons are HTML elements that give users the ability to submit the data entered as well as transition to new pages.

```html
<button>My Button</button>
```

##### Images:

- Image tags accept a relative path or absolute URL to the location of an image file. They then display the image in the browser window:

```html
<img src="images/puppies.jpg />
```

## CSS Stylesheets

- CSS stylesheets provide the look and feel of the website.
- There are two main ways of referencing CSS in the HTML so you can apply styles - classes and IDs.
- Consider this HTML:

```html
<div class="header">
    My Header
</div>
```

- Here we have a class attribute that can serve as the bridge between the HTML and CSS code.
- Here is how we would reference this class in the stylesheet:

```css
.header {
    font-size:20px;
    background-color:blue;
}
```

- We could also use IDs to reference the style:

HTML

```html
<div id="header">
    My Header
</div>
```

CSS

```css
#header {
    font-size:20px;
    background-color:blue;
}
```

> **The main difference between classes and IDs is that classes can be used multiple times in the HTML document whereas IDs should only be used once.**

##### Linking CSS with HTML

- In order to run external CSS you need to link it to the HTML. This usually goes in the `head` tag:

```html
<link rel="stylesheet" href="css/style.css" />
```

##### Linking JS with HTML

- JavaScript enables interaction with the page.
- In order to run external JS you need to link it to the HTML. This usually goes before the closing `body` tag:

```html
<script src="js/app.js"></script>
```

## HTML Markup Lab

- [Please refer to the project here](https://github.com/arun-projects/HTML-Form)

## A Little More on CSS

- CSS is a powerful language and has an easy-to-learn syntax.
- CSS can be used to achieve everything from pixel-perfect colors to advanced animations.
- If you want to see a couple examples, check these out:
	- [http://codepen.io/juliangarnier/pen/idhuG](http://codepen.io/juliangarnier/pen/idhuG)
	- [http://www.rleonardi.com/interactive-resume/](http://www.rleonardi.com/interactive-resume/)

## CSS Colors

- There are three main ways to use colors in CSS - semantic, HEX values, and RGB(A) values.

##### Semantic:

```css
div {
    background-color:black;
}
```

##### HEX:

```css
div {
    background-color:#000000;
}
```

##### RGBA:

```css
div {
    background-color:rgba(0,0,0,0.5);
}
```

## CSS Gradients

- CSS gradients were introduced as of CSS3.
- They allow for a gradient of colors to be applied across multiple solid colors.
- These are hard to write via raw CSS, so generators are often used.
- Let's have a look at one [here](http://www.colorzilla.com/gradient-editor/).

## Layout with HTML and CSS

- Laying out elements on the page usually leverages HTML and CSS together to create variants of a 12-column grid.
- The overall layout is created by mixing and matching rows with variable width columns.
- To achieve more advanced layouts, rows and columns can also be nested.
- We will try a simple example using the `float` property.

![12-Column Grid](img/grid.jpg)

## About Me Lab

- [Please refer to the project here](https://github.com/arun-projects/about_me)

## Introduction to JavaScript

- JavaScript is a language that is primarily used to make your HTML and CSS components dynamic.
- It can be used to respond to events (clicks, hovers, blurs, etc.) and also manipulate the DOM.
- JavaScript has evolved over the years to perform more and more tasks, and can even now do things such as pull data from the backend and repopulate the UI (think [airbnb.com](https://www.airbnb.com/)).

## Using JavaScript Files

- Like CSS, JavaScript files are linked to the HTML to run them.
- Google Chrome and other browsers wrap in a "JavaScript Runtime", which is essentially a program designed to interpret our JavaScript code and convert it to "machine code" (0's and 1's).
- To use a JS file with a HTML file, we will incorporate the `<script>` tag:

```html
<script src="app.js"></script>
```

## Coding in JavaScript

##### Strings

Strings are simply pieces of text denoted by quotation marks. An example may be:

```javascript
"Hello World!"
```

##### Integers

Integers are simply whole numbers without any decimals. An example may be `45` or `2`.

##### Variables

Variables allow us to represent information by a specific set of characters. Therefore we do not have to keep typing the same code over and over:

```javascript
var saying = "Hello World!";

alert(saying);
```

Variables can be overwritten by referring to them without the `var` keyword:

```javascript
var saying = "Hello World!";

saying = "Hey Arun!";

alert(saying); //Gives us "Hey Arun!"
```

##### Arrays

Arrays allow us to be able to store a set of data in one place. Let's say we want to look up information about a particular user. An array of a user's information may look like this:

```javascript
var arun = ["Arun", "Instructor", 27, "San Francisco"];
```

We can access pieces of this information through the index value:

- First Name: `arun[0]`
- Age: `arun[2]`

##### Functions

Functions allow us to write code once and call it a number of times throughout our program. This helps us keep code maintainable and also helps to make it dynamic.

```javascript
function sayHello() {
	alert("Hello World!");
}
```

We can also pass in data to perform a dynamic operation:

```javascript
function addTwo(num1, num2) {
	alert(num1 + num2);
}
```

When using JavaScript to perform operations, you may need to `return` the data outside of the function. You can do this like so:

```javascript
function addTwo(num1, num2) {
	return num1 + num2;
}
```

To call a function after it is written, you refer to it by its name:

```javascript
sayHello();

addTwo(1, 2);
```

##### Loops

Loops allow you to perform an operation a set number of times. This is very widely used in most programming languages. A simple `for` loop can be written like this:

```javascript
for (var i = 0; i < 20; i++) {
	console.log(i);
}
```

## JavaScript Game Lab

- [TicTacToe](https://github.com/arun-projects/TicTacToe)
- [Memory Game](https://github.com/arun-projects/Memory)

## Control Flow in JavaScript
- Often times you want to make sure certain blocks of code get activated under specific circumstances.
- Control flow structures help you specify when you want blocks of code to run based on a number of true/false conditions.

## Conditionals

- Standard `if, else` blocks
- Slightly more advanced `if, else if, else` blocks

## Comparison Operators

- AND `&&`, OR `||`
- `>`, `<`, `>=`, `<=`

## Control Flow Exercise: The Marathon Runner
- Create a prompt that asks the user what their best marathon time was.
- If their time was between 4 to 5 hours, alert the user that their time was average.
- if the time was between 2 to 4 hours, alert the user that their time was excellent.
- If the time was greater than 5 hours, alert the user that they need to speed up!

## In-Class Lab: Part 1 
- Write a for loop that will iterate from 0 to 20. 
- For each iteration, it will check if the current number is even or odd, and report that to the screen (e.g. "2 is even").
- Do this using a `FOR` loop and then try to replicate the same functionality with a `WHILE` loop.
- You will have to look up the syntax for the while loop, and also the modulus (%) operator.

## In-Class Lab: Part 2
- Define a function max() that takes two numbers as arguments and returns the largest of them. Use the if-then-else construct available in Javascript.
- Define a function maxOfThree() that takes three numbers as arguments and returns the largest of them. Check out the [Math](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math) module built in to JavaScript to help you.