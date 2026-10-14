# Brief for writing a town's NPCs

You are writing every NPC of one town in Wonder Kingdom's first release, as one
YAML file: `C:\Users\user\WonderKingdomWiki\data\people\<town>.yml`.

## Read first

1. `C:\Users\user\WonderKingdomWiki\data\people\kingdom.yml`: the towns, how
   many NPCs yours needs, the places allowed in your town, the offices (who
   rules what), and the only cross-town relationships allowed.
2. Your town's lore page in `C:\Users\user\WonderKingdomWiki\docs\lore\towns\`,
   plus `docs\lore\index.md`, `docs\lore\history.md`, `docs\lore\balrog.md` and
   `docs\lore\principles.md`. Your NPCs must agree with all of them.
3. `C:\Users\user\WonderKingdomWiki\tools\people.py`: the exact rules the file
   is checked against.

## File format

```yaml
npcs:
  - id: dorrek_kragvar          # lower_snake_case, unique in the whole kingdom
    name: Dorrek                # display name; unique in the whole kingdom
    title: Chieftain of the Kragvar
    role: ruler                 # ruler council official guard merchant craftsman service worker scholar healer performer adventurer resident child animal
    office: midbarium.chief_kragvar   # only for the offices listed in kingdom.yml
    place: Great Hall           # one of your town's places in kingdom.yml
    age: elder                  # child young adult elder
    family: Kragvar             # Midbarium only: Kragvar, Tolmach, Uskari, Brenna or none
    kind: Child of the Tree     # optional; only when the NPC is not an ordinary person
    sells: Ropes, picks and climbing gear   # optional; merchants and shopkeepers
    game: tobin                 # optional; only for NPCs already in the game (see below)
    personality: One or two sentences.
    story: One to three sentences: who they are, their history, what they want.
relationships:
  # written ONCE per pair: [a, b, what a is to b, what b is to a]
  - [dorrek_kragvar, brakka_kragvar, father, daughter]
```

## Rules

- Exactly the number of NPCs kingdom.yml gives your town. Every office in your
  town must appear with the exact id, name, title and office from kingdom.yml.
- A mix that makes a living town: rulers and officials, guards, merchants and
  shopkeepers (with `sells`), craftspeople, workers, healers, scholars,
  performers, residents, elders and children, and a few adventurers.
- Personalities must differ from one another. Keep text short and concrete.
  Give some NPCs small hooks a quest could use later (a worry, a secret, a
  wish), and tie a few of them to the Age of Disturbance (monsters on the roads,
  the weakening seal) without solving any open mystery.
- Relationships: every NPC should have at least one, inside your town. Write
  each pair once with both directions. Family, friends, rivals, mentors,
  employers, sweethearts. Each person has at most one spouse, one father and
  one mother. Cross-town ties are ONLY the ones already in kingdom.yml; you may
  mention other towns in a story in general terms, but never name or invent a
  specific person from another town, and never mention another town's ruler.
- Nobody may rule, lead, or hold a title that belongs to an office in
  kingdom.yml except its holder. Don't invent extra kings, mayors, chieftains,
  Old Ones and so on. New posts below the leader (a steward, a captain of the
  watch, a guild head) are fine, but name each such post only once.
- Don't decide anything the lore pages list as still open, except where this
  brief or your town notes say so. The Children of the Tree's nature,
  appearance, abilities and origins are undecided: Children NPCs get a
  personality and a story, never a description of their body or powers.
- Names must suit the town's naming style (your town notes) and must not reuse
  any name of these existing game NPCs unless you are writing that very NPC:
  Aldous, Biscuit, Bram, Brann, Ewan, Fen, Gareth, Garrick, Gideon, Hale, Hilda,
  Hollis, Lia, Marta, Maud, Mirabel, Mirel, Nell, Orin, Orsa, Pell, Perrin, Pim,
  Quill, Rhys, Rosa, Selene, Tam, Tilda, Tobe, Tobin, Vessa, Wren. Also avoid
  Juna, Aveline, Hask, Dorrek, Sennu, Tavi, Odda, Calyra, Rook, Marrun, Quenna
  and Iska except for those exact NPCs.
- Plain, warm English. No emojis.

## Checking your work

Run `python C:\Users\user\WonderKingdomWiki\tools\people.py` from any
directory. It checks every town, so ignore problems about other towns'
missing files; fix every problem that names your town or your NPCs. Do not
run it with any other arguments, and do not edit any file other than your own
town's YAML file.

## Limits

Only write your own `data/people/<town>.yml`. Do not edit anything in GameLib
(you may read `C:\Users\user\GameLib\games\wonder_kingdom\content\npcs\*.json`).
No git commands, no package installs, and do not call any mcp__hearthbot__
tools. When done, reply with the NPC count and anything you were unsure about.
