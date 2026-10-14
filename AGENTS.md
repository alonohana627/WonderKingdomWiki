# Working on the Wonder Kingdom Wiki

## Sources of truth

- **Game data** comes only from GameLib's `games/wonder_kingdom/content/*.json`.
  That folder is the source of truth for everything about how the game plays:
  items, skills, jobs, monsters, drops, EXP tables, quests, shops, maps,
  professions. Pages outside `docs/lore/` and `docs/index.md` are generated from
  it by `tools/generate.py` and are never edited by hand.
- The generator reads only `content/`. It never reads GameLib's `src/` and never
  writes anywhere in GameLib. If the wiki needs a number that is not in
  `content/`, the fix is to move it into `content/` in GameLib, not to read or
  copy it from the code.
- **Lore** is owned by this wiki, in `docs/lore/`, written by hand.
  The text can be edited and written creatively, but the main themes and the
  established facts stay the same (see `docs/lore/principles.md`). Open
  questions and real-world inspirations go in "Design notes" boxes, not in the
  in-world text. The lore navigation follows the links in
  `docs/lore/index.md`; town pages live in `docs/lore/towns/`, and a town that
  is also a game region gets a link to and from its world page.

## NPCs

`data/people/` is the registry of every NPC in the first release: one YAML
file per town, plus `kingdom.yml` with each town's NPC count and places, every
office (one holder each) and the only allowed cross-town relationships.
`tools/people.py` checks it for contradictions (one holder per office, one
spouse per person, unique ids and names, relationships written once with both
directions, game NPCs matching GameLib) and renders `docs/lore/people/`. Every
NPC gets its own page, and each town's list is a Name | Role table. NPCs marked
`menu: true` (shopkeepers, storage, taxis and other NPCs that only open a menu)
get a short page without personality or story. Never
edit those pages by hand; edit the YAML and rerun it. CI runs
`python tools/people.py --check`.

## What goes on a page

Only what a player would want to know: stats, levels, EXP per level, damage,
MP costs, cooldowns, drop rates, prices, rewards, where things are and how to
get them.

Leave out presentation and technical details: animation timings, wind-ups,
frame data, pixel distances and hitbox sizes, UI layout, art and sound ids,
palettes, music.

## Before committing

```bash
python tools/generate.py
mkdocs build --strict
```

## Story direction (for writers, not shown on the wiki)

These guide how lore and quests are written. They are not wiki pages.

**The player's place.** The player character is a native of Wonder Kingdom,
born and raised there. They are not an outsider and never have to earn
acceptance; the kingdom is their home. They start as one of the peaceful
generation that inherited the founders' work. They explore Veligor's towns,
wilds, caves, forests, mountains and ancient places, fight monsters stirred up
by the weakening seal, meet every community and learn its traditions. Many
stories are local and have nothing to do with the Balrog; the threat sits
inside a living world rather than defining all of it. As they progress they
uncover the deeper past (the founding, the ancient battle, the World Tree, the
Great Expedition, the guardians of Cavelor) and finally what the damaged seal
means. Undecided: the exact story progression, quest structure and the
player's final role against the Balrog.

**The central narrative.** The story is about unity, peace and each
generation's duty to protect what the last one built. The first generation
beat the Balrog only by overcoming its divisions, and founded the kingdom. The
current generation is already united; what it inherited is the duty to keep
the Balrog imprisoned. The expedition's accident has been wearing down the
founders' protections, and the monsters are the first sign. The conflict is
not about rebuilding a broken society but about protecting a good, peaceful
civilization from an ancient danger that is returning. The kingdom is worth
protecting because it is genuinely good.
