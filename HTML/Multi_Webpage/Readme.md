# Multi-Page Website File Paths - README

## Overview
File path management for multi-page websites ensures proper navigation, resource loading, and maintainable code structure across multiple HTML pages.

## Website Structure Best Practices

### Recommended Directory Structure
```
website/
├── index.html              # Homepage
├── about.html              # About page
├── contact.html            # Contact page
├── pages/
│   ├── services.html       # Services page
│   ├── portfolio.html      # Portfolio page
│   └── blog/
│       ├── index.html      # Blog homepage
│       └── post1.html      # Blog post
├── assets/
│   ├── css/
│   │   ├── style.css       # Main styles
│   │   └── responsive.css  # Mobile styles
│   ├── js/
│   │   ├── main.js         # Main JavaScript
│   │   └── utils.js        # Utility functions
│   └── images/
│       ├── logo.png
│       ├── hero-bg.jpg
│       └── gallery/
│           ├── photo1.jpg
│           └── photo2.jpg
└── downloads/
    └── brochure.pdf
```

## Multi-Page Navigation Examples

### 1. Root Level Pages (`index.html`, `about.html`, `contact.html`)
```html
<!DOCTYPE html>
<html>
<head>
    <!-- CSS Links -->
    <link rel="stylesheet" href="assets/css/style.css">
    <link rel="stylesheet" href="assets/css/responsive.css">
</head>
<body>
    <!-- Navigation Menu -->
    <nav>
        <a href="index.html">Home</a>
        <a href="about.html">About</a>
        <a href="contact.html">Contact</a>
        <a href="pages/services.html">Services</a>
        <a href="pages/portfolio.html">Portfolio</a>
        <a href="pages/blog/index.html">Blog</a>
    </nav>
    
    <!-- Page Content -->
    <img src="assets/images/logo.png" alt="Logo">
    <img src="assets/images/hero-bg.jpg" alt="Hero Background">
    
    <!-- Scripts -->
    <script src="assets/js/main.js"></script>
</body>
</html>
```

### 2. Subdirectory Pages (`pages/services.html`, `pages/portfolio.html`)
```html
<!DOCTYPE html>
<html>
<head>
    <!-- CSS Links - Go up one level -->
    <link rel="stylesheet" href="../assets/css/style.css">
    <link rel="stylesheet" href="../assets/css/responsive.css">
</head>
<body>
    <!-- Navigation Menu -->
    <nav>
        <a href="../index.html">Home</a>
        <a href="../about.html">About</a>
        <a href="../contact.html">Contact</a>
        <a href="services.html">Services</a>
        <a href="portfolio.html">Portfolio</a>
        <a href="blog/index.html">Blog</a>
    </nav>
    
    <!-- Page Content -->
    <img src="../assets/images/logo.png" alt="Logo">
    <img src="../assets/images/gallery/photo1.jpg" alt="Gallery Photo">
    
    <!-- Scripts -->
    <script src="../assets/js/main.js"></script>
</body>
</html>
```

### 3. Deep Nested Pages (`pages/blog/post1.html`)
```html
<!DOCTYPE html>
<html>
<head>
    <!-- CSS Links - Go up two levels -->
    <link rel="stylesheet" href="../../assets/css/style.css">
    <link rel="stylesheet" href="../../assets/css/responsive.css">
</head>
<body>
    <!-- Navigation Menu -->
    <nav>
        <a href="../../index.html">Home</a>
        <a href="../../about.html">About</a>
        <a href="../../contact.html">Contact</a>
        <a href="../services.html">Services</a>
        <a href="../portfolio.html">Portfolio</a>
        <a href="index.html">Blog Home</a>
    </nav>
    
    <!-- Page Content -->
    <img src="../../assets/images/logo.png" alt="Logo">
    <a href="../../downloads/brochure.pdf">Download Brochure</a>
    
    <!-- Scripts -->
    <script src="../../assets/js/main.js"></script>
</body>
</html>
```

## Alternative: Using Absolute Paths

### All Pages with Absolute Paths
```html
<!DOCTYPE html>
<html>
<head>
    <!-- CSS Links - Always from root -->
    <link rel="stylesheet" href="/assets/css/style.css">
    <link rel="stylesheet" href="/assets/css/responsive.css">
</head>
<body>
    <!-- Navigation Menu - Same for all pages -->
    <nav>
        <a href="/index.html">Home</a>
        <a href="/about.html">About</a>
        <a href="/contact.html">Contact</a>
        <a href="/pages/services.html">Services</a>
        <a href="/pages/portfolio.html">Portfolio</a>
        <a href="/pages/blog/index.html">Blog</a>
    </nav>
    
    <!-- Page Content -->
    <img src="/assets/images/logo.png" alt="Logo">
    <img src="/assets/images/gallery/photo1.jpg" alt="Gallery Photo">
    
    <!-- Scripts -->
    <script src="/assets/js/main.js"></script>
</body>
</html>
```

## Multi-Page Best Practices

### 1. Consistent Navigation
- Keep navigation menu identical across all pages
- Use CSS classes for active page highlighting
- Include breadcrumbs for deep pages

### 2. Resource Management
- Use a common CSS/JS structure for all pages
- Implement caching strategies
- Optimize images for web delivery

### 3. SEO-Friendly URLs
```html
<!-- Good: Descriptive URLs -->
<a href="pages/about-us.html">About Us</a>
<a href="pages/blog/web-design-tips.html">Web Design Tips</a>

<!-- Avoid: Generic URLs -->
<a href="pages/page1.html">Page 1</a>
<a href="pages/blog/post1.html">Post 1</a>
```

### 4. Error Handling
```html
<!-- Include 404 error page -->
<!-- 404.html in root directory -->
<h1>Page Not Found</h1>
<a href="/index.html">Return to Homepage</a>
```

## Common Multi-Page Issues

### Path Problems
- **Broken links**: When moving files between directories
- **Missing resources**: CSS/JS files not loading on some pages
- **Image paths**: Different relative paths for different page levels

### Solutions
```html
<!-- Use base tag for consistent relative paths -->
<base href="/">

<!-- Or use absolute paths consistently -->
<link rel="stylesheet" href="/assets/css/style.css">
```

## Testing Checklist
- [ ] All navigation links work from every page
- [ ] CSS/JS loads correctly on all pages
- [ ] Images display properly across all pages
- [ ] Forms submit to correct destinations
- [ ] Download links work from all locations
- [ ] Mobile navigation functions properly
- [ ] Search functionality works site-wide

## Quick Multi-Page Template
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Page Title - Your Website</title>
    <link rel="stylesheet" href="/assets/css/style.css">
</head>
<body>
    <header>
        <nav>
            <a href="/index.html">Home</a>
            <a href="/about.html">About</a>
            <a href="/contact.html">Contact</a>
        </nav>
    </header>
    
    <main>
        <!-- Page-specific content -->
    </main>
    
    <footer>
        <p>&copy; 2024 Your Website. All rights reserved.</p>
    </footer>
    
    <script src="/assets/js/main.js"></script>
</body>
</html>
```
