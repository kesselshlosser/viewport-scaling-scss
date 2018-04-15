<!--
VIEWPORT-SCALING-SCSS
/README.md
By James Walker.
Copyright James Walker 2018. Public-domain software under the Unlicense.

This file contains the README message for viewport-scaling-scss.
-->

viewport-scaling-scss
---------------------
*By James Walker. Public-domain software under the Unlicense.*

This project contains a Sass mixin to enable responsive property value scaling based on viewport values.

The mixin allows you to define a floor and ceiling to limit the minimum and maximum values of any given property.

Between the floor and ceiling, the value is automatically scaled according to a given viewport unit.

# Usage

A single mixin `viewport-scaling` is defined:

- `$property` - the name of the property to scale (e.g. `font-size`)
- `$min-value` - the minimum value the property can have, before the floor is reached (e.g. `16px`)
- `$max-value` - the maximum value the property can have, after the ceiling is reached (e.g. `72px`)
- `$bp-floor` - the floor breakpoint at which viewport scaling enables (e.g. `480px`)
- `$bp-ceiling` - the ceiling breakpoint at which viewport scaling disables (e.g. `960px`)
- `$v-unit` - the viewport unit to scale the value by between the floor and ceiling (e.g. `vw`)
- `$mq-prop` - the media query property to determine the floor and ceiling by (e.g. `min-width`)

This works for any properties and units which are compatible with media queries and viewport units.

**Example:**

```scss
h1 {
	@include viewport-scaling(font-size, 16px, 72px, 480px, 960px, vw, min-width);
}
```

Scales the text size using `vw` units when the viewport width is between `480px` and `960px`; `<480px` the size is always `16px`, and `>=960px`, the size is always `72px`.

**Example (2):**

```scss
div {
	@include viewport-scaling(width, 150px, 300px, 480px, 960px, vw, min-width);
	@include viewport-scaling(height, 150px, 300px, 480px, 960px, vw, min-width);
}
```

Scales the width and height using `vw` units when the viewport width is between `480px` and `960px`; `<480px` the dimensions are always `150px`, and `>=960px`, the dimensions are always `72px`.

**CodePen** [View on CodePen](https://codepen.io/ilmiont/pen/ZxMbrE)

This project is released as public domain software under the Unlicense license.

Copyright ©James Walker 2018. Public-domain software under the Unlicense.

<!--
End of file.
-->