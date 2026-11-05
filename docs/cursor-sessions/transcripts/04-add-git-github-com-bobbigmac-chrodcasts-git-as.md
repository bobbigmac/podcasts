---
cursor_session: 5b46f7e0-ccf5-4846-b7ca-f9913bd39497
source: cursor-composer
cursor_hint: ?
user_entries: 14
---

# transcript — add-git-github-com-bobbigmac-chrodcasts-git-as

### you

add git@github.com:bobbigmac/chrodcasts.git as a second remote, and add a file like @/home/bobbigmac/projects/podcasts/push-code.sh , just with the name udpated, as we want to ship 2 github pages repos from this one config

### assistant

Completed:

1. **Added remote** `chrodcasts` → `git@github.com:bobbigmac/chrodcasts.git`
2. **Created** `push-code.sh` (defaults: origin, chrodcasts, main) and made it executable

Run `./push-code.sh` to push `main` to both remotes.

### you

what env vars should I be setting on the new chrodcasts github env?

### assistant

Configure the **chrodcasts** repo’s `github-pages` environment with:

**Variables (vars):**
| Variable | Purpose | Example |
|----------|---------|---------|
| `VOD_FEEDS` | Feeds config file | `feeds/church.md` |
| `VOD_CACHE_BRANCH` | Branch for feed cache | `cache-church` or `cache` |
| `VOD_BASE_PATH` | Site base path | `/` |

**Secrets (secrets):**
| Secret | Purpose |
|--------|---------|
| `VOD_SUPABASE_URL` | Supabase project URL (timed comments) |
| `VOD_SUPABASE_ANON_KEY` | Supabase anon key |
| `VOD_HCAPTCHA_SITEKEY` | hCaptcha site key (comments) |

Use a different `VOD_CACHE_BRANCH` than vodcasts so each repo has its own cache branch. If chrodcasts uses a different domain, you may need a separate hCaptcha site key.

### you

update our church.md header section to add these 4 options as alts, so I can manually swap in after review. Also check the suggested feeds, most of them 404, so you'll need to check which ones actually have entries that do point to active video content. 



### New Header Text Suggestions
Based on the existing header in your document (title: "Prays.be Streaming Church", subtitle: "Prays.be", description: "Enjoy unlimited streaming church content"), here are a few refreshed variations to enhance appeal while keeping the faith-focused, streaming theme. These aim to be more engaging, SEO-friendly, and aligned with the site's purpose of aggregating Christian video feeds:

1. **Option 1** (Emphasizing accessibility and variety):
   - title: Prays.be: Stream Faith Anytime, Anywhere
   - subtitle: Prays.be Streaming Church
   - description: Discover endless Christian sermons, Bible teachings, and worship videos from global ministries.

2. **Option 2** (Focusing on spiritual growth):
   - title: Prays.be: Nourish Your Soul with Streaming Church
   - subtitle: Prays.be
   - description: Unlimited access to inspiring sermons, Bible studies, and faith-building content for daily devotion.

3. **Option 3** (Highlighting community and modernity):
   - title: Prays.be: Modern Worship in Your Hands
   - subtitle: Streaming Church Essentials
   - description: Enjoy free, on-demand Christian videos including sermons, teachings, and live-inspired music from trusted sources.

4. **Option 4** (Keeping it simple yet expansive):
   - title: Prays.be Streaming Church Network
   - subtitle: Prays.be
   - description: Unlimited streaming of global church content: sermons, Bible studies, TV ministries, and more.

Feel free to mix and match or tweak based on your branding.

### Recommended Additional Feeds
I've reviewed your existing feeds list, which focuses on Christian sermons, Bible studies, TV ministries, worship, and related categories with video enclosures (vodcasts). All recommendations below are open RSS feeds with video support, fitting the same use case—primarily U.S.-based or international English-language Christian content. I prioritized ones not already in your list, emphasizing variety (e.g., more megachurches, well-known pastors, and diverse tags like prosperity, expositional, or practical living). These were sourced from reliable directories and church sites, ensuring they have video enclosures for streaming.

Here are 20 recommendations (a solid "dozen or two"), structured like your entries for easy integration:

## elevation-church
- url: https://elevationchurch.org/feed/podcast/video
- title: Elevation Church
- category: sermons
- tags: sermons, contemporary, north-carolina, steven-furtick, worship, concert, live-music

## hillsong-church
- url: https://hillsong.com/collected/all/blogs/category/blogs/feed
- title: Hillsong Church
- category: sermons
- tags: sermons, worship, australia, brian-houston, global, concert, live-music

## bethel-church
- url: https://www.bethel.com/podcasts/rss
- title: Bethel Church
- category: sermons
- tags: sermons, charismatic, california, bill-johnson, healing, worship, concert, live-music

## lakewood-church
- url: https://www.lakewoodchurch.com/podcasts/video
- title: Lakewood Church
- category: tv-ministry
- tags: tv-ministry, prosperity, joel-osteen, texas, encouragement, sunday

## saddleback-church
- url: https://saddleback.com/podcasts/video
- title: Saddleback Church
- category: sermons
- tags: sermons, practical-living, rick-warren, california, multi-site, concert, live-music

## gateway-church
- url: https://gatewaypeople.com/podcasts/rss
- title: Gateway Church
- category: sermons
- tags: sermons, texas, robert-morris, multi-site, bible-teaching, sunday

## life-church
- url: https://openblog.life.church/feed/
- title: Life.Church
- category: sermons
- tags: sermons, craig-groeschel, oklahoma, multi-site, practical, concert, live-music

## passion-city
- url: https://passioncitychurch.com/podcasts/video/rss
- title: Passion City Church
- category: sermons
- tags: sermons, louie-giglio, georgia, worship, young-adults, concert, live-music

## village-church
- url: https://www.thevillagechurch.net/resources/sermons/rss
- title: The Village Church
- category: sermons
- tags: sermons, matt-chandler, texas, expositional, reformed, sunday

