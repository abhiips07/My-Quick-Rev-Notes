> source: Angela Yu Course

```js
console.log();

`==` data comparision
`===` data and datatype comparision

// to get text of an element
var.innerHTML
```

## Code syntax
if else if
```js
if (condition1)
	statement1
else if (condition2)
	statement2
else if (condition3)
	statement3
// …
else
	statementN
```

switch
```js
switch (key) {
	case "w":
		// statements
		break;
	case "a":
		// statements
		break;
	default:
		// statements
		break;
}
```

## Math
```js
Math.floor(val);
Math.round();  // ranges from 0 to 1
```

## Timeout
```js
setTimeout(function, time);
// Example
setTimeout(function() {
	// statements
}, 100);
```
> :exclamation: setTimeout() is ***non-blocking*** which means it will run when the statements outside of it have executed and then after specified time it will execute.

## Dom

CSS query selector
```js
document.querySelector("h1")
document.querySelectorAll("h1")

document.querySelector("h1").classList.toggle("className");

document.querySelector("h1").setAttribute("key", "value");
Ex: document.querySelector("h1").setAttribute("src", "image.png");
```

## Add Events
```js
element.addEventListener("click", function(event) {
	// code block
	this // used to access the element on which event has occured
	event // used to access data related to event
})
```


## Others
```js
// Play Audio
var sound = new Audio("sound.mp3");
sound.play();
```

## jQuery
```js
// syntax
$(css-selector).function()

$(document).keypress(function(event) {
	$("h1").text(event.key);
})
$("body").addClass("classname");
$("body").removeClass("classname");
$("body").text("texty");
$("body").fadeIn(time);
$("body").fadeOut(time);
```