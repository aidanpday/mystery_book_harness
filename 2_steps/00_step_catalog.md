# Step Catalog

Each step of the mystery-writing process is prototyped **in isolation** on its **smallest testable unit**. This keeps outputs fast for a human to compare across 10 concurrent prototypes and isolates a single layer of creative decision-making at a time.

## Isolated Steps & Unit Scopes

| Step Folder | Focus | Smallest Testable Unit | Target Length |
|-------------|-------|------------------------|---------------|
| `01_setting/` | Fabula | Overall bounded-location premise + **1 distinct zone** | ~250–350 words |
| `02_character_bible/` | Fabula | **1 single character** profile and reason for entering the location | ~200–300 words |
| `03_crime_fabula/` | Fabula | **1 core crime mechanism** (how the theft/deception physically works in reality) | ~250–350 words |
| `04_clues_syuzhet/` | Syuzhet | **1 deduction chain** (1–2 observable clues, misdirection, and true implication) | ~200–300 words |
| `05_timeline/` | Fabula | Chronological state slice across **1 key event window** (e.g., First Disruption) | ~200–300 words |
| `06_scene_list/` | Syuzhet | Sequence of **2–3 connected scenes** testing reader-facing ordering and reveals | ~250–350 words |
| `07_narrative_beats/` | Syuzhet | Granular beat-by-beat breakdown for **1 single scene** | ~250–350 words |
| `08_scene_draft/` | Syuzhet | Drafted narrative prose for **1 short scene or beat slice** | ~350–500 words |

## Principles for Base & Generated Instructions

1. **Keep `base_instructions.md` minimal and neutral:** Base instructions define *what* single unit is being produced, the word-count cap, and minimal required fields. Avoid baking a specific craft school or concrete story bias (such as mentioning a specific vehicle or building) into `base_instructions.md` so the 10 artistic directions per iteration have full room to explore.
2. **Ground directions in credible craft frameworks:** When generating `instructions/01.md`–`10.md` during an iteration, draw on respected fiction-writing frameworks (academics and accomplished mystery/fiction authors) and concrete lessons from successful works of art.
3. **Prioritize high-leverage instructions:** Writing advice is not of equal weight. Each prototype's generated instructions should emphasize 1–3 core creative levers that define its direction rather than diluting focus with tangential rules.
4. **Optimize for single-pass AI execution:** Because each prototype runs in a fresh, isolated context with no follow-up revision pass, instructions must clearly specify the output shape and distinguish internal planning labels (e.g., `C-01`, `MacGuffin`) from reader-facing prose.
5. **Use fixed `context.md` fixtures for downstream steps:** Steps `04`–`08` depend on upstream story assumptions. Their `context.md` files hold a frozen minimal fixture so all 10 prototypes in an iteration test against identical inputs. Once an upstream step converges on a winning output, you can freeze that output into downstream `context.md` files for subsequent experiments.

