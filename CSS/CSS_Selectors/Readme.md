# CSS Selectors - Quick Reference

## Basic Selectors

### 1. Element Selector
Selects all elements of a specific type.
```css
p { color: blue; }        /* All <p> elements */
h1 { font-size: 24px; }   /* All <h1> elements */
```

### 2. Class Selector
Selects elements with a specific class attribute.
```css
.highlight { background: yellow; }  /* class="highlight" */
.btn { padding: 10px; }             /* class="btn" */
```

### 3. ID Selector
Selects element with a specific ID attribute.
```css
#header { background: navy; }       /* id="header" */
#main-content { margin: 20px; }     /* id="main-content" */
```

### 4. Universal Selector
Selects all elements.
```css
* { margin: 0; padding: 0; }        /* All elements */
```

## Combination Selectors

### 1. Descendant Selector
Selects elements inside other elements.
```css
div p { color: red; }               /* <p> inside <div> */
.container h2 { font-weight: bold; } /* <h2> inside .container */
```

### 2. Child Selector
Selects direct children only.
```css
ul > li { list-style: none; }       /* Direct <li> children of <ul> */
.nav > a { display: block; }        /* Direct <a> children of .nav */
```

### 3. Adjacent Sibling Selector
Selects element immediately after another.
```css
h1 + p { margin-top: 0; }           /* <p> right after <h1> */
.btn + .btn { margin-left: 10px; }  /* .btn right after .btn */
```

### 4. General Sibling Selector
Selects all siblings after an element.
```css
h1 ~ p { color: gray; }             /* All <p> after <h1> */
.active ~ li { opacity: 0.5; }      /* All <li> after .active */
```

## Attribute Selectors

```css
[type] { border: 1px solid; }           /* Elements with type attribute */
[type="text"] { background: white; }     /* type="text" */
[class^="btn"] { padding: 5px; }        /* class starts with "btn" */
[class$="large"] { font-size: 20px; }   /* class ends with "large" */
[class*="nav"] { display: flex; }       /* class contains "nav" */
```

## Pseudo-Classes

### Common States
```css
a:hover { color: red; }             /* On hover */
a:active { color: blue; }           /* When clicked */
a:focus { outline: 2px solid; }     /* When focused */
a:visited { color: purple; }        /* Visited links */
```

### Structural Pseudo-Classes
```css
li:first-child { font-weight: bold; }   /* First child */
li:last-child { margin-bottom: 0; }     /* Last child */
li:nth-child(2) { color: red; }         /* 2nd child */
li:nth-child(odd) { background: #f0f0f0; } /* Odd children */
li:nth-child(even) { background: white; }  /* Even children */
p:not(.special) { color: gray; }        /* Not having .special class */
```

## Pseudo-Elements

```css
p::first-line { font-weight: bold; }    /* First line of paragraph */
p::first-letter { font-size: 2em; }     /* First letter */
.quote::before { content: """; }        /* Insert content before */
.quote::after { content: """; }         /* Insert content after */
```

## Selector Specificity

**Priority Order (highest to lowest):**
1. Inline styles (`style="..."`)
2. IDs (`#id`)
3. Classes (`.class`), attributes (`[attr]`), pseudo-classes (`:hover`)
4. Elements (`div`, `p`)

```css
/* Specificity: 0,0,0,1 */
p { color: black; }

/* Specificity: 0,0,1,0 */
.text { color: blue; }

/* Specificity: 0,1,0,0 */
#title { color: red; }

/* Specificity: 0,1,1,1 */
#title.text p { color: green; }
```

## Common Patterns

### Multiple Classes
```css
.btn.primary { background: blue; }      /* Has both btn AND primary */
.btn, .link { text-decoration: none; }  /* btn OR link */
```

### Complex Selectors
```css
/* Table rows on hover */
table tr:hover td { background: #f5f5f5; }

/* Form inputs except submit */
input:not([type="submit"]) { border: 1px solid #ccc; }

/* Every 3rd item starting from 2nd */
li:nth-child(3n+2) { color: blue; }
```

## Tips

- **Use classes** for reusable styles
- **Use IDs** for unique elements
- **Keep specificity low** for maintainability
- **Avoid overly complex selectors** for performance
- **Use semantic selectors** when possible

## Quick Examples

```css
/* Navigation menu */
.nav ul li a:hover { color: #007bff; }

/* Form styling */
input[type="email"]:focus { border-color: green; }

/* Card component */
.card:first-child { margin-top: 0; }
.card:last-child { margin-bottom: 0; }

/* Responsive helper */
.mobile-only { display: none; }
@media (max-width: 768px) {
    .mobile-only { display: block; }
}
```
