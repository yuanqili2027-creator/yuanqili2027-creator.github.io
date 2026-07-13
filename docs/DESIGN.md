# Design Spec

Design language: **Swiss (International Typographic Style) minimalism, strictly
monochrome.** No frameworks, no build step — hand-written HTML + a single shared
stylesheet (`assets/style.css`).

## Color

Grayscale only. **No accent colors anywhere.**

| Token      | Value     | Use                      |
| ---------- | --------- | ------------------------ |
| Background | `#fafafa` | Page background          |
| Text       | `#111`    | Primary text             |
| Secondary  | `#666`    | Dates, captions, meta    |
| Hairline   | `#e5e5e5` | Rules / borders          |

Links: underlined black; hover thickens the underline or shifts opacity. Any
future images get a `grayscale(100%)` filter.

## Typography

- Sans stack: `-apple-system, "Helvetica Neue", Helvetica, Inter, Arial,
  "PingFang SC", "Hiragino Sans GB", sans-serif`.
- Mono stack (dates, numbering, labels): `"SF Mono", Menlo, monospace` — small
  size, letter-spaced, often uppercase.
- Home page name: large display size (~3–4rem), tight tracking, uppercase.
- Body line-height ~1.7–1.8; Chinese articles use `.cjk` (line-height ~1.9).

## Layout

- Content column: `max-width: 680px`, centered, generous whitespace.
- Hairline rules separate sections (`.section-title`, `.row`, header, footer).
- Fully responsive; collapses to a single column on mobile.

## Navigation

On every page, numbered Swiss-style nav: `01 Essays / 02 Projects / 03 CV`.
The name/logo top-left links home. Current page marked with
`aria-current="page"` (underlines its label).

## Structure

```
index.html            Home / About (hero name, bio, interests, recent essays)
essays/index.html     Essay list grouped by year
essays/2026/*.html    Individual essays (on-reading-history.html = template)
projects/index.html   Project list
cv/index.html         CV with "Download PDF" button
assets/style.css      Shared stylesheet
assets/cv.pdf         CV PDF (placeholder)
```

## Footer

Identical on every page: Email (mailto) · GitHub (real) · LinkedIn (`#`) ·
X (`#`). All UI text in English.