## north-point
- url: https://northpoint.org/messages/rss
- title: North Point Ministries
- category: sermons
- tags: sermons, andy-stanley, georgia, practical-living, multi-site, sunday

## desiring-god
- url: https://www.desiringgod.org/messages/rss
- title: Desiring God
- category: bible-study
- tags: bible-study, john-piper, reformed, minnesota, theology, teaching

## gospel-coalition
- url: https://www.thegospelcoalition.org/podcasts/rss
- title: The Gospel Coalition
- category: teaching
- tags: teaching, reformed, conferences, multi-source, theology

## andrew-wommack
- url: https://www.awmi.net/video/tv-archives/rss
- title: Andrew Wommack Ministries
- category: tv-ministry
- tags: tv-ministry, faith-teaching, grace, colorado, daily

## amazing-facts
- url: https://www.amazingfacts.org/media-library/podcasts/rss
- title: Amazing Facts
- category: bible-study
- tags: bible-study, doug-batchelor, sabbath, california, prophecy

## in-touch
- url: https://www.intouch.org/broadcast/video-archives/rss
- title: In Touch Ministries
- category: tv-ministry
- tags: tv-ministry, charles-stanley, georgia, teaching, daily

## bible-project
- url: https://bibleproject.com/podcasts/rss
- title: Bible Project
- category: bible-study
- tags: bible-study, animated, theology, oregon, series

## bible-recap
- url: https://www.thebiblerecap.com/podcast/rss
- title: The Bible Recap
- category: bible-study
- tags: bible-study, through-the-bible, daily, tara-leigh-cobble

## through-the-word
- url: https://throughtheword.org/podcasts/rss
- title: Through the Word
- category: bible-study
- tags: bible-study, audio-guide, chapter-by-chapter, california

## james-river-church
- url: https://feed.podbean.com/jamesriverchurch/feed.xml
- title: James River Church Podcast
- category: sermons
- tags: sermons, john-lindell, missouri, pentecostal, sunday, concert, live-music

## church-leaders
- url: https://churchleaders.libsyn.com/rss
- title: ChurchLeaders Podcast
- category: ministry
- tags: ministry, leadership, interviews, pastors, practical

These should integrate seamlessly into your feeds section. They all use open RSS with video enclosures (confirmed via feed structures supporting MP4 or similar). If any don't load properly in your setup, test the enclosures for video mime types. Let me know if you need more or help verifying!

### assistant

Creating the header options and a summary of the feed checks:

### assistant

Summary of changes:

**Header options (lines 6–9)**  
Added four alternatives as comments. To use one, replace the active `title`, `subtitle`, and `description` with the values from that option.

**Suggested feeds**  
All 20 suggested feeds were checked; none were added:

| Status | Feeds |
|--------|-------|
| **404** | elevation, bethel, lakewood, saddleback, gateway, village, northpoint, desiring-god, amazing-facts, intouch, bible-project, bible-recap |
| **500** | lakewood, church-leaders |
| **Timeout** | hillsong, gospel-coalition |
| **Empty / no video** | passion-city (no items), andrew-wommack (comments only), through-the-word (comments only) |
| **Blog only** | life-church (no video enclosures) |
| **Duplicate** | james-river-church (audio-only; `james-river` already has video) |

A verification note is in the HTML comment above the Feeds section.

### you

add a y2k/millenium-inspired theme to themes, style and ui, thinkking silvers and curves.

### assistant

Summary of changes:

**themes.css – Y2K theme**
- **Colors:** Silver palette (`--y2k-silver`, `--y2k-chrome`), light gray backgrounds, blue-silver accents
- **Curves:** 20px panels, 14–24px radius, pill-shaped buttons (`border-radius: 999px`)
- **Chrome look:** Radial gradients on play button and scrubber thumb, light inner highlights
- **Panels:** Rounded corners, soft borders, light shadows
- **Guide grid:** Rounded episode blocks, silver progress bars, chrome-style scrollbars

**theme_takeover.js**
- Added a “Y2K” theme option next to Modern and DOS

To use it: long-press the theme button in the guide bar, then choose Y2K.

### you

add these as TODOs to our Readme so I can review properly, I think the first priority should be making 'real' page content based on each page, but not sure yet if we should monkey-patch the 404.html or build a dedicated landing page for each feed, and have that hotswap (faking a multipage site)... Just log for now, will think about it later...


Your current top block is still placeholder-y (`title: Prays.be Streaming Church`, `description: Enjoy unlimited streaming church content`). 

Pick one of these sets and drop it into `# Site`:

```md
- title: Prays.be
- subtitle: Distraction-free streaming church
- description: A calm video player for services and sermons, straight from RSS video enclosures.
```

```md
- title: Prays.be
- subtitle: Press play. Stay present.
- description: Watch services, sermons, prayer, and teaching with no algorithm, no comments, no noise.
```

```md
- title: Prays.be
- subtitle: Church vodcasts, neatly
- description: A directory + player for open RSS video feeds. Simple, fast, distraction-free.
```

If you want to tighten the “identity” signal for feed hosts/CDNs, I’d also change:

```md
- user_agent: prays.be/vodcasts (+https://prays.be/)
```

---

Add these to your `# Feeds` list (all intended as video-enclosure feeds, matching your use-case):

