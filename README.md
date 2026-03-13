# filetype-mask-icons

A tiny set of file-type icons implemented as **CSS mask images**.

These icons inherit color from `currentColor`, which allows them to automatically adapt to **light mode, dark mode, and custom themes** without needing separate icon assets.

The icons are intentionally minimal and intended to represent common file types in interfaces such as file browsers, dashboards, and developer tools.


---

# Quick Example

```html
<div class="filetype-mask-icon"
     style="--icon:var(--filetype-mask-icon-file); width:24px; height:24px;">
</div>
```

```css
.filetype-mask-icon{
  display:inline-block;
  background:currentColor;
  mask:var(--icon) center / contain no-repeat;
  -webkit-mask:var(--icon) center / contain no-repeat;
  mask-mode:luminance;
}
```

The icon color is inherited from `currentColor`, which means it automatically adapts to your theme.

---

# Demo

A live demo of the icons is available here:

<https://opbarnes.github.io/filetype-mask-icons/demo/>

The demo shows:

- All available icons
- Multiple icon sizes
- Light and dark theme behavior

This allows you to see exactly how the icons render and how they inherit color from `currentColor`.

---

# Why this exists

Traditional icon approaches often require:

- Separate icons for **light and dark themes**
- Inline SVG manipulation
- Multiple color variants

These icons use **CSS masking**, which allows the icon color to come directly from CSS.

Because of this:

- Icons automatically match surrounding text color
- They work with **light and dark themes**
- They can be styled with **hover effects, transitions, or theme variables**
- No separate dark/light icon sets are required

Example theme:

```css
.light {
  color: black;
}

.dark {
  color: white;
}
```

The icon automatically adapts to the theme.

---

# Icon Set

Currently included icons:

- file
- folder
- image
- zip
- code
- video
- audio
- document

---

# Demo

A visual demo of all icons and sizes is available here:

```
demo/index.html
```

Open this file in a browser to preview the icons and test light/dark mode behavior.

---

# Installation

## Using npm

If you are using a JavaScript build tool (such as Vite, Webpack, Parcel, etc.), install the package with npm:

```bash
npm install filetype-mask-icons
```

Then import the stylesheet into your project.

### Import from JavaScript

Add the import to your main JavaScript entry file (for example `src/main.js`, `src/index.js`, or `src/main.ts`):

```javascript
import "filetype-mask-icons/css/icons.css"
```

### Import from CSS

If your project has a main stylesheet (for example `src/style.css`, `src/main.css`, or similar), you can import it there instead:

```css
@import "filetype-mask-icons/css/icons.css";
```

---

## Using Vite

Vite supports CSS imports directly.

Add the import to your main entry file (usually `src/main.js` or `src/main.ts`):

```javascript
import "filetype-mask-icons/css/icons.css"
```

Example `src/main.js`:

```javascript
import "filetype-mask-icons/css/icons.css"
import "./style.css"
```

No additional configuration is required.

---

## Using SCSS / Sass

If your project uses SCSS or Sass, import the stylesheet inside your SCSS file.

Example:

```scss
@import "filetype-mask-icons/css/icons.css";
```

Or using modern Sass syntax:

```scss
@use "filetype-mask-icons/css/icons.css";
```

---

## Without npm

You can copy the stylesheet directly into your project:

```
css/icons.css
```

Then include it in your HTML:

```html
<link rel="stylesheet" href="css/icons.css">
```

---

# Usage

Apply the `.filetype-mask-icon` class and set the `--icon` variable to one of the provided icon variables.

Example:

```html
<div class="filetype-mask-icon"
     style="--icon:var(--filetype-mask-icon-file); width:24px; height:24px;">
</div>
```

The icon color comes from `currentColor`.

Example:

```css
.file {
  color: #444;
}

.dark .file {
  color: #eee;
}
```

The icon will automatically inherit the color.

---

# Available icon variables

```css
--filetype-mask-icon-file
--filetype-mask-icon-folder
--filetype-mask-icon-image
--filetype-mask-icon-zip
--filetype-mask-icon-code
--filetype-mask-icon-video
--filetype-mask-icon-audio
--filetype-mask-icon-doc
```

---

# Example

```html
<div class="filetype-mask-icon"
     style="--icon:var(--filetype-mask-icon-folder); width:32px; height:32px;">
</div>
```

---

# Customizing size

The icon size is controlled using normal CSS `width` and `height`.

You can set the size inline:

```html
<div class="filetype-mask-icon"
     style="--icon:var(--filetype-mask-icon-file); width:24px; height:24px;">
</div>
```

Or define your own CSS classes:

```css
.icon-small{
  width:16px;
  height:16px;
}

.icon-large{
  width:48px;
  height:48px;
}
```

Then apply them to the element:

```html
<div class="filetype-mask-icon icon-large"
     style="--icon:var(--filetype-mask-icon-folder);">
</div>
```

---

# License

MIT License

See the `LICENSE` file for details.