---
devin-sessionlog: transcript
session_id: dent-share
session_title: "Digest.json Producer Implementation"
cwd: /home/bobbigmac/projects/podcasts
created: 2026-08-31 23:02:39 UTC
last_activity: 2026-08-31 23:03:15 UTC
entries: 16
---

# digest-json-producer-implementation

Full session transcript — user and machine messages in order.

*Edits stick: dedupe keys on the `<!-- r:N m:ID -->` marker lines, not the text. To remove an entry permanently, delete its body and change its marker to `<!-- devin-sessionlog:removed m:ID -->` — deleting the marker outright lets backfill re-add it.*

---

<!-- r:2769441 m:7744b63c-b26c-4c97-a24e-40d18398357a h:bd3a81ed -->
### [node 2] user — 2026-08-31 23:03:15 UTC

is the new digest.json producer implemented and wired in correctly?

---

<!-- r:2769462 m:8a582183-faf5-4893-a7ff-8ad27460d8d3 h:da39a3ee -->
### [node 23] assistant — 2026-08-31 23:03:15 UTC



<tool_call code_search> {"search_term": "digest.json producer - where is digest.json generated and written, and how is it wired into the build pipeline", "search_folder_absolute_uri": "/home/bobbigmac/projects/podcasts"}
<tool_call grep> {"pattern": "digest\\.json", "output_mode": "content", "-n": true}
<tool_call grep> {"pattern": "digest", "output_mode": "files_with_matches"}

---

<!-- r:2769464 m:1f9bc665-8745-4518-a532-29336e31d985 h:d1164e31 -->
### [node 25] tool — 2026-08-31 23:03:15 UTC

A search subagent explored the codebase, running these commands:
- Grepped digest.json in .
- Grepped digest in .
- Grepped digest.*producer in .
- Grepped producer.*digest in .
- Grepped digest in .
- Grepped digest.*json in .
- Grepped json.*digest in .
- Grepped digest in .
- Read scripts/build_site.py
- Grepped build.*digest|digest.*build in scripts
- Read scripts/build_site.py
- Grepped write_json in scripts
- Read scripts/build_site.py
- Grepped feeds|all_episodes_index in scripts/build_site.py
- Grepped digest.*json|json.*digest in .
- Read scripts/shared.py
- Read scripts/build_site.py
- Grepped digest in .
- Read scripts/shared.py
- Grepped _build_digest in scripts
- Read scripts/build_site.py
- Grepped dist_dir in scripts/build_site.py
- Read scripts/build_site.py
- Grepped build.*site in scripts

It believes the snippets below are relevant to your search. Be careful evaluating their relevance — the subagent can make mistakes — and follow up with your normal grep/glob/read tools to fill in anything it missed:

