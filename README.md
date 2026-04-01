# Gym Shopify Theme Template

A clean, dark Shopify theme built for gyms and fitness brands. Bold black background with a lime green accent, fully SEO-optimized, system fonts only, and easy to rebrand for any new client.

> Built with Shopify Online Store 2.0 (JSON templates). No build tools required — edit files directly.

---

## Design Defaults

| Property | Value |
|---|---|
| Background | `#0a0a0a` |
| Surface | `#161616` |
| Accent color | `#c8ff00` (lime green) |
| Heading text | `#ffffff` |
| Body text | `#e0e0e0` |
| Subtext | `#888888` |
| Border | `#2c2c2c` |
| Button text | `#0a0a0a` |
| Header background | `#0f0f0f` |
| Button radius | `3px` |
| Fonts | System fonts (no external font requests) |

All colors are set in `config/settings_data.json` and can be overridden in the Shopify Theme Editor.

---

## Sections Included

| Section | Description |
|---|---|
| `hero.liquid` | Full-screen hero with background image, headline, and CTA button |
| `gym-highlights.liquid` | Zone cards — full-bleed portrait image cards with lime badge, gradient overlay, white text |
| `memberships-pricing.liquid` | Membership tier pricing cards |
| `day-passes.liquid` | Day pass options |
| `pt-services.liquid` | Personal training page with contact form, trainer profile, and FAQ |
| `about-story.liquid` | Gym story / about section |
| `apparel-grid.liquid` | Merchandise/apparel product grid |
| `contact-info.liquid` | Location, hours, and contact details with Google Maps embed |
| `google-reviews.liquid` | Google Reviews widget embed (app-based) |
| `announcement-bar.liquid` | Top-of-page announcement strip |
| `header.liquid` | Sticky header with nav and logo |
| `footer.liquid` | Footer with links and address |

---

## Reusing This for a New Client

### 1. Fork or duplicate this repo

Click **Use this template** on GitHub to create a fresh repo for the new client.

### 2. Find and replace the gym's details

Do a global find-and-replace across all files for these placeholders:

| Replace | With |
|---|---|
| `[GYM NAME]` | e.g. `Iron House Gym` |
| `[GYM ADDRESS]` | e.g. `1200 Main St` |
| `[GYM CITY, STATE ZIP]` | e.g. `Austin, TX 78701` |
| `[GYM PHONE]` | e.g. `(512) 555-0100` |
| `[GYM EMAIL]` | e.g. `info@ironhousegym.com` |

### 3. Swap brand colors

Open `config/settings_data.json` and update the color values, or change them in the Shopify Theme Editor under **Theme Settings → Colors** after connecting.

To change the accent from lime green to another color, update `#c8ff00` in `assets/main.css` and `config/settings_data.json`.

### 4. Replace the logo

Upload the new gym's logo in the Theme Editor under **Header → Logo image**, or update the logo reference in `layout/theme.liquid`.

### 5. Replace zone / facility photos

The gym highlights section uses 6 portrait zone images. Replace them in the Theme Editor under **Gym Highlights → Zone Cards**.

Recommended image size: **800 × 1000px** (4:5 portrait ratio).

### 6. Update membership & pricing

Edit `sections/memberships-pricing.liquid` and `sections/day-passes.liquid` with the new gym's pricing tiers, descriptions, and sign-up links.

### 7. Update the SEO snippet

Open `snippets/seo-head.liquid` and update:

```liquid
{% assign seo_title = "Gym Name | City" %}
{% assign seo_description = "Short description of the gym." %}
```

Also update the `LocalBusiness` JSON-LD structured data block with the correct address, phone, hours, and coordinates.

### 8. Swap favicons

Upload the new gym's favicon to Shopify Files and update the favicon URLs in `layout/theme.liquid`:

```liquid
<link rel="icon" href="YOUR_FAVICON_URL">
<link rel="apple-touch-icon" href="YOUR_APPLE_TOUCH_ICON_URL">
```

### 9. Connect to Shopify

1. Go to **Shopify Admin → Online Store → Themes**
2. Click **Add theme → Connect from GitHub**
3. Authorize Shopify's GitHub integration, then select your new repo and the `main` branch
4. Click **Connect**, then **Publish** when ready

> Once connected, any changes in the Theme Editor will automatically push to GitHub.

---

## Navigation Menus

Create these menus in **Shopify Admin → Navigation**:

### Main Menu (`main-menu`)

| Title | URL |
|---|---|
| Memberships | `/pages/memberships` |
| Day Passes | `/pages/passes` |
| Personal Training | `/pages/personal-training` |
| Shop | `/collections/apparel` |
| About | `/pages/about` |
| Contact | `/pages/contact` |

### Footer Menu (`footer`)

Same links as the main menu, or a subset.

---

## Pages & Templates

Create each page in **Shopify Admin → Online Store → Pages** and assign the correct template from the right sidebar:

| Page Title | URL Handle | Template |
|---|---|---|
| Memberships | `memberships` | `page.memberships` |
| Day Passes | `passes` | `page.passes` |
| Personal Training | `personal-training` | `page.personal-training` |
| About | `about` | `page.about` |
| Contact | `contact` | `page.contact` |

---

## Google Reviews Setup

1. Install the **Google Reviews** app from the Shopify App Store
2. Create a widget in the app and copy the embed code
3. In Theme Editor → Homepage → **Google Reviews** section, paste the embed code
4. Save

---

## File Structure

```
├── assets/
│   ├── main.css              # All custom styles
│   └── main.js               # Mobile menu, smooth scroll — no dependencies
├── config/
│   ├── settings_data.json    # Theme setting values (colors, text, etc.)
│   └── settings_schema.json  # Theme Editor settings definitions
├── layout/
│   └── theme.liquid          # Master layout: favicons, SEO tags, scripts
├── sections/                 # All page sections (see table above)
├── snippets/
│   └── seo-head.liquid       # SEO meta tags + JSON-LD structured data
├── templates/
│   └── index.json            # Homepage section order and settings
└── locales/                  # Translation strings
```

---

## SEO Features

- `GymOrHealthClub` JSON-LD schema on every page
- `LocalBusiness` structured data with address, phone, hours, and coordinates
- `BreadcrumbList` schema on inner pages
- `Product` and `ItemList` schema on product/collection pages
- Canonical URL, Open Graph, and Twitter Card tags on every page
- One `H1` per page enforced by section design
- Semantic HTML throughout (`<main>`, `<header>`, `<footer>`, `<nav>`, `<section>`, `<address>`)
- System fonts — zero external font requests

---

## Tips

- **No build step** — edit Liquid, CSS, and JSON files directly
- **Force push if needed** — if GitHub and the Theme Editor get out of sync, run `git pull --rebase` before pushing, or use `--force` if your local version is the source of truth
- **Accent color** — `#c8ff00` appears in both `main.css` and `settings_data.json`; update both when rebranding
