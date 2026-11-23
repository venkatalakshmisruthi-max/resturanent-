# resturanent-
# Ember & Oak – Website & Code Documentation

A single-page, responsive fine-dining restaurant website written in **HTML5 and CSS3 only** (no JavaScript, no frameworks).

---

## 1. Project Overview

| Item | Detail |
|---|---|
| Site name | Ember & Oak |
| Page title | Ember & Oak – Fine Dining Restaurant |
| Meta description | Ember & Oak: wood-fired cooking, seasonal ingredients and warm hospitality. |
| Tagline | "Where fire, season and craft meet on the plate." |
| Type | Single-page restaurant site (menu, offers, story, reviews, contact) |
| Files | One `.html` file with CSS embedded in a `<style>` block |
| Language | `lang="en"` |
| JavaScript | None (mobile menu uses a CSS checkbox technique) |
| Currency | Indian rupees (₹) |
| Location shown | Vijayawada, Andhra Pradesh, India |

---

## 2. Design System

### Color palette (CSS variables in `:root`)

| Variable | Hex | Used for |
|---|---|---|
| `--brown-dark` | `#2a1a12` | Main text, offers and form backgrounds |
| `--brown` | `#4a2f20` | Offer card background |
| `--cream` | `#f7efe2` | Page background |
| `--cream-deep` | `#eadcc4` | Borders, reviews background, image placeholders |
| `--black` | `#140e0a` | Header, footer, offers gradient |
| `--terra` | `#b4533a` | Prices, send button |
| `--terra-dark` | `#8f3f2a` | Links, category titles, button hover |
| `--gold` | `#c9a24d` | Accents, stars, underlines, primary buttons |
| `--gold-soft` | `#e3c785` | Hero tagline, form labels, quote marks |
| `--muted` | `#6f5b4d` | Secondary text |

### Typography

| Role | Font stack |
|---|---|
| Headings (`h1`–`h4`), brand, prices | `"Playfair Display", Georgia, "Times New Roman", serif` |
| Body and buttons | `"Segoe UI", "Helvetica Neue", Arial, sans-serif` |
| Body line-height | 1.7 |
| Heading line-height | 1.2 |

### Other tokens

- `--radius: 14px` for cards, images and forms.
- `--shadow: 0 10px 30px rgba(42, 26, 18, 0.15)` for card shadows.
- Container: `.container` has a max width of 1200px, centered. Sections use 5% side padding.
- Fluid type with `clamp()` on the hero heading, tagline and section headings.

---

## 3. HTML Structure (in page order)

Semantic elements used: `header`, `nav`, `main`, `section`, `article`, `blockquote`, `footer` (inside reviews), `address`, `cite`, `form`.

| # | Section | Element and ID | Purpose |
|---|---|---|---|
| 1 | Navigation | `<header class="site-header">` | Sticky dark nav bar |
| 2 | Hero | `<section id="home" class="hero">` | Full-screen intro with background photo |
| 3 | Menu | `<section id="menu" class="section">` | 4 categories, 8 dishes |
| 4 | Special Offers | `<section id="offers" class="section offers">` | Banner and 3 offer cards |
| 5 | About | `<section id="about" class="section">` | Story, two photos, bullet points |
| 6 | Reviews | `<section id="reviews" class="section reviews">` | 3 guest testimonials |
| 7 | Contact | `<section id="contact" class="section">` | Details, map, form |
| 8 | Footer | `<footer class="site-footer">` | Links, contact, hours, copyright |

### Navigation links

| Link text | Target |
|---|---|
| Home | `#home` |
| Menu | `#menu` |
| Special Offers | `#offers` |
| Reviews | `#reviews` |
| About | `#about` |
| Contact | `#contact` |
| Book a Table (gold button) | `#contact` |
| Brand logo ("E&O" mark + name) | `#home` |

### Mobile menu (CSS only)

