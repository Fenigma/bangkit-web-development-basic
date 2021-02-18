# Module 6-7 (Flexbox and JavaScript)

On this part of module, the course teaches about Flexbox and JS. Here is my learning notes:

## Flexbox (Module 6)

1. Learned that **Flexbox** is another way to create a reponsive CSS other than what is taught on module 4-5. Flexbox can be adjusted based (relative) on its container. There are 2 elements of flexbox: `flex-container` and `flex-item`. In the CSS code, `flex-container` is the parent element with `{display: flex}` and `flex-item` is the child element with `{flex-grow: {value here};}` or `{flex-basis: {value % here};}`.
```
Example:
========
.container {
    display: flex;
    width: 1000px;
    height: 400px;
}
.box {
    margin: 5px;
    border: 1px solid red;
}
.first {
    flex-grow: 2;
}
.second {
    flex-grow: 3;
}

<div class="container">
   <div class="box first"></div>
   <div class="box second"></div>
</div>
```
2. Flex can be adjusted to some orientation using **`flex-direction property`**. There are 4 direction:
- row           : default value, flex-item will be rendered horizontally from left to right.
- row-reverse   : flex-item will be rendered horizontally from right to left.
- column        : flex-item will be rendered vertically from top to bottom.
- column-reverse: flex-item will be rendered vertically from bottom to top.

3. Learned the difference between **flex-grow** and **flex-basis**. `{flex-grow: 2;}` is not necessarily 2 times the size of `{flex-grow: 1;}`, it will just give a non-exact proportion that `{flex-grow: 2;}` will be bigger than `{flex-grow: 1;}`. To make sure that the proportion is exact, `flex-basis` can be used. For more, look [here](https://www.dicoding.com/academies/123/tutorials/5752?from=5759) 
```
* {
    box-sizing: border-box;
}

.flex-row {
    display: flex;
    flex-direction: row;
    border: 2px solid blue;
    margin: 2px;
}

.box {
    flex-basis: 25%;
    border: 1px solid red;
    margin: 5px;
}
.double-box {
    flex-basis: 50%;
    border: 1px solid red;
    margin: 5px;
}

<div class="flex-row">
    <div class="box">1</div>
    <div class="box">2</div>
    <div class="double-box">3</div>
</div>

We see that the 3rd box is literally 2 times the size of other box.
```
4. Learned that **flex is already responsive but we still need to add viewport and @media screen** and adjust so that the padding and margin inside the `flex-item` is not too big for smaller devices (still need to add @media screen to make sure that when viewport is small, we reduce the padding/margin).

## Javascript (Module 7)
Here are some of my notes when studying about JS in the module:
1. Learned **the difference between `var` and `let`**. When using `var` for decalaring variable, we can initiate the variable before decaring it (it is called hoisting). We can't do this with `let`.
```
a = 10;
var a;
console.log(a);

/* output: 10 */
```

2. Learned about **object**. It is equivalent to dict() in Python.
```
let object = {key1: "value1", key2: "value2", key3: "value3"}
```

3. Noted the type juggling in JavaScript between operator `==` and `===`.
```
const aString = '100';
const aNumber = 100

console.log(aString == aNumber) // true
console.log(aString === aNumber) // false
```

4. Learned about `for...of` for iterating elements.
```
let myArray = ["a", "b", "c", "d"];

for(const arrayItem of myArray) {
    console.log(arrayItem)
}
```

5. Learned how to **access things inside the document**.
- getElementById("display")          --> return element with id="display"
- getElementsByName("button")        --> return element with attribute name="button"
- getElementsByClassName("button")   --> return collection of elements that have class="button"
- getElementsByTagName("div")        --> return collection of `<div>` elements 
- querySelector(".box")              --> return first element with class="box"
- querySelectorAll("#someid")           --> return collection of elements that have id="someid"

6. Learned how to **manipulate ATTRIBUTE of element**. We can user `setAttribute()` and `getAttribute()`.
```
someElement.setAttribute("attribute_name", "attribute_value");

We can obtain information of an attribute by using getAttribute()
```

7. Learned how to **manipulate CONTENT of element**. Use `innerHTML` or `innerText`. With innerHTML, we can insert HTML elements to the HTML and it will be rendered as HTML. If using innerText, what we inserted will be rendered as text (Example: `<b>something</b>` will be rendered as `<b>something</b>` instead of `something` in bold style.)
```
let caption = document.querySelector("#caption");
caption.innerHTML = '<b>This is the changed caption</b>';
```

8. Learned how to **create new elements inside the document**. We need to follow 3 steps:
- Create the element                            --> createElement()
- Create the content of the element / set attrs --> innerHTML (or innerText)
- append the created element into the document  --> appendChild()
```
Type this in console
====================

let newElement = document.createElement('p');
newElement.innerHTML = '<b>This</b> is the new paragraph';
document.body.appendChild(newElement); // if we want to append to <body>
```

9. Learned how to **add listener**. THis can be done using `addEventListener( {event}, {function} )`.
```
let myimg = document.getElementById("profile-picture");
myimg.addEventListener('click', function() {alert("clicked");})
```
