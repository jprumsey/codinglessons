# HTML and CSS Cheat Sheet

## HTML

A standard HTML file will look like this:

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title> WEBSITE TITLE </title>
</head>
<body>
    <!-- Content -->
</body>
</html>
```

The content that is *displayed* on the website goes in `<body>`. The content *about* the website such as title, styling, goes in `<head>`.

### Headers, Paragraphs, and Lists
Headers come in sizes 1-6 (1 is largest, 6 smallest):
```html
<h1>This is my website.</h1>
<h2>Today I'll be adding HTML. </h2>
<h3>In my next lesson, I'll be adding CSS. </h3>
<h4>I love coding!</h4>
<h5>I also love making websites!</h5>
<h6>This is great</h6>
```
Paragraphs work the same way but only have one default size:
```html
<p> TEXT </p>
```

With lists, remember to separate your list items in `<li>` tags inside either the numbered or unordered list.

Numbered lists:
```html
<ol>
    <li>TEXT 1</li>
    <li>TEXT 2</li>
    <li>TEXT 3</li>
</ol>
```
Bulleted (unordered) lists:
```html
<ul>
    <li>TEXT 1</li>
    <li>TEXT 2</li>
    <li>TEXT 3</li>
</ul>
```
### Bold, Italics, and Links (Inline Elements)

* Bold: ```<b> Bolded Text </b>``` or ``` <strong> Bolded Text </strong>```
* Italics: ```<i> Bolded Text </i>``` or ``` <em> Bolded Text </em>```

Bold, italicize, or add a link to text **inside** the paragraph, heading, or list:

```html
<p> My <i>favorite</i> animal in the entire world is an elephant. </p>
```

* Links: ```<a href="URL">DISPLAYED TEXT</a>```

ex: 
```html
<p> Click <a href="https://www.the-cs.org"> here </a> to learn more. </p> 
```

### Images and Videos

To add an image to your page:
```html
<img src="PHOTO LINK GOES HERE" />
```

* If adding a picture from the **web** add the image URL (copy image address)
* If adding a picture from your computer, keep it in a folder in your repl.it or wherever your website files are and add the file path

So far, we have only gone over how to add YouTube videos to webpages:
```html
<iframe width="420" height="315"
src="https://www.youtube.com/embed/tgbNymZ7vqY">
</iframe>
```

More info [here](https://www.w3schools.com/html/html_youtube.asp).

## CSS

When adding styling, we need to add ```<style>``` tags to our head (see above) like this:

```html
<head>
    <meta charset="UTF-8">
    <title>WEBSITE TITLE</title>
    <style type="text/css">
    ALL CSS CODE GOES HERE
    </style>
</head>
```

In general, to add styling for a HTML tag, use this template (we use paragraphs in this example, but can do multiple by separating them with commas before the "`{`" ):

```css
p {
    property-name: property-value;
}
```

### Colors

```CSS
p {
    color: red;
}
```

Can use color name, six-digit hexadecimal code (ex: #123ABC) or `rgb(70%, 20%, 10%)` for red, green, blue values.

### Fonts

```html
h1 {
    font-size: 48px;
    font-weight: bolder;
    font-family: Verdana, Helvetica, Arial, sans-serif;
}
```
**Sizing**: Can use `px`, or `em` or `%` for relative sizing.

**Weight**: Different font weights include: lighter, normal, bold, bolder.

**Font style**: Font families include: Arial Black, Comic Sans MS, Georgia, Times New Roman, Verdana, and many other fonts (try some that are on Microsoft Word or Google Docs, for example). CSS starts by trying the first font - if the browser does not support it, it tries the next one after a comma.

**Important!!**:

Be sure to add 

```CSS
body {
    font-size: 100%;
}
```

to your CSS so that fonts re-adjust based on your screen size throughout the whole website when using `em` or `%`.

### Text Alignment

This is the horizontal alignment of a particular text element like headers, paragraphs, and lists:

```CSS
h1 {
   text-align: center
}
h2 {
    text-align: justify
}
```

Can use left, right, center, and justify.

### Text Decoration (over/under/through text)

**Type** with `text-decoration`: underline, overline, line-through
```CSS
h1 {
    text-decoration: underline; 
}
```

**Style** with `text-decoration-style`: wavy, double, dotted, dashed (or none at all)

We can also change the color of this with `text-decoration-color`:

```CSS
h1 {
    text-decoration: underline;
    text-decoration-style: dotted;
    text-decoration-color: blue;
}
```

### Borders

```CSS
p {
    border-width: 2px;
    border-style: solid;
    border-color: black;
}
```
Width can use `px`, `em`, or `%`. Border style can be: dotted, dashed, double, groove, outset, inset, ridges, or solid.

OR put all three properties together on one line:
```CSS
p {
    border: 2px solid red;
}
```

To add a border to only the top, bottom, or one of the sides of the text, use:

```CSS
p {
    border-bottom: 1px dotted black;
    border-top: 1px dotted red;
}
```

### Padding and Margins

Padding adds extra space **between** the element (ex: text) and its border:
```CSS
p {
    padding: 20px;
}
```

Or to add different padding for top/bottom and sides, we can use:

```CSS
p {
    margin: 30px 15px;
}
```

Margins add extra space **around** an element, surrounding the border:
```CSS
p {
    margin: 30px;
}
```
### Background Color

To change the background color of one element (or `body`):
```CSS
p {
    background-color: red;
}
```

### Separating CSS with div, span, and classes:

#### Divs: Grouping Elements

We can change the style for a specific *group* of elements with `<div>`:

```HTML
<div style="color:red;">
<p> TEXT 1 </p>
<p> TEXT 2 </p>
<p> TEXT 3 </p>
</div>
<p> TEXT 4 </p>
```

The same CSS styles we use normally can be put in `style=""`.

#### Spans: Changing Individual Text

Similarly, we can change the styling for text **inside** an element (like a paragraph) like this:

```HTML
<p>Halloween is my <span style="color: red;"> favorite </span> holiday. </p>
```
This works the same way as bolding and italics in HTML, but we can use any CSS styles we want (ex: changing color of text or using background color to "highlight" it).

#### Classes: Styling Specific Elements (Not Groups or Text)

In HTML, we must name the class:

```HTML
 <p class="CLASSNAME"> TEXT </p>
 ```

 In CSS, we select the styling for that particular class:

 ```CSS
 p.CLASSNAME {
     color:red;
 }
 ```

Multiple tags (p, h1, etc.) can belong to the same class:

```CSS
p {
    font-size: 12px;
    font-family: "Times New Roman", Verdana, serif;
}
p.penguin {
    background-color: blue; /* Any p with .penguin will have this */
}
.penguin {
  margin: 30px;  /* Any tag with .penguin will have this */
}
```


#### Selector Hierarchy

Sometimes, styles will conflict because we told CSS to for example, make paragraphs one color. But, it's also possible that somewhere else (like in a div, class, etc.) told we told paragraphs to be another color. The order of preference/priority is:

1. Identifiers (not yet covered)
2. Classes
3. Tags (`p`, `h1`, etc.)
