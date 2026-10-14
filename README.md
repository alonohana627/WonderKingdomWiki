# Wonder Kingdom Wiki

This is the wiki for **Wonder Kingdom**, a MapleStory-like open-world
platformer RPG built with [GameLib](https://github.com/alonohana627/GameLib).
It is a [MkDocs Material](https://squidfunk.github.io/mkdocs-material/) site.

## Sources of truth

- **Lore** lives here, in `docs/lore/`, written by hand.
- **Game data** lives in GameLib (`games/wonder_kingdom/content/`). Every other
  section of `docs/` (items, skills, jobs, monsters, bosses, NPCs, quests,
  shops, world, maps, professions, runs, game systems) is generated from it by
  `tools/generate.py`. Don't edit those pages by hand: change the game data in
  GameLib and regenerate. The generator only reads GameLib.

## Working on the wiki

```bash
pip install -r requirements.txt
python tools/generate.py          # expects GameLib next to this repo; or pass --game PATH
mkdocs serve                      # preview at http://127.0.0.1:8000
mkdocs build --strict             # what to run before committing
```

The generator also rewrites the `nav:` block at the end of `mkdocs.yml`, so add
new lore pages under `docs/lore/` and rerun it to put them in the navigation.

## Publishing

Every push to `main` builds the site with `mkdocs build --strict` and publishes
it to GitHub Pages from the `gh-pages` branch (`.github/workflows/pages.yml`).

Every pull request gets its own preview site at
`https://alonohana627.github.io/WonderKingdomWiki/pr-preview/pr-<number>/`,
linked in a comment on the pull request. The preview updates with each push
and is removed when the pull request closes.

The workflow builds the committed pages; rerun `tools/generate.py` locally and
commit when the game data changes.