```md
## watermark-porch-video
- url: https://media.watermark.org/podcasts/porch-video.xml
- title: The Porch (Video) — Watermark Community Church
- category: sermons
- tags: sermons, young-adults, teaching, weekly, dallas

## desiring-god-messages-video
- url: http://feed.desiringgod.org/messages-by-desiring-god-video.rss
- title: Messages by Desiring God (Video)
- category: teaching
- tags: sermons, preaching, conference, reformed, weekly

## ancient-faith-simple-path-video
- url: http://feeds.ancientfaith.com/SimplePathToGodVideo/
- title: The Simple Path to God (Video) — Ancient Faith
- category: teaching
- tags: orthodox, teaching, catechesis, practical, weekly

## wisdom-television-murdock-video
- url: https://feed.podbean.com/wisdomonline/feed.xml
- title: Wisdom Television (Video) — Dr. Mike Murdock
- category: tv-ministry
- tags: tv-ministry, teaching, daily, talk

## battle-drill-daily-devotional-video
- url: https://api.substack.com/feed/podcast/5786250.rss
- title: Battle Drill Daily Devotional (Video)
- category: devotional
- tags: devotional, bible-reading, daily, short-form

## tung-fook-cbc-video
- url: http://share.tungfook.com/tungfook/podcasts/cbc/video/video.xml
- title: Tung Fook Chuen Kee Church — CBC (Video)
- category: sermons
- tags: sermons, hong-kong, chinese, weekly

## church-of-the-highlands-weekend-video
- url: https://feeds.churchofthehighlands.com/media/weekend/video
- title: Church of the Highlands — Weekend Service (Video)
- category: sermons
- tags: sermons, weekend, multi-site, alabama, weekly

## hpumc-sanctuary-videocast
- url: http://feeds2.feedburner.com/HpumcSanctuaryServiceVideocast
- title: Highland Park UMC — Sanctuary Service (Videocast)
- category: sermons
- tags: sermons, methodist, liturgy, weekly, dallas

## all-souls-sundays
- url: http://feeds.feedburner.com/AllSoulsChurchSundays
- title: All Souls Church — Sundays (Video)
- category: sermons
- tags: sermons, anglican, uk, weekly, london

## sermontv-calvarylighthouse-video
- url: http://CalvaryLighthouse.sermon.tv/rss/main/video
- title: Calvary Lighthouse (Sermon.tv) — Main (Video)
- category: sermons
- tags: sermons, sermontv, church, weekly

## sermontv-ccfhkingwood-video
- url: http://CCFHKingwood.sermon.tv/rss/main/video
- title: CCFH Kingwood (Sermon.tv) — Main (Video)
- category: sermons
- tags: sermons, sermontv, church, weekly, texas

## sermontv-communitychurchtv-video
- url: http://CommunityChurchTV.sermon.tv/rss/main/video
- title: CommunityChurchTV (Sermon.tv) — Main (Video)
- category: sermons
- tags: sermons, sermontv, church, weekly

## sermontv-genoaunitedbaptistchurch-video
- url: http://GenoaUnitedBaptistChurch.sermon.tv/rss/main/video
- title: Genoa United Baptist Church (Sermon.tv) — Main (Video)
- category: sermons
- tags: sermons, baptist, sermontv, weekly

## sermontv-lbcwylie-video
- url: http://LBCWylieTX.sermon.tv/rss/main/video
- title: LBC Wylie TX (Sermon.tv) — Main (Video)
- category: sermons
- tags: sermons, baptist, sermontv, weekly, texas

## sermontv-ncfstillwaterok-video
- url: http://NCFStillwaterOK.sermon.tv/rss/main/video
- title: NCF Stillwater OK (Sermon.tv) — Main (Video)
- category: sermons
- tags: sermons, sermontv, weekly, oklahoma

## sermontv-thenetrev-video
- url: http://TheNetRev.sermon.tv/rss/main/video
- title: TheNetRev (Sermon.tv) — Main (Video)
- category: sermons
- tags: sermons, sermontv, weekly

## sermontv-apostolicclassics-video
- url: http://apostolicclassics.sermon.tv/rss/main/video
- title: Apostolic Classics (Sermon.tv) — Main (Video)
- category: teaching
- tags: teaching, sermontv, archives, classic, weekly

## sermontv-drumley-video
- url: http://drumley.sermon.tv/rss/main/video
- title: Drumley (Sermon.tv) — Main (Video)
- category: sermons
- tags: sermons, sermontv, weekly
```

Source checks for the new feeds, in order:

1. The Porch feed URL ([podbean.com][1])
2. Desiring God video feed URL ([podbean.com][2])
3. Simple Path to God video feed URL ([Podstatus][3])
4. Wisdom Television feed URL ([Podstatus][4])
5. Battle Drill Daily Devotional feed URL ([Podstatus][5])
6. Tung Fook CBC video feed URL ([Podstatus][6])
7. Church of the Highlands video feed URL ([Podstatus][7])
8. HPUMC videocast feed URL ([Podstatus][8])
9. All Souls Sundays feed URL ([Podstatus][9])
   10–18) sermon.tv feed hostnames (and one explicit `/video` example) ([Gist][10])

---

Short shortlist for discoverability + accessibility (keeping the “mostly a player” vibe)

* bake real text into the homepage: what it is, what “video RSS” means, what you don’t do (no recommendations/comments), plus a couple of example categories (Services, Sermons, Prayer, Kids, Study)
* give every feed its own page with a stable URL, a plain description, and a tiny episode list (enough for indexing + sharing)
* OPML export and a public JSON index of feeds (slug, title, tags, url) so people can fork/clone/auto-import
* add OpenGraph/Twitter cards so a shared link previews as “watchable” instead of “random site”
* sitemap + sensible canonical URLs; keep query params out of canonical
* keyboard-first controls (space play/pause, ←/→ seek, m mute, f fullscreen), with a visible “shortcuts” help panel
* captions/transcript affordances even when unavailable (show “captions not provided” instead of silent absence)
* focus rings that are obvious, skip-to-content, and no hover-only UI
* don’t autoplay; remember volume + playback speed per user; respect reduced-motion
* “low distraction mode” toggle that hides feed list + metadata and leaves just the player + next/prev

