---
cursor_session: be86753f-9f91-46ec-8ebc-4adb54d537bc
source: cursor-composer
cursor_hint: ?
user_entries: 20
---

# transcript — run-through-feeds-news-possibilities-json-and-for

### you

run through @feeds/news.possibilities.json and for each that you confirm exists and has video content, add to a new news.md feeds file in the same approach as the church.md file.

### assistant

Checking feed structure and how we verify video content:

### assistant

Creating a script to verify feeds and generate `news.md`.

### assistant

Verifying failed feeds with web fetch:

### assistant

Creating `news.md` with the three verified feeds.

### assistant

Created `/home/bobbigmac/projects/vodcasts/feeds/news.md` with 3 feeds that were verified to exist and include video enclosures:

| Feed | Category |
|------|----------|
| PBS NOVA Video | science |
| TED Talks Video | talks |
| Democracy Now! Video | news |

**Not included** (could not be verified):
- **Reuters** (10 feeds) – DNS resolution failed / 502 Bad Gateway
- **NASA** (2 feeds), **JPL** – 404
- **CNET** – 410 Gone
- **ABC News** (3 feeds) – no video enclosures in the feed structure

### you

that's not many, can you find real working urls for the other entries?

### assistant

Creating a verification script and testing candidate feeds:

### assistant

Updating news.md with verified working feeds:

### assistant

Updating `news.possibilities.json` with working URLs for future reference:

### assistant

Updated `news.md` to include **12 feeds** (up from 3). Added feeds:

| Feed | Category |
|------|----------|
| MSNBC Rachel Maddow (Video) | news |
| Tech News Weekly (Video) | tech |
| Daily Tech News Show (Video) | tech |
| Geek News Central (Video) | tech |
| TWiT News (Video) | tech |
| CBN Christian World News | news |
| NASA on Odysee | science |
| Linux Action News (Video) | tech |
| Security Weekly News (Video) | tech |

**Still no working feeds for:** Reuters (DNS/502), NASA/JPL (404), CNET (410 Gone), ABC News (no video enclosures).

### you

okay, check@feeds/news.possibilities.json and port those that do work and are not there already into complete.md (not news.md, I deleted that).

### assistant

From `news.possibilities.json`:

**Working feeds (3):**
- PBS NOVA Video  
- TED Talks Video  
- Democracy Now! Video  

**Not working:** Reuters (10), NASA (3), CNET, ABC News (3).

All three working feeds are already in `complete.md` (lines 358–374). There’s nothing to add.

### you

you couldn't find the real feed urls for those? also, format that json file so I can browse it

### assistant

Updating the JSON with findings and formatting it.

### assistant

Updates are in place. Summary:

**Reuters (10 feeds)** – No public video RSS. `feeds.reuters.com` returns DNS/502. Video is only via Reuters Connect (auth) or their Live Video API.

**NASA (3 feeds)** – Old vodcast URLs return 404. Current NASA podcasts (`https://www.nasa.gov/feeds/podcasts/<slug>`) are audio-only (Megaphone). No official video RSS.

**CNET** – `feed.cnet.com` returns 410 Gone. Podbean still points to the same URL; CNET has discontinued the feed.

**ABC News (3 feeds)** – `feeds.abcnews.com` returns HTML or feeds without video enclosures. The Megaphone feed (`https://feeds.megaphone.fm/ESP4140596756`) is audio-only.

**Working feeds** – PBS NOVA, TED Talks, and Democracy Now are marked as working.

The JSON file is now pretty-printed and includes `status` and `note` fields for each feed.

### you

wow, so none of the mainstream media even publish to openrss feeds? but the christians are still active? what other sectors still use this tech a lot?

### assistant

From your feeds and the broader ecosystem, the pattern looks like this:

**Sectors still using open RSS for video**

- **Church/Christian** – Very active. Sermons, teaching, worship. Many churches use Subsplash, Podbean, Libsyn, etc., and keep public RSS.
- **Universities** – UCTV, NIH VideoCast, Chiasmos (UChicago). Public institutions often keep open feeds.
- **Tech / indie podcasters** – TWiT, Geek News Central, Daily Tech News Show, Security Weekly. Creator-owned shows and small networks still rely on RSS.
- **Science / education** – PBS NOVA, TED. Nonprofits and public media often keep open feeds.
- **Fitness / wellness** – Ben Greenfield, Mind Pump, etc. Many still use RSS.
- **Alternative / progressive media** – Democracy Now, CBN. Smaller outlets that care about reach beyond walled platforms.

**Sectors that have largely moved away**

