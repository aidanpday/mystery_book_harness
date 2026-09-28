# Rubric

This document scores a manuscript in a neutral manner. It records several different scores, categorized.

Simple texts can vacuously score well in the Flaw category, but this would result is awful scores in the Goodness category and Mystery category. It would lack parts that score highly. Robust manuscripts are the only possible way to score well in all three categories.

For each step, begin by answering the questions against the manuscript. Next, calculate individual scores per question. Lastly, add the scores together. It is unacceptable to generate a score before populating the evidence. Missing information defaults to the worst possible score.

Return the total score, the scores for each individual question, and a summary of important details.

## Flaw analysis (badness)

The purpose of this check is to verify that bad traits are absent from the text. A lack of flaws gives a high score. Use a scale from 1 to 20 for each question, where 1 means highly flawed and 20 means no flaws. The total score should be between 4 and 80.

Score the manuscript using the following questions:
  - 1
    QUESTION: Do locations, character interactions, and movements violate established causality or story rules?
    TARGET_DEFECTS: Impossible transit times; characters bypassing locks; objects teleporting; plot holes.
    SAMPLE_20: Zero causal breaks. The physical space operates with consistency. Characters' actions are legible and make sense in the context of the story.
    SAMPLE_10: 1 to 2 noticeable spatial lapses or minor plot contrivances. This breaks credibility but it does not break the overall narrative.
    SAMPLE_01: Core logic collapses. Characters perform impossible actions. The world is inconsistent, changing throughout.
  - 2
    QUESTION: Does the prose display repetitive syntactical defaults, purple prose, cliché saturation, or machine-like artifacts?
    TARGET_DEFECTS: Repeated phrasing, melodramatic filler, pointless jargon, over-reliance on bodily sensations to show emotion.
    SAMPLE_20: Prose is precise, varied, and stylistically mature. Sensory details are grounded and fresh. Characters express emotion through action and subtext. Jargon is minimal and purposeful.
    SAMPLE_10: Descriptive passages occasionally feel inflated. Normal emotions are over-emphasized. Pointless jargon is present which does not help the reader experience.
    SAMPLE_01: Severe prose artifacting. Dialogue and narrative are heavily clichéd. Text includes filler. Exact phrases are repeated. Useless tangents dominate the text.
  - 3
    QUESTION: Does the narrative halt dramatic action to lecture the reader, over-explain its themes, or force dialogue into unnatural exposition dumps?
    TARGET_DEFECTS: Narrators explicitly stating the moral of the story. Characters delivering monologues explaining their psychology. Dialogue used to deliver raw plot information ("As you know, Bob").
    SAMPLE_20: Themes emerge organically through character actions, dilemmas, and subtext. Dialogue is driven by immediate interpersonal friction and duelling character goals.
    SAMPLE_10: Periodic expository dialogue. Characters occasionally explain background information they would both naturally know. Theme is made overly explicit in 1 or 2 reflections.
    SAMPLE_01: Pervasive didacticism. The cast is charicatures. Action is paused to explain what just happened.
  - 4
    QUESTION: Are key plot points resolved through coincidences or ungrounded intuitions, rather than clear cause and effect?
    TARGET_DEFECTS: Overly simple plot complications. Established issues being resolved by external miracles. Unlikely events that strain credibility in the story.
    SAMPLE_20: Discoveries result from deliberate action. The plot feels earned, as it clearly follows a chain of events.
    SAMPLE_10: 1-2 events do not have clear causes set in motion earlier. Events in the plot generally form a path that makes sense.
    SAMPLE_01: The plot hinges on coincidence. Character actions lack consequence. Leaps in storytelling logic are not fair to the reader.

## Artistic merit (goodness)

The purpose of this check is to focus on the reader's experience. Good novels have enduring qualities which a reader can think about. Use a scale of 1 to 20 for each question. The total score should be between 5 and 100.