- A hidden `<input type="checkbox" id="nav-toggle">` sits before a `<label for="nav-toggle" class="nav-burger">`.
- At 860px and below the links collapse into a dropdown. The selector `.nav-toggle:checked ~ .nav-links` raises `max-height` to 480px to reveal them.
- The burger icon animates into an "X" when checked (`::before` and `::after` rotate ±45°).
- Keyboard focus on the hidden checkbox shows an outline on the burger label.

---

## 4. Website Content Details

### 4.1 Hero

- Kicker: "Wood-fired kitchen · Est. 2012" (with ◆ ornaments on each side on larger screens)
- H1: **Ember & Oak**
- Tagline (italic serif): "Where fire, season and craft meet on the plate."
- Intro: "Slow-cooked over oak, plated with care. Join us for dinner that feels like an occasion, however ordinary the evening."
- Buttons: **Explore Menu** (gold, `#menu`) and **Reserve a Table** (outline, `#contact`).
- Background: restaurant photo from Unsplash under a dark gradient overlay, with a brown fallback color.
- Animation: the hero content fades and rises once on page load (`@keyframes rise`).

### 4.2 Menu (8 dishes in 4 categories)

| Category | Dish | Description | Vegetarian | Price |
|---|---|---|---|---|
| Starters | Charred Garden Salad | Grilled greens, heirloom tomato, toasted seeds and lemon-thyme dressing. | Yes | ₹320 |
| Starters | Sourdough & Soft Egg | Oak-toasted sourdough, whipped butter, soft egg and fresh herbs. | Yes | ₹280 |
| Main Course | Oak-Grilled Ribeye | Dry-aged cut, smoked garlic butter and roasted root vegetables. | No | ₹1,150 |
| Main Course | Wild Mushroom Pasta | Hand-rolled pasta, roasted mushrooms, parmesan and black pepper cream. | Yes | ₹640 |
| Desserts | Dark Chocolate Torte | Molten centre, sea salt and vanilla bean cream. | Yes | ₹360 |
| Desserts | Honey Pancake Stack | Fluffy pancakes, wild honey, seasonal berries and toasted almonds. | Yes | ₹340 |
| Drinks | Smoked Oak Old Fashioned | Aged whisky, orange peel, bitters and a hint of oak smoke. | No | ₹520 |
| Drinks | Citrus & Mint Cooler | Fresh orange, lime, mint and sparkling water over crushed ice. | Yes | ₹220 |

Each card has an image, a category tag, an optional green "Vegetarian" tag, the dish name, a description and a price.

### 4.3 Special Offers

| Element | Detail |
|---|---|
| Banner | "**20% off** your bill every Tuesday for tables of four or more." (dashed gold border) |
| Feature card, "Today's Special" | **Chef's Tasting Plate**: three small courses chosen by the head chef from the morning's best produce. ~~₹1,400~~ **₹990** |
| Card, "Combo Meal" | **Date Night for Two**: two starters, two mains, one dessert to share and two drinks. **₹2,100** |
| Card, "Seasonal Dish" | **Winter Roast Platter**: slow-roasted vegetables, spiced grains and oak-smoked paneer. **₹780** |

All three cards have an **Order Now** button linking to `#contact`.

### 4.4 About ("Our Story")

- Founded in 2012 as a ten-table kitchen cooking over real fire.
- Vegetables from farms within 100 km, meat from small producers, bread baked every morning.
- **Chef Rohan Mehta** leads the kitchen, with fifteen years of experience across India and Europe.
- Highlights:
  - Fresh, local, seasonal ingredients
  - Wood-fired cooking and house-made breads
  - Warm service in a relaxed, candle-lit room
- Two overlapping photos (dining room and chef) with a gold outline frame behind.

### 4.5 Reviews

| Guest | Rating | Review |
|---|---|---|
| Priya S. | 5 of 5 | The ribeye was the best I've had in years, and the staff made our anniversary feel special. |
| Ananya R. | 5 of 5 | Beautiful room, thoughtful vegetarian options and a dessert I still think about. |
| Karthik M. | 4 of 5 | Great food and a lovely atmosphere. Book ahead on weekends, it fills up quickly. |

