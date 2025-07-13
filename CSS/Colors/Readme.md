# CSS Colors - Quick Reference

## Color Formats

### 1. Named Colors
```css
color: red;
background-color: blue;
border-color: green;
```

### 2. Hexadecimal
```css
color: #ff0000;        /* Red */
color: #00ff00;        /* Green */
color: #0000ff;        /* Blue */
color: #fff;           /* White (shorthand) */
color: #000;           /* Black (shorthand) */
```

### 3. RGB
```css
color: rgb(255, 0, 0);      /* Red */
color: rgb(0, 255, 0);      /* Green */
color: rgb(0, 0, 255);      /* Blue */
color: rgba(255, 0, 0, 0.5); /* Red with 50% opacity */
```

### 4. HSL
```css
color: hsl(0, 100%, 50%);     /* Red */
color: hsl(120, 100%, 50%);   /* Green */
color: hsl(240, 100%, 50%);   /* Blue */
color: hsla(0, 100%, 50%, 0.5); /* Red with 50% opacity */
```

## Common Properties

```css
color: #333;                  /* Text color */
background-color: #f0f0f0;    /* Background color */
border-color: #ccc;           /* Border color */
outline-color: blue;          /* Outline color */
```

## Popular Color Palettes

### Grays
```css
--black: #000000;
--dark-gray: #333333;
--gray: #666666;
--light-gray: #cccccc;
--white: #ffffff;
```

### Blues
```css
--primary-blue: #007bff;
--dark-blue: #0056b3;
--light-blue: #e3f2fd;
```

### Modern Colors
```css
--success: #28a745;
--danger: #dc3545;
--warning: #ffc107;
--info: #17a2b8;
```

## CSS Variables Example

```css
:root {
  --primary: #007bff;
  --secondary: #6c757d;
  --success: #28a745;
  --danger: #dc3545;
  --light: #f8f9fa;
  --dark: #343a40;
}

.btn-primary {
  background-color: var(--primary);
  color: white;
}
```

## Quick Tips

- Use **hex** for solid colors: `#ff0000`
- Use **rgba/hsla** for transparency: `rgba(255, 0, 0, 0.5)`
- Use **CSS variables** for consistent theming
- **HSL** is great for color variations: `hsl(240, 100%, 50%)`

## Common Color Functions

```css
/* Opacity */
color: rgba(255, 0, 0, 0.8);

/* Gradients */
background: linear-gradient(45deg, #ff0000, #00ff00);
background: radial-gradient(circle, #ff0000, #0000ff);

/* Current color */
border-color: currentColor;  /* Uses text color */
```

## Accessibility

```css
/* Good contrast ratios */
.text-primary { color: #212529; }      /* Dark text */
.bg-light { background-color: #f8f9fa; } /* Light background */

/* Focus states */
button:focus {
  outline: 2px solid #007bff;
  outline-offset: 2px;
}
```
