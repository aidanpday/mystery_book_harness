# UNIVERSAL QUALITY CHECK

Every step must run these quality checks after running and before adding a change log entry. The output from that step must pass ALL of the following checks.

If any output fails a single check, it must not be accepted. The agent must log the specific failure, and immediately rework the output with targeted corrections.

## 1. Deliverable format

- **1.1 Template conformance:** The output follows the exact structure defined in the step's `template.md`. No template sections are omitted, re-ordered, or summarized away.
- **1.2 No placeholders:** The deliverable contains exactly 0 unfilled placeholder brackets, tags, or tokens (e.g., `[...]`, `<...>`, `TODO`, `TBD`, `INSERT_X`).
- **1.3 No artifacting:** The output contains only the formal deliverable. Zero conversational chat filler, conversational meta-commentary (e.g., "Here is your deliverable..."), or incomplete stubs.
- **1.4 Scope correctness:** The output strictly fulfills the mandate of the current step without introducing elements reserved for future steps.

## 2. Anti-drift and goals

- **2.1 Immutable goals:** The output must not contradict, alter, or retcon `4_data/01_goals.md`.
- **2.2 Location drift:** All narrative events after act 1 and before the denouement remain within the bounded experience. Zero external interventions, flashbacks, or cutaways.
- **2.3 Consistency:** Character names, the MacGuffin, and any systems/organizations relevant to the story have the same names and properties across all files.

## 3. Tonal check

- **3.1 Seriousness calibration:** Check `4_data/02_style.md` to ensure output has the correct seriousness on the tonal scale.
- **3.2 Blacklist:** Output contains zero blacklisted words or concepts, from `4_data/02_style.md`.

## 4. Mystery fair-play

- **4.1 Domain expertise:** Character actions tend towards the things they are competent in. Characters do not display brilliant skill in topics they are unfamiliar with.
- **4.2 Solvability:** All clues must be fully observable by normal human senses (sight, touch, smell, sound) or deducible from conversation and alibi contradictions. Clues should also be subtle, with meaning obscured.
- **4.3 No measurements:** Omit all calculations to verify exact numbers. Do not track exact weights, distances, etc.
- **4.4 Procedural Stakes Integrity & No Arbitrary Leniency:** Stakes and consequences established early must have follow-through for characters unable to avoid them.
- **4.5 Focus on tactile experience:** Descriptions and observations focus on tactile and sensory feel (temperature, heft, texture, etc.) rather than exact technical properties.
- **4.6 No beaurocratic solutions:** No legal mentions. No bureaucratic
- **4.7 Strict Ban on Money & Finances:** Money and finances are strictly banned from steps 00–12. Money is not a compelling motivation. Characters can generally be rich or generally be poor, but none of what they do in the story should affect that. Exactly 0 financial motives, debts, bankruptcies, monetary gains/losses, or financial leverage are permitted to drive any character action, secret, alibi, or plot development.

## 5. Narrative Economy, Language Simplification & Prose Rigor

* [ ] **5.1 Progressive Condensation & Anti-Echo Protocol:** Never re-explain mechanical solutions or deductions already established or witnessed by the reader. Successive references must condense technical details into sharp dramatic leverage rather than recapitulating the puzzle mechanics from scratch.
* [ ] **5.2 Reader-Centric Staging (SOP 6):** Let physical facts, character reactions, and scene events speak for themselves. Zero narratorial handholding explaining the "significance" or thematic meaning of an event to the reader.
* [ ] **5.3 Rule 10 Syntactic Rigor (Universal for All Prose and Narrative Text):**
  - **Zero Semicolons in Narration:** Exactly 0 semicolons in narrative prose.
  - **Em-Dashes Dialogue-Only:** Em-dashes (`—`) are restricted strictly to dialogue quotation marks to denote spoken interruptions or cutoffs. Exactly 0 em-dashes in narration.
  - **Zero Rhetorical Meta-Questions in Narration:** Narrative prose contains zero rhetorical self-musings (e.g., *"Could it be that...?"*). Internal thoughts must be rendered as active, direct deductions or sensory observations.
  - **Zero Weak Qualifiers:** Eliminate weak qualifiers (`seemed`, `almost`) in narration.
* [ ] **5.4 Banned AI Vocabulary & Somatic Clichés:** Exactly **0** occurrences of:
  - *Banned AI filler:* `palpable`, `tapestry`, `testament`, `unyielding`, `structural`, `cacophony`, `unspoken`, `visceral`, `labyrinthine`, `dance of shadows`.
  - *Banned somatic clichés:* non-freezing `shudder` / `shuddered`, `breath caught in throat` / `breath hitched`.
  - *Banned melodramatic speech attributions:* `barked`, `hissed`, `bellowed`, `roared` (use `said`, `replied`, or active physical beats).
* [ ] **5.5 Action-First Staging (*In Media Res*):** 100% of scenes, chapters, and section openings plunge immediately into direct character action, an object, or dialogue. Zero atmospheric filler, weather descriptions, sunset musings, or room lighting recaps.
* [ ] **5.6 Anti-Jargon & Pre-Approval Gate:** AI tends to use jargon: several words to describe or embellish a function, when there's a simple, non-technical term. Jargon is allowed strictly and only in the specific case where it serves the reader experience and was approved beforehand. Step 12 drafting may not introduce ANY jargon at all outside the pre-approved registry, because all technical terms must be planned in advance.
* [ ] **5.7 Post-Step Language & Intent Simplification (The Hammer Rule):** After every single step, language and intent should be simplified for clarity. A 3.5mm hammer from Shanghai is ultimately just a hammer, and the other details should be skipped. Once these details have been stripped, the story must still make complete sense in-universe.
* [ ] **5.8 Mannerism & Habit Phrasing Variation Gate:** While characters possess distinct habits, character gestures, mannerisms, and physical descriptions must NEVER repeat verbatim across scenes or chapters. Each appearance of a habit must be rephrased, freshly observed, and moulded to the character's immediate emotional tension, lighting, and interacting props.
* [ ] **5.9 Chapter Titling & Labeling Gate:** Chapter titles are strictly for internal cohesion during planning and context briefing. They must not appear in the final chapter; chapters must only be labelled "chapter 01" (or "Chapter 01") etc.
* [ ] **5.10 Step 12 File Output Integrity:** Step 12 produces strictly individual chapter files (`4_writing/12_chapters/chapter_XX.md`) and NO other files (no verification files, no separate context dossier files, and no large compiled version of everything).
* [ ] **5.11 Step 13 Master Presentation Gate:** Step 13 collects all chapter files into one big file ready for presentation (`4_writing/13_revision.md`). The output file must not include any fields other than the text itself (zero audit tables, zero verification checklists, zero metadata fields).
* [ ] **5.12 Organizational Clue & Slip Labeling Boundary Gate:** Metadata identifiers such as `CLUE-0*`, `CLUE-XX`, and `SLIP-XX` are strictly authorial/organizational labels for outline tracking, fair-play matrices, and verification checklists. They must NEVER appear in narrative prose or character dialogue in-universe. Characters have zero awareness of these cataloging tags and must refer to items naturally by their tangible in-universe identities.