Each card has a gold top border, a large decorative quote mark, a star rating, and a round avatar.

### 4.6 Contact (placeholder details)

| Field | Value |
|---|---|
| Address | 12 Heritage Lane, MG Road, Vijayawada, Andhra Pradesh 520010 |
| Phone | +91 98765 43210 (`tel:` link) |
| Email | hello@emberandoak.example (`mailto:` link) |
| Hours, Mon–Fri | 12:00 – 15:00 and 18:30 – 23:00 |
| Hours, Sat–Sun | 12:00 – 23:30 |
| Social links | Instagram, Facebook, X (`href="#"` placeholders) |
| Map | Embedded Google Map (iframe) centered on Vijayawada |

### 4.7 Footer

- Brand logo and one-line description: "Wood-fired cooking, seasonal ingredients, warm hospitality."
- **Quick links:** Menu, Special Offers, Reviews, About, Contact
- **Contact:** 12 Heritage Lane, MG Road, Vijayawada 520010, +91 98765 43210
- **Hours:** Mon–Fri 12–3 and 6:30–11; Sat–Sun 12–11:30 (shortened format)
- Social pills: Instagram, Facebook
- Copyright: © 2026 Ember & Oak. All rights reserved.

---

## 5. CSS Architecture

The stylesheet is numbered into 13 commented blocks:

| # | Block | Contents |
|---|---|---|
| 1 | Variables | Colors, fonts, radius, shadow |
| 2 | Base | Reset, smooth scroll, 80px scroll offset, focus outlines |
| 3 | Buttons | `.btn`, `.btn-gold`, `.btn-outline`, `.btn-terra` |
| 4 | Navigation | Sticky header, underline hover animation, burger menu |
| 5 | Hero | Background overlay, kicker, fluid heading, entrance animation |
| 6 | Shared section styles | `.section`, `.container`, `.section-head`, `.tag` variants |
| 7 | Menu | `.cat-title`, `.card-grid`, `.food-card`, image zoom |
| 8 | Offers | Dark gradient section, banner, `.offer-card`, feature layout |
| 9 | About | Overlapping images, bullet points with ◆ markers |
| 10 | Reviews | Testimonial cards, stars, avatar |
| 11 | Contact | Info column, social pills, map, dark form card |
| 12 | Footer | 4-column grid, link hover colors |
| 13 | Responsive | Media queries and reduced motion |

### Reusable classes

| Class | Function |
|---|---|
| `.container` | Centered 1200px wrapper |
| `.section` | Standard vertical and side padding |
| `.section-head` (`.light`) | Centered heading with gold underline; `.light` variant for dark backgrounds |
| `.btn` + `.btn-gold` / `.btn-outline` / `.btn-terra` | Pill-shaped buttons |
| `.tag`, `.tag.veg`, `.tag.gold` | Pill labels (category, vegetarian, special) |
| `.card-grid` | Auto-fit grid of food cards |
| `.food-card`, `.img-wrap`, `.card-body` | Menu item card parts |
| `.price`, `.offer-price` | Serif price styling |
| `.social` | Pill-style social links |

### Layout techniques

| Area | Technique |
|---|---|
| Header | Flexbox, `position: sticky; top: 0; z-index: 100` |
| Hero | Grid with `place-items: center`, `min-height: 92vh` |
| Menu cards | `repeat(auto-fit, minmax(260px, 1fr))` |
| Offers | 2-column grid; the feature card spans both columns (`grid-column: 1 / -1`) and goes side by side with `flex-direction: row` |
| About | 2-column grid with overlapping absolutely-positioned image |
| Reviews | `repeat(auto-fit, minmax(270px, 1fr))` |
| Contact | 2-column grid; form is a flex column |
| Footer | 4-column grid (`1.4fr 1fr 1fr 1fr`) |

