# PostCSS Gutters

[![NPM Version][npm-img]][npm-url]
[![Linux Build Status][cli-img]][cli-url]
[![Windows Build Status][win-img]][win-url]
[![Gitter Chat][git-img]][git-url]


Apply gutters between child elements of any container element.

Example:

```css
.container {
    gutters: 40px;
}

```

Output:

```css
/* Some output not shown to simplify example */

.container > * {
    --FI_gutters_parent: 40px !important;
    --FI_gutters_item: 40px !important;
    --FI_gutters: var(--FI_gutters_item) !important;
    margin-top: var(--FI_gutters);
    margin-left: var(--FI_gutters);
}

.container {
    --FI_gutters_container: calc(var(--FI_gutters_parent, 0px) - 40px) !important;
    --FI_gutters: var(--FI_gutters_container);
    margin-top: var(--FI_gutters);
    margin-left: var(--FI_gutters);
}
```


It works by adding margins to each child element and recalculating their widths and applying a negative margin to the container.

- Works with unlimited nested elements
- No additional class names or divs needed
- Use with or without a wrapper div
- Works well with responsive design
- Gutters don't have to be even numbers
- Style borders and padding as normal
- Supports percentages (Note on flex containers they behave inconsistently amongst browsers)


## Setup

```bash
npm install postcss-gutters --save-dev
```

## Browsers

Supports all current modern browsers, Edge, Firefox, Chrome, Safari, Opera.


[npm-url]: https://www.npmjs.com/package/postcss-gutters
[npm-img]: https://img.shields.io/npm/v/postcss-gutters.svg
[cli-url]: https://travis-ci.org/mindthetic/postcss-gutters
[cli-img]: https://img.shields.io/travis/mindthetic/postcss-gutters.svg
[win-url]: https://ci.appveyor.com/project/mindthetic/postcss-gutters
[win-img]: https://img.shields.io/appveyor/ci/mindthetic/postcss-gutters.svg
[git-url]: https://gitter.im/postcss/postcss
[git-img]: https://img.shields.io/badge/chat-gitter-blue.svg

[PostCSS]: https://github.com/postcss/postcss
