# Mirandel interactive maps

| File | What it is |
|---|---|
| `index.html` | Home hub: where the party is now, welcome, buttons to the map, markets and NPCs, last session recap, active quests, quick tips. |
| `world.html` | World map. Click rings for lore; click the outlined area to open the regional map. |
| `regional.html` | Amox / Ferry Falls / Everwoods regional map. |
| `amox.html` | City of Amox map. |
| `markets.html` | Markets: shops by city and a price finder. |
| `pantheon.html` | The Pantheon: the sixteen gods, their domains, and their alignments, in one alphabetical table. |
| `npcs.html` | NPC database. |
| `recaps.html` | Session recaps, newest first. |
| `about-dm.html` | About the DM. Linked only from the hub footer, not the top bar. |
| `assets/bg-forest.jpg` | Blurred forest backdrop behind every page: the hub, Markets, NPC, recap, About, and behind the maps. |

## Editing
Each map page has a settings block at the top of its `<script>`: `MAP_WIDTH_MILES`, `DAY_HOURS`, `MODES` (travel speeds), `LINKS` (buttons on location cards), and `WORLD_URL` / `REGION_URL` (links between pages). Location text lives in the `PLACES` list in the same file.

The home hub (`index.html`) has no script: edit the sections marked `<!-- EDIT ... -->` right in the HTML, after each session.

Markets (`markets.html`) has its editable lists at the top of its `<script>`: items (prices in copper, 100 cp = 1 gp), then cities and their shops. To add a city, copy the Amox block (or the smaller Towns block for a generic city) and fill in its shops; each city has its own price modifier. DM price changes (shop markups, events, custom items and specials, inflation) have no panel in the page: use the Save / load box at the top, Export, edit the JSON, Import — the format is documented in a comment above `CITIES` in the file.

NPCs (`npcs.html`) and recaps (`recaps.html`) each have one editable list at the top of their `<script>`: `NPCS` and `SESSIONS`. Pantheon (`pantheon.html`) has one editable list, `GODS` (name, domain, alignment); the page sorts alphabetically, and faction info does not go on the site. Add new sessions anywhere in `SESSIONS`; the page sorts newest first by date, so write dates like "Oct 22, 2026". A session without a date still works and shows at the bottom.

Every page has the same top bar (Home, World Map, Markets, NPCs, Pantheon, Recaps). The bar is copied into each file, so adding a page means adding its link to every file.

## Publishing
The live site is GitHub Pages, deploying from branch `main`. See `CONTRIBUTING.md`: work on a branch, open a pull request, and merge only after reviewing a rendered preview.
