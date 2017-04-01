# CSS Styling

My css styling conventions. Linter rules file available for stylelint (.stylelintrc).



## TOC
 |
 V


## Conventions
These convention rules are set in a way that styles
will be most readable for every developer in the team.
They also bear in mind other css' best practices to increase
css code quality.

### General rules

* Indentation: 2 spaces
* Strings are all double quoted.


### Class names
* Be descriptive and specific; what is it?
  * A list containing usernames; username-list, username-list-item
  * For a contact form; contact-form, message-field, message-field-label, ...

* Component names dashed.
  ```css
  /* Example with a list */
  .user-list {}
  .user-list-item {}
  ```

* Mixin classes CamelCase.
  * Less:
    ```less
      .BorderRadius(@radius) {/* ... */}
    ```

  * Sass:
    ```scss
      @mixin BorderRadius($radius) {
        border-radius: $radius;
      }
    ```



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
* Prevent use of universal selector, always be specific and
  do not style unused elements.
  ```css
    /* Yes */
    body {}
    .class-selector {}
    .attr-selector[attribute="value"] {}

    /* No */
    * {}
    div > * {}
  ```


* Only use !important for specific cases;
  ```css
    /* Yes: Specific */
    .red-text-color {
      color: red !important;
    }

    /* No: Not specific */
    ul > li {
      margin: 0 0 0 1em !important;
    }
  ```


* Do not use duplicate selectors:
  ```css
    /* Yes: general styling first, specific styling later */
    h1,
    h2,
    h3 {
      margin: 0;
    }

    h1 {
      margin-bottom: 1rem;
    }

    /*
    ** No: (accidentally?) overwriting or appending styles
    ** with same selector.
    */
    h1 {
      margin-bottom: 1rem;
    }
    /* ...some declarations later... */
    h1 {
      margin-bottom: 1em;
      text-decoration: underline;
    }

  ```
