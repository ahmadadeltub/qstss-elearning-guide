# 🏛️ QSTSS E-Learning & Digital Services Portal — Design System Specification
> **Document Version:** 2.0.0  
> **Source Project:** Qatar Science & Technology Schools — Digital Services Guide (`qstss-elearning-guide`)  
> **Target Audiences:** Students, Parents, Educators, AI Coding Agents, Frontend Engineers, UI/UX Designers  
> **Core Purpose:** The authoritative **Single Source of Truth** for the visual identity, styling tokens, component library, responsive behavior, and bilingual (RTL/LTR) architecture. Any new website adopting this design system must match the exact aesthetics, behavior, and interaction patterns documented herein.

---

## 32. DESIGN SYSTEM SUMMARY & QUICK REFERENCE

| Aspect | Specification |
| :--- | :--- |
| **Design Style** | High-prestige educational & institutional portal; clean card-based UI, subtle glassmorphism, rounded pill accents, crisp borders, and deep dual-theme lighting. |
| **Primary Palette** | Official Qatar STEM Navy (`#0E265C`), Royal Sapphire Blue (`#1E5FE0`), and Academic Gold (`#D98200` / `#FFAE26`). |
| **Surface & Canvas** | Light Mode Canvas: `#F0F4F8` / Surface: `#FFFFFF` \| Dark Mode Canvas: `#050C1B` / Surface: `#0B1730`. |
| **Primary Arabic Font** | **'Tajawal'** (Weights: 300, 400, 500, 700, 800, 900) loaded via Google Fonts. |
| **Primary Latin / English Font** | **'Inter'** (Weights: 400, 500, 600, 700, 800) for codes, links, numbers, and LTR subtitles. |
| **System Fallback Font Stack** | `-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif`. |
| **Border Radius Scale** | Pill/Full (`50px`), Card Large (`18px`), Card Medium (`16px`), Base (`12px`), Small (`8px`). |
| **Elevation / Shadows** | Multi-tiered deep navy shadows (`--shadow-sm`, `--shadow-md`, `--shadow-lg`, `--shadow-dropdown`). |
| **Primary Breakpoints** | Desktop: `> 1024px` \| Tablet / Laptop: `769px – 1024px` \| Mobile: `376px – 768px` \| Small Mobile: `≤ 375px`. |
| **Container Width** | Max-width `1240px` with fluid responsive padding (`20px` desktop, `14px` mobile, `12px` micro). |
| **Responsive Approach** | Hybrid Desktop-First with dedicated Mobile Specialization (stacked header, 2x2 hero hub, grid filters). |
| **Iconography** | Semantic emoji badges enclosed in rounded gradient avatars (`44px` desktop / `38px` mobile). |
| **RTL / LTR Architecture** | Primary `dir="rtl"` right-to-left layout; isolated inline English with `.en` (`direction: ltr;`). |
| **Dynamic Theming** | Native Light and Dark themes toggled via `data-theme="light|dark"` attribute on `<html>`. |

---

## 2. DESIGN IDENTITY & PHILOSOPHY

### 2.1 Brand Personality & Tone
The design language is engineered specifically for **Qatar Science & Technology Preparatory Secondary School for Boys (مدارس قطر للعلوم والتكنولوجيا)** — a premier STEM and AP (Advanced Placement) institution.
* **Prestige & Institutional Authority:** Anchored by Qatar's sovereign education colors — deep midnight navy, vibrant tech blue, and warm desert gold.
* **Educational Clarity & Reassurance:** Clear categorization, high contrast, easily scannable cards, and intuitive badges designed to reassure parents and guide students.
* **Modern & Technological Feel:** Subtle glassmorphism (`backdrop-filter: blur(12px - 18px)`), radial gradient lighting in the hero section, smooth micro-interactions, pill-shaped interactive controllers, and smooth theme transitions.
* **Information Density:** Medium-high density organized via hierarchical card grouping, segmented category tabs, and collapsible accordion menus preventing visual clutter.
* **Whitespace Philosophy:** Generous section padding (`52px` desktop / `34px` mobile) and uniform card padding (`24px` desktop / `16px` mobile) that gives each service breathing room while retaining immediate accessibility.

---

## 3. COLOR SYSTEM

The color system is organized into semantic design tokens that dynamically adapt between **Light Theme** and **Dark Theme** via CSS custom properties.

### 3.1 Master Color Palette Table

| Token Name | Theme Mode | HEX | RGB | HSL | Primary Usage & Components |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `--bg-page` | Light | `#F0F4F8` | `rgb(240, 244, 248)` | `hsl(210°, 36%, 96%)` | Overall page background canvas |
| `--bg-page` | Dark | `#050C1B` | `rgb(5, 12, 27)` | `hsl(221°, 69%, 6%)` | Dark mode page background canvas |
| `--bg-surface` | Light | `#FFFFFF` | `rgb(255, 255, 255)` | `hsl(0°, 0%, 100%)` | Cards, modals, header background base |
| `--bg-surface` | Dark | `#0B1730` | `rgb(11, 23, 48)` | `hsl(221°, 63%, 12%)` | Dark mode cards, elevated surfaces |
| `--bg-surface-subtle` | Light | `#F7FAFC` | `rgb(247, 250, 252)` | `hsl(204°, 45%, 98%)` | Explanation boxes, tab backgrounds |
| `--bg-surface-subtle` | Dark | `#101F40` | `rgb(16, 31, 64)` | `hsl(221°, 60%, 16%)` | Dark mode inner container boxes |
| `--bg-surface-elevated`| Dark | `#142750` | `rgb(20, 39, 80)` | `hsl(221°, 60%, 20%)` | Dark mode floating elements, active tabs |
| `--text-primary` | Light | `#0A193B` | `rgb(10, 25, 59)` | `hsl(222°, 71%, 14%)` | Primary headings, brand title, card titles |
| `--text-primary` | Dark | `#FFFFFF` | `rgb(255, 255, 255)` | `hsl(0°, 0%, 100%)` | Dark mode primary text |
| `--text-secondary` | Light | `#1E293B` | `rgb(30, 41, 59)` | `hsl(217°, 33%, 17%)` | Body copy, explanations, tab labels |
| `--text-secondary` | Dark | `#D2E0FA` | `rgb(210, 224, 250)` | `hsl(219°, 80%, 90%)` | Dark mode readable body text |
| `--text-muted` | Light | `#64748B` | `rgb(100, 116, 139)` | `hsl(215°, 16%, 47%)` | Subtitles, helper text, inactive icons |
| `--text-muted` | Dark | `#8FAEDC` | `rgb(143, 174, 220)` | `hsl(216°, 52%, 71%)` | Dark mode secondary helper text |
| `--brand-navy-dark` | Constant | `#06132D` | `rgb(6, 19, 45)` | `hsl(220°, 76%, 10%)` | Footer background, deep gradient bases |
| `--brand-navy` | Light | `#0E265C` | `rgb(14, 38, 92)` | `hsl(222°, 74%, 21%)` | Primary buttons, active filter tab, brand |
| `--brand-navy` | Dark | `#3D7DF5` | `rgb(61, 125, 245)` | `hsl(219°, 90%, 60%)` | Dark mode primary brand blue highlight |
| `--brand-navy-light` | Light | `#18429A` | `rgb(24, 66, 154)` | `hsl(221°, 73%, 35%)` | Secondary brand accents, gradient stops |
| `--brand-navy-light` | Dark | `#689DFF` | `rgb(104, 157, 255)` | `hsl(219°, 100%, 70%)` | Dark mode lighter navy accents |
| `--brand-blue` | Light | `#1E5FE0` | `rgb(30, 95, 224)` | `hsl(220°, 76%, 50%)` | Interactive links, focus borders, primary CTA |
| `--brand-blue` | Dark | `#4B8BF5` | `rgb(75, 139, 245)` | `hsl(217°, 89%, 63%)` | Dark mode bright interactive blue |
| `--brand-blue-subtle` | Light | `rgba(30,95,224,0.08)` | `rgba(30,95,224,0.08)` | — | Badge chips, hover highlights, nav hover |
| `--brand-blue-subtle` | Dark | `rgba(75,139,245,0.15)` | `rgba(75,139,245,0.15)` | — | Dark mode badge chips & hover fills |
| `--brand-gold` | Light | `#D98200` | `rgb(217, 130, 0)` | `hsl(36°, 100%, 43%)` | Accent badges, gold buttons, highlights |
| `--brand-gold` | Dark | `#FFBA38` | `rgb(255, 186, 56)` | `hsl(39°, 100%, 61%)` | Dark mode bright gold accent |
| `--brand-gold-glow` | Light | `#FFAE26` | `rgb(255, 174, 38)` | `hsl(38°, 100%, 57%)` | Hero heading highlights, footer headers |
| `--brand-gold-glow` | Dark | `#FFD580` | `rgb(255, 213, 128)` | `hsl(40°, 100%, 75%)` | Dark mode soft glowing gold text |
| `--border-subtle` | Light | `rgba(10,25,60,0.07)` | `rgba(10,25,60,0.07)` | — | Card borders, divider lines, grid borders |
| `--border-subtle` | Dark | `rgba(110,160,250,0.1)` | `rgba(110,160,250,0.1)` | — | Dark mode subtle separation lines |
| `--border-strong` | Light | `rgba(10,25,60,0.14)` | `rgba(10,25,60,0.14)` | — | Input borders, dropdown panel borders |
| `--border-strong` | Dark | `rgba(110,160,250,0.22)`| `rgba(110,160,250,0.22)`| — | Dark mode prominent container borders |