Score the manuscript using the following questions:
  - 1
    QUESTION: How distinctive and compelling is the perspective of the novel?
    TARGET: A fresh angle on nuanced topics. A clear stance.
    SAMPLE_20: Clear tone that is sophisticated and opinionated. Memorable voice.
    SAMPLE_10: Discernable tone. The novel has a perspective.
    SAMPLE_01: Flat, functional, or inconsistent. Generic and boring prose.
  - 2
    QUESTION: Are the characters interesting?
    TARGET: Characters are distinct and engaging. They have some interiority.
    SAMPLE_20: Characters have autonomous motives. Each has a distinct dialogue cadence.
    SAMPLE_10: Characters have identifiable desires and conflicts. They have distinct dialogue but it is either heavy handed or does not serve the overall experience.
    SAMPLE_01: Caricatures defined by single traits. Characters behave strictly to service plot needs. Their dialogue is indistinguishable.
  - 3
    QUESTION: Would the target audience profile of a smart teenager enjoy this novel?
    TARGET: The novel is intriguing and fun.
    SAMPLE_20: Clues are possible to find, but the leads are subtle. It is challenging to deduce the answer before the book explains it. It is fun to grapple with.
    SAMPLE_10: The mystery is coherent, but it is either too jumbled or too simple. It is sometimes fun.
    SAMPLE_01: The mystery is unfair, lying to the reader or using off-screen clues. It is unfun.
  - 4
    QUESTION: Could the target audience profile of a busy professional relax by reading this novel?
    TARGET: The novel is familiar to the genre but brings fresh ideas.
    SAMPLE_20: The novel uses genre tropes to say something new. The format is comfortable and suits the genre. There are twists or challenging themes that defy reader expectations, and they feel earned.
    SAMPLE_10: The novel follows basic genre tropes in a typical but satisfying journey.
    SAMPLE_01: The novel is too unfamiliar for a seasoned mystery fan to acclimatize. The mystery does not introduce twists.
  - 5
    QUESTION: Would the target audience profile of a parent find this novel breezy enough to read and satisfying to ponder?
    TARGET: The novel easily catches the reader's imagination.
    SAMPLE_20: Easy to pick up and put down. The plot is easy to follow, and it has depth.
    SAMPLE_10: The plot is easy to follow along with, but it lacks depth. Alternately, the plot is hard to follow along with, but it has good depth. 
    SAMPLE_01: The plot and prose are challenging to penetrate. The characters and plot lack depth.

## Mystery

The purpose of this check is to determine the structure of the mystery itself, and whether it is compelling. The total score for this category is between 3 and 60.

Score the manuscript using these questions:
  - 1
    QUESTION: Are all clues that solve the mystery visible and intelligible to the reader, planted before the climax? In other words, does the syuzhet present the fabula fairly?
    TASK: Trace every clue cited in the solution to the mystery back to its first origin.
    SAMPLE_20: Every deduction is anchored to evidence that has been planted. The conclusion is non-obvious due to misdirection and a tangled web of contradictions, but it is possible to have solved in advance.
    SAMPLE_10: Every deduction is anchored to evidence that has been planted. The conclusion is obvious because all evidence pointed to the same conclusion and there were no viable alternatives.
    SAMPLE_01: The result of the investigation was not possible for the reader to solve in advance. Crucial clues are jumbled, lying, or off-screen.
  - 2
    QUESTION: Is the culprit an established character introduced before the crime with plausible motive and opportunity?
    TASK: Record when the culprit first appeared and the details of the crime.
    SAMPLE_20: The culprit is part of the central cast. The crime is possible. Many characters have possible motives, but the culprit's motive is more potent.
    SAMPLE_10: The culprit appears before the crime. The crime is possible within the rules of the narrative. The culprit does not have an active role in the story otherwise. Their motive is boring.
    SAMPLE_01: The culprit does not appear before the crime. They are not a substantial part of the story. The crime does not make sense within the rules of the narrative.
  - 3
    QUESTION: Has the syuzhet introduced twists which defy the reader's expectations?
    TASK: Record the default expectations that a reader would have after reading portions of the text: stopping just after the crime, stopping just before the reveal, and reading all the way through.
    SAMPLE_20: Reader expectations change dynamically. Their expectations are defied at least once, but in retrospect it makes sense.
    SAMPLE_10: The reader expectations changed from the crime to the reveal, but not after the climax.
    SAMPLE_01: The reader had the same expectations at each stage of the book.

## Ranking parts

Rank this list of components to a story, based on what the manuscript does well. Score them individually, then list the 3 top scoring components and the 3 bottom scoring ones.

  - Plot and causality
  - Pacing and tension management
  - Characters: depth and agency
  - Prose and subtext
  - The mystery
  - How clues are presented and used
  - Setting
  - Thematic subtlety
  - Climax and payoff
