# Stylelint

In VSCode, to fix all fixable errors, open the Command Palette and choose *"Stylelint: Fix all auto-fixable problems"*

- Install [VSCode Stylelint plugin](https://marketplace.visualstudio.com/items?itemName=stylelint.vscode-stylelint)
- Clone repo to your computer (eg `/Users/jeanine.schoessler/code/stylelint`)
- cd to `stylelint` and `npm install`
 

## Example VSCode config:

```json
{
  ...
  "stylelint.snippet": [
      "css",
      "scss"
    ],
    "stylelint.validate": [
      "css",
      "scss"
    ],
    "stylelint.configFile": "/Users/jeanine.schoessler/code/stylelint/.stylelintrc.json"
    ...
}
```

----

## Creative Hive standards (2022 April):

Use indentation of four (4) spaces and add new lines between selectors and css blocks; `0` should always be a unitless `0` (not `0px` nor `0rem`):

```scss
.custom-hero-welcome {
    .hero-right-content {
        margin: 0 auto;
        
        @include media(tablet-and-up) {
            padding: 24px $theme-space-large;
        }

        h2,
        p,
        .SearchForm {
            background-color: $ptc-gray-light;
        }
    }
}
```

Alphabetize attributes (`background-color` goes before `color`):

```scss
.custom-hero-welcome {
    @include flexbox();
    @include flex-flow(row wrap);
    @include align-items(center);
    background-color: $theme-color-grey-hero-background;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    color: $theme-black;
}
```

Hex colors: lowercase, can be full `#ffffff` or shorthand `#fff`:

```scss
$theme-dark-blue:     #236192;
$theme-cool-gray:     #c8c9c7;
$theme-gray:          #3d4647;
$theme-white:         #fff;
```

Comment after `!important` why necessary:

```scss
.lia-cancel-search {
    font-size: $font-size-xsmall !important; // override Hermes !important
}
```

Combinators (`>`, `+`, `~`) should have a space before and after:
```scss
.selector > .child { 
    color: $theme-color-primary; 
    &.anotherclass {
        & + p {
            color: $theme-color-secondary;
        }
        li ~ li {
            margin-top: 0;
        }
    }
}
.selector {
    & > * {
        color: $theme-color-secondary;
    }
}
```

Add space before opening curly brace (`{`):

```scss
.selector { 
    color: $theme-color-primary; 
    @include media(desktop-and-up) {
        @include flexbox();
        @include flex-direction(row-reverse);
    }
}
```


Aim to develop mobile-first, preferred variable uses:
- `$large-desktop`
- `$desktop-and-up`
- `$tablet-and-up`
- `$phone`
- `$phone-min`
- `$tablet-and-down`
- `$desktop-and-down`


## New files

### Freemarker

Freemarker files should be named either starting with `custom.name-of-component` (custom) or `theme-lib.name-of-component` (Hermes). Avoid creating filenames or code referencing the customer name.

Basic building block of `custom.name-of-component.ftl`:

```ftl
<#-- custom profile notifications -->
<div class="custom-profile-notifications">
    ...
</div>
```

### SCSS

For new scss partials for styling custom component, create the partial in `custom`; don't name it using "custom" or "customer name", for example: `custom/_wayfinding-tiles.scss` would be a good name.

For new partials, add a comment at the top of the .scss file, eg:

```scss
// custom/_wayfinding-tiles.scss
```

## To-do:

- Can we generate .map files for css, js? This would be done in the compiledskin folder as part of core LIA