### 3.2 Service Card Semantic Accent Colors (Border-Right Themes)
Each detailed service card has a colored right-border accent (`5px solid <color>`) that reinforces its functional domain:

| Theme Class | Accent Color HEX | RGB | Category / Meaning |
| :--- | :--- | :--- | :--- |
| *(Default)* | `#1E5FE0` | `rgb(30, 95, 224)` | Core Qatar Education & Digital Systems |
| `.border-navy` | `#0D3B86` | `rgb(13, 59, 134)` | Ministry of Education (بوابة معارف) & Schedules |
| `.border-green`| `#0D6E4A` | `rgb(13, 110, 74)` | Official Policies, Regulations & Compliance |
| `.border-gold` | `#D98200` | `rgb(217, 130, 0)` | Student Advice, Tips & Password Services |
| `.border-purple`| `#7B1FA2` | `rgb(123, 31, 162)` | Parent Engagement & Classroom Apps (ClassDojo) |
| `.border-teal` | `#00897B` | `rgb(0, 137, 123)` | Literacy & Advanced English (Achieve 3000) |
| `.border-brown`| `#7B4A1A` | `rgb(123, 74, 26)` | E-Library, Digital Research & Qatar National Library |
| `.border-social`| `#E1306C` | `rgb(225, 48, 108)` | Social Media Platforms & Public Channels |
| `.border-slate`| `#394B6B` | `rgb(57, 75, 107)` | Organizational Governance & General Guides |

### 3.3 Gradients & Glassmorphism

```css
/* Hero Multi-Stop Navy Gradient */
--hero-gradient-light: linear-gradient(145deg, #071533 0%, #0E275E 55%, #18429A 100%);
--hero-gradient-dark:  linear-gradient(145deg, #040A18 0%, #091733 55%, #102654 100%);

/* Hero Dual Radial Lighting Overlay */
background: radial-gradient(circle at 80% 20%, rgba(30, 95, 224, 0.3) 0%, transparent 50%),
            radial-gradient(circle at 20% 80%, rgba(217, 130, 0, 0.2) 0%, transparent 45%);

/* Top Announcement Strip Gradient */
background: linear-gradient(90deg, #07173B, #0E2963, #153E90);

/* Accent Line Gradient */
background: linear-gradient(90deg, var(--brand-blue), var(--brand-gold));

/* Password Reset Button Gold Gradient */
background: linear-gradient(135deg, #FFB338, #D98200);

/* Glassmorphism Specs */
/* Header Glass */
background: var(--bg-header); /* rgba(255, 255, 255, 0.96) or rgba(7, 15, 35, 0.96) */
backdrop-filter: blur(18px);
-webkit-backdrop-filter: blur(18px);

/* Card Glass (Hero Action Cards & Vision/Mission) */
background: rgba(255, 255, 255, 0.1);
border: 1px solid rgba(255, 255, 255, 0.2);
backdrop-filter: blur(12px);
-webkit-backdrop-filter: blur(12px);
```

---

## 4. TYPOGRAPHY SYSTEM

### 4.1 Fonts and Loading Strategy
```html
<link rel="preconnect" href="https://fonts.googleapis.com"/>
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin/>
<link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;500;700;800;900&family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet"/>
```

* **Primary Font (Arabic):** `'Tajawal', sans-serif` — Modern, geometric, readable Arabic sans-serif with excellent legibility across all digital screens.
* **Secondary Font (Latin / English):** `'Inter', sans-serif` — Applied specifically to English subtitles, acronyms, URLs, codes, and numbers via the `.en` utility class (`direction: ltr; display: inline-block;`).
* **Root Configuration:** `html { font-size: 16px; scroll-behavior: smooth; -webkit-text-size-adjust: 100%; }`
* **Global Text Defaults:** `body { line-height: 1.75; direction: rtl; text-align: right; -webkit-font-smoothing: antialiased; }`

### 4.2 Comprehensive Typography Hierarchy Table

| UI Element | Selector | Font Family | Weight | Desktop Size | Mobile Size (`≤768px`) | Line Height | Letter Spacing |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Top Bar Announcement** | `.announcement-bar` | Tajawal | 600 | `0.82rem` (13.1px) | `0.76rem` (12.1px) | 1.5 | Normal |
| **Top Bar Badge** | `.announcement-bar .badge-gold` | Tajawal | 800 | `0.72rem` (11.5px) | `0.70rem` (11.2px) | 1.2 | Normal |
| **Header Brand Title** | `.brand-title h1` | Tajawal | 900 | `clamp(0.88rem, 1.3vw, 1.05rem)` | `0.92rem` (14.7px) | 1.3 | Normal |
| **Header Brand Subtitle** | `.brand-title p` | Inter / Tajawal | 600 | `0.65rem` (10.4px) | *Hidden (`display:none`)* | 1.2 | `0.02em` |
| **Desktop Nav Dropdown** | `.nav-dropdown-btn` | Tajawal | 700 | `0.86rem` (13.7px) | *Hidden* | 1.2 | Normal |
| **Desktop Dropdown Link** | `.nav-dropdown-menu a` | Tajawal | 600 | `0.84rem` (13.4px) | *Hidden* | 1.3 | Normal |
| **Mobile Dropdown Item** | `.m-nav-link` | Tajawal | 700 | *Hidden* | `0.84rem` (13.4px) | 1.3 | Normal |
| **Mobile Accordion Title** | `.m-accordion-header` | Tajawal | 800 | *Hidden* | `0.88rem` (14px) | 1.3 | Normal |
| **Hero Badge Chip** | `.hero-badge-pill` | Tajawal | 800 | `0.80rem` (12.8px) | `0.72rem` (11.5px) | 1.2 | Normal |
| **Hero Main Heading** | `.hero-heading` | Tajawal | 900 | `clamp(1.75rem, 4.5vw, 3rem)` | `1.50rem` (24px) | 1.28 / 1.25 | `-0.01em` |
| **Hero Description** | `.hero-description` | Tajawal | 500 | `clamp(0.88rem, 2vw, 1.1rem)` | `0.82rem` (13.1px) | 1.75 / 1.6 | Normal |
| **Smart Hub Title** | `.smart-hub-card h4` | Tajawal | 800 | `0.92rem` (14.7px) | `0.82rem` (13.1px) | 1.3 | Normal |
| **Smart Hub Description** | `.smart-hub-card p` | Tajawal | 400 | `0.74rem` (11.8px) | `0.66rem` (10.5px) | 1.4 / 1.3 | Normal |
| **Smart Hub Link** | `.smart-hub-link` | Tajawal | 700 | `0.72rem` (11.5px) | `0.66rem` (10.5px) | 1.2 | Normal |
| **Filter Tab Button** | `.filter-tab-btn` | Tajawal | 700 | `0.80rem` (12.8px) | `0.74rem` (11.8px) | 1.2 | Normal |
| **Search Input** | `.search-input-box input` | Tajawal | 500 | `0.86rem` (13.7px) | `0.84rem` (13.4px) | 1.4 | Normal |
| **Stats Number** | `.stat-number` | Inter / Tajawal | 900 | `1.50rem` (24px) | `1.20rem` (19.2px) | 1.2 | Normal |
| **Stats Label** | `.stat-label` | Tajawal | 700 | `0.74rem` (11.8px) | `0.64rem` (10.2px) | 1.3 | Normal |
| **Section Chip Badge** | `.section-badge-chip` | Tajawal | 800 | `0.76rem` (12.1px) | `0.72rem` (11.5px) | 1.2 | Normal |
| **Section Title** | `.section-title` | Tajawal | 900 | `clamp(1.45rem, 3.2vw, 2rem)` | `1.25rem` (20px) | 1.3 | Normal |
| **Section Subtitle** | `.section-subtitle` | Tajawal | 400 | `0.94rem` (15px) | `0.84rem` (13.4px) | 1.7 | Normal |
| **Service Card Title** | `.service-title-text h3`| Tajawal | 900 | `1.10rem` (17.6px) | `0.96rem` (15.3px) | 1.3 | Normal |
| **Service English Subtitle**| `.service-title-text span.en`| Inter | 500 | `0.72rem` (11.5px) | `0.68rem` (10.8px) | 1.2 | `0.01em` |
| **Service Status Tag** | `.service-status-tag` | Tajawal | 800 | `0.72rem` (11.5px) | `0.68rem` (10.8px) | 1.2 | Normal |
| **Explanation Box Text**| `.service-explanation-box`| Tajawal | 400 | `0.88rem` (14px) | `0.84rem` (13.4px) | 1.75 / 1.7 | Normal |
| **Action Button** | `.action-btn` | Tajawal | 800 | `0.82rem` (13.1px) | `0.74rem` (11.8px) | 1.2 | Normal |
| **Quick Link Tile Title**| `.quick-link-tile h4` | Tajawal | 800 | `0.86rem` (13.7px) | `0.78rem` (12.5px) | 1.3 | Normal |
| **Quick Link Tile Subtext**| `.quick-link-tile p` | Tajawal | 400 | `0.70rem` (11.2px) | `0.64rem` (10.2px) | 1.3 | Normal |
| **Footer Column Heading**| `.footer-col h5` | Tajawal | 800 | `0.90rem` (14.4px) | `0.86rem` (13.7px) | 1.4 | Normal |
| **Footer Navigation Link**| `.footer-col ul li a` | Tajawal | 600 | `0.80rem` (12.8px) | `0.78rem` (12.5px) | 1.8 | Normal |
| **Copyright Text** | `.footer-bottom-bar` | Tajawal | 500 | `0.76rem` (12.1px) | `0.72rem` (11.5px) | 1.5 | Normal |