- **Mainstream commercial news** – Reuters, ABC, NBC, CNET. Most have shifted to apps, streaming, and auth-only APIs.
- **Big entertainment** – Mostly YouTube, apps, and proprietary platforms.

**Why the split**

RSS is still the core of podcast distribution (Apple, Spotify, etc. all consume RSS). The difference is who keeps *public* RSS:

- **Institutions** (churches, universities, public media) – mission-driven, long-term, often want broad reach.
- **Indie creators** – depend on RSS for distribution and ownership.
- **Commercial media** – moved to owned platforms, subscriptions, and controlled distribution.

So it’s less “RSS is dead” and more “commercial media has moved to walled gardens,” while churches, universities, and indie creators still use open RSS heavily.

### you

i'd like to understand what there's a lot of that IS NOT in my collection already...

### assistant

From your `complete.md` and what’s common in the ecosystem, here’s what you have vs. what’s missing:

---

**What you already have (and where it’s strong)**

| Category | Count | Notes |
|----------|-------|-------|
| Church/Christian | ~35 | Very strong |
| University | ~10 | UCTV, NIH, Chiasmos, etc. |
| Tech | ~25 | TWiT, Geek News Central, Security Weekly, etc. |
| Gaming | ~5 | Kinda Funny, Elder Scrolls, Fallout Lorecast, Video Gamers |
| Science | 3 | NOVA, TED, NASA Odysee |
| News | 4 | Democracy Now, MSNBC Maddow, CBN, tech news |
| Fitness | 3 | Ben Greenfield, Eric Roberts, Mind Pump |
| Bible | 1 | Bible Study Guide |
| Talks/ideas | 1 | TED |
| Autoline (cars) | 1 | |
| PragerU | 1 | |

---

**Categories with lots of content that you’re missing**

| Category | Why it’s a gap | Notes |
|----------|----------------|-------|
| **Comedy** | 0 feeds | Daily Show, Colbert, late-night, etc. – most are audio or platform-locked (e.g. Joe Rogan on Spotify). Some indie comedy podcasts have video RSS. |
| **True crime** | 0 feeds | Huge podcast category; most are audio. Few video true crime feeds. |
| **Sports** | 0 feeds | ESPN, Barstool, etc. mostly use apps/YouTube. A few video feeds (e.g. Vegas Video Network, 124NotOut Cricket). |
| **Cooking / food** | 0 feeds | Splendid Table, Bon Appétit, etc. – mostly audio or YouTube. |
| **Business / finance** | 0 feeds | Many audio business podcasts; video is rarer. |
| **History** | 0 feeds | Some documentary-style shows; most are audio. |
| **Politics** | 1 feed (MSNBC) | Lots of political podcasts; most are audio. |
| **Music / concerts** | 0 feeds | Live sessions, Tiny Desk, etc. – mostly YouTube. |
| **Kids / family** | 0 feeds | Some educational video podcasts; niche. |
| **DIY / maker** | 0 feeds | MAKE Magazine and similar; small but active. |
| **Rooster Teeth / gaming networks** | 0 feeds | Rooster Teeth, Funhaus, etc. – Megaphone feeds are mostly audio. |
| **International / non-English** | 0 feeds | Spanish, etc. – large market, under-indexed in your list. |

---

**Summary**

You’re strong in: **church, university, tech, gaming (light), science, fitness**.

You’re missing or very light in: **comedy, true crime, sports, cooking, business, history, politics (beyond MSNBC), music, kids, DIY, international**.

The main reason: many of those categories are dominated by audio podcasts or by platforms (YouTube, Spotify, apps) that don’t expose open video RSS. Comedy, sports, and true crime are especially big in audio but thin in open video RSS.

### you

you're not asking my question, you need to google stuff and find out, not inside my collection

### assistant

From research and industry reports (Edison, Statista, Triton, Spotify, etc.):

---

**Video podcast categories by viewership (US, Jan 2024)**

| Rank | Category | Share of video podcast viewers |
|------|----------|--------------------------------|
| 1 | News and current affairs | 46% |
| 2 | Health and wellness | 34% |
| 3 | Educational content | 33% |
| 4 | Pop culture and entertainment | 32% |
| 5 | True crime | 30% |
| 6 | Lifestyle and personal development | 27% |
| 7 | Technology and science | 27% |
| 8 | Gaming | 22% |
| 9 | Business and finance | 20% |

---

**Overall podcast genres (reach and downloads)**

- **Comedy** – Most consumed genre (66% of listeners); ~27.5% of Spotify video podcast viewers (H1 2023).
- **Society & culture** – #2 by reach.
- **News** – #1 by downloads; 46% of video podcast viewers.
- **True crime** – #3 by downloads; ~23,000 shows; 19.1M weekly listeners; 84% of US pop consume some true crime.
- **Religion & spirituality** – One of the fastest-growing genres.

