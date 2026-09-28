# lock-wood for the web

The lock-wood palette as design tokens for web applications.

## Files

| File                    | Format                                            |
| ----------------------- | ------------------------------------------------- |
| `lock-wood.css`         | CSS custom properties                             |
| `lock-wood.scss`        | SCSS variables + palette map                      |
| `lock-wood.tailwind.css`| Tailwind CSS v4 `@theme` tokens                   |
| `lock-wood.tailwind.js` | Tailwind CSS v3 colour object for `tailwind.config.js` |

## CSS

```css
@import "lock-wood.css";

body {
  background: var(--lw-bg-primary);
  color: var(--lw-white-dark);
}

/* with alpha, via the RGB-channel variables */
.overlay {
  background: rgb(var(--lw-bg-secondary-rgb) / 0.8);
}
```

## Semantic aliases

Every file also ships semantic tokens following the
[suggested mapping](../README.md#suggested-semantic-mapping) in the main
README. Every palette colour is covered:

| Semantic token      | Palette colour   | Role                                          |
| ------------------- | ---------------- | --------------------------------------------- |
| `background`        | `bg-primary`     | Background                                    |
| `surface`           | `bg-secondary`   | Elevated surfaces                             |
| `border`            | `text-border`    | Borders and separators                        |
| `comment`           | `black-dark`     | Comments                                      |
| `muted`             | `black-bright`   | Subdued text                                  |
| `error`             | `red-dark`       | Errors and destructive states                 |
| `error-bright`      | `red-bright`     | Errors and destructive states (bright)        |
| `success`           | `green-dark`     | Success, strings, additions                   |
| `success-bright`    | `green-bright`   | Success, strings, additions (bright)          |
| `warning`           | `yellow-dark`    | Warnings and constants                        |
| `warning-bright`    | `yellow-bright`  | Warnings and constants (bright)               |
| `selection`         | `blue-dark`      | Selection and highlight backgrounds           |
| `info`              | `blue-bright`    | Information                                   |
| `link`              | `blue-bright`    | Links and functions                           |
| `keyword`           | `magenta-dark`   | Keywords and special syntax                   |
| `keyword-bright`    | `magenta-bright` | Keywords and special syntax (bright)          |
| `type`              | `cyan-dark`      | Types, tags, operators                        |
| `type-bright`       | `cyan-bright`    | Types, tags, operators (bright)               |
| `accent`            | `cyan-dark`      | Secondary information, accents                |
| `foreground`        | `white-dark`     | Primary foreground                            |
| `foreground-bright` | `white-bright`   | Primary foreground (bright)                   |

In CSS the tokens are prefixed `--lw-` (e.g. `var(--lw-error)`), in SCSS they
are plain variables (`lw.$error`) plus a `$semantic` map, and in Tailwind they
become utilities (`text-lw-error`, `bg-lw-surface`).

## SCSS

```scss
@use "lock-wood" as lw;

body {
  background: lw.$bg-primary;
  color: lw.$white-dark;
}
```

## Tailwind CSS v4

```css
@import "tailwindcss";
@import "lock-wood.tailwind.css";
```

```html
<div class="bg-lw-bg-primary text-lw-white-dark border border-lw-text-border">
```

## Tailwind CSS v3

```js
// tailwind.config.js
const lockWood = require("./lock-wood.tailwind");

module.exports = {
  theme: {
    extend: {
      colors: { lw: lockWood },
    },
  },
};
```
