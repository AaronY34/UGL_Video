# Install on another computer

This ZIP contains the Codex skill and its instructions. It does not contain student footage, a logo, or the fixed intro/outro. ChatCut Desktop and the HyperFrames plugin must be installed and available to Codex on that computer.

## Install from GitHub in Codex

Give Codex this prompt on the other computer:

```text
Use $skill-installer to install https://github.com/AaronY34/UGL_Video/tree/main/skills/ugl-social-video-workflow
```

Restart Codex after installation. For a private repository, sign in to GitHub on that computer first.

## Install from ZIP manually

1. Download and extract `ugl-social-video-workflow.zip` from the repository's `dist/` folder.
2. Copy the extracted `ugl-social-video-workflow` folder into Codex's skills directory (`~/.codex/skills/` on macOS; `%USERPROFILE%\.codex\skills\` on Windows). Keep the folder name and `SKILL.md` together.
3. Restart Codex so it discovers the skill and the ChatCut Desktop tools.
4. Open ChatCut Desktop, then open the working folder in Codex. Put the raw videos in `Video/` or the folder root.
5. Invoke: `Use $ugl-social-video-workflow to make a UGL social video from the footage in this folder.` On first use, give Codex the paths to your fixed intro and outro files. They remain outside the skill package and are recorded in that working folder.

The workflow pauses in Codex for two creative choices: one of three storylines and one of three short HyperFrames effect previews. It then finishes and exports the selected edit.