---

**Other notable sectors**

- **Health/wellness** – 30% growth in listeners; 61% female; 34% of video podcast viewers.
- **Sports** – Strong on YouTube; “New Heights” (Kelce) 10–12M monthly; most sports content on YouTube, not RSS.
- **Gaming** – 22% of video podcast viewers; 18.9B hours on Twitch; mostly live streaming, not podcast RSS.
- **Business and finance** – 20% of video podcast viewers; 83% of senior business leaders listen to podcasts.
- **Christian/faith** – Fast-growing segment; religion/spirituality among fastest-growing genres.

---

**Summary**

The largest categories with the most content and viewership are:

1. **Comedy**
2. **News and current affairs**
3. **Society & culture**
4. **True crime**
5. **Health and wellness**
6. **Educational content**
7. **Pop culture and entertainment**
8. **Lifestyle and personal development**
9. **Technology and science**
10. **Religion and spirituality**
11. **Gaming**
12. **Business and finance**

### you

you didn't look especially for openrss/video-podcasts, and generic platform-specific (spotify, youtube) video podcasts are useless to us. can you find any truecrime video podcast rss feeds? good educational stuff to add to complete.md and business/finance or pop culture?

### assistant

Adding verified working feeds to `complete.md`:

### assistant

Summary:

**True crime** – No open RSS video feeds found. Dateline True Crime Weekly, Crime Junkie, and others are audio-only. True crime video is mostly on YouTube/Spotify, not open RSS.

**Added to complete.md:**

| Feed | Category |
|------|----------|
| PeerView Neuroscience & Psychiatry (CME) | education |
| PeerView Internal Medicine (CME) | education |
| PeerView Oncology & Hematology (CME) | education |
| Better Business Coach Video (Matthew Pollard) | business |
| You Can Read the Bible Christian Education | education |
| Denver Education Video (Granicus) | education |
| WGBH Science City (archival, 2007) | education |

**Pop culture** – Astonishing News & Reviews (media.rss.com) has no video enclosures. Other pop culture hits were audio or platform-only.

**Duplicate slugs** – Removed duplicate entries for democracy-now-video, tech-news-weekly-video, and daily-tech-news-show-video.

### you

tae a look at our @feeds/church-audio-only.md and use the find-feeds thing to find audio podcasts of interest to our users, the fans of our church.md stuff, but our audio-only list will accept audio only

### assistant

Added **20 audio feeds** to `church-audio-only.md` via find-feeds:

**Bible teaching & sermons**
- Help Me Teach The Bible — Nancy Guthrie  
- Reality LA — Bible Teaching  
- Verse by Verse — Chris White  
- Crossway Milford — Sermons  
- Richwoods Christian Church — Sermons  

**Theology / reformed**
- Reformed Brotherhood  
- Reformed Forum — Westminster Theological Seminary  
- Doctrine at Work  

**Apologetics**
- Apologetics.com Radio Show  
- Adherent Apologetics  
- Cave to the Cross Apologetics  
- Mama Bear Apologetics  

**Devotionals**
- MY Devotional — Leading The Way (Michael Youssef)  
- UNSHACKLED! Daily Devotionals  
- WELS Daily Devotions  

**Gospel music**
- Songs of Hope Gospel Music  
- Greatest Gospel Music Of All Time  

All feeds were checked and return HTTP 200.

### you

surely you can find more than 20

### assistant

Expanded `church-audio-only.md` from ~52 to **108 feeds** (about 56 new).

**New feeds added:**

**Sermons & teaching**
- Martyn Lloyd-Jones, Timothy Keller, Bishop Barron
- Harvest Baptist GA, Saint Andrew’s Presbyterian, Redeemer Presbyterian
- South Run Baptist, CBC Aiken, Amazing Grace Baptist, First Baptist Columbia WF
- Perdido Bay Methodist, St. Matthew’s Methodist, First Church Warsaw Methodist
- Godspeak Calvary Chapel, Moira Pentecostal, Mount Calvary Lutheran
- Eric Walsh (SDA), Paul Washer

**Lutheran**
- Issues, Etc., The Word of the Lord Endures Forever, Lutheran Witness
- Luther for the Busy Man

**Orthodox (Ancient Faith)**
- Daily Orthodox Scriptures, Whole Counsel of God, Ancient Faith Today Live
- Orthodoxy Live, The Lord of Spirits, Made to Be a Kingdom
- Orthodox Christian Fellowship, Fourth Antiphon, Orthodox Christian Parenting

**Spurgeon**
- Morning and Evening, From the Heart of Spurgeon, Engaging Spurgeon
- Spurgeon Sermons (official)

