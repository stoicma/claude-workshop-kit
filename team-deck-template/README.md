# Team Deck Template

A self-calibrating deck Skill that any team can fork and tune to their house style. Built for the AI Harnessing Workshop as the homework artifact each attendee uses to ship their first calibrated Skill between Session 1 and Session 2.

## What this is

A Skill folder with the McKinsey methodology baked into `rules/` (Pyramid Principle, MECE, action titles, SCR storyline, slide formatting, visual vocabulary). On first run, an interview captures **your team's** overrides on top of that methodology: audience, length, branding, language, voice rules, gold-standard reference deck.

The methodology is universal. The calibration is yours.

## How to use it

1. Copy this folder to your skills directory:

   ```bash
   cp -r team-deck-template ~/.claude/skills/myteam-deck
   ```

2. Edit `SKILL.md` line 2 to rename the Skill: `name: myteam-deck`.

3. (Optional) Drop your branded `template.pptx` into the new folder root. The renderer will use it as the master so colors, fonts, and layout inherit from your master.

4. (Optional) Drop 1-2 finished historical decks (sanitized) into `examples/`. The calibration interview will reference them.

5. In Cowork or Claude Code, ask for any deck:

   > Build a 12-slide steering committee deck for the Acme account.

   The Skill notices `calibration.md` is missing and starts the interview.

6. Answer six questions. The Skill writes `calibration.md` and runs a calibration test against your gold-standard deck.

7. Score the regenerated deck on five axes (structure, titles, narrative, formatting, accuracy). Apply any rule overrides the Skill suggests.

8. Once structure, titles, and narrative score 4+, the Skill is production-ready. Future deck requests skip the interview entirely.

## What's in the box

```
team-deck-template/
  SKILL.md            # interview-mode logic + draft instructions
  README.md           # this file
  rules/              # universal McKinsey-derived methodology
    structure.md      # Pyramid Principle + SCR storyline
    titles.md         # action title patterns
    mece.md           # MECE + Rule of 3
    formatting.md     # slide anatomy + source citation
    visuals.md        # chart and layout vocabulary
  examples/           # YOU drop reference decks here (empty by default)
  scripts/
    generate.py       # markdown deck plan → .pptx renderer (charts, matrices, 3-cards)
  output/             # generated decks land here
```

## What you write vs what the Skill writes

You write:
- Optional `template.pptx` for branding
- Optional reference decks in `examples/`

The Skill writes:
- `calibration.md` (after the interview)
- Any rule overrides learned during the calibration test
- Output decks in `output/`

You never edit `rules/` or `SKILL.md`. The methodology is fixed. Your team-specific differences live in `calibration.md`.

## Quality expectations

- **Before calibration.** Generic McKinsey output. Decent structure, no team voice.
- **After calibration, first production deck.** ~70-80% client-ready. Some manual polish required.
- **After 3-5 real production runs with corrections fed back into `calibration.md`.** ~85-90% client-ready, 5-10 minutes manual polish per deck.
- **Never 100% one-shot.** The Skill is a strong first draft. The team still owns the final deliverable.

The calibration test is non-negotiable. Side-by-side a regenerated deck against a finished historical deck the team agreed was client-ready. Score it. Tighten the rules. Repeat until threshold.

## Why fork this instead of writing from scratch?

The methodology layer (Pyramid Principle, MECE, action titles, SCR storyline) is universal across consulting, banking, internal strategy, executive briefings. You do not need to re-derive it. What changes between teams is the calibration: branding, voice, length, what they call "client-ready." The fork pattern keeps the universal layer fixed and surfaces the team-specific layer for explicit configuration.

## Workshop note

If you are a workshop attendee: your homework between Session 1 and Session 2 is to fork this template, run the interview, and produce one calibrated deck. Bring the `calibration.md` file and the calibration-test scores to Session 2. We will iterate live.
