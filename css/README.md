# CSS Styling

My css styling conventions. Linter rules file available for stylelint (.stylelintrc).



## TOC
 |
 V


## Conventions

My style.

### General rules

* Indentation: 2 spaces
* Strings are double quoted.


### Class names
* Always lower-case-and-with-dashes {}.
* Mixin classes Capitalized() {}.


### Declarations
* Start with empty newline before declaration for overall readability.
  ```css
    .declaration-1 {}   /* First */
                        /* Empty newline */
    .declaration-2 {}   /* Second */
  ```
* Always make multi-line declarations for overall consistency / readability.
  ```css
    .multi-line-declaration {
      color: black;
      background-color: white;
    }

    .even-with-one-declaration {
      content: "Just one declaration!";
    }
  ```


### Selectors
* Prevent use of universal selector
* Only use !important for specific cases;
  ```css
    .red-text-color {
      color: red !important;
    }
  ```


### Whitespace
