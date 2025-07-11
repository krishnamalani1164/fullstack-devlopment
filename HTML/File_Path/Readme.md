# HTML File Paths - Relative vs Absolute

## Overview
File paths in HTML define the location of resources (images, CSS, JS, other HTML files) relative to the current document or from the root of the file system/server.

## Types of Paths

### 1. Absolute Paths
- **Definition**: Complete path from the root directory
- **Starts with**: `/` (root) or `http://`/`https://` (URL)
- **Independent**: Works regardless of current file location

### 2. Relative Paths
- **Definition**: Path relative to the current document's location
- **Starts with**: filename, `./`, or `../`
- **Dependent**: Changes based on current file location

## Path Syntax

| Syntax | Meaning | Example |
|--------|---------|---------|
| `/` | Root directory | `/images/logo.png` |
| `./` | Current directory | `./styles.css` |
| `../` | Parent directory | `../images/photo.jpg` |
| `../../` | Two levels up | `../../assets/script.js` |

## Example Implementation

### Directory Structure
```
project/
├── index.html
├── about/
│   └── about.html
├── assets/
│   ├── css/
│   │   └── style.css
│   ├── images/
│   │   └── logo.png
│   └── js/
│       └── script.js
└── contact/
    └── contact.html
```

### From `index.html` (Root Level)
```html
<!-- Relative Paths -->
<link rel="stylesheet" href="assets/css/style.css">
<img src="assets/images/logo.png" alt="Logo">
<script src="assets/js/script.js"></script>
<a href="about/about.html">About</a>

<!-- Absolute Paths -->
<link rel="stylesheet" href="/assets/css/style.css">
<img src="/assets/images/logo.png" alt="Logo">
<script src="/assets/js/script.js"></script>
<a href="/about/about.html">About</a>
```

### From `about/about.html` (Subdirectory)
```html
<!-- Relative Paths -->
<link rel="stylesheet" href="../assets/css/style.css">
<img src="../assets/images/logo.png" alt="Logo">
<script src="../assets/js/script.js"></script>
<a href="../index.html">Home</a>
<a href="../contact/contact.html">Contact</a>

<!-- Absolute Paths -->
<link rel="stylesheet" href="/assets/css/style.css">
<img src="/assets/images/logo.png" alt="Logo">
<script src="/assets/js/script.js"></script>
<a href="/index.html">Home</a>
<a href="/contact/contact.html">Contact</a>
```

## Best Practices

### Use Relative Paths When:
- Building portable websites
- Working in development environments
- Files may be moved to different servers
- Creating reusable components

### Use Absolute Paths When:
- Referencing external resources (CDNs)
- Working with large, complex site structures
- Ensuring consistent resource loading
- Linking to specific server locations

## Common Mistakes
- **Mixed usage**: Inconsistent path types can cause broken links
- **Case sensitivity**: Server environments may be case-sensitive
- **Missing `../`**: Forgetting to go up directories when needed
- **Extra slashes**: Double slashes can break paths

## Quick Reference
```html
<!-- Current directory -->
<img src="image.jpg">
<img src="./image.jpg">

<!-- Parent directory -->
<img src="../image.jpg">

<!-- Root directory -->
<img src="/images/image.jpg">

<!-- External URL -->
<img src="https://example.com/image.jpg">
```

## Testing Tips
1. Always test links in different browsers
2. Use browser developer tools to check for 404 errors
3. Verify paths work when files are moved
4. Test both local and server environments
