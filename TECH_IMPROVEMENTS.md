# Blog Technical Improvement Plan

Audit performed 2026-03-21. Updated after investigating theme capabilities.

The blog uses [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes) via `remote_theme: mmistakes/minimal-mistakes` (no version pin — always pulls latest, currently v4.28.0). The theme already includes built-in SEO (`_includes/seo.html`) that generates OG tags, canonical URLs, Twitter Cards, meta descriptions, ARIA labels, and article metadata. No additional SEO plugin is needed.

---

## Priority 1: Accessibility — fix image alt text

~145 posts use `![img](...)` — a meaningless alt text. Screen readers say "img" and search engines ignore these images entirely.

Replace with a short description of what the image shows. Does not need to be long:
- `![img]` → `![Screenshot of AKS cluster in Azure portal]`
- `![img]` → `![Slide from AI Tour presentation on RAG architecture]`

The 15 posts from 2022 and a few others already have decent alt text — use those as examples.

**Approach:** This is a bulk task. Could be partially automated: for each post, the image filename often hints at the content (e.g., `2024-09-20-rag-chat.jpg` → "RAG Chat architecture diagram").

---

## Priority 2: SEO — add description to post front matter

The theme uses `page.description | page.excerpt | site.description` for meta tags and OG tags. We standardize on `description:` (not `excerpt:`) because:
- The theme checks `description` first
- It has no auto-generation side effects (unlike `excerpt`, which Jekyll auto-generates from the first paragraph and uses in feed/list contexts)
- It signals clear intent: this field is for meta tags

**Example:**
```yaml
---
title: "How we built Learn MCP Server"
description: "How the Microsoft Learn team built an MCP Server that connects AI agents directly to trusted documentation."
categories:
  - Learning
tags:
  - Artificial intelligence
---
```

**Approach:** Tackle incrementally — start with the 20 most-visited posts (check App Insights), then work through the rest over time.

---

## Ongoing: Compress images before publishing

Images should be resized to max 1920×1080 and compressed (JPG quality 85) before committing. Use ImageMagick:

```bash
convert input.png -resize 1920x1080\> -quality 85 -strip output.jpg
```

---

## Optional / later

- Add `robots.txt` to repo root
- Implement lazy loading for images
- Add responsive image `srcset` markup
- Configure `twitter.username` in _config.yml to enable Twitter Card metadata
