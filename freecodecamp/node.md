# SASS IN ONE VIDEO (FREECODECAMP)

# Date: 21 / 10 / 2021

## What is SASS

its is a css extension language, its give you css super power, once you see that how easy to write and how logical and orgranige it is, you never write plan css again.

## SETUP

- vscode

  now your browser don't understand SASS, so we need to convert into plan css, but don't scary its very easy. there are many way we can use node.js or we can use gulp or we can use vs code extension that compile you SASS to plan css called "live sass compiler"

- live sass compiler (vs code extension)

### Syntax

there are two type of syntax support by SASS.

1. SCSS SYNTAX

SCSS is superset of css it mean that all valid css it valid in SCSS and it easy and very popular. we use that

```CSS
@mixin button-base(){
  @include typography(button);

  display: inline-flex;
  border: none;
  &:hover{
    cursor: pointer;
  }
}
```

### how to link into html

so we don't link the scss file we link the compiled css file our html, because browser don't recognize scss.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="../dist/css/style.main.css" />
    <title>hello</title>
  </head>
  <body></body>
</html>
```

## important note

we don't edit the main css file, we edit the sass file.

## Variable

to create a variable we use $ to create a variable

```scss
// variable
$bg-lightblue: rgb(82, 177, 221);

body {
  background-color: $bg-lightblue;
}
```

## map

if you familyer with javascript then you can campare to array, maps are list key value pare.

```scss
//map
$font-weight: (
  "small": 200,
  "medium": 400,
  "bold": 600,
);

h1 {
  font-weight: map-get($font-weight, bold);
}
```

## nesting

nesting is the best part of scss

```scss
//nesting
.main {
  width: 80%;
  margin: 0 auto;
  p {
    text-align: center;
    color: $txt-color;
  }
}
```
