# MCP server tool changes

Last change observed 2026-11-07T06:40:24+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

79931 changes to a tool definition: 3402 npm releases (3156 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 76529 readings of hosted servers that found their tools changed; 3519 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-07 | `remote/com.synthexforge.x402/paid-agent-services` | 2026-11-06T214846441518 -> 2026-11-07T064028758602 | 3 changed, 4 added | quiet |
| 2026-11-07 | `remote/com.stackerscan/stackerscan` | 2026-11-06T162154138984 -> 2026-11-07T064025929043 | 1 changed | quiet |
| 2026-11-07 | `remote/com.patchmcp/patch` | 2026-11-05T222229477210 -> 2026-11-07T064023966197 | 18 removed | quiet |
| 2026-11-07 | `remote/studio.gradients/mcp` | 2026-11-06T214840470251 -> 2026-11-07T064020532078 | 1 changed | quiet |
| 2026-11-07 | `remote/fi.akkilahdot/travel-search` | 2026-11-06T214836180260 -> 2026-11-07T064018482494 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-06T214836277096 -> 2026-11-07T064019246482 | 4 changed | quiet |
| 2026-11-07 | `remote/io.github.seasonsagents-art/webaz` | 2026-11-06T214832601250 -> 2026-11-07T064017764113 | 4 changed | quiet |
| 2026-11-07 | `remote/io.github.privatelawattorneys/wiki-private-law` | 2026-11-06T214835011151 -> 2026-11-07T064019020643 | 3 changed | quiet |
| 2026-11-07 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-06T144833550805 -> 2026-11-07T064017991496 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-06T214833636033 -> 2026-11-07T064018644703 | 16 added | quiet |
| 2026-11-07 | `remote/com.theopenapps/openapps` | 2026-11-06T144726669745 -> 2026-11-07T064015918920 | 1 changed | quiet |
| 2026-11-07 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-06T214830150241 -> 2026-11-07T064016724447 | 2 changed | quiet |
| 2026-11-07 | `remote/com.tetheredtrust/tethered-trust` | 2026-11-06T214828266217 -> 2026-11-07T064014307636 | 4 added | quiet |
| 2026-11-07 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-06T162141907098 -> 2026-11-07T064012169643 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.liad142/yedapo` | 2026-11-06T072811529827 -> 2026-11-07T064010995335 | 2 changed (every tool) | quiet |
| 2026-11-07 | `remote/no.restplass/travel-search` | 2026-11-06T214843078606 -> 2026-11-07T064009924037 | 1 changed | quiet |
| 2026-11-07 | `remote/com.sapiensinteticos/sapiens` | 2026-11-06T072810875652 -> 2026-11-07T064009802160 | 1 changed | quiet |
| 2026-11-07 | `remote/ai.arcreport/mcp` | 2026-11-06T144754499106 -> 2026-11-07T064007844895 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.ohad6k/viberaven-guides` | 2026-11-05T150808029469 -> 2026-11-07T064007146939 | 7 changed (every tool) | quiet |
| 2026-11-07 | `remote/dk.afbudsrejser/travel-search` | 2026-11-06T214839860593 -> 2026-11-07T064007919610 | 1 changed | quiet |
| 2026-11-07 | `remote/io.taifoon/coordination-layer.1` | 2026-11-06T214858637210 -> 2026-11-07T064006496416 | 1 changed | quiet |
| 2026-11-07 | `remote/se.sistaminuten/travel-search` | 2026-11-06T214857920209 -> 2026-11-07T064005711096 | 1 changed | quiet |
| 2026-11-07 | `remote/org.thealibrary/thea` | 2026-11-06T214835054265 -> 2026-11-07T064004662003 | 1 changed | quiet |
| 2026-11-07 | `remote/ai.arcreport/ask` | 2026-11-06T214853427224 -> 2026-11-07T064003048101 | 4 changed, 1 added | quiet |
| 2026-11-07 | `remote/com.supercatch/supercatch` | 2026-11-06T214831993492 -> 2026-11-07T064002317118 | 5 changed, 11 added | quiet |
| 2026-11-07 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-06T214833517849 -> 2026-11-07T064001637851 | 1 added | quiet |
| 2026-11-07 | `remote/online.pageaudit/pageaudit` | 2026-11-05T115137580747 -> 2026-11-07T064003327369 | 3 changed | quiet |
| 2026-11-07 | `remote/com.panelcompare/panelcompare` | 2026-11-06T144445221167 -> 2026-11-07T064006620424 | 2 changed | quiet |
| 2026-11-07 | `remote/io.github.kwizzlesurp10-ctrl/x402-mcp` | 2026-11-05T115516324144 -> 2026-11-07T063958755200 | 1 added | quiet |
| 2026-11-07 | `remote/dev.toolrail/mcp` | 2026-11-05T115247348517 -> 2026-11-07T063958885319 | 28 changed (every tool) | quiet |
| 2026-11-07 | `remote/com.thefomite/fomite` | 2026-11-06T072758843194 -> 2026-11-07T063958959344 | 1 changed | quiet |
| 2026-11-07 | `remote/com.scienceshot/data-centres` | 2026-11-06T214829053698 -> 2026-11-07T063959163538 | 6 added | quiet |
| 2026-11-07 | `remote/io.github.cryptoconspiracy/vurto-swap` | 2026-11-05T010724392317 -> 2026-11-07T063957742338 | 10 changed | review |
| 2026-11-07 | `remote/de.objelio/immobiliensuche` | 2026-11-06T214843299241 -> 2026-11-07T063959917274 | 3 changed | quiet |
| 2026-11-07 | `remote/fun.pumpdata/pumpdata` | 2026-11-06T072758529633 -> 2026-11-07T063956087317 | 1 added | quiet |
| 2026-11-07 | `remote/com.multicinesortega/cartelera` | 2026-11-06T214813156519 -> 2026-11-07T063958539804 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-06T214842282227 -> 2026-11-07T063956842241 | 2 changed | quiet |
| 2026-11-07 | `remote/com.probativegrowth/legal-marketing-data` | 2026-11-06T214824641071 -> 2026-11-07T063955596081 | 1 changed | quiet |
| 2026-11-07 | `remote/com.lucernanoetica/lucerna` | 2026-11-06T144426733652 -> 2026-11-07T063955251063 | 3 changed, 3 added | quiet |
| 2026-11-07 | `remote/com.googleapis.monitoring/mcp` | 2026-11-06T144355882689 -> 2026-11-07T063955858366 | 5 changed | quiet |
| 2026-11-07 | `remote/ai.screwtape/screwtape` | 2026-11-06T144512793817 -> 2026-11-07T063955769249 | 3 changed, 2 added | review |
| 2026-11-07 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-06T144348938326 -> 2026-11-07T063955388380 | 12 added, 3 removed | review |
| 2026-11-07 | `remote/io.github.brawlaphant/vealth` | 2026-11-05T222209811899 -> 2026-11-07T063954773425 | 3 changed, 8 removed | quiet |
| 2026-11-07 | `remote/com.partstable/partstable` | 2026-11-06T072757462557 -> 2026-11-07T063954930133 | 1 changed | quiet |
| 2026-11-07 | `remote/com.nymwell/mcp` | 2026-11-06T144349651379 -> 2026-11-07T063953694851 | 32 changed, 22 added (every tool) | quiet |
| 2026-11-07 | `remote/pl.finwire/data` | 2026-11-06T162144611864 -> 2026-11-07T063954138522 | 1 changed, 2 added | quiet |
| 2026-11-07 | `remote/io.github.Luis-Cwk/entropiav2` | 2026-11-05T115122657871 -> 2026-11-07T063953268513 | 1 added | quiet |
| 2026-11-07 | `remote/es.proceres/proceres` | 2026-11-06T214837599076 -> 2026-11-07T063953278749 | 3 changed | quiet |
| 2026-11-07 | `remote/io.github.jakegallen/poascan` | 2026-11-05T115039969996 -> 2026-11-07T063952431772 | 2 changed | quiet |
| 2026-11-07 | `remote/io.github.exquad/thecablecode` | 2026-11-06T162126523941 -> 2026-11-07T063953462701 | 6 changed | quiet |
| 2026-11-07 | `remote/ai.switchapp/switch` | 2026-11-06T214805285446 -> 2026-11-07T063950687498 | 3 changed | quiet |
| 2026-11-07 | `remote/com.socialseal/mcp` | 2026-11-06T162121207533 -> 2026-11-07T063950505441 | 101 changed, 7 removed | quiet |
| 2026-11-07 | `remote/com.rushordertees/rushordertees` | 2026-11-06T162119924305 -> 2026-11-07T063949486294 | 11 changed | quiet |
| 2026-11-07 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-11-06T072805241000 -> 2026-11-07T063949379960 | 1 changed | quiet |
| 2026-11-07 | `remote/now.salesjobs/mcp` | 2026-11-05T222157646244 -> 2026-11-07T063949598905 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.smarterweather/weather` | 2026-11-06T214809279956 -> 2026-11-07T063947932687 | 4 changed | quiet |
| 2026-11-07 | `remote/io.github.jake-zaiba/deai-research` | 2026-11-05T222217150342 -> 2026-11-07T063947860138 | 1 changed | quiet |
| 2026-11-07 | `remote/co.civai.nova/mcp-firecrawl` | 2026-11-06T214831423822 -> 2026-11-07T063949698948 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.magichourhq/magic-hour` | 2026-11-06T072803902725 -> 2026-11-07T063947379184 | 30 changed | quiet |
| 2026-11-07 | `remote/io.github.cnucho/methodiq-tools` | 2026-11-06T144251970555 -> 2026-11-07T063946739048 | 15 changed, 14 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 49836 substantive, 29223 that changed only numbers (a catalogue counter ticking, a date), 872 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 43277 | 15883 | 27394 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1604 | 1604 | 0 | 0 |
| `caseyjhand.com` | 354 | 354 | 0 | 0 |
| `sistaminuten.se` | 205 | 6 | 0 | 199 |
| `afbudsrejser.dk` | 204 | 6 | 0 | 198 |
| `akkilahdot.fi` | 204 | 6 | 0 | 198 |
| `restplass.no` | 204 | 6 | 0 | 198 |
| `socialloop.ai` | 196 | 196 | 0 | 0 |
| `revmesh2074.workers.dev` | 181 | 158 | 23 | 0 |
| `modevc.com` | 174 | 174 | 0 | 0 |
| `remoshift.com` | 165 | 14 | 151 | 0 |
| 7810 other operators | 30822 | 29088 | 1655 | 79 |
