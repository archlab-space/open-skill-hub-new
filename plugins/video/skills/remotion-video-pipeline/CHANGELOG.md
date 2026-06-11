# Changelog

## [0.2.0] - 2026-06-11

### Added
- Optional multi-platform packaging: produce the script→audio→SRT→timeline master once, then fan out render (per aspect-ratio profile, with safe-area reframing — never letterbox) and copy/cover per platform (Xiaohongshu 3:4 / YouTube Shorts 9:16 / X), assembling a per-platform bundle + manifest.
- Delegation: copy/cover to `saas-founder-content-writer`; Remotion code to a Remotion skill; audio/SRT to the core pipeline. No new scripts; no auto-posting. Single-video use is unchanged.
- English-only skill text and examples; copy/cover delegation references a content-writing skill by capability rather than a hardcoded name.

## [0.1.0] - 2026-06-11

### Added
- Initial release of `remotion-video-pipeline`: an orchestration playbook for an audio-driven Remotion short-video workflow (script → audio → SRT → timeline → render → CapCut).
- Two mandatory human STOP gates: script confirmation (before audio) and timeline confirmation (after SRT recalibration, before render); audio approval and a pre-render preview documented as optional checks.
- The `scenes.json` / timeline data contract (`meta` + `scenes[]`, seconds-based authoring with sec→frames conversion).
- Governing principle (audio = master timeline · SRT = time ruler · Remotion = visuals generator · CapCut = sound + final edit) and the rule that the script is frozen once audio exists.
- Remotion audio method A (narration baked in, default) vs. method B (silent render + separate voice, advanced), and a CapCut handoff bundle + checklist.
- Delegation of Remotion composition code to a Remotion skill such as `remotion-best-practices`; tool-agnostic audio/STT guidance with Whisper as the documented SRT default.
- English skill body with Chinese-term glosses for the working vocabulary; source uses one-sentence-per-line formatting to match the repo convention.
