# NOVEL FOCUS

We write novels using AI agentically. Our ultimate goal is to write a novel that has maximum quality to readers. Our north star, though, is to iterate quickly and to learn from each iteration. We run a breadth of experiments to prototype many possible options. Every prototype, we evaluate its results and its process.

## WORKFLOW

HARNESS: pass instructions to an iteration
ITERATION: for each step,
    - run step instructions
    - run quality checks
    - run change log instructions
ITERATION: output final draft and generate other eval docs
HARNESS: review eval docs to tweak instructions

## HARNESS

This repository is the project manager that manages iterations. Each iteration has distinct documentation (`1_plan/` and `2_steps/`) because the goal of each iteration is to evaluate a distinct set of instructions.

Each prototype should efficiently complete its steps, so that iteration is cost effective. Since we learn from every step, we prefer to iterate cheaply and frequently. Prototypes do not need much polish.

After a prototype is complete, its report is stored in the harness as an entry. Each entry is a folder numbered sequentially containing the eval steps. A human will review the reports to determine which feedback is actionable. Then, the harness updates `2_steps/` and begins another iteration.

### Which folders to modify

The goal of immutability is for our experiments to be fair, allowing us to measure relative success. The `1_plan/` folder must remain constant between iterations. The instructions to generate entries in `03_change_log/` and `05_evaluation` must be exactly the same. By contrast, `2_steps/` and the seed info in `4_data/` (goals, style guide) should take different general approaches. This is to compare the instructions we try.

IMMUTABILITY (HARNESS): The harness should create `1_plan/` which should not change at all. The harness should also create steps for evaluation steps (manuscript format, manuscript review, change log learnings, suggestions) which should not change at all. The harness may change `2_steps/` and seed data.

IMMUTABILITY (ITERATION): To any iteration, `1_plan/`, `2_steps/`, and the goals file in `4_data/` become immutable. Entries in `3_change_log/` can be added but may not be modified once they have been created. Files in `4_data/` may be modified (including the style guide but NOT the goals file). `5_evaluation/` may only be added at the end by the universal eval steps.

### How to choose different instructions

The harness is a means to test and compare the results from varied instructions. Each set of instructions is a data point in a vast field. Try breadth first search first, to survey the possible options. Each set of instructions must still be rigorously defensible, using fiction-writing advice and frameworks from respected authors.

`4_data/01_goals.md` can use different plot configurations and general ideas. Take inspiration here from successful works from the same industry, highlighting which elements to encourage.

The main agency is to choose different steps to use, and to update the requirements in each step. Stories have many possible concepts to them. Try formulations that include or exclude certain types of step, or that change the order (to shift emphasis).

After several prototypes, the focus shifts to refine the instructions within existing steps. However, every iteration should changes the step contents at least a little.

## EACH ITERATION

Prototypes should be fast and cheap to run. The goal is not to polish each individual run. Rather than tweaking an imperfect approach so perfectly that it can produce good results, we should fail quickly in varied ways to triangulate on an approach that produces generally good output. We can polish the model once we are confident that the instructions are in the right direction.

Each iteration is a fresh repository with the folders:
- `1_plan/`
- `2_steps/`
- `3_change_log/`
- `4_data/`
- `5_evaluation/`

### 1_plan/

This folder holds universal documentation:
- Project details
- Change log instructions
- Evaluation instructions

### Project details

Main goals for the project to adhere to. This is set at a project level and does NOT change between iterations. Details that may possibly change between iterations belong in `4_data/01_goals.md` instead.

This file is intended to clarify:
- Genre
- Target audience
- Target outcomes for the reader
- Parameters for the project (i.e. wordcount, which AI model to use, etc.)

### Change log instructions

Must be run after every step of instructions, no exceptions. Generates a sequential file in `3_change_log/` that form a record. These entries should be brief yet complete accounts of problems encounters and decisions made.

### Evaluation instructions

These are to be run once the prototype is completely drafted. This document details the steps to generate the documents in `5_evaluation/`, one at a time.

### 2_steps/

The reason we use steps is that human authors don't just immaculately conceive of a book. They start with an idea that grows as they write it. Human writers think of pieces out of order, as they find inspiration. We use an AI process. We must generate a book procedurally, with one step after another. All characters are generated at once, and revision only happens if it's explicitly listed.

Steps should provide a clear basis of truth. We want to isolate creative decisions early in the process, so that the prose can simply glide through the story already described. 

Chapters are generated one by one in isolation, so it's important to share a context. This anchors all the chapters together, preventing drift between them.

### Purpose and organization

Some steps introduce new content. For example, a step might generate a list of characters. Another step might generate a timeline of all events in the story, and what each character was doing at that time. All steps have an index, but there is also a "new content step" index. These steps should add files to `4_data/` under a file that uses the new content step index.