<file path="scripts/build_site.py" total_lines=2995>
1144|def _build_digest(
1145|    *,
1146|    feeds: list[dict[str, Any]],
1147|    all_episodes_index: list[dict[str, Any]],
1148|    site_cfg: dict[str, Any],
1149|) -> dict[str, Any]:
1150|    """
1151|    Build a compact digest.json for external consumers (e.g. ceefaxish teletext).
1152|    Contains: shows with categories + inferred publish day, upcoming shows,
1153|    recent episodes, recent guests, category groupings.
1154|    """
1155|    from collections import Counter, defaultdict
1156|    from datetime import datetime, timezone
1157|
1158|    now = datetime.now(timezone.utc)
1159|    day_names = ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"]
1160|    today_idx = now.weekday()
1161|
1162|    # Build show summaries
1163|    shows: list[dict[str, Any]] = []
1164|    for feed in feeds:
1165|        slug = str(feed.get("slug") or "")
1166|        title = str(fee

---

<!-- r:2769465 m:8edc3c47-deae-4f1e-9fdd-90c1d65e0306 h:cd58946a -->
### [node 26] tool — 2026-08-31 23:03:15 UTC

Tool 'grep' validation failed: Failed to parse input: tool 'grep' does not accept field '-n', so the call was rejected instead of run with it ignored. Accepted fields: 'pattern', 'path', 'glob_pattern', 'output_mode', 'case_insensitive', 'max_results', 'context_lines'.

---

<!-- r:2769466 m:2730bead-6027-4b99-bb95-de45fa72e421 h:bc9adcfc -->
### [node 27] tool — 2026-08-31 23:03:15 UTC

Found 8 file(s) with matches for pattern 'digest' in /home/bobbigmac/projects/podcasts:
/home/bobbigmac/projects/podcasts/scripts/build_site.py (8 matches at lines: 1144, 1151, 1870, 1871, 1872, 1874, 1875, 1876)
/home/bobbigmac/projects/podcasts/scripts/shared.py (1 matches at lines: 61)
/home/bobbigmac/projects/podcasts/scripts/pod-api-speaker-search.js (2 matches at lines: 83, 84)
/home/bobbigmac/projects/podcasts/scripts/further_search.py (4 matches at lines: 112, 149, 153, 174)
/home/bobbigmac/projects/podcasts/scripts/make_promo.py (1 matches at lines: 192)
/home/bobbigmac/projects/podcasts/Podcast-Feature_Ideas_and_Backlog.md (3 matches at lines: 1033, 1036, 1043)
/home/bobbigmac/projects/podcasts/ChatGPT-Podcaster_Ideas_and_Backlog.md (3 matches at lines: 1033, 1036, 1043)
/home/bobbigmac/projects/podcasts/ChatGPT-Android_app_porting_options.md (3 matches at lines: 1019, 1022, 1029)


---

<!-- r:2769467 m:ef04eacb-20c2-473e-9d4c-df3aca3e73b5 h:da39a3ee -->
### [node 28] assistant — 2026-08-31 23:03:15 UTC



<tool_call read> {"file_path": "/home/bobbigmac/projects/podcasts/scripts/build_site.py", "offset": 1840, "limit": 60}
<tool_call read> {"file_path": "/home/bobbigmac/projects/podcasts/scripts/shared.py", "offset": 40, "limit": 40}
<tool_call grep> {"pattern": "_infer_publish_day", "output_mode": "content", "context_lines": 3}

---

<!-- r:2769469 m:6a6a9c02-4fbf-4979-9fb0-be93d2945c6b h:6a679b43 -->
### [node 30] tool — 2026-08-31 23:03:15 UTC

Output truncated at line 1899; continue reading from line 1900.

<file-view path="/home/bobbigmac/projects/podcasts/scripts/build_site.py" start_line="1840" end_line="1899">
1840|
1841|    if feed_order and not all_episodes_index:
1842|        print("[warn] No cached episodes found yet (run update script / wait for Action).", file=sys.stderr)
1843|
1844|    # Emit search index JSON (lazy-loaded by the client).
1845|    index_json = []
1846|    for e in all_episodes_index:
1847|        if not e.get("episode_key"):
1848|            continue
1849|        image_url = str((e.get("episode_image_url") or e.get("feed_image_url") or "")).strip()
1850|        row = {
1851|            "k": e["episode_key"],
1852|            "t": e.get("title") or "",
1853|            "d": (e.get("published_at") or "")[:10],
1854|            "f": e.get("feed_slug") or "",
1855|            "ft": e.get("feed_title") or "",
1856|            "im": image_url,
1857|            "s": e.get("speakers") or [],
1858|            "x": e.get("topics") or [],
1859|        }
1860|        b = e.get("enclosure_bytes")
1861|        du = e.get("duration_seconds")
1862|        if isinstance(b, int) and b > 0:
1863|            row["b"] = int(b)
1864|        if isinstance(du, int) and du > 0:
1865|            row["du"] = int(du)
1866|        index_json.append(row)
1867|    write_json(dist_dir / "index.json", index_json)
1868|    write_json(dist_dir / "site.json", site_cfg)
1869|
1870|    # Emit digest.json for external consumers (ceefaxish teletext, etc.)
1871|    digest = _build_digest(feeds=feeds, all_episodes_index=all_episodes_index, site_cfg=site_cfg)
1872|    write_json(dist_dir / "digest.json", digest)
1873|    print(
1874|        f"[digest] {digest['total_shows']} shows, {digest['total_episodes']} episodes, "
1875|        f"{len(digest['upcoming'])} upcoming, {len(digest['recent_guests'])} recent guests, "
1876|        f"{len(digest['categories'])} categories",
1877|        file=sys.stderr,
1878|    )
1879|
1

---

<!-- r:2769470 m:b28cfedb-ac50-4374-8b87-25bd2e4ab1ee h:5507d80d -->
### [node 31] tool — 2026-08-31 23:03:15 UTC

<file-view path="/home/bobbigmac/projects/podcasts/scripts/shared.py" start_line="40" end_line="79">
 40|            f"Feeds config must be Markdown (.md).\n"
 41|            f"Got: {path}\n"
 42|            f"Tip: run `yarn convert:feedsmd` to generate `feeds.md` from legacy `feeds*.json`."
 43|        )
 44|    text = path.read_text(encoding="utf-8", errors="replace")
 45|    cfg = parse_feeds_markdown(text, base_dir=path.parent)
 46|    if not isinstance(cfg, dict):
 47|        raise ValueError(f"Invalid markdown feeds config: {path}")
 48|    return cfg
 49|
 50|
 51|def write_json(path: Path, data: Any) -> None:
 52|    path.parent.mkdir(parents=True, exist_ok=True)
 53|    path.write_text(json.dumps(data, ensure_ascii=False, indent=2) + "\n", encoding="utf-8")
 54|
 55|
 56|def utc_now_iso() -> str:
 57|    return datetime.now(timezone.utc).replace(microsecond=0).isoformat()
 58|
 59|
 60|def sha1_hex(text: str) -> str:
 61|    return hashlib.sha1(text.encode("utf-8")).hexdigest()
 62|
 63|
 64|def strip_html(text: str) -> str:
 65|    text = html.unescape(text or "")
 66|    text = re.sub(r"<[^>]+>", " ", text)
 67|    text = re.sub(r"\s+", " ", text).strip()
 68|    return text
 69|
 70|
 71|def normalize_ws(text: str) -> str:
 72|    return re.sub(r"\s+", " ", (text or "")).strip()
 73|
 74|
 75|def slugify(text: str) -> str:
 76|    text = (text or "").strip().lower()
 77|    text = re.sub(r"[’']", "", text)
 78|    text = re.sub(r"[^a-z0-9]+", "-", text)
 79|    return text.strip("-") or "unknown"