[1]: https://www.podbean.com/podcast-detail/aucu4-4576e/The-Porch-%28Video%29-Podcast?utm_source=chatgpt.com "The Porch (Video) Podcast | Free Listening on Podbean App"
[2]: https://www.podbean.com/podcast-detail/u4wrq-232960/Messages-by-Desiring-God-%28Video%29-Podcast?utm_source=chatgpt.com "Messages by Desiring God (Video) Podcast | Free Listening on Podbean App"
[3]: https://podstatus.com/podcasts/battle-drill-daily-devotional-video-christian-5-mi-1078552?utm_source=chatgpt.com "Battle Drill Daily Devotional (Video) | Christian 5-Minute Bible Devotions Podcast - Rankings, Reviews - Podstatus"
[4]: https://podstatus.com/podcasts/wisdom-television-with-dr-mike-murdock-video-podca-119380?utm_source=chatgpt.com "Wisdom Television With Dr. Mike Murdock (Video) Podcast Podcast - Rankings, Reviews - Podstatus"
[5]: https://podstatus.com/podcasts/the-simple-path-to-god-video-71781?utm_source=chatgpt.com "The Simple Path to God (Video) Podcast - Rankings, Reviews - Podstatus"
[6]: https://podstatus.com/podcasts/tung-fook-church-154119?utm_source=chatgpt.com "同福堂 視聽版講道重溫 Tung Fook Church Podcast - Rankings, Reviews - Podstatus"
[7]: https://podstatus.com/podcasts/church-of-the-highlands-sunday-messages-video-396170 "Church of the Highlands - Sunday Messages - Video Podcast - Rankings, Reviews - Podstatus
"
[8]: https://podstatus.com/podcasts/hpumc-sanctuary-sermons-traditional-worship-438688 "HPUMC - Sanctuary Sermons (Traditional Worship) Podcast - Rankings, Reviews - Podstatus
"
[9]: https://podstatus.com/podcasts/all-souls-sunday-sermons-177319 "All Souls Sunday Sermons Podcast - Rankings, Reviews - Podstatus
"
[10]: https://gist.github.com/eteubert/5986525?permalink_comment_id=4536668&utm_source=chatgpt.com "List of Podcast RSS Feeds, extracted via iTunes API · GitHub"

### assistant

Updated the README TODO section with:

1. **Priority: real page content** — Logged the 404 vs dedicated landing-page decision for later.
2. **Site identity** — All three title/subtitle/description options plus the `user_agent` change.
3. **New feeds** — The 19 feeds listed as a single TODO (grouped by source).
4. **Discoverability + accessibility** — The full shortlist as separate checkboxes.

The full feed markdown blocks are not in the README; they’re in your message for when you implement the feeds TODO.

### you

I forgot there were new feeds in there... Check these feeds and for the actve ones with video enclosures, include in our church.md....

## watermark-porch-video
- url: https://media.watermark.org/podcasts/porch-video.xml
- title: The Porch (Video) — Watermark Community Church
- category: sermons
- tags: sermons, young-adults, teaching, weekly, dallas

## desiring-god-messages-video
- url: http://feed.desiringgod.org/messages-by-desiring-god-video.rss
- title: Messages by Desiring God (Video)
- category: teaching
- tags: sermons, preaching, conference, reformed, weekly

## ancient-faith-simple-path-video
- url: http://feeds.ancientfaith.com/SimplePathToGodVideo/
- title: The Simple Path to God (Video) — Ancient Faith
- category: teaching
- tags: orthodox, teaching, catechesis, practical, weekly

## wisdom-television-murdock-video
- url: https://feed.podbean.com/wisdomonline/feed.xml
- title: Wisdom Television (Video) — Dr. Mike Murdock
- category: tv-ministry
- tags: tv-ministry, teaching, daily, talk

## battle-drill-daily-devotional-video
- url: https://api.substack.com/feed/podcast/5786250.rss
- title: Battle Drill Daily Devotional (Video)
- category: devotional
- tags: devotional, bible-reading, daily, short-form

## tung-fook-cbc-video
- url: http://share.tungfook.com/tungfook/podcasts/cbc/video/video.xml
- title: Tung Fook Chuen Kee Church — CBC (Video)
- category: sermons
- tags: sermons, hong-kong, chinese, weekly

## church-of-the-highlands-weekend-video
- url: https://feeds.churchofthehighlands.com/media/weekend/video
- title: Church of the Highlands — Weekend Service (Video)
- category: sermons
- tags: sermons, weekend, multi-site, alabama, weekly

## hpumc-sanctuary-videocast
- url: http://feeds2.feedburner.com/HpumcSanctuaryServiceVideocast
- title: Highland Park UMC — Sanctuary Service (Videocast)
- category: sermons
- tags: sermons, methodist, liturgy, weekly, dallas

## all-souls-sundays
- url: http://feeds.feedburner.com/AllSoulsChurchSundays
- title: All Souls Church — Sundays (Video)
- category: sermons
- tags: sermons, anglican, uk, weekly, london

## sermontv-calvarylighthouse-video
- url: http://CalvaryLighthouse.sermon.tv/rss/main/video
- title: Calvary Lighthouse (Sermon.tv) — Main (Video)
- category: sermons
- tags: sermons, sermontv, church, weekly

## sermontv-ccfhkingwood-video
- url: http://CCFHKingwood.sermon.tv/rss/main/video
- title: CCFH Kingwood (Sermon.tv) — Main (Video)
- category: sermons
- tags: sermons, sermontv, church, weekly, texas

## sermontv-communitychurchtv-video
- url: http://CommunityChurchTV.sermon.tv/rss/main/video
- title: CommunityChurchTV (Sermon.tv) — Main (Video)
- category: sermons
- tags: sermons, sermontv, church, weekly

## sermontv-genoaunitedbaptistchurch-video
- url: http://GenoaUnitedBaptistChurch.sermon.tv/rss/main/video
- title: Genoa United Baptist Church (Sermon.tv) — Main (Video)
- category: sermons
- tags: sermons, baptist, sermontv, weekly

## sermontv-lbcwylie-video
- url: http://LBCWylieTX.sermon.tv/rss/main/video
- title: LBC Wylie TX (Sermon.tv) — Main (Video)
- category: sermons
- tags: sermons, baptist, sermontv, weekly, texas

## sermontv-ncfstillwaterok-video
- url: http://NCFStillwaterOK.sermon.tv/rss/main/video
- title: NCF Stillwater OK (Sermon.tv) — Main (Video)
- category: sermons
- tags: sermons, sermontv, weekly, oklahoma

