# Grid with Grid

A robust, responsive grid system library built using native **CSS Grid Layout**.

Unlike many traditional grid libraries (like Bootstrap v4) that rely on Flexbox, **Grid with Grid** harnesses the two-dimensional power of CSS Grid. This allows for more complex layouts, including row spanning and precise placement, while maintaining a familiar class-based API.

## Features

- **Native CSS Grid:** Built on `display: grid` for true 2D layout control.
- **12-Column System:** Familiar 12-column structure.
- **Row Spanning:** Easily make items span multiple rows (a feature unique to CSS Grid).
- **Responsive:** Mobile-first breakpoints (`sm`, `md`, `lg`, `xl`, `xxl`).
- **Spacing Utilities:** Extensive margin and padding classes.
- **Alignment Utilities:** Full control over `align-items`, `justify-content`, etc.
- **SASS/SCSS:** Modular SCSS architecture.

## Getting Started

### Installation

1.  Clone the repository.
2.  Install dependencies:
    ```bash
    npm install
    ```
3.  Build the project:
    ```bash
    npm run build
    ```

### Usage

Include the compiled CSS file in your project:

```html
<link rel="stylesheet" href="dist/css/grid-with-grid.css" />
```

## Documentation

### Breakpoints

The library uses the following mobile-first breakpoints:

- `sm`: 36rem
- `md`: 48rem
- `lg`: 64rem
- `xl`: 80rem
- `xxl`: 90rem

### Grid System

#### Container

The `.container` class centers content and sets a `max-width` responsive to the current breakpoint.

```html
<div class="container">
  <!-- Content here -->
</div>
```

#### Rows

The `.row` class creates a grid container with 12 equal columns. Direct children span the full width (12 columns) by default.

```html
<div class="row">
  <!-- Grid items -->
</div>
```

Use `.row-autoflow` to switch to an auto-flow column layout instead of the fixed 12-column template.

#### Columns (`.col-`)

Use `.col-{n}` to define how many columns an item should span (1-12).

```html
<div class="row">
  <div class="col-6">Spans 6 columns (50%)</div>
  <div class="col-6">Spans 6 columns (50%)</div>
</div>
```

Responsive classes allow you to change column spans at different breakpoints:
Format: `.col-{breakpoint}-{n}`

```html
<div class="row">
  <div class="col-12 col-md-6 col-lg-4">
    <!-- 100% on mobile, 50% on md, 33.3% on lg -->
  </div>
</div>
```

#### Row Spanning (`.row-`)

A unique feature of CSS Grid is vertical spanning. Use `.row-{n}` to make an item span multiple rows.

```html
<div class="row">
  <div class="col-4 row-2">Spans 4 cols and 2 rows</div>
  <div class="col-8">Spans 8 cols</div>
  <div class="col-8">Spans 8 cols</div>
</div>
```

Responsive variants: `.row-{breakpoint}-{n}`.

#### Offsets

Control the start line of an item.

- `.col-offset-{n}`: Starts the item at column line `n + 1`.
- `.row-offset-{n}`: Starts the item at row line `n + 1`.

Responsive variants: `.col-offset-{breakpoint}-{n}`.

### Spacing

Control margin and padding with utility classes.
Scale: `0` to `10`.

**Format:** `{property}{side}-{size}` or `{property}{side}-{breakpoint}-{size}`

- **Property:** `m` (margin), `p` (padding).
- **Side:**
  - `t` (top), `b` (bottom), `l` (left), `r` (right)
  - `x` (horizontal), `y` (vertical)
  - _(blank)_ (all sides)

**Examples:**

- `p-4`: Padding 1rem on all sides.
- `my-2`: Margin top and bottom 0.5rem.
- `mt-lg-5`: Margin top 1.25rem on large screens and up.
- `mx-auto`: Centers an element horizontally.

### Gaps

Control the gutter between grid items.
Scale: `0` to `8`.

**Format:** `{property}-{size}` or `{property}-{breakpoint}-{size}`

- **Property:** `g` (gap), `gx` (column-gap), `gy` (row-gap).

```html
<div class="row g-3">
  <!-- Items with 0.75rem gap -->
</div>
```

### Alignment

Utilities for CSS Grid alignment properties.

**Format:** `.{property}-{value}` or `.{property}-{breakpoint}-{value}`

- **align-items:** `start`, `end`, `center`, `stretch`, `baseline`.
- **align-content:** `start`, `end`, `center`, `space-between`, `space-around`, `space-evenly`, `stretch`.
- **justify-items:** `start`, `end`, `center`, `stretch`.
- **justify-content:** `start`, `end`, `center`, `space-between`, `space-around`, `space-evenly`.

### Text Alignment

**Format:** `.text-{alignment}` or `.text-{breakpoint}-{alignment}`

Values: `start`, `end`, `left`, `right`, `center`, `justify`.

## Development

To watch for changes in SCSS files and recompile automatically:

```bash
npm run watch
```
