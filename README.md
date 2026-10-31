# NOVEL FOCUS

We write novels using AI agentically. The goal is NOT to draft a complete novel, nor is it to deliver a quality end product. Our north star is to iterate quickly and to learn from each attempt. Art is complex, so we will try many possibilities to slowly hone in on a good path.

We run a breadth of experiments to prototype many possible options. Every prototype, a human evaluates the output. Overall quality is irrelevant because the purpose is to evaluate the direction & instructions, using the output as a proxy. Each experiment uses the same model to ensure apples-to-apples comparisons. 

We follow the scientific process. Thus, we optimize for limited scope. Output must be fast for a human to review (i.e. concise) and they strictly must test a small unit of the decision-making process. A novel is complex web of interwoven ideas, and our goal is to reduce it to the smallest possible units.

Thus, we prototype each step of the novel individually, on smallest parts. For example, if one step of the novel-writing process is to make character bibles, then we would prototype one character, over and over. Each step gets its own round of prototypes.

Each iteration has 10 prototypes. Within an iteration, imagine an unknown field of all possible artistic choices and directions. We first choose 10 distinct possible artistic directions, then we generate a set of minimal instructions for each of them, then all 10 are run as prompts. Finally, a human reviews all 10 outputs, scoring them using a template.

The next iteration uses the first 1-2 directions as a "midpoint" for the next 10 possible artistic choices. These new 10 directions must not copy the midpoint but must test possibilities similar to them. The goal is to find the best direction in the field via breadth-first search.

## WORKFLOW

HARNESS: pass a step & a base set of instructions
ITERATION:
    - generate 50 possible directions
    - sort based on viability. pick the best 10
    - PER DIRECTION (concurrently):
        - generate instructions based on the direction
        - run the instructions to generate output
HUMAN: review output and score the directions chosen. pick 1-2 to continue with

## HARNESS

This repository is the experimental harness that manages isolated step iterations. Rather than running an entire novel pipeline end-to-end, the harness tests **one novel-writing step at a time**, scoped down to its **smallest testable unit** (for example: one setting zone, one character profile, one clue chain, or one short scene).

Each iteration runs a batch of **10 concurrent prototypes** for that single unit. Because execution per prototype is at most one step of instructions with no intermediate artifacts, prototypes are fast to run and concise enough for a human to review side-by-side in minutes. Prototypes do not need end-product polish; their output serves strictly as a proxy to evaluate the underlying artistic direction and instructions.

### Scientific Controls & Immutability

Fair, apples-to-apples comparisons require holding everything constant except the artistic direction and the minimal instructions derived from it:

- **Immutable across a step's iterations (Controls):**
  - `1_harness/` — project parameters, baseline story goals, style guardrails, iteration workflow, and the human evaluation template.
  - **The AI model** — every prototype in an experiment uses the exact same model.
  - **The step baseline** — the target step's `base_instructions.md` (defining the unit scope and base deliverable shape) and any fixed upstream `context.md` fixture.
