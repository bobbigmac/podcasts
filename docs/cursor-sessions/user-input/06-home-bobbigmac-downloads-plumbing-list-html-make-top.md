---
cursor_session: 1fab715c-e4c0-401f-9b75-d116771fc195
source: cursor-composer
cursor_hint: ?
user_entries: 12
---

# user input — home-bobbigmac-downloads-plumbing-list-html-make-top

## 1

@/home/bobbigmac/Downloads/plumbing-list.html make top level li items into numbered items,

## 2

change the style so the panels are white not grey, and make the heading bits bolder

## 3

I suppose I meant make the ol bold, not the li below them

## 4

NOT the ones below them

## 5

add cursor to my path

## 6

for every entry in church.md add a  - tags: entry that has mutliple tags based off the content described by our gathered rss feeds. They're to be used to filter channels by the type of content typically found on that channel, and can/should have multiple tags each. I dont want you to update the file from a script though, I want you to read our cache/build as needed (our composited rss might be useful) to identify what content is on each channel/feed, and set tags to the church.md for those for each feed. There probably shouldn't be more than say 6-7 tags per feed. I'm not sure what the best way to segment them is, so you might want to do some basic nlp/content detection, not just on titles but on others, so you may find it helpful to query the feeds caches in various ways with one-use/throwaway scripts you can use briefly in /scripts to help understand actual feed content, titles, etc. Some python might make that pretty easy, but I understand that asking you to determine tags naturally that communicate what each channel/feed ACTUALLY contains as video content, is tricky but from browsing the channels, many share keywords/tags, but none of them should have exactly the same set of tags, we are using these to hint to the user which channels have the same types of content, and will form the basis of our ui, as having all category set to 'church' isn't helpful, that should for all entries be updated to a single category that properly groups channels just by primary content type based on their feed infos.

## 7

i noticed none of these have like concert or music, but a LOT of these videos have a lot of 'concert-like' coverage, can we tag up any with like large stage performances or particulalry musically heavy

## 8

gimme a  quick  preort on our cataegory and tags distributions/frequency, so I can sanity check

## 9

can you find any more kids channels to add for that category, see our scripts, i think one or two of them searches podcast index. Feeds MUST have video, and should be fairly churchy, but if there are some reliably good quality and wholesome 'kids' openrss feeds, like christian-adjacent/down-home-american, that kind of thing, expanding our kids section with not explitly religious if not enough kids religious stuff, would be good.

## 10

can you find any more good fits for our worship and lifestyle categories too?

## 11

i think all our feeds have a redundant field "- fetch_via: auto" which is set the same for every entry, just remove that line for all feeds/*md files, and check the implementation doesn't rely on it being set to auto.

## 12

if they're all set to auto, why are we setting it?
