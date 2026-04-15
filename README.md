# Bootstrap-CSS Basics

> *Click &#9733; if you like the project. Your contributions are heartily ♡ welcome.*

<br/>

## Table of Contents

* [Bootstrap Overview](#-1-bootstrap-overview)
* [Bootstrap Layout](#-2-bootstrap-layout)
* [Bootstrap Grid System](#-3-bootstrap-grid-system)
* [Bootstrap Forms](#-4-bootstrap-forms)
* [Bootstrap Components](#-5-bootstrap-components)
* [Bootstrap Navigation](#-6-bootstrap-navigation)
* [Bootstrap Utilities](#-7-bootstrap-utilities)
* [Bootstrap 5 Features](#-8-bootstrap-5-features)

<br/>

## # 1. BOOTSTRAP OVERVIEW

<br/>

## Q. What is Bootstrap?

**Bootstrap** is a front-end framework used for creating **HTML, CSS, and JavaScript** web applications. Key characteristics:

- **Responsive layout** — adapts to different screen sizes out of the box
- **Easy and fast** to use
- **Mobile-first** focus — primarily designed for building mobile applications
- Includes pre-built **design templates** for common UI components like:
  - Dropdowns
  - Forms
  - Buttons
  - Alerts
  - Tabs

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Why to choose Bootstrap for building the websites?

Here are the reasons to choose Bootstrap for building websites:

**1. Mobile-First & Responsive Design**

Bootstrap provides full mobile support in a single CSS file. It automatically adjusts layouts based on screen size using a responsive grid system — no separate mobile stylesheet needed.

**2. Easy to Learn**

If you know basic HTML and CSS, you can start building with Bootstrap quickly using its pre-built class names and components.

**3. Cross-Browser Compatibility**

Bootstrap supports all major browsers — Chrome, Firefox, Safari, Opera, Edge, and IE — ensuring a consistent look across platforms.

**4. Rich Component Library**

Bootstrap ships with ready-to-use UI components: navbars, modals, carousels, alerts, buttons, forms, cards, and more — reducing development time significantly.

**5. Customizable**

You can customize Bootstrap by selecting only the components you need, overriding Sass variables, or using the Utility API (Bootstrap 5) to generate utility classes.

**6. Large Community & Ecosystem**

Bootstrap has extensive documentation, a large community, and a wide ecosystem of themes and plugins, making it easy to find help and resources.

**7. Consistent Design**

Using Bootstrap enforces design consistency across pages and team members since everyone works from the same base classes and design tokens.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What are the key components of Bootstrap?

The key components of Bootstrap are:

| Component | Description |
|---|---|
| **CSS** | Comes with extensive pre-built CSS files covering typography, tables, forms, buttons, images, and more |
| **Scaffolding** | Provides the base structure — the 12-column grid system, link styles, and default background |
| **Layout Components** | Ready-to-use UI components like navbars, panels, wells, jumbotron, breadcrumbs, pagination, badges, and alerts |
| **JavaScript Plugins** | A collection of jQuery/JavaScript plugins for interactive components — modals, dropdowns, carousels, tooltips, scrollspy, and collapse |
| **Customize** | Ability to select only the components you need and override variables to generate your own tailored version of the framework |

In Bootstrap 5, the JS plugins were rewritten in **vanilla JavaScript**, removing the jQuery dependency entirely.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## # 2. BOOTSTRAP LAYOUT

<br/>

## Q. What are the types of layout available in Bootstrap?


Bootstrap provides **two main types of layouts**:

**1. Fluid Layout — `.container-fluid`**

Spans the **full width** of the viewport at all screen sizes. Best used when you want the content to take up 100% of the browser width.

```html
<div class="container-fluid">
  <div class="row">
    <div class="col-md-6">Left</div>
    <div class="col-md-6">Right</div>
  </div>
</div>
```

**2. Fixed Layout — `.container`**

Has a **fixed max-width** that changes at each breakpoint, and centers content on the page. The width was traditionally ~940px on standard screens.

```html
<div class="container">
  <div class="row">
    <div class="col-md-8">Main</div>
    <div class="col-md-4">Sidebar</div>
  </div>
</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is the difference between `.container`, `.container-fluid`, and `.container-{breakpoint}` in Bootstrap 5?

| Class | Behavior |
|---|---|
| `.container` | Fixed-width, centered; max-width changes at each breakpoint |
| `.container-fluid` | Always 100% wide across all viewport sizes |
| `.container-sm` | 100% wide below `sm` (576px), fixed-width at `sm` and above |
| `.container-md` | 100% wide below `md` (768px), fixed-width at `md` and above |
| `.container-lg` | 100% wide below `lg` (992px), fixed-width at `lg` and above |
| `.container-xl` | 100% wide below `xl` (1200px), fixed-width at `xl` and above |
| `.container-xxl` | 100% wide below `xxl` (1400px), fixed-width at `xxl` and above |

```html
<div class="container">Fixed-width centered container</div>
<div class="container-fluid">Full-width container</div>
<div class="container-md">Full-width on mobile, fixed-width on md+</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What are Bootstrap 5 breakpoints and what are their default values?

Bootstrap 5 has **six** responsive breakpoints based on minimum viewport widths:

| Breakpoint | Class infix | Dimensions |
|---|---|---|
| Extra small | *(none)* | < 576px |
| Small | `sm` | ≥ 576px |
| Medium | `md` | ≥ 768px |
| Large | `lg` | ≥ 992px |
| Extra large | `xl` | ≥ 1200px |
| Extra extra large | `xxl` | ≥ 1400px |

Breakpoints are built with Sass maps and can be customised:

```scss
$grid-breakpoints: (
  xs: 0,
  sm: 576px,
  md: 768px,
  lg: 992px,
  xl: 1200px,
  xxl: 1400px
);
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is a Bootstrap row and what rules apply to it?

A `.row` is a wrapper for columns inside a `.container` or `.container-fluid`. Key rules:

- Rows use negative margins to counteract the column padding (gutters).
- Columns must be **direct children** of a row.
- A row always creates a 12-column horizontal grid that columns are placed within.
- Use `.row-cols-*` to set a fixed number of equal-width columns per row.

```html
<div class="container">
  <div class="row">
    <div class="col-md-6">Left half</div>
    <div class="col-md-6">Right half</div>
  </div>
  <!-- Fixed 3 columns per row on any screen size -->
  <div class="row row-cols-3">
    <div class="col">Col 1</div>
    <div class="col">Col 2</div>
    <div class="col">Col 3</div>
  </div>
</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What are gutters in Bootstrap 5 and how do you control them?

Gutters are the padding between columns that create spacing in the grid layout. Bootstrap 5 introduced dedicated gutter utility classes:

| Class | Effect |
|---|---|
| `.g-{size}` | Sets both horizontal and vertical gutters |
| `.gx-{size}` | Sets horizontal (column) gutters only |
| `.gy-{size}` | Sets vertical (row) gutters only |
| `.g-0` | Removes all gutters |

Sizes range from `0` to `5` (maps to spacing scale: 0 → 4rem).

```html
<!-- No gutters -->
<div class="row g-0">
  <div class="col">No gutter column</div>
</div>

<!-- Horizontal gutters only -->
<div class="row gx-4">
  <div class="col">Column A</div>
  <div class="col">Column B</div>
</div>

<!-- Different horizontal and vertical gutters -->
<div class="row gx-3 gy-2">
  <div class="col-6">Card 1</div>
  <div class="col-6">Card 2</div>
  <div class="col-6">Card 3</div>
  <div class="col-6">Card 4</div>
</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. How do you create a responsive two-column layout that stacks on mobile in Bootstrap?

Use responsive column classes. Apply `col-12` for full-width on the smallest screens and `col-md-6` (or another breakpoint) for the two-column split on larger screens.

```html
<div class="container">
  <div class="row">
    <!-- Full-width on xs/sm, half-width on md and above -->
    <div class="col-12 col-md-6">
      <p>Left column content</p>
    </div>
    <div class="col-12 col-md-6">
      <p>Right column content</p>
    </div>
  </div>
</div>
```

On screens narrower than 768 px the two `div`s stack vertically; at 768 px and wider they sit side by side.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is the Bootstrap `z-index` layering system used in layouts?

Bootstrap defines a set of `z-index` values to ensure components overlay each other consistently:

| Component | z-index |
|---|---|
| Dropdown | 1000 |
| Sticky elements (`.sticky-top`) | 1020 |
| Fixed elements (`.fixed-top`, `.fixed-bottom`) | 1030 |
| Offcanvas backdrop | 1040 |
| Offcanvas | 1045 |
| Modal backdrop | 1050 |
| Modal | 1055 |
| Popover | 1070 |
| Tooltip | 1080 |
| Toast | 1090 |

These values are defined as Sass variables (`$zindex-dropdown`, `$zindex-modal`, etc.) and can be customised.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. How does Bootstrap\'s `.sticky-top` differ from `.fixed-top`?

| Feature | `.sticky-top` | `.fixed-top` |
|---|---|---|
| CSS property | `position: sticky` | `position: fixed` |
| Flow | Remains in normal document flow | Removed from document flow |
| Scroll behavior | Sticks when it reaches the top of the viewport, scrolls with page otherwise | Always fixed at the top regardless of scroll position |
| Space reservation | Space is reserved in layout | No space reserved — content shifts under it |
| Browser support | Modern browsers (IE not supported) | All browsers |

```html
<!-- Sticks to top only when scrolled to its position -->
<div class="sticky-top bg-light p-2">Sticky header</div>

<!-- Always sits at top of viewport, overlapping content -->
<nav class="navbar fixed-top navbar-light bg-light">Fixed Nav</nav>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## # 3. BOOTSTRAP GRID SYSTEM

<br/>

## Q. What is Bootstrap Grid System?

The Bootstrap Grid System is a **12-column, mobile-first, responsive layout system** built on flexbox (Bootstrap 4/5) or floats (Bootstrap 3).

**How it works:**

- The page is divided into **12 equal columns** per row.
- You place content in columns inside rows, inside a container.
- Column widths are specified using classes like `.col-md-6` (takes 6 of 12 columns = 50% width).
- Columns automatically become full-width (stack) below their target breakpoint.

**Basic structure:**

```html
<div class="container">
  <div class="row">
    <div class="col-md-4">Column 1 (1/3 width)</div>
    <div class="col-md-4">Column 2 (1/3 width)</div>
    <div class="col-md-4">Column 3 (1/3 width)</div>
  </div>
</div>
```

**Grid class tiers (Bootstrap 5):**

| Class prefix | Applies from |
|---|---|
| `.col-` | All screen sizes (< 576px) |
| `.col-sm-` | ≥ 576px |
| `.col-md-` | ≥ 768px |
| `.col-lg-` | ≥ 992px |
| `.col-xl-` | ≥ 1200px |
| `.col-xxl-` | ≥ 1400px |

**Key rules:**

- Columns must be direct children of a `.row`
- The 12 column numbers in a row should add up to 12 (or less; remaining space is left empty)
- If columns exceed 12, they wrap to the next line
- Use `.col` (no number) for equal-width auto columns

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What are offset columns in Bootstrap?

**Offset columns** shift a column to the right by a specified number of columns, creating empty space before it — useful for centering columns or creating asymmetric layouts.

**Bootstrap 4/5 — use `.offset-{breakpoint}-{n}`:**

```html
<!-- Shifts 3 columns to the right, leaving 3 empty columns on the left -->
<div class="container">
  <div class="row">
    <div class="col-md-6 offset-md-3">Centered column</div>
  </div>

  <div class="row">
    <div class="col-md-4">Left column</div>
    <div class="col-md-4 offset-md-4">Right column (pushed right)</div>
  </div>
</div>
```

- The offset number consumes columns — `.offset-md-3` eats 3 of the 12 available columns.
- Total of column widths + offsets in a row should not exceed 12 to avoid wrapping.
- Responsive: you can apply different offsets at different breakpoints (e.g., `offset-sm-2 offset-md-4`).

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is column ordering in Bootstrap?

**Column ordering** lets you change the visual order of columns independently from their order in the HTML source.

**Bootstrap 4/5 — use `.order-{n}` or `.order-{breakpoint}-{n}`:**

```html
<div class="container">
  <div class="row">
    <div class="col order-3">First in HTML, shown third</div>
    <div class="col order-1">Second in HTML, shown first</div>
    <div class="col order-2">Third in HTML, shown second</div>
  </div>
</div>
```

**Responsive ordering:**

```html
<div class="row">
  <!-- On mobile: shown second. On md+: shown first -->
  <div class="col-12 col-md-8 order-2 order-md-1">Main content</div>
  <div class="col-12 col-md-4 order-1 order-md-2">Sidebar</div>
</div>
```

**Special order classes:**

| Class | Effect |
|---|---|
| `.order-first` | `order: -1` — forces to the very beginning |
| `.order-last` | `order: 6` — forces to the very end |
| `.order-0` to `.order-5` | Explicit order values |

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What function you can use to wrap a page content?

In Bootstrap, you use the **`.container`** class to wrap page content. It creates a centered, fixed-width responsive wrapper.

**Three container variants:**

```html
<!-- Fixed-width, centers at each breakpoint -->
<div class="container">
  Page content here
</div>

<!-- Always 100% wide -->
<div class="container-fluid">
  Full-width content here
</div>

<!-- 100% wide until md breakpoint, then fixed-width -->
<div class="container-md">
  Responsive container
</div>
```

**What `.container` does:**

- Centers content horizontally with `margin: auto`
- Adds horizontal padding (`15px` each side in BS4, `12px` in BS5)
- Sets a `max-width` that steps up at each breakpoint:

| Breakpoint | `.container` max-width |
|---|---|
| xs (< 576px) | 100% |
| sm (≥ 576px) | 540px |
| md (≥ 768px) | 720px |
| lg (≥ 992px) | 960px |
| xl (≥ 1200px) | 1140px |
| xxl (≥ 1400px) | 1320px |

**Typical full-page structure:**

```html
<body>
  <nav class="navbar">...</nav>

  <div class="container">
    <div class="row">
      <div class="col-md-8">Main content</div>
      <div class="col-md-4">Sidebar</div>
    </div>
  </div>

  <footer class="container-fluid">...</footer>
</body>
```

Use `.container` for standard pages, `.container-fluid` for full-bleed layouts like dashboards sections.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What pagination in bootstrap is and how they are classified?

**Pagination** in Bootstrap is a component used to divide content across multiple pages and provide navigation links between them. It is built using an unordered list (`<ul>`) styled with Bootstrap classes.

**Basic pagination:**

```html
<nav aria-label="Page navigation">
  <ul class="pagination">
    <li class="page-item"><a class="page-link" href="#">Previous</a></li>
    <li class="page-item"><a class="page-link" href="#">1</a></li>
    <li class="page-item"><a class="page-link" href="#">2</a></li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
    <li class="page-item"><a class="page-link" href="#">Next</a></li>
  </ul>
</nav>
```

**Classification of pagination classes:**

| Class | Purpose |
|---|---|
| `.pagination` | Applied to `<ul>` — creates the base pagination component |
| `.page-item` | Applied to each `<li>` — wraps each page link |
| `.page-link` | Applied to each `<a>` — styles the clickable link |
| `.active` | Highlights the current page |
| `.disabled` | Makes a link unclickable (e.g., Previous on first page) |

**Sizing variants:**

```html
<!-- Large -->
<ul class="pagination pagination-lg"> ... </ul>

<!-- Default -->
<ul class="pagination"> ... </ul>

<!-- Small -->
<ul class="pagination pagination-sm"> ... </ul>
```

**Active and disabled states:**

```html
<ul class="pagination">
  <li class="page-item disabled">
    <a class="page-link" href="#" tabindex="-1" aria-disabled="true">Previous</a>
  </li>
  <li class="page-item"><a class="page-link" href="#">1</a></li>
  <li class="page-item active" aria-current="page">
    <a class="page-link" href="#">2</a>
  </li>
  <li class="page-item"><a class="page-link" href="#">3</a></li>
  <li class="page-item">
    <a class="page-link" href="#">Next</a>
  </li>
</ul>
```

**Alignment:**

```html
<!-- Left (default) -->
<ul class="pagination justify-content-start"> ... </ul>

<!-- Center -->
<ul class="pagination justify-content-center"> ... </ul>

<!-- Right -->
<ul class="pagination justify-content-end"> ... </ul>
```
 
<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is the difference between Bootstrap and Foundation?

|Bootstrap               |Foundation              |
|------------------------|------------------------|
|Bootstrap offers unlimited number of UI elements|In Foundation UI element options are very limited in numbers|
|Bootstraps uses pixels  | Foundation use REMs|
|Bootstrap encourages to design for both desktop and mobile.| Foundation encourages to design mobile first|
|Bootstrap support LESS as its preprocessor | Foundation support Sass and Compass as its preprocessor|

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. In Bootstrap what are the two ways you can display the code?

In bootstrap you can display code in two ways

`tag` : If you are going to display code inline, you should use `code` tag
`pre` tag: If you want to display the code as a standalone block element or it has multiple lines then you should use `pre` tag

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## # 4. BOOTSTRAP FORMS

<br/>

## Q. What are the steps for creating basic or vertical forms?

**Bootstrap 4/5 — Basic (vertical) form:**

A vertical form stacks labels directly above their inputs, which is the default form layout in Bootstrap.

**Steps:**

1. Create a `<form>` element
2. Wrap each label+input pair in a `<div class="mb-3">` (Bootstrap 5) or `<div class="form-group">` (Bootstrap 4)
3. Add `.form-label` to each `<label>`
4. Add `.form-control` to all `<input>`, `<textarea>`, and `<select>` elements

**Bootstrap 5 example:**

```html
<form>
  <!-- Text input -->
  <div class="mb-3">
    <label for="userName" class="form-label">Full Name</label>
    <input type="text" class="form-control" id="userName" placeholder="Enter your name">
  </div>

  <!-- Email input -->
  <div class="mb-3">
    <label for="userEmail" class="form-label">Email address</label>
    <input type="email" class="form-control" id="userEmail" placeholder="name@example.com">
    <div class="form-text">We'll never share your email.</div>
  </div>

  <!-- Password input -->
  <div class="mb-3">
    <label for="userPassword" class="form-label">Password</label>
    <input type="password" class="form-control" id="userPassword">
  </div>

  <!-- Textarea -->
  <div class="mb-3">
    <label for="message" class="form-label">Message</label>
    <textarea class="form-control" id="message" rows="3"></textarea>
  </div>

  <!-- Select -->
  <div class="mb-3">
    <label for="country" class="form-label">Country</label>
    <select class="form-select" id="country">
      <option selected>Choose...</option>
      <option value="1">India</option>
      <option value="2">USA</option>
    </select>
  </div>

  <!-- Checkbox -->
  <div class="mb-3 form-check">
    <input type="checkbox" class="form-check-input" id="agreeTerms">
    <label class="form-check-label" for="agreeTerms">I agree to the terms</label>
  </div>

  <button type="submit" class="btn btn-primary">Submit</button>
</form>
```

**Key classes:**

| Class | Applies to | Purpose |
|---|---|---|
| `.form-control` | `<input>`, `<textarea>` | Full-width styled input |
| `.form-select` | `<select>` | Styled dropdown |
| `.form-label` | `<label>` | Proper label spacing |
| `.form-text` | Helper `<div>`/`<span>` | Small hint text below input |
| `.form-check` | Wrapper `<div>` | Checkbox/radio container |
| `.form-check-input` | `<input type="checkbox/radio">` | Styled checkbox or radio |
| `.mb-3` | Wrapper `<div>` | Bottom margin between fields |

**Bootstrap 4 difference** — use `.form-group` instead of `.mb-3`:

```html
<div class="form-group">
  <label for="email">Email</label>
  <input type="email" class="form-control" id="email">
</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## # 5. BOOTSTRAP COMPONENTS

<br/>

## Q. What is Modal plugin used for in Bootstrap?

The Modal plugin in Bootstrap is used to create dialog boxes/popup windows that appear on top of the current page — without navigating away — for alerts, confirmations, forms, images, or any custom content.

**Basic modal structure:**

```html
<!-- Trigger button -->
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#myModal">
  Open Modal
</button>

<!-- Modal -->
<div class="modal fade" id="myModal" tabindex="-1" aria-labelledby="myModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">

      <!-- Header -->
      <div class="modal-header">
        <h5 class="modal-title" id="myModalLabel">Modal Title</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>

      <!-- Body -->
      <div class="modal-body">
        Modal content goes here...
      </div>

      <!-- Footer -->
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Save changes</button>
      </div>

    </div>
  </div>
</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is Bootstrap Container?

A Bootstrap **container** is the fundamental layout wrapper that constrains and centers page content horizontally. It is required as the outermost wrapper for the grid system.

**Three types:**

```html
<!-- Fixed-width: centers content, max-width steps up at each breakpoint -->
<div class="container">...</div>

<!-- Fluid: always 100% of the viewport width -->
<div class="container-fluid">...</div>

<!-- Responsive: 100% wide below the breakpoint, fixed-width above it -->
<div class="container-md">...</div>
```

**Max-width per breakpoint (`.container`):**

| Breakpoint | Viewport width | Container max-width |
|---|---|---|
| xs | < 576px | 100% |
| sm | ≥ 576px | 540px |
| md | ≥ 768px | 720px |
| lg | ≥ 992px | 960px |
| xl | ≥ 1200px | 1140px |
| xxl | ≥ 1400px | 1320px |

**What a container provides:**

- Horizontal centering via `margin-left: auto; margin-right: auto`
- Horizontal padding on left and right (`padding-x`)
- A controlled max-width to prevent content from stretching too wide on large screens

**Typical page layout:**

```html
<body>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark">...</nav>

  <div class="container my-4">
    <div class="row">
      <div class="col-md-8">Main content</div>
      <div class="col-md-4">Sidebar</div>
    </div>
  </div>

  <footer class="container-fluid bg-dark text-white p-4">...</footer>
</body>
```

**When to use which:**

| Use case | Container type |
|---|---|
| Standard blog/article page | `.container` |
| Dashboard or admin panel | `.container-fluid` |
| Full-width hero, narrow body | Mix both |
| Fluid on mobile, fixed on desktop | `.container-md` / `.container-lg` |

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is Bootstrap collapsing elements?

**Bootstrap collapsing elements** allow you to show or hide content with a smooth animation — without writing any custom JavaScript.

**How it works:**

- Add `data-bs-toggle="collapse"` to the trigger element (button or link)
- Add `data-bs-target="#id"` pointing to the collapsible element
- Add `.collapse` to the element you want to show/hide
- Add `.show` to make it visible by default

**Example:**

```html
<!-- Trigger -->
<button class="btn btn-primary" type="button"
  data-bs-toggle="collapse" data-bs-target="#collapseExample"
  aria-expanded="false" aria-controls="collapseExample">
  Toggle Content
</button>

<!-- Collapsible content -->
<div class="collapse" id="collapseExample">
  <div class="card card-body">
    This content is hidden by default and shown on toggle.
  </div>
</div>
```

**Using a link as trigger:**

```html
<a class="btn btn-primary" data-bs-toggle="collapse" href="#collapseExample" role="button">
  Toggle
</a>
```

**Accordion pattern (only one open at a time):**

```html
<div class="accordion" id="accordionExample">

  <div class="accordion-item">
    <h2 class="accordion-header" id="headingOne">
      <button class="accordion-button" type="button"
        data-bs-toggle="collapse" data-bs-target="#collapseOne"
        aria-expanded="true" aria-controls="collapseOne">
        Section 1
      </button>
    </h2>
    <div id="collapseOne" class="accordion-collapse collapse show"
      data-bs-parent="#accordionExample">
      <div class="accordion-body">Content for section 1.</div>
    </div>
  </div>

  <div class="accordion-item">
    <h2 class="accordion-header" id="headingTwo">
      <button class="accordion-button collapsed" type="button"
        data-bs-toggle="collapse" data-bs-target="#collapseTwo"
        aria-expanded="false" aria-controls="collapseTwo">
        Section 2
      </button>
    </h2>
    <div id="collapseTwo" class="accordion-collapse collapse"
      data-bs-parent="#accordionExample">
      <div class="accordion-body">Content for section 2.</div>
    </div>
  </div>

</div>
```

**JavaScript API:**

```js
const collapseEl = document.getElementById('collapseExample');
const bsCollapse = new bootstrap.Collapse(collapseEl);

bsCollapse.show();    // Show the element
bsCollapse.hide();    // Hide the element
bsCollapse.toggle();  // Toggle visibility
```

**Key classes and attributes:**

| Class / Attribute | Purpose |
|---|---|
| `.collapse` | Hides the element by default |
| `.collapse.show` | Makes the element visible on load |
| `.collapsing` | Applied during the transition animation |
| `data-bs-toggle="collapse"` | Marks the trigger element |
| `data-bs-target="#id"` | Points to the collapsible element |
| `data-bs-parent="#id"` | Closes siblings when one opens (accordion) |

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is list group in Bootstrap and what is the use of it?

**List groups** are flexible components for displaying a series of content — from simple lists to complex custom content with images, badges, and actions.

**Basic list group:**

```html
<ul class="list-group">
  <li class="list-group-item">Item one</li>
  <li class="list-group-item">Item two</li>
  <li class="list-group-item">Item three</li>
</ul>
```

**Common use cases:**

- Navigation menus / sidebars
- Notification or message feeds
- Settings panels
- File/folder trees
- Search result lists

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. How you can add badge to list group in Bootstrap?

To add a badge to a list group item, combine flexbox utilities with the `.badge` component inside the `.list-group-item`.

**Basic badge on a list group item:**

```html
<ul class="list-group">
  <li class="list-group-item d-flex justify-content-between align-items-center">
    Inbox
    <span class="badge bg-primary rounded-pill">14</span>
  </li>
  <li class="list-group-item d-flex justify-content-between align-items-center">
    Notifications
    <span class="badge bg-danger rounded-pill">3</span>
  </li>
  <li class="list-group-item d-flex justify-content-between align-items-center">
    Messages
    <span class="badge bg-success rounded-pill">7</span>
  </li>
</ul>
```

**How it works:**

| Class on `<li>` | Purpose |
|---|---|
| `d-flex` | Makes the item a flex container |
| `justify-content-between` | Pushes text left, badge right |
| `align-items-center` | Vertically centers both text and badge |

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## # 6. BOOTSTRAP NAVIGATION

<br/>

## Q. How you can create Nav elements in Bootstrap?

Bootstrap offers various options for styling navigation elements all of them use the same markup and base class `.nav`.

To create Tabular Navigation or Tabs

Start with a basic unordered list with the base class of .nav
Then add class `.nav-tabs`

**Example:**

```html
<ul class="nav">
  <li class="nav-item">
    <a class="nav-link active" href="#">Home</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">About</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Services</a>
  </li>
  <li class="nav-item">
    <a class="nav-link disabled">Disabled</a>
  </li>
</ul>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is the use of Bootstrap Carousel plugin?

The **Bootstrap Carousel plugin** is used to add an image/content **slider** to your site. It\'s ideal when you want to display a large amount of content within a small space on a web page.

It provides the following standard methods:

| Method | Description |
|---|---|
| `.carousel(options)` | Initializes the carousel with optional configuration |
| `.carousel('cycle')` | Cycles through carousel items left to right |
| `.carousel('pause')` | Pauses the carousel cycling |
| `.carousel('number')` | Cycles to a specific item (0-indexed) |
| `.carousel('prev')` | Cycles to the previous item |
| `.carousel('next')` | Cycles to the next item |

It is a flexible, responsive component that supports sliding through **images, videos, and other content** with navigation controls.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Why Bootstrap is used for Mobile Web Development?

Bootstrap is used for Mobile Web Development because:

- It has **responsive designs and templates** that automatically adapt to different screen sizes (mobile, tablet, desktop)
- Templates are **easy to use**, reducing development time
- It follows a **mobile-first** approach — styles are designed for small screens first, then scaled up
- Its built-in **grid system** makes laying out content for mobile screens straightforward
- It ensures **cross-browser compatibility**, so mobile sites work consistently across different browsers

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Explain the features of Bootstrap?

Bootstrap\'s features include:

- **Open Source** — freely available for use with no licensing cost
- **Cross-browser Compatibility** — works consistently across all major browsers
- **Responsive Designs** — layouts automatically adapt to different screen sizes (mobile, tablet, desktop)
- **Easy to use and fast** — pre-built components and templates speed up development

Additional key components that support these features:

| Component | Description |
|---|---|
| **Scaffolding** | Grid system, background, and base styles |
| **CSS** — pre-defined CSS stylesheets for styling |
| **JS Plugins** | Built-in JavaScript and jQuery plugins |
| **Customizable** | Framework can be tailored to project needs |

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Define the key components of Bootstrap?

Bootstrap is built around four core components:

| Component | Description |
|---|---|
| **Scaffolding** | Grid system, background, and base styles for layout |
| **CSS** | Pre-defined stylesheets for typography, forms, buttons, tables, etc. |
| **JS Plugins** | JavaScript and jQuery plugins for interactive components |
| **Customize** | Ability to configure and extend the framework to match project needs |

**Example — using Scaffolding (grid) + CSS + JS together:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.6/dist/css/bootstrap.min.css">
</head>
<body>

  <!-- Scaffolding: grid system -->
  <div class="container">
    <div class="row">
      <div class="col-md-8">Main content</div>
      <div class="col-md-4">Sidebar</div>
    </div>
  </div>

  <!-- JS Plugin: modal trigger -->
  <button class="btn btn-primary" data-toggle="modal" data-target="#myModal">
    Open Modal
  </button>

  <div class="modal fade" id="myModal">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-body">Hello from Bootstrap JS Plugin!</div>
      </div>
    </div>
  </div>

  <script src="https://cdn.jsdelivr.net/npm/jquery@3.6/dist/jquery.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@4.6/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What do you understand by Bootstrap container?

A Bootstrap container is the fundamental layout element that wraps site content. It provides horizontal padding and centers content on the page, making it responsive.

Bootstrap provides three container variants:

| Class | Behavior |
|---|---|
| `.container` | Fixed max-width at each breakpoint, centered |
| `.container-fluid` | Always 100% wide, full viewport width |
| `.container-{breakpoint}` | 100% wide until breakpoint, then fixed |

**Example:**

```html
<!-- Fixed-width container -->
<div class="container">
  <p>Content is centered with fixed max-width per breakpoint.</p>
</div>

<!-- Fluid container (full width) -->
<div class="container-fluid">
  <p>Content spans the full viewport width.</p>
</div>

<!-- Responsive container (full width until md, then fixed) -->
<div class="container-md">
  <p>Full width below md breakpoint, fixed above it.</p>
</div>
```

## Q. How many types of layouts are there in Bootstrap?

There are two types of layouts in Bootstrap:

- **Fluid Layout** — spans the full width of the browser using `.container-fluid`
- **Fixed Layout** — has a fixed max-width that changes at each breakpoint using `.container`

**Example:**

```html
<!-- Fixed Layout -->
<div class="container">
  <div class="row">
    <div class="col-md-6">Fixed left column</div>
    <div class="col-md-6">Fixed right column</div>
  </div>
</div>

<!-- Fluid Layout -->
<div class="container-fluid">
  <div class="row">
    <div class="col-md-6">Fluid left column</div>
    <div class="col-md-6">Fluid right column</div>
  </div>
</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Define Fluid Layout?

Fluid Layout is useful when you need an app that spans the full width of the screen. It adjusts itself according to the browser/viewport size using `.container-fluid`.

**Example:**

```html
<div class="container-fluid">
  <div class="row">
    <div class="col-sm-4">Column 1</div>
    <div class="col-sm-4">Column 2</div>
    <div class="col-sm-4">Column 3</div>
  </div>
</div>
```

## Q. Define Fixed Layout.

Fixed layout uses a fixed max-width controlled by `.container`. Unlike fluid layout it does not span the full browser width — it centers content at predefined widths (e.g., 940px on medium screens).

**Example:**

```html
<div class="container">
  <!-- Centers to 540px on sm, 720px on md, 960px on lg, 1140px on xl -->
  <div class="row">
    <div class="col-md-8">Main content area</div>
    <div class="col-md-4">Sidebar</div>
  </div>
</div>
```

## Q. How can you display a code in Bootstrap?

You can display code in two ways — using the `<code>` tag for inline code and using the `<pre>` tag for multi-line code blocks.

**Example:**

```html
<!-- Inline code -->
<p>Use the <code>console.log()</code> function to print output.</p>

<!-- Multi-line code block -->
<pre>
  function greet(name) {
    return 'Hello, ' + name;
  }
</pre>

<!-- Scrollable pre block -->
<pre class="pre-scrollable">
  .selector {
    color: red;
    background: blue;
  }
</pre>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. When will you use `code` tag and `pre` tag?

- **`<code>`** — for short, inline code snippets embedded within a sentence
- **`<pre>`** — for blocks of code with multiple lines that must preserve whitespace and line breaks

**Example:**

```html
<!-- Inline: single expression within text -->
<p>The CSS property <code>display: flex</code> enables flexbox layout.</p>

<!-- Block: multi-line snippet -->
<pre><code>function add(a, b) {
  return a + b;
}
console.log(add(2, 3)); // 5
</code></pre>
```

## Q. What is a progress bar in bootstrap?

A progress bar visually represents the progress of a task. Bootstrap uses the HTML5 `<progress>` concept via CSS classes applied to `<div>` elements nested inside a `.progress` wrapper.

**Example:**

```html
<!-- Basic progress bar -->
<div class="progress">
  <div class="progress-bar" role="progressbar"
       style="width: 60%" aria-valuenow="60"
       aria-valuemin="0" aria-valuemax="100">
    60%
  </div>
</div>

<!-- Striped and animated -->
<div class="progress">
  <div class="progress-bar progress-bar-striped progress-bar-animated"
       role="progressbar" style="width: 75%">
    75%
  </div>
</div>
```

## Q. Name the contextual classes that are used with the progressive bar in bootstrap?

The contextual classes used with the progress bar control the color:

| Class | Color |
|---|---|
| `.progress-bar-success` | Green |
| `.progress-bar-info` | Blue |
| `.progress-bar-warning` | Yellow/Orange |
| `.progress-bar-danger` | Red |

**Example:**

```html
<div class="progress">
  <div class="progress-bar progress-bar-success" style="width: 40%">40% Success</div>
</div>
<div class="progress">
  <div class="progress-bar progress-bar-info" style="width: 60%">60% Info</div>
</div>
<div class="progress">
  <div class="progress-bar progress-bar-warning" style="width: 70%">70% Warning</div>
</div>
<div class="progress">
  <div class="progress-bar progress-bar-danger" style="width: 90%">90% Danger</div>
</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## # 7. BOOTSTRAP UTILITIES

<br/>

## Q. What are responsive utility classes in Bootstrap?

Responsive utility classes are a set of classes used to show or hide HTML elements based on the current screen resolution, detected via CSS media queries.

**Bootstrap 4 display utilities:**

| Class | Behavior |
|---|---|
| `.d-none` | Hidden on all screens |
| `.d-sm-none` | Hidden on sm and up |
| `.d-md-none` | Hidden on md and up |
| `.d-none .d-md-block` | Hidden on xs/sm, visible from md |

**Example:**

```html
<!-- Hidden on small screens, visible on medium and up -->
<div class="d-none d-md-block">
  <p>Visible only on md, lg, xl screens.</p>
</div>

<!-- Visible on small screens only -->
<div class="d-block d-md-none">
  <p>Visible only on xs and sm screens.</p>
</div>

<!-- Always hidden -->
<div class="d-none">This is never shown.</div>
```

## Q. What are the different button styles in Bootstrap?

Bootstrap provides seven built-in button style classes, each mapped to a semantic color:

| Class | Description |
|---|---|
| `.btn-default` | Default white/grey button |
| `.btn-primary` | Primary blue action |
| `.btn-success` | Green for success |
| `.btn-info` | Light blue for information |
| `.btn-warning` | Yellow/orange for warnings |
| `.btn-danger` | Red for destructive actions |
| `.btn-link` | Styled as a hyperlink |

**Example:**

```html
<button type="button" class="btn btn-default">Default</button>
<button type="button" class="btn btn-primary">Primary</button>
<button type="button" class="btn btn-success">Success</button>
<button type="button" class="btn btn-info">Info</button>
<button type="button" class="btn btn-warning">Warning</button>
<button type="button" class="btn btn-danger">Danger</button>
<button type="button" class="btn btn-link">Link</button>

<!-- Sizing -->
<button type="button" class="btn btn-primary btn-lg">Large</button>
<button type="button" class="btn btn-primary btn-sm">Small</button>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What are Bootstrap alerts?

Bootstrap alerts display contextual feedback messages to the user. They highlight important information with color-coded styling.

Four contextual classes are available: `.alert-success`, `.alert-info`, `.alert-warning`, `.alert-danger`.

**Example:**

```html
<div class="alert alert-success" role="alert">
  <strong>Well done!</strong> You successfully completed the action.
</div>

<div class="alert alert-info" role="alert">
  <strong>Heads up!</strong> This is an informational message.
</div>

<div class="alert alert-warning" role="alert">
  <strong>Warning!</strong> Please check your input.
</div>

<div class="alert alert-danger" role="alert">
  <strong>Error!</strong> Something went wrong.
</div>

<!-- Dismissible alert -->
<div class="alert alert-warning alert-dismissible fade show" role="alert">
  Dismissible warning.
  <button type="button" class="close" data-dismiss="alert" aria-label="Close">
    <span aria-hidden="true">&times;</span>
  </button>
</div>
```

## Q. Define Bootstrap thumbnails?

Bootstrap thumbnails provide a way to lay out images, videos, and text in a grid system. Adding `.thumbnail` class to an `<a>` or `<div>` around an image adds 4px of padding and a grey border.

**Example:**

```html
<!-- Simple image thumbnail -->
<div class="row">
  <div class="col-sm-6 col-md-3">
    <a href="#" class="thumbnail">
      <img src="image.jpg" alt="Thumbnail">
    </a>
  </div>
  <div class="col-sm-6 col-md-3">
    <a href="#" class="thumbnail">
      <img src="image2.jpg" alt="Thumbnail">
    </a>
  </div>
</div>

<!-- Thumbnail with caption -->
<div class="col-sm-6 col-md-3">
  <div class="thumbnail">
    <img src="image.jpg" alt="Photo">
    <div class="caption">
      <h3>Thumbnail Label</h3>
      <p>Some description text here.</p>
      <a href="#" class="btn btn-primary">Button</a>
    </div>
  </div>
</div>
```

## Q. Explain Modal plugin in Bootstrap?

A modal is a dialog box overlaid on the parent page. It is used to augment the user experience by showing information, forms, or confirmations without navigating away from the page. Modal windows are created with the Bootstrap modal plugin.

**Example:**

```html
<!-- Trigger button -->
<button type="button" class="btn btn-primary"
  data-toggle="modal" data-target="#myModal">
  Open Modal
</button>

<!-- Modal structure -->
<div class="modal fade" id="myModal" tabindex="-1"
  role="dialog" aria-labelledby="myModalLabel">
  <div class="modal-dialog" role="document">
    <div class="modal-content">

      <div class="modal-header">
        <h4 class="modal-title" id="myModalLabel">Modal Title</h4>
        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>

      <div class="modal-body">
        <p>Modal body content goes here.</p>
      </div>

      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Save changes</button>
      </div>

    </div>
  </div>
</div>
```

## Q. Which class is used for pagination in Bootstrap?

To add pagination to a webpage, use the `.pagination` class on a `<ul>` element. Each page item uses `.page-item` and each link uses `.page-link`.

**Example:**

```html
<nav aria-label="Page navigation">
  <ul class="pagination">
    <li class="page-item disabled">
      <a class="page-link" href="#" tabindex="-1">Previous</a>
    </li>
    <li class="page-item active">
      <a class="page-link" href="#">1</a>
    </li>
    <li class="page-item">
      <a class="page-link" href="#">2</a>
    </li>
    <li class="page-item">
      <a class="page-link" href="#">3</a>
    </li>
    <li class="page-item">
      <a class="page-link" href="#">Next</a>
    </li>
  </ul>
</nav>

<!-- Sizing variants -->
<ul class="pagination pagination-lg">...</ul>
<ul class="pagination pagination-sm">...</ul>
```

## Q. What is Bootstrap collapsing elements?

Bootstrap collapse allows you to toggle the visibility of content without writing any JavaScript. Add `data-toggle="collapse"` to a trigger element and point it at the collapsible element via `data-target`.

**Example:**

```html
<!-- Trigger -->
<button class="btn btn-primary" type="button"
  data-toggle="collapse" data-target="#collapseExample"
  aria-expanded="false" aria-controls="collapseExample">
  Toggle Content
</button>

<!-- Collapsible content -->
<div class="collapse" id="collapseExample">
  <div class="card card-body">
    This content is hidden by default and shown when toggled.
  </div>
</div>

<!-- Using .collapse(options) via JavaScript -->
<script>
  $('#collapseExample').collapse({ toggle: false });
  $('#collapseExample').collapse('show');
  $('#collapseExample').collapse('hide');
</script>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is Bootstrap Well?

Bootstrap well is a container that makes content appear recessed or inset on the page. It wraps content using the `.well` class and adds a rounded border with inner padding.

**Example:**

```html
<!-- Default well -->
<div class="well">
  <p>Look, I am in a well! Content appears inset.</p>
</div>

<!-- Large well -->
<div class="well well-lg">
  <p>Large well with more padding.</p>
</div>

<!-- Small well -->
<div class="well well-sm">
  <p>Small well with less padding.</p>
</div>
```

> **Note:** Wells were removed in Bootstrap 4. Use utility classes instead:
> ```html
> <div class="bg-light rounded p-3 border">Bootstrap 4+ equivalent</div>
> ```

## Q. Explain the uses of carousel plugin in Bootstrap?

Carousel plugin in bootstrap is used to make sliders in the web pages or your site. There are several carousel plugins that are used in bootstrap to display large contents within a small space by adding sliders.

Example: `.carousel(options)`, `.carousel('pause')`, `.carousel('cycle')`, `.carousel('prev')`, `.carousel('next')`.

## Q. What will be the output of the below code and why?

```html
<div class="progress">
    <div class="progress-bar progress-bar-success" style="width: 65%">
        <span class="sr-only">75% successfully completed</span>
    </div>
    <div class="progress-bar progress-bar-warning" style="width: 20%">
        <span class="sr-only">30% completed with warnings</span>
    </div>
    <div class="progress-bar progress-bar-danger" style="width: 15%">
        <span class="sr-only">15% did not complete</span>
    </div>
</div>
```

If we place multiple bars with the same .progress parent element, Bootstrap will pile them into one single progress bar. As we know, in bootstrap the sum of the progress bar is 100 %. So, the progress bar will give the result as full width and fully populated.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. How can we customize links of pagination in Bootstrap?

Pagination links can be customized using:
- `.disabled` — makes a link visually unclickable (greyed out)
- `.active` — highlights the current page

**Example:**

```html
<nav aria-label="Pagination example">
  <ul class="pagination">
    <!-- Disabled: cannot click Previous on first page -->
    <li class="page-item disabled">
      <a class="page-link" href="#" tabindex="-1" aria-disabled="true">Previous</a>
    </li>

    <li class="page-item"><a class="page-link" href="#">1</a></li>

    <!-- Active: current page -->
    <li class="page-item active" aria-current="page">
      <a class="page-link" href="#">2 <span class="sr-only">(current)</span></a>
    </li>

    <li class="page-item"><a class="page-link" href="#">3</a></li>
    <li class="page-item"><a class="page-link" href="#">Next</a></li>
  </ul>
</nav>
```

## Q. Explain input group in Bootstrap?

Input groups extend form controls by prepending or appending text, buttons, or icons to text-based inputs. Wrap everything in a `.input-group` div and use `.input-group-prepend` / `.input-group-append` with `.input-group-text` for add-ons.

**Example:**

```html
<!-- Prepend text -->
<div class="input-group mb-3">
  <div class="input-group-prepend">
    <span class="input-group-text">@</span>
  </div>
  <input type="text" class="form-control" placeholder="Username">
</div>

<!-- Append text -->
<div class="input-group mb-3">
  <input type="text" class="form-control" placeholder="Amount">
  <div class="input-group-append">
    <span class="input-group-text">.00</span>
  </div>
</div>

<!-- Prepend and append -->
<div class="input-group mb-3">
  <div class="input-group-prepend">
    <span class="input-group-text">$</span>
  </div>
  <input type="text" class="form-control" placeholder="0.00">
  <div class="input-group-append">
    <span class="input-group-text">.00</span>
  </div>
</div>

<!-- With button -->
<div class="input-group mb-3">
  <input type="text" class="form-control" placeholder="Search...">
  <div class="input-group-append">
    <button class="btn btn-outline-secondary" type="button">Go</button>
  </div>
</div>
```

## Q. Write the ways to create a tabbed navigation menu in Bootstrap?

Create a tabbed navigation by building an unordered list with the base class `.nav` and adding the modifier class `.nav-tabs`.

**Example:**

```html
<ul class="nav nav-tabs" id="myTab" role="tablist">
  <li class="nav-item">
    <a class="nav-link active" id="home-tab" data-toggle="tab"
       href="#home" role="tab">Home</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" id="profile-tab" data-toggle="tab"
       href="#profile" role="tab">Profile</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" id="contact-tab" data-toggle="tab"
       href="#contact" role="tab">Contact</a>
  </li>
</ul>

<!-- Tab content -->
<div class="tab-content" id="myTabContent">
  <div class="tab-pane fade show active" id="home" role="tabpanel">Home content</div>
  <div class="tab-pane fade" id="profile" role="tabpanel">Profile content</div>
  <div class="tab-pane fade" id="contact" role="tabpanel">Contact content</div>
</div>
```

## Q. In Bootstrap, how can you create a pills navigation menu?

Create a pills navigation menu by building an unordered list with the base class `.nav` and adding the modifier class `.nav-pills`.

**Example:**

```html
<ul class="nav nav-pills">
  <li class="nav-item">
    <a class="nav-link active" href="#">Home</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Profile</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Messages</a>
  </li>
  <li class="nav-item">
    <a class="nav-link disabled" href="#" tabindex="-1">Disabled</a>
  </li>
</ul>

<!-- Stacked pills (vertical) -->
<ul class="nav nav-pills flex-column">
  <li class="nav-item"><a class="nav-link active" href="#">Home</a></li>
  <li class="nav-item"><a class="nav-link" href="#">About</a></li>
</ul>
```

## Q. How navbar works in Bootstrap?

The Bootstrap navbar is a responsive navigation header component. In mobile view it collapses into a hamburger toggle button. As the viewport width increases, it expands to show navigation links horizontally.

Key classes:
- `.navbar` — base wrapper
- `.navbar-expand-{breakpoint}` — controls collapse breakpoint
- `.navbar-toggler` — the hamburger button for mobile
- `.navbar-collapse` — wraps collapsible content

**Example:**

```html
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Brand</a>

  <!-- Hamburger button (shown on mobile) -->
  <button class="navbar-toggler" type="button"
    data-toggle="collapse" data-target="#navMenu">
    <span class="navbar-toggler-icon"></span>
  </button>

  <!-- Collapsible section -->
  <div class="collapse navbar-collapse" id="navMenu">
    <ul class="navbar-nav ml-auto">
      <li class="nav-item active"><a class="nav-link" href="#">Home</a></li>
      <li class="nav-item"><a class="nav-link" href="#">About</a></li>
      <li class="nav-item"><a class="nav-link" href="#">Contact</a></li>
    </ul>
  </div>
</nav>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. How we can create a navbar in Bootstrap?

To create a navbar in Bootstrap:
1. Add `.navbar` and `.navbar-default` (Bootstrap 3) or `.navbar-light`/`.navbar-dark` (Bootstrap 4+) to the `<nav>` tag
2. Add `role="navigation"` for accessibility
3. Add `.navbar-brand` for the logo/brand text
4. Wrap navigation links in `.navbar-collapse`

**Example:**

```html
<nav class="navbar navbar-expand-md navbar-dark bg-dark" role="navigation">
  <!-- Brand -->
  <a class="navbar-brand" href="#">MySite</a>

  <!-- Mobile toggler -->
  <button class="navbar-toggler" type="button"
    data-toggle="collapse" data-target="#mainNav"
    aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <!-- Nav links -->
  <div class="collapse navbar-collapse" id="mainNav">
    <ul class="navbar-nav ml-auto">
      <li class="nav-item active">
        <a class="nav-link" href="#">Home</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Services</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Contact</a>
      </li>
    </ul>
  </div>
</nav>
```

## Q. What is Bootstrap breadcrumb?

Bootstrap breadcrumb shows the navigational hierarchy of a site, informing users of their current page location. It is built as an unordered list with the class `.breadcrumb`. Separators are added automatically via CSS.

Common uses: documentation pages, blogs, ERP systems.

**Example:**

```html
<nav aria-label="breadcrumb">
  <ol class="breadcrumb">
    <li class="breadcrumb-item"><a href="#">Home</a></li>
    <li class="breadcrumb-item"><a href="#">Library</a></li>
    <li class="breadcrumb-item active" aria-current="page">Data</li>
  </ol>
</nav>
```

The separator is defined via CSS:

```css
.breadcrumb-item + .breadcrumb-item::before {
  color: #6c757d;
  content: "/";
}
```

## Q. What are labels in Bootstrap?

Bootstrap labels are small informational tags used to display counts, statuses, or tips inline with content. Apply the `.label` class along with a contextual class.

**Example:**

```html
<h3>Example heading <span class="label label-default">New</span></h3>
<h3>Notifications <span class="label label-primary">3</span></h3>

<!-- Contextual label variants -->
<span class="label label-default">Default</span>
<span class="label label-primary">Primary</span>
<span class="label label-success">Success</span>
<span class="label label-info">Info</span>
<span class="label label-warning">Warning</span>
<span class="label label-danger">Danger</span>
```

> **Note:** Labels were removed in Bootstrap 4. Use `.badge` instead.

## Q. What are badges in Bootstrap?

Badges are similar to labels but with more rounded corners. They are used to highlight new or unread items, such as message counts or notification numbers. Add `<span class="badge">` inside links or nav items.

**Example:**

```html
<!-- Badge on a link -->
<a href="#">Inbox <span class="badge">42</span></a>

<!-- Badge on a button -->
<button type="button" class="btn btn-primary">
  Notifications <span class="badge badge-light">9</span>
</button>

<!-- Contextual badges (Bootstrap 4) -->
<span class="badge badge-primary">Primary</span>
<span class="badge badge-success">Success</span>
<span class="badge badge-danger">Danger</span>
<span class="badge badge-warning text-dark">Warning</span>

<!-- Pill badge (fully rounded) -->
<span class="badge badge-pill badge-info">New</span>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is a jumbotron in Bootstrap?

A jumbotron is a large, prominently styled box used to showcase key marketing content or featured messages. It increases the size of headings and adds extra padding/margins. Create it with a `<div class="jumbotron">`.

**Example:**

```html
<div class="jumbotron">
  <h1 class="display-4">Welcome to My Site!</h1>
  <p class="lead">This is a simple hero unit for highlighting featured content.</p>
  <hr class="my-4">
  <p>It uses utility classes for typography and spacing.</p>
  <a class="btn btn-primary btn-lg" href="#" role="button">Learn more</a>
</div>

<!-- Full-width jumbotron (no rounded corners) -->
<div class="jumbotron jumbotron-fluid">
  <div class="container">
    <h1 class="display-4">Full-width Jumbotron</h1>
    <p class="lead">Spans the full width of the viewport.</p>
  </div>
</div>
```

> **Note:** Jumbotron was removed in Bootstrap 5. Achieve the same effect with utility classes:
> ```html
> <div class="p-5 mb-4 bg-light rounded-3">
>   <h1 class="display-5">Hello, world!</h1>
> </div>
> ```

## Q. How can we make image responsive in Bootstrap?

Add the class `.img-responsive` (Bootstrap 3) or `.img-fluid` (Bootstrap 4+) to the `<img>` tag. This sets `max-width: 100%` and `height: auto` so the image scales with its parent container.

**Example:**

```html
<!-- Bootstrap 3 -->
<img src="photo.jpg" class="img-responsive" alt="Responsive image">

<!-- Bootstrap 4 / 5 -->
<img src="photo.jpg" class="img-fluid" alt="Responsive image">

<!-- With rounded corners -->
<img src="photo.jpg" class="img-fluid rounded" alt="Rounded responsive image">

<!-- Circle crop -->
<img src="avatar.jpg" class="img-fluid rounded-circle" alt="Circle image">

<!-- Thumbnail style -->
<img src="photo.jpg" class="img-fluid img-thumbnail" alt="Thumbnail image">
```

## Q. What do you mean by normalize in Bootstrap?

Bootstrap normalize is a small CSS file (`normalize.css`) that ensures consistent default styling across all browsers by overriding browser-specific default styles.

**What it does:**
- Corrects inconsistencies between browsers (e.g., margins, fonts, line heights)
- Makes `<h1>`–`<h6>`, `<p>`, `<a>`, `<code>` render the same in Chrome, Firefox, Safari, Edge
- Preserves useful defaults rather than removing all styles

**Example — without normalize vs with normalize:**

```html
<!-- Without normalize: button looks different in each browser -->
<button>Click me</button>

<!-- Bootstrap includes normalize so this renders consistently everywhere -->
<button class="btn btn-primary">Click me</button>
```

In Bootstrap 4+, `normalize.css` is incorporated into `_reboot.scss`, which applies to the base document:

```css
/* From Bootstrap reboot */ 
*, *::before, *::after {
  box-sizing: border-box;
}
body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  font-size: 1rem;
  line-height: 1.5;
}
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is lead body copy in Bootstrap?

Adding `class="lead"` to a `<p>` element makes it stand out from regular body text by increasing the font size and line height, typically used for introductory paragraphs.

**Example:**

```html
<p class="lead">
  This is a lead paragraph. It will stand out from regular paragraphs
  with a larger font size and taller line height.
</p>

<p>
  This is a regular paragraph. It uses the default body font size and line height.
</p>
```

## Q. What are panels in Bootstrap?

Panels are boxed components used to group related DOM content visually. Add `.panel` and a contextual class (e.g., `.panel-default`) to a `<div>`. Content goes inside `.panel-body`.

**Example:**

```html
<!-- Default panel -->
<div class="panel panel-default">
  <div class="panel-body">
    This is a basic panel.
  </div>
</div>

<!-- Contextual panels -->
<div class="panel panel-primary">
  <div class="panel-heading">Panel with heading</div>
  <div class="panel-body">Primary panel content.</div>
</div>

<div class="panel panel-success">
  <div class="panel-heading">Success</div>
  <div class="panel-body">Operation completed successfully.</div>
  <div class="panel-footer">Panel footer</div>
</div>
```

> **Note:** Panels were removed in Bootstrap 4 and replaced by Cards.

## Q. How will you create a Bootstrap panel with heading?

There are two ways to add a heading to a Bootstrap panel:
1. Use `.panel-heading` class directly on a `<div>`
2. Use a heading tag (`<h1>`–`<h6>`) with `.panel-title` inside `.panel-heading` for richer styling

**Example:**

```html
<!-- Method 1: .panel-heading directly -->
<div class="panel panel-primary">
  <div class="panel-heading">Panel Heading</div>
  <div class="panel-body">Panel body content.</div>
</div>

<!-- Method 2: heading tag + .panel-title for better semantics -->
<div class="panel panel-success">
  <div class="panel-heading">
    <h3 class="panel-title">Styled Panel Title</h3>
  </div>
  <div class="panel-body">
    This panel uses a semantic heading with panel-title class.
  </div>
  <div class="panel-footer">Footer text</div>
</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is a scrollspy plugin in Bootstrap?

Scrollspy automatically updates navigation links based on scroll position. Add the `.active` class to the navbar link corresponding to the currently visible section.

**Example:**

```html
<!-- Navbar to spy into -->
<nav id="navbar-spy" class="navbar navbar-light bg-light"
     style="position: sticky; top: 0;">
  <ul class="nav nav-pills">
    <li class="nav-item"><a class="nav-link" href="#section1">Section 1</a></li>
    <li class="nav-item"><a class="nav-link" href="#section2">Section 2</a></li>
    <li class="nav-item"><a class="nav-link" href="#section3">Section 3</a></li>
  </ul>
</nav>

<!-- Scrollable content -->
<div data-spy="scroll" data-target="#navbar-spy" data-offset="0"
     style="height: 300px; overflow-y: scroll;">
  <h4 id="section1">Section 1</h4>
  <p>Content for section one...</p>
  <h4 id="section2">Section 2</h4>
  <p>Content for section two...</p>
  <h4 id="section3">Section 3</h4>
  <p>Content for section three...</p>
</div>
```

## Q. What is grid system in Bootstrap?

Bootstrap’s grid system uses a 12-column flex-based layout to build responsive multi-column page structures. It is built with containers, rows, and columns.

**Example:**

```html
<!-- Equal-width columns (each is 4/12) -->
<div class="container">
  <div class="row">
    <div class="col-md-4">Column 1</div>
    <div class="col-md-4">Column 2</div>
    <div class="col-md-4">Column 3</div>
  </div>
</div>

<!-- Unequal columns -->
<div class="container">
  <div class="row">
    <div class="col-md-8">Main content (8/12)</div>
    <div class="col-md-4">Sidebar (4/12)</div>
  </div>
</div>

<!-- Auto-layout: equal widths without specifying numbers -->
<div class="container">
  <div class="row">
    <div class="col">Auto</div>
    <div class="col">Auto</div>
    <div class="col">Auto</div>
  </div>
</div>
```

## Q. What are Grid classes in the Bootstrap?

Bootstrap defines four responsive grid tiers:

| Class Prefix | Breakpoint | Target Device |
|---|---|---|
| `.col-` (xs) | < 576px | Small phones |
| `.col-sm-` | ≥ 576px | Phones / large phones |
| `.col-md-` | ≥ 768px | Tablets |
| `.col-lg-` | ≥ 992px | Small laptops |
| `.col-xl-` | ≥ 1200px | Desktops |

**Example:**

```html
<div class="container">
  <div class="row">
    <!-- Full-width on phones, half-width on tablets, one-third on desktop -->
    <div class="col-12 col-sm-6 col-md-4">Card 1</div>
    <div class="col-12 col-sm-6 col-md-4">Card 2</div>
    <div class="col-12 col-sm-12 col-md-4">Card 3</div>
  </div>
</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What are global styles that are used in Bootstrap Default Typography?

In Bootstrap the global default font-size is 14px and the line height is 1.428. The default font changes to Helvetica and Arial are with sans-serif fallback and all these styles are applicable for both body and all paragraphs.

## Q. What will be the output of the below code?

```html
<div class="row">
    <div class="col-xs-12 col-md-3">.col-xs-12 .col-md-3</div>
</div>
```

The output of this will give the grids for extra small devices as we can see in the snippet col-xs-12 that has been used and it will also give the grids for desktop devices and above as the class col-md-3 has been used.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What dependencies does Bootstrap require to work properly?

For Bootstrap 3/4, **jQuery** is the only external dependency required for JavaScript plugins. Bootstrap 5 removed the jQuery dependency and uses vanilla JavaScript.

**Bootstrap 4 — required script order:**

```html
<!-- 1. jQuery (required for Bootstrap 4 JS plugins) -->
<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>

<!-- 2. Popper.js (required for tooltips and dropdowns) -->
<script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.1/dist/umd/popper.min.js"></script>

<!-- 3. Bootstrap JS -->
<script src="https://cdn.jsdelivr.net/npm/bootstrap@4.6/dist/js/bootstrap.min.js"></script>
```

**Bootstrap 5 — no jQuery needed:**

```html
<!-- Bootstrap 5 bundle includes Popper.js -->
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5/dist/js/bootstrap.bundle.min.js"></script>
```

## Q.  What the below code will do?

```html
<a href="#">Home <span class="badge">36</span></a>
```

 This code will produce a link with an inline badge which will give an important notification to the user like number received, message received or the number of requests etc.

## Q. What are the two codes that are used for code display in Bootstrap?

The codes are `code` tag and `pre` tag.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is a transition plugin in Bootstrap?

The Bootstrap transition plugin provides simple CSS transition effects such as sliding and fading for modal dialogs, alerts, collapsible elements, and carousels.

**Example — fade transition on a modal:**

```html
<!-- Adding .fade enables fade-in/out transition on the modal -->
<div class="modal fade" id="fadeModal" tabindex="-1">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title">Fade Modal</h5>
        <button type="button" class="close" data-dismiss="modal">&times;</button>
      </div>
      <div class="modal-body">This modal fades in and out.</div>
    </div>
  </div>
</div>

<!-- Fade transition on an alert -->
<div class="alert alert-success alert-dismissible fade show" role="alert">
  This alert fades when dismissed.
  <button type="button" class="close" data-dismiss="alert" aria-label="Close">
    <span aria-hidden="true">&times;</span>
  </button>
</div>
```

## Q. Explain the concept of creating a vertical or basic form in Bootstrap?

A basic (vertical) form in Bootstrap stacks labels above inputs. The key steps are:
1. Add `role="form"` to the parent `<form>` element
2. Wrap each label and input pair in a `<div class="form-group">`
3. Add `.form-control` to all `<input>`, `<textarea>`, and `<select>` elements

**Example:**

```html
<form role="form">
  <div class="form-group">
    <label for="name">Name</label>
    <input type="text" class="form-control" id="name" placeholder="Enter your name">
  </div>

  <div class="form-group">
    <label for="email">Email address</label>
    <input type="email" class="form-control" id="email" placeholder="Enter email">
    <small class="form-text text-muted">We'll never share your email.</small>
  </div>

  <div class="form-group">
    <label for="message">Message</label>
    <textarea class="form-control" id="message" rows="3"></textarea>
  </div>

  <div class="form-group">
    <label for="country">Country</label>
    <select class="form-control" id="country">
      <option>USA</option>
      <option>UK</option>
      <option>India</option>
    </select>
  </div>

  <button type="submit" class="btn btn-primary">Submit</button>
</form>
```

## Q. Explain the Bootstrap framework structure?

Bootstrap is a responsive front-end mobile development framework. Sites can be effectively created with the grid system of the Bootstrap framework. its holds a highly responsive design and very much customizable, Mobile sites can be built on top of the Bootstrap framework using below  programming entities,

HTML5 markup
CSS Styling
Javascript
Fonts
Here on mobile measurements content can be divided into 12 columns, then it can further be reduced to 6,4,3, etc. Ease of style and making define the Bootstrap buttons with default classes available for images as well.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What are Breadcrumbs in bootstrap?

Breadcrumbs depict the navigational hierarchy of a site, separators in the hierarchy are automatically added by means of CSS.

Bootstrap breadcrumb used for,

Documentation page
Magazine
ERP system
A breadcrumb in Bootstrap is simply an unordered list with a class of .breadcrumb.

Example:

```css

.breadcrumb > li + li:before {
    color: #CCCCCC;
    content: “/ “;
    padding: 0 5px;
}
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Why do we use Jumbotron in Bootstrap?

Jumbotron is a user-attractive function of Bootstrap. it is a brilliant way to highlight the key contents of a page. the content could be a slogan or probably a headline or any other catchy element of the page. Jumbotron works by increasing the content of the landing page and also increasing the heading size of the content. In order to implement Jumbotron in a Bootstrap use:

Create a container `div` with the class of. Jumbotron

Example: The example shows wrapping up of heading contents inside a div class Jumbotron container.

```html
<div class="jumbotron">
    <h1>Learn to Create Websites</h1>
    <p>In today\'s world internet is the most popular way…</p>
    <p><a href="#" class="btn btn-primary btn-lg">Learn more</a></p>
</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Explain types of lists supported by Bootstrap?

Lists supported by Bootstrap are as following,

Definition lists −  Evey list is by default introduced with a `dt` and `dd` tag ement

`dt` : definition term
`dd` : corresponds to the defenition of `dt`
Ordered lists − lies in a sequential order and prefixed by numerical values.

Unordered lists −  styled traditionally, does not follow any specific order. bullets can be easily customized.  class, list-inline can be used to hold all list items within a single line.

Let us move to the next Bootstrap Interview Questions And Answer.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Navigation bar in Bootstrap?

This is the advanced Bootstrap Interview Questions which is asked in an interview. It resembles the navigation header in the top of the page, the navigation bar can be created with Nav tag. Navbars and their contents are fluid by default. The horizontal width can be scaled and controlled using Navigation containers. Navbars are concealed by default while printing.

Example:  

```html
<nav class="navbar navbar-expand-lg navbar-light bg-light">
    <div class="dropdown-menu" aria-labelledby="navbarDropdown">
        <a class="dropdown-item" href="#">Action</a>
        <a class="dropdown-item" href="#">Another action</a>
    <div class="dropdown-divider"></div>
        <a class="dropdown-item" href="#">Something else here</a>
    </div>
</nav>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Describe a Bootstrap panel Bootstrap well and Bootstrap carousel?

Bootstrap well: Adds a greyish rounded background around the content, it is a container class. The .well-sm class for small wells and .well-lg class for large wells allows alternate the size of the well. Default well size is normal.

Example:

```html
<div class="well">Basic Well</div>
```

Bootstrap panel: There could be situations where some site contents need to be wrapped up in a box to enhance the visibility for the user. Bootstrap panels lock hands on these needs. They can be created with the .panel class and content inside the panel has a .panel-body class.

Example:

```html
<div class="panel panel-default">
    <div class="panel-body">Look, I'm in a panel!</div>
</div>
```

Bootstrap carousel:  Adds a slider through which images, videos, and contents can be populated and sided for the users. It is a flexible, handy and responsive way to add a carousel to our site. Carousel plug-in is a component which is used for the same.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## # 8. BOOTSTRAP 5 FEATURES

<br/>

## Q. What are the new features added in Bootstrap-5?

Bootstrap 5 introduced several major changes over Bootstrap 4:

- **Dropped jQuery**: All JavaScript plugins are rewritten in vanilla JS — no jQuery dependency.
- **New `xxl` breakpoint**: Added a sixth breakpoint at ≥1400px; breakpoints are `xs`, `sm`, `md`, `lg`, `xl`, `xxl`.
- **RTL support**: Built-in right-to-left language support via separate RTL CSS builds.
- **Offcanvas component**: New sidebar/drawer component (`.offcanvas`) for menus and panels.
- **Improved grid gutters**: New `.g-*`, `.gx-*`, `.gy-*` gutter classes replace the old padding approach.
- **Row columns**: `.row-cols-*` classes control the number of columns per row directly on the row.
- **Redesigned forms**: Fully rewritten form controls with a consistent custom appearance across browsers; floating labels (`.form-floating`).
- **Utility API**: A Sass-based API to generate and extend utility classes without custom CSS.
- **Improved color system**: Extended palette with new `text-opacity-*`, `bg-opacity-*`, and tint/shade variants.
- **CSS custom properties**: Increased use of CSS variables for colors, font sizes, and component styles.
- **New Accordion component**: Dedicated `.accordion` component replacing the old collapse-based pattern.
- **Updated Popper**: Uses Popper.js v2 for tooltips and popovers.
- **Dropped IE support**: IE 10 and IE 11 are no longer supported.
- **Renamed data attributes**: All `data-*` attributes are now `data-bs-*` (e.g. `data-bs-toggle`, `data-bs-target`).
- **Helpers & extended utilities**: New ratio helpers (`.ratio`), position utilities, stacks (`.vstack`, `.hstack`), and more.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Types of Layouts in Bootstrap?

Bootstrap supports two main types of layouts:

1. **Fixed Layout** (`.container`): Has a fixed max-width that changes at each breakpoint. Centers content on the page.
2. **Fluid Layout** (`.container-fluid`): Always 100% wide, spanning the full viewport width.

```html
<div class="container">Fixed width layout</div>
<div class="container-fluid">Full width layout</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is the role of Jumbotron in Bootstrap?

Jumbotron is used to highlight key marketing messages or featured content. It provides a large, prominently styled box with enlarged headings and increased padding.

```html
<div class="jumbotron">
  <h1 class="display-4">Hello, World!</h1>
  <p class="lead">This is a simple hero unit.</p>
  <hr class="my-4">
  <a class="btn btn-primary btn-lg" href="#" role="button">Learn more</a>
</div>
```

**Note:** Jumbotron was removed in Bootstrap 5. Use utility classes to achieve the same effect.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. How to align a flex item on the baseline in Bootstrap?

Use the `.align-self-baseline` class to align a single flex item along the text baseline. For responsive variants, use `.align-self-{breakpoint}-baseline`.

```html
<div class="d-flex align-items-start">
  <div class="align-self-baseline" style="font-size: 2rem;">Large</div>
  <div class="align-self-baseline">Normal baseline-aligned item</div>
</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Differentiate between Bootstrap and Foundation

| Bootstrap | Foundation |
|-----------|-----------|
| Developed by Twitter | Developed by ZURB |
| Uses `px` (v3) / `rem` (v4+) | Uses `rem` units |
| Uses Sass (v4+) | Uses Sass |
| Mobile-first from v4 | Mobile-first by design |
| Larger community and ecosystem | Smaller but dedicated community |
| No built-in icons from v4 | No built-in icons |
| 12-column grid | 12-column grid |

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is an Alert component in Bootstrap?

Alerts provide contextual feedback messages for typical user actions. Available classes: `.alert-primary`, `.alert-secondary`, `.alert-success`, `.alert-danger`, `.alert-warning`, `.alert-info`, `.alert-light`, `.alert-dark`.

```html
<div class="alert alert-success" role="alert">
  This is a success alert!
</div>
<div class="alert alert-danger" role="alert">
  This is a danger alert!
</div>
<div class="alert alert-warning alert-dismissible fade show" role="alert">
  Dismissible warning alert.
  <button type="button" class="close" data-dismiss="alert" aria-label="Close">
    <span aria-hidden="true">&times;</span>
  </button>
</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is a Tooltip component in Bootstrap?

A tooltip is a small pop-up that appears when the user hovers over an element. Tooltips require JavaScript initialization and are opt-in for performance reasons.

```html
<!-- HTML -->
<button type="button" class="btn btn-secondary"
  data-toggle="tooltip" data-placement="top" title="Tooltip on top">
  Hover me
</button>

<!-- JavaScript initialization -->
<script>
  $(function () {
    $('[data-toggle="tooltip"]').tooltip();
  });
</script>
```

Placements: `top`, `bottom`, `left`, `right`.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Striped Progress Bar in Bootstrap

Add `.progress-bar-striped` to the `.progress-bar` element to apply a CSS gradient striped effect. Combine with `.progress-bar-animated` to animate the stripes.

```html
<!-- Striped -->
<div class="progress">
  <div class="progress-bar progress-bar-striped bg-success" role="progressbar"
       style="width: 50%" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100">
    50%
  </div>
</div>

<!-- Animated striped -->
<div class="progress">
  <div class="progress-bar progress-bar-striped progress-bar-animated"
       role="progressbar" style="width: 75%">
    75%
  </div>
</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Why the align-self-sm-stretch class used in Bootstrap 5?

`.align-self-sm-stretch` applies `align-self: stretch` to a **single** flex item starting at the `sm` breakpoint (≥576px) and above. It makes that one item expand to fill the full cross-axis height of the flex container, regardless of what the container\'s `align-items` value is set to.

**Why it is useful:**

- **Override container alignment for one item**: the container may use `align-items-start` or `align-items-center`, but a specific child needs to fill the full height
- **Equal-height cards/columns**: stretch a button or image panel to match the tallest sibling without making every item stretch
- **Responsive-only**: only stretches on `sm`+ screens; on `xs` the item uses its natural height

```html
<!-- Container aligns to start, but one item stretches to full height on sm+ -->
<div class="d-flex align-items-start" style="height: 150px; background: #eee;">
  <div class="p-2 bg-primary text-white">Short item</div>
  <div class="p-2 bg-success text-white align-self-sm-stretch">
    Stretches on sm+
  </div>
  <div class="p-2 bg-warning">Another short item</div>
</div>

<!-- Common use: stretch a sidebar to match main content height -->
<div class="d-sm-flex">
  <div class="p-3 bg-light align-self-sm-stretch">Sidebar</div>
  <div class="p-3">Main content that may be taller</div>
</div>
```

**Comparison of `align-self` values on a single item:**

| Class | CSS value | Effect on that item |
|---|---|---|
| `.align-self-sm-start` | `flex-start` | Aligns to top of container |
| `.align-self-sm-center` | `center` | Vertically centered |
| `.align-self-sm-end` | `flex-end` | Aligns to bottom |
| `.align-self-sm-baseline` | `baseline` | Aligns on text baseline |
| `.align-self-sm-stretch` | `stretch` | Fills full container height |

`align-self-*` always targets **one item**; `align-items-*` targets **all items** in the container. The `sm` infix means the rule only activates at ≥576px — on `xs` the item reverts to the container\'s default alignment.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Form Control states in Bootstrap

Bootstrap provides several visual states for form controls:

- **Focus**: Highlighted with an outline/box-shadow when active.
- **Disabled**: Add `disabled` attribute to grey out the input.
- **Readonly**: Add `readonly` to make non-editable but selectable.
- **Validation states**: Use `.is-valid` / `.is-invalid` for success/error feedback.

```html
<input type="text" class="form-control is-valid" value="Correct value">
<div class="valid-feedback">Looks good!</div>

<input type="text" class="form-control is-invalid" value="Wrong value">
<div class="invalid-feedback">Please provide a valid input.</div>

<input type="text" class="form-control" disabled placeholder="Disabled input">
<input type="text" class="form-control" readonly value="Readonly input">
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Why do we need a static Control in Bootstrap?

A static control (`.form-control-plaintext`) displays a form field value as plain text while maintaining the same layout alignment as other form controls. It is useful in read-only/view modes where consistent alignment matters.

```html
<form>
  <div class="form-group row">
    <label class="col-sm-2 col-form-label">Email</label>
    <div class="col-sm-10">
      <input type="text" readonly class="form-control-plaintext"
             value="email@example.com">
    </div>
  </div>
</form>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Why should we use Button Groups in Bootstrap?

Button groups place multiple buttons on a single line, useful for toolbars and toggle sets. Use `.btn-group` for horizontal groups and `.btn-group-vertical` for vertical groups.

```html
<!-- Basic button group -->
<div class="btn-group" role="group" aria-label="Basic example">
  <button type="button" class="btn btn-secondary">Left</button>
  <button type="button" class="btn btn-secondary">Middle</button>
  <button type="button" class="btn btn-secondary">Right</button>
</div>

<!-- Button toolbar -->
<div class="btn-toolbar" role="toolbar">
  <div class="btn-group mr-2" role="group">
    <button type="button" class="btn btn-secondary">1</button>
    <button type="button" class="btn btn-secondary">2</button>
  </div>
  <div class="btn-group" role="group">
    <button type="button" class="btn btn-secondary">3</button>
  </div>
</div>
```

Use `.btn-group-sm` or `.btn-group-lg` for sizing.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Horizontal Form in Bootstrap

A horizontal form aligns labels and controls side by side using the grid system. Add `.row` to form groups and use `.col-sm-*` classes for labels and inputs.

```html
<form>
  <div class="form-group row">
    <label for="inputEmail" class="col-sm-2 col-form-label">Email</label>
    <div class="col-sm-10">
      <input type="email" class="form-control" id="inputEmail" placeholder="Email">
    </div>
  </div>
  <div class="form-group row">
    <label for="inputPassword" class="col-sm-2 col-form-label">Password</label>
    <div class="col-sm-10">
      <input type="password" class="form-control" id="inputPassword" placeholder="Password">
    </div>
  </div>
  <div class="form-group row">
    <div class="col-sm-10 offset-sm-2">
      <button type="submit" class="btn btn-primary">Sign in</button>
    </div>
  </div>
</form>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is a Bootstrap Navbar?

The Bootstrap Navbar is a responsive navigation header component that collapses on smaller screens (toggled with a hamburger button) and expands on larger ones.

Key classes:
- `.navbar` — base class
- `.navbar-expand-{breakpoint}` — controls when navbar collapses
- `.navbar-light` / `.navbar-dark` — color scheme
- `.bg-*` — background color utilities

```html
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Brand</a>
  <button class="navbar-toggler" type="button"
    data-toggle="collapse" data-target="#navbarNav">
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse" id="navbarNav">
    <ul class="navbar-nav">
      <li class="nav-item active">
        <a class="nav-link" href="#">Home</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Features</a>
      </li>
    </ul>
  </div>
</nav>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. How to add inline subheadings in Bootstrap

Use the `<small>` tag or `.text-muted` class inside a heading to add an inline subheading.

```html
<h1>Main heading <small class="text-muted">Subheading</small></h1>
<h2>Section title <small class="text-muted">Secondary text</small></h2>
<h3>Another heading <small class="text-muted">Supporting text</small></h3>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. How to wrap flex items on different screens in Bootstrap?

Use `.flex-wrap`, `.flex-nowrap`, or `.flex-wrap-reverse` to control wrapping. Add breakpoint infixes for responsive behavior.

```html
<!-- Always wrap -->
<div class="d-flex flex-wrap">...</div>

<!-- No wrap on xs, wrap from sm upward -->
<div class="d-flex flex-nowrap flex-sm-wrap">...</div>

<!-- Wrap only from md upward -->
<div class="d-flex flex-nowrap flex-md-wrap">...</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. How to make a link unclickable in Bootstrap Navbar?

Add the `.disabled` class to a `.nav-link` to make it visually disabled and suppress pointer events.

```html
<ul class="navbar-nav">
  <li class="nav-item">
    <a class="nav-link disabled" href="#"
       tabindex="-1" aria-disabled="true">Disabled</a>
  </li>
</ul>
```

The `.disabled` class sets `pointer-events: none` and reduces the link\'s opacity.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is a Bootstrap Container?

Bootstrap provides three container classes:

| Class | Behavior |
|---|---|
| `.container` | Fixed max-width, changes at each breakpoint, centered |
| `.container-fluid` | Always 100% viewport width |
| `.container-{breakpoint}` | 100% wide until the specified breakpoint, then fixed |

```html
<div class="container">Fixed width</div>
<div class="container-fluid">Full width</div>
<div class="container-md">Full width until md, then fixed</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Bootstrap Collapse example?

The collapse component toggles the visibility of content. Use `data-toggle="collapse"` and `data-target` to wire up a trigger.

```html
<button class="btn btn-primary" type="button"
  data-toggle="collapse" data-target="#collapseExample"
  aria-expanded="false" aria-controls="collapseExample">
  Toggle Content
</button>

<div class="collapse" id="collapseExample">
  <div class="card card-body">
    This content is hidden by default and shown on toggle.
  </div>
</div>
```

For an accordion, group collapses in a parent and use `data-parent`:

```html
<div id="accordion">
  <div class="card">
    <div class="card-header">
      <button class="btn btn-link" data-toggle="collapse"
        data-target="#collapseOne" data-parent="#accordion">
        Item #1
      </button>
    </div>
    <div id="collapseOne" class="collapse show" data-parent="#accordion">
      <div class="card-body">Content for item 1.</div>
    </div>
  </div>
</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Why the .flex-sm-shrink-1 class used in Bootstrap 5?

The `.flex-sm-shrink-1` class applies `flex-shrink: 1` to a flex item starting at the `sm` breakpoint (≥576px) and above. It allows the item to shrink proportionally when there is insufficient space in the flex container.

It is most commonly used to re-enable shrinking on an item that was previously prevented from shrinking with `.flex-shrink-0`:

**Example**:

```html
<div class="d-flex">
  <div class="flex-shrink-0 p-2">Always full size — won\'t shrink</div>
  <div class="flex-shrink-0 flex-sm-shrink-1 p-2">
    Won\'t shrink on xs, but can shrink on sm and above
  </div>
</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Why Bootstrap has a Grid System?

The grid system allows complex responsive layouts to be built quickly and consistently using rows and columns based on a 12-column Flexbox layout.

Benefits:
- **Responsive**: Columns automatically adapt to screen size.
- **Flexible**: Columns can be nested, offset, and reordered.
- **Consistent**: All layouts follow the same pattern, making code predictable.

```html
<div class="container">
  <div class="row">
    <div class="col-md-4">Column 1</div>
    <div class="col-md-4">Column 2</div>
    <div class="col-md-4">Column 3</div>
  </div>
</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Why the flex-md-row-reverse class used in Bootstrap 5?

Compacted conversation`.flex-md-row-reverse` applies `flex-direction: row-reverse` to a flex container at the `md` breakpoint (≥768px) and above. It reverses the visual order of flex items from right to left **without changing the HTML source order**.

**Why it is useful:**

- **Responsive layout swapping**: show content in one order on mobile, reversed on desktop — without duplicating HTML
- **Alternate image/text layouts**: place an image on the left on mobile but push it to the right on wider screens
- **SEO/accessibility**: keep the most important content first in the DOM regardless of visual presentation

```html
<!-- Text first in DOM (good for SEO), image pushed left on md+ -->
<div class="d-flex flex-column flex-md-row-reverse align-items-center gap-3">
  <div class="p-3">
    <h2>Heading</h2>
    <p>This text is first in the DOM but appears on the right on md+.</p>
  </div>
  <img src="photo.jpg" alt="Photo" class="img-fluid">
  <!-- Image is second in DOM but shown on the LEFT on md+ -->
</div>
```

**Comparison of `flex-direction` responsive variants:**

| Class | CSS value | Effect |
|---|---|---|
| `.flex-md-row` | `row` | Left→right order on md+ |
| `.flex-md-row-reverse` | `row-reverse` | Right→left order on md+ |
| `.flex-md-column` | `column` | Top→bottom stacking on md+ |
| `.flex-md-column-reverse` | `column-reverse` | Bottom→top stacking on md+ |

The `md` infix means the rule only activates at ≥768px — below that the element uses whatever flex direction was set for smaller breakpoints (or the browser default). The class name and behavior are identical in Bootstrap 4 and 5.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. How to display flex items vertically on small screen in Bootstrap 5?

Use `.flex-column` to stack flex items vertically. Combine with a responsive `.flex-{breakpoint}-row` variant to switch to horizontal layout on larger screens.

```html
<!-- Always vertical -->
<div class="d-flex flex-column">
  <div class="p-2">Item 1</div>
  <div class="p-2">Item 2</div>
  <div class="p-2">Item 3</div>
</div>

<!-- Vertical on xs only, horizontal from sm (≥576px) upward -->
<div class="d-flex flex-column flex-sm-row">
  <div class="p-2">Item 1</div>
  <div class="p-2">Item 2</div>
</div>

<!-- Vertical on xs and sm, horizontal from md (≥768px) upward -->
<div class="d-flex flex-column flex-md-row">
  <div class="p-2">Item 1</div>
  <div class="p-2">Item 2</div>
</div>
```

**Key classes:**

| Class | Effect |
|---|---|
| `.flex-column` | Vertical on all screen sizes |
| `.flex-column-reverse` | Vertical, reversed order |
| `.flex-sm-row` | Switch to horizontal at ≥576px |
| `.flex-md-row` | Switch to horizontal at ≥768px |

In Bootstrap 5 the class names are identical to Bootstrap 4 — only the data attributes (`data-bs-*`) and jQuery dependency changed, not the flex utilities.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Why the align-items-sm-baseline class used in Bootstrap 5?

`.align-items-sm-baseline` applies `align-items: baseline` to a flex container starting at the `sm` breakpoint (≥576px) and above. It aligns **all** child flex items along their shared text baseline, ensuring that text content across items of different heights or font sizes sits on the same invisible horizontal line.

**When to use it:**

- Items have differing font sizes but should appear text-aligned
- Mixed content (icons + text, large heading + small label) needs visual baseline coherence
- You only want baseline alignment on `sm`+ screens, stacking vertically on `xs`

**Example**: 

```html
<!-- Baseline alignment activates at sm (≥576px) -->
<div class="d-flex align-items-sm-baseline">
  <div class="p-2" style="font-size: 2.5rem;">Big</div>
  <div class="p-2">Normal</div>
  <div class="p-2" style="font-size: 0.75rem;">Small</div>
</div>
```

**Comparison of `align-items` values:**

| Class | CSS value | Effect |
|---|---|---|
| `.align-items-sm-start` | `flex-start` | Top-align all items |
| `.align-items-sm-center` | `center` | Vertically center all items |
| `.align-items-sm-end` | `flex-end` | Bottom-align all items |
| `.align-items-sm-baseline` | `baseline` | Align all items on text baseline |
| `.align-items-sm-stretch` | `stretch` | Stretch all items to full height |

The class name and behavior are identical in Bootstrap 4 and 5 — Bootstrap 5 did not change flex utility naming, only data attributes (`data-bs-*`) and the jQuery dependency.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Can Tabs be centered in Bootstrap?

Yes. Add `.justify-content-center` to the `.nav` element to center tabs.

```html
<ul class="nav nav-tabs justify-content-center">
  <li class="nav-item">
    <a class="nav-link active" href="#">Home</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Profile</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="#">Contact</a>
  </li>
</ul>
```

Use `.nav-fill` to have each tab take an equal proportional width, or `.nav-justified` to fill the full width evenly.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Grid Structure in Bootstrap

The Bootstrap grid is built with three components:

1. **Container** (`.container` / `.container-fluid`) — wraps rows and provides horizontal padding.
2. **Row** (`.row`) — a horizontal group of columns; uses negative margins to compensate for column gutters.
3. **Column** (`.col-*`) — defines content width; columns within a row should sum to 12.

```html
<div class="container">
  <div class="row">
    <div class="col-sm-8">Main Content</div>
    <div class="col-sm-4">Sidebar</div>
  </div>
</div>
```

Breakpoints: `xs` (<576px), `sm` (≥576px), `md` (≥768px), `lg` (≥992px), `xl` (≥1200px).

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Why Offset Columns introduced in Bootstrap

Offset columns create empty space to the left of a column, useful for centering content or creating asymmetric layouts without adding empty HTML elements.

```html
<div class="container">
  <!-- Centered: 4 columns wide, offset by 4 -->
  <div class="row">
    <div class="col-md-4 offset-md-4">Centered column</div>
  </div>
  <!-- Asymmetric gap between two columns -->
  <div class="row">
    <div class="col-md-3 offset-md-3">Column A</div>
    <div class="col-md-3">Column B</div>
  </div>
</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Column Ordering in Bootstrap?

Bootstrap 4 uses `.order-*` classes to reorder columns visually. Responsive variants (`.order-{breakpoint}-*`) allow different ordering at different screen sizes.

```html
<div class="container">
  <div class="row">
    <div class="col order-2">First in DOM, second visually</div>
    <div class="col order-1">Second in DOM, first visually</div>
  </div>
</div>
```

Responsive ordering:

```html
<div class="col order-md-1 order-2">Reorders at md breakpoint</div>
```

In Bootstrap 3, use `.col-md-push-*` and `.col-md-pull-*` instead.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Define Bootstrap Panels

**Note:** Panels were removed in Bootstrap 4 and replaced by Cards.

In Bootstrap 3, a panel is a bordered box with padding used to group related content.

```html
<!-- Bootstrap 3 -->
<div class="panel panel-default">
  <div class="panel-heading">Panel Heading</div>
  <div class="panel-body">Panel content goes here.</div>
  <div class="panel-footer">Panel Footer</div>
</div>
```

In Bootstrap 4+, use the Card component instead:

```html
<div class="card">
  <div class="card-header">Card Header</div>
  <div class="card-body">Card content.</div>
  <div class="card-footer">Card Footer</div>
</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is a Bootstrap Well?

**Note:** Wells were removed in Bootstrap 4.

In Bootstrap 3, a well creates an inset visual effect around content by wrapping it with the `.well` class.

```html
<!-- Bootstrap 3 -->
<div class="well">Content inside a well appears sunken.</div>
<div class="well well-lg">Large well</div>
<div class="well well-sm">Small well</div>
```

In Bootstrap 4+, achieve the same effect with utility classes:

```html
<div class="bg-light rounded p-3 border">Equivalent in Bootstrap 4</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Create Inline form in Bootstrap

An inline form displays all form elements on a single line. Add `.form-inline` to the `<form>` element. Inline forms only apply on viewports ≥576px; they stack vertically on smaller screens.

```html
<form class="form-inline">
  <div class="form-group mb-2 mr-sm-2">
    <label for="inputEmail" class="sr-only">Email</label>
    <input type="email" class="form-control" id="inputEmail" placeholder="Email">
  </div>
  <div class="form-group mb-2 mr-sm-2">
    <label for="inputPassword" class="sr-only">Password</label>
    <input type="password" class="form-control" id="inputPassword" placeholder="Password">
  </div>
  <button type="submit" class="btn btn-primary mb-2">Sign in</button>
</form>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Pagination in Bootstrap?

Bootstrap provides a styled pagination component using a `<ul>` with `.pagination`. Use `.page-item` for list items and `.page-link` for links. Add `.active` or `.disabled` to indicate state.

```html
<nav aria-label="Page navigation">
  <ul class="pagination">
    <li class="page-item disabled">
      <a class="page-link" href="#" tabindex="-1">Previous</a>
    </li>
    <li class="page-item active"><a class="page-link" href="#">1</a></li>
    <li class="page-item"><a class="page-link" href="#">2</a></li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
    <li class="page-item">
      <a class="page-link" href="#">Next</a>
    </li>
  </ul>
</nav>
```

Sizing: `.pagination-lg` or `.pagination-sm`. Alignment: add `.justify-content-center` or `.justify-content-end` to the `<ul>`.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Container-fluid vs Container in Bootstrap

| `.container` | `.container-fluid` |
|---|---|
| Fixed max-width that changes at each breakpoint | Always 100% wide |
| Centers content with auto left/right margins | Spans the full viewport width |
| Suitable for fixed-width page layouts | Suitable for full-width layouts |
| Widths: 540 / 720 / 960 / 1140px at sm/md/lg/xl | Always 100% regardless of breakpoint |

```html
<div class="container">Fixed width</div>
<div class="container-fluid">Full width</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is a card in Bootstrap?

Cards are a flexible content container introduced in Bootstrap 4 to replace panels, wells, and thumbnails. They support headers, footers, images, and overlay content.

```html
<div class="card" style="width: 18rem;">
  <img src="image.jpg" class="card-img-top" alt="Card image">
  <div class="card-body">
    <h5 class="card-title">Card Title</h5>
    <p class="card-text">Some quick example text.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
  <div class="card-footer text-muted">Footer</div>
</div>
```

Card layout helpers: `.card-group`, `.card-deck`, `.card-columns`.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Why the d-sm-flex class used in Bootstrap 5?

`.d-sm-flex` sets `display: flex` on an element at the `sm` breakpoint (≥576px) and above. Below `sm` the element retains its default block display, causing children to stack vertically on mobile and lay out side-by-side on larger screens — without writing any custom media queries.

**Why it is useful:**

- **Mobile-first responsive layouts**: stack children on `xs`, place them side-by-side from `sm` upward
- **Avoids custom CSS**: no need to write `@media (min-width: 576px) { display: flex; }`
- **Composable with other flex utilities**: combine freely with `align-items-*`, `justify-content-*`, `gap-*`, etc.

**Example**:

```html
<!-- Block on xs, flex from sm (≥576px) upward -->
<div class="d-sm-flex align-items-center gap-3">
  <img src="avatar.jpg" alt="Avatar" width="64">
  <div>
    <h5 class="mb-0">Jane Doe</h5>
    <small class="text-muted">Developer</small>
  </div>
</div>

<!-- Flex only in a specific range: flex on sm, hidden on lg+ -->
<div class="d-sm-flex d-lg-none">
  <span>Visible as flex on sm–md only</span>
</div>
```

**Full display utility pattern:**

| Class | Breakpoint | CSS applied |
|---|---|---|
| `.d-flex` | all sizes | `display: flex` |
| `.d-sm-flex` | ≥576px | `display: flex` |
| `.d-md-flex` | ≥768px | `display: flex` |
| `.d-lg-flex` | ≥992px | `display: flex` |
| `.d-xl-flex` | ≥1200px | `display: flex` |
| `.d-xxl-flex` | ≥1400px | `display: flex` (Bootstrap 5 only) |

The class name and behavior are identical in Bootstrap 4 and 5. Bootstrap 5 added only the `xxl` breakpoint variant (`.d-xxl-flex`) and dropped jQuery — the display utility classes themselves were unchanged.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What does a default navbar consist of?

A default Bootstrap navbar consists of:

- **Brand/Logo** (`.navbar-brand`) — site name or logo
- **Toggler** (`.navbar-toggler`) — hamburger button for mobile
- **Navigation links** (`.navbar-nav` > `.nav-item` > `.nav-link`)
- **Dropdown menus** — optional dropdowns within nav items
- **Inline forms** (`.form-inline`) — optional search bar
- **Collapse container** (`.navbar-collapse`) — wraps collapsible content

```html
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Logo</a>
  <button class="navbar-toggler" type="button"
    data-toggle="collapse" data-target="#nav">
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse" id="nav">
    <ul class="navbar-nav ml-auto">
      <li class="nav-item active"><a class="nav-link" href="#">Home</a></li>
      <li class="nav-item"><a class="nav-link" href="#">About</a></li>
    </ul>
    <form class="form-inline my-2 my-lg-0">
      <input class="form-control mr-sm-2" type="search" placeholder="Search">
      <button class="btn btn-outline-success" type="submit">Search</button>
    </form>
  </div>
</nav>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What are Carets in Bootstrap?

Carets are small downward-pointing triangles that indicate dropdown menus. In Bootstrap 4, they are added automatically via CSS `::after` pseudo-element on `.dropdown-toggle` elements.

```html
<div class="dropdown">
  <button class="btn btn-secondary dropdown-toggle" type="button"
    data-toggle="dropdown">
    Dropdown
  </button>
  <div class="dropdown-menu">
    <a class="dropdown-item" href="#">Action</a>
    <a class="dropdown-item" href="#">Another action</a>
  </div>
</div>
```

To suppress the caret, override `.dropdown-toggle::after { display: none; }`.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Align components in Bootstrap

Bootstrap 4 provides multiple alignment utilities:

**Text alignment:**
```html
<p class="text-left">Left</p>
<p class="text-center">Center</p>
<p class="text-right">Right</p>
```

**Flexbox alignment:**
```html
<div class="d-flex justify-content-center">Horizontally centered</div>
<div class="d-flex align-items-center" style="height:100px">Vertically centered</div>
<div class="d-flex justify-content-center align-items-center" style="height:100px">Both</div>
```

**Margin auto (push items apart):**
```html
<div class="d-flex">
  <div class="mr-auto">Left</div>
  <div>Right</div>
</div>
```

**Block element centering:**
```html
<div class="mx-auto" style="width: 200px;">Centered block</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. How can I add footer to panel in Bootstrap

**Bootstrap 3** — use `.panel-footer`:

```html
<div class="panel panel-default">
  <div class="panel-body">Panel content</div>
  <div class="panel-footer">Panel footer</div>
</div>
```

**Bootstrap 4+** — use `.card-footer`:

```html
<div class="card">
  <div class="card-body">Card content</div>
  <div class="card-footer text-muted">Card footer</div>
</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. Center an element in Bootstrap

**Horizontally center a block element:**
```html
<div class="mx-auto" style="width: 200px;">Centered block</div>
```

**Center text:**
```html
<p class="text-center">Centered text</p>
```

**Center with flexbox:**
```html
<div class="d-flex justify-content-center">
  <div>Horizontally centered item</div>
</div>
```

**Center both horizontally and vertically:**
```html
<div class="d-flex justify-content-center align-items-center" style="height: 200px;">
  <div>Fully centered</div>
</div>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. How do we add outline to Buttons in Bootstrap?

Bootstrap provides outline button variants using `.btn-outline-*` classes. These remove the background and show only a colored border, which fills on hover/focus.

```html
<button type="button" class="btn btn-outline-primary">Primary</button>
<button type="button" class="btn btn-outline-secondary">Secondary</button>
<button type="button" class="btn btn-outline-success">Success</button>
<button type="button" class="btn btn-outline-danger">Danger</button>
<button type="button" class="btn btn-outline-warning">Warning</button>
<button type="button" class="btn btn-outline-info">Info</button>
<button type="button" class="btn btn-outline-dark">Dark</button>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. How to create a responsive navbar in Bootstrap?

A responsive navbar uses `.navbar-expand-{breakpoint}` to collapse below the specified breakpoint and expand above it.

```html
<nav class="navbar navbar-expand-md navbar-dark bg-dark">
  <a class="navbar-brand" href="#">MySite</a>

  <button class="navbar-toggler" type="button"
    data-toggle="collapse" data-target="#mainNav"
    aria-controls="mainNav" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="mainNav">
    <ul class="navbar-nav ml-auto">
      <li class="nav-item active">
        <a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">About</a>
      </li>
      <li class="nav-item dropdown">
        <a class="nav-link dropdown-toggle" href="#"
          id="navDropdown" role="button" data-toggle="dropdown">
          Services
        </a>
        <div class="dropdown-menu dropdown-menu-right">
          <a class="dropdown-item" href="#">Web Design</a>
          <a class="dropdown-item" href="#">Development</a>
        </div>
      </li>
    </ul>
  </div>
</nav>
```

`.navbar-expand-md` collapses below 768px and expands at md and above. `.ml-auto` pushes nav links to the right.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. How to create striped table with Bootstrap?

Add `.table-striped` to a `<table>` that already has `.table` to apply alternating row shading using CSS zebra-striping.

```html
<table class="table table-striped">
  <thead class="thead-dark">
    <tr>
      <th>#</th>
      <th>Name</th>
      <th>Email</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td><td>Alice</td><td>alice@example.com</td>
    </tr>
    <tr>
      <td>2</td><td>Bob</td><td>bob@example.com</td>
    </tr>
    <tr>
      <td>3</td><td>Carol</td><td>carol@example.com</td>
    </tr>
  </tbody>
</table>
```

Combine with `.table-hover` for hover states and `.table-bordered` for borders on all cells.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. How to create Navbar in Bootstrap?

```html
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <!-- Brand -->
  <a class="navbar-brand" href="#">Brand</a>

  <!-- Mobile toggle -->
  <button class="navbar-toggler" type="button"
    data-toggle="collapse" data-target="#navContent"
    aria-controls="navContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <!-- Collapsible content -->
  <div class="collapse navbar-collapse" id="navContent">
    <ul class="navbar-nav mr-auto">
      <li class="nav-item active">
        <a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>
      <li class="nav-item dropdown">
        <a class="nav-link dropdown-toggle" href="#"
          id="navbarDropdown" role="button" data-toggle="dropdown">
          Dropdown
        </a>
        <div class="dropdown-menu" aria-labelledby="navbarDropdown">
          <a class="dropdown-item" href="#">Item 1</a>
          <div class="dropdown-divider"></div>
          <a class="dropdown-item" href="#">Item 2</a>
        </div>
      </li>
    </ul>
  </div>
</nav>
```

Key steps:
1. Use `<nav>` with `.navbar` and `.navbar-expand-{breakpoint}`.
2. Add brand link with `.navbar-brand`.
3. Add a toggler button pointing to the collapse container via `data-target`.
4. Wrap nav items in `.collapse.navbar-collapse`.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is the Offcanvas component in Bootstrap 5?

Offcanvas is a sidebar/drawer component introduced in Bootstrap 5. It slides in from any edge of the viewport (start, end, top, bottom) and is used for navigation menus, filter panels, or any hidden-until-needed content.

```html
<!-- Trigger button -->
<button class="btn btn-primary" type="button"
  data-bs-toggle="offcanvas" data-bs-target="#offcanvasDemo"
  aria-controls="offcanvasDemo">
  Open Offcanvas
</button>

<!-- Offcanvas panel -->
<div class="offcanvas offcanvas-start" tabindex="-1" id="offcanvasDemo"
  aria-labelledby="offcanvasDemoLabel">
  <div class="offcanvas-header">
    <h5 class="offcanvas-title" id="offcanvasDemoLabel">Menu</h5>
    <button type="button" class="btn-close" data-bs-dismiss="offcanvas"
      aria-label="Close"></button>
  </div>
  <div class="offcanvas-body">
    <ul class="list-group list-group-flush">
      <li class="list-group-item"><a href="#">Home</a></li>
      <li class="list-group-item"><a href="#">About</a></li>
      <li class="list-group-item"><a href="#">Contact</a></li>
    </ul>
  </div>
</div>
```

**Placement classes:** `.offcanvas-start` (left), `.offcanvas-end` (right), `.offcanvas-top`, `.offcanvas-bottom`.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is the Accordion component in Bootstrap 5?

Bootstrap 5 introduced a dedicated `.accordion` component to replace the Bootstrap 4 pattern of using collapse with `data-parent`. It groups collapsible items, automatically closing the open one when another is opened.

```html
<div class="accordion" id="faqAccordion">

  <div class="accordion-item">
    <h2 class="accordion-header" id="headingOne">
      <button class="accordion-button" type="button"
        data-bs-toggle="collapse" data-bs-target="#collapseOne"
        aria-expanded="true" aria-controls="collapseOne">
        Question 1
      </button>
    </h2>
    <div id="collapseOne" class="accordion-collapse collapse show"
      aria-labelledby="headingOne" data-bs-parent="#faqAccordion">
      <div class="accordion-body">Answer to question 1.</div>
    </div>
  </div>

  <div class="accordion-item">
    <h2 class="accordion-header" id="headingTwo">
      <button class="accordion-button collapsed" type="button"
        data-bs-toggle="collapse" data-bs-target="#collapseTwo"
        aria-expanded="false" aria-controls="collapseTwo">
        Question 2
      </button>
    </h2>
    <div id="collapseTwo" class="accordion-collapse collapse"
      aria-labelledby="headingTwo" data-bs-parent="#faqAccordion">
      <div class="accordion-body">Answer to question 2.</div>
    </div>
  </div>

</div>
```

Add `.accordion-flush` to remove borders and rounded corners for edge-to-edge styling inside a parent container.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What are Floating Labels in Bootstrap 5?

Floating labels are a new form pattern in Bootstrap 5 where the label floats above the input when the field is focused or filled. Wrap the `<input>` and `<label>` in a `.form-floating` container — the label must come **after** the input.

```html
<div class="form-floating mb-3">
  <input type="email" class="form-control" id="floatingEmail"
    placeholder="name@example.com">
  <label for="floatingEmail">Email address</label>
</div>

<div class="form-floating mb-3">
  <input type="password" class="form-control" id="floatingPassword"
    placeholder="Password">
  <label for="floatingPassword">Password</label>
</div>

<div class="form-floating">
  <select class="form-select" id="floatingSelect">
    <option selected>Open this select menu</option>
    <option value="1">One</option>
    <option value="2">Two</option>
  </select>
  <label for="floatingSelect">Works with selects</label>
</div>
```

**Note:** The `placeholder` attribute on the input is required (though visually hidden) for the floating label CSS to work correctly.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is the Bootstrap 5 Utility API?

The Utility API is a Sass-based system in Bootstrap 5 that lets you generate, modify, or extend utility classes without writing raw CSS. It is defined in `_utilities.scss` and consumed by `_utility-api.scss`.

```scss
// Add a custom utility via the API in your own Sass
@import "bootstrap/scss/bootstrap";

$utilities: map-merge(
  $utilities,
  (
    "cursor": (
      property: cursor,
      class: cursor,
      responsive: true,
      values: auto pointer grab,
    )
  )
);
```

This generates `.cursor-auto`, `.cursor-pointer`, `.cursor-grab` (and responsive variants) automatically.

**Key map keys available:**

| Key | Purpose |
|---|---|
| `property` | CSS property name |
| `class` | Generated class name prefix |
| `values` | List or map of values |
| `responsive` | Generate breakpoint variants |
| `print` | Generate print variants |
| `state` | Generate hover/focus variants |

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What are gutter utilities in Bootstrap 5?

Bootstrap 5 replaced the old column-padding approach with dedicated gutter utility classes on the `.row` element. Gutters control the spacing between columns.

| Class | Axis |
|---|---|
| `.g-{size}` | Both horizontal and vertical gutters |
| `.gx-{size}` | Horizontal (column) gutters only |
| `.gy-{size}` | Vertical (row) gutters only |

Sizes follow the spacing scale: `0`, `1`, `2`, `3`, `4`, `5` (and optionally custom values via Sass).

```html
<!-- No gutters -->
<div class="row g-0">
  <div class="col-6">No gutter left column</div>
  <div class="col-6">No gutter right column</div>
</div>

<!-- Horizontal gutter only -->
<div class="row gx-5">
  <div class="col">Wide horizontal gap</div>
  <div class="col">Wide horizontal gap</div>
</div>

<!-- Both axes -->
<div class="row g-3">
  <div class="col-6">Card 1</div>
  <div class="col-6">Card 2</div>
  <div class="col-6">Card 3</div>
  <div class="col-6">Card 4</div>
</div>
```

Gutters are responsive: `.g-md-4`, `.gx-lg-3`, etc.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What changed with data attributes in Bootstrap 5?

Bootstrap 5 renamed all `data-*` attributes to `data-bs-*` to avoid conflicts with third-party libraries and custom code.

| Bootstrap 4 | Bootstrap 5 |
|---|---|
| `data-toggle="modal"` | `data-bs-toggle="modal"` |
| `data-target="#id"` | `data-bs-target="#id"` |
| `data-dismiss="modal"` | `data-bs-dismiss="modal"` |
| `data-toggle="tooltip"` | `data-bs-toggle="tooltip"` |
| `data-toggle="collapse"` | `data-bs-toggle="collapse"` |
| `data-ride="carousel"` | `data-bs-ride="carousel"` |
| `data-slide="next"` | `data-bs-slide="next"` |

```html
<!-- Bootstrap 4 -->
<button data-toggle="modal" data-target="#myModal">Open</button>

<!-- Bootstrap 5 -->
<button data-bs-toggle="modal" data-bs-target="#myModal">Open</button>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What are Stacks in Bootstrap 5?

Stacks are shorthand helper classes introduced in Bootstrap 5.1 for quickly building common flex layouts. They wrap Flexbox utilities into single, semantic class names.

- **`.vstack`** — vertical stack (`flex-column`); items are full-width and stacked top to bottom.
- **`.hstack`** — horizontal stack (`flex-row` + `align-items-center`); items are side-by-side and vertically centered.

```html
<!-- Vertical stack with gap -->
<div class="vstack gap-3">
  <div class="bg-light border p-2">First</div>
  <div class="bg-light border p-2">Second</div>
  <div class="bg-light border p-2">Third</div>
</div>

<!-- Horizontal stack with divider and auto-margin push -->
<div class="hstack gap-3">
  <div class="bg-light border p-2">Left item</div>
  <div class="vr"></div>
  <div class="bg-light border p-2 ms-auto">Right item</div>
</div>
```

`.vr` renders a vertical rule (divider line) between horizontal stack items.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is the `.ratio` helper in Bootstrap 5?

The `.ratio` helper creates responsive aspect-ratio boxes without `padding-top` hacks. Child elements automatically fill the container. It uses the CSS `aspect-ratio` property internally via a pseudo-element.

```html
<!-- 16:9 video embed -->
<div class="ratio ratio-16x9">
  <iframe src="https://www.youtube.com/embed/..." allowfullscreen></iframe>
</div>

<!-- 4:3 ratio -->
<div class="ratio ratio-4x3">
  <iframe src="..."></iframe>
</div>

<!-- Custom ratio via CSS variable -->
<div class="ratio" style="--bs-aspect-ratio: 50%;">
  <!-- 2:1 ratio (50% = 1/2) -->
  <iframe src="..."></iframe>
</div>
```

**Built-in ratio classes:**

| Class | Ratio |
|---|---|
| `.ratio-1x1` | 1:1 (square) |
| `.ratio-4x3` | 4:3 |
| `.ratio-16x9` | 16:9 (widescreen) |
| `.ratio-21x9` | 21:9 (ultrawide) |

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What are Spinners in Bootstrap 5?

Spinners are loading indicators built entirely with CSS and HTML — no JavaScript required. Bootstrap 5 provides two types: border spinner and growing spinner.

```html
<!-- Border spinner (default) -->
<div class="spinner-border" role="status">
  <span class="visually-hidden">Loading...</span>
</div>

<!-- Growing spinner -->
<div class="spinner-grow" role="status">
  <span class="visually-hidden">Loading...</span>
</div>

<!-- Colored spinners using text utilities -->
<div class="spinner-border text-primary" role="status"></div>
<div class="spinner-border text-success" role="status"></div>
<div class="spinner-border text-danger" role="status"></div>

<!-- Sizing -->
<div class="spinner-border spinner-border-sm" role="status"></div>

<!-- Button with spinner -->
<button class="btn btn-primary" type="button" disabled>
  <span class="spinner-border spinner-border-sm me-1" role="status"></span>
  Loading...
</button>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What are Toast notifications in Bootstrap 5?

Toasts are lightweight push notifications that appear in a corner of the screen. They require JavaScript initialization and are opt-in (not shown automatically).

```html
<!-- Toast HTML -->
<div class="toast-container position-fixed bottom-0 end-0 p-3">
  <div id="liveToast" class="toast" role="alert" aria-live="assertive"
    aria-atomic="true">
    <div class="toast-header">
      <strong class="me-auto">Bootstrap</strong>
      <small>Just now</small>
      <button type="button" class="btn-close" data-bs-dismiss="toast"
        aria-label="Close"></button>
    </div>
    <div class="toast-body">Hello! This is a toast message.</div>
  </div>
</div>

<!-- JavaScript trigger -->
<script>
  const toastEl = document.getElementById('liveToast');
  const toast = new bootstrap.Toast(toastEl);
  toast.show();
</script>
```

**Key options:** `autohide` (default `true`), `delay` (default 5000ms). Use `.toast-container` with position utilities to place groups of toasts.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What are Placeholders in Bootstrap 5?

Placeholders (skeleton screens) are a new Bootstrap 5 component that shows animated loading blocks in place of real content while data is fetching. They improve perceived performance.

```html
<div class="card">
  <div class="card-body">
    <h5 class="card-title placeholder-glow">
      <span class="placeholder col-6"></span>
    </h5>
    <p class="card-text placeholder-glow">
      <span class="placeholder col-7"></span>
      <span class="placeholder col-4"></span>
      <span class="placeholder col-4"></span>
      <span class="placeholder col-6"></span>
    </p>
    <a href="#" class="btn btn-primary disabled placeholder col-4"
      aria-disabled="true"></a>
  </div>
</div>
```

**Animation classes:**

| Class | Effect |
|---|---|
| `.placeholder-glow` | Fading glow animation |
| `.placeholder-wave` | Left-to-right wave animation |

**Width:** control with `.col-*` grid classes (e.g. `.col-6` = 50% width).

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is the `row-cols-*` class in Bootstrap 5?

`row-cols-*` classes set the number of equal-width columns per row directly on the `.row` element, without needing to add column classes to each child.

```html
<!-- Always 2 columns per row -->
<div class="row row-cols-2">
  <div class="col">Item 1</div>
  <div class="col">Item 2</div>
  <div class="col">Item 3</div>
  <div class="col">Item 4</div>
</div>

<!-- 1 column on xs, 2 on sm, 3 on md, 4 on lg -->
<div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-4">
  <div class="col"><div class="card">Card 1</div></div>
  <div class="col"><div class="card">Card 2</div></div>
  <div class="col"><div class="card">Card 3</div></div>
  <div class="col"><div class="card">Card 4</div></div>
</div>
```

This is particularly useful for card grids where each item should have the same width and the number of items per row should change at breakpoints.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What are CSS custom properties (variables) in Bootstrap 5?

Bootstrap 5 significantly expanded its use of CSS custom properties (CSS variables), making it easier to theme components without recompiling Sass.

```css
/* Bootstrap 5 root variables (excerpt) */
:root {
  --bs-blue: #0d6efd;
  --bs-font-sans-serif: system-ui, -apple-system, "Segoe UI", Roboto, sans-serif;
  --bs-body-font-size: 1rem;
  --bs-body-line-height: 1.5;
  --bs-body-color: #212529;
  --bs-body-bg: #fff;
  --bs-border-radius: 0.375rem;
}
```

You can override them locally per-component or globally:

```css
/* Override for a specific section */
.my-section {
  --bs-body-bg: #f8f9fa;
  --bs-body-color: #343a40;
}

/* Change primary button color without Sass */
.btn-primary {
  --bs-btn-bg: #6f42c1;
  --bs-btn-border-color: #6f42c1;
}
```

**Advantage over Bootstrap 4:** No Sass recompile needed for simple theming — variables can be changed at runtime with JavaScript.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What are the `gap-*` utilities in Bootstrap 5?

The `gap-*` utilities apply CSS `gap` to flex and grid containers, setting spacing between items without needing margin utilities on each child.

```html
<!-- Flex with gap -->
<div class="d-flex gap-3">
  <div class="p-2 bg-light border">Item 1</div>
  <div class="p-2 bg-light border">Item 2</div>
  <div class="p-2 bg-light border">Item 3</div>
</div>

<!-- Column gap only -->
<div class="d-flex column-gap-4">
  <div class="p-2 bg-light border">Item A</div>
  <div class="p-2 bg-light border">Item B</div>
</div>

<!-- Row gap only (useful in wrapping flex containers) -->
<div class="d-flex flex-wrap row-gap-2">
  <div class="p-2 bg-light border">Item 1</div>
  <div class="p-2 bg-light border">Item 2</div>
  <div class="p-2 bg-light border">Item 3</div>
</div>
```

`gap-*` values follow the spacing scale (`0`–`5`). Responsive variants are supported: `.gap-md-3`, `.column-gap-lg-4`.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What are background and text opacity utilities in Bootstrap 5?

Bootstrap 5 added `bg-opacity-*` and `text-opacity-*` utilities that control the alpha transparency of background and text colors using CSS variables — without requiring custom CSS.

```html
<!-- Background with opacity -->
<div class="bg-primary bg-opacity-100 p-3 text-white">100% opacity</div>
<div class="bg-primary bg-opacity-75 p-3 text-white">75% opacity</div>
<div class="bg-primary bg-opacity-50 p-3">50% opacity</div>
<div class="bg-primary bg-opacity-25 p-3">25% opacity</div>
<div class="bg-primary bg-opacity-10 p-3">10% opacity</div>

<!-- Text with opacity -->
<p class="text-primary text-opacity-100">Full opacity text</p>
<p class="text-primary text-opacity-75">75% opacity text</p>
<p class="text-primary text-opacity-50">50% opacity text</p>
<p class="text-primary text-opacity-25">25% opacity text</p>
```

These utilities change the opacity of the color only — they do not affect the element\'s overall `opacity` property, so child content is not affected.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is the `flex-fill` class in Bootstrap 5?

`.flex-fill` forces a flex item to fill all available free space along the main axis by applying `flex: 1 1 auto`. When multiple siblings have `.flex-fill`, they share the remaining space equally.

```html
<!-- All items share space equally -->
<div class="d-flex">
  <div class="flex-fill p-2 bg-primary text-white">Item 1</div>
  <div class="flex-fill p-2 bg-secondary text-white">Item 2</div>
  <div class="flex-fill p-2 bg-success text-white">Item 3</div>
</div>

<!-- Only center item fills; others use natural width -->
<div class="d-flex">
  <div class="p-2 bg-light border">Fixed left</div>
  <div class="flex-fill p-2 bg-info text-white">Fills remaining space</div>
  <div class="p-2 bg-light border">Fixed right</div>
</div>
```

Responsive variants: `.flex-sm-fill`, `.flex-md-fill`, `.flex-lg-fill`, `.flex-xl-fill`, `.flex-xxl-fill`.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is RTL support in Bootstrap 5?

Bootstrap 5 ships with separate RTL (right-to-left) CSS builds for languages such as Arabic, Hebrew, and Persian. RTL flips directional styles (margins, paddings, text alignment, flex direction) automatically.

**How to enable:**

1. Link the RTL stylesheet instead of the default one:
```html
<link rel="stylesheet"
  href="https://cdn.jsdelivr.net/npm/bootstrap@5/dist/css/bootstrap.rtl.min.css">
```

2. Add `dir="rtl"` and the appropriate `lang` to `<html>`:
```html
<html lang="ar" dir="rtl">
```

**Logical properties used internally:**

| LTR (Bootstrap 4) | RTL-aware (Bootstrap 5) |
|---|---|
| `margin-left` | `margin-start` (`.ms-*`) |
| `margin-right` | `margin-end` (`.me-*`) |
| `padding-left` | `padding-start` (`.ps-*`) |
| `text-align: left` | `text-start` |
| `float: left` | `float-start` |

Bootstrap 5 replaced all directional utility suffixes (`-left`/`-right`) with `-start`/`-end` so the same HTML works in both LTR and RTL.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is the `xxl` breakpoint in Bootstrap 5?

Bootstrap 5 added a sixth responsive breakpoint, `xxl`, at a minimum width of **1400px**. Bootstrap 4 only had five breakpoints.

**Full breakpoint table (Bootstrap 5):**

| Breakpoint | Class infix | Min width |
|---|---|---|
| Extra small | *(none)* | <576px |
| Small | `sm` | ≥576px |
| Medium | `md` | ≥768px |
| Large | `lg` | ≥992px |
| Extra large | `xl` | ≥1200px |
| Extra extra large | `xxl` | ≥1400px |

**Usage examples:**

```html
<!-- Column that is 4-wide only on xxl screens -->
<div class="col-12 col-xxl-4">Content</div>

<!-- Container that becomes fixed at xxl -->
<div class="container-xxl">Content</div>

<!-- Display flex only on xxl+ -->
<div class="d-xxl-flex">...</div>

<!-- Navbar that collapses below xxl -->
<nav class="navbar navbar-expand-xxl">...</nav>
```

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is a Bootstrap 5 Modal and how to initialize it without jQuery?

A modal is a dialog box overlaid on the current page. Bootstrap 5 rewrote the Modal plugin in vanilla JavaScript — no jQuery required.

```html
<!-- Trigger -->
<button type="button" class="btn btn-primary"
  data-bs-toggle="modal" data-bs-target="#exampleModal">
  Open Modal
</button>

<!-- Modal -->
<div class="modal fade" id="exampleModal" tabindex="-1"
  aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
        <button type="button" class="btn-close"
          data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        Modal body content goes here.
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary"
          data-bs-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Save changes</button>
      </div>
    </div>
  </div>
</div>

<!-- JavaScript initialization (no jQuery) -->
<script>
  // Programmatic open
  const modal = new bootstrap.Modal(document.getElementById('exampleModal'));
  modal.show();
</script>
```

Modal size variants: `.modal-sm`, `.modal-lg`, `.modal-xl`, `.modal-fullscreen`.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What are the `position-*` utilities added/updated in Bootstrap 5?

Bootstrap 5 added new position utilities for vertical and horizontal centering and for controlling coordinate values.

**Position type classes:** `.position-static`, `.position-relative`, `.position-absolute`, `.position-fixed`, `.position-sticky`.

**Edge positioning classes (Bootstrap 5+):**
```html
<div class="position-relative" style="height: 200px; background: #eee;">

  <!-- Top-left corner -->
  <span class="position-absolute top-0 start-0">Top Left</span>

  <!-- Top-right corner -->
  <span class="position-absolute top-0 end-0">Top Right</span>

  <!-- Center -->
  <span class="position-absolute top-50 start-50 translate-middle">
    Centered
  </span>

  <!-- Bottom-center -->
  <span class="position-absolute bottom-0 start-50 translate-middle-x">
    Bottom Center
  </span>

</div>
```

**Available value classes:** `top-0`, `top-50`, `top-100`, `bottom-0`, `bottom-50`, `bottom-100`, `start-0`, `start-50`, `start-100`, `end-0`, `end-50`, `end-100`.

**Translation helpers:** `.translate-middle` (both axes), `.translate-middle-x` (horizontal only), `.translate-middle-y` (vertical only).

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is the `visually-hidden` class in Bootstrap 5?

Bootstrap 5 replaced the old `.sr-only` and `.sr-only-focusable` classes with `.visually-hidden` and `.visually-hidden-focusable`. These hide content visually but keep it accessible to screen readers.

```html
<!-- Visually hidden label (screen reader only) -->
<label class="visually-hidden" for="searchInput">Search</label>
<input id="searchInput" type="search" class="form-control" placeholder="Search">

<!-- Hidden text inside a button (icon button) -->
<button type="button" class="btn btn-close">
  <span class="visually-hidden">Close</span>
</button>

<!-- Focusable: visible when focused (e.g. skip-to-main link) -->
<a class="visually-hidden-focusable" href="#main-content">Skip to main content</a>
```

**Why the rename?** `.sr-only` implied "screen-reader only" but the technique also benefits keyboard-only users and search engines. `.visually-hidden` is a more accurate description.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is the `btn-close` component in Bootstrap 5?

Bootstrap 5 introduced a standardized `.btn-close` component — a pre-styled close/dismiss button that uses an SVG `×` icon embedded via CSS, requires no icon font, and is fully accessible.

```html
<!-- Default close button -->
<button type="button" class="btn-close" aria-label="Close"></button>

<!-- White variant (for dark backgrounds) -->
<button type="button" class="btn-close btn-close-white" aria-label="Close"></button>

<!-- Disabled state -->
<button type="button" class="btn-close" disabled aria-label="Close"></button>
```

It is used automatically inside `.modal-header`, `.alert-dismissible`, `.offcanvas-header`, and `.toast-header` when you add `data-bs-dismiss`.

**Bootstrap 4 equivalent:** Manually placed `&times;` characters inside `<button>` tags.

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>

## Q. What is Color Mode (dark mode) support in Bootstrap 5.3?

Bootstrap 5.3 introduced built-in color mode support, including a dark mode, via the `data-bs-theme` attribute. No custom CSS is required.

```html
<!-- Enable dark mode for the entire page -->
<html data-bs-theme="dark">

<!-- Enable dark mode for a specific component only -->
<div data-bs-theme="dark">
  <div class="card">
    <div class="card-body">This card uses dark theme.</div>
  </div>
</div>

<!-- Light mode (explicit) -->
<div data-bs-theme="light">
  <nav class="navbar navbar-expand-lg bg-body-tertiary">...</nav>
</div>
```

**Toggle dark mode with JavaScript:**

```javascript
// Switch the page to dark mode
document.documentElement.setAttribute('data-bs-theme', 'dark');

// Switch back to light
document.documentElement.setAttribute('data-bs-theme', 'light');
```

**New semantic color utilities in 5.3:**

| Utility | Description |
|---|---|
| `bg-body` | Adapts to current color mode |
| `bg-body-secondary` | Slightly off-body background |
| `text-body` | Adapts body text color |
| `text-body-emphasis` | Higher contrast text |
| `border-secondary-subtle` | Subtle border color |

<div align="right">
    <b><a href="#table-of-contents">↥ back to top</a></b>
</div>
