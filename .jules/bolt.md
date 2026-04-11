## 2024-05-24 - Redundant CI Asset Generation
**Learning:** In GitHub profile repos, duplicate/unused assets are sometimes generated via actions (like `snk/svg-only`) even if they share the identical parameters or are never referenced in the `README.md`. This wastes CI runner time and bloats the storage size of the output branches.
**Action:** Audit action workflows in profile readmes to ensure we aren't generating multiple assets when they're redundant or entirely unused.
## 2026-04-10 - Lazy Loading Markdown Badges
**Learning:** Large blocks of markdown badges (like in Tech Stack sections) load eagerly by default, exhausting concurrent connection limits and delaying critical above-the-fold content.
**Action:** Convert large blocks of below-the-fold markdown badges to HTML `<img>` tags with `loading="lazy"` to prioritize critical rendering path.