</file-view>

---

<!-- r:2769471 m:39a4a003-9d47-44a4-a4df-40bf2e00041c h:df232184 -->
### [node 32] tool — 2026-08-31 23:03:15 UTC

Found 2 match(es) for pattern '_infer_publish_day' in /home/bobbigmac/projects/podcasts:
-- 2 matches in /home/bobbigmac/projects/podcasts/scripts/build_site.py
 1109|    return {"nodes": list(node_by_id.values()), "edges": edges}
 1110|
 1111|
>1112|def _infer_publish_day(episodes: list[dict[str, Any]]) -> str | None:
 1113|    """
 1114|    Infer the most common day-of-week from the most recent ~20 episodes.
 1115|    Returns day name (e.g. 'Wednesday') or None if not enough data.
...
 1180|        # Sort episodes by date desc
 1181|        sorted_eps = sorted(eps, key=lambda e: e.get("published_at") or "", reverse=True)
 1182|        latest_date = (sorted_eps[0].get("published_at") or "")[:10]
>1183|        publish_day = _infer_publish_day(sorted_eps)
 1184|        shows.append({
 1185|            "slug": slug,
 1186|            "title": title,

---

<!-- r:2769472 m:ec515d05-472e-4591-9212-b06e231a6735 h:da39a3ee -->
### [node 33] assistant — 2026-08-31 23:03:15 UTC



<tool_call read> {"file_path": "/home/bobbigmac/projects/podcasts/scripts/build_site.py", "limit": 35, "offset": 1112}
<tool_call grep> {"context_lines": 5, "output_mode": "content", "pattern": "all_episodes_index\\s*=|all_episodes_index\\.sort|all_episodes_index\\s*=.*sort"}

---

<!-- r:2769474 m:f95bd1e7-2918-4e8b-b0eb-55080a187cd1 h:92ee4f5f -->
### [node 35] tool — 2026-08-31 23:03:15 UTC

Output truncated at line 1146; continue reading from line 1147.

<file-view path="/home/bobbigmac/projects/podcasts/scripts/build_site.py" start_line="1112" end_line="1146">
1112|def _infer_publish_day(episodes: list[dict[str, Any]]) -> str | None:
1113|    """
1114|    Infer the most common day-of-week from the most recent ~20 episodes.
1115|    Returns day name (e.g. 'Wednesday') or None if not enough data.
1116|    """
1117|    from collections import Counter
1118|
1119|    recent = []
1120|    for ep in episodes:
1121|        ts = ep.get("published_at") or ""
1122|        if ts:
1123|            recent.append(ts)
1124|        if len(recent) >= 20:
1125|            break
1126|    if len(recent) < 5:
1127|        return None
1128|    days = Counter()
1129|    for ts in recent:
1130|        try:
1131|            dt = datetime.fromisoformat(ts)
1132|            days[dt.strftime("%A")] += 1
1133|        except Exception:
1134|            continue
1135|    if not days:
1136|        return None
1137|    top_day, top_count = days.most_common(1)[0]
1138|    # Only return if there's a clear pattern (>50% of recent episodes)
1139|    if top_count / max(len(recent), 1) > 0.5:
1140|        return top_day
1141|    return None
1142|
1143|
1144|def _build_digest(
1145|    *,
1146|    feeds: list[dict[str, Any]],
</file-view>

---

<!-- r:2769475 m:300885c0-7b2e-4355-8cc3-dc4bc5180469 h:2d9f478d -->
### [node 36] tool — 2026-08-31 23:03:15 UTC

Found 3 match(es) for pattern 'all_episodes_index\s*=|all_episodes_index\.sort|all_episodes_index\s*=.*sort' in /home/bobbigmac/projects/podcasts:
-- 3 matches in /home/bobbigmac/projects/podcasts/scripts/build_site.py
 1834|        if base in used:
 1835|            base = f"{sp_slug}-speaker"
 1836|        speaker_page_slug_by_slug[sp_slug] = _unique_slug(base, used, salt="speaker:" + sp_slug)
 1837|
 1838|    # Sort index by date desc.
>1839|    all_episodes_index.sort(key=lambda e: e.get("published_at") or "", reverse=True)
 1840|
 1841|    if feed_order and not all_episodes_index:
 1842|        print("[warn] No cached episodes found yet (run update script / wait for Action).", file=sys.stderr)
 1843|
 1844|    # Emit search index JSON (lazy-loaded by the client).
...
 1866|        index_json.append(row)
 1867|    write_json(dist_dir / "index.json", index_json)
 1868|    write_json(dist_dir / "site.json", site_cfg)
 1869|
 1870|    # Emit digest.json for external consumers (ceefaxish teletext, etc.)
>1871|    digest = _build_digest(feeds=feeds, all_episodes_index=all_episodes_index, site_cfg=site_cfg)
 1872|    write_json(dist_dir / "digest.json", digest)
 1873|    print(
 1874|        f"[digest] {digest['total_shows']} shows, {digest['total_episodes']} episodes, "
 1875|        f"{len(digest['upcoming'])} upcoming, {len(digest['recent_guests'])} recent guests, "
 1876|        f"{len(digest['categories'])} categories",
 1877|        file=sys.stderr,
 1878|    )
 1879|
>1880|    graph_data = _build_graph_data(feeds=feeds, all_episodes_index=all_episodes_index, base_path=base_path)
 1881|    graph_json = json.dumps(graph_data, ensure_ascii=False, separators=(",", ":"))
 1882|
 1883|    # Categories (feeds can be in multiple categories).
 1884|    category_to_feeds: dict[str, dict[str, dict[str, Any]]] = defaultdict(dict)
 1885|    for feed in feeds:

---

<!-- r:2769476 m:7299385a-a7d6-4d9c-8644-690556d140b1 h:c9e8ce7f -->
### [node 37] assistant — 2026-08-31 23:03:15 UTC

Let me verify the `feeds` list has episodes populated by the time `_build_digest` is called, and check the supplemental field.

<tool_call grep> {"context_lines": 3, "output_mode": "content", "pattern": "feeds\\.append|feeds\\s*=\\s*\\[|for feed in feeds|feed\\[.episodes.\\]\\s*=|feed\\.setdefault\\(.episodes", "path": "/home/bobbigmac/projects/podcasts/scripts/build_site.py", "max_results": 40}
<tool_call grep> {"context_lines": 2, "output_mode": "content", "pattern": "supplemental", "path": "/home/bobbigmac/projects/podcasts/scripts/build_site.py", "max_results": 30}

---

<!-- r:2769478 m:efdd93df-67f3-4beb-91d7-7dc4677a22f1 h:4c49f8cb -->
### [node 39] tool — 2026-08-31 23:03:15 UTC

Found 8 match(es) for pattern 'feeds\.append|feeds\s*=\s*\[|for feed in feeds|feed\[.episodes.\]\s*=|feed\.setdefault\(.episodes' in /home/bobbigmac/projects/podcasts/scripts/build_site.py:
-- 8 matches in /home/bobbigmac/projects/podcasts/scripts/build_site.py
 1161|
 1162|    # Build show summaries
 1163|    shows: list[dict[str, Any]] = []
>1164|    for feed in feeds:
 1165|        slug = str(feed.get("slug") or "")
 1166|        title = str(feed.get("title") or slug)
 1167|        eps = feed.get("episodes") or []
...
 1243|    # excluding owners of the specific feed (hosts don't count as guests on their own show).
 1244|    # Speaker data is noisy (name variants, tagging errors) so we keep a low threshold.
 1245|    owners_by_feed_slug: dict[str, set[str]] = {}
>1246|    for feed in feeds:
 1247|        slug = str(feed.get("slug") or "")
 1248|        owners_by_feed_slug[slug] = {str(o).lower() for o in (feed.get("owners") or [])}
 1249|    guest_counts: Counter = Counter()
...
 1470|            and isinstance(v, (int, float))
 1471|        }
 1472|        if not feed:
>1473|            feeds.append(
 1474|                {
 1475|                    "slug": slug,
 1476|                    "title": cfg_title or slug,
...
 1507|                exclude=cfg_exclude,
 1508|            )
 1509|            ep["topics"] = sanitize_topics(ep.get("topics"))
>1510|        feeds.append(feed)
 1511|
 1512|    # Build speaker index.
 1513|    speaker_name_by_slug: dict[str, str] = {}
 1514|    speaker_eps_by_slug: dict[str, dict[str, dict[str, Any]]] = defaultdict(dict)
 1515|    all_episodes_index: list[dict[str, Any]] = []
>1516|    for feed in feeds:
 1517|        feed_slug = feed.get("slug") or ""
 1518|        feed_title = feed.get("title") or feed_slug
 1519|        feed_image_url = feed.get("image_url")
...
 1882|
 1883|    # Categories (feeds can be in multiple categories).
 1884|    category_to_feeds: dict[str, dict[str, dict[str, Any]]] = defaultdict(dict)
>1885|   

---

<!-- r:2769479 m:85137203-b4bd-4ed2-9e78-413ff019b414 h:66964578 -->
### [node 40] tool — 2026-08-31 23:03:15 UTC

Found 30 match(es) (limited by max_results) for pattern 'supplemental' in /home/bobbigmac/projects/podcasts/scripts/build_site.py:
-- 30 matches in /home/bobbigmac/projects/podcasts/scripts/build_site.py
 1016|    feed_by_slug: dict[str, dict[str, Any]] = {str(f.get("slug") or ""): f for f in feeds}
 1017|    owners_by_feed: dict[str, set[str]] = {}
>1018|    supplemental_by_feed: dict[str, bool] = {}
 1019|
 1020|    for slug, feed in feed_by_slug.items():
 1021|        owners = sanitize_speakers(feed.get("owners") or [])
 1022|        owners_by_feed[slug] = {n.lower() for n in owners}
>1023|        supplemental_by_feed[slug] = bool(feed.get("supplemental"))
 1024|
 1025|    # Count appearances per (podcast, speaker) and podcasts-per-speaker.
...
 1089|            "l": title[:80],
 1090|            "h": _href(base_path, f"{feed_slug}/"),
>1091|            "sup": 1 if supplemental_by_feed.get(feed_slug) else 0,
 1092|        }
 1093|
...
 1175|                "latest_date": None,
 1176|                "publish_day": None,
>1177|                "supplemental": bool(feed.get("supplemental")),
 1178|            })
 1179|            continue
...
 1190|            "latest_date": latest_date,
 1191|            "publish_day": publish_day,
>1192|            "supplemental": bool(feed.get("supplemental")),
 1193|        })
 1194|
...
 1197|    upcoming: list[dict[str, Any]] = []
 1198|    for show in shows:
>1199|        if not show["publish_day"] or show["supplemental"]:
 1200|            continue
 1201|        day_idx = day_names.index(show["publish_day"])
...
 1222|    upcoming.sort(key=lambda s: s["days_until"])
 1223|
>1224|    # Recent episodes (latest 30 across all shows, excluding supplemental)
 1225|    recent_eps = []
 1226|    for ep in all_episodes_index:
 1227|        feed_slug = ep.get("feed_slug") or ""
 1228|        feed = next((f for f in feeds if f.get("slug") == feed_slug), None)
>1229|        if feed and feed.get("supplemental"):
 1230|            continue

---

<!-- r:2769480 m:f2118f39-76a9-4ef7-bafe-15412321c1b1 h:1842dcc0 -->
### [node 41] assistant — 2026-08-31 23:03:15 UTC

Yes — the `digest.json` producer is implemented and wired in correctly. Here's the verification:

## Implementation
- **`_build_digest`** is defined at <ref_snippet file="/home/bobbigmac/projects/podcasts/scripts/build_site.py" lines="1144-1297" />, taking keyword-only args `feeds`, `all_episodes_index`, `site_cfg`. It assembles shows, upcoming, recent episodes (30), recent guests (top 15 from last 200, ≥2 appearances, excluding feed owners), and category groupings.
- **`_infer_publish_day`** helper at <ref_snippet file="/home/bobbigmac/projects/podcasts/scripts/build_site.py" lines="1112-1141" /> infers the day-of-week from the most recent ~20 episodes (only returns if >50% land on the same day).

## Wiring
Called at <ref_snippet file="/home/bobbigmac/projects/podcasts/scripts/build_site.py" lines="1870-1878" />:
```
digest = _build_digest(feeds=feeds, all_episodes_index=all_episodes_index, site_cfg=site_cfg)
write_json(dist_dir / "digest.json", digest)
```
- It runs **after** `all_episodes_index.sort(..., reverse=True)` at line 1839, so the "recent 30" / "recent 200" slices correctly get newest-first ordering.
- The `feeds` list is fully populated by this point — `episodes`, `categories`, `owners`, and `supplemental` are all set (feeds built ~1473–1510, `supplemental` set at line 1498), so the supplemental-exclusion logic in the digest (lines 1199, 1229, 1253, 1268) works.
- `write_json` (shared.py:51) creates parent dirs and writes UTF-8 JSON.
- A `[digest] …` summary line is printed to stderr.

## Notes / one thing worth flagging
- No client code in this repo consumes `digest.json` — by design, it's for external consumers (the comment cites "ceefaxish teletext"). The `digest` match in `scripts/shared.py:61` is a false positive (`hashlib…hexdigest()`). No service-worker precache update is needed since it's a runtime-fetched data file, not a static app asset.
- **Minor inconsistency:** `total_shows` (line 1290) excludes supplemental shows, but `total_episodes` (line 1291) sums `episode_count` over *all* shows including supplemental ones:
  ```python
  "total_shows": len([s for s in shows if not s["supplemental"]]),
  "total_episodes": sum(s["episode_count"] for s in shows),
  ```
  So `total_episodes` counts supplemental episodes while `total_shows` doesn't count supplemental shows. If that's not intended, the sum should filter the same way: `sum(s["episode_count"] for s in shows if not s["supplemental"])`. Want me to fix that?

---

<!-- devin-sessionlog:end -->
