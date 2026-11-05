---
cursor_session: ba864f6c-5563-4cab-ab6d-6464344ca088
source: cursor-composer
cursor_hint: ?
user_entries: 3
---

# transcript — we-want-feeds-to-exclude-some-speakers-because

### you

we want feeds to exclude some 'speakers' (because they're not speakers, they're mentions of that person, which I'm not interested in). Exclude (from the detected level onwards, not just at the end on the ui)... Donald Trump, Elon Musk, Harry Potter, James Bond, Taylor Swift, Tony Blair, Albert Hall, David Cameron, Liz Truss, Joe Biden, Ted Lasso, King Charles, Keir Starmer, Gordon Brown, actually I've set them to the feeds.*.md as exclude_speakers, sample those.

### assistant

Got it. I’m going to (1) inspect how `feeds*.md` are parsed into feed config, (2) trace where “speakers” are detected/expanded during the build, then (3) wire `exclude_speakers` into that pipeline so those names never make it into the generated speaker lists/pages/index (not just hidden in the UI).

### assistant

I found the config key in all three `feeds*.md`, but the parser currently treats it as a plain string, so it never affects the build. Next I’ll add `exclude_speakers` as a proper list field in `scripts/feeds_md.py`, then thread it through `scripts/build_site.py` (and likely `scripts/update_feeds.py`) so excluded names are removed before the speaker index/search/graph are built.

### assistant

I’ve located where speakers are extracted (`scripts/update_feeds.py`) and where speaker pages/search/graph are built (`scripts/build_site.py`). Next I’ll (a) make `exclude_speakers` parse as a list, then (b) filter those names during feed updates *and* during site build so they’re fully removed from the generated data.

### assistant

Now I’ll quickly sanity-check that `exclude_speakers` parses as a list, that `scripts/update_feeds.py --sanitize-cache` would actually remove those names, and that a site build no longer emits those speakers into `dist/index.json` / speaker pages / graph.

### assistant

Build succeeded, so the build-side filtering path is working. Next I’ll verify `exclude_speakers` is now parsed as a real list (site-level), and confirm the generated `dist/index.json` no longer contains any of your excluded names.

### assistant

### Done: `exclude_speakers` now removes those names from the *data*, not just the UI

- **`exclude_speakers` is now parsed as a list** from `feeds*.md` (site-level and per-feed).
- The excluded names are **filtered out of episode `speakers` during updates** (`scripts/update_feeds.py`) and also **during site build** (`scripts/build_site.py`) as a safety net.
- Result: they won’t appear in **speaker detection output**, **speaker index/pages**, **search index speaker lists**, or the **graph** (mentions in titles/descriptions remain untouched).

### Files changed
- `scripts/feeds_md.py`
- `scripts/update_feeds.py`
- `scripts/build_site.py`

### you

fairly miniamlly, can you, when the page is scrolled, make the header disappear and instead sticky the player to the top of the viewport.

### assistant

I’ll implement this with a tiny scroll-state toggle: when you’ve scrolled past the header, we’ll slide the header out and set the player’s sticky offset to 0 so it pins to the very top.

### assistant

I’m going to make this a pure front-end change: add a scroll-triggered class on the root element, slide the header out when scrolled, and set `--header-offset` to ~0 so the sticky player snaps to the top.

### assistant

### Implemented: hide header on scroll, player sticks to top

- **Header**: now slides away once you scroll a little (`.ap-scrolled .site-header`).
- **Player**: becomes sticky at the very top by driving `--header-offset` to ~0 when scrolled.

Changed files:
- `site/assets/app/ui/header_offset.js`
- `site/assets/style.css`

### you

the og:image isn't getting the right path in speaker pages...


    <meta property="og:image" content="/podcasts/podcasts/assets/images/speakers/dave-gorman.jpg" />

### assistant

I’ll fix the `og:image` builder so if a path already starts with `/` (or already includes the base path), we don’t prefix the base path again. That should remove the duplicated `/podcasts/podcasts/` on speaker pages.

### assistant

### Fixed `og:image` double base-path on speaker pages

Updated `_meta_extra_html()` in `scripts/build_site.py` so **paths that already start with `/` don’t get `base_path` prefixed again**.

Your example will now come out as:

- **Before**: `/podcasts/podcasts/assets/images/speakers/dave-gorman.jpg`
- **After**: `/podcasts/assets/images/speakers/dave-gorman.jpg`
