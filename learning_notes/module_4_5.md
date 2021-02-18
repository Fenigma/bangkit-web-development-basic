# Module 4-5 (Styling)
On this part of the course, I learned new things about CSS. These are my findings:

1. Learned about **attribute selector** (Example: `a[href]` means apply styling on `<a> elements with href attribute`). This can also be combined with regex like syntax (Example: `a[href$=".com"]` which will trigger styling on `<a> elements with href attribute which value ends with ".com"`).
2. Learned about **universal selector** (Example: `*[lang^=en]` which will apply styling to `all elements with lang attribute which value starts with "en"`). To apply styling to all elements, we can use `*` (Example: `* { color: red; }`).
3. Learned about **combinators** which consits of 4 parts: `Adjacent Sibling Selector (+)`, `General Sibling Selector (~)`, `Child Selector (>)`, and `Descendant Selector (space)`. These are applied in css file like following:
```
(element) (selector) (element) {
    (property): (value);
}

div + p {
    color: green;
}

(selector == +)       --> the p that comes directly after div will be colored green.
(selector == ~)       --> all p that comes after div will be colored green.
(selector == >)       --> the p which is directly inside a div will be colored green.
(selector == {space}) --> all p which is inside a div will be colored green (even if not direct child of div -> ex: <div><section><p>).
```
4. Learned about **pseudo-selector** which is divided into **`Pseudo Selector`** (Example: `:hover`, `:link`, `:visited`, `:active`) and **`Pseudo-element Selector`** (example: `::before`, `::after`, `::first-letter`). For more info, check this [resource](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements).
5. Learned about **many more styling** with notes like following:

**Font Styling** (look more at [resource](https://www.dicoding.com/academies/123/tutorials/4218?from=4217))
```
font-family     --> which font to use. (Example: font-family: "Open Sans", Verdana, sans-serif;)
font-size       --> specify the size of font (Example: em, rem, vw, vh, px, %, xx-small, x-small, small, medium, large, ...)
font-weight     --> boldness (value of `100 - 900` or a descriptive term like: `normal, bold, boled, lighter`)
font-style      --> giving style (normal, italic, oblique)
font-variant    --> other variant of fonts (example: small-caps)

font            --> to abbreviate all above     
target { font: style, weight, variant, size, font-family ; }
example: h1 { font: italic, 1em, sans-serif; }
```

**Text Styling** (look more at [resource](https://www.dicoding.com/academies/123/tutorials/4224?from=4221))
```
line-height     --> give a height to every line in a text (Example: p {line-height: 2em;})
text-indent     --> give an indentation before first character of text (Example: p {text-indent: 2em;})
text-align      --> give alignment (center, right, left, justify)
text-decoration --> give other decoration (underline, overline, line-through, none)
text-transform  --> (none, capitalize, lowercase, uppercase) (capital => first letter become upper, lower/uppercase => all character become lower/upper)
letter-spacing  --> adjust spacing of each char (Ex: p {letter-spacing: 2px;})
word-spacing    --> adjust spacing of each word (Ex: p {word-spacing: 1.5em;})
text-shadow     --> give shadow to text (ex: p {text-shadow: (horizontal) (vertical) (blur level) (color) }). (p {text-shadow: -2px 3px 0.7 red; })
```
6. Learned that we can use fonts from goole by using `@import_url('{URL HERE}')` in our CSS file for importing google's CSS font. Manually we can use `@font-face` to define our own font. For example:
```
style.css
=========
@import url('https://fonts.googleapis.com/css?family=Quicksand:400,700&display=swap');
body {
    font-family: 'Quicksand', sans-serif;
}

Example using @font-face
========================
@font-face {
    font-family: "myfont";
    src: url('FILE-FONT.TTF'); /*or an URL for .ttf*/
}
p {font-family: 'myfont';}
```
7. Learned about **`box element of CSS`**. Since it has lots of topic, it is better to look at [source](https://www.dicoding.com/academies/123/tutorials/5814).
8. Learned shortcut in using **border**. Example: `div {border: width style color;}`. Alsp learned that we can specify shortcut for `border-width` like following: `order-width: 1px 2px 3px 4px; /*top right bottom left*/`
9. Learned how to **center the position of a content**. It can be done by using: `.center { margin: 0 auto; }`
10. Learned about **display**. Here, I learned the difference between `p { display: block;}` and `p { display: inline;}`. [source](https://www.dicoding.com/academies/123/tutorials/5843?from=5838)
11. Learned about **positioning**. There are many positionings available: `Normal Flow / Static Flow`, `relative`, `absolute`, `fixed`. Read [here](https://www.dicoding.com/academies/123/tutorials/5909?from=6153).
```
Normal Flow / Static Flow : The default behaviour. Every block element is rendered in a new line even when there is spare spaces beside it horizontally.

Relative Positioning : Elemenet can be moved up, right, left, down from its initial position without effecting other elements. More about this can be read here: https://www.dicoding.com/academies/123/tutorials/5910?from=5909

Absolute Positioning : Same like relative positioning but it is relative to browser window or parent element if the parent also not in normal flow. When other elements are aware of `element with relative positioning`, they don't aware about the existance of `element with absolute positioning`. Look here: https://www.dicoding.com/academies/123/tutorials/5923?from=5919

Fixed Positioning : Same like absolute positioning but only relative to browser window. The position won't change even if scrolled.

Sticky Positioning : Same like Fixed positioning but other elements are aware of its existance (like Fixed but based on relative, not absolute).
```
12. Learned about **float**  property. Float is easy but have some problematic result when implemented, we might need to use `clear property` (have 3 value: right, left, both) or `overflow:auto`. See [here](https://www.dicoding.com/academies/123/tutorials/5906).
13. Learned that we need to adjust the **viewport** so that the rendered HTML can be shown responsively on smaller devices. Also see number 14 since adjusting only viewport is not enough.
```
    <meta name="viewport" content="width=device-width, initial-scale=1">
```
14. To make the website responsive we can also use **CSS Media Queries** to apply a specific CSS for each size of screen. For more, look [here](https://www.dicoding.com/academies/123/tutorials/5946?from=5945)
```
/* The rule inside the @media will be implemented in device with sreen width < 992px.*/
@media screen and (max-width: 992px) {
  ........
}

Example:
@media screen and (max-width: 700px) {
    #content,
    aside {
        width: 100%;
        padding: 0;
    }
}
```
15. Learned to create **sticky navigation**. Here, I learned to create a navbar that is sticky when scrolled. TO make this, we can use combination of `position: sticky` on the `<nav>` and making the wrapper of `<nav>` have `display: inline`.
```
index.html
==========
<header>
    <div class="jumbotron">
        <h1>Bandung</h1>
        <p lang="id" translate="no">Kota metropolitan terbesar di Provinsi Jawa Barat, sekaligus menjadi ibu kota provinsi tersebut.</p>
    </div>

    <nav>
        <ul>
            <li><a href="#sejarah">Sejarah</a></li>
            <li><a href="#geografis">Geografis</a></li>
            <li><a href="#wisata">Wisata</a></li>
        </ul>
    </nav>
</header>

style.css
=========
nav li {
   display: inline;
   list-style-type: none;
   margin-right: 20px;
}

nav {
   position: sticky;
   top: 0;
}

header {
   display: inline;
}
```
