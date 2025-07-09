# HTML Self-Closing Tags

## Overview

Self-closing tags (also called void elements) are HTML elements that don't require a closing tag because they don't contain content. They represent standalone elements like images, line breaks, and form inputs.

## Common Self-Closing Tags

### Essential Elements
```html
<img src="image.jpg" alt="Description">
<br>
<hr>
<input type="text" name="username">
<meta charset="UTF-8">
<link rel="stylesheet" href="style.css">
```

### Complete List
| Tag | Purpose | Example |
|-----|---------|---------|
| `<img>` | Images | `<img src="photo.jpg" alt="Photo">` |
| `<br>` | Line break | `<br>` |
| `<hr>` | Horizontal rule | `<hr>` |
| `<input>` | Form input | `<input type="email" required>` |
| `<meta>` | Metadata | `<meta name="viewport" content="width=device-width">` |
| `<link>` | External resources | `<link rel="icon" href="favicon.ico">` |
| `<area>` | Image map area | `<area shape="rect" coords="0,0,50,50" href="page.html">` |
| `<base>` | Base URL | `<base href="https://example.com/">` |
| `<col>` | Table column | `<col span="2" style="background-color:yellow">` |
| `<embed>` | Embedded content | `<embed src="video.mp4" type="video/mp4">` |
| `<source>` | Media resource | `<source src="audio.mp3" type="audio/mpeg">` |
| `<track>` | Text track | `<track kind="subtitles" src="subs.vtt">` |
| `<wbr>` | Word break opportunity | `<wbr>` |

## Syntax Rules

### HTML5 (Recommended)
```html
<!-- No closing slash needed -->
<img src="image.jpg" alt="Description">
<br>
<input type="text">
```

### XHTML Style (Optional)
```html
<!-- With closing slash -->
<img src="image.jpg" alt="Description" />
<br />
<input type="text" />
```

## Key Points

### ✅ Correct Usage
```html
<img src="logo.png" alt="Company Logo">
<input type="email" placeholder="Enter email">
<meta charset="UTF-8">
<link rel="stylesheet" href="styles.css">
```

### ❌ Common Mistakes
```html
<!-- Don't add closing tags -->
<img src="image.jpg"></img>  <!-- Wrong -->
<br></br>                    <!-- Wrong -->
<input type="text"></input>  <!-- Wrong -->

<!-- Don't self-close regular elements -->
<div />                      <!-- Wrong -->
<p />                        <!-- Wrong -->
<span />                     <!-- Wrong -->
```

## Practical Examples

### Form Elements
```html
<form>
    <input type="text" name="name" placeholder="Your name">
    <input type="email" name="email" required>
    <input type="password" name="password">
    <input type="submit" value="Submit">
</form>
```

### Document Head
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <link rel="icon" href="favicon.ico">
</head>
```

### Content Structure
```html
<article>
    <h1>Article Title</h1>
    <img src="hero-image.jpg" alt="Article illustration">
    <p>First paragraph of content.</p>
    <hr>
    <p>Second paragraph after divider.</p>
</article>
```

## Best Practices

1. **Always include required attributes** (like `alt` for images)
2. **Use semantic meaning** (don't use `<br>` for spacing)
3. **Validate your HTML** to catch missing attributes
4. **Be consistent** with your chosen syntax style
5. **Don't close void elements** in HTML5

## Quick Reference

**Most Used:**
- `<img>` - Images
- `<br>` - Line breaks  
- `<input>` - Form fields
- `<meta>` - Page metadata
- `<link>` - External resources

**Remember:** These elements represent things, not containers, so they don't need closing tags.
