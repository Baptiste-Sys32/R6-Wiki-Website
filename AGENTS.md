# AGENTS.md - R6 wiki (projet-perso-r6site-deploy)

> Applies ONLY when cwd is inside `projet-perso-r6site-deploy/`.
> Global `~/AGENTS.md` still applies. On conflict, global security/safety wins, otherwise this file wins.

## 0. Workflow guards

- `~/Downloads/` stays until ship. Never delete previews, zips, or `Guide.md` until the wiki ships.
- No remake to `main` unasked. Never push a remake/rewrite to `main` without explicit approval.
- One commit + push per feedback round. Batch each approved round into a single commit + push.

## 1. Data pipeline (scrapers only)

- All data via `scripts/sync-r6-*.js` to `content/*.json` + manifest, then images, then `build-data.js` validation, then views. Never hand-edit content JSON.
- Truth order: scrape `en-us` (obligatory); Ubisoft wins loadouts; `scripts/r6-stat-truth.js` wins stats; videos Ubi first, Fandom backup.
- Port DBD markup and class names verbatim; only strings, fields, and counts change.
- `web/engine/` stays byte-identical to shared DBD `engine.css`; R6 overrides are R6-scoped only, never edits to shared classes.
- TTK is precomputed into static JSON; zero client-side math. Liquipedia free no-key API only.

## 2. Videos (never hosted locally)

- YouTube via nocookie click-to-load embed plus `<video preload="none">` hotlink (`staticctf.ubisoft.com`); posters local only.

## 3. Attachments (per gun)

- Full named + schematic table per gun on sheets and op pages. Union tables deleted. `compat[]` is dead.
- Magnified B / 2.0x dropped (no live entry upstream). Drop Notes and summary sections. Used-by is operator-list rows with no star.

## 4. Art and maps

- Schematics over photos: sights/scopes use white HUD-icon schematics. Ubisoft gun PNGs for lists/tables/cards only; sheets keep Fandom renders; fallback never blank.
- Maps: bomb layouts only. Overviews dropped where per-floor exists; spawns kept; site pairs as plain list v1. Bank basement to 2F swap deferred to a later map pass.
- Favicons: white-on-dark badges matching R6/DBD.

## 5. UI contracts

- Infobox Season is clickable.
- First two sections go in rail via `ArticleShell.leadExtra`.
- Settings pages: appearance + features only.
- Gadget card images are non-clickable.
- Gun image scrolls to `attach-gun-<normkey>`; gun name opens the weapon page.
- Unique Ability is the 4th card.
- Sentry/Striker text-only gadget on operator pages; B and W logos on Gadgets list only.
- Lists: strip `cx-lead` subtitles and `{n} results` counts on all six lists; uniform search portal-row to chips.
- Seasons list shows `New:` / `Rework:` only, never TS/WW dates.

## 6. Backburner

- `w.atwiki.jp/siegespoiler` stays untouched.
