# DonateMate Design System Reference

Use this reference when generating HTML for Figma import via HTML to Figma plugin.

## Quick Start

Include this CSS link in your HTML:
```html
<link href="https://raw.githubusercontent.com/donate-mate/design-tokens/main/tokens.css" rel="stylesheet">
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
```

## Colors

### Text Colors
| Variable | Use For |
|----------|---------|
| `var(--text-primary)` | Main text, headings |
| `var(--text-secondary)` | Secondary text, descriptions |
| `var(--text-tertiary)` | Placeholder text, disabled |
| `var(--text-label)` | Form labels |
| `var(--text-error)` | Error messages |
| `var(--text-success)` | Success messages |
| `var(--text-inverse)` | Text on dark backgrounds |

### Background Colors
| Variable | Use For |
|----------|---------|
| `var(--bg-primary)` | Main background (white) |
| `var(--bg-secondary)` | Cards, sections |
| `var(--bg-tertiary)` | Subtle backgrounds |
| `var(--bg-inverse)` | Dark backgrounds |

### Accent Colors
| Variable | Use For |
|----------|---------|
| `var(--accent-primary)` | Primary buttons, links, active states |
| `var(--accent-primary-light)` | Hover states (lighter) |
| `var(--accent-primary-dark)` | Pressed states |

### Border Colors
| Variable | Use For |
|----------|---------|
| `var(--border-primary)` | Default borders |
| `var(--border-focus)` | Focus states |
| `var(--border-error)` | Error states |
| `var(--border-success)` | Success states |

## Typography Classes

### Display (Hero text)
- `.text-display-xl` - 40px Bold
- `.text-display-lg` - 32px Bold
- `.text-display-md` - 28px Bold

### Headings
- `.text-heading-xl` - 24px SemiBold
- `.text-heading-lg` - 20px SemiBold
- `.text-heading-md` - 18px SemiBold
- `.text-heading-sm` - 16px SemiBold

### Body
- `.text-body-lg` - 18px Regular
- `.text-body-md` - 16px Regular (default)
- `.text-body-sm` - 14px Regular
- `.text-body-xs` - 12px Regular

### Labels
- `.text-label-lg` - 16px Medium
- `.text-label-md` - 14px Medium
- `.text-label-sm` - 12px Medium

## Spacing

| Variable | Value | Use For |
|----------|-------|---------|
| `var(--space-xs3)` | 4px | Tiny gaps |
| `var(--space-xs2)` | 8px | Small gaps |
| `var(--space-xs)` | 12px | Compact spacing |
| `var(--space-sm)` | 16px | Default spacing |
| `var(--space-md)` | 20px | Medium spacing |
| `var(--space-lg)` | 24px | Large spacing |
| `var(--space-xl)` | 28px | Section spacing |
| `var(--space-xl2)` | 32px | Large sections |

## Border Radius

| Variable | Value | Use For |
|----------|-------|---------|
| `var(--radius-xs)` | 4px | Checkboxes, small elements |
| `var(--radius-sm)` | 8px | Tags, chips |
| `var(--radius-md)` | 12px | Inputs, small cards |
| `var(--radius-lg)` | 16px | Buttons, cards |
| `var(--radius-xl)` | 20px | Modals |
| `var(--radius-full)` | 9999px | Circles, pills |

## Shadows

| Variable | Use For |
|----------|---------|
| `var(--shadow-xs)` | Subtle elevation |
| `var(--shadow-sm)` | Cards, inputs |
| `var(--shadow-md)` | Dropdowns |
| `var(--shadow-lg)` | Popovers |
| `var(--shadow-xl)` | Modals |

## Component Classes

### Buttons
```html
<button class="btn-primary">Primary Button</button>
<button class="btn-secondary">Secondary Button</button>
```

### Inputs
```html
<input class="input" placeholder="Enter text...">
<input class="input input-error" placeholder="Error state">
```

### Cards
```html
<div class="card">Card content</div>
```

### Modals
```html
<div class="modal-overlay">
  <div class="modal">Modal content</div>
</div>
```

## Example: Login Screen

```html
<!DOCTYPE html>
<html>
<head>
  <link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
  <link href="https://raw.githubusercontent.com/donate-mate/design-tokens/main/tokens.css" rel="stylesheet">
</head>
<body style="background: var(--bg-secondary); padding: var(--space-lg);">
  <div class="card" style="max-width: 400px; margin: 0 auto;">
    <h1 class="text-heading-xl" style="color: var(--text-primary); margin-bottom: var(--space-sm);">
      Welcome back
    </h1>
    <p class="text-body-md" style="color: var(--text-secondary); margin-bottom: var(--space-lg);">
      Sign in to your account
    </p>

    <div style="margin-bottom: var(--space-sm);">
      <label class="text-label-sm" style="color: var(--text-label); display: block; margin-bottom: var(--space-xs3);">
        Email
      </label>
      <input class="input" style="width: 100%;" placeholder="you@example.com">
    </div>

    <div style="margin-bottom: var(--space-lg);">
      <label class="text-label-sm" style="color: var(--text-label); display: block; margin-bottom: var(--space-xs3);">
        Password
      </label>
      <input class="input" type="password" style="width: 100%;" placeholder="••••••••">
    </div>

    <button class="btn-primary" style="width: 100%;">Sign In</button>
  </div>
</body>
</html>
```

## Mobile Screen Template (375x812)

```html
<!DOCTYPE html>
<html>
<head>
  <link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
  <style>
    /* Paste tokens.css content here or link it */
  </style>
</head>
<body style="
  width: 375px;
  min-height: 812px;
  background: var(--bg-primary);
  font-family: var(--font-family);
  margin: 0;
  padding: var(--space-lg);
  box-sizing: border-box;
">
  <!-- Screen content here -->
</body>
</html>
```