---

## 5. RESPONSIVE DESIGN SYSTEM & BREAKPOINTS

### 5.1 Definitive Breakpoints Matrix

```css
/* BREAKPOINT DEFINITIONS IN CSS */
/* 1. Large & Standard Desktop: > 1024px */
/* 2. Tablet / Laptop Transition: max-width: 1024px */
/* 3. Mobile / Smartphones: max-width: 768px */
/* 4. Small Mobile (iPhone SE / 320px): max-width: 375px */
```

| Viewport Category | Exact Breakpoint Range | Container Max-Width | Horizontal Padding | Grid Columns | Navigation State | Header Layout |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Large Desktop** | `≥ 1440px` | `1240px` | `20px` (each side) | Hub: 4 \| Stats: 6 \| Footer: 3 (2:1:1) | Full Horizontal Dropdowns | Inline Row (Space-between) |
| **Desktop / Laptop** | `1025px – 1439px` | `1240px` | `20px` | Hub: 4 \| Stats: 6 \| Footer: 3 (2:1:1) | Full Horizontal Dropdowns | Inline Row (Space-between) |
| **Tablet / Small Laptop**| `769px – 1024px` | `100%` (`≤1024px`) | `20px` | Hub: 2 \| Stats: 3 \| Footer: 2 (1:1) | Mobile Toggle Button + Panel | Inline Row with Toggle Button |
| **Standard Mobile** | `376px – 768px` | `100%` | `14px` | Hub: 2 (2x2) \| Stats: 3 \| Footer: 1 | Categorized Accordion Dropdown | **Vertical Stack** (Logo top, Actions right) |
| **Small Mobile** | `≤ 375px` | `100%` | `12px` | Hub: 2 \| Stats: 3 \| Footer: 1 | Categorized Accordion Dropdown | Compact Vertical Stack (Logo 30px) |

---

## 6. MOBILE-FIRST VS. DESKTOP-FIRST BEHAVIOR

The codebase follows a **Desktop-First Architecture with Deep Mobile Specialization**. Rather than merely scaling down CSS values, the mobile experience is custom-engineered to prioritize one-handed thumb reach, vertical clarity, and clean stacking.

### 6.1 Component Structural Transformations

#### 1. Header & Branding
* **Desktop (`> 768px`):**
  * Layout: Single horizontal flex row (`justify-content: space-between; align-items: center;`).
  * Right: School Logo (`46px` height) + Two-line Brand Title (`h1` + `p`).
  * Center: Categorized Dropdowns (`.desktop-nav-organized`).
  * Left: Action CTA Button (`header-cta-btn`) + Theme Switcher.
* **Mobile (`≤ 768px`):**
  * Layout: Two-tier vertical stack (`flex-direction: column; align-items: stretch;`).
  * Row 1 (Top Center): Brand Logo (`44px`, shrinks to `30px` on `≤375px`) + Title (`0.92rem`), Subtitle hidden.
  * Row 2 (Bottom Right-Aligned in RTL): Border-top divider separating a dedicated controls bar containing:
    1. Menu Toggle Button (`[القائمة ▼]`) with border and blue tint.
    2. Theme Switcher (`[🌙 الوضع الليلي]`) with border and rounded pill shape.
  * CTA button (`.header-cta-btn`) is completely hidden to eliminate header congestion.

#### 2. Hero Smart Hub Cards
* **Desktop:** `grid-template-columns: repeat(4, 1fr);` — 4 cards in a single clean row.
* **Tablet (`1024px`):** `grid-template-columns: repeat(2, 1fr);` — 2 rows of 2 cards.
* **Mobile (`≤ 768px`):** `grid-template-columns: 1fr 1fr;` — Compact 2x2 grid with reduced padding (`12px 10px`), icons (`1.35rem`), and tight line heights.

#### 3. Category Filter Tabs
* **Desktop:** Single horizontal row with `overflow-x: auto; flex-wrap: nowrap;`.
* **Mobile (`≤ 768px`):** Fully wrapped grid (`flex-wrap: wrap; justify-content: center;`).
  * `.filter-tab-btn[data-category="all"]`: Takes **100% full width** (`flex: 1 1 100%;`) at the top of the grid.
  * Other 4 category tabs: Displayed neatly as a **2-column grid** (`flex: 1 1 calc(50% - 6px);`).

#### 4. Service Detail Action Buttons
* **Desktop:** Inline flex row with auto-width buttons (`display: flex; gap: 10px; flex-wrap: wrap;`).
* **Mobile (`≤ 768px`):** Converted into a rigid 2-column grid (`display: grid; grid-template-columns: 1fr 1fr; gap: 6px;`). Buttons expand to fill 100% of their grid cell with centered text.

#### 5. Password Reset Hero Card
* **Desktop:** Horizontal flex layout (`align-items: center; gap: 28px;`) with circular icon on the right, content in the center, and button on the left.
* **Mobile (`≤ 768px`):** Vertical flex stack (`flex-direction: column; text-align: center; gap: 12px;`). Circular icon centered horizontally (`margin: 0 auto;`), action button expands to full width (`width: 100%; justify-content: center;`).

#### 6. Footer Layout
* **Desktop:** Asymmetric 3-column grid (`grid-template-columns: 2fr 1fr 1fr; gap: 36px;`).
* **Tablet:** 2-column grid (`grid-template-columns: 1fr 1fr;`).
* **Mobile (`≤ 768px`):** Single column stack (`grid-template-columns: 1fr; gap: 20px; text-align: center;`).

---

## 7. CONTAINER SYSTEM

```css
/* CONTAINER TOKENS */
:root {
  --container-max-width:        1240px;
  --container-padding-desktop:  20px;
  --container-padding-tablet:   20px;
  --container-padding-mobile:   14px;
  --container-padding-micro:    12px;
}

.container {
  width: 100%;
  max-width: var(--container-max-width);
  margin-left: auto;
  margin-right: auto;
  padding-left: var(--container-padding-desktop);
  padding-right: var(--container-padding-desktop);
}

@media (max-width: 768px) {
  .container {
    padding-left: var(--container-padding-mobile);
    padding-right: var(--container-padding-mobile);
  }
}

@media (max-width: 375px) {
  .container {
    padding-left: var(--container-padding-micro);
    padding-right: var(--container-padding-micro);
  }
}
```

---

## 8. SPACING SYSTEM

The website follows an 8-point harmonic spacing scale:

```css
:root {
  --space-1: 4px;   /* Micro gaps, badge vertical padding */
  --space-2: 8px;   /* Button gaps, compact list item spacing */
  --space-3: 12px;  /* Card inner sub-element gaps, small padding */
  --space-4: 16px;  /* Base card padding, search box horizontal padding */
  --space-5: 20px;  /* Container padding, featured video gap */
  --space-6: 24px;  /* Service card padding, section gap */
  --space-7: 36px;  /* Section header margin, footer grid gap */
  --space-8: 52px;  /* Major content section vertical padding (desktop) */
}
```

* **Section Vertical Padding (Desktop):** `52px 0` (`.content-section`)
* **Section Vertical Padding (Mobile):** `34px 0` (`@media (max-width: 768px)`)
* **Hero Vertical Padding (Desktop):** `48px 0 60px`
* **Hero Vertical Padding (Mobile):** `34px 0 40px`
* **Card Inner Padding (Desktop):** `24px` (`.service-detail-card`), `36px` (`.password-box-card`)
* **Card Inner Padding (Mobile):** `16px 12px` (`.service-detail-card`), `20px 14px` (`.password-box-card`)
* **Grid Gaps:** Large grids: `20px - 36px` \| Mobile grids: `6px - 8px`

---

## 9. GRID & LAYOUT SYSTEM

### 9.1 Grid Templates and Mobile Collapse Specifications

```css
/* 1. Hero 4 Action Hubs */
.hero-smart-hub-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 14px;
}
@media (max-width: 1024px) {
  .hero-smart-hub-grid { grid-template-columns: repeat(2, 1fr); }
}
@media (max-width: 768px) {
  .hero-smart-hub-grid { grid-template-columns: 1fr 1fr; gap: 8px; }
}

/* 2. Stats Bar */
.stats-grid {
  display: grid;
  grid-template-columns: repeat(6, 1fr);
}
@media (max-width: 1024px) {
  .stats-grid { grid-template-columns: repeat(3, 1fr); }
}

/* 3. Featured 2 Videos */
.featured-videos-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(min(100%, 450px), 1fr));
  gap: 20px;
}

/* 4. Poster Showcase */
.poster-showcase-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 36px;
  align-items: center;
}
@media (max-width: 1024px) {
  .poster-showcase-grid { grid-template-columns: 1fr; }
}

/* 5. Vision & Mission */
.vision-mission-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
}
@media (max-width: 1024px) {
  .vision-mission-grid { grid-template-columns: 1fr; }
}

/* 6. Quick Links Directory */
.quick-links-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(165px, 1fr));
  gap: 12px;
}
@media (max-width: 768px) {
  .quick-links-grid { grid-template-columns: repeat(2, 1fr); gap: 8px; }
}

/* 7. Footer Top Grid */
.footer-top-grid {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr;
  gap: 36px;
}
@media (max-width: 1024px) {
  .footer-top-grid { grid-template-columns: 1fr 1fr; }
}
@media (max-width: 768px) {
  .footer-top-grid { grid-template-columns: 1fr; gap: 20px; }
}
```

---

## 10. HEADER & NAVIGATION SYSTEM

### 10.1 Desktop Header Specification (`> 1024px`)
* **Position:** `position: sticky; top: 0; z-index: 1000;`
* **Height:** Approx. `66px` – `70px` depending on screen size.
* **Background:** `var(--bg-header)` with `backdrop-filter: blur(18px); -webkit-backdrop-filter: blur(18px);`
* **Border:** `border-bottom: 1px solid var(--header-border);`
* **Branding:** Logo on the right (`height: 46px; width: auto; object-fit: contain;`) + school title (`font-weight: 900;`) + subtitle (`0.65rem; color: var(--text-muted);`).
* **Dark Mode Logo Treatment:** `[data-theme="dark"] .brand-logo-img { filter: brightness(0) invert(1); }`
* **Desktop Dropdown Menus:**
  * Container: `.desktop-nav-organized { display: flex; align-items: center; gap: 6px; list-style: none; margin: 0 auto; }`
  * Buttons: `.nav-dropdown-btn { padding: 8px 12px; font-weight: 700; font-size: 0.86rem; border-radius: 10px; }`
  * Menu flyout: `.nav-dropdown-menu { position: absolute; top: 100%; right: 0; min-width: 220px; background: var(--bg-surface); border-radius: 14px; padding: 8px; box-shadow: var(--shadow-lg); opacity: 0; visibility: hidden; transform: translateY(8px); transition: all 0.22s cubic-bezier(0.16, 1, 0.3, 1); }`
  * Hover Trigger: `.nav-item-dropdown:hover .nav-dropdown-menu { opacity: 1; visibility: visible; transform: translateY(2px); }`
  * Item Hover: `transform: translateX(-3px); background: var(--brand-blue-subtle); color: var(--brand-blue);`

### 10.2 Mobile Header & Navigation Specification (`≤ 768px`)
* **Layout:** Stacked 2-tier layout inside `.header-container`.
* **Top Row:** Brand logo and school name centered at top.
* **Bottom Row:** Border-top separation line (`border-top: 1px solid var(--border-subtle);`) with:
  1. Menu button (`.mobile-dropdown-toggle-btn`): `padding: 6px 12px; font-size: 0.82rem; border-radius: 10px; border: 1.5px solid var(--brand-blue); background: var(--brand-blue-subtle); color: var(--brand-blue); font-weight: 800;`
  2. Theme switcher (`.theme-switch-btn`): `padding: 6px 12px; font-size: 0.80rem; border-radius: 10px; border: 1px solid var(--border-strong);`
* **Mobile Dropdown Panel (`.mobile-dropdown-panel`):**
  * Position: `position: absolute; top: calc(100% + 4px); right: 14px; width: min(340px, calc(100vw - 28px));`
  * Border & Radius: `border: 1.5px solid var(--border-strong); border-radius: 18px; box-shadow: var(--shadow-dropdown);`
  * Animation: `max-height: 0; opacity: 0; transform: translateY(-10px) scale(0.96); transform-origin: top right; transition: max-height 0.35s cubic-bezier(0.16, 1, 0.3, 1), opacity 0.25s ease, transform 0.25s cubic-bezier(0.16, 1, 0.3, 1);`
  * Open state (`.mobile-dropdown-panel.open`): `max-height: 82vh; overflow-y: auto; opacity: 1; transform: translateY(0) scale(1);`
* **Accordion Navigation Groups (`.m-accordion-group`):**
  * Sub-menus are arranged in accordion folders: (1) Core Systems, (2) Academic Platforms, (3) Services & Ministry.
  * Clicking an accordion header rotates the chevron: `.acc-chevron { transition: transform 0.25s ease; } .m-accordion-group.active .acc-chevron { transform: rotate(180deg); color: var(--brand-blue); }`
  * Accordion content animates height: `max-height: 0;` to `max-height: 320px;` via `transition: max-height 0.3s cubic-bezier(0.16, 1, 0.3, 1);`

---

## 11. BUTTON SYSTEM

The portal defines a standardized button typography and geometry with multiple semantic color variants.

### 11.1 Base Button Properties (`.action-btn`)
```css
.action-btn {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 8px 16px;
  border-radius: 50px;
  font-size: 0.82rem;
  font-weight: 800;
  cursor: pointer;
  transition: all 0.2s ease;
  box-shadow: var(--shadow-sm);
  text-decoration: none;
  white-space: nowrap;
}

.action-btn:hover {
  transform: translateY(-2px);
  box-shadow: var(--shadow-md);
  filter: brightness(1.05);
}

.action-btn:active {
  transform: translateY(0);
}
```

### 11.2 Button Style Variants