## sermontv-thenetrev-video
- url: http://TheNetRev.sermon.tv/rss/main/video
- title: TheNetRev (Sermon.tv) — Main (Video)
- category: sermons
- tags: sermons, sermontv, weekly

## sermontv-apostolicclassics-video
- url: http://apostolicclassics.sermon.tv/rss/main/video
- title: Apostolic Classics (Sermon.tv) — Main (Video)
- category: teaching
- tags: teaching, sermontv, archives, classic, weekly

## sermontv-drumley-video
- url: http://drumley.sermon.tv/rss/main/video
- title: Drumley (Sermon.tv) — Main (Video)
- category: sermons
- tags: sermons, sermontv, weekly

### assistant

Adding the four active feeds with video enclosures to `church.md`:

### assistant

Added 4 feeds to `church.md`:

| Feed | Status |
|------|--------|
| **watermark-porch-video** | ✓ Added (video/x-m4v) |
| **desiring-god-messages-video** | ✓ Added (video/mp4) |
| **wisdom-television-murdock-video** | ✓ Added (video/mp4) |
| **church-of-the-highlands-weekend-video** | ✓ Added (video enclosures) |

**Not added:**
- **ancient-faith-simple-path-video** — 0 items
- **battle-drill-daily-devotional-video** — 0 items (Substack feed)
- **tung-fook-cbc-video** — 0 items
- **hpumc-sanctuary-videocast** — audio only (mp3)
- **all-souls-sundays** — no video enclosures
- **sermontv-*** (all 9) — "Studio not found"

### you

also I told you to add those other earlier ones.... that do NOT 404. Remove the placeholder and ADD entries only for the video based feeds that do not 404.


## elevation-church
- url: https://elevationchurch.org/feed/podcast/video
- title: Elevation Church
- category: sermons
- tags: sermons, contemporary, north-carolina, steven-furtick, worship, concert, live-music

## hillsong-church
- url: https://hillsong.com/collected/all/blogs/category/blogs/feed
- title: Hillsong Church
- category: sermons
- tags: sermons, worship, australia, brian-houston, global, concert, live-music

## bethel-church
- url: https://www.bethel.com/podcasts/rss
- title: Bethel Church
- category: sermons
- tags: sermons, charismatic, california, bill-johnson, healing, worship, concert, live-music

## lakewood-church
- url: https://www.lakewoodchurch.com/podcasts/video
- title: Lakewood Church
- category: tv-ministry
- tags: tv-ministry, prosperity, joel-osteen, texas, encouragement, sunday

## saddleback-church
- url: https://saddleback.com/podcasts/video
- title: Saddleback Church
- category: sermons
- tags: sermons, practical-living, rick-warren, california, multi-site, concert, live-music

## gateway-church
- url: https://gatewaypeople.com/podcasts/rss
- title: Gateway Church
- category: sermons
- tags: sermons, texas, robert-morris, multi-site, bible-teaching, sunday

## life-church
- url: https://openblog.life.church/feed/
- title: Life.Church
- category: sermons
- tags: sermons, craig-groeschel, oklahoma, multi-site, practical, concert, live-music

## passion-city
- url: https://passioncitychurch.com/podcasts/video/rss
- title: Passion City Church
- category: sermons
- tags: sermons, louie-giglio, georgia, worship, young-adults, concert, live-music

## village-church
- url: https://www.thevillagechurch.net/resources/sermons/rss
- title: The Village Church
- category: sermons
- tags: sermons, matt-chandler, texas, expositional, reformed, sunday

## north-point
- url: https://northpoint.org/messages/rss
- title: North Point Ministries
- category: sermons
- tags: sermons, andy-stanley, georgia, practical-living, multi-site, sunday

## desiring-god
- url: https://www.desiringgod.org/messages/rss
- title: Desiring God
- category: bible-study
- tags: bible-study, john-piper, reformed, minnesota, theology, teaching

## gospel-coalition
- url: https://www.thegospelcoalition.org/podcasts/rss
- title: The Gospel Coalition
- category: teaching
- tags: teaching, reformed, conferences, multi-source, theology

## andrew-wommack
- url: https://www.awmi.net/video/tv-archives/rss
- title: Andrew Wommack Ministries
- category: tv-ministry
- tags: tv-ministry, faith-teaching, grace, colorado, daily

## amazing-facts
- url: https://www.amazingfacts.org/media-library/podcasts/rss
- title: Amazing Facts
- category: bible-study
- tags: bible-study, doug-batchelor, sabbath, california, prophecy

## in-touch
- url: https://www.intouch.org/broadcast/video-archives/rss
- title: In Touch Ministries
- category: tv-ministry
- tags: tv-ministry, charles-stanley, georgia, teaching, daily

## bible-project
- url: https://bibleproject.com/podcasts/rss
- title: Bible Project
- category: bible-study
- tags: bible-study, animated, theology, oregon, series

## bible-recap
- url: https://www.thebiblerecap.com/podcast/rss
- title: The Bible Recap
- category: bible-study
- tags: bible-study, through-the-bible, daily, tara-leigh-cobble

## through-the-word
- url: https://throughtheword.org/podcasts/rss
- title: Through the Word
- category: bible-study
- tags: bible-study, audio-guide, chapter-by-chapter, california

## james-river-church
- url: https://feed.podbean.com/jamesriverchurch/feed.xml
- title: James River Church Podcast
- category: sermons
- tags: sermons, john-lindell, missouri, pentecostal, sunday, concert, live-music

## church-leaders
- url: https://churchleaders.libsyn.com/rss
- title: ChurchLeaders Podcast
- category: ministry
- tags: ministry, leadership, interviews, pastors, practical

### assistant

Verifying: none of the earlier feeds return valid RSS with video enclosures. Removing the placeholder comment.

### assistant

Placeholder comment is removed.

From the earlier list, **none** of the feeds meet both “no 404” and “video enclosures”:

