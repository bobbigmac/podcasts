---
cursor_session: 8ee47303-ee78-492d-8a03-10ec99933376
source: cursor
cursor_project: home-bobbigmac-projects-podcasts
user_entries: 1
source_file: /home/bobbigmac/.cursor/projects/home-bobbigmac-projects-podcasts/agent-transcripts/8ee47303-ee78-492d-8a03-10ec99933376/8ee47303-ee78-492d-8a03-10ec99933376.jsonl
---

# transcript — go-take-a-look-at-fubarradio-com-and

### you

go take a look at fubarradio.com and tell me how many shows they maintain in listen again/archive and estimate number of hours of content

### assistant

I’ll check FUBAR Radio’s Listen Again/archive pages directly, count unique shows listed there, then estimate total hours from the episode runtimes shown. I’m starting by pulling the relevant pages now.

> `WebSearch` {"search_term": "fubarradio.com listen again archive shows"}

> `WebFetch` {"url": "https://www.fubarradio.com/listen-again/"}

### assistant

I found the main Listen Again index pages; next I’m pulling the full `progs` archive page and sampling show pages to estimate typical episode length so the hour estimate is grounded.

> `WebFetch` {"url": "https://www.fubarradio.com/progs/"}

> `WebFetch` {"url": "https://www.fubarradio.com/player/on-demand/politics-uncensored/"}

> `rg` {"path": "/home/bobbigmac/.cursor/projects/home-bobbigmac-projects-podcasts/agent-tools/ce40b0ae-9233-4bc9-a0f7-e9dac84403d1.txt", "pattern": "duration|Duration| mins| min|:[0-5][0-9]", "output_mode":…

> `rg` {"path": "/home/bobbigmac/.cursor/projects/home-bobbigmac-projects-podcasts/agent-tools/ce40b0ae-9233-4bc9-a0f7-e9dac84403d1.txt", "pattern": "Episode|Play", "output_mode": "content", "head_limit": 40…

> `Shell` {"command": "ffprobe -v error -show_entries format=duration -of default=noprint_wrappers=1:nokey=1 \"https://aod.sharp-stream.com/content/fubar_radio/storage/1776963809-politics_uncensored.mp3?aw_0_1s…

### assistant

I confirmed a sample episode runtime from their MP3 source (about 1 hour). I’m now counting the actual show entries on the Listen Again archive page and then converting that into a total-hours estimate.

> `rg` {"path": "/home/bobbigmac/.cursor/projects/home-bobbigmac-projects-podcasts/agent-tools/ce40b0ae-9233-4bc9-a0f7-e9dac84403d1.txt", "pattern": "data-player-audio-url-param=\"([^\"]+)\"", "output_mode":…

> `Shell` {"command": "python3 - <<'PY'\nimport requests\nfrom bs4 import BeautifulSoup\nurl='https://www.fubarradio.com/progs/'\nhtml=requests.get(url,timeout=20).text\ns=BeautifulSoup(html,'html.parser')\n# c…

> `Shell` {"command": "python3 - <<'PY'\nimport urllib.request,re\nhtml=urllib.request.urlopen('https://www.fubarradio.com/progs/',timeout=20).read().decode('utf-8','ignore')\n# Count unique show slugs from on-…

> `Shell` {"command": "python3 - <<'PY'\nimport urllib.request,re\nhtml=urllib.request.urlopen('https://www.fubarradio.com/progs/',timeout=20).read().decode('utf-8','ignore')\nslugs=set(re.findall(r'/podcasts/(…

> `Shell` {"command": "python3 - <<'PY'\nimport urllib.request,re,subprocess,statistics,random\nbase='https://www.fubarradio.com'\nhtml=urllib.request.urlopen(base+'/progs/',timeout=20).read().decode('utf-8','i…

### assistant

`fubarradio.com` Listen Again/archive appears to currently list **about 68 shows** (I counted the `Listen Again` entries on `/progs/`; about **64** have active podcast pages, with a few legacy entries still listed).

Estimated archive size: **~6,000 to 12,000 hours** of audio.

- A sampled episode runtime is about **1 hour**.
- Typical show archive pages appear to hold on the order of **dozens to a couple hundred episodes**.
- Using ~68 shows × rough per-show back catalog gives that range.

If you want, I can do a stricter crawl and give you a tighter number per-show.
