# Blog Revamp — Requirements & Design Decisions

> Reskinning blog.pdebruin.org to match the visual identity established for pdebruin.org (landing page).
> Approach: **Reskin Minimal Mistakes** — override CSS with landing page palette, fonts, and tone. Reuse before build.

---

## Current State

- **Platform:** Jekyll + Minimal Mistakes remote theme (`mmistakes/minimal-mistakes`, "air" skin)
- **Hosting:** GitHub Pages, custom domain `blog.pdebruin.org`
- **Content:** 154 published posts (2020–2026), micro-post format (80–200 words), curator-style
- **Voice:** Warm, first-person, "mostly notes to self" — see WRITING_STYLE.md
- **Customizations:** Minimal — custom LinkedIn share button, custom analytics hook, everything else is theme defaults
- **Author sidebar:** Name, avatar (`pieter-200-r.jpg`), link to pdebruin.org only (all other social links commented out)
- **Features:** Search enabled, pagination (10/page), categories/tags archives, related posts, jekyll-feed, jekyll-sitemap
- **Images:** 163 files in `/assets/images/`, PNGs/JPGs well-sized (mostly under 500KB), 3 large GIFs (up to 3.4MB)

## Landing Page Design System (source of truth)

Established in `~/_projects/dev-landing-page/requirements.md` with 25 logged decisions. The following elements carry over to the blog:

### Color Palette

| Role              | Hex       | Color          |
|-------------------|-----------|----------------|
| Background        | `#FBF2ED` | Warm cream     |
| Text              | `#2D3436` | Dark charcoal  |
| Text (secondary)  | `#636e72` | Charcoal light |
| Accent (links)    | `#CDEFFE` | Sky blue       |
| Subtle accent     | `#CDD5C6` | Sage green     |
| Secondary accent  | `#CECED7` | Lavender gray  |
| Warm highlight    | `#E8D4C6` | Blush/peach    |

### Typography

- **Display:** Cormorant Garamond (serif) — headings, blog title, author name
- **Body:** Outfit (geometric sans) — post text, navigation, meta
- **Self-hosted:** woff2 files, Latin + Latin-ext subsets (~118KB)
- **No external font CDNs** (Google Fonts, etc.)

### Shared Design Principles

- Privacy-first: no tracking, no cookies, no external CDN calls
- Self-hosted everything (fonts, icons, assets)
- Favicon: serif "P" in charcoal on transparent, 32x32px
- Professional tone — serious but warm
- Whitespace and restraint
- Muted, confident color palette

---

## Blog-Specific Considerations

### Different context than the landing page

The landing page is an **impression machine** — 3 seconds to establish credibility for execs/recruiters. The blog is a **reading experience** — 154 micro-posts, regulars come for weekly content.

The landing page voice is "executive boardroom." The blog voice is "coffee with a colleague." Same person, different register. The design should reflect this: **same palette, same fonts, but dialed back ~30%** — more breathing room, less formality.

### What the blog needs that the landing page doesn't

- Navigation (home, about, categories, tags, archives)
- Post list with dates and excerpts
- Individual post layout with readable line length
- Author sidebar (already in Minimal Mistakes)
- Search
- Pagination
- Related posts
- RSS feed / sitemap
- Responsive layout for long-form reading

---

## Approach: Reskin Minimal Mistakes

Override the remote theme's defaults via Sass variables and custom CSS. Minimal Mistakes supports this through:

1. **`assets/css/main.scss`** — Import custom font-face declarations, override Sass variables before theme import
2. **`_sass/` overrides** — Custom partials that override theme defaults
3. **`_config.yml`** — Skin, author, and site-level settings
4. **`_includes/` overrides** — Custom head tags, footer, etc.

### What to override

