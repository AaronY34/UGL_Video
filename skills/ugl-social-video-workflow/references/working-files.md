# Run records

Use relative paths within the working folder when possible, so the edit can be moved with its assets. Do not copy raw student footage into the skill package.

## Brand profile

Create `.ugl-social-video/brand.json` after the user supplies the fixed files. Store the actual local paths and media facts, for example:

```json
{
  "brand": "UGL",
  "intro": "brand/ugl-intro.mp4",
  "outro": "brand/ugl-outro.mp4",
  "language": "English-first",
  "defaultAspect": "9:16",
  "defaultDurationSeconds": [15, 30],
  "audio": "live-sound-first"
}
```

The paths are relative to the working folder in this example. If the files stay elsewhere, use their real local paths; never pretend the example files exist. Inspect dimensions, duration, frame rate, and audio before final assembly. If either asset is wider than 9:16, reframe for vertical only after checking that logos and text remain visible.

## Per-video folder

Create `video-edits/<project-slug>/` with only the records and outputs actually produced:

```text
selects.csv
edit-record.json
roughcut.mp4
hyperframes/                 # editable project, when the installed workflow writes here
previews/A.mp4, B.mp4, C.mp4
final.mp4
```

`selects.csv` columns: `clip_id,source_file,in_time,out_time,content,sound,quality,visibility_note`. Use source timecodes, not timeline positions, for `in_time` and `out_time`. Keep IDs stable across the story options, ChatCut rough cut, and final record.

`edit-record.json` should contain the working-folder source paths, ChatCut project/timeline identifiers returned by Desktop, target aspect and duration, three offered story summaries, chosen story ID, rough-cut path and cut points, three effect preview paths, chosen effect ID, fixed asset paths, HyperFrames project path, final export path, and current stage. Update it after each completed stage so a later Codex session can resume without redoing expensive work. Never invent absent identifiers or claim a file exists before verification.

## Choice cards

For story options, use this compact shape in Codex:

```text
1. Title — one-sentence hook
   Beats: C03 (0–2s) → C07 (2–6s) → C11 (6–12s)
   On-screen copy: ...
   Why/constraint: ...
```

For effect options, show playable A/B/C previews from the same passage, each with the visual treatment and any readability tradeoff. The option descriptions are a guide to the generated previews, not a replacement for them.
