---
name: team-deck
description: Self-calibrating deck Skill template. Fork this folder, run any deck request, and the Skill walks you through a 6-question interview on first run to learn your team's audience, length defaults, branding, language, voice rules, and gold-standard reference deck. From the second run onward it produces decks in your team's house style. Use when your team needs to produce decks (status reports, pitches, steering committees, recommendations) on a recurring basis and wants a Skill calibrated to your conventions, not a generic one.
---

# Team Deck Skill (Template)

This Skill produces decks in **your team's** house style. It does not assume any specific branding or methodology. On first run it asks six questions to calibrate. After that it produces decks directly.

If you want a McKinsey-style deck, use the `mckinsey-deck-skill` Skill instead. This one is for your team.

## Step 1. Detect calibration state

Before responding to any deck request, list this Skill folder.

- If `calibration.md` does **not** exist → run **interview mode** (Step 2).
- If `calibration.md` **exists** → read it as your style guide and skip to Step 3.

The presence of `calibration.md` is the only state signal. To re-calibrate, delete that file.

## Step 2. Interview mode (first run only)

Ask these six questions one at a time. After all six are answered, write the answers to `calibration.md` using the template at the bottom of this file. Then proceed to Step 3.

### The six questions

1. **Audience.** Who reads these decks most often? (e.g. senior client management, board, internal team, prospects)
2. **Length default.** Your typical deck length? (5 / 10 / 20 / 30+ slides)
3. **Branding.** Drop a `template.pptx` into this folder if you have a branded master. Otherwise, give me primary color (hex), accent color (hex), and font preference. Default is white background, navy #0A2540 text, orange #E76F00 accent, Helvetica.
4. **Language.** English, German, your client's language? Mixed?
5. **Voice constraints.** Anything to avoid? (em dashes, specific jargon, AI-tell phrases, vague hedging, marketing-speak). Example: "no em dashes; never say 'leverage' as a verb; numbers always with units."
6. **Gold-standard reference.** Pick one finished deck the team agrees was client-ready. Drop the file in `examples/` or paste an outline. This becomes the calibration test target.

### Calibration test

After writing `calibration.md`, regenerate the gold-standard deck from the brief that produced it (ask the user for the brief). Show the regenerated plan side-by-side with the original. Ask the user to score on five axes, 1-5:
- Structure (SCR storyline holds, Resolution divider lands)
- Action titles (each title states a conclusion, title-only test passes)
- Narrative (titles read as a paragraph, not a list)
- Formatting fidelity (visual layout matches team conventions)
- Factual accuracy (numbers match, sources cited correctly)

Append scores and any rule corrections to `calibration.md`. The Skill is production-ready once structure, titles, and narrative all score 4+.

If a score is below 4, ask: "What would have made it a 5?" and capture the answer as a rule override in `calibration.md`. Iterate until threshold.

## Step 3. Read the rules in order

Before drafting any deck:

1. `calibration.md` (your team's overrides take priority)
2. `rules/structure.md` (Pyramid Principle + SCR storyline)
3. `rules/titles.md` (action title patterns)
4. `rules/mece.md` (MECE + Rule of 3)
5. `rules/formatting.md` (slide anatomy + source citation)
6. `rules/visuals.md` (chart and layout decisions)
7. `examples/{closest-match}.md` (the user-provided gold-standard deck or other examples)

If `calibration.md` overrides any rule from the `rules/` files, the `calibration.md` version wins.

## Step 4. Produce the deck plan

Output a markdown deck plan with the same format the renderer expects:

```
# {Action title for the whole deck}

**Audience:** {from calibration}
**Length target:** N slides
**Storyline (SCR):**
- **S:** {one sentence}
- **C:** {one sentence}
- **R:** {one sentence}

---

## Slide N: {Action title}
**Layout:** title | content | divider
**Body:**
- {one-line argument}
**Visual:** {visual-spec, see rules/visuals.md and the spec table below}
**Source footer:** Source: {data source, year}
```

### Visual spec types

- `bar`, `line`, `column-grouped`, `pie` (charts)
- `matrix-2x3`, `3-card`, `comparison`, `roadmap` (layouts)
- `risk-table`, `decision-table` (closing-deck tables)
- `none` (title and divider slides)

See `rules/visuals.md` for full syntax.

## Step 5. Render to .pptx

```bash
python3 scripts/generate.py output/your-deck-plan.md output/your-deck.pptx
```

If `template.pptx` exists in this folder, it is used as the master and your branding inherits automatically.

## Calibration template

When writing `calibration.md` after the interview, use this exact format:

```markdown
# Calibration for {team name}
Calibrated: {YYYY-MM-DD}

## Audience
{answer to Q1}

## Length default
{answer to Q2}

## Branding
- Primary color: {hex}
- Accent color: {hex}
- Fonts: {fonts}
- Template file: {path or "default"}

## Language
{answer to Q4}

## Voice constraints
{list form, one rule per line}

## Gold-standard reference
{path or outline of the reference deck}

## Calibration test scores

| Run | Date | Structure | Titles | Narrative | Formatting | Accuracy | Notes |
|---|---|---|---|---|---|---|---|
| 1 | YYYY-MM-DD | x/5 | x/5 | x/5 | x/5 | x/5 | corrections applied |

## Rule overrides
{any rule that diverges from rules/*.md, captured per-team here}
- {override 1, with reason}
- {override 2, with reason}
```

## Forking checklist (for new users)

1. Copy this whole folder to your skills directory: `cp -r team-deck-template ~/.claude/skills/{yourteam}-deck`
2. Edit the new `SKILL.md` line 2: change `name: team-deck` to `name: {yourteam}-deck`.
3. (Optional) Drop your branded `template.pptx` in the folder root.
4. (Optional) Drop 1-2 finished historical decks into `examples/` to give the calibration interview something concrete to reference.
5. In Cowork or Claude Code, ask for any deck. The Skill enters interview mode automatically.
6. Answer the six questions. The Skill writes `calibration.md`.
7. Run the calibration test. Iterate until structure / titles / narrative all score 4+.
8. Done. Future deck requests skip the interview and produce calibrated output directly.