For example, if step 1 is a new content step and step 2 is a review step and step 3 is a new content step, then step 3 has a new content step index of 2. Content generated from this step is put in `4_data/02_{step_name}.md`. If step 3 produces more than one file of output, it instead creates a folder in the format `4_data/02_{step_name}.md`.

Review steps are ones that look at (and change) the existing files in `4_data/` rather than making new files. Review steps should aim to make minimal changes, only where necessary. They can have the following goals:
- to align files to one source of truth
- to identify pieces that don't serve the overall project goals, and refactor them
- to identify issues early, and course correct

### Mandatory steps

Each step should be run by a fresh agent context. Each step runs the instructions for the step, against its template, to generate a result. After this, every step must perform, without exception:
- quality checks (in `2_steps/QUALITY_CHECK.md`)
- change log instructions (in `1_plan/CHANGE_LOG.md`)

The last step for every iteration is strictly required to run the evaluation steps `1_plan/EVALUATION.md`.

### Possible step ideas

New content steps:
- Character bible - Detailed descriptions of each character's relationships, goals, tendencies, etc. Informs the interactions between characters.
- Scene lists - List of all events that take place in the book, with detailed descriptions of the story beats within each scene. This are used as context files to write chapters.

Review steps:
- Are the entries in `4_data/` myopically obsessed with details that don't enhance the reader's experience?
- What are the most interesting and engaging ideas so far? Can we shift the focus of the story towards those?
- Can we simplify and choose clearer terms for character descriptions?

### 3_change_log/

This folder stores entries generated from `1_plan/change_log.md`. Each entry has a sequential number in its prefix. For example, `3_change_log/005_step_5.md` labels the 5th entry, written by the agent right after it finishes step 5.

### 4_data/

This folder stores the results of running the instructions from `1_plan/` and `2_steps/` via agentic AI.

Every step should check the instructions, then check the output in `4_data/`. Then it will likely generate a new file in this folder OR modify existing files. When one step creates multiple files, it should create a folder within `4_data/`, labelled with the step name. For example, if step 12 generates 5 chapter files, they would be stored in `4_data/12_chapters/03.md`.

The harness passes two folders as seed values to begin an iteration:
- `01_goals.md` (malleable by the harness, immutable within a prototype)
- `02_style.md` (malleable to all)

`01_goals.md` is the source of truth for storytelling decisions. It should guide every other step because nothing added to `4_data/` is allowed to contradict `01_goals.md`.

`02_style.md` is a list of writing rules that strictly must be adhered to by chapter drafting. Output from other steps should use these style rules when possible, too, though they do not have a strict requirement.

### 5_evaluation/

This folder has four files generated in a sequence of steps.
- `01_manuscript.txt`
- `02_review.md`
- `03_learnings.md`
- `04_suggestions.md`

`01_manuscript.txt` is the prototype made by the iteration. It is the final step of creative work. It is stored here because it should be passed from the iteration to the harness. `01_manuscript.txt` should be a plain text version of the story, intended for a reader. It should have no internal fields. This is the output.

`02_review.md` is generated second. The goal is to judge whether the prototype has succeeded.

It is done by evaluating `5_evaluation/1_manuscript.txt` against the design goals set at the start (`1_plan/01_overall.md` and `1_plan/02_rubric.md`). This evaluation should give an unbiased general score out of 100, for the overall quality. It should also rank each part of the project to determine which parts were good and bad (judged according to the rubric). List the main issues and the main successes in `02_review.md`.

`03_learnings.md` is generated third. It reviews all entries in `03_change_log/` to aggregate its data. The goal is to understand where each specific problem began.

First, it should check change log entries to group problems. Some are one-offs, while other issues may come up repeatedly. Problems that arise multiple times are more likely to be structural. However, `03_learnings.md` must report one-off issues because they might be structural too. Consider the case where an issue comes up exactly once for every iteration; this would be structural to the harness. Thus, one-off issues must be reported too. For repeat issues, try to determine the similarities and shared truth. This helps understand the underlying cause of the problem.

Lastly for learnings, check `5_evaluation/02_review.md` for the problems that it brings up. Scan all change log entries to find the first instance where a decision creates that issue. `03_learnings.md` aims to pair every problem to the decision where it originated.

`04_suggestions.md` is a list of changes proposed from within an iteration to the overall harness. While `5_evaluation/02_review.md` and `5_evaluation/03_learnings.md` focus on issues and clarifying what the problems are, this file suggests solutions. Praise for a topic should be a weight against change. Criticism and problems are a weight towards change. Propose several different possible solutions.