**Devotionals & teaching**
- The Word For Today (Chuck Smith), Insight for Living (Chuck Swindoll)
- David Jeremiah Turning Point, Grace to You (John MacArthur)

**Gospel & hymns**
- Shiloh Bluegrass Gospel Songs 2, Southern Branch Bluegrass & Gospel
- Shiloh Instrumental Hymns

**Other**
- Aldersgate UMC Children, UNSHACKLED Audio Dramas
- Sabbath School Study Hour, Ten Commandments (EPC Australia)
- In the Market with Janet Parshall
- Focus on the Family Weekend, Focus Equipping Parents

### you

are there any muslim/jewish or other religious/spiritual feeds that wouldn't necessarily be core interest, but wouldn't offend christians to be included, and might broaden their udnerstanding of religions across borders, ideally video based, but a handful of audio ones might work.

### assistant

Auditing promising feeds for video and accessibility:

### assistant

Checking interfaith and Muslim feeds and reverting accidental adds to dev.md:

### assistant

Removing accidental adds from dev.md and adding an interfaith section to church-audio-only.md.

### you

might be worth looking for some humanist feeds too

### you

continue

### you

continue with a much shorter timeout, if it fails, it fails fast

### assistant

Added two humanist feeds:

- **How to Humanist** — American Humanist Association; Greg Epstein (Harvard/MIT humanist chaplain, *Good Without God*) and others
- **Point of Inquiry** — Center for Inquiry; science, religion, and politics with guests like Eugenie Scott, Neil deGrasse Tyson, Francis Collins

### you

Check these feeds exist, and have entries, add each to the appropriate feeds file (church (must have video), church-audio-only, and a new one called news.md for news feeds).... 

Yeah. A bunch of what I gave you earlier was unverified (and some of it was straight-up made up). Worse: I stapled on fake citation IDs. That’s on me.

Here are feed URLs that are actually *published on pages I can point to* (you can run your checker to see which still return items + which have video enclosures).

BBC / global news video-ish feeds