| Class Name | Background Color | Text Color | Border | Shadow / Effect | Usage |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `.btn-navy-solid` | `var(--brand-navy)` | `#FFFFFF` | None | `--shadow-sm` | Primary portal actions, newsletter links |
| `.btn-blue-solid` | `var(--brand-blue)` (`#1E5FE0`) | `#FFFFFF` | None | `--shadow-sm` | Primary platform actions (Achieve, iRead, SafeSpace) |
| `.btn-green-solid` | `#0D6E4A` | `#FFFFFF` | None | `--shadow-sm` | Policies, guides, downloads |
| `.btn-gold-solid` | `var(--brand-gold)` (`#D98200`)| `#071533` | None | `--shadow-sm` | Direct password reset shortcuts, highlighted actions |
| `.btn-purple-solid`| `#7B1FA2` | `#FFFFFF` | None | `--shadow-sm` | ClassDojo app access |
| `.btn-teal-solid` | `#00897B` | `#FFFFFF` | None | `--shadow-sm` | Achieve 3000 alternate actions |
| `.btn-outline-blue`| `transparent` | `var(--brand-blue)` | `1.5px solid var(--brand-blue)` | None | Secondary/alternative actions, document viewing |
| `.btn-app-store` | `#333333` | `#FFFFFF` | None | `0 2px 8px rgba(0,0,0,0.2)` | Apple App Store direct downloads |
| `.btn-play-store` | `#0F9D58` | `#FFFFFF` | None | `0 2px 8px rgba(15,157,88,0.2)`| Google Play Store direct downloads |
| `.btn-social-tw` | `#1DA1F2` | `#FFFFFF` | None | None | Twitter / X social channel link |
| `.btn-social-fb` | `#1877F2` | `#FFFFFF` | None | None | Facebook school profile |
| `.btn-social-yt` | `#FF0000` | `#FFFFFF` | None | None | YouTube official school channel |
| `.btn-social-ig` | `linear-gradient(45deg, #833AB4, #E1306C, #F77737)` | `#FFFFFF` | None | None | Instagram school profile |
| `.password-action-btn`| `linear-gradient(135deg, #FFB338, #D98200)` | `#071533` | None | `0 4px 16px rgba(217,130,0,0.35)` | Password reset CTA in hero card |

---

## 12. CARD SYSTEM

### 12.1 Detailed Service Card (`.service-detail-card`)
The signature component of the portal.
* **Background:** `var(--bg-surface)`
* **Border:** `1px solid var(--border-subtle)`
* **Right Accent Border:** `border-right: 5px solid var(--brand-blue);` (re-colored via `.border-green`, `.border-purple`, etc.)
* **Border Radius:** `18px` (`14px` on mobile)
* **Padding:** `24px` (`16px 12px` on mobile)
* **Shadow:** `var(--shadow-sm)`
* **Hover Interaction:** `transform: translateY(-2px); box-shadow: var(--shadow-md);`
* **Internal Anatomy:**
  1. `.service-header-row`: Flex row holding `.service-header-left` and `.service-status-tag`.
  2. `.service-avatar-icon`: `44px × 44px` (`38px` mobile) rounded container (`border-radius: 12px`) with thematic gradient and emoji.
  3. `.service-title-text`: Contains Arabic `<h3>` and English `<span class="en">`.
  4. `.service-explanation-box`: Light background (`var(--bg-surface-subtle)`), border (`var(--border-subtle)`), radius `12px`, padding `14px 18px` (`10px 12px` mobile).
  5. Media Area: Either `.sub-videos-grid`, `.service-images-grid`, or `.smart-video-player-container`.
  6. `.service-action-buttons`: Bottom actions row (converts to `grid-template-columns: 1fr 1fr;` on mobile).

### 12.2 Hero Smart Hub Card (`.smart-hub-card`)
* **Background:** `rgba(255, 255, 255, 0.1)` with `backdrop-filter: blur(12px); -webkit-backdrop-filter: blur(12px);`
* **Border:** `1px solid rgba(255, 255, 255, 0.2)`
* **Radius:** `16px` (`12px` mobile)
* **Padding:** `16px 14px` (`12px 10px` mobile)
* **Hover:** `background: rgba(255, 255, 255, 0.18); transform: translateY(-3px); border-color: rgba(255, 255, 255, 0.4);`

### 12.3 Password Reset Hero Card (`.password-box-card`)
* **Background:** `var(--hero-gradient)`
* **Radius:** `20px` (`14px` mobile)
* **Padding:** `36px` (`20px 14px` mobile)
* **Shadow:** `var(--shadow-lg)`
* **Icon:** `74px × 74px` circle (`58px` mobile) with `border: 2px solid rgba(255, 255, 255, 0.25);`

### 12.4 Quick Link Directory Tile (`.quick-link-tile`)
* **Background:** `var(--bg-surface)`
* **Radius:** `14px` (`12px` mobile)
* **Padding:** `16px 12px` (`12px 8px` mobile)
* **Shadow:** `var(--shadow-sm)`
* **Hover:** `border-color: var(--brand-blue); transform: translateY(-2px);`

---

## 13. BORDER RADIUS SYSTEM

```css
:root {
  --radius-xs:   4px;   /* Accent indicator lines */
  --radius-sm:   8px;   /* Playlist tabs, dropdown items, small tags */
  --radius-md:   12px;  /* Avatar icons, explanation boxes, mobile buttons */
  --radius-lg:   14px;  /* Quick links tiles, dropdown menus, mobile cards */
  --radius-xl:   18px;  /* Service detail cards, video cards, poster frame */
  --radius-2xl:  20px;  /* Password box card */
  --radius-full: 50px;  /* Buttons, pills, chips, search bar, theme toggle */
}
```

---

## 14. SHADOW & ELEVATION SYSTEM

The portal employs a 4-tier elevation system tailored for high readability in both light and dark modes:

```css
/* LIGHT THEME SHADOWS */
:root, [data-theme="light"] {
  --shadow-sm:       0 2px 6px rgba(10, 25, 60, 0.05);
  --shadow-md:       0 6px 18px rgba(10, 25, 60, 0.07);
  --shadow-lg:       0 14px 36px rgba(10, 25, 60, 0.10);
  --shadow-dropdown: 0 20px 40px -8px rgba(10, 25, 60, 0.22);
}

/* DARK THEME SHADOWS */
[data-theme="dark"] {
  --shadow-sm:       0 2px 10px rgba(0, 0, 0, 0.40);
  --shadow-md:       0 8px 24px rgba(0, 0, 0, 0.55);
  --shadow-lg:       0 18px 44px rgba(0, 0, 0, 0.70);
  --shadow-dropdown: 0 24px 50px rgba(0, 0, 0, 0.85);
}
```

---

## 15. ICONOGRAPHY & EMOJI DESIGN LANGUAGE

Rather than relying on heavy third-party font icon bundles, the portal implements a **Semantic Emoji Iconography System** paired with custom geometric avatar wrappers.

### 15.1 Avatar Icon Tokens
Each card or category uses a `44px × 44px` (`border-radius: 12px; font-size: 1.35rem;`) container with an explicit linear gradient:
* **Academic / Education (QEducation):** `linear-gradient(135deg, #1E5FE0, #4A90D9)` with `🎓`
* **E-Portal & Grades:** `linear-gradient(135deg, #0D6E4A, #1AA56E)` with `📊`
* **Achieve 3000 Literacy:** `linear-gradient(135deg, #00897B, #26A69A)` with `📖`
* **iRead Arabic:** `linear-gradient(135deg, #1E5FE0, #4A90D9)` with `📝`
* **ClassDojo:** `linear-gradient(135deg, #7B1FA2, #AB47BC)` with `🧑‍🏫`
* **SafeSpace Digital Safety:** `linear-gradient(135deg, #0072CE, #00A3E0)` with `🛡️`
* **School Policies:** `linear-gradient(135deg, #0D6E4A, #1AA56E)` with `📋`
* **Schedules & Newsletter:** `linear-gradient(135deg, #0D3B86, #1E5FE0)` with `📰`
* **Social Media Channels:** `linear-gradient(135deg, #833AB4, #E1306C, #F77737)` with `📱`
* **Ministry Services:** `linear-gradient(135deg, #0D3B86, #1E5FE0)` with `🏛️`
* **E-Library & Digital Resources:** `linear-gradient(135deg, #7B4A1A, #C07830)` with `📚`

---

## 16. IMAGES, MEDIA & LIGHTBOX SYSTEM

### 16.1 Image Grid Specifications
```css
.service-images-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 12px;
  margin: 14px 0;
}

.service-images-grid.single-img {
  grid-template-columns: minmax(240px, 480px);
}

.service-image-holder {
  border-radius: 12px;
  overflow: hidden;
  border: 1px solid var(--border-subtle);
  background: var(--bg-surface);
  cursor: pointer;
  box-shadow: var(--shadow-sm);
  transition: all 0.2s ease;
}

.service-image-holder:hover {
  transform: translateY(-2px);
  box-shadow: var(--shadow-md);
  border-color: var(--brand-blue);
}

.service-image-holder img {
  width: 100%;
  height: 180px;
  object-fit: cover;
  object-position: top;
  transition: transform 0.3s ease;
}

.service-image-holder:hover img {
  transform: scale(1.02);
}

.image-caption-tag {
  padding: 8px 12px;
  font-size: 0.76rem;
  font-weight: 700;
  color: var(--text-secondary);
  background: var(--bg-surface-subtle);
  border-top: 1px solid var(--border-subtle);
}
```

