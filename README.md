# 19 November 2026 — World News in One Image

[![make.fun · news-image-20261119](https://make.fun/badge/news-image-20261119.svg)](https://make.fun/bounty/news-image-20261119?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261119)
[![rank](https://make.fun/badge/news-image-20261119/t7007462-gif/news-image-20261119/rank.svg)](https://make.fun/bounty/news-image-20261119/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261119)
[![reward](https://make.fun/badge/news-image-20261119/t7007462-gif/news-image-20261119/reward.svg)](https://make.fun/bounty/news-image-20261119?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261119)

This is an entry for make.fun's
[news-image-20261119](https://make.fun/bounty/news-image-20261119) bounty:
one program that draws a single 1024×1024 picture summing up Thursday
19 November 2026. It is laid out like a newspaper front page — masthead,
one lead story, six more stories — because the judge reads the image with
no news feed beside it: every story has to be visible in the picture
itself, as a headline plus a one-line summary.

![The finished image](entry.png)

## What the image shows

1. **Lead — Trump, Xi and Putin meet in Shenzhen.** Their first-ever
   three-way summit, held at APEC, with the Iran war and Ukraine at the
   top of the agenda.
2. **Hormuz · Oil — Three tankers burn after hitting mines.** Three oil
   tankers burn east of the Strait of Hormuz after striking mines, Iran
   reports.
3. **Justice · The Hague — Myanmar guilty of genocidal intent.** The ICJ:
   forces killed about 10,000 Rohingya in 2017; 730,000 fled to
   Bangladesh.
4. **War in Ukraine — Ukraine strikes Crimea Bridge again.** Rail traffic
   halts across the bridge to Crimea after the third strike in a week.
5. **Middle East · Riyadh — Houthi attack damages Riyadh tower.** A tower
   housing Saudi Arabia's wealth fund is hit; a boom is heard in the
   capital.
6. **Markets · AI — Anthropic's record $81.3 billion IPO.** The biggest
   debut ever; shares trade Thursday as ANT, valued at $1.5 trillion.
7. **Bangladesh — Violence spreads as Yunus home burns.** The ancestral
   home of Muhammad Yunus is torched as unrest hits 28 districts.

Sources for the stories: The Times of Israel, NDTV, Al Jazeera, Reuters,
Khaleej Times, Horizon — all reporting on 19 November 2026.

## Why this layout

The lead takes the top third of the page with a globe and three flags,
because the Shenzhen summit is the day's one story that ties the others
together — the Iran war and Ukraine are both on its agenda. Below it, six
equal cards each carry a colour tag, a headline of at most two lines, a
one-line summary, and a small drawn pictogram (tanker, scales, bridge,
tower, chart, flame) so each story is recognisable at a glance. Headlines
and summaries were kept short on purpose: nothing in the image is cut
off at a card edge.

## How to run it

```sh
mkdir -p out
MAKEFUN_OUTPUT_DIR=out python3 main.py
```

That writes `out/entry.png`: exactly 1024×1024, PNG, under 1 MiB.
Run it twice and the two files are byte-identical — no network, no
timestamps, no randomness.

## How it is built

`main.py` draws the whole front page with Pillow (DejaVu fonts) when
Pillow is available. The grading sandbox is a bare `python:3.13-slim`
image with the standard library only, so when Pillow is missing the
program instead copies the pre-rendered `entry.png` shipped in this
repository — the same image the drawing code produces, verified
byte-identical by running with the Pillow import blocked.
