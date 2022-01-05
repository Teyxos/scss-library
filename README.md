# Info

This is just a project I'm working on and a guide on how to make a class-based CSS Library I will update this README with some infomation and example in some time

# How to start

## First of all you need a SASS Compiler

I use a node package but there is more. For install it run:

```sh
npm i -g sass
```

and to run the command will be:

```sh
sass input.scss output.css
```

## Variables

To declare a variable is simple as put a $ before the name. There are other types of variables like maps or list

```scss
$variable: "value"

$list: 1em, 2em, 3em

$maps: (
    "key": "val"
)
```

We are gonna use this to loops thourgh values so we can generate classes for every color. Example:

```scss
$colors: (
  'primary': blue,
  'secondary': gray,
  'success': green,
  'danger': red,
  'warning': orange,
  'info': teal,
);
```

## Looping

To loop we have differents options like `@each` function or `@for` function.
In this tutorial / guide we are going to use `@each`. Example:

```scss
// Looping in list

@each $var in $list {
  .something-#{$var} {
    color: #{$var};
  }
}

// $colors from the previous example. Looping in maps

@each $prop, $var in $colors {
  // We use #{} to insert varibles

  .bg-#{$prop} {
    background-color: #{$var};
  }
}
```

## Importing

To import some file we can use two ways: `@use` or `@forward`, there is also a `@import` but it is decrapted.

We use `@use` when we are going to use that file variables or mixins (Explained later). And we use `@forward` when we are only forwarding that file variables or mixins. Example:

```scss
// main.scss

// We use "as *" so we can access by its names you can also add you prefix
@use '_variables' as *;
@use 'mixins' as m;

body {
  color: $text-color;
  @include m.mixin1();
}
```

```scss
// _variables.scss
$text-color: white;

// Other variales
```

```scss
// mixins.scss
@mixin reset-list {
  margin: 0;
  padding: 0;
  list-style: none;
}
```

## Mixins

A mixin is a part of code that can be re-used. Example:

```scss
// To declare it just use @mixin

@mixin name {
  // Declarations
}

// To use it use @include

body {
  @include name;
}

// They can also take arguments

@mixin name($argument1, $argument2) {
  margin: $argument1;
}

body {
  @include name(24em, 0);
}

// Compiled
body {
  margin: 24em;
}

// Optional arguments
@mixin name($argument1: 50%) {
  margin: $argument1;
}

body {
  @include name(40%);
}

p {
  @include name;
}

// Compiled

body {
  margin: 40%;
}

p {
  margin: 50%;
}
```
