# CSS Cheat Sheet

## Selectors

```css
*       /* Universal */
.element { }  /* Class */
#id { }       /* ID */
element { }   /* Tag */

/* Combinators */
parent > child {}
parent descendant {}
element1 + element2 {}
element1 ~ element2 {}
```

## Colors

```css
color: red;
color: #ff0000;
color: rgb(255, 0, 0);
color: hsl(0, 100%, 50%);
```

## Units & Sizes

```css
px, %, em, rem, vw, vh
width: 100px;
font-size: 1.2rem;
```

## Box Model

```css
margin, border, padding, content
box-sizing: border-box;
border: 1px solid black;
padding: 10px;
margin: 20px;
```

## Typography

```css
font-family: Arial, sans-serif;
font-size: 16px;
font-weight: bold;
line-height: 1.5;
text-align: center;
text-transform: uppercase;
```

## Styling Links

```css
a:link { color: blue; }
a:visited { color: purple; }
a:hover { color: red; }
a:active { color: orange; }
```

## List Styles

```css
ul { list-style-type: square; }
ol { list-style-type: decimal-leading-zero; }
list-style-position: inside;
```

## Mini Project

*Simple Navigation Bar*

```html
<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
  </ul>
</nav>
```

```css
nav ul {
  display: flex;
  list-style: none;
  background: #333;
}
nav ul li a {
  color: white;
  padding: 10px;
  display: block;
}
```

## Display

```css
display: block | inline | inline-block | flex | grid | none;
```

## Floats

```css
float: left | right;
clear: both;
```

## Columns

```css
column-count: 3;
column-gap: 20px;
```

## Position

```css
position: static | relative | absolute | fixed | sticky;
top, right, bottom, left
z-index: 10;
```

## Flexbox

```css
display: flex;
justify-content: center;
align-items: center;
flex-direction: row | column;
flex-wrap: wrap;
gap: 20px;
```

## Grid Layout

```css
display: grid;
grid-template-columns: 1fr 1fr;
grid-gap: 10px;
grid-column: 1 / span 2;
```

## Images

```css
img {
  width: 100%;
  height: auto;
  border-radius: 10px;
}
```

## Media Queries

```css
@media (max-width: 768px) {
  body { font-size: 14px; }
}
```

## Card Project

*Basic Card Layout*

```html
<div class="card">
  <img src="img.jpg" alt="">
  <h3>Title</h3>
  <p>Description</p>
</div>
```

```css
.card {
  border: 1px solid #ccc;
  border-radius: 10px;
  padding: 20px;
  width: 300px;
  box-shadow: 0 4px 6px rgba(0,0,0,0.1);
}
```

## Pseudo

```css
:hover, :focus, :nth-child(2), ::before, ::after
```

## Variables

```css
:root {
  --main-color: #3498db;
}
body {
  background: var(--main-color);
}
```

## Functions

```css
calc(), rgba(), hsl(), var(), url()
width: calc(100% - 50px);
```

## Animations

```css
@keyframes slideIn {
  from { transform: translateX(-100%); }
  to { transform: translateX(0); }
}
.box {
  animation: slideIn 1s ease-in-out;
}
```

## Organization

```css
/* Reset CSS */
/* Variables */
/* Base Styles */
/* Layout */
/* Components */
/* Utilities */
```

Split CSS into multiple files or use comments to separate sections.
