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

## 2. Brainstorm 50 Options & Human Selection

1. **Brainstorm 50 distinct artistic options** in `3_runs/iteration_XX/brainstorm.md` as an isolated task. Do not intentionally generate better or worse ideas—all 50 must be viable, and there is no need to preemptively rank them:
   - **First iteration on this step (no prior midpoint):** Survey the broadest viable field via breadth-first search. Draw on diverse fiction-writing frameworks, structural theories, and artistic inspirations so the 50 candidates span genuinely distinct creative angles.
   - **Follow-up iteration on this step (1–2 midpoints provided):** Anchor around the chosen midpoint(s). None of the 50 candidates may copy a midpoint verbatim; each must propose a specific variation, shift in emphasis, structural modification, or synthesis in the neighborhood of the midpoint(s).
   - Every candidate must remain testable within the step's single-unit conciseness cap.
2. **Format `3_runs/iteration_XX/brainstorm.md` for rapid top-down review:**
   - **Top-level summary:** Keep the top-level summary block at the top of the file (`Step`, `Input Midpoint`, `Target Scope`, calibration, and constraints).
   - **Human selection section:** Keep `## Human Selection (Pick 10 to Pursue)` with numbered slots `1.` through `10.` (`[    ]`) for recording the 10 chosen option numbers (`01`–`50`).
   - **`## 50 options` section & bare numeric subtitles:** Name the overall section `## 50 options`. Each option subtitle must be *only* the two-digit number (e.g., `### 03`) with no title, label, or explanation.
   - **30–60 words total per option (no explicit section/bullet titles):** Optimize every option for a quick top-down pass to tell whether the idea has promise. Keep the entire option between **30 and 60 words** total, with **no bold field titles** on the summary or bullets:
     1. **Overall approach summary first:** Open immediately with a concise summary of the overall approach, spending most of the option's 30–60 word count here.
     2. **Style bullet:** One concise bullet naming the author or work being emulated and which basic traits are relevant (e.g., `- *Swan Song* by Edmund Crispin — crisp theatrical wit under unpausable live broadcast pressure.`).
     3. **Main decision bullets (2–10 words each):** One bullet per main decision for the iteration (for example, the content of the play, and the reason the play continues). Keep each decision bullet strictly between **2 and 10 words** for just the basic idea.
3. **Human selects 10 options to pursue:** Once the human records the 10 chosen option numbers in `Human Selection`, map those 10 selections to subfolders `3_runs/iteration_XX/01/` through `3_runs/iteration_XX/10/`.

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

