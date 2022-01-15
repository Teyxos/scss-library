# Initial Code

For this moment you should have some classes, so we'll use them for our first component a Button

More examples in `./components/*.scss`

# Making the component

```scss
@use "../_variables.scss" as *; // Path to the variables or in the same file

@each $prop, $var in $colors {
  .btn-#{$prop} {
    background-color: #{$var};
    padding: 2em;
    // The style you want for the button by its value.
    // You can also use @if to make conditionals

    @if $var == teal {
      color: white;
    } @else {
      color: black;
    }
  }
}

// You can add as many options as you want
```
