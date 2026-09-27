# Evaluation

This file contains instructions to populate the folder `5_evaluation/` via these steps:
1. Format the final manuscript for the reader.
2. Review the manuscript by applying the rubric.
3. Write a learnings document via the change log.
4. Suggest improvements to the instructions.

These instructions must run for every project as the last step.

## Manuscript

Combine the content of the chapters into one plaintext file `5_evaluation/01_manuscript.txt`. This file must be standalone and ready for a reader who will not see any other file from the project. Chapters should be separated by a header that states the chapter number (e.g. "Chapter 3") but exclude all other metadata and labels.

## Review

Use `1_plan/02_rubric.md` to generate a review of the manuscript. Put the review in `5_evaluation/02_review.md`.

Calculate each score individually and return a summary: the badness score, the goodness score, the mystery score. Explain the factors that went into the scores in a 100-200 word summary, per score type. Also list the 3 best and 3 worst elements of the story in the review, as well.

## Learnings

Use entries in `3_change_log/` to determine what problems the project had, and where mistakes were made.

### Find patterns in issues

Categorize the problems section of each entry. The goal is to group similar issues from different entries. Represent each group with the commonalities between the individual problems in that category. Some problems will not match with any other ones. List each group and their frequencies.

For example, the issues "character professions use jargon that overcomplicates simple roles" and "clues are unclear because they are hyperspecific and focused on logistical jargon" are similar, sharing the trait that "jargon made simple traits less clear and had to be simplified". However, "three characters share the same expertise and motivation" is distinct. This example has two distinct problems, with frequencies 2 and 1 respectively.

### Match problems to decisions

Use the review in `5_evaluation/02_review.md` to make a list of problems in the manuscript. For each problem, check entries in the change log, starting from the beginning. The goal is to match problems to the earliest decision that led to that result. This assigns blame for the issues, so we learn from the decision-making rather than just the result.

If a problem does not clearly match any decision that predecated it, list it with "no clear cause".

## Improvements

Read `5_evaluation/02_review.md` and `5_evaluation/03_learnings.md` to determine the issues with the text. Read the documentation in `2_steps/` to determine:
  - Which instructions helped improve the book?
  - Which instructions caused problems in the book?
  - What should have been instructed but was missed?

Use the answers to these questions to inform suggestions for future batches of steps. Positive feedback reinforces the instructions to keep. Negative feedback flags details to remove. Missing information suggests new steps or new instructions in existing steps.

Create a report summarizing these findings. Each suggestion must include a brief justification.
