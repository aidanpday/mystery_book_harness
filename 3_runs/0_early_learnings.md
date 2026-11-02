# Early learnings

This is a collection of issues and problems from early attempts to generate a high-quality novel via AI. They did not use the iteration system defined in this project, so the format is an outlier.

## Prevent wild swings in behavior by creating a scale

I've generated chapters that were too somber, so I prompted again asking for something more lighthearted. The result was cartoonish. There is a spectrum here, and nudges invite overcorrection. Try to define the entire spectrum, with several reference points along it. Then state the target point.

For example, "Consider a scale of seriousness of tone from 1 to 100, where 1 is silly like Sheep Detectives and 100 is somber and gritty like True Detective. The midpoint is Sherlock Holmes at 50, and right now we're at 60. Our goal is to be at 40."

## Chapters should not make storytelling decisions

Explicitly ban chapter generation (writing the prose for a scene and list of story beats) from introducing new elements. AI commonly inserts or adds jargon, new characters, etc. Jargon is actually fine in these projects, if it's important or interesting, but it should be clearly defined in advance.

Drafting a chapter should faithfully recreate the storytelling decisions already made in prior steps.

## Instructions should not bias towards any particular story

It's important that `1_plan/` and `2_step/` do not reference any specific examples unless they are intended to be inspiration. A mention of a boat could influence an agent to using a boat in the story, which pre-emptively makes storytelling decisions. Be very careful about any examples used in documentation.

Documentation should be neutral about the approach, context, and details about the story. Info that restricts the setting is limited to `4_data/`.

## Instructions must distinguish final information

Some info is mainly useful to confirm that something is possible or likely, and should not be directly included in the final story.

Labels such as C-01, C-02, etc. are helpful for intermediate steps to sort characters. However, these are not terms that should appear in drafts. Drafting steps should be aware that many fields are intended as internal only. Otherwise, these become artifacts in the text.

## Standardize the output format for similar ideas

Steps that create multiple objects of a similar type (i.e. characters or entries in a timeline) should use the same template, with the same fields. This makes the AI consistent but it does not necessarily focus on the correct things. Crucially, important fields must include more detail than tangential info.

## Dialogue by default must be interactive

Style rules must guide dialogue towards fewer declarative statements via fostering questions and disagreements among characters.

## Contradictory sources

Edits in files over the course of a project can lead to later steps that naturally contradict earlier steps. It's important to establish a heirarchy for sources of truth, per subject. For example, chapter drafting should draw almost exclusively on scene info and narrative beats. However, the goals file will always be the source of direction for later steps.

## Chapters have independent contexts

Because chapters only really interact with the beginning and end of the next and previous chapters respectively, infomation is rarely shared between chapters. They tend to rely on static info from the project files. This breaks down when information changes mid-story, such as with a character arc or an object moving.

Thus, each scene should track the current state of the world: characters, locations, important objects, and what information has been shared with the reader.

## Simplify

Intermediate labels were repeatedly vague and jargon-filled. For example, a "waiter" was labelled as a "dining specialist and guest service member". Instructions should encourage simple, precise labels that catch the core purpose only. Descriptive fields can explain the extra stuff if needed.

## Common issues in early iterations

Issues that arose in over half of reviews of prior drafts:
  - Climax stakes and the resolution. Avoid bureaucratic solutions to personal issues
  - Character mannerisms and sensory crutches. Some chapters repeated exact phrasings for character mannerisms. The text used boilerplate AI expressions of emotion via repeated sensory experiences.
  - The crime was not an interesting puzzle. AI focused on microscopic or invisible issues that made it uninteractive and too simple.
  - Physical logistics were overly emphasized. AI was highly specific about irrelevant details of weights, millimeters, and tools.

## Avoid repeat explanations

One draft had the investigators explain the crime in their deductions, then the culprit gave a monologue after being caught where they once again explained the crime. This should happen exactly once, and culprit monologues should be avoided too.
