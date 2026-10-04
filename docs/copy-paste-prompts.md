# Copy-paste prompts

For chat assistants without skill support. Replace the bracketed parts.

## Shot list

```
Act as a first assistant director and cinematographer. Turn the scene below into a practical shot list.
Format: [aspect ratio]. Tone/references: [..]. Constraints: [location, actors, gear, time].
If any of that is missing, state your assumptions in one line.
Mark the scene's beats, start with a master shot, add coverage, vary size/movement with intent.
Output a table: # | Beat | Size | Angle | Movement | Lens (approx.) | Action | Est. screen time | Notes.
End with: 3 must-get shots, what to cut if time runs out, max 3 questions.
Never invent plot or dialogue. Don't pad.

Scene:
[paste]
```

## Scene breakdown

```
Break down the script below for a small-crew shoot. Extract only what is in the text.
Output a table: Scene | Slug | Cast | Props/wardrobe | Sound/music | VFX/special | Lighting needs | Complexity (Low/Med/High + reason).
Then: risks and unknowns (with cheaper alternatives), a shooting order grouped by location/light, a prep list (permits, releases, gear).
Limits: [days, locations, crew].

Script:
[paste]
```

## Color script

```
Build a color script for the story below. Identify the beats and their emotions.
Table per beat: Emotion | Dominant | Accent | Contrast | Saturation | 3-5 hex swatches | Grade direction (relative moves: temperature, tint, contrast, saturation).
Then: the recurring color motif and how it evolves, continuity warnings, skin-tone and subtitle readability checks.
Delivery: [Rec.709 / HDR]. Tool: [Resolve / Premiere / other]. References: [..].
Say which choices are taste and which are technical. Recommend testing on a graded still.

Story:
[paste]
```

## Cut list

```
Turn the material below into an edit plan. Target: [runtime, platform]. Frame rate: [fps].
Start with the edit concept and runtime math (current, target, delta).
Table: # | Clip | In | Out | Duration | Purpose | Transition | Audio notes. Use HH:MM:SS:FF only when real timecodes exist; otherwise label estimates.
Then 3-5 pacing notes and an ordered list of trim candidates with the cost of each.
Vertical: the hook must land in the first 1-2 seconds.
Never invent footage or timecodes.

Material:
[paste]
```

## Export checklist

```
I'm exporting a video for [destinations]. Project: [resolution, fps, color space, captions burned in?]. Tool: [Premiere / Resolve / other].
Give me: one recommended preset per destination, a QC checklist limited to what's relevant (picture, fps, color, audio levels around -14 LUFS with true peak near -1 dBTP, caption safe zones, music/font/stock rights), my top 3 risks, and where to find the settings in my tool.
Remind me to verify against each platform's current specs.
```
