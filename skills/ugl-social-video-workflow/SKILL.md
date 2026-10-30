---
name: ugl-social-video-workflow
description: Turn UGL class, tournament, and golf footage in the current working folder into a social video through ChatCut Desktop rough cutting and HyperFrames finishing. Use when the user wants the full UGL video workflow with three story choices, three real motion previews, fixed intro/outro, and a final export.
---

# UGL social video workflow

This skill coordinates **ChatCut Desktop** and **HyperFrames**. Use the installed versions' own skills and live tool schemas for their editing commands; this skill defines the handoff, user choices, and deliverables. Do not silently substitute the hosted ChatCut connector for Desktop. Do not invent tool names when Desktop's MCP surface differs.

## Defaults and setup

- Default deliverable: English-first, 9:16, 15–30 seconds **including** the fixed intro and outro. Allow a per-video override.
- UGL tone: premium golf lounge, restrained type and motion, clear real-world action. Use the provided brand assets and the current project's style instructions; do not impose the older location animation on every student video.
- Keep useful live sound (impact, instruction, reactions). Add music only when the user supplies an approved track or specifies a usable source.
- On first use in a working folder, ask for the user's existing intro and outro files, then record their paths and durations in `.ugl-social-video/brand.json`. Reuse them on later runs. If either is missing, prepare the rest of the edit and ask only for that file before final assembly. Do not treat the existing 10.2-second location animation as a fixed opener by default.
- The source videos arrive in the current working folder. Prefer its `Video/` directory when present; otherwise identify the newly provided files from the current folder. Do not sweep unrelated archives or old exports into the batch. Resolve ambiguity before editing. Preserve originals. One run produces one finished video, which may feature several students.
- Create a unique `video-edits/<project-slug>/` under that working folder for the run. Read [working-files.md](references/working-files.md) when creating or resuming its records. Keep source media and student footage out of the skill folder itself.

## 1. Inspect and select source moments

Check that ChatCut Desktop is running and its `chatcut_desktop` tools are available. Use its synced editing skills and `get_active_project` to establish the intended project. If unavailable, use the installed `connect-chatcut-desktop` instructions; do not silently move to another service. Load the installed HyperFrames entrypoint before HyperFrames work.

Inspect every supplied video with available local source viewing and ChatCut media inspection. Note what is **seen and heard** with source timecodes: student swing, coaching, class activity, tournament play, group interaction, result/reaction, clean establishing shot, and unusable sections. Avoid inventing ball flight or outcomes that the footage does not show.

Import the original source videos into ChatCut. Use ChatCut to mark/trim useful ranges into native clips or a selects timeline, with meaningful labels and source offsets. Preserve enough handle frames for later timing changes. Record each selected range in `selects.csv` with stable clip ID, source filename, in/out, content label, sound/dialogue, quality note, and any visibility concern. A CSV alone is not a substitute for the ChatCut selects. Inspect the composed selects before offering a story.

## 2. Offer exactly three storylines in Codex

Ground all three in the selected clip IDs. Make the approaches genuinely different in opening hook, sequence, and payoff, for example progress, class energy, or competition. Each option should fit the available footage and target duration **after** intro/outro. Show in Codex a short title, one-sentence premise, ordered clip IDs with approximate timing, suggested on-screen English copy, and any important tradeoff. Recommend one option. Use Codex's native choice prompt when available, or a concise numbered question in chat. Ask the user to choose **1, 2, or 3** and wait for the answer. Do not start the rough cut based on an unselected option.

## 3. Build the ChatCut rough cut

Use ChatCut Desktop to assemble the chosen storyline from the original source assets, with trims, sequencing, framing, and essential audio. Keep an editable ChatCut timeline. Check pacing, visible content, source offsets, gaps, and sound. Show the rough cut in ChatCut and export an intermediate `roughcut.mp4` for HyperFrames, using the desktop tool's actual export workflow. Record the exact cut points and chosen story in `edit-record.json`. The rough cut is the story and timing reference; HyperFrames should not silently rewrite the story.

## 4. Generate three HyperFrames effect previews

Use the installed HyperFrames skill's current project, media, animation, preview, and render rules. Start from the **same** representative 3–5-second passage of the rough cut for all three variants, so the difference is the effects. Produce three actual short video previews, not text descriptions or still images. Keep the UGL premium lounge feel while varying the treatment meaningfully (for example restrained typography, subtle focus/zoom, or energetic but controlled sports data accents). Preserve action visibility and legibility. Apply any user-supplied visual brand rules.

Present the three playable preview videos in Codex with one-line descriptions and a recommendation. Use Codex's native choice prompt when available, or a concise A/B/C question in chat. Ask the user to choose **A, B, or C** and wait. Save the selected treatment in `edit-record.json`. Do not make the full effects pass before selection.

## 5. Finish and deliver

Apply the chosen HyperFrames treatment to the whole rough cut. Add the user's fixed intro and outro, adjusting their fit only as needed for the approved 9:16 final. Keep the total duration in the agreed range, or explain a concrete reason it cannot fit and ask for a choice. Check text safe areas, consistent style, motion through every cut, audio transitions, and the final frame. Follow the installed HyperFrames skill's validation and review requirements, then render the final MP4.

Deliver the final MP4 plus the editable ChatCut project/timeline and HyperFrames project location, the selects list, and a concise record of story/effect choices. Verify the exported file's duration, dimensions, audio, and several representative frames before saying it is finished. The request is to create a finished video file; posting to social media is a separate action.

## Resume and boundaries

Read the run's `edit-record.json` before continuing. Keep the two user choice gates explicit; a prior answer persists across turns. If a needed plugin, source file, or fixed intro/outro asset is unavailable, complete independent steps and name the specific blocker. Do not upload private student footage to another service or publish it without a separate request.
