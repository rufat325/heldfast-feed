# MCP server tool changes

Last change observed 2026-11-02T16:39:50+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

70841 changes to a tool definition: 2981 npm releases (2735 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 67860 readings of hosted servers that found their tools changed; 3208 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-02 | `remote/io.github.xzntexe/yruz-x402` | 2026-10-27T210203814695 -> 2026-11-02T163952097792 | 44 changed | quiet |
| 2026-11-02 | `remote/dev.zambo/zambo` | 2026-10-30T210624083890 -> 2026-11-02T163951596118 | 8 changed | quiet |
| 2026-11-02 | `remote/com.quailos/quailos` | 2026-10-30T210622272124 -> 2026-11-02T163919651326 | 4 added | quiet |
| 2026-11-02 | `remote/de.objelio/immobiliensuche` | 2026-10-26T133705652886 -> 2026-11-02T163916279039 | 1 changed | quiet |
| 2026-11-02 | `remote/com.market0x/marketplace` | 2026-10-31T130255086890 -> 2026-11-02T163910150831 | 1 changed | quiet |
| 2026-11-02 | `remote/ai.go-rocket/go-rocket` | 2026-10-21T202505861183 -> 2026-11-02T163858705771 | 2 changed, 1 added, 1 removed | quiet |
| 2026-11-02 | `remote/io.github.Ments123/dmd-costs-tools` | 2026-10-26T133640329040 -> 2026-11-02T163848776347 | 32 changed, 1 added | quiet |
| 2026-11-02 | `remote/me.walalook/tools.3` | 2026-10-19T135200706582 -> 2026-11-02T163811156711 | 1 added | quiet |
| 2026-11-02 | `remote/io.github.sorindecu/vibeshipped` | 2026-10-30T152340358232 -> 2026-11-02T163801974528 | 3 changed | quiet |
| 2026-11-02 | `remote/co.videoupscaler/video-upscaler` | 2026-10-23T120603976025 -> 2026-11-02T163801384385 | 1 changed | quiet |
| 2026-11-02 | `remote/com.zinvyl/marketplace` | 2026-10-28T062211140616 -> 2026-11-02T163801369002 | 5 changed | quiet |
| 2026-11-02 | `remote/com.xn--5kvtwv52d/jizhineng-mcp-gateway` | 2026-10-31T062146125351 -> 2026-11-02T163754140872 | 21 changed (every tool) | quiet |
| 2026-11-02 | `remote/com.synthexforge.x402/paid-agent-services` | 2026-11-02T065458215882 -> 2026-11-02T163748884830 | 1 changed | quiet |
| 2026-11-02 | `remote/shop.grokzilla/micro-pay.1` | 2026-10-26T153210443754 -> 2026-11-02T163745370376 | 2 changed | review |
| 2026-11-02 | `remote/com.theprotoclinical/commerce` | 2026-10-31T062141945287 -> 2026-11-02T163733438671 | 1 changed | quiet |
| 2026-11-02 | `remote/io.github.switchwize/switchwize-mcp` | 2026-10-28T133136996882 -> 2026-11-02T163731226049 | 16 changed, 2 added (every tool) | quiet |
| 2026-11-02 | `remote/com.riddle/creator` | 2026-10-30T133103225743 -> 2026-11-02T163723813316 | 2 changed | quiet |
| 2026-11-02 | `remote/com.patchmcp/patch` | 2026-10-29T212907570780 -> 2026-11-02T163714198137 | 30 changed, 1 added, 6 removed | quiet |
| 2026-11-02 | `remote/design.overflow/mcp` | 2026-10-28T133128040060 -> 2026-11-02T163716551491 | 2 changed | quiet |
| 2026-11-02 | `remote/io.github.imokokok/insight-oracle` | 2026-11-02T065458082038 -> 2026-11-02T163714939893 | 1 changed | quiet |
| 2026-11-02 | `remote/io.github.exquad/thecablecode` | 2026-11-02T065429848364 -> 2026-11-02T163705161780 | 6 changed | quiet |
| 2026-11-02 | `remote/cc.thecolony/mcp-server` | 2026-11-01T205259720957 -> 2026-11-02T163705346322 | 2 changed | quiet |
| 2026-11-02 | `remote/studio.gradients/mcp` | 2026-11-02T065455571230 -> 2026-11-02T163653070129 | 1 changed | quiet |
| 2026-11-02 | `remote/com.synapticrelay/freelance-board.1` | 2026-10-19T135120911404 -> 2026-11-02T163645057330 | 2 changed | quiet |
| 2026-11-02 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-10-27T210236352173 -> 2026-11-02T163638663685 | 1 changed | quiet |
| 2026-11-02 | `remote/com.suomiatlas/area-statistics` | 2026-10-20T104232644882 -> 2026-11-02T163636237369 | 7 changed | quiet |
| 2026-11-02 | `remote/ar.com.consignatarias/cattle-market` | 2026-10-31T130355268882 -> 2026-11-02T163656394618 | 3 changed | quiet |
| 2026-11-02 | `remote/app.sunsetstrip/gta6` | 2026-10-26T133502765542 -> 2026-11-02T163635285240 | 1 changed, 3 added | review |
| 2026-11-02 | `remote/io.github.xentoshi/clarke` | 2026-10-26T133510202404 -> 2026-11-02T163630250669 | 3 changed | quiet |
| 2026-11-02 | `remote/at.schitterhof.www/camping` | 2026-10-19T135857665207 -> 2026-11-02T163621687166 | 6 changed (every tool) | quiet |
| 2026-11-02 | `remote/no.restplass/travel-search` | 2026-11-02T065445788583 -> 2026-11-02T163619829288 | 1 changed | quiet |
| 2026-11-02 | `remote/fi.akkilahdot/travel-search` | 2026-11-02T065454894023 -> 2026-11-02T163617501603 | 1 changed | quiet |
| 2026-11-02 | `remote/app.sprkly/sprkly` | 2026-10-31T130059104574 -> 2026-11-02T163618965985 | 4 changed | quiet |
| 2026-11-02 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-11-01T135243641382 -> 2026-11-02T163613461882 | 13 changed, 1 added | quiet |
| 2026-11-02 | `remote/ar.mueblito/mueblito` | 2026-10-18T051541341235 -> 2026-11-02T163610401065 | 8 changed | quiet |
| 2026-11-02 | `remote/com.juzpost/mcp` | 2026-10-29T104601009586 -> 2026-11-02T163602658212 | 9 changed | quiet |
| 2026-11-02 | `remote/com.sitecomb/check-website` | 2026-10-30T132729340594 -> 2026-11-02T163556155533 | 1 changed | quiet |
| 2026-11-02 | `remote/work.funfriday/funfriday` | 2026-10-17T060441369085 -> 2026-11-02T163556123383 | 1 changed | quiet |
| 2026-11-02 | `remote/com.walletmcppass/wallet-mcp` | 2026-10-19T135509868224 -> 2026-11-02T163549895115 | 2 changed (every tool) | quiet |
| 2026-11-02 | `remote/me.walalook/tools.5` | 2026-10-19T135508697418 -> 2026-11-02T163551562426 | 1 added, 1 removed | quiet |
| 2026-11-02 | `remote/me.walalook/tools.2` | 2026-10-17T055909222848 -> 2026-11-02T163551538926 | 1 added, 1 removed | quiet |
| 2026-11-02 | `remote/co.shopwithin/within` | 2026-10-26T133430033426 -> 2026-11-02T163549156252 | 2 added | quiet |
| 2026-11-02 | `remote/com.shipshapedata/shipshape-data` | 2026-11-01T135226797189 -> 2026-11-02T163548963497 | 1 changed | quiet |
| 2026-11-02 | `remote/com.lordevo/shop` | 2026-10-30T152335971551 -> 2026-11-02T163552410600 | 19 changed, 6 added | review |
| 2026-11-02 | `remote/app.openkrill/sharelink` | 2026-11-01T135225482402 -> 2026-11-02T163545798412 | 1 changed | quiet |
| 2026-11-02 | `remote/io.github.SecondShotAI/verifylite` | 2026-10-28T153207935105 -> 2026-11-02T163540010027 | 8 changed, 6 added | review |
| 2026-11-02 | `remote/io.github.smartsurfsolar/senlay` | 2026-11-01T135218857429 -> 2026-11-02T163536248242 | 2 changed | quiet |
| 2026-11-02 | `remote/ai.arcreport/mcp` | 2026-10-19T135824829162 -> 2026-11-02T163535638234 | 1 changed | quiet |
| 2026-11-02 | `remote/dk.afbudsrejser/travel-search` | 2026-11-02T065444817421 -> 2026-11-02T163532132041 | 1 changed | quiet |
| 2026-11-02 | `remote/io.github.aneduaim/untap-mcp` | 2026-10-17T055857559851 -> 2026-11-02T163530837099 | 3 changed | quiet |
| 2026-11-02 | `remote/eu.scheir/portfolio` | 2026-10-17T060125408237 -> 2026-11-02T163524709587 | 1 changed | quiet |
| 2026-11-02 | `remote/com.satmarin/catalog` | 2026-10-17T060123707481 -> 2026-11-02T163521409099 | 1 changed | quiet |
| 2026-11-02 | `remote/uk.co.transportstatementcost/site` | 2026-10-06T110318794758 -> 2026-11-02T163520892031 | 1 changed | quiet |
| 2026-11-02 | `remote/ai.wem3/wem-price-compare` | 2026-10-31T202130310790 -> 2026-11-02T163520024173 | 2 changed | quiet |
| 2026-11-02 | `remote/io.github.a1476/verateca` | 2026-10-26T153234026426 -> 2026-11-02T163503570690 | 2 changed | quiet |
| 2026-11-02 | `remote/cloud.pandy/tickets` | 2026-10-17T155957719060 -> 2026-11-02T163503370276 | 1 changed | quiet |
| 2026-11-02 | `remote/rs.rides/airport-transfers` | 2026-10-28T133357347178 -> 2026-11-02T163503779344 | 6 changed (every tool) | quiet |
| 2026-11-02 | `remote/io.github.shashwatgtm/revenue-enablement-mcp` | 2026-10-28T133355130580 -> 2026-11-02T163504553897 | 5 changed | quiet |
| 2026-11-02 | `remote/com.restaurantdoctorai/profit-check` | 2026-11-01T065431804422 -> 2026-11-02T163459242036 | 2 changed, 1 added | quiet |
| 2026-11-02 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-02T065452088489 -> 2026-11-02T163456784176 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 44810 substantive, 25245 that changed only numbers (a catalogue counter ticking, a date), 786 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 39567 | 15869 | 23698 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1245 | 1245 | 0 | 0 |
| `caseyjhand.com` | 313 | 313 | 0 | 0 |
| `sistaminuten.se` | 186 | 6 | 0 | 180 |
| `afbudsrejser.dk` | 185 | 6 | 0 | 179 |
| `akkilahdot.fi` | 185 | 6 | 0 | 179 |
| `restplass.no` | 185 | 6 | 0 | 179 |
| `socialloop.ai` | 179 | 179 | 0 | 0 |
| `remoshift.com` | 155 | 12 | 143 | 0 |
| `revmesh2074.workers.dev` | 146 | 128 | 18 | 0 |
| `fundinglandscape.com` | 143 | 89 | 54 | 0 |
| 6992 other operators | 26011 | 24610 | 1332 | 69 |
