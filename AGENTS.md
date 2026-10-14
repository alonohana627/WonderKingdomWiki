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
