# Brief for reviewing a town's NPC lore for contradictions

Every NPC lore file in your town is written. Find every contradiction and fix
it.

## Read everything, in this order

1. `data\people\kingdom.yml` and your town's `data\people\<town>.yml`
   (names, titles, ages, places, family fields, relationships). The YAML is
   the ground truth.
2. `data\people\facts\kingdom.md` and `data\people\facts\<town>.md`.
3. Every file in `data\people\lore\<town>\`, all of them, start to finish.
4. Your town's lore page `docs\lore\towns\<town>.md`, plus `docs\lore\history.md`,
   `docs\lore\balrog.md`, `docs\lore\principles.md` and `docs\lore\timeline.md`.
5. For NPCs with `game:`, their file in
   `C:\Users\user\GameLib\games\wonder_kingdom\content\npcs\` and the quests in
   `..\quests\` that name them.

## What counts as a contradiction

- Two files disagree on a fact: an age, a year count, a date, who married whom,
  who taught whom, who knows a secret, who did something, where someone lives,
  how many of something, the order of events.
- Arithmetic that doesn't work. Check every pair of ages and year counts: a
  parent must be old enough, someone can't have done a job for 30 years at 25,
  "since X happened N years ago" must match the facts.
- A file gives someone a living spouse, parent, child or sibling who isn't in
  the YAML relationships, or contradicts the YAML (title, age group, family,
  place, relationship wording).
- Two people credited with the same unique thing (the same post, the same
  first-ever act, the same predecessor with different names).
- Pronouns that don't match: NPCs whose YAML and earlier lore set no gender
  must have none anywhere.
- A dead or invented person with the same first name as a registry NPC, or two
  different invented people with the same name.
- Lore that settles an open question (the Balrog's nature, how to fix the
  seal, the Children of the Tree's nature or appearance, how the monarch is
  chosen, which coast a harbour is on) or names a person from another town
  outside kingdom.yml's links.
- Disagreement with the game files or the lore pages.

## How to fix

Make the smallest edit that makes everything agree, in the lore file that is
wrong. Prefer to change the less-connected NPC's file, and never change the
leaders' facts in kingdom.md unless they are the error. Keep every file at 400
words or more. Update `data\people\facts\<town>.md` to match. You may edit only
your town's lore files and your town's facts file. If a contradiction involves
another town, the leaders, or the YAML, don't fix it: report it.

Run `python C:\Users\user\WonderKingdomWiki\tools\people.py` when done. Fix any
problem it reports for your town; ignore the "N NPCs still need lore" line.

## Report

Reply with a list: each contradiction you found, the files involved, and the
fix you made (or why you left it for me). Then say how many files you read.
No git, no installs, no mcp__hearthbot__ tools.
