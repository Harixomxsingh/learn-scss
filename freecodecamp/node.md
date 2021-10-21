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

## Partials

a partials is simply a sass file name with a leading @ , so the @ let sass know that the file is a partials

basically it mean we add another scss file into our scss file

- first create a scss file
- then import into main scss file

```scss
// _resets.scss
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

// import into main scss file

// partials
// to include the file we use @import file directory

@import "./resets";
```

## function

if you know about javascript function then the sass function the kind of same thing.

```scss
// function
@function weight($weight_name) {
  @return map-get($font-weight, $weight_name);
}

h1 {
  font-weight: weight(bold);
  text-align: center;
}
```

## Mixin

Mixin is kind of same thing as function.
basically mixin is a way to write DRY(DON'T REPEAT YOURSELF) code. imagine that we ne to type flex jcc aic 3 time i need mixin and then include it when i want to use.

```scss
// define a mixin
@mixin flexCenter {
  display: flex;
  flex-direction: row;
  gap: 2;
  justify-content: center;
  align-items: center;
}

// then include where you want the flexCenter mixin
// using mixin
.card {
  @include flexCenter();
}
```

we can use value as parameter

```scss
@mixin flexCenter($direction) {
  display: flex;
  flex-direction: $direction;
  gap: 2;
  justify-content: center;
  align-items: center;
}

.card {
  @include flexCenter(row);
}
```

### mixin example 2

```scss
//_variable.scss
$mobile: 800px;

// style.scss
// mixin example 2
@mixin mobile {
  @media screen and (max-width: $mobile) {
    @content;
  }
}

.card {
  @include flexCenter(row);
  @include mobile {
    @include flexCenter(column);
  }
}
```
