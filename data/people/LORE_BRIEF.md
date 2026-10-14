# Brief for writing NPC lore

You are writing the long lore for a batch of Wonder Kingdom NPCs. Each NPC gets
one Markdown file of **at least 450 words** (the checker's floor is 400; aim
higher so edits never drop below it):

    C:\Users\user\WonderKingdomWiki\data\people\lore\<town>\<npc id>.md

## Read first, every time

1. Your batch's NPC entries in `data\people\<town>.yml`: name, title, role,
   place, age, family, kind, personality, story. The lore must agree with every
   one of these fields. Don't edit the YAML.
2. Every relationship involving your NPCs: the `relationships:` list in
   `data\people\<town>.yml` and the `links:` in `data\people\kingdom.yml`.
3. The canon so far:
   - `data\people\facts\kingdom.md`: facts about the leaders and the kingdom.
   - `data\people\facts\<town>.md`: facts already set for your town.
   - The lore file of **every NPC already written who is related to one of
     yours** (in `data\people\lore\<town>\`), and of your town's leaders.
   You may not contradict any of it. If something written earlier is about one
   of your NPCs (for example, "Hob taught Ned to whittle"), your NPC's lore must
   agree with it.
4. The town's lore page `docs\lore\towns\<town>.md`, plus `docs\lore\history.md`,
   `docs\lore\balrog.md`, `docs\lore\principles.md` and `docs\lore\timeline.md`.
5. For NPCs with `game:`, their file in
   `C:\Users\user\GameLib\games\wonder_kingdom\content\npcs\` and any quests in
   `..\quests\` naming them. The lore must agree with what they say in the game.

## What to write

Plain prose about the person, in the wiki's warm, clear voice: where they come
from, what shaped them, what they do each day, the people in their life (link
nothing; just use names), what they want, what they fear, and one or two hooks
a quest could use later. You may use `###` headings inside the file, or none.
No `#` or `##` headings. No emojis.

## Rules that prevent contradictions

- **Family is fixed by the registry.** Never give anyone a living spouse,
  parent, child or sibling who isn't in the relationships list. You may invent
  people who are dead, or who live far away and play no part, but write each
  such invention into the facts file (below) so later writers see it.
- **Names are unique.** Never give a dead, absent or invented person the first
  name of any NPC in the registry (any town), or of anyone already invented in
  the facts files.
- **Offices are fixed.** Only the holders in `kingdom.yml` rule or lead their
  towns. Posts below them that the YAML already names are fine; don't invent
  new ones that sound like leadership of the town.
- **Other towns:** mention places and peoples freely, but name no person from
  another town except through the `links:` in kingdom.yml.
- **Numbers and dates:** before stating an age, a year count ("for twenty
  years"), or a date relative to an event, check the facts files and related
  lore; then record it.
- **Open questions stay open** (lore principle 20): the Balrog's nature, how
  to fix the seal, the Children of the Tree's nature and appearance, how the
  monarch is chosen, which coast each harbour is on, and the rest listed in the
  pages' design notes. Characters may wonder, guess or fear; they may not know.
- Agree with each NPC's short `story` and `personality`; expand them, don't
  replace them.

## The facts file

After writing each NPC, append the new hard facts you set (ages, years, dead or
absent relatives you invented, past events, who did what to whom, places you
named) to `data\people\facts\<town>.md`, as short bullets under a heading with
the NPC's name and id. Leaders' facts go to `data\people\facts\kingdom.md`.
Keep bullets factual and short; they are for other writers, not readers.
Re-read the file just before appending, and append; never rewrite others'
entries.

## Check

Run `python C:\Users\user\WonderKingdomWiki\tools\people.py` (no arguments). It
reports "N NPCs still need lore" until everything is done: ignore that line.
Fix every other problem that names one of your NPCs (word counts, headings).

## Limits

Write only your batch's lore files and the facts file(s) named above. Don't
edit any YAML, page, tool or GameLib file. No git commands, no installs, and
don't call any mcp__hearthbot__ tools. When done, reply with your NPC ids, each
one's word count, and every fact you weren't sure was consistent.
