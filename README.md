# cinema-skills

**Five agent skills for filmmakers, editors and video creators.** Drop them into your AI agent and get real production documents instead of generic advice: shot lists, scene breakdowns, color scripts, cut lists, export checklists.

No framework. No dependencies. Just `SKILL.md` files.

![demo](docs/demo.gif)

## What's inside

| Skill | You give it | You get back |
|-------|-------------|--------------|
| [`shot-list`](skills/shot-list/SKILL.md) | A scene or script excerpt | Shot table: size, angle, movement, lens, duration, must-get shots |
| [`scene-breakdown`](skills/scene-breakdown/SKILL.md) | A script | Production breakdown, risks, efficient shooting order, prep list |
| [`color-script`](skills/color-script/SKILL.md) | A synopsis or scene list | Palette and grade direction per story beat, hex swatches, motif |
| [`cut-list`](skills/cut-list/SKILL.md) | A transcript, footage log or beat sheet | Edit plan with in/out, runtime math, pacing notes, optional EDL |
| [`export-checklist`](skills/export-checklist/SKILL.md) | A destination (YouTube, vertical, festival...) | QC checklist, starting export settings, top 3 risks |

## Install

Built on the open [Agent Skills](https://agentskills.io) format, so it works in Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI and any agent that reads `SKILL.md`.

**Any agent, one command:**

```bash
npx skills add Benitoow/cinema-skills
```

or with the GitHub CLI:

```bash
gh skill install Benitoow/cinema-skills --all
```

**Claude Code plugin** (gets updates, skills appear as `/cinema-skills:shot-list` etc.):

```
/plugin marketplace add Benitoow/cinema-skills
/plugin install cinema-skills@cinema-skills
```

**Manual:**

```bash
git clone https://github.com/Benitoow/cinema-skills.git
mkdir -p ~/.claude/skills
cp -r cinema-skills/skills/* ~/.claude/skills/
```

For a single project only, copy into `.claude/skills/` (Claude Code) or `.agents/skills/` (Codex, Cursor, Copilot) at the project root instead.

## Use

Just describe what you need. The agent picks the right skill from its description.

```
Make me a shot list for this scene, 9:16, handheld, one actor, one location:
<paste scene>
```

```
Break down this script for a 2-day shoot with two locations.
```

```
Build a color script for my short film. Arc: calm, disruption, loss, quiet acceptance.
```

```
Turn this transcript into a 60-second vertical cut list. 24 fps.
```

```
I'm exporting for YouTube and Reels. Run the export checklist.
```

## No agent? Copy-paste prompts

Every skill has a short prompt version in [`docs/copy-paste-prompts.md`](docs/copy-paste-prompts.md). Paste it into any chat assistant.

## Example output (shot-list)

Assumptions: 9:16 vertical, one actor, one apartment (kitchen), night, practical light only; no tone or reference was given, so I assumed a quiet, tense drama with a mostly locked-off camera.

Visual idea: keep Maya and the face-down phone in the same tall frame so her avoidance stays visible, then tighten on each beat until only the message and her face are left.

| # | Beat | Size | Angle | Movement | Lens (approx.) | Action / subject | Est. screen time | Notes |
|---|------|------|-------|----------|----------------|------------------|------------------|-------|
| 1 | Setup | WS | eye-level | static | 24-35mm | Maya at the kitchen table, cold coffee beside a face-down phone | 4 s | Establishes the room. Table and phone in the lower third, empty space above her. |
| 2 | Turn | MS | eye-level | static | 35-50mm | First buzz. She ignores it | 3 s | Face at the top, phone at the bottom of the same tall frame. Let the buzz sound carry the beat. |
| 3 | Turn | CU | high | static | 50mm | Second buzz. Her hand turns the phone over | 3 s | Insert from above. Keep the phone out of the bottom caption zone. |
| 4 | Reveal | ECU | POV | static | 50mm | The screen: "We found him." | 3 s | Must-get. Phone screens can flicker on camera; if so, shoot the message as a screen capture and cut it in. |
| 5 | Payoff | CU | eye-level | slow dolly in | 85mm | She reads the message twice | 4 s | Must-get. Two clear passes of the eyes. The move should be barely visible. |
| 6 | Payoff | ECU | eye-level | static | 85mm+ | She slowly closes her eyes | 3 s | Must-get. Hold a beat after the eyes close. |

## Design principles

- **Never invent.** Skills work from the text you give them and ask when something is missing.
- **Working documents, not essays.** Tables, lists, timecodes.
- **Honest about limits.** Lens, loudness and platform specs are starting points: verify against current specs.

## Roadmap

- [ ] `storyboard-prompts`: frame-by-frame image prompts from a shot list
- [ ] `sound-design-notes`
- [ ] `trailer-structure`
- [ ] Companion project: a 100% local film recommender from your Letterboxd export (Ollama). Your film history never leaves your machine. *(coming soon)*

## Contributing

Add a skill: create `skills/<name>/SKILL.md` with `name` and `description` in the frontmatter, keep it concrete, include an output format and rules. PRs welcome.

## License

MIT