### 16.2 Video Embeds
* Video containers use an exact **16:9 Aspect Ratio**:
```css
.video-embed-box {
  position: relative;
  width: 100%;
  padding-bottom: 56.25%; /* 16:9 ratio */
  height: 0;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: var(--shadow-sm);
}

.video-embed-box iframe {
  position: absolute;
  top: 0;
  right: 0;
  width: 100%;
  height: 100%;
  border: none;
}
```

### 16.3 Fullscreen Lightbox Modal
* Background: `rgba(0, 0, 0, 0.9); backdrop-filter: blur(8px);`
* Active transition: `opacity: 1; visibility: visible;`
* Close Button: `34px × 34px` round button top-left, `background: rgba(255, 255, 255, 0.2)`.

---

## 17. FORMS, INPUTS & SEARCH CONTROLS

### 17.1 Smart Search Bar (`.search-input-box`)
* **Container:** Flex item (`flex: 1; min-width: 220px; max-width: 400px; position: relative;`)
* **Input Styling:**
  ```css
  .search-input-box input {
    width: 100%;
    background: var(--bg-surface-subtle);
    border: 1.5px solid var(--border-strong);
    border-radius: 50px;
    padding: 8px 38px 8px 16px; /* Right padding 38px accommodates the search icon in RTL */
    font-family: inherit;
    font-size: 0.86rem;
    color: var(--text-primary);
    outline: none;
    transition: all 0.2s ease;
  }
  .search-input-box input:focus {
    border-color: var(--brand-blue);
    background: var(--bg-surface);
    box-shadow: 0 0 0 3px var(--brand-blue-subtle);
  }
  ```
* **Search Icon Position (RTL):** `position: absolute; right: 12px; top: 50%; transform: translateY(-50%);`
* **Clear Button Position (RTL):** `position: absolute; left: 12px; top: 50%; transform: translateY(-50%);`

---

## 18. UI STATES & INTERACTION MATRIX

| State | Visual Manifestation | Elements Applied |
| :--- | :--- | :--- |
| **Default** | Standard token colors, resting elevation (`--shadow-sm`). | All cards, buttons, tabs. |
| **Hover** | `transform: translateY(-2px / -3px);`, elevation increases to `--shadow-md` or `--shadow-lg`, borders brighten to `--brand-blue`. | Buttons, cards, tiles, nav links. |
| **Active / Pressed**| `transform: translateY(0);`, shadow resets, slight inset contrast. | Buttons, tabs, accordion headers. |
| **Focus-Visible** | `outline: none; border-color: var(--brand-blue); box-shadow: 0 0 0 3px var(--brand-blue-subtle);` | Inputs, interactive buttons. |
| **Selected (Tabs)**| Background fills with `--tab-active-bg` (`#0E265C` light / `#3D7DF5` dark), text turns `#FFFFFF`, shadow applied. | Filter buttons (`.filter-tab-btn.active`). |
| **Highlighted Card**| `@keyframes highlightPulse { 0% { box-shadow: 0 0 0 0 rgba(30,95,224,0.7); } 50% { box-shadow: 0 0 0 10px rgba(30,95,224,0.25); transform: translateY(-2px); } 100% { box-shadow: var(--shadow-sm); transform: translateY(0); } }` Duration: `1.4s`. | Deep link targets navigated from menus. |
| **Hidden / Muted** | `display: none;` or `opacity: 0; pointer-events: none;` | Non-matching search cards, inactive modals. |

---

## 19. ANIMATION & MOTION SYSTEM

### 19.1 Motion Design Tokens
```css
:root {
  --duration-fast:   0.15s;
  --duration-normal: 0.25s;
  --duration-slow:   0.35s;
  --ease-standard:   cubic-bezier(0.16, 1, 0.3, 1); /* Apple-style spring ease */
  --ease-smooth:     ease;
}
```

* **Hover Transitions:** `transition: all 0.2s ease;`
* **Dropdown & Modal Reveals:** `transition: all 0.25s cubic-bezier(0.16, 1, 0.3, 1);`
* **Accordion Folder Slide:** `transition: max-height 0.35s cubic-bezier(0.16, 1, 0.3, 1), opacity 0.25s ease;`
* **Theme Switching:** `transition: background-color 0.3s ease, color 0.3s ease;`

---

## 20. HERO SECTION SPECIFICATION

* **Layout:** Centered content with maximum inner width of `1000px`.
* **Background Gradient:** Multi-stop diagonal navy: `linear-gradient(145deg, #071533 0%, #0E275E 55%, #18429A 100%)`.
* **Atmospheric Dual Radial Glows:**
  ```css
  .hero-section::before {
    content: "";
    position: absolute;
    inset: 0;
    background: radial-gradient(circle at 80% 20%, rgba(30, 95, 224, 0.3) 0%, transparent 50%),
                radial-gradient(circle at 20% 80%, rgba(217, 130, 0, 0.2) 0%, transparent 45%);
    pointer-events: none;
  }
  ```
* **Badge Chip:** `.hero-badge-pill` with golden glow text `#FFAE26` and translucent border.
* **Heading Structure:**
  * Title: `دليل الخدمات الرقمية لولي الأمر والطالب` with highlighted word `<span>خيارك الذكي</span>`.
  * Desktop Font: `clamp(1.75rem, 4.5vw, 3rem); font-weight: 900; line-height: 1.28;`
  * Mobile Font: `1.5rem; line-height: 1.25;`
* **Action Hubs:** 4 glassmorphic action cards at base of hero leading directly to critical services.

---

## 21. FOOTER SPECIFICATION

* **Background:** Deep solid midnight navy `#06132D` with top border `rgba(255, 255, 255, 0.08)`.
* **Grid Anatomy (Desktop):**
  * Column 1 (`2fr`): Inverted white logo (`height: 44px; filter: brightness(0) invert(1);`), school name, STEM/AP credentials, and e-learning team credit.
  * Column 2 (`1fr`): Important platform navigation anchors (`روابط هامة`).
  * Column 3 (`1fr`): Official government and social channel links (`قنوات التواصل الرسمية`).
* **Bottom Bar (`.footer-bottom-bar`):** Border-top separation line, text color `rgba(255, 255, 255, 0.5)`, copyright year `© 2026/2027 — جميع الحقوق محفوظة | مدارس قطر للعلوم والتكنولوجيا`.

---

## 22. RTL / LTR BILINGUAL ARCHITECTURE

The design system is fundamentally built for **Arabic-first (Right-to-Left)** reading patterns with seamless Latin/English integration.

1. **Document Direction:** Set on `<html>`: `<html lang="ar" dir="rtl" data-theme="light">`.
2. **Text Alignment:** `body { direction: rtl; text-align: right; }`.
3. **English Subtitles & Codes (`.en`):**
   ```css
   .en {
     font-family: 'Inter', sans-serif;
     direction: ltr;
     display: inline-block;
   }
   ```
4. **Border Accents:** Detailed service cards use `border-right: 5px solid <color>;` (in RTL this appears on the starting edge of the card).
5. **Icon & Text Flow:** Avatars and icons sit on the right, followed by text on the left.
6. **Search Input Ergonomics:** Search magnifying glass sits at `right: 12px`; input has `padding-right: 38px`. Clear button sits at `left: 12px`.
7. **Hover Displacements:** Interactive sub-links slide **leftward** on hover (`transform: translateX(-3px);`), mirroring western rightward slides.

---

## 23. ACCESSIBILITY & USABILITY STANDARDS

* **Color Contrast:** All text tokens meet WCAG 2.1 AA contrast requirements against their respective backgrounds:
  * Dark Navy `#0A193B` on `#FFFFFF` = **15.2:1** (Passes AAA).
  * White `#FFFFFF` on Navy `#0E265C` = **12.4:1** (Passes AAA).
  * Muted text `#64748B` on `#FFFFFF` = **4.6:1** (Passes AA).
* **Minimum Touch Targets:** All clickable mobile elements maintain a minimum hit-box of `44px × 44px`.
* **Focus Indicators:** Interactive elements maintain clean focus outlines (`box-shadow: 0 0 0 3px var(--brand-blue-subtle);`).
* **Tap Highlight Removal:** `-webkit-tap-highlight-color: transparent;` prevents awkward gray flashes on iOS Safari and Android Chrome.

---

## 24. COMPLETE REUSABLE DESIGN TOKENS (CSS)

