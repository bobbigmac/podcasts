---
cursor_session: 92b3d551-8c4e-4072-bb69-608de1e81862
source: cursor
cursor_project: home-bobbigmac-projects-podcasts
user_entries: 4
source_file: /home/bobbigmac/.cursor/projects/home-bobbigmac-projects-podcasts/agent-transcripts/92b3d551-8c4e-4072-bb69-608de1e81862/92b3d551-8c4e-4072-bb69-608de1e81862.jsonl
---

# transcript — integrate-feed-check-priority-mjs-so-the-github

### you

Integrate feed-check-priority.mjs so the github actions updates check fcuses on target feeds that are in the priority list first, instead of just all feeds every time. Abandoned/dead/inactive feeds should still be checked occasionally, so maybe we want a kinda cooldown, like check even seemingly inactive feeds at least once a week. Try not to fuxk with the system, our cache storage is intentionally weird, just focus on priorities and reducing how many queries we make with every run, while still hitting feeds where it's clear we expect content.

### assistant

I'll explore the priority script and how GitHub Actions currently checks feeds so we can wire priorities in without touching the cache layout.

> `Read` {"path": "/home/bobbigmac/projects/podcasts/scripts/feed-check-priority.mjs"}

> `Glob` {"glob_pattern": "**/.github/**/*"}

> `Grep` {"pattern": "feed-check|update_feeds|priority", "glob": "**/*"}

> `Read` {"path": "/home/bobbigmac/projects/podcasts/.github/workflows/update-and-deploy.yml"}

> `Read` {"path": "/home/bobbigmac/projects/podcasts/scripts/update_feeds.py", "limit": 200}

> `Grep` {"pattern": "lastChecked|last_checked|feed.*cache|update_feed", "glob": "**/*"}

> `Grep` {"path": "/home/bobbigmac/projects/podcasts/scripts", "pattern": "cooldown|last_fetch|last_checked|should_fetch|force"}

> `Grep` {"path": "/home/bobbigmac/projects/podcasts", "pattern": "cooldown|last_fetch|last_checked|should_fetch", "glob": "*.py"}

> `Read` {"offset": 380, "limit": 50, "path": "/home/bobbigmac/projects/podcasts/scripts/update_feeds.py"}

> `Read` {"offset": 1280, "limit": 200, "path": "/home/bobbigmac/projects/podcasts/scripts/update_feeds.py"}

> `Grep` {"path": "/home/bobbigmac/projects/podcasts", "pattern": "COOLDOWN|cooldown_hours|min_check"}

> `Read` {"limit": 100, "offset": 1180, "path": "/home/bobbigmac/projects/podcasts/scripts/update_feeds.py"}

> `Grep` {"path": "/home/bobbigmac/projects/podcasts", "pattern": "min_hours_between_checks|priority|weight"}

> `Read` {"path": "/home/bobbigmac/projects/podcasts/feeds.fubar.md"}

> `Grep` {"path": "/home/bobbigmac/projects/podcasts/scripts/update_feeds.py", "pattern": "_load_existing_feed_json|published_at|publishedAt"}

> `Read` {"path": "/home/bobbigmac/projects/podcasts/package.json"}

> `Glob` {"glob_pattern": "cache/feeds/*.md"}

> `Read` {"limit": 80, "path": "/home/bobbigmac/projects/podcasts/feeds.md"}

> `Read` {"limit": 80, "offset": 360, "path": "/home/bobbigmac/projects/podcasts/scripts/update_feeds.py"}

> `Grep` {"path": "/home/bobbigmac/projects/podcasts", "pattern": "check_limit|prioritize|feed-check"}

> `Grep` {"path": "/home/bobbigmac/projects/podcasts/feeds.md", "pattern": "^## ", "output_mode": "count"}

> `Grep` {"path": "/home/bobbigmac/projects/podcasts/feeds.actualplays.md", "pattern": "^## ", "output_mode": "count"}

> `Grep` {"path": "/home/bobbigmac/projects/podcasts/feeds.other.md", "pattern": "^## ", "output_mode": "count"}

