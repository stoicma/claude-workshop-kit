# examples/

Drop 1-2 finished historical decks (sanitized) here before running the calibration interview. The Skill references them when producing your deck plans.

Format: any of these work
- `.pptx` files (the renderer cannot read these directly, but they tell the Skill what your output looks like)
- `.md` files with slide-by-slide outlines (action titles + body + visual notes per slide). See `examples/01-market-entry.md` in the McKinsey deck Skill for the format.
- `.pdf` files (Skill can read these for structural reference)

What "sanitized" means:
- Replace real client names with placeholders ("Acme", "Client A")
- Mask sensitive numbers if the team data-sensitivity policy requires it
- Keep structure, narrative, and visual choices intact

Why the Skill needs this:
- The calibration interview asks for a "gold-standard reference deck"
- The reference is what the calibration test regenerates
- Without one, the Skill cannot measure whether its output meets your team's quality bar

If you have nothing to drop here, the Skill defaults to McKinsey-style output. That is usable, but not calibrated to your team. The fork is more valuable when you have at least one real example.
