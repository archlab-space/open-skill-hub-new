# Changelog

## [0.10.0] - 2026-06-11

### Added
- 产品/科普 content-angle mode: 科普 (knowledge/explainer) mode drops the product gate, captures a topic profile instead, and uses knowledge angles (explainer / how-it-works / 误区纠正 / 踩坑·复盘 / comparison / "what this means for you").
- YouTube platform rules (title / description / thumbnail brief; default 9:16 Shorts) and a 9:16 `youtube-thumbnail.html` template for `render-image.js`.

### Changed
- Broadened the skill identity (description, intro, core principle) from SaaS-only to founders **and** creators, covering knowledge content and YouTube. Skill name unchanged.

## [0.8.0] - 2026-06-08

### Added
- New Step 9 "Save To Vault (Optional)": opt-in archiving of finalized drafts to `<vault>/Founder Posts/YYYY-MM-DD.md`, one file per day. Reuses the env-var / named-path / three-option location resolution, `obsidian`-skill delegation, and graceful chat fallback. Rendered PNGs (Xiaohongshu covers / data cards) are copied into `Founder Posts/attachments/` and embedded with Obsidian `![[...]]`; when no PNG was rendered, the image brief is saved instead. The per-section file format records angle, platform, and platform-specific fields (X thread numbering, Reddit title/body, Xiaohongshu 标题/正文/#标签).

### Changed
- Output Format gains a first-draft "Save to vault?" prompt line; Key Rules document the opt-in save behavior. README lists the new step.

## [0.7.2] - 2026-06-07

### Changed
- `scripts/render-image.js`: stop hardcoding the Chromium sandbox-disabling launch flags; launch Chromium with the OS sandbox enabled by default and read optional extra flags from the `RENDER_CHROME_ARGS` environment variable. Container/CI users opt in explicitly. No behavior change on macOS / standard desktops. This removes the privilege-escalation pattern that static security scanners flagged.
- `render-image-setup.md`: document `RENDER_CHROME_ARGS` using a `<chromium-flags>` placeholder and a link to Puppeteer's troubleshooting guide, with no literal flag tokens in prose.

## [0.7.0] - 2026-06-05

### Added
- Xiaohongshu (小红书) platform support: platform option in intake, a dedicated Platform Rules section (image-first cover, title/body/tags conventions, soft-promotion norms), output format and key-rule updates, and Chinese-by-default behavior.
- New Step 7 "Decide Whether An Image Helps" with an image brief, plus a "Rendering Text/Data Graphics" subsection for HTML/CSS + headless Chrome rendering and a decision rule for when to render vs. use an image model vs. a real screenshot. Xiaohongshu always requires a cover.
- Rendering tooling: `scripts/render-image.js` (Puppeteer, with system-Chrome and manual fallback), `scripts/package.json`, `render-image-setup.md`, and example templates `assets/xiaohongshu-cover.html`, `assets/data-card.html`.

### Changed
- Renumbered the review step (Score And Revise) to Step 8 and added an "Image fit" rubric row. Updated the skill description and README to cover Xiaohongshu and image rendering.

## [0.6.0] - 2026-06-02
- Initial release of `saas-founder-content-writer`: a self-contained skill that turns founder product updates, user pain points, technical lessons, and observations into high-signal posts for X, Reddit, and LinkedIn.
- Four-phase workflow (Intake → Choose the angle → Draft → Review) with a portable product profile, 8 content angles, six writing principles with before/after examples, per-platform rules (X / Reddit / LinkedIn), a review rubric, and safety boundaries against fabricated claims.