| Feed | Status |
|------|--------|
| elevation | 429 + Vercel checkpoint → HTML |
| hillsong | 200, 0 items (blog feed) |
| bethel | 404 |
| lakewood | 200, HTML not-found |
| saddleback | 404 |
| gateway | 404 |
| life-church | 200, blog only, no video |
| passion-city | 200, empty RSS |
| village-church | 200, 0 items |
| northpoint | 200, 0 items |
| desiring-god | 403 |
| gospel-coalition | 403 |
| andrew-wommack | 200, 0 items |
| amazing-facts | 404 |
| in-touch | 200, 0 items |
| bible-project | 202, 0 items |
| bible-recap | 404 |
| through-the-word | 200, 0 items |
| james-river-church | Audio only (we already have james-river video) |
| church-leaders | 200, no video enclosures |

So nothing from that list was added. The four feeds added earlier (watermark-porch-video, desiring-god-messages-video, wisdom-television-murdock-video, church-of-the-highlands-weekend-video) remain.

### you

try these ones next....

I think they're mostly dead, but try them all anyway. Then look for more...

Below are confirmed video RSS feeds that match your format (true RSS/vodcast feeds with video enclosures). I stayed inside your scope: sermons/services/teaching or equivalent, and deliberately widened geography + traditions (African, Black diaspora, Asian, non-Christian).

I grouped by region/tradition so you can slot them into your taxonomy easily.

---

## African & Black-majority churches (video RSS)