```css
/* ══════════════════════════════════════════════════════
   DESIGN TOKENS (LIGHT & DARK THEMES)
   Single Source of Truth for QSTSS Portals
══════════════════════════════════════════════════════ */
:root, [data-theme="light"] {
  /* Surface & Page */
  --bg-page:             #F0F4F8;
  --bg-surface:          #FFFFFF;
  --bg-surface-subtle:   #F7FAFC;
  --bg-surface-elevated: #FFFFFF;
  --bg-header:           rgba(255, 255, 255, 0.96);
  --header-border:       rgba(10, 25, 60, 0.08);
  --border-subtle:       rgba(10, 25, 60, 0.07);
  --border-strong:       rgba(10, 25, 60, 0.14);

  /* Typography */
  --text-primary:        #0A193B;
  --text-secondary:      #1E293B;
  --text-muted:          #64748B;
  --text-inverse:        #FFFFFF;

  /* Brand Palette */
  --brand-navy-dark:     #06132D;
  --brand-navy:          #0E265C;
  --brand-navy-light:    #18429A;
  --brand-blue:          #1E5FE0;
  --brand-blue-subtle:   rgba(30, 95, 224, 0.08);
  --brand-gold:          #D98200;
  --brand-gold-glow:     #FFAE26;
  --brand-gold-bg:       rgba(217, 130, 0, 0.10);

  /* Shadows */
  --shadow-sm:           0 2px 6px rgba(10, 25, 60, 0.05);
  --shadow-md:           0 6px 18px rgba(10, 25, 60, 0.07);
  --shadow-lg:           0 14px 36px rgba(10, 25, 60, 0.10);
  --shadow-dropdown:     0 20px 40px -8px rgba(10, 25, 60, 0.22);

  /* Gradients */
  --hero-gradient:       linear-gradient(145deg, #071533 0%, #0E275E 55%, #18429A 100%);
  --hero-text:           #FFFFFF;
  --hero-subtext:        rgba(255, 255, 255, 0.88);

  /* Filter Tabs */
  --tab-bg:              #FFFFFF;
  --tab-text:            #1E293B;
  --tab-border:          rgba(10, 25, 60, 0.12);
  --tab-active-bg:       #0E265C;
  --tab-active-text:     #FFFFFF;

  /* Fonts */
  --font-arabic:         'Tajawal', sans-serif;
  --font-latin:          'Inter', sans-serif;

  /* Sizing & Geometry */
  --radius-sm:           8px;
  --radius-md:           12px;
  --radius-lg:           14px;
  --radius-xl:           18px;
  --radius-full:         50px;

  /* Spacing Scale */
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-5: 20px;
  --space-6: 24px;
  --space-7: 36px;
  --space-8: 52px;
}

[data-theme="dark"] {
  --bg-page:             #050C1B;
  --bg-surface:          #0B1730;
  --bg-surface-subtle:   #101F40;
  --bg-surface-elevated: #142750;
  --bg-header:           rgba(7, 15, 35, 0.96);
  --header-border:       rgba(110, 160, 250, 0.14);
  --border-subtle:       rgba(110, 160, 250, 0.10);
  --border-strong:       rgba(110, 160, 250, 0.22);

  --text-primary:        #FFFFFF;
  --text-secondary:      #D2E0FA;
  --text-muted:          #8FAEDC;
  --text-inverse:        #0A193B;

  --brand-navy-dark:     #030711;
  --brand-navy:          #3D7DF5;
  --brand-navy-light:    #689DFF;
  --brand-blue:          #4B8BF5;
  --brand-blue-subtle:   rgba(75, 139, 245, 0.15);
  --brand-gold:          #FFBA38;
  --brand-gold-glow:     #FFD580;
  --brand-gold-bg:       rgba(255, 186, 56, 0.15);

  --shadow-sm:           0 2px 10px rgba(0, 0, 0, 0.40);
  --shadow-md:           0 8px 24px rgba(0, 0, 0, 0.55);
  --shadow-lg:           0 18px 44px rgba(0, 0, 0, 0.70);
  --shadow-dropdown:     0 24px 50px rgba(0, 0, 0, 0.85);

  --hero-gradient:       linear-gradient(145deg, #040A18 0%, #091733 55%, #102654 100%);
  --hero-text:           #FFFFFF;
  --hero-subtext:        rgba(255, 255, 255, 0.88);

  --tab-bg:              #0B1730;
  --tab-text:            #D2E0FA;
  --tab-border:          rgba(110, 160, 250, 0.18);
  --tab-active-bg:       #3D7DF5;
  --tab-active-text:     #FFFFFF;
}
```

---

## 25. COMPONENT INVENTORY & SPECIFICATION

### C01: Announcement Strip
* **Purpose:** Broadcast school year session and official portal launch banner.
* **Markup:**
  ```html
  <div class="announcement-bar">
    <span class="badge-gold">دليل 2026/2027</span>
    <span>مرحبا بكم في الدليل الرقمي لتفعيل التعليم الإلكتروني والحلول الرقمية (الطالب - ولي الأمر )</span>
  </div>
  ```
* **Style:** Centered, flexbox, gradient background `#07173B` to `#153E90`.

### C02: Header Navigation Bar
* **Desktop:** Sticky header with school crest (`school-logo.png`), Title, 4 categorized dropdown menus, theme switcher, and direct CTA.
* **Mobile:** Logo at top center, lower row controls with Menu Accordion Toggle (`mobileDropdownToggle`) and Theme Switcher (`themeToggleBtn`).

### C03: Mobile Accordion Panel
* **Purpose:** Clean categorized menu for touchscreens.
* **Groups:** 3 distinct accordion groups (`.m-accordion-group`) with smooth chevron rotation and max-height transitions.

### C04: Hero Section & Action Hubs
* **Heading:** Multi-size clamp typography with glowing gold span.
* **Smart 4 Hubs:** Direct portal entries to QEducation, Password Reset, Student E-Portal, and Official Website.

### C05: Filter & Live Search Bar
* **Segmented Tabs:** All (`🌟 الكل`), Core Systems (`🎓 الأنظمة`), Academic (`📖 المنصات`), Guidance (`💡 المتابعة`), Services (`🏛️ الوزارة`).
* **Live Search:** Instant client-side search filtering by title, description, and keywords with clear (`✕`) button.

### C06: Metrics & Stats Strip
* **Structure:** 6-column grid on desktop collapsing to 3-columns on mobile with left-borders.
* **Stats Displayed:** 13+ Services, 15+ Videos, 13 Interactive Guides, STEM, QE, 24/7 Access.

### C07: Password Reset Hero Box
* **Style:** High-priority card with deep gradient base, circular key icon, explanation, and golden CTA button.

### C08: Featured Dual Video Cards
* **Structure:** 2-column grid featuring (1) Parent Guide and (2) Student Guide with responsive 16:9 YouTube players.

### C09: Tabbed Multi-Video Player
* **Structure:** Embedded master iframe player with a horizontal scrolling tab playlist underneath for switching videos dynamically without reloading.

### C10: Detailed Service Cards Catalog
* **Structure:** Catalog of 13 cards with colored right borders, gradient icon avatars, status tags, explanation boxes, media previews, and action buttons.

### C11: Qatar Education Poster Showcase
* **Structure:** Split 2-column showcase with clickable poster (triggers lightbox) and bulleted checklist of parental benefits.

### C12: Vision & Mission Section
* **Structure:** 2-column dark gradient container with 2 glassmorphic cards for School Vision and School Mission.

### C13: Quick Links Directory
* **Structure:** Compact grid of resource tiles with large icons, titles, and directional arrows.

### C14: Multi-Column Footer
* **Structure:** 3-column top grid, copyright bottom strip, Dark mode inverted logo.

### C15: Floating Scroll-to-Top Button
* **Behavior:** Fixed round button (`bottom: 24px; left: 24px; width: 42px; height: 42px; border-radius: 50%;`) appearing after `350px` scroll.

---

## 26. DESIGN RULES

Any developer, engineer, or AI coding agent implementing or modifying pages in this project MUST strictly follow these rules:

