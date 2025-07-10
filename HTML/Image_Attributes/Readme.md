# Image Tag and Attributes

A comprehensive guide for HTML image tags and their attributes for web development.

## Theory

The `<img>` tag embeds images in HTML documents. It's a self-closing tag that requires the `src` attribute to specify the image source. Additional attributes control display, accessibility, and behavior.

## Basic Syntax

```html
<img src="image.jpg" alt="Description" width="300" height="200">
```

## Essential Attributes

### Required
- `src` - Image source URL or file path
- `alt` - Alternative text for accessibility

### Common Attributes
- `width` - Image width in pixels
- `height` - Image height in pixels
- `title` - Tooltip text on hover
- `loading` - Lazy loading behavior

## Examples

### Basic Image
```html
<img src="logo.png" alt="Company Logo">
```

### Responsive Image
```html
<img src="photo.jpg" alt="Nature photo" 
     width="100%" style="max-width: 500px;">
```

### Lazy Loading
```html
<img src="hero.jpg" alt="Hero image" loading="lazy">
```

### Image with Link
```html
<a href="portfolio.html">
    <img src="thumbnail.jpg" alt="Portfolio thumbnail">
</a>
```

### Srcset for Different Screens
```html
<img src="small.jpg" 
     srcset="small.jpg 480w, medium.jpg 800w, large.jpg 1200w"
     sizes="(max-width: 600px) 480px, (max-width: 900px) 800px, 1200px"
     alt="Responsive image">
```

## Advanced Attributes

| Attribute | Description | Example |
|-----------|-------------|---------|
| `crossorigin` | CORS settings | `anonymous` |
| `decoding` | Image decoding hint | `async` |
| `fetchpriority` | Loading priority | `high` |
| `referrerpolicy` | Referrer policy | `no-referrer` |
| `usemap` | Image map reference | `#map1` |

## Best Practices

### Accessibility
```html
<!-- Good: Descriptive alt text -->
<img src="chart.png" alt="Sales increased 25% in Q3 2024">

<!-- Bad: Generic alt text -->
<img src="chart.png" alt="chart">
```

### Performance
```html
<!-- Lazy load images below the fold -->
<img src="image.jpg" alt="Description" loading="lazy">

<!-- Preload critical images -->
<link rel="preload" as="image" href="hero.jpg">
```

### SEO Optimization
```html
<img src="product.jpg" 
     alt="Red leather handbag with golden buckles"
     title="Premium Leather Handbag - $299">
```

## File Formats

- **JPEG** - Photos, complex images
- **PNG** - Transparency, simple graphics
- **WebP** - Modern format, better compression
- **SVG** - Vector graphics, scalable

## Code Template

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Gallery</title>
</head>
<body>
    <h1>Image Examples</h1>
    
    <!-- Basic image -->
    <img src="assets/photo1.jpg" alt="Mountain landscape at sunset">
    
    <!-- Responsive image -->
    <img src="assets/photo2.jpg" 
         alt="City skyline"
         srcset="assets/photo2-small.jpg 480w, 
                 assets/photo2-large.jpg 1200w"
         sizes="(max-width: 600px) 480px, 1200px">
    
    <!-- Lazy loaded image -->
    <img src="assets/photo3.jpg" 
         alt="Ocean waves" 
         loading="lazy"
         width="800" 
         height="600">
</body>
</html>
```

## Common Issues

- **Missing alt text** - Always provide descriptive alt attributes
- **Large file sizes** - Optimize images for web
- **Layout shift** - Specify width/height to prevent CLS
- **Broken links** - Validate image paths and URLs

## Browser Support

All modern browsers support the `<img>` tag. For advanced features:
- `loading="lazy"` - Chrome 76+, Firefox 75+
- `srcset` - All modern browsers
- WebP format - Chrome 23+, Firefox 65+