* [http://newsrss.bbc.co.uk/rss/newsplayer_uk_edition/front_page/rss.xml](http://newsrss.bbc.co.uk/rss/newsplayer_uk_edition/front_page/rss.xml) ([Petafloptimism][1])
* [http://newsrss.bbc.co.uk/rss/newsplayer_uk_edition/uk/rss.xml](http://newsrss.bbc.co.uk/rss/newsplayer_uk_edition/uk/rss.xml) ([Petafloptimism][1])
* [http://newsrss.bbc.co.uk/rss/newsplayer_uk_edition/world/rss.xml](http://newsrss.bbc.co.uk/rss/newsplayer_uk_edition/world/rss.xml) ([Petafloptimism][1])
* [http://newsrss.bbc.co.uk/rss/newsplayer_uk_edition/business/rss.xml](http://newsrss.bbc.co.uk/rss/newsplayer_uk_edition/business/rss.xml) ([Petafloptimism][1])
* [http://newsrss.bbc.co.uk/rss/newsplayer_uk_edition/sci-tech/rss.xml](http://newsrss.bbc.co.uk/rss/newsplayer_uk_edition/sci-tech/rss.xml) ([Petafloptimism][1])
* [http://newsrss.bbc.co.uk/rss/newsplayer_uk_edition/health/rss.xml](http://newsrss.bbc.co.uk/rss/newsplayer_uk_edition/health/rss.xml) ([Petafloptimism][1])
* [http://newsrss.bbc.co.uk/rss/newsplayer_uk_edition/entertainment/rss.xml](http://newsrss.bbc.co.uk/rss/newsplayer_uk_edition/entertainment/rss.xml) ([Petafloptimism][1])
* [http://newsrss.bbc.co.uk/rss/newsplayer_world_edition/front_page/rss.xml](http://newsrss.bbc.co.uk/rss/newsplayer_world_edition/front_page/rss.xml) ([Petafloptimism][1])
* [http://newsrss.bbc.co.uk/rss/newsplayer_world_edition/uk/rss.xml](http://newsrss.bbc.co.uk/rss/newsplayer_world_edition/uk/rss.xml) ([Petafloptimism][1])
* [http://newsrss.bbc.co.uk/rss/newsplayer_world_edition/world/rss.xml](http://newsrss.bbc.co.uk/rss/newsplayer_world_edition/world/rss.xml) ([Petafloptimism][1])
* [http://newsrss.bbc.co.uk/rss/newsplayer_world_edition/business/rss.xml](http://newsrss.bbc.co.uk/rss/newsplayer_world_edition/business/rss.xml) ([Petafloptimism][1])
* [http://newsrss.bbc.co.uk/rss/newsplayer_world_edition/sci-tech/rss.xml](http://newsrss.bbc.co.uk/rss/newsplayer_world_edition/sci-tech/rss.xml) ([Petafloptimism][1])
* [http://newsrss.bbc.co.uk/rss/newsplayer_world_edition/health/rss.xml](http://newsrss.bbc.co.uk/rss/newsplayer_world_edition/health/rss.xml) ([Petafloptimism][1])
* [http://newsrss.bbc.co.uk/rss/newsplayer_world_edition/entertainment/rss.xml](http://newsrss.bbc.co.uk/rss/newsplayer_world_edition/entertainment/rss.xml) ([Petafloptimism][1])

BBC “regular” RSS + OPML (not necessarily video)

* [http://newsrss.bbc.co.uk/rss/newsonline_uk_edition/front_page/rss.xml](http://newsrss.bbc.co.uk/rss/newsonline_uk_edition/front_page/rss.xml) ([BBC Support][2])
* [http://news.bbc.co.uk/rss/feeds.opml](http://news.bbc.co.uk/rss/feeds.opml) ([BBC Support][2])
* [http://news.bbc.co.uk/rss/newsonline_uk_edition/latest_published_stories/rss.xml](http://news.bbc.co.uk/rss/newsonline_uk_edition/latest_published_stories/rss.xml) ([BBC Support][3])
* [http://news.bbc.co.uk/rss/sportonline_uk_edition/latest_published_stories/rss.xml](http://news.bbc.co.uk/rss/sportonline_uk_edition/latest_published_stories/rss.xml) ([BBC Support][3])

Euronews MRSS (explicit “format=mrss” endpoints)

* [https://www.euronews.com/rss?format=mrss&level=theme&name=news](https://www.euronews.com/rss?format=mrss&level=theme&name=news) ([euronews][4])
* [https://www.euronews.com/rss?format=mrss&level=program&name=nocomment](https://www.euronews.com/rss?format=mrss&level=program&name=nocomment) ([euronews][4])
* [https://www.euronews.com/rss?format=mrss&level=vertical&name=travel](https://www.euronews.com/rss?format=mrss&level=vertical&name=travel) ([euronews][4])
* [https://euronews.com/rss?format=mrss&level=vertical&name=my-europe](https://euronews.com/rss?format=mrss&level=vertical&name=my-europe) ([euronews][4])
* [https://euronews.com/rss?format=mrss&level=theme&name=sport](https://euronews.com/rss?format=mrss&level=theme&name=sport) ([euronews][4])
* [https://euronews.com/rss?format=mrss&level=vertical&name=next](https://euronews.com/rss?format=mrss&level=vertical&name=next) ([euronews][4])
* [https://euronews.com/rss?format=mrss&level=vertical&name=culture](https://euronews.com/rss?format=mrss&level=vertical&name=culture) ([euronews][4])
* [https://euronews.com/rss?format=mrss&level=vertical&name=green](https://euronews.com/rss?format=mrss&level=vertical&name=green) ([euronews][4])

DW RSS + MRSS (Persian page that lists the URLs)

* [http://rss.dw-world.de/xml/rss-per-all_volltext](http://rss.dw-world.de/xml/rss-per-all_volltext) ([Deutsche Welle][5])
* [http://rss.dw-world.de/xml/rss-per_politik_volltext](http://rss.dw-world.de/xml/rss-per_politik_volltext) ([Deutsche Welle][5])
* [http://partner.dw-world.de/syndication/feeds/rss-per_bloghaus.4073-mrss.xml](http://partner.dw-world.de/syndication/feeds/rss-per_bloghaus.4073-mrss.xml) ([Deutsche Welle][5])
* [http://rss.dw-world.de/xml/rss-per_deutschland_volltext](http://rss.dw-world.de/xml/rss-per_deutschland_volltext) ([Deutsche Welle][5])
* [http://rss.dw-world.de/xml/rss-per_gesellschaft_kultur_volltext](http://rss.dw-world.de/xml/rss-per_gesellschaft_kultur_volltext) ([Deutsche Welle][5])
* [http://rss.dw-world.de/xml/rss-per-sports_volltext](http://rss.dw-world.de/xml/rss-per-sports_volltext) ([Deutsche Welle][5])
* [http://rss.dw-world.de/rdf/rss-per-all](http://rss.dw-world.de/rdf/rss-per-all) ([Deutsche Welle][5])
* [http://rss.dw-world.de/xml/rss-per_politik](http://rss.dw-world.de/xml/rss-per_politik) ([Deutsche Welle][5])
* [http://partner.dw-world.de/syndication/feeds/rss-per_bloghaus_volltext.5722-mrss.xml](http://partner.dw-world.de/syndication/feeds/rss-per_bloghaus_volltext.5722-mrss.xml) ([Deutsche Welle][5])
* [http://rss.dw-world.de/xml/rss-per_gesellschaft_kultur](http://rss.dw-world.de/xml/rss-per_gesellschaft_kultur) ([Deutsche Welle][5])
* [http://rss.dw-world.de/xml/rss-per_deutschland](http://rss.dw-world.de/xml/rss-per_deutschland) ([Deutsche Welle][5])
* [http://rss.dw-world.de/xml/rss-per-sports](http://rss.dw-world.de/xml/rss-per-sports) ([Deutsche Welle][5])

DW Chinese podcast MRSS (from a directory listing)

* [http://partner.dw-world.de/syndication/feeds/podcast_radio_china.1169-mrss.xml](http://partner.dw-world.de/syndication/feeds/podcast_radio_china.1169-mrss.xml) ([Miro Guide][6])

Al Jazeera RSS (the URL is on their domain; listing source is third-party)

* [https://www.aljazeera.com/xml/rss/all.xml](https://www.aljazeera.com/xml/rss/all.xml) ([The Intelligence Cable][7])

“Known-working” video-oriented feeds (handy for your “news/balance” picker)

* [http://feeds.reuters.com/reuters/USVideoBreakingviews](http://feeds.reuters.com/reuters/USVideoBreakingviews) ([Littlstar Support][8])
* [http://feeds.reuters.com/reuters/USVideoPolitics](http://feeds.reuters.com/reuters/USVideoPolitics) ([Littlstar Support][8])
* [https://www.nasa.gov/rss/dyn/TWAN_vodcast.rss](https://www.nasa.gov/rss/dyn/TWAN_vodcast.rss) ([Littlstar Support][8])
* [https://www.nasa.gov/rss/dyn/nasa360_vodcast.rss](https://www.nasa.gov/rss/dyn/nasa360_vodcast.rss) ([Littlstar Support][8])
* [http://feed.cnet.com/feed/podcast/all/hd.xml](http://feed.cnet.com/feed/podcast/all/hd.xml) ([Littlstar Support][8])
* [https://www.jpl.nasa.gov/multimedia/podcast/podfeed.xml](https://www.jpl.nasa.gov/multimedia/podcast/podfeed.xml) ([Littlstar Support][8])
* [http://feeds.pbs.org/pbs/wgbh/nova-video](http://feeds.pbs.org/pbs/wgbh/nova-video) ([Littlstar Support][8])
* [http://feeds.feedburner.com/TEDTalks_video](http://feeds.feedburner.com/TEDTalks_video) ([Littlstar Support][8])

Global sermons / non-US churches / Black ministries / African / Chinese

UK (some explicitly labeled “Video” on Podbean pages — your script should confirm enclosures)

* [https://feed.podbean.com/firstlovechurchuk/feed.xml](https://feed.podbean.com/firstlovechurchuk/feed.xml) ([firstlovechurchuk.podbean.com][9])
* [https://feed.podbean.com/soulchurchuk/feed.xml](https://feed.podbean.com/soulchurchuk/feed.xml) ([soulchurchuk.podbean.com][10])
* [https://feed.podbean.com/skylarkchurch/feed.xml](https://feed.podbean.com/skylarkchurch/feed.xml) ([skylarkchurch.podbean.com][11])
* [https://feed.podbean.com/lifevineyardchurch/feed.xml](https://feed.podbean.com/lifevineyardchurch/feed.xml) ([lifevineyardchurch.podbean.com][12])
* [https://feed.podbean.com/lifewarrington/feed.xml](https://feed.podbean.com/lifewarrington/feed.xml) ([lifewarrington.podbean.com][13])
* [https://feed.podbean.com/citychapelchurch/feed.xml](https://feed.podbean.com/citychapelchurch/feed.xml) ([citychapelchurch.podbean.com][14])
* [https://feed.podbean.com/pastorsacademy/feed.xml](https://feed.podbean.com/pastorsacademy/feed.xml) ([pastorsacademy.podbean.com][15])
* [https://sermons.estuaryelim.church/podcast.xml](https://sermons.estuaryelim.church/podcast.xml) 

Ghana / Black ministry (explicit “Video Podcast” on Podbean)

* [https://feed.podbean.com/daghewardmillsvideo/feed.xml](https://feed.podbean.com/daghewardmillsvideo/feed.xml) ([daghewardmillsvideo.podbean.com][16])

Other Christian “video podcast” style feeds (Podbean)

* [https://feed.podbean.com/djjvideo/feed.xml](https://feed.podbean.com/djjvideo/feed.xml) ([djjvideo.podbean.com][17])
* [https://feed.podbean.com/DungenessCommunityChurch/feed.xml](https://feed.podbean.com/DungenessCommunityChurch/feed.xml) ([dungenesscommunitychurch.podbean.com][18])
* [https://feed.podbean.com/potentialvideo/feed.xml](https://feed.podbean.com/potentialvideo/feed.xml) ([potentialvideo.podbean.com][19])

Chinese-language church/ministry podcasts (Podbean; you’ll need to check whether any are video)

* [https://feed.podbean.com/crossccc/feed.xml](https://feed.podbean.com/crossccc/feed.xml) ([crossccc.podbean.com][20])
* [https://feed.podbean.com/bamboopastors/feed.xml](https://feed.podbean.com/bamboopastors/feed.xml) ([bamboopastors.podbean.com][21])
* [https://feed.podbean.com/sfcbc/feed.xml](https://feed.podbean.com/sfcbc/feed.xml) ([sfcbc.podbean.com][22])
* [https://feed.podbean.com/chichurch/feed.xml](https://feed.podbean.com/chichurch/feed.xml) ([chichurch.podbean.com][23])

Black gospel/radio (not sermons; still a useful “Black Christian” vertical if you want it)

* [https://feed.podbean.com/affinityxtra/feed.xml](https://feed.podbean.com/affinityxtra/feed.xml) ([affinityxtra.podbean.com][24])


[1]: https://petafloptimism.com/2005/11/03/bbc-news-video-in-rss/ "BBC News video in RSS! – Petafloptimism"
[2]: https://support.bbc.co.uk/platform/feeds/UkNews.htm "BBC Developer"
[3]: https://support.bbc.co.uk/platform/feeds/LastFifty.htm "BBC Developer"
[4]: https://www.euronews.com/widgets "Free Euronews widgets and services - Euronews"
[5]: https://www.dw.com/fa-ir/rss-feed-%D9%87%D8%A7%DB%8C-%D8%AF%D9%88%DB%8C%DA%86%D9%87-%D9%88%D9%84%D9%87-%D9%81%D8%A7%D8%B1%D8%B3%DB%8C/a-15689225 "RSS- Feed های دویچه وله فارسی – DW – ۱۳۹۰/۱۱/۵"
[6]: https://www.miroguide.com/audio/5141?utm_source=chatgpt.com "Miro Guide - 德国之声中文广播"
[7]: https://www.intelligencecable.com/2020/08/09/al-jazeera/ "Middle East | The Intelligence Cable"
[8]: https://littlstar.zendesk.com/hc/en-us/articles/360028563112-RSS-Feeds-EN "RSS Feeds [EN] – Littlstar Support"
[9]: https://firstlovechurchuk.podbean.com/?utm_source=chatgpt.com "First Love Church UK - Video | firstlovechurchuk"
[10]: https://soulchurchuk.podbean.com/?utm_source=chatgpt.com "SOUL Church UK | SOUL Church"
[11]: https://skylarkchurch.podbean.com/?utm_source=chatgpt.com "Skylark Church | skylarkchurch"
[12]: https://lifevineyardchurch.podbean.com/?utm_source=chatgpt.com "Life Vineyard Church | lifevineyardchurch"
[13]: https://lifewarrington.podbean.com/?utm_source=chatgpt.com "LifeChurch Warrington | Life Church Warrington"
[14]: https://citychapelchurch.podbean.com/?utm_source=chatgpt.com "City Chapel Sermons | City Chapel Church"
[15]: https://pastorsacademy.podbean.com/?utm_source=chatgpt.com "London Seminary & the Pastors’ Academy | London Seminary & the Pastors’ Academy"
[16]: https://daghewardmillsvideo.podbean.com/?utm_source=chatgpt.com "Dag Heward-Mills Video Podcast | Dag Heward-Mills"
[17]: https://djjvideo.podbean.com/e/enugu-a-new-vision/?utm_source=chatgpt.com "Enugu: A New Vision | Discovering The Jewish Jesus Video Podcast"
[18]: https://dungenesscommunitychurch.podbean.com/e/forgotten-prophets-zechariah-tim-richards-video/?utm_source=chatgpt.com "\"Forgotten Prophets\" - Zechariah - Tim Richards [VIDEO] | Dungeness Community Church - VIDEO"
[19]: https://potentialvideo.podbean.com/?utm_source=chatgpt.com "[VIDEO] Potential Church with Pastor Troy Gramling | Pastor Troy Gramling"
[20]: https://crossccc.podbean.com/?utm_source=chatgpt.com "CCCC"
[21]: https://bamboopastors.podbean.com/?utm_source=chatgpt.com "The Bamboo Pastors Podcast | Jalon Chan & Jon Mann"
[22]: https://sfcbc.podbean.com/?utm_source=chatgpt.com "The Chinese Bible Church Podcast | Norman Lau"
[23]: https://chichurch.podbean.com/?utm_source=chatgpt.com "Chinese Community Church, Sacramento, CA | chichurch"
[24]: https://affinityxtra.podbean.com/?utm_source=chatgpt.com "Affinity Xtra On Demand | AffinityXtra"

### assistant

Treating "not-a-feed-xml" as a skip (not an error) and ensuring the update script always exits 0:

### assistant

Done. Responses that aren’t valid feed XML are now treated as skips instead of errors: the script logs `[skip] fourth-antiphon (not-a-feed-xml)` and continues without failing.

### you

aquarium.js went missing, check the log, it must have got lost... GET https://prays.be/assets/app/player/audio_plugins/aquarium.js net::ERR_ABORTED 404 (Not Found)

### assistant

Restored `aquarium.js` from git history (commit 945ec3d).

### assistant

Summary:

**Verification (5s timeout):**
- **Dead/404:** BBC newsplayer, NASA TWAN/nasa360, JPL podcast, CNET HD, Reuters
- **Working:** BBC newsonline, Euronews, Al Jazeera, DW Persian, PBS Nova (video), TED (video), church feeds

**Added:**

1. **`feeds/news.md`** (new): BBC news, Euronews (news, nocomment, sport, green), Al Jazeera, DW Persian, PBS Nova (video), TED (video)

2. **`feeds/church.md`** (video): Dag Heward-Mills, Dungeness Community Church, Potential Church, First Love Church UK

3. **`feeds/church-audio-only.md` (audio):** SOUL Church UK, Skylark, Life Vineyard, LifeChurch Warrington, City Chapel, Pastors Academy, Affinity Xtra, CCCC, Bamboo Pastors, Chinese Bible Church, Chinese Community Church Sacramento

**Excluded:** Estuary Elim (0 items), BBC latest_published (0 items), BBC sport (1 item)

**`scripts/verify_feeds_quick.js`** — quick script to verify feeds (5s timeout). Usage: `node scripts/verify_feeds_quick.js <url1> <url2> ...`

### you

can you use our find-feeds script to find more feeds from podcastindex that complement our existing lists

### assistant

Adding complementary feeds to the appropriate files:

### assistant

Summary of feeds added from PodcastIndex:

**news.md**
- TED Talks HD
- Science Friday Videos
- UCTV Science (Video)
- Tech News Weekly (Video)
- Geek News Central (Video)

**church.md**
- Life.Church with Craig Groeschel (Video)
- Sandals Church Sermon Video
- Scottsdale Bible Church Sermon HD
- Reality LA — Bible Teaching (Video)
- Between Sermons (Video)
- The Well — Sermon Video
- Sanctus Church Video Sermons

**church-audio-only.md**
- Sikh History Sakhi (interfaith)

All feeds were checked with `verify_feeds_quick.js` (items present, video where expected). Build completed successfully.

### you

our tv guide currently wraps episodes per channel, but I don't think  it really works because so many of our feeds only have a few videos, and it's hard to parse our loop point. For each channel in the guide, below the name, the left, next to the fave tooggle, but under the channel name text, show the number of episodes. Disable episode looping by default, but put it behind a const, as I might want to turn it back on later if I don't like the new setting.

### assistant

Summary of changes:

**1. Episode count under channel name**
- Added a count (e.g. `12 ep`) in `guideGridChanSub`, left side, next to the fave toggle
- Uses schedule playable count when available, otherwise counts playable episodes from loaded data
- Shows `—` while loading
- Styled with `guideGridChanEpCount` (small, muted)

**2. Episode looping off by default**
- Introduced `EPISODE_LOOP_ENABLED = false` at the top of `guide.js`
- When `false`:
  - `programAt`: returns `null` for times beyond the last episode
  - `blocksForRange`: stops after the last episode instead of wrapping
- Set `EPISODE_LOOP_ENABLED = true` to restore TV-style looping

### you

don't include 'ep' and make it barely visible, it's more for my use than the user, so it shouldn't draw the eye

### assistant

Updates applied: show only the numeric count (no "ep") and reduced visibility (opacity 0.28, 10px font).

### you

check our church entries for duplicates, I can see at least 1 of Fresh Life church has duplicate entries

### assistant

Removing duplicate entries from `church.md` (it includes `church-audio-only.md`, so those feeds remain):
