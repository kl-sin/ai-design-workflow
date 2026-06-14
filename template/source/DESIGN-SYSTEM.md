# DESIGN-SYSTEM.md
> Source doc — implementation truth. Owned by the Designer/Engineer roles.
> The UI spec the AI builds against: tokens, component recipes, layout patterns, behavior rules.
> This is what makes AI-generated screens look like the real product instead of generic software.
>
> KEY IDEA: if you have no design files, you reconstruct this from the live product —
> `getComputedStyle` in the browser for exact values, screenshots for layout. Always mark
> which values are exact (DOM-confirmed) vs approximate (screenshot-observed) so the AI
> knows what it can trust.

---

## 1. Tokens

### 1.1 Source / confidence
| Type | Source | Confidence |
|---|---|---|
| DOM-confirmed | `getComputedStyle` on the live product | Exact |
| Screenshot-observed | reference screenshots only | Approximate unless noted |

### 1.2 CSS custom properties
> Define brand, text, surface, status, typography, spacing, and radius tokens as variables.

```css
:root {
  /* brand */
  --brand-primary: [#hex];
  /* text */
  --text-body: [#hex];
  /* surfaces */
  --surface: [#hex];
  --bg-page: [#hex];
  /* status */
  --status-error: [#hex];
  /* typography */
  --font-sans: [stack];
  --fs-body: [px];
  /* spacing & radius */
  --radius-default: [px];
}
```

### 1.3 Hard rules
**Do:** [e.g. use size + color for hierarchy]
**Don't:** [e.g. invent colors not grounded in DOM or screenshots]

---

## 2. Controls
> Component recipes — buttons, inputs, selects, pills, tabs. Give each a CSS recipe and note
> whether it's DOM-confirmed or screenshot-observed.

### `control/[name]`
```css
.[class] { /* recipe */ }
```

---

## 3. Patterns / Pages
> Larger layout patterns — nav, sidebars, list rows, panels, preview pages. Describe structure
> and spacing rhythm.

### `pattern/[name]`
- [structure notes]

---

## 4. Behaviors
> Interaction rules that aren't visual — what a control does, what context it belongs in,
> what must stay consistent.

### `behavior/[name]`
**Rule:** [the rule]

---

## 5. Implementation notes

### Reuse order
1. use DOM-confirmed tokens first
2. apply screenshot-observed patterns second
3. label anything approximate

### Safe defaults for future prototypes
- use tokenized CSS variables
- keep distinct surface types visually distinct
- keep control heights consistent within one surface
- prefer white space over decorative separators
- use exact values only when confirmed
