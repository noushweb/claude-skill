# Claude Skills

## advanced-logo-animation
Creates premium, original logo animations (HTML/SVG/CSS/JS) from an uploaded logo and optional reference animation.

**Optional sound design.** Once the animation is approved, it asks whether you want sound: none, subtle, or a full sting.
- Sources sounds from free libraries (SFXMint, Pixabay, Mixkit, Zapsplat, Freesound and others) and checks each license. If none fit, it can search online, and it asks before downloading anything.
- Edits precisely with ffmpeg: maps each cue to the storyboard in milliseconds, then trims, fades and places the sounds so each hit lands within one frame of its visual event. Loudness is normalized to −14 LUFS.
- Delivers a WAV master, an MP4 with audio, and `sound/CREDITS.md` listing the source and license of every file. On the web, sound stays muted until the viewer presses play.

### Install
```bash
cp -R advanced-logo-animation ~/.claude/skills/
```

## enkay-ux-audit
Audits UX for a flow, screen, component, or whole project. Asks for scope, lets you pick the checks, reports prioritized findings, and only fixes what you approve (optionally using the Impeccable skill for UI fixes).

### Install
```bash
cp -R enkay-ux-audit ~/.claude/skills/
```

## ai-native-product-design
Designs a new AI-native app or audits an existing app or feature: maps users, workflows and pain points, decides where AI genuinely helps (and where a rule or form is better), then prioritises an MVP with RICE scores, risks and KPIs.

### Install
```bash
cp -R ai-native-product-design ~/.claude/skills/
```
