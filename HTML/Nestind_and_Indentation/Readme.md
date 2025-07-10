# HTML Nesting and Indentation

## Overview

Proper nesting and indentation make HTML code readable, maintainable, and easier to debug. These practices are essential for clean, professional web development.

## Nesting Rules

### Basic Nesting Structure
```html
<html>
    <head>
        <title>Page Title</title>
    </head>
    <body>
        <header>
            <h1>Main Title</h1>
        </header>
    </body>
</html>
```

### Parent-Child Relationships
```html
<!-- Parent contains children -->
<div>                    <!-- Parent -->
    <h2>Section Title</h2>    <!-- Child -->
    <p>Content here</p>       <!-- Child -->
</div>
```

## Indentation Standards

### 2-Space Indentation (Recommended)
```html
<section>
  <article>
    <h2>Article Title</h2>
    <p>Article content goes here.</p>
  </article>
</section>
```

### 4-Space Indentation (Alternative)
```html
<section>
    <article>
        <h2>Article Title</h2>
        <p>Article content goes here.</p>
    </article>
</section>
```

### Tab Indentation
```html
<section>
	<article>
		<h2>Article Title</h2>
		<p>Article content goes here.</p>
	</article>
</section>
```

## Proper Nesting Examples

### ✅ Correct Nesting
```html
<!-- Block elements containing inline elements -->
<div>
    <p>This is a <strong>paragraph</strong> with <em>emphasis</em>.</p>
    <ul>
        <li>List item 1</li>
        <li>List item 2</li>
    </ul>
</div>

<!-- Nested lists -->
<ul>
    <li>Frontend
        <ul>
            <li>HTML</li>
            <li>CSS</li>
        </ul>
    </li>
    <li>Backend</li>
</ul>

<!-- Form structure -->
<form>
    <fieldset>
        <legend>Contact Info</legend>
        <label for="name">Name:</label>
        <input type="text" id="name">
    </fieldset>
</form>
```

### ❌ Incorrect Nesting
```html
<!-- Wrong: Inline containing block -->
<span>
    <div>Block inside inline</div>  <!-- Invalid -->
</span>

<!-- Wrong: Overlapping tags -->
<p>Text with <strong>bold and <em>italic</p></strong></em>

<!-- Wrong: Missing closing tags -->
<div>
    <p>Paragraph without closing tag
    <span>Span content</span>
</div>

<!-- Wrong: Improper list nesting -->
<ul>
    <ul>  <!-- Missing parent <li> -->
        <li>Nested item</li>
    </ul>
</ul>
```

## Indentation Best Practices

### 1. Consistent Spacing
```html
<!-- ✅ Good: Consistent 2-space indentation -->
<article>
  <header>
    <h1>Title</h1>
    <p>Subtitle</p>
  </header>
  <main>
    <p>Content</p>
  </main>
</article>

<!-- ❌ Bad: Inconsistent indentation -->
<article>
 <header>
     <h1>Title</h1>
  <p>Subtitle</p>
 </header>
</article>
```

### 2. Align Closing Tags
```html
<!-- ✅ Good: Clear structure -->
<div class="container">
    <div class="row">
        <div class="col">
            <p>Content</p>
        </div>
    </div>
</div>

<!-- ❌ Bad: Poor alignment -->
<div class="container">
<div class="row">
<div class="col">
<p>Content</p>
</div>
</div>
</div>
```

### 3. Self-Closing Tags
```html
<!-- ✅ Good: Proper spacing -->
<div>
    <img src="image.jpg" alt="Description">
    <br>
    <input type="text" name="username">
</div>

<!-- ❌ Bad: Inconsistent spacing -->
<div>
<img src="image.jpg" alt="Description">
<br>
        <input type="text" name="username">
</div>
```

## Common Nesting Patterns

### Navigation Structure
```html
<nav>
    <ul>
        <li><a href="#home">Home</a></li>
        <li>
            <a href="#services">Services</a>
            <ul>
                <li><a href="#web">Web Design</a></li>
                <li><a href="#mobile">Mobile Apps</a></li>
            </ul>
        </li>
    </ul>
</nav>
```

### Article Layout
```html
<article>
    <header>
        <h1>Article Title</h1>
        <p class="meta">By Author • Date</p>
    </header>
    <section>
        <h2>Introduction</h2>
        <p>Article content...</p>
    </section>
    <footer>
        <p>Tags: HTML, CSS</p>
    </footer>
</article>
```

### Form Structure
```html
<form>
    <div class="form-group">
        <label for="email">Email:</label>
        <input type="email" id="email" required>
    </div>
    <div class="form-group">
        <label for="message">Message:</label>
        <textarea id="message" rows="4"></textarea>
    </div>
    <button type="submit">Send</button>
</form>
```

## Validation Rules

### Block vs Inline Elements
```html
<!-- ✅ Valid: Block elements can contain inline and block -->
<div>
    <p>Paragraph</p>
    <span>Inline text</span>
</div>

<!-- ❌ Invalid: Inline elements cannot contain block -->
<span>
    <div>Block content</div>  <!-- Not allowed -->
</span>
```

### Specific Element Rules
```html
<!-- ✅ Valid: List items in lists -->
<ul>
    <li>Only li elements allowed directly in ul</li>
</ul>

<!-- ❌ Invalid: Direct content in lists -->
<ul>
    Direct text not allowed
    <li>List item</li>
</ul>
```

## Tools for Formatting

### VS Code Extensions
- **Prettier** - Auto-formatting
- **Auto Rename Tag** - Sync opening/closing tags
- **Bracket Pair Colorizer** - Visual nesting aid

### Online Formatters
- HTML Formatter
- Code Beautifier
- W3C Markup Validator

## Quick Tips

1. **Use consistent indentation** (2 or 4 spaces)
2. **Never mix tabs and spaces**
3. **Align opening and closing tags**
4. **Validate your HTML** regularly
5. **Use semantic elements** for better structure
6. **Keep nesting shallow** when possible

## Common Mistakes

- Overlapping tags
- Missing closing tags
- Inconsistent indentation
- Block elements inside inline elements
- Improper list nesting

**Remember:** Good nesting and indentation make your code professional and maintainable!
