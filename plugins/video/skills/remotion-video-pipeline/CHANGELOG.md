# Changelog

## [0.1.0] - 2026-06-11

### Added
- Initial release of `remotion-video-pipeline`: an orchestration playbook for an
  audio-driven Remotion short-video workflow (script → audio → SRT → timeline →
  render → CapCut).
- Two mandatory human STOP gates: script confirmation (before audio) and timeline
  confirmation (after SRT recalibration, before render); audio approval and a
  pre-render preview documented as optional checks.
- The `scenes.json` / timeline data contract (`meta` + `scenes[]`, seconds-based
  authoring with sec→frames conversion).
- Governing principle (音频=主时间轴 · SRT=时间标尺 · Remotion=画面生成器 ·
  CapCut=声音/最终剪辑) and the rule that the script is frozen once audio exists.
- Remotion audio method A (narration baked in, default) vs. method B (silent
  render + separate voice, advanced), and a CapCut handoff bundle + checklist.
- Delegation of Remotion composition code to the `remotion-best-practices` skill;
  tool-agnostic audio/STT guidance with Whisper as the documented SRT default.
