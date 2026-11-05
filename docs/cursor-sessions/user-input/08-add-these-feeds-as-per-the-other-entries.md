---
cursor_session: d396cbfd-3147-41ff-a4fa-8dac8cb10135
source: cursor-composer
cursor_hint: ?
user_entries: 10
---

# user input — add-these-feeds-as-per-the-other-entries

## 1

add these feeds as per the other entries in feeds.md AND add them to feeds.other.md (but in feeds.other.md set them as supplemental).

You’ve already got most of the high-degree “UK-comedian guest graph” hubs. The obvious missing connectors (from your current feed list) are:

* [Chatabix (Joe Wilkinson & David Earl)](https://podcasts.apple.com/gb/podcast/chatabix/id1560965008) — frequent celeb/comedy guests, lots of volume so it stitches edges fast. ([Apple Podcasts][1])
* [The Socially Distant Sports Bar](https://podcasts.apple.com/gb/podcast/the-socially-distant-sports-bar/id1500451926) — pulls in a big Welsh/UK panel-show orbit plus sports/TV adjacent guests. ([Apple Podcasts][2])
* [The Skewer (BBC Radio 4)](https://podcasts.apple.com/gb/podcast/the-skewer/id1499553630) — satirical/news remix; different guest pool + recurring voices that link back into Friday Night Comedy / News Quiz land. ([Podbean][3])
* [Comedy of the Week (BBC Radio 4)](https://podcasts.apple.com/gb/podcast/comedy-of-the-week/id412151541) — basically a “catch whatever Radio 4 comedy is doing” vacuum cleaner. ([Apple Podcasts][4])
* [Early Work with Rhys James](https://podcasts.apple.com/be/podcast/early-work-with-rhys-james/id1491354878) — smaller, but very “comedian’s comedian” guest mix you’ll want for cross-links. ([Apple Podcasts][5])
* [Rule of Three](https://podcasts.apple.com/gb/podcast/rule-of-three/id1562789734) — comedy-writing/industry angle; great for joining up writers, showrunners, sketch people who don’t always do the big interview pods. ([Apple Podcasts][6])
* [Where There’s a Will, There’s a Wake](https://podcasts.apple.com/gb/podcast/where-theres-a-will-theres-a-wake/id1592093686) — strong UK-comedy guest rotation, very “adjacent social cloud” to your existing set. ([Apple Podcasts][7])
* [Pod Save the UK](https://en.wikipedia.org/wiki/Pod_Save_the_UK) — if you want “politics-but-comedian-host” bridges (Nish Kumar) into the rest of your politics feeds. ([Wikipedia][8])

If you add just the first four, you’ll notice the guest graph getting denser quickly without exploding your feed count.

[1]: https://podcasts.apple.com/gb/podcast/chatabix/id1560965008?utm_source=chatgpt.com "Chatabix - Podcast - Apple Podcasts"
[2]: https://podcasts.apple.com/gb/podcast/where-there%27s-a-will%2C-there%27s-a-wake/id1654059310 "https://podcasts.apple.com/gb/podcast/where-there%27s-a-will%2C-there%27s-a-wake/id1654059310"
[3]: https://www.podbean.com/podcast-detail/ygfn9-b28be/The-Skewer-Podcast?utm_source=chatgpt.com "The Skewer Podcast | Free Listening on Podbean App"
[4]: https://podcasts.apple.com/gb/podcast/comedy-of-the-week/id412151541?utm_source=chatgpt.com "Comedy of the Week - Podcast - Apple Podcasts"
[5]: https://podcasts.apple.com/be/podcast/early-work-with-rhys-james/id1491354878?utm_source=chatgpt.com "Early Work with Rhys James - Podcast - Apple Podcasts"
[6]: https://podcasts.apple.com/gb/podcast/distraction-pieces-podcast-with-scroobius-pip/id929136539?utm_source=chatgpt.com "Distraction Pieces Podcast with Scroobius Pip - Podcast - Apple Podcasts"
[7]: https://podcasts.apple.com/gb/podcast/my-time-capsule/id1506937544 "https://podcasts.apple.com/gb/podcast/my-time-capsule/id1506937544"
[8]: https://en.wikipedia.org/wiki/Pod_Save_the_UK?utm_source=chatgpt.com "Pod Save the UK"

## 2

don't rebuilt it for just minor changes, just make the changes. I'll come back with some more sites to add soon

## 3

these should be added to the britcom list as normal, and to the feeds.other as supplemental (I think some are duplicates you just added, so dedupe)...

```## griefcast
- url: https://feeds.acast.com/public/shows/6b139f7b-0974-4b07-99fa-945390989fd8
- title_override: Griefcast
- supplemental: true
- owners: Cariad Lloyd
- categories: comedy/british, interviews

## drunk-women-solving-crime
- url: https://feeds.acast.com/public/shows/580adc7a-3ec4-4ee1-a811-02ba70ad9aad
- title_override: Drunk Women Solving Crime
- supplemental: true
- owners: Hannah George; Taylor Glenn
- categories: comedy/british, panel, true-crime

## the-socially-distant-sports-bar
- url: https://feeds.acast.com/public/shows/68e81932d798804c9ef004e3
- title_override: The Socially Distant Sports Bar
- supplemental: true
- owners: Elis James; Mike Bubbins; Steff Garrero
- categories: comedy/british, sports

## rule-of-three
- url: https://feeds.acast.com/public/shows/a18c2026-fb61-4cb6-a153-32d529de0a07
- title_override: Rule Of Three
- supplemental: true
- owners: Joel Morris; Jason Hazeley
- categories: comedy/british, interviews, craft/writing

## chatabix
- url: https://feeds.megaphone.fm/GLT7256806225
- title_override: Chatabix
- supplemental: true
- owners: Joe Wilkinson; David Earl
- categories: comedy/british, chat

## out-with-suzi-ruffell
- url: https://feeds.megaphone.fm/GLT9819213775
- title_override: Out with Suzi Ruffell
- supplemental: true
- owners: Suzi Ruffell
- categories: comedy/british, interviews

## all-killa-no-filla
- url: https://allkillanofilla.libsyn.com/rss
- title_override: All Killa No Filla
- supplemental: true
- owners: Kiri Pritchard-McLean; Rachel Fairburn
- categories: comedy/british, true-crime

## brydon-and
- url: https://rss.art19.com/brydon
- title_override: Brydon & (Rob Brydon)
- supplemental: true
- owners: Rob Brydon
- categories: comedy/british, interviews

## where-theres-a-will-theres-a-wake
- url: https://feeds.megaphone.fm/wtawtaw
- title_override: Where There’s A Will, There’s A Wake
- supplemental: true
- categories: comedy/british, interviews

## just-a-minute
- url: https://podcasts.files.bbci.co.uk/b006s5dp.rss
- title_override: Just a Minute
- supplemental: true
- owners: BBC Radio 4
- categories: comedy/british, bbc, radio/panel

## breaking-the-news
- url: https://podcasts.files.bbci.co.uk/b066zypj.rss
- title_override: Breaking the News
- supplemental: true
- owners: BBC Radio Scotland
- categories: comedy/british, bbc, radio/panel, news

## scummy-mummies
- url: https://scummymummies.libsyn.com/rss
- title_override: Scummy Mummies
- supplemental: true
- owners: Ellie Gibson; Helen Thorn
- categories: comedy/british, interviews, parenting```

## 4

don't try and guess it, google it

## 5

forget brydon&, doesn't matter

## 6

okay good. Add these ones to just the britcom list (no more going on the other feed)...

```## bbc-comedy-of-the-week
- url: https://podcasts.files.bbci.co.uk/p02pc9x6.rss
- title_override: Comedy of the Week (BBC Radio 4)

## bbc-wheel-of-misfortune
- url: https://podcasts.files.bbci.co.uk/p08m3z73.rss
- title_override: Wheel of Misfortune (BBC Radio 4)

## bbc-graham-norton
- url: https://podcasts.files.bbci.co.uk/p02nrtl3.rss
- title_override: The Graham Norton Podcast (BBC Radio 2)

## bottoms-up
- url: https://feeds.megaphone.fm/GLT2696747469
- title_override: Bottoms Up! With Alan Carr and Lee Peart

## trusty-hogs
- url: https://feeds.acast.com/public/shows/trustyhogs
- title_override: Trusty Hogs

## welcome-to-hell
- url: https://feeds.acast.com/public/shows/welcome-to-hell-with-daniel-foxx-dane-buckley
- title_override: Welcome To Hell

## cuddle-club
- url: https://feeds.acast.com/public/shows/dc460793-43f6-4464-a809-8e23f92194bb
- title_override: Cuddle Club (Lou Sanders)

## pappys-flatshare
- url: https://feeds.megaphone.fm/NSR6478712326
- title_override: Pappy’s Flatshare

## tvi
- url: https://feeds.megaphone.fm/GLT5047224671
- title_override: TVI with Carl Donnelly and Julian Deane

## whats-upset-you-now
- url: https://anchor.fm/s/10818226c/podcast/rss
- title_override: What’s Upset You Now?

## beef-and-dairy
- url: https://feeds.simplecast.com/4NOSW3hj
- title_override: Beef And Dairy Network```

## 7

you forgot to find owners and set categories

## 8

add that gaming podcast by sarah keyworth (iirc) and pierree novellie and the other guy

## 9

look up pottering with tom allen and add it to both feeds and feeds.other (not supplmental)

## 10

look up and add "The Good Ones" from Vulture, only to the feeds.md
