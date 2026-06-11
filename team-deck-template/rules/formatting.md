# Slide formatting rules

## The slide anatomy

Every content slide has three zones:

1. **Header (action title).** Top of the slide. One line. 24-28pt bold. Never wraps to three lines. If it wraps to two, the second line is shorter than the first.
2. **Body.** Center of the slide. The evidence. Charts, text, diagrams. One message only.
3. **Footer (source).** Bottom of the slide. 9-10pt. Format: `Source: {data source name, year}`. If multiple sources: `Source: {primary source, year}; {secondary source, year}.`

## One message per slide

If the slide has two equally-weighted points, it has two messages. Split it. Two crisp slides beat one busy one. The audience reads slide titles to follow the argument; two titles is two beats of the argument.

Tell yourself: "The takeaway from this slide is ___." If the blank takes more than 12 words to fill, the slide has too much.

## Visual hierarchy

- **One dominant element per slide.** A chart, a diagram, or a card grid. Not all three.
- **White space is content.** Empty space directs the eye. Cluttered slides hide the conclusion.
- **Color carries meaning, not decoration.** Use the accent color to mark the point that matters. Greys for everything else.
- **Charts have action titles too.** Not "Revenue by quarter (chart 3)" but "Q4 carried 60% of full-year revenue".

## Default visual specs (when no template.pptx is provided)

- Background: white (#FFFFFF)
- Primary text: dark navy (#0A2540)
- Accent (for emphasis, not decoration): orange (#E76F00) or muted blue (#1A6FB8)
- Fonts: Helvetica or Inter (sans-serif). 28pt titles, 18pt body, 10pt footers.
- Margins: 0.5 inch all sides minimum. Content area never touches the edges.

## Source citation discipline

Every number on a slide has a source in the footer. No exceptions on data slides. Sources are how decks survive a senior partner pushing back: "Where does that number come from?"

Acceptable sources:
- Public reports (named): "Source: McKinsey Global Institute, 2024"
- Industry data (named): "Source: BloombergNEF, EV Outlook 2025"
- Proprietary data (named): "Source: client data, FY2024 management accounts"
- Synthesis: "Source: team analysis based on {primary source}"

Never acceptable:
- "Internet research"
- "Public information"
- "Various sources"
- No source at all

## What does NOT belong on a slide

- Decorative icons that do not encode meaning
- Stock photos of handshakes / globes / cityscapes
- Three different chart styles in the same deck
- Italics for emphasis (use weight or color)
- Underlines (suggest hyperlinks)
- ALL CAPS BODY TEXT
- Generic transitions or animations (none in this Skill's output)

## Output handoff

The Skill produces a markdown deck plan first. Visual rendering happens in `scripts/generate.py` which reads the markdown and writes a `.pptx`. Keep the markdown plan readable as a standalone artifact. The team should be able to review it without rendering, catch structural issues at the cheap stage.
