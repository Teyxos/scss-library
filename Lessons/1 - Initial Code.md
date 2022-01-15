# Initial Code

Feel free to copy this repo for the initial code or write it out reading this

# Files

The file structure can be as you want, but in the tutorial will be using the next structure.

```
.
├── main.scss               # Here we'll have all the imports to simplify the compile task
├── _variables.scss         # Here we'll have all the variables, list and maps
├── _utilities.scss         # Here we'll have all the mixins, loops and more utility stuff
├── helpers.scss            # The main import for utilites
├── components.scss         # Import for all of the components directory
├── components              # The folder for the components files
│   └── ...
└── ...                     # Etc
```

# Compiler

As I say in the README you need a compiler you can use whatever you want. We'll use the node sass compiler

```sh
npm install -g sass
```

# Code

We'll start by making some loops for background colors and text colors (See \_utilities.scss for more detailed example).
For this we'll base on bootstrap colors

```scss
$colors: (
  "primary": blue,
  "secondary": gray,
  "success": green,
  "warning": orange,
  "danger": red,
  "info": teal,
);

// Background
@each $prop, $var in $colors {
  .bg-#{$prop} {
    background-color: #{$var};
  }
}

// Text
@each $prop, $var in $colors {
  .text-#{$prop} {
    color: #{$var};
  }
}
```

You can follow along this to make as many classes as you want these are the basics for making the full library.

On the next lesson we'll make our first component

[To lesson 2](./2%20-%20Our%20first%20component.md)
