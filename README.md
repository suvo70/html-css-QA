# html-css-QA
html & css interview question and answer with in depth code and structure

## HTML

## CSS
- [CSS box model](#CSS-box-model)
- [What is Flexbox](#What-is-Flexbox)
- [What is a Media Query?](#What-is-a-Media-Query)
- [What is the Viewport?](#What-is-the-Viewport)



## CSS-box-model

The **CSS box model** is a fundamental concept that describes how elements are structured and spaced on a web page. Every HTML element is considered a **box** composed of four parts (from the inside out):

1. **Content** – The actual content like text, image, etc.
2. **Padding** – Space between the content and the border.
3. **Border** – The border surrounding the padding and content.
4. **Margin** – Space outside the border, separating it from other elements.

---

### 🔹 Visual Representation:

```
+-----------------------------+
|         Margin             |
|  +----------------------+  |
|  |       Border         |  |
|  |  +---------------+   |  |
|  |  |   Padding     |   |  |
|  |  | +----------+  |   |  |
|  |  | | Content  |  |   |  |
|  |  | +----------+  |   |  |
|  |  +---------------+   |  |
|  +----------------------+  |
+-----------------------------+
```

---

### 🔸 CSS Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Box Model Example</title>
  <style>
    .box {
      width: 200px;             /* Content width */
      padding: 20px;            /* Space inside the box */
      border: 5px solid blue;   /* Border around the padding */
      margin: 30px;             /* Space outside the box */
      background-color: lightyellow;
    }
  </style>
</head>
<body>
  <div class="box">
    This is a box model example.
  </div>
</body>
</html>
```

---

### 🔍 Breakdown of the `.box` dimensions:

- `width`: 200px (content)
- `padding`: 20px on all sides
- `border`: 5px on all sides
- `margin`: 30px on all sides

➡️ **Total width of the element =** `200 + (2×20 padding) + (2×5 border) = 250px`  
➡️ **Total height** would similarly include the content height + paddings + borders.

---

## What is Flexbox

**Flexbox** (Flexible Box Layout) is a CSS layout model designed to arrange items **along a single axis** (either row or column). It’s perfect for aligning, distributing space, and making layouts responsive **without float or positioning hacks**.

---

## 🔸 Key Concepts

### 1. **Flex Container** – The parent element
You apply `display: flex` to the container.  
It enables **flex context** for its children.

### 2. **Flex Items** – The direct children of the flex container  
These are laid out in either a row or column, and can be aligned, spaced, and wrapped flexibly.

---

## 🔧 Example CSS + HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Flexbox Example</title>
  <style>
    .flex-container {
      display: flex;
      flex-direction: row;      /* Main axis is horizontal */
      justify-content: space-between; /* Distribute items evenly */
      align-items: center;      /* Center items vertically */
      height: 200px;
      background-color: #f0f0f0;
      padding: 20px;
      border: 2px solid #ccc;
    }

    .flex-item {
      background-color: #4CAF50;
      color: white;
      padding: 20px;
      margin: 10px;
      font-size: 1.2rem;
      border-radius: 8px;
      flex: 1; /* Each item takes equal space */
      text-align: center;
    }
  </style>
</head>
<body>

  <div class="flex-container">
    <div class="flex-item">Item 1</div>
    <div class="flex-item">Item 2</div>
    <div class="flex-item">Item 3</div>
  </div>

</body>
</html>
```

---

### 🧠 What’s Happening Here?

- `display: flex` — turns the container into a flexbox.
- `flex-direction: row` — lays out the items left to right.
- `justify-content: space-between` — even spacing between items.
- `align-items: center` — vertically centers them in the container.
- `flex: 1` — all items grow equally to fill the available space.

---

### 🧭 Flexbox Cheatsheet (Common Properties)

| Property              | Description                               |
|-----------------------|-------------------------------------------|
| `flex-direction`      | `row` (default) / `column`                |
| `justify-content`     | Aligns items on **main axis**             |
| `align-items`         | Aligns items on **cross axis**            |
| `flex-wrap`           | Wraps items to next line if needed        |
| `flex-grow`, `shrink` | Controls item growth/shrink behavior      |
| `align-self`          | Overrides `align-items` for single item   |

---

Absolutely! Let's dive into **media queries**, one of the most powerful features in **CSS3** for building **responsive websites**.

---

## What is a Media Query

A **media query** lets you apply CSS **only when certain conditions are true**, such as screen width, height, resolution, orientation, or device type.

They’re essential for **responsive design**, allowing your layout to adapt across desktops, tablets, and phones.

---

## 🔸 Basic Syntax

```css
@media media-type and (condition) {
  /* CSS rules here */
}
```

- `media-type`: usually `screen`, but can also be `print`, `all`, etc.
- `condition`: like `(max-width: 768px)`, `(orientation: landscape)`

---

## 🧪 Example: Responsive Box

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Media Query Example</title>
  <style>
    .responsive-box {
      width: 100%;
      background-color: lightblue;
      padding: 20px;
      font-size: 24px;
      text-align: center;
    }

    /* Media query for screens smaller than 600px */
    @media screen and (max-width: 600px) {
      .responsive-box {
        background-color: lightcoral;
        font-size: 18px;
      }
    }
  </style>
</head>
<body>
  <div class="responsive-box">
    Resize the browser to see the effect!
  </div>
</body>
</html>
```

---

### 🔍 What This Does:

- On screens **wider than 600px**:  
  - Blue background  
  - Font size: 24px

- On screens **600px or narrower**:  
  - Coral background  
  - Font size: 18px

---

## 📱 Common Media Query Breakpoints

These are not strict rules, but popular sizes:

```css
/* Small devices (phones) */
@media (max-width: 600px) { ... }

/* Medium devices (tablets) */
@media (min-width: 601px) and (max-width: 1024px) { ... }

/* Large devices (desktops) */
@media (min-width: 1025px) { ... }
```

Great question! The **viewport** is a super important concept in CSS, especially for responsive design.

---

## What is the Viewport

The **viewport** is the **visible area of a web page** in the browser window. It's the part of the page that's currently viewable on screen **without scrolling**.

Think of it as the browser's "window" through which you see your webpage content.

---

##  Why is it Important?

The size of the viewport **varies across devices**:
- Desktop monitor → Large viewport
- Tablet → Medium viewport
- Mobile phone → Small viewport

Since screen sizes are different, you need CSS to **adapt** your content to fit the viewport correctly.

---

## 🧠 CSS Viewport Units

CSS provides special units based on the viewport size:

| Unit | Meaning                          |
|------|----------------------------------|
| `vw` | 1% of the **viewport width**     |
| `vh` | 1% of the **viewport height**    |
| `vmin` | 1% of the **smaller** of vw or vh |
| `vmax` | 1% of the **larger** of vw or vh |

---

### ✅ Example:

```css
.hero {
  width: 100vw;  /* Full width of the screen */
  height: 100vh; /* Full height of the screen */
  background-color: lightblue;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 5vw; /* Font scales with screen width */
}
```

```html
<div class="hero">
  Hello Viewport!
</div>
```

---

## 📱 Viewport Meta Tag (Very Important for Mobile)

Add this to your `<head>` for proper scaling on mobile devices:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

Without it, your mobile site may look zoomed out or broken because the browser uses a "default" desktop-sized viewport.

---

Want an example where the layout adjusts based on viewport size using media queries and `vw`/`vh` units?

---
