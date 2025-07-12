# CSS - Cascading Style Sheets

## What is CSS?

CSS (Cascading Style Sheets) is a stylesheet language used to describe the presentation and visual formatting of HTML documents. It controls how web pages look and feel by defining styles for layout, colors, fonts, spacing, positioning, and responsive design.

CSS works by selecting HTML elements and applying styling rules to them. It separates content (HTML) from presentation (CSS), making websites more maintainable and flexible.

## Key Features of CSS

- **Separation of Concerns**: Keeps content and presentation separate
- **Cascading**: Styles can inherit from parent elements and be overridden
- **Responsive Design**: Adapts layouts to different screen sizes
- **Cross-browser Compatibility**: Works across different web browsers
- **Maintainability**: Centralized styling makes updates easier

## Types of CSS

### 1. Inline CSS

Styles applied directly to HTML elements using the `style` attribute.

```html
<p style="color: blue; font-size: 16px;">This is inline CSS</p>
<div style="background-color: yellow; padding: 10px;">Inline styled div</div>
```

**Pros:**
- Quick and direct styling
- High specificity
- Useful for testing

**Cons:**
- Not reusable
- Hard to maintain
- Mixes content with presentation

### 2. Internal CSS (Embedded CSS)

Styles defined within the `<style>` tag in the HTML document's `<head>` section.

```html
<!DOCTYPE html>
<html>
<head>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
        }
        
        h1 {
            color: #333;
            text-align: center;
        }
        
        .highlight {
            background-color: yellow;
            padding: 5px;
        }
    </style>
</head>
<body>
    <h1>Welcome to My Site</h1>
    <p class="highlight">This paragraph is highlighted</p>
</body>
</html>
```

**Pros:**
- Styles are contained within the document
- Can be reused within the same page
- Good for single-page styling

**Cons:**
- Not reusable across multiple pages
- Increases HTML file size
- Still mixes content with presentation

### 3. External CSS

Styles defined in separate `.css` files and linked to HTML documents.

**styles.css:**
```css
/* Reset and base styles */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    line-height: 1.6;
    color: #333;
    background-color: #fff;
}

/* Header styles */
header {
    background-color: #2c3e50;
    color: white;
    padding: 1rem 0;
    text-align: center;
}

/* Navigation */
nav ul {
    list-style: none;
    display: flex;
    justify-content: center;
    background-color: #34495e;
}

nav li {
    margin: 0 10px;
}

nav a {
    color: white;
    text-decoration: none;
    padding: 10px 15px;
    display: block;
    transition: background-color 0.3s;
}

nav a:hover {
    background-color: #2c3e50;
}

/* Main content */
main {
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px;
}

/* Responsive design */
@media (max-width: 768px) {
    nav ul {
        flex-direction: column;
    }
    
    main {
        padding: 10px;
    }
}
```

**HTML file:**
```html
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>My Website</h1>
    </header>
    <nav>
        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>
    <main>
        <p>Welcome to my website!</p>
    </main>
</body>
</html>
```

**Pros:**
- Reusable across multiple pages
- Cleaner HTML code
- Better maintainability
- Cacheable by browsers
- Team collaboration friendly

**Cons:**
- Requires additional HTTP request
- Slight delay in loading styles

## CSS Methodologies and Architectures

### 1. BEM (Block Element Modifier)

A naming convention for CSS classes that makes code more organized and maintainable.

```css
/* Block */
.card {
    background: white;
    border-radius: 8px;
    padding: 20px;
}

/* Element */
.card__title {
    font-size: 1.5rem;
    font-weight: bold;
    margin-bottom: 10px;
}

.card__content {
    color: #666;
    line-height: 1.4;
}

/* Modifier */
.card--featured {
    border: 2px solid #007bff;
    background: #f8f9ff;
}

.card--large {
    padding: 30px;
}
```

### 2. CSS Modules

Scoped CSS that prevents style conflicts by automatically generating unique class names.

```css
/* styles.module.css */
.container {
    max-width: 1200px;
    margin: 0 auto;
}

.button {
    background-color: #007bff;
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

.button:hover {
    background-color: #0056b3;
}
```

### 3. Atomic CSS (Utility-First)

Small, single-purpose classes that can be combined to create designs.

```css
/* Atomic/Utility classes */
.text-center { text-align: center; }
.text-left { text-align: left; }
.text-right { text-align: right; }

.mt-1 { margin-top: 0.25rem; }
.mt-2 { margin-top: 0.5rem; }
.mt-3 { margin-top: 1rem; }

.bg-blue { background-color: #007bff; }
.bg-red { background-color: #dc3545; }
.bg-green { background-color: #28a745; }

.flex { display: flex; }
.flex-column { flex-direction: column; }
.justify-center { justify-content: center; }
.items-center { align-items: center; }
```

## CSS Preprocessors

### 1. Sass/SCSS

Adds features like variables, nesting, mixins, and functions to CSS.