> `Read` {"limit": 30, "path": "/home/bobbigmac/projects/podcasts/AGENTS.md"}

> `Grep` {"path": "/home/bobbigmac/projects/podcasts/scripts", "pattern": "\"slug\"", "glob": "feeds_md.py"}

> `Read` {"limit": 80, "path": "/home/bobbigmac/projects/podcasts/scripts/feeds_md.py"}

### assistant

Implementing priority selection in `update_feeds.py` and wiring it into the GitHub Actions workflow.

> `Read` {"limit": 45, "offset": 68, "path": "/home/bobbigmac/projects/podcasts/scripts/update_feeds.py"}

> `StrReplace` {"path": "/home/bobbigmac/projects/podcasts/scripts/update_feeds.py", "old_string": "import argparse\nimport html\nimport json\nimport os\nimport re\nimport sys\nimport time", "new_string": "import ar…

> `StrReplace` {"path": "/home/bobbigmac/projects/podcasts/scripts/update_feeds.py", "old_string": "    p.add_argument(\"--quiet\", action=\"store_true\", help=\"Less logging (still prints errors).\")\n    return p.…

> `StrReplace` {"path": "/home/bobbigmac/projects/podcasts/scripts/update_feeds.py", "old_string": "    except Exception:\n        return None\n\n\ndef _norm_name_list(value) -> list[str]:", "new_string": "    excep…

> `StrReplace` {"new_string": "    jobs: list[_FeedJob] = []\n    per_feed_state_by_slug: dict[str, dict] = {}\n\n    priority_selected: set[str] | None = None\n    priority_meta: dict[str, dict[str, Any]] = {}\n   …

> `StrReplace` {"new_string": "        last_checked = per_feed_state.get(\"last_checked_at\")\n\n        # If state is missing but cache exists, infer last-checked so manual runs don't refetch.\n        if not per_f…

> `StrReplace` {"new_string": "      - name: Set up Node.js\n        uses: actions/setup-node@v4\n        with:\n          node-version: \"20\"\n\n      - name: Restore cached state (cache branch)", "old_string": " …

> `StrReplace` {"new_string": "      - name: Update feed cache\n        run: |\n          set -euo pipefail\n          FEEDS=\"${AP_FEEDS:-feeds.md}\"\n          CACHE_DIR=\"${AP_CACHE:-cache}\"\n          CHECK_LIM…

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && node --version && echo '[{\"id\":\"test\",\"episodes\":[{\"publishedAt\":\"2025-06-01T12:00:00Z\",\"title\":\"Ep1\"},{\"publishedAt\":\"2025-06-08T…

> `Glob` {"glob_pattern": "cache*/state.json"}

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && python3 -m scripts.update_feeds --feeds feeds.fubar.md --cache /tmp/podcast-test-cache --prioritize --check-limit 3 2>&1 | head -30", "description"…

### assistant

Stale-recheck was bypassing the check limit for feeds with no prior check — tightening that condition.

> `StrReplace` {"new_string": "        last_ts = _feed_last_checked_unix(slug=slug, per_feed_state=per_feed_state, feeds_md_dir=feeds_md_dir)\n        if last_ts is not None and last_ts < stale_cutoff:", "old_string…

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && python3 -m scripts.update_feeds --feeds feeds.fubar.md --cache /tmp/podcast-test-cache --prioritize --check-limit 3 2>&1 | head -15", "description"…

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && python3 -m scripts.update_feeds --feeds feeds.fubar.md --cache /tmp/podcast-test-cache --prioritize --check-limit 3 2>&1", "description": "Full pri…

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && python3 -c \"\nimport json, subprocess\nfrom pathlib import Path\nfrom scripts.shared import read_feeds_config, REPO_ROOT\nfrom scripts.update_feed…

> `StrReplace` {"new_string": "        if priority_selected is not None and slug not in priority_selected:\n            _log(f\"[skip] {slug} (not selected this run)\", quiet=args.quiet)", "old_string": "        if …

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && python3 <<'PY'\nimport json, subprocess, time\nfrom datetime import datetime, timezone, timedelta\nfrom pathlib import Path\n\ncache = Path('/tmp/p…

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && python3 <<'PY'\nimport json, time\nfrom datetime import datetime, timezone, timedelta\nfrom pathlib import Path\nfrom scripts.update_feeds import _…

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && python3 <<'PY'\nimport json, subprocess\nfrom datetime import datetime, timezone, timedelta\nfrom scripts.shared import utc_now_iso\n\nrecent = (da…

> `ReadLints` {"paths": ["/home/bobbigmac/projects/podcasts/scripts/update_feeds.py"]}

### assistant

Capping stale inactive rechecks so they fill remaining budget instead of bypassing the limit.

> `StrReplace` {"new_string": "    stale_cutoff = int(time.time()) - max(1, int(inactive_recheck_days)) * 86400\n    stale_candidates: list[tuple[int, str]] = []\n    for feed_cfg in feeds:\n        slug = str(feed_…

### assistant

Integrated `feed-check-priority.mjs` into the update pipeline.

**`scripts/update_feeds.py`**
- New flags: `--prioritize`, `--check-limit` (default 20), `--inactive-recheck-days` (default 7)
- Builds priority input from existing cache markdown + `state.json` (no cache format changes)
- Calls the Node script to pick due feeds first, up to the limit
- Fills any remaining budget with oldest stale feeds (7+ days since last check), so inactive ones still rotate through without blowing the cap
- When `--prioritize` is on, the old flat cooldown skip is bypassed — interval logic lives in the priority script

**`.github/workflows/update-and-deploy.yml`**
- Adds Node 20 setup
- Runs updates with `--prioritize --check-limit "${AP_CHECK_LIMIT:-20}"`

Each 3-hour CI run now checks ~20 feeds instead of every feed past the 2-hour cooldown. Active/overdue feeds win slots; early ones defer; inactive ones get a weekly stale pass. Override per repo with `AP_CHECK_LIMIT`. Local runs without `--prioritize` behave as before; `--force` still checks everything.

### you

only 20 feeds is very tight, let it use a more generous budget (don't hardcode to a limit of checkables, use banding based on what's in the groups, no basic threshold assumptions).

### assistant

I'll inspect how priority tiers and feed groups are defined so we can replace the fixed 20-feed cap with a tier-based budget.

> `Read` {"path": "/home/bobbigmac/projects/podcasts/scripts/update_feeds.py", "offset": 70, "limit": 50}

> `Read` {"path": "/home/bobbigmac/projects/podcasts/scripts/update_feeds.py", "offset": 430, "limit": 120}

> `Read` {"path": "/home/bobbigmac/projects/podcasts/.github/workflows/update-and-deploy.yml", "offset": 76, "limit": 15}

> `Read` {"path": "/home/bobbigmac/projects/podcasts/scripts/feed-check-priority.mjs", "offset": 430, "limit": 270}

> `Grep` {"path": "/home/bobbigmac/projects/podcasts/scripts/update_feeds.py", "pattern": "check_limit|_select_feeds_for_check"}

### assistant

Replacing the fixed cap with tier-based selection and a stale budget derived from group size and run interval.

> `StrReplace` {"path": "/home/bobbigmac/projects/podcasts/scripts/update_feeds.py", "old_string": "    p.add_argument(\n        \"--prioritize\",\n        action=\"store_true\",\n        help=\"Use feed-check-prior…

> `StrReplace` {"path": "/home/bobbigmac/projects/podcasts/scripts/update_feeds.py", "old_string": "def _select_feeds_for_check(\n    *,\n    feeds: list[dict],\n    feeds_md_dir: Path,\n    state: dict,\n    min_ho…

> `StrReplace` {"path": "/home/bobbigmac/projects/podcasts/scripts/update_feeds.py", "old_string": "            priority_selected, priority_meta = _select_feeds_for_check(\n                feeds=feeds,\n            …

> `StrReplace` {"path": "/home/bobbigmac/projects/podcasts/.github/workflows/update-and-deploy.yml", "old_string": "          CHECK_LIMIT=\"${AP_CHECK_LIMIT:-20}\"\n          python -m scripts.update_feeds --feeds \…

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && python3 -m scripts.update_feeds --feeds feeds.fubar.md --cache /tmp/podcast-test-cache --prioritize 2>&1 | head -15", "description": "Test tier-bas…

> `ReadLints` {"paths": ["/home/bobbigmac/projects/podcasts/scripts/update_feeds.py"]}

### assistant

Removed the hardcoded 20-feed cap. Selection is now tier-driven:

- **Due now**: every feed the priority script marks `shouldCheckNow` — all critical/high/normal/low bands that are actually due, no numeric ceiling
- **Stale band**: inactive/deferred feeds rotate on a budget derived from how many are stale and how often CI runs (`ceil(stale_count / runs_in_recheck_window)`), so a 7-day recheck window with 3-hour runs spreads them across ~56 runs

`--check-limit` and `AP_CHECK_LIMIT` are gone. `--run-interval-hours` (default 3, matching the cron) controls stale spread math.

### you

run that locally against the existing (stale) cache, then check some of the feeds it says are overdue/etc

> `Glob` {"glob_pattern": "**/cache*/state.json"}

> `Glob` {"glob_pattern": "**/cache*/feeds/*.md"}

> `Shell` {"command": "ls -la /home/bobbigmac/projects/podcasts/ | head -30", "description": "List project root for cache dirs"}

> `Shell` {"command": "ls /home/bobbigmac/projects/podcasts/cache/feeds/*.md 2>/dev/null | wc -l; ls -la /home/bobbigmac/projects/podcasts/cache/state.json 2>/dev/null; test -x /home/bobbigmac/projects/podcasts…

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && .venv/bin/python3 <<'PY'\nimport json\nfrom pathlib import Path\nfrom scripts.shared import read_feeds_config, read_json, utc_now_iso, REPO_ROOT\nf…

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && .venv/bin/python3 -c \"\nfrom scripts.shared import read_feeds_config, REPO_ROOT\ncfg = read_feeds_config(REPO_ROOT / 'feeds.md')\nprint('feeds cou…

> `Read` {"path": "/home/bobbigmac/projects/podcasts/cache/state.json"}

> `Read` {"limit": 30, "path": "/home/bobbigmac/projects/podcasts/feeds.md"}

> `Grep` {"path": "/home/bobbigmac/projects/podcasts/scripts", "pattern": "def read_feeds_config"}

> `Read` {"limit": 40, "path": "/home/bobbigmac/projects/podcasts/scripts/shared.py"}

> `Read` {"limit": 120, "offset": 170, "path": "/home/bobbigmac/projects/podcasts/scripts/feeds_md.py"}

> `Read` {"limit": 80, "offset": 300, "path": "/home/bobbigmac/projects/podcasts/scripts/feeds_md.py"}

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && .venv/bin/python3 -c \"\nfrom scripts.shared import read_feeds_config, REPO_ROOT\nfor f in ['feeds.md','feeds.other.md','feeds.actualplays.md','fee…

> `Shell` {"command": "ls /home/bobbigmac/projects/podcasts/cache/feeds/*.md | wc -l; ls /home/bobbigmac/projects/podcasts/cache.other/feeds/*.md 2>/dev/null | wc -l; ls /home/bobbigmac/projects/podcasts/cache/…

> `Grep` {"path": "/home/bobbigmac/projects/podcasts/feeds.md", "pattern": "^# "}

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && .venv/bin/python3 -m scripts.update_feeds --feeds feeds.md --cache cache --prioritize 2>&1 | head -20", "description": "Try update_feeds with feeds…

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && comm -12 <(ls cache/feeds | sed 's/.md$//' | sort) <(ls cache.other/feeds 2>/dev/null | sed 's/.md$//' | sort) | wc -l; comm -23 <(ls cache/feeds |…

> `Read` {"limit": 5, "path": "/home/bobbigmac/projects/podcasts/cache.other/state.json"}

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && .venv/bin/python3 <<'PY'\nfrom scripts.update_feeds import _load_existing_feed_json\nfrom pathlib import Path\nj = _load_existing_feed_json(Path('c…

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && .venv/bin/python3 -c \"\nfrom scripts.update_feeds import _load_existing_feed_json\nfrom pathlib import Path\nj=_load_existing_feed_json(Path('cach…

### assistant

Building a temp feeds config from `feeds.md` (missing `# Feeds` header) and running priority against the stale `cache/`.

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && awk 'BEGIN{p=0} /^# Defaults/{print; print \"\"; print \"# Feeds\"; p=1; next} {print}' feeds.md > /tmp/feeds-britcom-test.md && .venv/bin/python3 …

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && .venv/bin/python3 <<'PY'\nimport json, subprocess\nfrom pathlib import Path\nfrom scripts.shared import read_feeds_config, read_json, utc_now_iso, …

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && .venv/bin/python3 -m scripts.update_feeds --feeds /tmp/feeds-britcom-test.md --cache cache --prioritize 2>&1", "description": "Run prioritized feed…

### assistant

Spot-checking overdue feeds against updated cache and live RSS:

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && .venv/bin/python3 <<'PY'\nimport json, subprocess\nfrom datetime import datetime, timezone\nfrom pathlib import Path\nfrom scripts.update_feeds imp…

> `Shell` {"command": "curl -sL --max-time 15 \"https://feeds.acast.com/public/shows/18dcd5db-f898-42c6-ab31-3a1853c1a645\" | head -80 | grep -E '<title>|<pubDate>|item' | head -12", "description": "Spot-check …

> `Shell` {"command": "curl -sL --max-time 15 \"https://feeds.megaphone.fm/VMP8521265258\" | head -80 | grep -E '<title>|<pubDate>' | head -8", "description": "Spot-check good-one RSS newest episode"}

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && .venv/bin/python3 <<'PY'\nimport json\nfrom pathlib import Path\nfrom scripts.shared import read_json, REPO_ROOT\nstate = read_json(REPO_ROOT/'cach…

### assistant

Ran `--prioritize` against `cache/` (last touched ~Apr 23). `feeds.md` is missing a `# Feeds` header so the parser sees 0 feeds — used a temp copy with that line inserted (`/tmp/feeds-britcom-test.md`, 54 feeds vs 63 cached files).

**Before run (stale cache)**

| Band | Count | Examples |
|------|-------|----------|
| overdue | 19 | adam-buxton, bugle, good-one, rhlstp, taskmaster |
| probably_due | 1 | skewer |
| inactive/defer | 34 | rule-of-three, parenting-hell, films-to-be-buried-with |

Selection: **21/54** (20 due-now: 15 critical + 5 normal; 1 stale from the inactive pool)

**Run result:** 21 feeds fetched/updated in ~3m20s. 33 skipped (inactive/defer, not due yet).

**Spot-checks after fetch**

| Feed | Was | Cache last ep (before) | Now | RSS match? |
|------|-----|------------------------|-----|------------|
| adam-buxton | overdue, 59d | 2026-04-20 | **2026-06-16** EP.275 | Yes — RSS pubDate Jun 16 |
| good-one | overdue, 63d | 2026-04-16 | **2026-06-11** | Yes — RSS Jun 11 |
| bugle | overdue, 57d | 2026-04-22 | **2026-06-17** | Updated |
| skewer | probably_due | 2026-05-20 | 2026-05-20 | No new ep (likely between seasons) |
| rule-of-three | inactive, 1225d | 2023-02-09 | unchanged | Correctly skipped |
| parenting-hell | inactive | 2026-04-21 | unchanged | Skipped — stale rotation next runs |
| taskmaster-peoples | inactive | 2026-04-20 | unchanged | Skipped |

Overdue calls on active weekly shows were right — the cache was ~2 months behind and they had new episodes. Inactive/hiatus feeds were correctly deprioritized; they'll rotate in via the stale band (~1/run at current pool size).

Side note: `feeds.md` needs a `# Feeds` line before the first `##` slug or `yarn update` / CI with `feeds.md` will no-op. Want me to add that?

### you

I just updated feed-check-priority.mjs, check it again

> `Read` {"path": "/home/bobbigmac/projects/podcasts/scripts/feed-check-priority.mjs"}

> `Grep` {"path": "/home/bobbigmac/projects/podcasts/scripts/update_feeds.py", "pattern": "feed-check-priority|_select_feeds_for_check|rank|select"}

### assistant

Re-running priority against the local cache with the updated script.

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && test -f /tmp/feeds-britcom-test.md || awk 'BEGIN{p=0} /^# Defaults/{print; print \"\"; print \"# Feeds\"; p=1; next} {print}' feeds.md > /tmp/feeds…

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && .venv/bin/python3 <<'PY'\nimport json, subprocess\nfrom collections import Counter\nfrom pathlib import Path\nfrom scripts.shared import read_feeds…

> `Shell` {"block_until_ms": 120000, "command": "cd /home/bobbigmac/projects/podcasts && .venv/bin/python3 -m scripts.update_feeds --feeds /tmp/feeds-britcom-test.md --cache cache --prioritize 2>&1", "descripti…

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && .venv/bin/python3 <<'PY'\nimport json, subprocess\nfrom pathlib import Path\nfrom scripts.shared import read_feeds_config, read_json, utc_now_iso, …

> `Shell` {"command": "curl -sL --max-time 15 \"https://podcasts.files.bbci.co.uk/p02pc9x6.rss\" | grep -E '<title>|<pubDate>' | head -6; echo '---'; curl -sL --max-time 15 \"https://feeds.megaphone.fm/CROOKEDM…

> `Shell` {"command": "cd /home/bobbigmac/projects/podcasts && .venv/bin/python3 -c \"\nfrom scripts.update_feeds import _load_existing_feed_json\nfrom pathlib import Path\nfor slug in ['bbc-comedy-of-the-week'…

### assistant

Re-ran against `cache/` with the updated script. **Integration is fine** — `update_feeds.py` still works via `rank` mode; no contract changes needed.

**Selection (54 britcom feeds, post–partial update cache)**

| Band | Count |
|------|-------|
| Due: overdue | 7 |
| Due: likely_waiting | 1 |
| Due: probably_due | 1 |
| Due: early | 9 |
| Due: inactive | 32 |
| **shouldCheckNow** | **8** |

Run fetched **9** (8 due + 1 stale: `bbc-graham-norton`).

**Spot-checks vs live RSS**

| Feed | New script | Last ep (cache) | Verdict |
|------|-----------|-----------------|---------|
| `bbc-comedy-of-the-week` | overdue ✓ | Apr 20 → **Jun 15** | RSS Jun 15 — real miss |
| `pod-save-the-uk` | overdue ✓ | Apr 23 → **Jun 18** | RSS Jun 18 — real miss |
| `all-killa-no-filla` | likely_waiting ✓ | Jun 8 | Checked, no change |
| `adam-buxton` | early, skip | Jun 16 | Correct — recently updated |
| `bugle` | early, skip | Jun 17 | Correct |
| `taskmaster` | probably_due, skip | Jun 11 | On cooldown from earlier run |
| `rule-of-three` | inactive, skip | Feb 2023 | Correct |
| `parenting-hell` | inactive, skip | Apr 21 | Correct — stale rotation later |

**vs old script:** Much tighter. Previously ~20 feeds flagged critical/overdue; now only feeds where the curve analogue says content is actually due. Recently-checked shows stay `early`; long-hiatus ones go `inactive` instead of false overdue.

**`cache.other`:** 104 feeds → 12 due + 2 stale = 14 selected (also sane).

No code changes required on our side. Still need `# Feeds` in `feeds.md` for the parser (used `/tmp/feeds-britcom-test.md` again).