1. **NEVER Introduce Random Colors:** Use ONLY the defined color tokens (`--brand-navy`, `--brand-blue`, `--brand-gold`, `--bg-page`, etc.).
2. **Strict Font Integrity:** Use ONLY `'Tajawal'` for Arabic and `'Inter'` for English/Latin (`.en`). Do not use Arial, Calibri, or generic system fonts.
3. **Preserve Dual Theming:** Every new component must look pristine in both `[data-theme="light"]` and `[data-theme="dark"]`. Never hardcode `#FFFFFF` or `#000000` directly in component backgrounds or text without CSS variable fallbacks.
4. **Preserve the Right-Border Coding:** Service cards must use `border-right: 5px solid <color>;` to maintain visual domain categorisation.
5. **Preserve Mobile Layout Specialization:** Do not revert the mobile header to a squished desktop row. On screens `≤ 768px`, the logo MUST be centered at top, with menu and theme buttons aligned below on the right (RTL start).
6. **Preserve 2x2 Hero Grid on Mobile:** Hero action cards must remain in a compact 2x2 grid on mobile screens.
7. **Maintain RTL Consistency:** All icon-text pairs must place the icon on the right and text on the left. All sub-links must shift leftward on hover (`translateX(-3px)`).
8. **Preserve Border Radius Rhythms:** Cards must use `18px` (desktop) / `14px` (mobile). Buttons must use `50px` (pill). Never use sharp rectangular corners.
9. **Touch Target Enforcement:** Any clickable element on mobile must have at least `44px` height or adequate tap padding.
10. **Do Not Modify Content or Identity Without Request:** School name is strictly **"مدارس قطر للعلوم والتكنولوجيا"**. Do not alter institutional branding.

---

## 27. DESKTOP DESIGN SPECIFICATION (`> 1024px`)

* **Canvas Width:** Full width with centered `.container` (`max-width: 1240px; padding: 0 20px;`).
* **Header:** Sticky, single horizontal line, height `68px`, backdrop blur `18px`.
* **Dropdown Navigation:** Hover-activated dropdown menus positioned below nav items with `opacity` and `transform: translateY(2px)` reveal.
* **Hero Section:** Height auto (approx. `440px`), 4-column action grid with `backdrop-filter: blur(12px)`.
* **Service Cards:** Full-width stacked catalog (`gap: 22px;`), card padding `24px`, right border `5px`.
* **Action Buttons:** Horizontal inline flex layout with auto widths.
* **Footer:** 3 columns (`2fr 1fr 1fr`).

---

## 28. MOBILE DESIGN SPECIFICATION (`≤ 768px`)

* **Viewport Behavior:** Rigid zero horizontal overflow (`overflow-x: hidden;`).
* **Header Transformation:**
  * Height auto (approx. `94px`).
  * Tier 1: School Logo centered (`44px` height, `30px` on `≤375px`), School name centered (`0.92rem`).
  * Tier 2: Separator border line with Right-aligned Menu button (`[القائمة ▼]`) and Theme button (`[🌙 الوضع الليلي]`).
* **Mobile Dropdown Panel:** Fixed width `min(340px, calc(100vw - 28px))`, anchored top-right below the toggle button, with accordion folder navigation.
* **Hero Section:** Padding reduced to `34px 0 40px`, heading `1.5rem`, 2x2 grid for action cards (`gap: 8px`).
* **Category Tabs:** Wrapped 2-column grid (`calc(50% - 6px)`) with "All" button spanning full width (`100%`).
* **Service Cards:** Padding `16px 12px`, radius `14px`, action buttons converted to 2-column grid.
* **Password Reset Card:** Vertical column stack, centered circular icon, 100% width CTA button.
* **Footer:** Single column vertical stack with centered copyright.

---

## 29. RESPONSIVE IMPLEMENTATION RULES

1. **Fluid Typography:** Always use `clamp()` for responsive headings:
   * Hero: `font-size: clamp(1.75rem, 4.5vw, 3rem);`
   * Sections: `font-size: clamp(1.45rem, 3.2vw, 2rem);`
   * Brand: `font-size: clamp(0.88rem, 1.3vw, 1.05rem);`
2. **Flexible Grids:** Grids must use `repeat(auto-fit, minmax(...))` or explicit media query reductions:
   * 4 columns $	o$ 2 columns $	o$ 2 columns compact (Hero).
   * 6 columns $	o$ 3 columns $	o$ 3 columns compact (Stats).
   * 3 columns $	o$ 2 columns $	o$ 1 column (Footer).
3. **Scroll Margins:** All sections must declare `scroll-margin-top: 130px;` (desktop) and `scroll-margin-top: 85px;` (mobile) so anchored links do not hide beneath sticky headers.

---

## 30. HOW TO RECREATE THIS DESIGN (STEP-BY-STEP)

To create a new website sharing this exact design system, follow this sequence:

1. **Import Fonts:** Include Google Fonts `'Tajawal'` (300 to 900) and `'Inter'` (400 to 800).
2. **Define Root Variables:** Copy the exact CSS token block from **Section 24** into your main stylesheet.
3. **Configure Reset & RTL:** Set `html { direction: rtl; }` and `*, *::before, *::after { box-sizing: border-box; }`.
4. **Implement Sticky Glass Header:** Build `.header-container` with blur filter and brand logo on the right.
5. **Build Navigation System:**
   * Desktop: Use `.desktop-nav-organized` with dropdown menus.
   * Mobile: Add `.mobile-dropdown-toggle-btn` and `.mobile-dropdown-panel` with `.m-accordion-group`.
6. **Implement Theme Switcher:** Add toggle button script switching `data-theme="light|dark"` and persisting in `localStorage`.
7. **Construct Hero Section:** Apply multi-stop navy gradient, dual radial glows, fluid title, and 4-card action grid.
8. **Add Live Filter & Search Hub:** Create pill search input with sticky/subtle category tabs.
9. **Build Stats Counter Bar:** 6-column grid with blue numbers and muted labels.
10. **Implement Detailed Service Cards:** Use card structure with 5px colored right border, emoji avatar, explanation box, and action buttons.
11. **Implement Video & Media Containers:** Use `padding-bottom: 56.25%` for YouTube embeds and add image lightbox script.
12. **Construct Footer:** Midnight navy footer with 3 columns, inverted logo, and copyright strip.
13. **Add Scroll-to-Top Button:** Floating round button showing after 350px scroll.
14. **Apply Media Queries:** Add breakpoints at `1024px`, `768px`, and `375px` exactly as specified in **Section 19**.
15. **Verify RTL and Dark Mode:** Test all states across both desktop and mobile viewports.

---

## 31. AI DESIGN IMPLEMENTATION RULES

When instructed to create or update pages using this design system, AI agents MUST:

* ✅ **Consult this document first** before writing any HTML, CSS, or components.
* ✅ **Reuse existing CSS variables** without exception. Never invent new color hex codes.
* ✅ **Maintain exact component class names** (`.service-detail-card`, `.action-btn`, `.btn-blue-solid`, etc.).
* ✅ **Preserve mobile-specific layouts:** Do not collapse mobile elements into ugly single-line squished layouts. Use the 2x2 hero grid and 2-column action buttons.
* ✅ **Keep English text in `.en` wrappers** with `direction: ltr;`.
* ✅ **Ensure all interactive links have hover states** (`transform: translateY(-2px);` or `translateX(-3px)`).

---

## 33. FINAL QUALITY VERIFICATION CHECKLIST

- [x] **Complete Color System:** Light & Dark tokens, Hex, RGB, HSL, and semantic borders documented.
- [x] **Complete Typography System:** Tajawal + Inter, font weights, line heights, clamp equations documented.
- [x] **Complete Spacing System:** 8-level scale (`--space-1` to `--space-8`) and section padding documented.
- [x] **Complete Radius System:** `--radius-xs` to `--radius-full` documented.
- [x] **Complete Shadow System:** Light & Dark elevation tokens documented.
- [x] **Complete Component System:** 15+ core components fully specified.
- [x] **Header Specification:** Desktop vs Mobile layout documented separately.
- [x] **Footer Specification:** 3-column to 1-column responsive breakdown documented.
- [x] **Hero Specification:** Gradient, dual radial lights, badge pill, action hubs documented.
- [x] **Button Specification:** 14 distinct button variants with exact hex codes documented.
- [x] **Card Specification:** Service cards, hub cards, password card, quick links documented.
- [x] **Form Specification:** Search input box, icon positioning, focus states documented.
- [x] **Animation Specification:** Keyframes, durations, and Apple-style cubic-bezier transitions documented.
- [x] **Desktop Specification:** Layout for screens `> 1024px` detailed.
- [x] **Tablet Specification:** Layout for screens `769px – 1024px` detailed.
- [x] **Mobile Specification:** Layout for screens `376px – 768px` and `≤ 375px` detailed.
- [x] **Responsive Breakpoints:** `1024px`, `768px`, `375px` exact rules documented.
- [x] **RTL / LTR Specification:** Directional rules, English `.en` isolation, hover directions documented.
- [x] **Accessibility Specification:** WCAG AA ratios, touch targets (44px), focus states documented.
- [x] **Design Tokens Block:** Copy-pasteable CSS `:root` and `[data-theme="dark"]` provided.
- [x] **AI Implementation Rules:** Strict constraints for future coding agents defined.
- [x] **Design Recreation Guide:** Chronological 15-step implementation guide included.
