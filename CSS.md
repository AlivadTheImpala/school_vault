Basic Syntax

Selectors
- Universal Selector
- Type Selectors
- Class Selectors
- Grouping Selectors
- Chaining Selectors
Combinators
- descendant combinator
Basic Properties to start with
- color
- background-color
- font-family
- font-size
- font-weight
- text-align

Image height and width
properties
- height
- width
if you wanted to keep an images aspect ratio. set the height to auto and adjust the width property. 

Linking an external CSS file to HTML. This is the preferred and most common method. although you can add styles directly to the head of an html file, or directly on a specific html element.
```html
<!-- index.html -->

<head>
  <link rel="stylesheet" href="styles.css" />
</head>
<!-- The `rel` attribute is required, and it specifies the relationship between the HTML file and the linked file.-->
```