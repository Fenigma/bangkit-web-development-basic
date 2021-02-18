# Module 6-7 (Flexbox and JavaScript)

On this part of module, the course teaches about Flexbox and JS. Here is my learning notes:

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
5. 