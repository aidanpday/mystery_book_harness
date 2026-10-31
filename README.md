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
  - The 10 chosen artistic directions and their generated minimal instruction sets (`instructions/01.md` through `instructions/10.md`).
- **Immutable once recorded (Experimental Record):**
  - Once an iteration folder (`iterations/01/`, `iterations/02/`, etc.) completes and a human records scores in `evaluation.md`, that iteration directory is frozen. The next iteration reads the 1–2 chosen midpoints from the completed `evaluation.md` and writes to a fresh `iterations/<NN>/` folder.

### Choosing Artistic Directions & Minimal Instructions

The harness explores a vast field of creative possibilities via breadth-first search. Within each iteration, 50 candidate artistic directions are brainstormed, sorted by viability for the target unit and project constraints, and narrowed to the best 10 distinct options.

Every direction must be rigorously defensible, drawing on fiction-writing frameworks and craft advice from respected authors. Take inspiration from successful works of art, highlighting specific structural or stylistic elements to encourage (and pitfalls to avoid).

How directions are generated depends on whether a prior iteration has established an "overall direction" (the 1–2 human-selected midpoints):

- **If no "overall direction" (midpoint) is given (Iteration 01):** Survey the widest possible space of viable artistic choices. The 50 candidates—and the top 10 selected—should test fundamentally different craft philosophies, focal priorities, and structural approaches so the initial batch maps the broader landscape.
- **If an "overall direction" (1–2 midpoints) is given (Iteration 02+):** Each new direction must include specific modifications that test possibilities around the midpoint(s) without copying them verbatim. Treat the 1–2 midpoints as a center of gravity—vary emphasis, framing, tension mechanics, or level of abstraction to triangulate on the strongest formulation in that neighborhood.

For each of the 10 selected directions, an isolated agent generates a set of **minimal instructions** anchored to the step's `base_instructions.md` and immediately executes those instructions once to produce a concise output. Instructions should stay lean and high-leverage rather than piling on tangential rules.

## REPOSITORY STRUCTURE

```text
.
├── 1_harness/                  # Universal baseline rules, story constants, & templates
│   ├── 01_project.md
│   ├── 02_goals.md
│   ├── 03_style.md
│   ├── 04_workflow.md
│   └── 05_evaluation_template.md
├── 2_steps/                    # Isolated novel-writing steps & their iteration batches
│   ├── 00_step_catalog.md
│   └── <NN_step_name>/
│       ├── base_instructions.md
│       ├── context.md          # Optional frozen upstream fixture for downstream steps
│       └── iterations/
│           └── <NN>/
│               ├── directions.md
│               ├── instructions/
│               │   └── 01.md ... 10.md
│               ├── outputs/
│               │   └── 01.md ... 10.md
│               └── evaluation.md
└── 3_history/                  # Learnings from pre-harness experiments
    └── early_learnings.md
```

### 1_harness/

Holds the fixed project baseline and universal execution rules shared across experiments:

- **`01_project.md`:** High-level project parameters—genre (whodunnit mystery), target audience profiles, bounded "bottle" setting scope, and AI experimentation rules (fixed model, single-unit conciseness, single-step execution).
- **`02_goals.md`:** Baseline story truth (fabula vs. syuzhet principles, core plot outline, mystery fair-play constraints, and positive/negative artistic inspirations).
- **`03_style.md`:** Tonal calibration scale, universal content bans (no money, no legal statutes), and prose rules for drafting steps.
- **`04_workflow.md`:** Operational guide for running an iteration on a step: generating 50 directions, sorting and picking 10, running 10 concurrent prototypes, and preparing the human scorecard.
- **`05_evaluation_template.md`:** Consolidated human review template copied into each iteration as `evaluation.md`.

### 2_steps/

Organizes the novel-writing process by individual step so each step's base definition and all of its batch iterations live together:

- **`00_step_catalog.md`:** Master list of steps in the mystery-writing process, defining how each step reduces to its smallest testable unit and how to write neutral base instructions.
- **`<NN_step_name>/base_instructions.md`:** Minimal, framework-neutral instructions for that step's isolated unit (for example, *one* character in `02_character_bible/` or *one* clue chain in `04_clues_syuzhet/`), including conciseness limits and base deliverable fields.
- **`<NN_step_name>/context.md`:** Optional frozen input context for downstream steps that depend on upstream story assumptions (such as a fixed sample scene beat sheet when prototyping prose directions in `08_scene_draft/`). Keeping `context.md` fixed ensures every prototype in an iteration starts from identical inputs.
- **`<NN_step_name>/iterations/<NN>/`:** A single batch run of 10 prototypes for that step:
  - **`directions.md`:** Records any input midpoints from the prior iteration, all 50 brainstormed artistic directions sorted by viability, and the top 10 chosen for prototyping.
  - **`instructions/01.md`–`10.md`:** Minimal instruction files generated concurrently for each of the 10 chosen directions.
  - **`outputs/01.md`–`10.md`:** Concise single-unit outputs produced by running each corresponding instruction file once. Kept in a flat numbered folder so a human reviewer can step rapidly from `01.md` through `10.md`.
  - **`evaluation.md`:** Consolidated human scorecard instantiated from `1_harness/05_evaluation_template.md`. Contains a compact scorecard per direction tried (`01`–`10`), side-by-side comparison scores, brief notes, and the 1–2 winning directions chosen as midpoints for the next iteration.

### 3_history/

Stores historical notes (`early_learnings.md`) from earlier novel-generation experiments that predate the batch step-prototyping harness, retained as craft and failure-mode reference material.
