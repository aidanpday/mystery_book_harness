# Iteration Workflow

This document defines the exact agentic procedure for running one batch **iteration** on a single isolated step in `2_steps/<NN_step_name>/`.

## 1. Load Fixed Controls & Prior Midpoints

1. Read the harness baseline:
   - `1_harness/01_project.md`
   - `1_harness/02_goals.md`
   - `1_harness/03_style.md`
2. Read the target step's baseline:
   - `2_steps/<NN_step_name>/base_instructions.md`
   - `2_steps/<NN_step_name>/context.md` (if present)
3. Determine the next sequential two-digit iteration folder: `2_steps/<NN_step_name>/iterations/<NN>/` (starting at `01`).
4. If `<NN>` is `02` or higher, read `iterations/<NN-1>/evaluation.md` and extract the **1–2 Chosen Midpoints** (and any human notes on dimensions to preserve or vary).

## 2. Generate 50 Directions & Select the Best 10

1. **Brainstorm 50 distinct artistic directions** for executing this step's single unit:
   - **Iteration `01` (no prior midpoint):** Survey the broadest viable field via breadth-first search. Draw on diverse fiction-writing frameworks, structural theories, and artistic inspirations so the 50 candidates span genuinely distinct creative angles.
   - **Iteration `02+` (1–2 midpoints provided):** Anchor around the chosen midpoint(s). None of the 50 candidates may copy a midpoint verbatim; each must propose a specific variation, shift in emphasis, structural modification, or synthesis in the neighborhood of the midpoint(s).
   - Every candidate must remain compatible with the universal constraints in `1_harness/` (e.g., bottle mystery scope, fair-play solvability, zero money or legal statutes) and testable within the step's single-unit conciseness cap.
2. **Sort all 50 directions by viability** from strongest to weakest based on:
   - **Testability on the unit:** Will the difference in direction be clearly visible in a concise single-unit output?
   - **Craft rigor:** Is the direction grounded in a defensible storytelling principle rather than a gimmick?
   - **Distinctiveness:** Does the top 10 cover meaningfully different hypotheses rather than minor rewordings of the same idea?
   - **Audience & mystery leverage:** How strongly does it serve intrigue, fair-play misdirection, and reader enjoyment?
3. **Pick the top 10 distinct directions** (numbered `01` through `10`).
4. Write `iterations/<NN>/directions.md` recording:
   - Input midpoint(s) (or `None — Iteration 01 wide breadth-first survey`)
   - The **Top 10 Selected Directions** (`01`–`10`), each with a concise title, craft rationale, and specific angle
   - The **Remaining 40 Ranked Candidates** (`11`–`50`) in viability order for auditability

## 3. Run 10 Prototypes Concurrently

Launch 10 isolated prototype runs concurrently (one per selected direction `01`–`10`), all using the **same AI model**:

For each direction `XX` (`01` through `10`):

1. **Generate minimal instructions** (`iterations/<NN>/instructions/XX.md`):
   - Start from `base_instructions.md` and specialize it for Direction `XX`.
   - Keep instructions minimal, direct, and focused on the core hypothesis of Direction `XX`. Avoid burying the core directive under tangential advice.
   - Preserve the step's single-unit scope and word-count ceiling so all 10 outputs remain comparably concise.
2. **Execute the instructions once** (`iterations/<NN>/outputs/XX.md`):
   - Run `instructions/XX.md` against the fixed baseline context (`1_harness/` + optional `context.md`) in a single pass with no intermediate files or change logs.
   - **Deliverable cleanliness:** Write *only* the requested unit output to `outputs/XX.md`—zero unfilled placeholders (`TODO`, `[...]`), zero meta-commentary, and zero conversational preambles.

## 4. Prepare the Human Evaluation Scorecard

1. Copy `1_harness/05_evaluation_template.md` to `iterations/<NN>/evaluation.md`.
2. Pre-populate the metadata header (step name, unit scope, iteration number, model identifier, and prior midpoints) and fill in the title and 1–2 sentence summary for Directions `01`–`10` in both the quick comparison table and each per-direction scorecard.
3. Leave all score fields, human notes, and the `Chosen Midpoints for Next Iteration` section blank for the human reviewer to complete.

