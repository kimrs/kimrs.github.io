# Twill — Hugo Theme

A custom Hugo theme for [solstad.dev](https://solstad.dev), the personal site of Kim Rune Solstad. Twill communicates **warmth and competency** — its visual language is inspired by smart casual Scandinavian style: trousers, shirt, sweater, brown leather derbys. Every color in the palette is drawn from that wardrobe: brown, olive, beige, and marine blue.

The target audience is fellow developers evaluating Kim as a freelance software development consultant. The design should feel like a well-curated outfit — intentional, not flashy.

---

## Color Palette

The palette is called **"Full Wardrobe"**. It blends two outfit palettes (brown/olive and beige/marine blue) into a single cohesive scheme. Every color has a role, and nothing is decorative for its own sake.

### Light Mode

| Role             | Name       | Hex       | CSS Variable              | Usage                              |
|------------------|------------|-----------|---------------------------|------------------------------------|
| Dark primary     | Deep Navy  | `#1E3044` | `--color-dark-primary`    | Header, footer, body text          |
| Dark secondary   | Forest     | `#2D3E2A` | `--color-dark-secondary`  | Header gradient end                |
| Mid accent       | Olive      | `#4A5E3C` | `--color-mid-accent`      | Section titles, tags, secondary text |
| Warm accent      | Cognac     | `#9B7340` | `--color-warm-accent`     | Links, buttons, hover states, CTAs |
| Light accent     | Wheat      | `#C9B896` | `--color-light-accent`    | Borders, dividers, subtle backgrounds |
| Background       | Cream      | `#F4F0E8` | `--color-background`      | Page background                    |
| Surface          | Sand       | `#E8E2D6` | `--color-tag-bg`          | Tag backgrounds, inline code bg    |
| Text tertiary    | Muted Olive| `#6B7B5C` | `--color-text-tertiary`   | Meta info, dates, captions         |

**Header gradient:**
```css
linear-gradient(135deg, #1E3044 0%, #2D3E2A 100%)
```

### Dark Mode — "Warm Charcoal"

Brown-tinted grays that stay warm without competing with code syntax highlighting. The key principle: dark mode should never feel cold or blue — it uses the same warm undertones as the light palette.

| Role             | Name           | Hex       | CSS Variable              | Usage                              |
|------------------|----------------|-----------|---------------------------|------------------------------------|
| Background       | Warm Black     | `#1A1816` | `--color-background`      | Page background                    |
| Surface          | Dark Brown     | `#242018` | `--color-dark-secondary`  | Cards, code blocks, raised surfaces|
| Border           | Charcoal Brown | `#302A22` | `--color-border`          | Borders, dividers, blockquote rules|
| Text primary     | Warm Cream     | `#E0D8C8` | `--color-text`            | Headings, primary body text        |
| Text secondary   | Muted Tan      | `#B8B0A0` | `--color-text-secondary`  | Body prose, paragraphs             |
| Text tertiary    | Warm Gray      | `#8A8070` | `--color-text-tertiary`   | Meta info, dates, captions         |
| Mid accent       | Sage           | `#7A9A6A` | `--color-mid-accent`      | Section titles, tags, code keywords|
| Warm accent      | Cognac         | `#C49A5C` | `--color-warm-accent`     | Links, buttons, hover states       |
| Inline code bg   | Dark Leather   | `#2A2420` | `--color-inline-code-bg`  | Inline code background, tag bg     |
| Code block bg    | Deep Black     | `#0E0C0A` | `--color-code-bg`         | Code blocks, footer background     |

**Header gradient (dark):**
```css
linear-gradient(135deg, #141210 0%, #121A14 100%)
```

### Design Rationale

The warm undertone across both modes is deliberate. Most developer sites default to cool grays and blues — Twill's palette says "this person has taste beyond the defaults." Cognac is the throughline: it's the link color in both modes, tying interaction to the brown leather of the wardrobe metaphor. Olive/Sage provides the secondary accent and shifts appropriately between modes to maintain contrast without changing character.

---

## Typography

| Role        | Font              | Weight        | CSS Variable      | Usage                              |
|-------------|-------------------|---------------|-------------------|------------------------------------|
| Headings    | Plus Jakarta Sans | 700 (Bold)    | `--font-heading`  | Article titles, section headings, nav |
| UI text     | Plus Jakarta Sans | 500–600       | `--font-heading`  | Meta info, labels, buttons, links  |
| Body        | Bitter            | 400 (Regular) | `--font-body`     | Article prose, blockquotes         |
| Body bold   | Bitter            | 600           | `--font-body`     | Inline emphasis                    |
| Body italic | Bitter            | 400 italic    | `--font-body`     | Blockquotes, citations             |
| Code        | JetBrains Mono   | 400           | `--font-code`     | Inline code, code blocks           |

### Google Fonts Import

```css
@import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700&family=Bitter:ital,wght@0,400;0,600;1,400&family=JetBrains+Mono:wght@400&display=swap');
```

### Rationale

Plus Jakarta Sans has subtle geometric curves that feel designed and intentional — distinctive without being flashy. Bitter was built for screen reading, with slab-influenced shapes that are wide and sturdy. Together they communicate craftsmanship: someone who chose deliberately rather than defaulting to the norm. JetBrains Mono is the natural choice for a developer's code samples.

---

## Icons

The theme uses **hand-drawn inline SVGs** in the Feather icon style (stroke-based, `stroke-width="2"`, `stroke-linecap="round"`, `stroke-linejoin="round"`). No icon library is loaded — each icon is embedded directly in the template HTML for zero external dependencies.

### Icon Set

| Icon     | Context              | Size   | Default Opacity | Hover Opacity |
|----------|----------------------|--------|-----------------|---------------|
| GitHub   | Nav + Footer social  | 20×20  | 0.5             | 1.0           |
| LinkedIn | Nav + Footer social  | 20×20  | 0.5             | 1.0           |
| YouTube  | Nav + Footer social  | 20×20  | 0.5             | 1.0           |
| Moon     | Theme toggle (light) | 18×18  | 0.5             | 1.0           |
| Sun      | Theme toggle (dark)  | 18×18  | 0.5             | 1.0           |

### Style Rules for New Icons

If you need to add icons, follow these conventions:

- Use inline SVG, not an icon font or image
- Stroke-based, not filled (`fill="none"`, `stroke="currentColor"`)
- `stroke-width="2"`, `stroke-linecap="round"`, `stroke-linejoin="round"`
- Viewbox: `0 0 24 24`
- Color inherited from parent via `currentColor`
- Consistent with Feather Icons (https://feathericons.com) style

---

## Spacing & Layout

The reading experience should feel **considered and unhurried** — each idea has room to land.

| Property                    | Value           | Notes                              |
|-----------------------------|-----------------|-------------------------------------|
| Content max-width           | `740px`         | ~75 chars/line at body size         |
| Body font size              | `1.125rem` (18px)| Slightly larger than default       |
| Body line-height            | `1.75`          | Generous — lets the eye rest        |
| Paragraph gap               | `1.5rem`        | Clear separation                    |
| Section break (h2)          | `3rem` top / `1.25rem` bottom | New thought, not new page |
| Code/blockquote margin      | `2rem`          | Visually separated from prose       |
| Content padding (desktop)   | `1.5rem`        | Side padding                        |
| Content padding (mobile)    | `1.25rem`       | Slightly tighter                    |
| Border radius (code, images)| `6px`           | Consistent rounding everywhere      |

### Responsive Breakpoint

Single breakpoint at `768px`. Below it: body font drops to `1rem`, h1 to `1.75rem`, date columns hide in favor of inline dates, social icons move from nav to footer only.

---

## Syntax Highlighting

Code blocks use a dark inset style in both modes — no line numbers, no language label, no copy button.

| Token     | Light Mode          | Dark Mode           |
|-----------|---------------------|---------------------|
| Keywords  | `#2D3E2A` (Forest)  | `#8BA07A` (Sage)    |
| Strings   | `#9B7340` (Cognac)  | `#C49A5C` (Cognac)  |
| Comments  | `#8A8A78` (Muted)   | `#5A5548` (Muted)   |
| Functions | `#1E3044` (Navy)    | `#E0D8C8` (Cream)   |
| Numbers   | `#6B5B3A` (Brown)   | `#C49A5C` (Cognac)  |
| Operators | `#4A5E3C` (Olive)   | `#7A9A6A` (Sage)    |
| Types     | `#4A5E3C` (Olive)   | `#7A9A6A` (Sage)    |

---

## Component Quick Reference

### Links
Cognac colored, no underline by default. Underline on hover with `text-underline-offset: 3px`. No visited color change (purple clashes with the warm palette).

### Tag Pills
Small, uppercase, understated: Plus Jakarta Sans 600, `0.68rem`, `letter-spacing: 0.06em`. Light mode: sand bg + olive text. Dark mode: dark leather bg + sage text.

### Blockquotes
Left border (`3px solid` wheat/charcoal), no background, Bitter italic, secondary text color. A quiet aside — not a pull-quote.

### Images
Full content width, `border-radius: 6px`, no shadow. Captions in Plus Jakarta Sans 400, `0.78rem`, tertiary color, centered.

### Tables
Minimal: header row with `2px` bottom border, body rows with `1px` dividers. No alternating row colors.

---

## Dark Mode Behavior

The theme supports both system preference detection (`prefers-color-scheme`) and a manual toggle. User choice persists in `localStorage`. If no explicit choice exists, the OS preference is followed.

All mode transitions use `transition: background-color 0.3s ease, color 0.3s ease` for a smooth shift.

---

## Accessibility

- WCAG 2.1 AA contrast ratios (4.5:1 body text, 3:1 large text)
- Focus states: `2px solid` cognac outline with `outline-offset: 2px` on all interactive elements
- Skip-to-content link hidden until focused
- All social icons carry `aria-label` attributes
- Semantic HTML throughout (`nav`, `main`, `article`, `header`, `footer`)

---

## Presentation Theme (Reveal.js)

Talks use a matching dark-mode Reveal.js theme (`reveal-twill.css`) with the same color variables prefixed `--rt-`. Background is Warm Black (`#1A1816`), accent is Cognac (`#C49A5C`), and the header gradient matches the site dark mode.

---

## For AI Agents

When creating assets (thumbnails, social images, slides, documents, videos) that should feel visually congruent with this site, follow these principles:

1. **Use the palette literally.** Cream/Warm Black backgrounds, Cognac for highlights and CTAs, Olive/Sage for secondary emphasis. Never introduce blues, purples, or cool grays.
2. **Warm undertones always.** Even "neutral" grays should lean brown, never blue. When in doubt, compare against `#1A1816` (dark) or `#F4F0E8` (light) — anything that looks cold next to them is wrong.
3. **Typography pairing.** Plus Jakarta Sans for display/UI, Bitter for body text, JetBrains Mono for code. If these fonts aren't available, substitute geometric sans-serif / slab serif / monospace — never use Helvetica, Arial, or system defaults.
4. **Stroke-based icons.** Feather-style, 2px stroke, round caps. Never filled icons, never emoji as UI.
5. **Generous whitespace.** The design breathes. Don't crowd elements. When in doubt, add more space.
6. **No decorative elements.** No gradients for decoration (only the header uses one, and it's subtle). No drop shadows except very faint card shadows. No rounded-to-circle avatars. Corners are `6px` when rounded.
7. **Understated confidence.** The personality comes through restraint and material quality, not loud choices. Think: well-made leather bag, not neon sneakers.
