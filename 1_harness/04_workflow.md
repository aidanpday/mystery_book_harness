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
3. Determine the next sequential two-digit iteration folder: `3_runs/iteration_XX/` (starting at `iteration_01`).
4. If a prior iteration in `3_runs/` exists for this target step (or is specified by the user), read its `eval.md` (`Best directions to pursue later`) and extract the **1–2 chosen directions** (plus any pros/cons notes) as input midpoints.

## 2. Generate 50 Directions & Select the Best 10

1. **Brainstorm 50 distinct artistic directions** for executing this step's single unit. You are encouraged to pick directions based on successful authors and stories that already exist:
   - **First iteration on this step (no prior midpoint):** Survey the broadest viable field via breadth-first search. Draw on diverse fiction-writing frameworks, structural theories, and artistic inspirations so the 50 candidates span genuinely distinct creative angles.
   - **Follow-up iteration on this step (1–2 midpoints provided):** Anchor around the chosen midpoint(s). None of the 50 candidates may copy a midpoint verbatim; each must propose a specific variation, shift in emphasis, structural modification, or synthesis in the neighborhood of the midpoint(s).
   - Every candidate must remain testable within the step's single-unit conciseness cap.
2. **Sort all 50 directions by viability** from strongest to weakest based on:
   - **Craft rigor:** Is the direction grounded in a defensible storytelling principle rather than a gimmick?
   - **Distinctiveness:** Does the top 10 cover meaningfully different hypotheses rather than minor rewordings of the same idea?
   - **Audience & mystery leverage:** How strongly does it serve intrigue, fair-play misdirection, and reader enjoyment?
3. **Pick the top 10 distinct directions** (numbered `01` through `10`), corresponding to subfolders `3_runs/iteration_XX/01/` through `3_runs/iteration_XX/10/`.

## 3. Run 10 Prototypes Concurrently

Launch 10 isolated prototype runs concurrently (one per selected direction `01`–`10`), all using the **same AI model**:

For each direction `DD` (`01` through `10`), inside subfolder `3_runs/iteration_XX/DD/`:

1. **Generate modified instructions** (`3_runs/iteration_XX/DD/instructions.md`):
   - Create a modified version of the target step's `base_instructions.md` by prioritizing the unique direction `DD`.
   - Keep instructions minimal, direct, and focused on the core hypothesis of Direction `DD`. Avoid burying the core directive under tangential advice.
   - Preserve the step's single-unit scope and word-count ceiling so all 10 outputs remain comparably concise.
2. **Execute the instructions once** (`3_runs/iteration_XX/DD/output.md`):
   - Run `DD/instructions.md` against the fixed baseline context (`1_harness/` + optional `context.md`) in a single pass with no intermediate files or change logs.
   - **Deliverable cleanliness:** Write *only* the requested unit output to `3_runs/iteration_XX/DD/output.md`—zero unfilled placeholders (`TODO`, `[...]`), zero meta-commentary, and zero conversational preambles.

## 4. Prepare the Human Evaluation Scorecard

1. Copy `1_harness/05_evaluation_template.md` to `3_runs/iteration_XX/eval.md`.
2. Pre-populate the metadata header (`<Step Name>`, `Iteration <XX>`, `Step`, and `Input Midpoint(s)`) and fill in the `<Title>` and 1–2 sentence `Direction Summary` for Directions `01`–`10` in each per-direction scorecard.
3. Leave all score fields, `Good` / `Bad` notes, and the `Best directions to pursue later` section blank for the human reviewer to complete.

