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
@each $prop, $var in $colors {
  // We use #{} to insert varibles

  .bg-#{$prop} {
    background-color: #{$var};
  }
}
```
