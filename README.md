# MCP server tool changes

Last change observed 2026-10-31T06:21:52+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

64706 changes to a tool definition: 2657 npm releases (2411 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 62049 readings of hosted servers that found their tools changed; 3052 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps and signed with Sigstore: [checkpoints/](checkpoints). To check a day, rebuild the manifest of the commit it names, compare it with `manifest_sha256`, then verify the proof (the full steps, and what each one trusts, are in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints)):

```bash
day=2026-09-28
commit=$(python3 -c "import json; print(json.load(open('checkpoints/$day.json'))['feed_commit'])")
mkdir ../at && git -c core.autocrlf=false archive "$commit" | tar -x -C ../at
(cd ../at && find . -type f ! -path './checkpoints/*' -printf '%P\0' \
  | LC_ALL=C sort -z | xargs -0 sha256sum | sha256sum)   # = manifest_sha256
pip install opentimestamps-client && ots verify checkpoints/$day.json.ots
```

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-10-31 | `remote/no.restplass/travel-search` | 2026-10-30T210642837929 -> 2026-10-31T062157734689 | 1 changed | quiet |
| 2026-10-31 | `remote/com.meridiandispatch/travel-guides` | 2026-10-30T063147920604 -> 2026-10-31T062155770876 | 1 changed | quiet |
| 2026-10-31 | `remote/dk.afbudsrejser/travel-search` | 2026-10-30T210630727236 -> 2026-10-31T062150609207 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.ohad6k/viberaven-guides` | 2026-10-30T132912964403 -> 2026-10-31T062144608827 | 1 added | quiet |
| 2026-10-31 | `remote/com.xn--5kvtwv52d/jizhineng-mcp-gateway` | 2026-10-30T133118606051 -> 2026-10-31T062146125351 | 5 added, 1 removed | quiet |
| 2026-10-31 | `remote/com.theprotoclinical/commerce` | 2026-10-30T133107214302 -> 2026-10-31T062141945287 | 1 added | quiet |
| 2026-10-31 | `remote/ai.greyridgesignals/tech-risk` | 2026-10-30T210638613814 -> 2026-10-31T062142926054 | 2 changed | quiet |
| 2026-10-31 | `remote/studio.gradients/mcp` | 2026-10-30T210635056410 -> 2026-10-31T062141031010 | 1 changed | quiet |
| 2026-10-31 | `remote/com.mintlify/searchmcp` | 2026-10-30T133053144835 -> 2026-10-31T062142328289 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.SoapyRED/freightutils` | 2026-10-30T152353912831 -> 2026-10-31T062140842699 | 3 changed | quiet |
| 2026-10-31 | `remote/se.sistaminuten/travel-search` | 2026-10-30T210623866970 -> 2026-10-31T062140178054 | 1 changed | quiet |
| 2026-10-31 | `remote/io.taifoon/coordination-layer.1` | 2026-10-30T210624469969 -> 2026-10-31T062139419373 | 1 changed | review |
| 2026-10-31 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-10-30T063141098271 -> 2026-10-31T062139282307 | 1 changed | quiet |
| 2026-10-31 | `remote/fi.akkilahdot/travel-search` | 2026-10-30T210632990996 -> 2026-10-31T062140117646 | 1 changed | quiet |
| 2026-10-31 | `remote/ai.startuphub/startuphub` | 2026-10-30T132918564508 -> 2026-10-31T062139592611 | 1 changed, 4 added | quiet |
| 2026-10-31 | `remote/fr.synergieloc/immobilier` | 2026-10-30T210616510825 -> 2026-10-31T062140136018 | 36 added | quiet |
| 2026-10-31 | `remote/io.github.miketwalker/tubepull` | 2026-10-29T063224912421 -> 2026-10-31T062137491904 | 2 changed (every tool) | quiet |
| 2026-10-31 | `remote/tools.settled/settled` | 2026-10-30T210612383511 -> 2026-10-31T062136328854 | 2 changed | quiet |
| 2026-10-31 | `remote/io.github.Timothymycompc/solana-pulse-gateway` | 2026-10-29T063220557788 -> 2026-10-31T062136019226 | 2 added | review |
| 2026-10-31 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-30T210629342431 -> 2026-10-31T062136505877 | 1 changed | quiet |
| 2026-10-31 | `remote/com.swarmmemo/bulletin.1` | 2026-10-30T210626829563 -> 2026-10-31T062150587697 | 2 changed, 1 added | quiet |
| 2026-10-31 | `remote/com.swarmmemo/bulletin` | 2026-10-30T210626594464 -> 2026-10-31T062150434822 | 2 changed | quiet |
| 2026-10-31 | `remote/re.rundata/temps-reel` | 2026-10-29T212843453062 -> 2026-10-31T062135456742 | 3 changed | quiet |
| 2026-10-31 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-30T210624477268 -> 2026-10-31T062134299336 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.SKalinin909/tradingcalc` | 2026-10-30T210616189626 -> 2026-10-31T062134179529 | 6 changed, 5 added | review |
| 2026-10-31 | `remote/io.github.JacobiusMakes/stienhardt-store` | 2026-10-30T132845326078 -> 2026-10-31T062134118322 | 1 added | quiet |
| 2026-10-31 | `remote/ai.rokha/rokha` | 2026-10-30T063133025686 -> 2026-10-31T062133782620 | 6 changed | quiet |
| 2026-10-31 | `remote/io.github.bnth09productions-maker/scrapling-x402-store` | 2026-10-30T210623185407 -> 2026-10-31T062133237846 | 1 changed | quiet |
| 2026-10-31 | `remote/com.thefomite/fomite` | 2026-10-30T063144947515 -> 2026-10-31T062133864074 | 1 changed | quiet |
| 2026-10-31 | `remote/com.straelo/relay` | 2026-10-30T210609512800 -> 2026-10-31T062133791953 | 1 added | quiet |
| 2026-10-31 | `remote/ai.swarmnest/mcp` | 2026-10-30T132700236121 -> 2026-10-31T062131763058 | 3 changed, 1 added | quiet |
| 2026-10-31 | `remote/io.github.richardsolomou/praetorium` | 2026-10-30T132624121252 -> 2026-10-31T062132779623 | 3 changed | quiet |
| 2026-10-31 | `remote/io.github.prof-1t/postlyra-mcp` | 2026-10-30T152354888881 -> 2026-10-31T062132312965 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.majidkabir/sootcase` | 2026-10-30T210611902071 -> 2026-10-31T062133115806 | 5 changed | quiet |
| 2026-10-31 | `remote/io.github.Fizzl13/presign-guard` | 2026-10-29T132848352503 -> 2026-10-31T062131796999 | 1 changed | review |
| 2026-10-31 | `remote/com.remoshift/jobs` | 2026-10-30T210622480544 -> 2026-10-31T062132350209 | 1 changed | quiet |
| 2026-10-31 | `remote/com.pourwire/pourwire` | 2026-10-30T210620005279 -> 2026-10-31T062130990327 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.teamhandyapps-oss/postlaunchkit` | 2026-10-29T104205555842 -> 2026-10-31T062130049441 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.scraping-api-plans/web-data-plan-finder` | 2026-10-29T063217926983 -> 2026-10-31T062131301707 | 3 changed | quiet |
| 2026-10-31 | `remote/fun.publish/mcp` | 2026-10-30T132529344382 -> 2026-10-31T062130159997 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.rezearcher/tech-risk` | 2026-10-30T210623124463 -> 2026-10-31T062128557406 | 2 changed | quiet |
| 2026-10-31 | `remote/io.github.Fizzl13/x402-doctor` | 2026-10-29T212838348413 -> 2026-10-31T062129519735 | 1 added | quiet |
| 2026-10-31 | `remote/xyz.pokeka/card-prices` | 2026-10-30T063132111731 -> 2026-10-31T062128144946 | 1 changed | quiet |
| 2026-10-31 | `remote/com.odilelabs/odile` | 2026-10-30T063130760537 -> 2026-10-31T062129106840 | 9 changed, 3 added | quiet |
| 2026-10-31 | `remote/com.nicevois/rvc-training` | 2026-10-30T132529706124 -> 2026-10-31T062129015953 | 1 changed | quiet |
| 2026-10-31 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-10-30T210616469827 -> 2026-10-31T062127637745 | 5 changed | quiet |
| 2026-10-31 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-10-30T063203996540 -> 2026-10-31T062128604399 | 2 changed | quiet |
| 2026-10-31 | `remote/com.multicinesortega/cartelera` | 2026-10-30T210617219149 -> 2026-10-31T062128984736 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.smarterweather/weather` | 2026-10-30T210600363845 -> 2026-10-31T062126307482 | 6 changed | quiet |
| 2026-10-31 | `remote/com.myanimetracker/myanimetracker-account` | 2026-10-30T152326271361 -> 2026-10-31T062124732533 | 2 changed | quiet |
| 2026-10-31 | `remote/io.github.exquad/thecablecode` | 2026-10-30T132818499088 -> 2026-10-31T062124701521 | 1 changed | quiet |
| 2026-10-31 | `remote/ai.switchapp/switch` | 2026-10-30T210609334477 -> 2026-10-31T062124572563 | 1 changed | quiet |
| 2026-10-31 | `remote/com.socialseal/mcp` | 2026-10-30T132517936821 -> 2026-10-31T062123677985 | 23 changed | quiet |
| 2026-10-31 | `remote/io.github.tinbox-labs/spawnpop` | 2026-10-30T210614494144 -> 2026-10-31T062122743543 | 4 added | quiet |
| 2026-10-31 | `remote/dev.uptimepage/uptimepage` | 2026-10-30T132337584940 -> 2026-10-31T062124273044 | 4 changed | quiet |
| 2026-10-31 | `remote/com.ableandagent/sandbox` | 2026-10-29T063201940246 -> 2026-10-31T062121061263 | 6 changed | review |
| 2026-10-31 | `remote/ai.skuit/catalog` | 2026-10-30T132317004044 -> 2026-10-31T062120738069 | 1 changed | quiet |
| 2026-10-31 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-30T063154062806 -> 2026-10-31T062120986916 | 1 changed | quiet |
| 2026-10-31 | `remote/pro.particle/particle-pro` | 2026-10-30T210553864838 -> 2026-10-31T062120297772 | 1 changed | review |
| 2026-10-31 | `remote/com.hireahelper/mcp` | 2026-10-30T210556816049 -> 2026-10-31T062119617918 | 16 removed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 42505 substantive, 21459 that changed only numbers (a catalogue counter ticking, a date), 742 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 35898 | 15833 | 20065 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1126 | 1126 | 0 | 0 |
| `caseyjhand.com` | 283 | 283 | 0 | 0 |
| `sistaminuten.se` | 176 | 6 | 0 | 170 |
| `afbudsrejser.dk` | 175 | 6 | 0 | 169 |
| `akkilahdot.fi` | 175 | 6 | 0 | 169 |
| `restplass.no` | 175 | 6 | 0 | 169 |
| `socialloop.ai` | 169 | 169 | 0 | 0 |
| `remoshift.com` | 145 | 10 | 135 | 0 |
| `fundinglandscape.com` | 134 | 85 | 49 | 0 |
| `revmesh2074.workers.dev` | 129 | 116 | 13 | 0 |
| 6581 other operators | 23780 | 22518 | 1197 | 65 |