**Redeemed Christian Church of God (RCCG) — UK / Nigeria diaspora**
[https://podcasts.subsplash.com/61y4yq7/podcast.rss](https://podcasts.subsplash.com/61y4yq7/podcast.rss)
(video sermons; Subsplash vodcast)

**Christ Embassy — Nigeria (global)**
[https://christembassyhouston.org/podcast/video.xml](https://christembassyhouston.org/podcast/video.xml)
(video sermons & services)

**Winners Chapel International (Living Faith Church)**
[https://lfcdallas.org/podcast/video.xml](https://lfcdallas.org/podcast/video.xml)
(video sermons; Nigerian Pentecostal megachurch network)

**Omega Fire Ministries — Nigeria**
[https://podpoint.com/feed/7017](https://podpoint.com/feed/7017)
(video sermons)

**Daystar Christian Centre — Nigeria**
[https://podcasts.subsplash.com/9vt4qk8/podcast.rss](https://podcasts.subsplash.com/9vt4qk8/podcast.rss)
(video sermons)

These all publish vodcasts with `<enclosure type="video/...">` and current items.

---

## Black churches (US/UK diaspora but culturally distinct)

**The Potter’s House (T. D. Jakes)**
[https://tdjakes.org/podcast/video.xml](https://tdjakes.org/podcast/video.xml)
(video sermons)

**Mount Zion Baptist Church — Nashville (Black Baptist)**
[https://mountzionnashville.sermon.net/rss/main/video](https://mountzionnashville.sermon.net/rss/main/video)
(video sermons)

**Ruach City Church — London (Black-majority Pentecostal)**
[https://podcasts.subsplash.com/7p9c2z5/podcast.rss](https://podcasts.subsplash.com/7p9c2z5/podcast.rss)
(video services)

---

## Asian / Chinese churches (video RSS)

**Beijing Zion Church (Chinese Protestant)**
[https://zionbeijing.sermon.net/rss/main/video](https://zionbeijing.sermon.net/rss/main/video)
(video sermons; Mandarin)

**Shanghai Community Fellowship**
[https://shcf.sermon.net/rss/main/video](https://shcf.sermon.net/rss/main/video)
(video sermons; English/Chinese)

**Taipei Bread of Life Christian Church**
[https://bolcc.sermon.net/rss/main/video](https://bolcc.sermon.net/rss/main/video)
(video sermons; Mandarin megachurch)

---

## Orthodox & Eastern (non-Western Christian)

**Orthodox Church in America — Sermons (video)**
[https://feeds.ancientfaith.com/oca-sermons-video](https://feeds.ancientfaith.com/oca-sermons-video)
(video homilies)

**Greek Orthodox Archdiocese — Divine Liturgy video**
[https://goarch.sermon.net/rss/main/video](https://goarch.sermon.net/rss/main/video)
(full services)

---

## Islamic (video sermons / khutbah)

**Ahmadiyya Muslim Community — Friday Sermon (video)**
[https://www.alislam.org/rss/friday-sermon-video.xml](https://www.alislam.org/rss/friday-sermon-video.xml)
(global khutbah; multilingual video RSS)
Al-Islam publishes official RSS for sermons worldwide. ([Al Islam Online][1])

**Islam Channel — programmes (video podcast)**
[https://watch.islamchannel.tv/rss/video](https://watch.islamchannel.tv/rss/video)
(UK Muslim TV channel sermons & talks)

**East London Mosque — Khutbah video**
[https://eastlondonmosque.sermon.net/rss/main/video](https://eastlondonmosque.sermon.net/rss/main/video)
(friday sermons; UK)

---

## Sikh (video kirtan / discourses)

**Akaal Channel — Sikh TV programmes (video RSS)**
[https://www.akaalchannel.tv/rss/video](https://www.akaalchannel.tv/rss/video)
(Sikh sermons, kirtan; global Sikh TV)
Akaal Channel is a Sikh religious broadcast network. ([Wikipedia][2])

**Sikh Channel — Gurbani & discourse**
[https://www.sikhchannel.tv/rss/video](https://www.sikhchannel.tv/rss/video)
(Sikh services/lectures)

---

## Buddhist / Hindu (temple teachings — video RSS)

**Plum Village (Zen Buddhist)**
[https://plumvillage.org/feed/podcast/video](https://plumvillage.org/feed/podcast/video)
(Dharma talks; Thich Nhat Hanh tradition)

**Fo Guang Shan (Chinese Buddhist)**
[https://fgs.org/rss/video](https://fgs.org/rss/video)
(Buddhist lectures; Mandarin)

**Chinmaya Mission (Hindu Vedanta)**
[https://chinmayamission.org/rss/video](https://chinmayamission.org/rss/video)
(Upanishad/Bhagavad Gita discourses)

---

## Jewish (video sermons / teaching)

**Central Synagogue — Shabbat services (video)**
[https://centralsynagogue.sermon.net/rss/main/video](https://centralsynagogue.sermon.net/rss/main/video)
(full services)

**Temple Emanu-El — sermons (video)**
[https://emanuelnyc.sermon.net/rss/main/video](https://emanuelnyc.sermon.net/rss/main/video)
(rabbinic sermons)

---

## Notes on verification / fit

* All above feeds resolve as RSS with video enclosures (mp4/m4v).
* They’re equivalent to your existing church vodcasts (same CMS families: Subsplash, Sermon.net, Podpoint, custom vodcast XML).
* Geographic expansion: Nigeria, UK diaspora, China/Taiwan, Sikh/Buddhist/Hindu/Jewish/Islamic traditions.
* Content type: sermons, services, liturgy, khutbah, Dharma talks — directly analogous to your current categories.

Your current catalogue is overwhelmingly US evangelical; adding these broadens culture + religion without changing UX.

Your existing site positioning already says “global ministries”. 
[1]: https://www.alislam.org/podcast/?utm_source=chatgpt.com "Podcast Service"
[2]: https://en.wikipedia.org/wiki/Akaal_Channel?utm_source=chatgpt.com "Akaal Channel"


I've got these feeds in my website (it's a video/channel browser), but I'd like to find more feeds, must have video, but I want to move beyond just/mostly american christians, to also other religions, services, sermons, lessons and such, basically more of the types of content we have, but not exclusively limited to christians or american, what other feeds can you find? they must have video, and be like our feeds, rss/openrss based. I'd also like to find some black ministries, african or even chinese ones, like expand our offering from what we have to worldwide. No guessing, confirm every feed

### assistant

Adding WWIC-music-video (the only new working feed). Creating a verification summary:

### assistant

**Verification summary**

All 22 feeds from your list were checked; none are usable:

| Group | Feeds | Result |
|-------|-------|--------|
| **African/Black** | RCCG, Christ Embassy, LFC Dallas, Omega Fire, Daystar, TD Jakes, Mount Zion, Ruach | Deleted, 404, empty, or wrong feed |
| **Asian** | Beijing Zion, Shanghai, Taipei Bread of Life | 404 |
| **Orthodox** | OCA, Greek Archdiocese | 404 |
| **Islamic** | Al-Islam, Islam Channel, East London Mosque | 404 |
| **Sikh** | Akaal Channel, Sikh Channel | 404 or empty |
| **Buddhist/Hindu** | Plum Village, Fo Guang Shan, Chinmaya Mission | HTML page, 404, or redirect |
| **Jewish** | Central Synagogue, Temple Emanu-El | 404 |

**Added**

- **wwic-music-video** — Praise and Worship Music Live at Without Walls International Church (1 video item; feed is live but sparse)

**Already in church.md**

- Pray More Novenas (Catholic)
- Shiloh Bluegrass Gospel Hymns

**README**

- Added a short feed verification note for this batch.

**Search for more**

- PodcastIndex `find-video` returned no results.
- Text search surfaced mostly tech/news feeds.
- Non–US-Christian video RSS feeds are rare; most religious content is on YouTube or proprietary platforms.

### you

I'd like to find more feeds, must have video, but I want to move beyond just/mostly american christians, to also other religions, services, sermons, lessons and such, basically more of the types of content we have, but not exclusively limited to christians or american, what other feeds can you find? they must have video, and be like our feeds, rss/openrss based. I'd also like to find some black ministries, african or even chinese ones, like expand our offering from what we have to worldwide. No guessing, confirm every feed

### assistant

Summary of what was verified:

## Verified: no usable diverse video feeds

**African / Nigerian**
- Sovereign Grace Abuja (Podbean) — audio only  
- Ikoyi Baptist — 0 items  
- RCCG Fountain of Fulfillment (Subsplash) — 109 items, audio only  
- RCCG Grace Pavilion — 20 items, audio only  
- Daystar Christian Centre (Podbean) — 39 items, audio only  
- Activefaith / Pastor Tshabuse (South Africa) — audio only  
- Watoto Church (Uganda) — audio only  

**Black US**
- The Black Church Still Speaks (Castos) — audio only  
- T.D. Jakes / Potter’s House (Acast) — 57 items, audio only  

**Chinese**
- River of Life (rolcc.net) — 406 or empty  

**Islamic**
- Al-Islam Friday Sermon Video — 404  

**Buddhist**
- Dhammatalks.org — audio only  
- Plum Village — HTML page, not RSS  

**Jewish**
- Park Avenue Synagogue (Podbean) — audio only  

**Other**
- Radiant Life, Life Community, Clay Church, Refuge Church, River Oaks, VRBC — all audio only  

---

## Working video feeds (not in church.md)

These have video enclosures but are not religious:

| Feed | URL | Content |
|------|-----|---------|
| Democracy Now! Video | https://www.democracynow.org/podcast-video.xml | News |
| NutritionFacts.org Video | https://nutritionfacts.org/videos/feed/podcast/ | Health |
| UCTV Vodcasts | https://podcast.uctv.tv/uctv_vodcasts.rss | University lectures |
| Corbett Report Videos | https://www.corbettreport.com/videorss.xml | News/commentary |

They are in `feeds/tech.md` and `feeds/complete.md`, not in `church.md`.

---

## Conclusion

No new religious video RSS feeds were found that meet your criteria (video enclosures, non–US-Christian, diverse). Most religious content is either:

- Audio-only in RSS, or  
- Video on YouTube/proprietary platforms without RSS.

If you want to broaden church.md beyond sermons, the four feeds above could be added as a “teaching / education” category. Otherwise, church.md is already using the main religious video RSS feeds that are available.

### you

what's the political direction/lean on those channels, since they're not religious we need to be a little careful.

### assistant

Political/orientation summary:

| Channel | Political lean | Notes |
|--------|----------------|-------|
| **Democracy Now!** | Strong left / progressive | Independent news, grassroots activism, voices outside mainstream power. Rated left by Media Bias/Fact Check, AllSides, Ad Fontes. Generally rated high for factual accuracy. |
| **NutritionFacts.org** | Not partisan | Dr. Greger focuses on nutrition and health. Main criticism is ideological (strong pro-vegan stance and cherry-picking). Some criticism of food/pharma lobbying. Low credibility rating from Media Bias/Fact Check. |
| **The Corbett Report** | Conspiracy / alternative | Covers 9/11 conspiracies, false flags, “deep state,” COVID, central banking. Media Bias/Fact Check: “Conspiracy-Pseudoscience,” low credibility. |
| **UCTV** | Neutral / academic | UC system’s educational channel. Content spans science, health, humanities, public affairs. UC system is often seen as left-leaning, but UCTV itself is academic and not overtly partisan. |

**Recommendation for a church/prays.be site**

- **Democracy Now!** — Clearly left-leaning; could be divisive.
- **NutritionFacts.org** — Not political, but credibility is disputed.
- **The Corbett Report** — Conspiracy-oriented; high risk for a faith/ministry site.
- **UCTV** — Most neutral; science and education content, but not religious.

If you want to keep the site clearly religious and low-controversy, it’s safest to skip all four.

### you

hmm, they might fit for a large section of our audience, but I don't want to 'trigger' those who will absolutely find a few of their positions offensive. Add them to the complete.md file instead, since they are interesting, but not on this deployment

### assistant

Those feeds are already in `complete.md`:

- **democracy-now-video** (line 305)
- **nutritionfacts-org-video-podcast** (line 310)
- **uctv_*** (several entries: uctv_ucsd, uctv_all, uctv_health, uctv_berkeley, uctv_ucsf, uctv_davis)
- **the-corbett-report-videos** (line 350)

`complete.md` is the full reference set; `church.md` is the deployment config. Since they’re only in `complete.md`, they’re not part of the church deployment. No edits are needed.

### you

oh okay, I see you misunderstood what I asked... I don't want you to search my repo for new church feeds, I want you to search the web for new feeds that compliment our church feeds.

### assistant

Checking existing feeds and searching for additional video feeds:

### assistant

Searching for additional verified video feeds:

### assistant

Web search results for church video RSS feeds that complement your current set:

**Summary**

Most Christian content is distributed as **audio-only** RSS. Video is usually on YouTube or proprietary apps (Subsplash, Planning Center, etc.), not in RSS.

**Checked and not suitable**

| Feed | Issue |
|------|--------|
| Atlanta First UMC (Rev. Jasmine Smothers) | Audio only (mp3) |
| Planetshakers | Audio only (mp3) |
| Calvary Chapel Anne Arundel | Audio only |
| Rebecca Weiss (Daystar) | Audio only (m4a) |
| Grace to You (GTY) | 404 / unreachable |
| Ligonier Renewing Your Mind | Audio only |
| Gateway Church Video | Last updated Nov 2023, no working RSS found |
| North Point, Saddleback, Willow Creek | No public video RSS found |

**Already in your church.md**

- Watermark Porch (video/x-m4v)
- Desiring God Messages Video
- Church of the Highlands Weekend Video
- Bridgetown, James River, Eagle Brook, etc.

**Conclusion**

No new, verified church video RSS feeds were found that meet your criteria (video enclosures, reachable, and complementary to your current feeds). Most churches that publish video use YouTube or their own platforms rather than video RSS.

### you

okay, write up a church-audio-only.md file. Must have episodes but does not have to be video, in fact should be audio, expliticly without video. Try and exhaust the sector for what's available. Try and find old archives of local talk/regional radio, that kind of thing too, americana and christiania.

### assistant

Created `feeds/church-audio-only.md` with **23 verified audio-only feeds**:

**Christian teaching & sermons**
- Desiring God (Messages, Ask Pastor John, Solid Joys, Light + Truth)
- Truth for Life — Alistair Begg (daily + sermons)
- Preach the Word — David Legge
- Focus on the Family, Greg Laurie, In Touch (Charles Stanley)
- White Horse Inn, Moody Radio Special Programs
- Revived Thoughts (Spurgeon, Moody, Calvin)
- Atlanta First UMC (Rev. Jasmine Smothers), Buford Road Baptist
- Adventures in Odyssey (family audio drama)

**Catholic**
- Sermons for Everyday Living — Station of the Cross (iCatholicRadio)

**Americana & roots**
- Big Fat Wide Americana Hour (Podbean)
- American Grooves Radio Hour — Joe Lauro (pre‑WWII 78s jazz/blues/gospel)
- Southern Gospel News Podcast

**Old-time radio & archives**
- The Old-Time Radio Hour (Podbean)
- Radio Survivor (radio history/preservation)

**NPR**
- NPR News Now (headlines)

Build tested with `--feeds feeds/church-audio-only.md`; all feeds fetched and built. The `# Feeds` heading must be exactly `# Feeds` (no extra text) for the parser to work.

### you

23 isn't many... can you do better, add more?

### assistant

Expanded `church-audio-only.md` from 23 to **42 feeds**:

**New Christian teaching & sermons**
- Bible in a Year — Fr. Mike Schmitz (Catholic)
- The Briefing — Albert Mohler
- Life.Church with Craig Groeschel
- Elevation with Steven Furtick
- James River Church (audio)
- BibleProject Podcast
- The Ten Minute Bible Hour — Matt Whitman
- Reformation Baptist Church — Wetumpka
- Watts Chapel Missionary Baptist (Black church, NC)
- Pastor Jonathan's Sermons
- MRC Sermons — Midland Reformed Church
- Fresh Life Church
- Calvary Chapel Anne Arundel
- Living on the Edge — Chip Ingram

**Orthodox**
- All Saints Homilies — Ancient Faith
- 3 Men and a Bible — Ancient Faith

**Ligonier**
- Ultimately — R.C. Sproul (short daily)

**Public radio**
- Wait Wait... Don't Tell Me!
- This American Life

Build completed successfully with all 42 feeds.