### Hover and motion effects

| Element | Effect |
|---|---|
| Buttons | Lift 3px, shadow, color change |
| Nav links | Gold underline grows from left (`::after` width 0 to 100%) |
| Food cards | Lift 8px, deeper shadow, image zoom 1.1× |
| Offer cards | Lift 6px, border turns gold, image zoom 1.05× |
| Review cards | Lift 6px |
| Social pills | Fill gold on hover |
| Hero | One-time fade-and-rise on load |

### Accessibility

- Visible `:focus-visible` outlines (gold, 3px) on links, buttons and form fields.
- `alt` text on all images; ARIA labels on star ratings and the menu toggle.
- `prefers-reduced-motion: reduce` disables animations and transitions and turns off smooth scrolling.
- `loading="lazy"` on below-the-fold images and the map iframe.
- Form labels are tied to inputs using `for` and `id`.

---

## 6. Responsive Breakpoints

| Breakpoint | Changes |
|---|---|
| **≤ 960px** | Footer becomes 2 columns; About and Contact stack into 1 column; feature offer card stacks image above text; about image width limited |
| **≤ 860px** | Burger menu appears; nav links become a dropdown panel with centered links |
| **≤ 640px** | Smaller section padding; offers and footer become 1 column; hero ◆ ornaments hidden; smaller form padding |

---

## 7. Forms

| Form | Fields | Validation |
|---|---|---|
| Contact / booking | Name (`text`, required), Email (`email`, required), Message or booking request (`textarea`, required, placeholder "Date, time and number of guests") | Browser validation only |

The form uses `action="#"` and `method="post"`. It does not send data anywhere because there is no backend.

---

## 8. External Resources

| Resource | Source | Used for |
|---|---|---|
| Photos | images.unsplash.com | Hero, 8 dishes, 3 offers, 2 about images, 3 avatars |
| Map | maps.google.com embed (`q=Vijayawada`) | Location iframe |
| Stylesheet | `style.css` (linked in `<head>`) | See note below |

---

## 9. Code Review Notes and Possible Issues

These are things worth knowing about the code as written:

1. **Misplaced `<style>` block.** The `<style>` element sits between `</head>` and `<body>`. Browsers tolerate this, but it belongs inside `<head>`.
2. **Unused external stylesheet link.** The page links `style.css` but also embeds all its CSS. If you don't have a `style.css` file, the browser makes a failed request that does no harm; you can remove the `<link>` or move the CSS into that file.
3. **Playfair Display is not loaded.** No Google Fonts link is present, so headings use Georgia unless the font is installed on the visitor's computer. Add a Google Fonts `<link>` for Playfair Display to get the intended look.
4. **Duplicate rule.** `.offer-card { overflow: hidden; }` appears twice (already set in the main `.offer-card` rule).
5. **Use of `!important`.** Used on `.price`, `.offer-price` and `.copyright` to override `p` styles. Using more specific selectors would avoid this.
6. **Social links use `<ul>` and `<li>`** with `.social` applied to the `<ul>`, which is correct, but the base `ul { list-style: none }` reset makes it look like pills.
7. **Placeholder links.** Social links use `href="#"`, and the "Order Now" buttons only scroll to the contact form (no ordering system).
8. **No real booking or ordering.** The form is not connected to a server, so submissions go nowhere.
9. **Internet needed** for photos and the map.
10. **Contact details are sample data** (phone, email, address, chef name, reviews and prices).

---

## 10. Suggested Next Steps

1. Move the `<style>` block into `<head>` or into `style.css` and remove the duplicate.
2. Add a Google Fonts link for Playfair Display.
3. Connect the form to a form service or backend so booking requests are delivered.
4. Replace placeholder social links and sample contact details with real ones.
5. Add a `<meta property="og:...">` set for sharing previews.
6. Optionally add JavaScript later for features like closing the mobile menu after a link click.