```scss
// Variables
$primary-color: #007bff;
$secondary-color: #6c757d;
$font-size-base: 16px;

// Mixins
@mixin button-style($bg-color: $primary-color) {
    background-color: $bg-color;
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    
    &:hover {
        background-color: darken($bg-color, 10%);
    }
}

// Nesting
.navigation {
    background-color: $secondary-color;
    
    ul {
        list-style: none;
        display: flex;
        
        li {
            margin: 0 10px;
            
            a {
                color: white;
                text-decoration: none;
                padding: 10px;
                
                &:hover {
                    background-color: rgba(255, 255, 255, 0.1);
                }
            }
        }
    }
}

// Using mixins
.btn-primary {
    @include button-style($primary-color);
}

.btn-secondary {
    @include button-style($secondary-color);
}
```

### 2. Less

Another CSS preprocessor with similar features to Sass.

```less
// Variables
@primary-color: #007bff;
@secondary-color: #6c757d;
@border-radius: 4px;

// Mixins
.button-style(@bg-color: @primary-color) {
    background-color: @bg-color;
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: @border-radius;
    cursor: pointer;
    
    &:hover {
        background-color: darken(@bg-color, 10%);
    }
}

// Usage
.btn-primary {
    .button-style(@primary-color);
}
```

## Modern CSS Features

### 1. CSS Grid

Two-dimensional layout system for complex layouts.

```css
.grid-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    grid-gap: 20px;
    padding: 20px;
}

.grid-item {
    background-color: #f8f9fa;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}
```

### 2. Flexbox

One-dimensional layout system for flexible layouts.

```css
.flex-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 20px;
}

.flex-item {
    flex: 1;
    min-width: 250px;
    background-color: #e9ecef;
    padding: 15px;
    border-radius: 6px;
}
```

### 3. CSS Custom Properties (Variables)

Native CSS variables for dynamic styling.

```css
:root {
    --primary-color: #007bff;
    --secondary-color: #6c757d;
    --font-size-base: 16px;
    --spacing-unit: 8px;
    --border-radius: 4px;
}

.card {
    background-color: var(--primary-color);
    color: white;
    padding: calc(var(--spacing-unit) * 2);
    border-radius: var(--border-radius);
    font-size: var(--font-size-base);
}

/* Theme switching */
[data-theme="dark"] {
    --primary-color: #0d6efd;
    --secondary-color: #6c757d;
}
```

## Best Practices

### 1. Organization and Structure

```css
/* 1. Reset/Normalize */
* {
    box-sizing: border-box;
}

/* 2. Base styles */
body {
    font-family: system-ui, -apple-system, sans-serif;
    line-height: 1.6;
}

/* 3. Layout */
.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
}

/* 4. Components */
.button { /* component styles */ }
.card { /* component styles */ }

/* 5. Utilities */
.text-center { text-align: center; }
.sr-only { /* screen reader only */ }

/* 6. Media queries */
@media (max-width: 768px) {
    /* responsive styles */
}
```

### 2. Performance Optimization

```css
/* Use efficient selectors */
.nav-item { /* Good */ }
div.nav ul li a { /* Avoid - too specific */ }

/* Minimize reflows and repaints */
.element {
    transform: translateX(100px); /* Better than left: 100px */
    opacity: 0; /* Better than visibility: hidden */
}

/* Use CSS containment */
.card {
    contain: layout style paint;
}
```

## Getting Started

1. **Create an HTML file** with basic structure
2. **Add CSS** using one of the three methods (inline, internal, or external)
3. **Start with basic styles** like colors, fonts, and spacing
4. **Learn selectors** (element, class, ID, pseudo-classes)
5. **Practice layouts** with Flexbox and Grid
6. **Make it responsive** with media queries
7. **Explore advanced features** like animations and transforms

## Resources

- [MDN CSS Documentation](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [CSS-Tricks](https://css-tricks.com/)
- [Can I Use](https://caniuse.com/) - Browser compatibility
- [Flexbox Froggy](https://flexboxfroggy.com/) - Learn Flexbox
- [Grid Garden](https://cssgridgarden.com/) - Learn CSS Grid

## Common CSS Properties Quick Reference

```css
/* Text and Typography */
font-family: Arial, sans-serif;
font-size: 16px;
font-weight: bold;
color: #333;
text-align: center;
line-height: 1.5;

/* Box Model */
width: 100px;
height: 100px;
padding: 10px;
margin: 20px;
border: 1px solid #ccc;

/* Background */
background-color: #f0f0f0;
background-image: url('image.jpg');
background-size: cover;
background-position: center;

/* Layout */
display: flex;
position: relative;
top: 10px;
left: 20px;
z-index: 1;

/* Flexbox */
justify-content: center;
align-items: center;
flex-direction: column;
flex-wrap: wrap;

/* Grid */
grid-template-columns: 1fr 1fr 1fr;
grid-gap: 20px;
grid-area: header;

/* Responsive */
@media (max-width: 768px) {
    /* Mobile styles */
}
```

This README provides a comprehensive overview of CSS, from basic concepts to advanced techniques, helping you understand and effectively use CSS in your web development projects.
