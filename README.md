# english-tutor

A personal English tutor skill. It helps you **learn and improve your English** — speaking, writing, grammar, vocabulary — grounded in proven second-language-acquisition methods (comprehensible input, pushed output with feedback, spaced retrieval, explicit error correction). Warm, friend-tone delivery; configurable focus area (professional / everyday / academic / travel).

## What it does

- **Corrects your real text** with a *why*-table (not just "this is wrong").
- **Finds your recurring patterns** (e.g. article choice) instead of fixing one-off typos.
- **Drills** the pattern, then checks it transfers to real writing.
- **Tracks progress across sessions** and **spaces** the reviews (`progress/english-log.md`).
- Flexes across four modes: correct real text · active practice · lessons + cheat sheets · conversation partner.

## Install

### Claude Code (recommended — full features)
Copy the folder into your skills directory; it's auto-discovered on next launch.

```bash
cp -r ./english-tutor "$HOME/.claude/skills/english-tutor"     # macOS / Linux
```
```powershell
Copy-Item -Recurse .\english-tutor "$env:USERPROFILE\.claude\skills\english-tutor"   # Windows
```

Then just ask: "fix this sentence", "improve my vocabulary", "is this natural?", or "teach me the present perfect". Force it anytime with `/english-tutor`.

### Claude.ai (web / desktop)
Requires **Pro, Max, Team, or Enterprise** with **code execution enabled**.
1. Zip this folder (or use the provided `english-tutor.zip`).
2. Claude.ai → **Settings → Features → Skills** → **Upload skill** → select the zip.
3. It validates `SKILL.md` and becomes available in conversations.

### API
Upload the same zip via the Skills API. See the Anthropic Agent Skills docs.

## ⚠️ Progress-tracking caveat (read this)

The skill's superpower is **spaced review across sessions**, stored in `progress/english-log.md`.

- **In Claude Code:** files are read-write, so the tutor updates your log each session and schedules the next review. Full feature. ✅
- **On Claude.ai / API:** the skill's files are effectively **read-only at runtime**. The tutor can *read* your log (warm start) but its end-of-session *updates won't persist* to the next conversation. Spaced review across sessions is therefore weaker here.

**Bottom line:** for cross-session memory and spaced repetition, prefer **Claude Code**. Use the Claude.ai upload for on-demand correction and lessons.

**Skills do not sync across surfaces** — Claude Code, Claude.ai, and the API each keep their own copy. Edits in one place don't propagate; re-zip and re-upload to update another surface.

## Layout

```
english-tutor/
├── SKILL.md                  # the tutor's instructions + method
├── README.md                 # this file
├── references/
│   ├── methods.md            # the SLA science (with sources)
│   ├── common-patterns.md    # recurring learner errors + fixes
│   ├── cheat-sheets.md       # article/tense/preposition/comma cards
│   └── focus-areas.md        # phrase banks per focus area
└── progress/
    └── english-log.md        # your patterns, mastery, spaced-review schedule
```

## Customizing

Open `progress/english-log.md` and set your **CEFR level** and **focus area** (professional / everyday / academic / travel). The tutor reads these and tailors examples to your world.
