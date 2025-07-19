# Font Properties

Quick reference for CSS font properties and values.

## Core Properties

### font-family
```css
font-family: "Arial", sans-serif;
font-family: "Times New Roman", serif;
font-family: "Courier New", monospace;
```

### font-size
```css
font-size: 16px;          /* pixels */
font-size: 1.2em;         /* relative to parent */
font-size: 1.5rem;        /* relative to root */
font-size: large;         /* keyword */
```

### font-weight
```css
font-weight: normal;      /* 400 */
font-weight: bold;        /* 700 */
font-weight: 100-900;     /* numeric values */
```

### font-style
```css
font-style: normal;
font-style: italic;
font-style: oblique;
```

### font-variant
```css
font-variant: normal;
font-variant: small-caps;
```

## Shorthand

```css
font: [style] [variant] [weight] size[/line-height] family;
font: italic bold 18px/1.4 "Arial", sans-serif;
```

## Web Fonts

### Google Fonts
```html
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;700&display=swap" rel="stylesheet">
```

### Custom Fonts
```css
@font-face {
  font-family: 'MyFont';
  src: url('myfont.woff2') format('woff2'),
       url('myfont.woff') format('woff');
  font-weight: normal;
  font-style: normal;
}
```

## Font Stacks

```css
/* System fonts */
font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;

/* Safe web fonts */
font-family: Georgia, "Times New Roman", serif;
font-family: "Helvetica Neue", Arial, sans-serif;
font-family: "Courier New", Courier, monospace;
```

## Best Practices

- Always include fallback fonts
- Use `font-display: swap;` for web fonts
- Limit font variations to improve performance
- Test font loading and fallbacks
- Consider system fonts for better performance
