# HTML Cheat Sheet

## Basic Tags

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Page Title</title>
  </head>
  <body>
    <!-- Your content goes here -->
  </body>
</html>
```

## Comments

```html
<!-- This is a comment -->
```

## Style & Color

```html
<h1 style="color: red; font-family: Arial;">Styled Heading</h1>
<p style="background-color: lightblue;">Colored Background</p>
```

## Formatting a Page

```html
<h1>Main Heading</h1>
<p>Paragraph text.</p>
<hr>
<br>
<strong>Bold</strong> <em>Italic</em>
```

## Links

```html
<a href="https://example.com">Visit Example</a>
<a href="#section">Jump to Section</a>
```

## Images

```html
<img src="image.jpg" alt="Description" width="200">
```

## Videos & YouTube iFrames

```html
<video controls>
  <source src="video.mp4" type="video/mp4">
</video>

<iframe width="560" height="315" src="https://www.youtube.com/embed/VIDEO_ID" frameborder="0" allowfullscreen></iframe>
```

## Lists

```html
<ul>
  <li>Unordered item</li>
</ul>
<ol>
  <li>Ordered item</li>
</ol>
<dl>
  <dt>Term</dt>
  <dd>Definition</dd>
</dl>
```

## Tables

```html
<table>
  <tr>
    <th>Heading</th>
    <th>Heading</th>
  </tr>
  <tr>
    <td>Data 1</td>
    <td>Data 2</td>
  </tr>
</table>
```

## Divs & Spans

```html
<div style="border: 1px solid black;">Block container</div>
<span style="color: blue;">Inline text</span>
```

## Input & Forms

```html
<form action="/submit" method="post">
  <label for="name">Name:</label>
  <input type="text" id="name" name="name">
  <input type="submit" value="Submit">
</form>
```

## iFrames

```html
<iframe src="https://example.com" width="300" height="200"></iframe>
```

## Meta Tags

```html
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="A short description of the page">
```

---

## Head Element

```html
<head>
  <title>My Page</title>
  <meta charset="UTF-8">
  <link rel="stylesheet" href="style.css">
</head>
```

## Text Basics

```html
<h1>Heading 1</h1>
<p>This is a paragraph.</p>
<b>Bold</b> <i>Italic</i>
```

## List Types

```html
<ul>
  <li>Item A</li>
</ul>
<ol>
  <li>Item 1</li>
</ol>
```

## Add Links

```html
<a href="https://example.com">Click Here</a>
```

## Add Images

```html
<img src="pic.jpg" alt="Image" width="150">
```

## Semantic Tags

```html
<header>Header content</header>
<nav>Navigation links</nav>
<main>Main content</main>
<article>Article section</article>
<footer>Footer info</footer>
```

## Create Tables

```html
<table>
  <thead>
    <tr><th>Name</th><th>Age</th></tr>
  </thead>
  <tbody>
    <tr><td>Alice</td><td>24</td></tr>
  </tbody>
</table>
```

## Forms & Inputs

```html
<form>
  <input type="text" placeholder="Your Name">
  <input type="email" placeholder="Your Email">
  <textarea placeholder="Message"></textarea>
  <button type="submit">Send</button>
</form>
```
