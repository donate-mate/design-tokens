# DonateMate Design Tokens

Design tokens for the DonateMate mobile application, managed via [Tokens Studio for Figma](https://tokens.studio/).

## Overview

This repository serves as the single source of truth for design tokens shared between the DonateMate Figma designs and React Native codebase. Changes made in Figma are automatically synced here, and developers can pull the latest tokens into the app.

## Token Structure

```
├── tokens.json      # All design tokens
├── $themes.json     # Theme configuration
└── $metadata.json   # Token set ordering
```

### Token Sets

| Set | Description |
|-----|-------------|
| `global` | Primitive tokens (colors, spacing, typography scales, shadows) |
| `light` | Light theme semantic tokens (references global tokens) |
| `typography` | Text styles (display, heading, body, label) |
| `component` | Component-specific tokens (button, input, card, modal, etc.) |

## Token Categories

### Colors

| Category | Tokens |
|----------|--------|
| **Palette** | `slate`, `sky`, `red`, `green` with numeric scales |
| **Text** | `primary`, `secondary`, `tertiary`, `label`, `error`, `success`, `inverse` |
| **Background** | `primary`, `secondary`, `tertiary`, `inverse` |
| **Border** | `primary`, `secondary`, `focus`, `error`, `success` + muted variants |
| **Accent** | `primary`, `primaryLight`, `primaryDark`, `primaryDarker`, `primaryMuted` |
| **Icon** | `default`, `muted`, `active`, `error`, `success`, `inverse` |
| **Gradient** | `primary`, `disabled`, `default`, `focus`, `error`, `success`, `background` |

### Spacing Scale

| Token | Value | Token | Value |
|-------|-------|-------|-------|
| `xs4` | 2px | `xl` | 28px |
| `xs3` | 4px | `xl2` | 32px |
| `xs2` | 8px | `xl3` | 36px |
| `xs` | 12px | `xl4` | 40px |
| `sm` | 16px | `xl5` | 48px |
| `md` | 20px | `xl6` | 56px |
| `lg` | 24px | `xl7` | 64px |

### Typography

| Style | Font | Weight | Size | Line Height |
|-------|------|--------|------|-------------|
| `display.xl` | DM Sans | Bold | 40px | 52px |
| `display.lg` | DM Sans | Bold | 32px | 42px |
| `display.md` | DM Sans | Bold | 28px | 38px |
| `heading.xl` | DM Sans | SemiBold | 24px | 32px |
| `heading.lg` | DM Sans | SemiBold | 20px | 30px |
| `heading.md` | DM Sans | SemiBold | 18px | 28px |
| `heading.sm` | DM Sans | SemiBold | 16px | 24px |
| `body.lg` | DM Sans | Regular | 18px | 28px |
| `body.md` | DM Sans | Regular | 16px | 24px |
| `body.sm` | DM Sans | Regular | 14px | 20px |
| `body.xs` | DM Sans | Regular | 12px | 18px |
| `label.lg` | DM Sans | Medium | 16px | 24px |
| `label.md` | DM Sans | Medium | 14px | 20px |
| `label.sm` | DM Sans | Medium | 12px | 18px |

### Shadows

| Token | Y Offset | Blur | Color |
|-------|----------|------|-------|
| `none` | 0 | 0 | transparent |
| `xs` | 1px | 2px | rgba(0,0,0,0.05) |
| `sm` | 2px | 4px | rgba(0,0,0,0.05) |
| `md` | 4px | 8px | rgba(0,0,0,0.08) |
| `lg` | 8px | 16px | rgba(0,0,0,0.10) |
| `xl` | 12px | 24px | rgba(0,0,0,0.12) |

## Figma Integration

### Setup Tokens Studio

1. Install [Tokens Studio for Figma](https://www.figma.com/community/plugin/843461159747178978)
2. Open the plugin in your Figma file
3. Go to **Settings** → **Sync providers** → **Add new** → **GitHub**
4. Configure:
   - **Personal Access Token**: Create a [GitHub PAT](https://github.com/settings/tokens) with `repo` scope
   - **Repository**: `donate-mate/design-tokens`
   - **Branch**: `main`
   - **File Path**: Leave empty (tokens are at root)
5. Click **Save**

### Workflow

1. **Pull tokens**: Click the sync icon to pull latest tokens from this repo
2. **Edit in Figma**: Make changes using the Tokens Studio interface
3. **Push changes**: Commit and push changes back to this repo
4. **CI runs**: GitHub Actions automatically validate and transform tokens

## Development

### Using Tokens in React Native

Tokens in this repo mirror the theme structure in the DonateMate app:

```typescript
// In donatemate-app/src/styles/themes/lightTheme.ts
const lightTheme = {
  colors: {
    text: {
      primary: '#0F172A',    // → light.text.primary
      secondary: '#64748B',  // → light.text.secondary
    },
    // ...
  },
  sizes: {
    sm: 16,  // → global.spacing.sm
    md: 20,  // → global.spacing.md
  },
  // ...
};
```

### Validating Tokens

```bash
# Validate JSON syntax
node -e "require('./tokens.json')"
```

## Related Resources

- [DonateMate App Repository](https://github.com/donate-mate/donatemate-app)
- [Tokens Studio Documentation](https://docs.tokens.studio/)
- [Design Tokens Community Group](https://www.w3.org/community/design-tokens/)
