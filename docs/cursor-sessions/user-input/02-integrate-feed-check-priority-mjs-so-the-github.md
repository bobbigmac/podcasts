---
cursor_session: 92b3d551-8c4e-4072-bb69-608de1e81862
source: cursor
cursor_project: home-bobbigmac-projects-podcasts
user_entries: 4
source_file: /home/bobbigmac/.cursor/projects/home-bobbigmac-projects-podcasts/agent-transcripts/92b3d551-8c4e-4072-bb69-608de1e81862/92b3d551-8c4e-4072-bb69-608de1e81862.jsonl
---

# user input — integrate-feed-check-priority-mjs-so-the-github

## 1

Integrate feed-check-priority.mjs so the github actions updates check fcuses on target feeds that are in the priority list first, instead of just all feeds every time. Abandoned/dead/inactive feeds should still be checked occasionally, so maybe we want a kinda cooldown, like check even seemingly inactive feeds at least once a week. Try not to fuxk with the system, our cache storage is intentionally weird, just focus on priorities and reducing how many queries we make with every run, while still hitting feeds where it's clear we expect content.

## 2

only 20 feeds is very tight, let it use a more generous budget (don't hardcode to a limit of checkables, use banding based on what's in the groups, no basic threshold assumptions).

## 3

run that locally against the existing (stale) cache, then check some of the feeds it says are overdue/etc

## 4

I just updated feed-check-priority.mjs, check it again
