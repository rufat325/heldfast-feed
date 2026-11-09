# MCP server tool changes

Last change observed 2026-11-09T17:04:19+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

84566 changes to a tool definition: 3727 npm releases (3481 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 80839 readings of hosted servers that found their tools changed; 3651 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-09 | `remote/com.starcovery/mcp` | 2026-11-07T133924375910 -> 2026-11-09T170423055716 | 10 changed | review |
| 2026-11-09 | `remote/agency.zoll/ausfuhr` | 2026-10-26T133625674584 -> 2026-11-09T170419458349 | 3 changed, 1 added, 1 removed | quiet |
| 2026-11-09 | `remote/no.restplass/travel-search` | 2026-11-09T071602041689 -> 2026-11-09T170414915259 | 1 changed | quiet |
| 2026-11-09 | `remote/io.github.yappmaniac/grocery-price-snapshots` | 2026-11-04T150647979730 -> 2026-11-09T170411762508 | 1 added | quiet |
| 2026-11-09 | `remote/com.yawplet/messages` | 2026-11-02T163755075475 -> 2026-11-09T170412374293 | 3 changed | quiet |
| 2026-11-09 | `remote/io.github.openaccountants/openaccountants` | 2026-11-08T204945711361 -> 2026-11-09T170407157420 | 1 changed | quiet |
| 2026-11-09 | `remote/ai.makeviral/makeviral` | 2026-11-08T135712754967 -> 2026-11-09T170359580371 | 1 changed | quiet |
| 2026-11-09 | `remote/io.github.e-tara/januarysales` | 2026-11-02T163601816613 -> 2026-11-09T170354911492 | 1 changed | quiet |
| 2026-11-09 | `remote/ai.haggl/haggl` | 2026-10-29T212904992923 -> 2026-11-09T170350994815 | 4 changed | quiet |
| 2026-11-09 | `remote/io.github.cryptoduke01/gloam` | 2026-11-07T133828568449 -> 2026-11-09T170349509752 | 6 changed | quiet |
| 2026-11-09 | `remote/com.finn.www/auto` | 2026-09-23T163132461506 -> 2026-11-09T170345203627 | 2 changed | quiet |
| 2026-11-09 | `remote/de.drgsystem/medical-catalogs` | 2026-11-04T150809684593 -> 2026-11-09T170342320361 | 2 changed | quiet |
| 2026-11-09 | `remote/io.github.junoventures/dojoplus-co` | 2026-10-28T212523534320 -> 2026-11-09T170339376531 | 2 changed, 1 added | quiet |
| 2026-11-09 | `remote/com.premierletters/mcp` | 2026-11-04T150622973840 -> 2026-11-09T170339092594 | 2 changed | quiet |
| 2026-11-09 | `remote/io.github.PettyMiggzy/oversize-escort-hub` | 2026-11-02T163713002054 -> 2026-11-09T170334534634 | 1 changed | quiet |
| 2026-11-09 | `remote/design.overflow/mcp` | 2026-11-08T135837030522 -> 2026-11-09T170335249348 | 3 changed (every tool) | quiet |
| 2026-11-09 | `remote/io.github.imokokok/insight-oracle` | 2026-11-08T204945082860 -> 2026-11-09T170335279263 | 10 changed | quiet |
| 2026-11-09 | `remote/ai.bordet/bordet` | 2026-10-20T104236749993 -> 2026-11-09T170330624158 | 2 changed | quiet |
| 2026-11-09 | `remote/com.yarnhen/stories` | 2026-11-02T163504450629 -> 2026-11-09T170325442739 | 3 changed | quiet |
| 2026-11-09 | `remote/com.cliniatlas/evidence` | 2026-10-22T110048385003 -> 2026-11-09T170326068026 | 2 changed | quiet |
| 2026-11-09 | `remote/dk.afbudsrejser/travel-search` | 2026-11-09T071558870743 -> 2026-11-09T170323626467 | 1 changed | quiet |
| 2026-11-09 | `remote/com.xmlvalid/xmlvalid` | 2026-10-26T133929819985 -> 2026-11-09T170323173412 | 5 changed (every tool) | quiet |
| 2026-11-09 | `remote/com.actualgroup/jobs` | 2026-10-23T120623679123 -> 2026-11-09T170322465607 | 6 changed (every tool) | quiet |
| 2026-11-09 | `remote/tr.com.isinn.www/isinn` | 2026-11-02T163659660038 -> 2026-11-09T170316069830 | 2 changed | quiet |
| 2026-11-09 | `remote/ai.wiretensors/wiretensors` | 2026-09-23T163114954668 -> 2026-11-09T170313993903 | 3 added | quiet |
| 2026-11-09 | `remote/org.windowsticker/window-sticker` | 2026-10-06T110251468309 -> 2026-11-09T170314057875 | 1 changed | quiet |
| 2026-11-09 | `remote/studio.gradients/mcp` | 2026-11-08T204942692782 -> 2026-11-09T170309001559 | 1 changed | quiet |
| 2026-11-09 | `remote/xyz.tereno/tereno` | 2026-11-09T071620431578 -> 2026-11-09T170305643335 | 1 added | review |
| 2026-11-09 | `remote/io.github.junoventures/genesis-social` | 2026-10-28T212426842016 -> 2026-11-09T170305181625 | 2 changed, 1 added | quiet |
| 2026-11-09 | `remote/ai.startuphub/startuphub` | 2026-11-04T200758660083 -> 2026-11-09T170303283486 | 13 changed | quiet |
| 2026-11-09 | `remote/se.sistaminuten/travel-search` | 2026-11-09T071619909259 -> 2026-11-09T170300760553 | 1 changed | quiet |
| 2026-11-09 | `remote/io.github.cooyun/etuki-finops-mcp` | 2026-11-09T071634046028 -> 2026-11-09T170259521288 | 9 changed (every tool) | review |
| 2026-11-09 | `remote/io.github.AndrewVG23/safe-bite` | 2026-10-26T133912225291 -> 2026-11-09T170258301652 | 5 changed (every tool) | quiet |
| 2026-11-09 | `remote/com.receptionistprices/pricing` | 2026-11-02T163434516474 -> 2026-11-09T170258261480 | 6 changed (every tool) | quiet |
| 2026-11-09 | `remote/io.github.junoventures/vilamariana-sampa-br` | 2026-10-28T212508866470 -> 2026-11-09T170255934312 | 2 changed, 1 added | quiet |
| 2026-11-09 | `remote/io.github.cryptosun/proximens-oracle` | 2026-11-03T144957319383 -> 2026-11-09T170255031150 | 4 changed | quiet |
| 2026-11-09 | `remote/com.diariobitcoin/news` | 2026-11-03T024307698759 -> 2026-11-09T170254189628 | 3 changed | quiet |
| 2026-11-09 | `remote/com.oxfordledge/oxford-ledge` | 2026-11-02T163428395537 -> 2026-11-09T170250269893 | 3 added | quiet |
| 2026-11-09 | `remote/io.github.andzar22/offstereo` | 2026-11-08T135855112441 -> 2026-11-09T170248116301 | 1 changed, 1 added | quiet |
| 2026-11-09 | `remote/io.github.mooshee/untax` | 2026-11-06T144717757291 -> 2026-11-09T170240506598 | 57 changed | quiet |
| 2026-11-09 | `remote/io.github.junoventures/bogeyland-golf` | 2026-10-28T212443902977 -> 2026-11-09T170300629760 | 2 changed, 1 added | quiet |
| 2026-11-09 | `remote/io.github.JcJamet/ia-qa-eval` | 2026-11-08T135847104774 -> 2026-11-09T170239846285 | 1 changed | quiet |
| 2026-11-09 | `remote/io.github.junoventures/graciebarrajiujitsu-site` | 2026-10-28T212416505743 -> 2026-11-09T170237664965 | 2 changed, 1 added | quiet |
| 2026-11-09 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-11-08T135847356836 -> 2026-11-09T170239946710 | 1 changed | quiet |
| 2026-11-09 | `remote/si.zazidljiva/mcp` | 2026-10-25T120041637933 -> 2026-11-09T170237997000 | 2 changed | quiet |
| 2026-11-09 | `remote/io.github.Gingiris-1031/analook` | 2026-10-06T110348312729 -> 2026-11-09T170235270587 | 8 changed (every tool) | quiet |
| 2026-11-09 | `remote/fi.akkilahdot/travel-search` | 2026-11-09T071634876967 -> 2026-11-09T170234372124 | 1 changed | quiet |
| 2026-11-09 | `remote/io.github.junoventures/filipe-coffee` | 2026-10-28T212416576902 -> 2026-11-09T170233340243 | 2 changed, 1 added | quiet |
| 2026-11-09 | `remote/com.followontours/cricket-travel` | 2026-11-03T144940045347 -> 2026-11-09T170234160713 | 1 changed | quiet |
| 2026-11-09 | `remote/io.github.Ockram4444/agentcompute` | 2026-11-02T163448595112 -> 2026-11-09T170232207320 | 3 changed, 1 added, 1 removed | quiet |
| 2026-11-09 | `remote/com.yachtcharterquotes/site` | 2026-09-23T160901644071 -> 2026-11-09T170231910869 | 1 changed | quiet |
| 2026-11-09 | `remote/xyz.x402helper/mcp` | 2026-11-05T222216338152 -> 2026-11-09T170228671875 | 4 changed, 1 added, 1 removed | quiet |
| 2026-11-09 | `remote/io.github.AndrewVG23/cufftracker` | 2026-10-26T133845045135 -> 2026-11-09T170227614537 | 5 changed (every tool) | quiet |
| 2026-11-09 | `remote/com.blitzreels/blitzreels` | 2026-11-07T151351448189 -> 2026-11-09T170225381355 | 3 changed | quiet |
| 2026-11-09 | `remote/com.answeringprices/pricing` | 2026-10-28T133426590667 -> 2026-11-09T170220232349 | 4 changed (every tool) | quiet |
| 2026-11-09 | `remote/io.github.Gingiris/analook` | 2026-10-06T110142826336 -> 2026-11-09T170219975346 | 8 changed (every tool) | quiet |
| 2026-11-09 | `remote/io.github.tradingale/mcp` | 2026-10-24T190414431273 -> 2026-11-09T170219204707 | 6 changed | quiet |
| 2026-11-09 | `remote/com.toolsthatdontupload/tools` | 2026-11-08T204941070097 -> 2026-11-09T170214290337 | 1 changed | quiet |
| 2026-11-09 | `remote/io.github.seasonsagents-art/webaz` | 2026-11-07T064017764113 -> 2026-11-09T170213577481 | 1 changed | quiet |
| 2026-11-09 | `remote/com.workinsiders/directory` | 2026-10-17T055550961935 -> 2026-11-09T170211822452 | 1 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 52457 substantive, 31194 that changed only numbers (a catalogue counter ticking, a date), 915 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 45128 | 15898 | 29230 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1843 | 1843 | 0 | 0 |
| `caseyjhand.com` | 359 | 359 | 0 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `civai.co` | 234 | 234 | 0 | 0 |
| `sistaminuten.se` | 215 | 6 | 0 | 209 |
| `afbudsrejser.dk` | 214 | 6 | 0 | 208 |
| `akkilahdot.fi` | 214 | 6 | 0 | 208 |
| `restplass.no` | 214 | 6 | 0 | 208 |
| `socialloop.ai` | 206 | 206 | 0 | 0 |
| `revmesh2074.workers.dev` | 197 | 174 | 23 | 0 |
| 8229 other operators | 33143 | 31120 | 1941 | 82 |