- **Variable within an iteration (Independent Variable):**
  - The 10 chosen artistic directions and their modified instruction sets (`3_history/iteration_XX/01/instructions.md` through `10/instructions.md`, derived from the step's `base_instructions.md` by prioritizing each unique direction).
- **Immutable once recorded (Experimental Record):**
  - Once an iteration folder (`3_history/iteration_01/`, `3_history/iteration_02/`, etc.) completes and a human records scores in `eval.md`, that iteration directory is frozen. A follow-up iteration on that step reads the 1–2 chosen directions ("midpoints") from the completed `eval.md` and writes to a fresh `3_history/iteration_XX/` folder.

### Choosing Artistic Directions & Minimal Instructions

The harness explores a vast field of creative possibilities via breadth-first search. Within each iteration, 50 candidate artistic directions are brainstormed, sorted by viability for the target unit and project constraints, and narrowed to the best 10 distinct options.

Every direction must be rigorously defensible, drawing on fiction-writing frameworks and craft advice from respected authors. Take inspiration from successful works of art, highlighting specific structural or stylistic elements to encourage (and pitfalls to avoid).

How directions are generated depends on whether a prior iteration on that step has established an "overall direction" (the 1–2 human-selected midpoints):

- **If no "overall direction" (midpoint) is given (first iteration on a step):** Survey the widest possible space of viable artistic choices. The 50 candidates—and the top 10 selected—should test fundamentally different craft philosophies, focal priorities, and structural approaches so the initial batch maps the broader landscape.
- **If an "overall direction" (1–2 midpoints) is given (follow-up iteration on a step):** Each new direction must include specific modifications that test possibilities around the midpoint(s) without copying them verbatim. Treat the 1–2 midpoints as a center of gravity—vary emphasis, framing, tension mechanics, or level of abstraction to triangulate on the strongest formulation in that neighborhood.

For each of the 10 selected directions, an isolated agent creates a subfolder (`01/` through `10/`) under `3_history/iteration_XX/`, writes `instructions.md` as a modified version of the step's `base_instructions.md` prioritizing that unique direction, and executes those instructions once to produce `output.md`. Instructions should stay lean and high-leverage rather than piling on tangential rules.

## REPOSITORY STRUCTURE

```text
.
├── 1_harness/                  # Universal baseline rules, story constants, & templates
│   ├── 01_project.md
│   ├── 02_goals.md
│   ├── 03_style.md
│   ├── 04_workflow.md
│   └── 05_evaluation_template.md
├── 2_steps/                    # Isolated novel-writing steps & baseline fixtures
│   ├── 00_step_catalog.md
│   └── <NN_step_name>/
│       ├── base_instructions.md
│       └── context.md          # Optional frozen upstream fixture for downstream steps
└── 3_history/                  # Iteration runs & historical learnings
    ├── early_learnings.md
    └── iteration_XX/           # One iteration batch (e.g., iteration_01/)
        ├── 01/ ... 10/         # 10 subfolders, one per direction tried
        │   ├── instructions.md # Modified base_instructions.md prioritizing this direction
        │   └── output.md       # Single-pass prototype output
        └── eval.md             # Evaluation scorecard copied from 05_evaluation_template.md
```

### 1_harness/

Holds the fixed project baseline and universal execution rules shared across experiments:

- **`01_project.md`:** High-level project parameters—genre (whodunnit mystery), target audience profiles, bounded "bottle" setting scope, and AI experimentation rules (fixed model, single-unit conciseness, single-step execution).
- **`02_goals.md`:** Baseline story truth (fabula vs. syuzhet principles, mystery fair-play constraints, and positive/negative artistic inspirations).
- **`03_style.md`:** Tonal calibration scale, universal content bans (no money, no legal statutes), and prose rules for drafting steps.
- **`04_workflow.md`:** Operational guide for running an iteration on a step: generating 50 directions, sorting and picking 10, running 10 concurrent prototypes into `3_history/iteration_XX/01/`–`10/`, and preparing `3_history/iteration_XX/eval.md`.
- **`05_evaluation_template.md`:** Consolidated human review template copied into each iteration as `3_history/iteration_XX/eval.md`.

### 2_steps/

Organizes the novel-writing process by individual step, holding each step's neutral base definition and any fixed input fixtures:

- **`00_step_catalog.md`:** Master list of steps in the mystery-writing process, defining how each step reduces to its smallest testable unit and how to write neutral base instructions.
- **`<NN_step_name>/base_instructions.md`:** Minimal, framework-neutral instructions for that step's isolated unit (for example, *one* character in `02_character_bible/` or *one* clue chain in `04_clues_syuzhet/`), including conciseness limits and base deliverable fields.
- **`<NN_step_name>/context.md`:** Optional frozen input context for downstream steps that depend on upstream story assumptions (such as a fixed sample scene beat sheet when prototyping prose directions in `08_scene_draft/`). Keeping `context.md` fixed ensures every prototype in an iteration starts from identical inputs.

### 3_history/

Stores all batch iteration runs (`iteration_01/`, `iteration_02/`, etc.) alongside historical learnings from earlier experiments:

- **`iteration_XX/`:** A single batch run of 10 prototypes for one target step:
  - **`01/`–`10/`:** 10 subfolders, one per artistic direction tried. Each subfolder contains two files:
    - **`instructions.md`:** A modified version of the target step's `base_instructions.md` that prioritizes this subfolder's unique artistic direction.
    - **`output.md`:** The concise single-unit output produced by running `instructions.md` once.
  - **`eval.md`:** Human evaluation scorecard copied from `1_harness/05_evaluation_template.md`. Records the target step, input midpoints, per-direction summaries and links (`01/instructions.md` and `01/output.md` through `10/instructions.md` and `10/output.md`), human scores and notes, and the 1–2 best directions chosen to pursue next.
- **`early_learnings.md`:** Historical notes from earlier novel-generation experiments that predate the batch step-prototyping harness, retained as craft and failure-mode reference material.
