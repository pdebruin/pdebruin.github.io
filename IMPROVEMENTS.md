# Blog Improvement Plan

## Fix 12 broken image references

These images were never committed to git — broken on the live blog. Options: remove refs, find replacements, or backfill from LinkedIn archive.

| Post date | Missing image |
|-----------|--------------|
| 2022-07-29 | zero-trust-learning-path.png |
| 2022-08-19 | 20220819-identityvideos.png (referenced twice) |
| 2023-02-10 | learning-the-big-three.png |
| 2023-03-17 | azure-kubernetes-service-introduction.png |
| 2023-03-24 | azure-kubernetes-service-102.png |
| 2023-05-26 | my-build-2023.png |
| 2023-06-02 | congratulations-on-your-microsoft-anniversary.png |
| 2023-06-30 | year-in-review.png |
| 2023-07-07 | new-year-plans.png |
| 2023-07-14 | microsoft-entra.png |
| 2023-07-21 | ai-challenge.png |
| 2023-09-22 | bicep.png |

---

## Backfill missing weekly posts from LinkedIn

Requested LinkedIn data archive (GDPR export). Once available, use post content to create blog posts for gaps.

### Deleted stub posts to restore (need LinkedIn content)

| Date | Title |
|------|-------|
| 2023-09-01 | New foundational C# certification |
| 2023-09-08 | Python day |
| 2023-09-15 | Microsoft Learn community content |

### Missing weeks (excluding summer/holiday breaks) — 15 gaps

| Gap | Weeks missing |
|-----|---------------|
| 2022-09-09 | 1 |
| 2023-02-24 → 2023-03-03 | 2 |
| 2023-09-29 → 2023-10-20 | 4 (right after deleted stubs) |
| 2023-11-03 | 1 |
| 2024-01-12 → 2024-01-19 | 2 |
| 2024-03-01 → 2024-03-08 | 2 |
| 2024-03-29 → 2024-04-05 | 2 |
| 2025-10-24 | 1 |

### Regular breaks (expected, no action needed)

- **Summer** (Jul/Aug): 3 weeks off every year (12 total)
- **Holidays** (Dec/Jan): 1-2 weeks off every year (7 total)

---

## Ongoing: Compress images before publishing

```bash
convert input.png -resize 1920x1080\> -quality 85 -strip output.jpg
```
