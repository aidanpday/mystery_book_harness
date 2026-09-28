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
- **4.6 No beaurocratic solutions:** No legal mentions. Outcomes should focus on people rather than technicalities.
- **4.7 No mention of finances:** Exactly 0 financial motives, debts, bankruptcies, monetary gains/losses, or financial leverage are permitted to drive any character action, secret, alibi, or plot development.