- [x] **Colors** — Replace "air" skin values with landing page palette
- [x] **Fonts** — Self-hosted Cormorant Garamond + Outfit, override `$serif` / `$sans-serif` / `$global-font-family`
- [x] **Background** — Flat warm cream (`#FBF2ED`), no gradient
- [x] **Links** — Charcoal text + blush underline, darken on hover
- [x] **Author sidebar** — B&W headshot with blush border, 3 links (pdebruin.org, LinkedIn, GitHub)
- [x] **Headings** — Cormorant Garamond serif for `h1`–`h3`, Outfit for `h4`–`h6`
- [x] **Footer** — Cream background, lavender divider, 3 links matching sidebar
- [x] **Favicon** — Serif "P" from landing page

### What to keep as-is

- Minimal Mistakes layout engine (single, home, archive, categories, tags)
- Search functionality
- Pagination
- Related posts
- jekyll-feed / jekyll-sitemap plugins
- Post front matter structure
- WRITING_STYLE.md voice guidelines

---

## Open Questions

- [ ] **Search styling** — Minimal Mistakes search works but may need palette adjustments after reskin

---

## Priorities

1. Visual reskin (palette + fonts + background) — biggest impact, establishes brand continuity
2. Self-hosted fonts — privacy alignment with landing page
3. Author sidebar + favicon update — brand consistency details
4. Clean up open questions above

## Out of Scope (this iteration)

- Switching away from Minimal Mistakes / Jekyll
- Content changes to existing posts
- Image compression (existing assets are already well-sized)
- Dark mode toggle

## Decisions Log

> Design decisions made during the blog revamp. Inherits from landing page where noted.

- **Author sidebar — minimal, refer don't repeat:** Headshot + name + 3 links (pdebruin.org, LinkedIn, GitHub). No bio text, no badges, no positioning statement. The landing page is the single source of truth for "who is Pieter"; the blog sidebar just links there.
- **Headshot:** Use the same B&W optimized photo from the landing page. Replace current `pieter-200-r.jpg`.
- **Background:** Flat warm cream (`#FBF2ED`), no gradient. The landing page has subtle radial gradients but they're barely noticeable — flat is cleaner for a reading-heavy blog.
- **Animations:** None. The landing page fade-in-up was intentional for a first-impression page. For a blog where people come back weekly, skip it.
- **Social sharing:** Remove custom LinkedIn share button. Clean is better — readers can copy the URL.
- **Link color — Option D:** Charcoal text (`#2D3436`) with blush (`#E8D4C6`) underline. Hover: underline darkens to charcoal. Sky blue (`#CDEFFE`) fails WCAG on cream — too light for text. Blush underline keeps links within the palette, passes AAA contrast, and feels warm.
- **Analytics:** Keep existing custom Application Insights analytics as-is.
- **Hover behavior — two patterns only:** (1) Post body links: blush underline → charcoal underline. (2) All UI links (nav, sidebar, footer, post titles): charcoal → charcoal-light (lighten on hover). Masthead nav also gets sky blue underline on hover as an accent.
- **Accent color roles:** Blush = personal (avatar border, link underlines). Sky blue = interactive (masthead nav hover underline). Lavender = structural (borders, dividers, pagination hover, prev/next). Sage = tag/category hover fills.
- **Typography tightening:** Nav/menu weights capped at 500 (Outfit only loads 300–500). Related posts heading uses sans not serif (too spindly at 12px). Archive titles explicit Outfit.
- **About page:** Keep as-is — it describes the blog, not the person. Landing page handles "about me."
- **Sidebar/footer link label:** Changed "www" → "pdebruin.org" — clear, professional.
- **Focus outline:** Replaced browser blue focus ring with subtle lavender outline on `:focus-visible` (keyboard nav only). No outline on mouse click/right-click.

---

## Reference

- **Landing page repo:** `~/_projects/dev-landing-page/`
- **Landing page requirements:** `~/_projects/dev-landing-page/requirements.md` (25 design decisions)
- **Blog writing voice:** `WRITING_STYLE.md` in this repo
- **Blog improvement backlog:** `IMPROVEMENTS.md` in this repo
- **Landing page live:** https://pdebruin.org
- **Blog live:** https://blog.pdebruin.org
