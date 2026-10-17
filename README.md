# MCP server tool changes

Last change observed 2026-10-17T18:54:11+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10495 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 23695 hosted endpoints (read daily, and every four hours while they keep changing).

30377 changes to a tool definition: 1052 npm releases (806 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 29325 readings of hosted servers that found their tools changed; 2060 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-17 | `remote/com.starcovery/mcp` | 2026-10-17T160028057532 -> 2026-10-17T185412456801 | 10 changed | quiet |
| 2026-10-17 | `remote/no.restplass/travel-search` | 2026-10-17T160027359547 -> 2026-10-17T185411670964 | 1 changed | quiet |
| 2026-10-17 | `remote/dk.afbudsrejser/travel-search` | 2026-10-17T160019170321 -> 2026-10-17T185403150999 | 1 changed | quiet |
| 2026-10-17 | `remote/xn--3ds443g.xn--s7y/duan-online` | 2026-10-17T055630650838 -> 2026-10-17T185402935212 | 4 changed | quiet |
| 2026-10-17 | `remote/io.github.witanmarkets/witan` | 2026-10-17T160018788676 -> 2026-10-17T185402886350 | 2 changed | quiet |
| 2026-10-17 | `remote/fi.akkilahdot/travel-search` | 2026-10-17T160009326159 -> 2026-10-17T185401055684 | 1 changed | quiet |
| 2026-10-17 | `remote/com.veridionmarkets/disclosures` | 2026-10-17T055624312443 -> 2026-10-17T185359541486 | 5 changed (every tool) | quiet |
| 2026-10-17 | `remote/se.sistaminuten/travel-search` | 2026-10-17T155958858014 -> 2026-10-17T185357576657 | 1 changed | quiet |
| 2026-10-17 | `remote/dev.vetagent/vetagent` | 2026-10-17T055904040980 -> 2026-10-17T185358353343 | 2 changed | quiet |
| 2026-10-17 | `remote/com.rightshold/rightshold` | 2026-10-17T060408175730 -> 2026-10-17T185351306814 | 10 changed, 2 added | quiet |
| 2026-10-17 | `remote/io.github.boriskendev/stormap` | 2026-10-17T060319381079 -> 2026-10-17T185348110569 | 18 changed (every tool) | quiet |
| 2026-10-17 | `remote/com.basischarts/basis` | 2026-10-17T060333488053 -> 2026-10-17T185349262103 | 6 changed | quiet |
| 2026-10-17 | `remote/ch.swisslivingindex/swiss-living-index` | 2026-10-17T155954409217 -> 2026-10-17T185347380605 | 1 added | quiet |
| 2026-10-17 | `remote/com.spacexploration/listings` | 2026-10-17T060310596618 -> 2026-10-17T185346195108 | 1 changed | quiet |
| 2026-10-17 | `remote/app.sallim/korea-stay` | 2026-10-17T055817785539 -> 2026-10-17T185346389529 | 2 changed | quiet |
| 2026-10-17 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-17T122842362350 -> 2026-10-17T185343546531 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.brawlaphant/vealth` | 2026-10-17T060259941529 -> 2026-10-17T185342980994 | 9 added | quiet |
| 2026-10-17 | `remote/io.github.cryptoconspiracy/vurto-swap` | 2026-10-17T055458258395 -> 2026-10-17T185342127171 | 8 changed, 2 added | quiet |
| 2026-10-17 | `remote/com.remoshift/jobs` | 2026-10-17T155944457945 -> 2026-10-17T185338220721 | 1 changed | quiet |
| 2026-10-17 | `remote/app.sallim/korea-realty` | 2026-10-17T060205869162 -> 2026-10-17T185338829827 | 11 changed | quiet |
| 2026-10-17 | `remote/com.plainrecords/us-recalls-food-products-vehicles` | 2026-10-17T055656316374 -> 2026-10-17T185331094588 | 2 changed | quiet |
| 2026-10-17 | `remote/io.github.cloakmaster/pact0` | 2026-10-17T110522102853 -> 2026-10-17T185329679627 | 3 changed | quiet |
| 2026-10-17 | `remote/com.santismm/knowledge` | 2026-10-17T110704357796 -> 2026-10-17T185329713778 | 2 changed, 5 added | quiet |
| 2026-10-17 | `remote/rs.rides/airport-transfers` | 2026-10-17T060115143276 -> 2026-10-17T185328510154 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.open-mtor-atlas/mtor-atlas` | 2026-10-17T060055300316 -> 2026-10-17T185325195797 | 2 changed | quiet |
| 2026-10-17 | `remote/io.github.Philongevity/phi-longevity-prism` | 2026-10-17T055353084972 -> 2026-10-17T185326024682 | 1 added | quiet |
| 2026-10-17 | `remote/com.obriym-crm/mcp` | 2026-10-17T055629062841 -> 2026-10-17T185325777498 | 3 changed, 1 added | quiet |
| 2026-10-17 | `remote/how.mise/mise` | 2026-10-17T122756085852 -> 2026-10-17T185326087732 | 8 changed | quiet |
| 2026-10-17 | `remote/com.owlchart/owlchart` | 2026-10-17T155930223644 -> 2026-10-17T185324361098 | 1 changed | quiet |
| 2026-10-17 | `remote/com.opedd/opedd-mcp` | 2026-10-17T055459237269 -> 2026-10-17T185312359561 | 9 changed | quiet |
| 2026-10-17 | `remote/world.tokenbank/tokenbank` | 2026-10-17T055237462792 -> 2026-10-17T185311552270 | 11 changed (every tool) | quiet |
| 2026-10-17 | `remote/dev.mcphost/mcphost` | 2026-10-17T155910554509 -> 2026-10-17T185309292835 | 2 changed | quiet |
| 2026-10-17 | `remote/ai.mapmap/mapmap` | 2026-10-17T122810348878 -> 2026-10-17T185309893430 | 30 changed | quiet |
| 2026-10-17 | `remote/com.kernelcad/kernelcad` | 2026-10-17T110820133230 -> 2026-10-17T185308274546 | 1 changed | quiet |
| 2026-10-17 | `remote/com.etfiq/etfiq` | 2026-10-17T055904487605 -> 2026-10-17T185306337868 | 2 changed | quiet |
| 2026-10-17 | `remote/com.metricduck/financial-analysis` | 2026-10-17T155909676933 -> 2026-10-17T185302899318 | 2 changed | quiet |
| 2026-10-17 | `remote/com.commerceforagents/commerceforagents` | 2026-10-17T055851958485 -> 2026-10-17T185303848601 | 2 changed | quiet |
| 2026-10-17 | `remote/io.github.privatebydefault/default-privacy` | 2026-10-17T055344910680 -> 2026-10-17T185259518490 | 5 changed | quiet |
| 2026-10-17 | `remote/com.problee/problee` | 2026-10-17T155901598059 -> 2026-10-17T185258422451 | 2 added | quiet |
| 2026-10-17 | `remote/ing.crank/crank` | 2026-10-17T055109107237 -> 2026-10-17T185257401290 | 2 changed, 3 removed | quiet |
| 2026-10-17 | `remote/io.github.ronrey/comos-federation` | 2026-10-17T055107024671 -> 2026-10-17T185256066637 | 1 changed | quiet |
| 2026-10-17 | `remote/com.convertlyft/convertlyft` | 2026-10-17T110319154433 -> 2026-10-17T185256212883 | 1 changed, 2 added | quiet |
| 2026-10-17 | `remote/io.github.ronrey/federation` | 2026-10-17T055626410232 -> 2026-10-17T185249925746 | 1 changed | quiet |
| 2026-10-17 | `remote/com.comos-federation/gateway` | 2026-10-17T055626289014 -> 2026-10-17T185249854317 | 1 changed | quiet |
| 2026-10-17 | `remote/com.adrianhomelab/leadgen-onrc` | 2026-10-17T155859713703 -> 2026-10-17T185251533095 | 8 changed | quiet |
| 2026-10-17 | `remote/ai.marketcrew/market-data` | 2026-10-17T055035541721 -> 2026-10-17T185249719547 | 1 changed | quiet |
| 2026-10-17 | `remote/expert.globalmacro/global-macro-expert` | 2026-10-17T055201854455 -> 2026-10-17T185244361840 | 1 changed | quiet |
| 2026-10-17 | `remote/de.livaglow/livaglow-shop` | 2026-10-17T055534691309 -> 2026-10-17T185243716695 | 2 changed | quiet |
| 2026-10-17 | `remote/app.getjopp/jobs` | 2026-10-17T055643223513 -> 2026-10-17T185243426800 | 1 changed | quiet |
| 2026-10-17 | `remote/app.gamedayweather/gdw` | 2026-10-17T110008885319 -> 2026-10-17T185241807314 | 3 added | quiet |
| 2026-10-17 | `remote/com.faceabot/capability-network` | 2026-10-17T054522238917 -> 2026-10-17T185237618830 | 1 changed, 3 added | quiet |
| 2026-10-17 | `remote/space.galaxymind/galaxy-mind` | 2026-10-17T155839368616 -> 2026-10-17T185233003691 | 3 changed, 2 removed | quiet |
| 2026-10-17 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-17T155846465392 -> 2026-10-17T185232726340 | 2 changed | quiet |
| 2026-10-17 | `remote/dev.workers.kikoribera03.flat-rate-llm/x402-tools` | 2026-10-17T155837212940 -> 2026-10-17T185239814160 | 1 changed | review |
| 2026-10-17 | `remote/build.naru/contract-compass` | 2026-10-17T054720060564 -> 2026-10-17T185228384116 | 2 changed | quiet |
| 2026-10-17 | `remote/io.github.TheRundown/documentation` | 2026-10-17T155833612222 -> 2026-10-17T185225317144 | 1 changed | quiet |
| 2026-10-17 | `remote/dev.zhiyong.easyshiftplan/shiftly-scheduling` | 2026-10-17T054259277201 -> 2026-10-17T185225714896 | 3 changed | quiet |
| 2026-10-17 | `remote/com.clypmint/clypmint` | 2026-10-17T054406542832 -> 2026-10-17T185223721462 | 2 changed, 1 added | quiet |
| 2026-10-17 | `remote/com.botsharper/botsharper` | 2026-10-17T155829786929 -> 2026-10-17T185218893678 | 2 added | quiet |
| 2026-10-17 | `remote/app.sallim/contract-compass` | 2026-10-17T054223408398 -> 2026-10-17T185220617217 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 21783 substantive, 8140 that changed only numbers (a catalogue counter ticking, a date), 454 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 14726 | 7201 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 126 | 126 | 0 | 0 |
| `sistaminuten.se` | 110 | 4 | 0 | 106 |
| `afbudsrejser.dk` | 109 | 4 | 0 | 105 |
| `akkilahdot.fi` | 109 | 4 | 0 | 105 |
| `restplass.no` | 109 | 4 | 0 | 105 |
| `socialloop.ai` | 106 | 106 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `fundinglandscape.com` | 80 | 48 | 32 | 0 |
| `remoshift.com` | 80 | 6 | 74 | 0 |
| 3790 other operators | 11731 | 11189 | 509 | 33 |
