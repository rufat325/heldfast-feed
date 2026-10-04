# MCP server tool changes

Last change observed 2026-10-04T12:43:34+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 19746 hosted endpoints (read daily, and every four hours while they keep changing).

19363 changes to a tool definition: 696 npm releases (450 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 18667 readings of hosted servers that found their tools changed; 218 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-04 | `remote/com.ifa-wisdom/library` | 2026-09-23T160843207938 -> 2026-10-04T124336226882 | 7 changed (every tool) | quiet |
| 2026-10-04 | `remote/io.taifoon/coordination-layer` | 2026-10-03T232153787028 -> 2026-10-04T124325382653 | 10 added | review |
| 2026-10-04 | `remote/io.github.JakubTrousil/agentsjunction` | 2026-10-03T121352489352 -> 2026-10-04T124321519022 | 2 added | quiet |
| 2026-10-04 | `remote/no.restplass/travel-search` | 2026-10-04T062343299823 -> 2026-10-04T124320343852 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.sajeetharan/devglobe` | 2026-09-23T163129707106 -> 2026-10-04T124307237698 | 1 changed | quiet |
| 2026-10-04 | `remote/se.sistaminuten/travel-search` | 2026-10-04T062403870230 -> 2026-10-04T124305840087 | 1 changed | quiet |
| 2026-10-04 | `remote/dk.afbudsrejser/travel-search` | 2026-10-04T062341021730 -> 2026-10-04T124259958649 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.ogasurfproject-jpg/horizon-shield-webmcp` | 2026-09-27T065956129605 -> 2026-10-04T124253085635 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.cyanheads/usgs-water-mcp-server` | 2026-09-25T120620161269 -> 2026-10-04T124245095092 | 2 changed | quiet |
| 2026-10-04 | `remote/com.thenewengineer/hvac` | 2026-10-02T210153062801 -> 2026-10-04T124242977538 | 1 changed | quiet |
| 2026-10-04 | `remote/cc.thecolony/mcp-server` | 2026-10-02T130502173782 -> 2026-10-04T124241329758 | 1 changed, 1 added | quiet |
| 2026-10-04 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-03T135735695755 -> 2026-10-04T124236773827 | 1 added | quiet |
| 2026-10-04 | `remote/fi.akkilahdot/travel-search` | 2026-10-04T062340183318 -> 2026-10-04T124234174015 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.thinksuitesolution-coder/visibilityai` | 2026-10-03T121515293933 -> 2026-10-04T124221114896 | 1 added | quiet |
| 2026-10-04 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-03T135739414202 -> 2026-10-04T124219132385 | 1 changed, 1 added | quiet |
| 2026-10-04 | `remote/com.shipshapedata/shipshape-data` | 2026-10-03T121201803922 -> 2026-10-04T124204790984 | 1 changed | quiet |
| 2026-10-04 | `remote/cn.savantcat/ai-compliance` | 2026-09-23T163105447435 -> 2026-10-04T124157083300 | 2 added | quiet |
| 2026-10-04 | `remote/cn.savantcat/geo-cn` | 2026-09-24T120340404939 -> 2026-10-04T124152746000 | 3 added | quiet |
| 2026-10-04 | `remote/io.github.kotinder/roomcomm` | 2026-10-01T212519104306 -> 2026-10-04T124144645585 | 11 changed (every tool) | quiet |
| 2026-10-04 | `remote/app.sallim/korea-stay` | 2026-10-01T134508313421 -> 2026-10-04T124145628468 | 1 changed | quiet |
| 2026-10-04 | `remote/com.shipshapedata/shipshape-data-docs` | 2026-10-03T120011493822 -> 2026-10-04T124142477949 | 1 changed | quiet |
| 2026-10-04 | `remote/com.quintadb/mcp` | 2026-10-01T134154496598 -> 2026-10-04T124136784752 | 1 changed | quiet |
| 2026-10-04 | `remote/io.railagent/railagent` | 2026-10-02T061619093234 -> 2026-10-04T124132133689 | 1 changed | quiet |
| 2026-10-04 | `remote/ua.com.quintadb/mcp` | 2026-10-01T134045550376 -> 2026-10-04T124133991121 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.cyanheads/pubmed-mcp-server` | 2026-09-28T073024260317 -> 2026-10-04T124131382866 | 6 changed | quiet |
| 2026-10-04 | `remote/io.github.Perufitlife/postwire-mcp` | 2026-10-03T192909356144 -> 2026-10-04T124122639644 | 1 changed, 1 added | quiet |
| 2026-10-04 | `remote/com.searchfragments/search-fragments` | 2026-10-03T192909353707 -> 2026-10-04T124122870738 | 1 changed | quiet |
| 2026-10-04 | `remote/com.plainrouter/mcp` | 2026-10-04T054932774962 -> 2026-10-04T124117873310 | 3 changed | quiet |
| 2026-10-04 | `remote/ru.quintadb/mcp` | 2026-10-01T134239565283 -> 2026-10-04T124112340845 | 1 changed | quiet |
| 2026-10-04 | `remote/cc.roboparts/roboparts` | 2026-09-25T120508182707 -> 2026-10-04T124110159318 | 5 added | quiet |
| 2026-10-04 | `remote/es.cesaryague/paki-curator` | 2026-10-02T182724554839 -> 2026-10-04T124108215037 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.AlvisoOculus/optionsahoy-mcp` | 2026-09-23T162906582343 -> 2026-10-04T124104367905 | 5 changed | quiet |
| 2026-10-04 | `remote/com.remoshift/jobs` | 2026-10-04T054918948610 -> 2026-10-04T124104529703 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.cyanheads/open-meteo-mcp-server` | 2026-09-23T160846920335 -> 2026-10-04T124038780688 | 10 changed | quiet |
| 2026-10-04 | `remote/net.clickwise/product-catalog` | 2026-10-03T135709344480 -> 2026-10-04T124035467556 | 1 added | quiet |
| 2026-10-04 | `remote/ua.com.mfoxa/catalog` | 2026-09-23T160832030319 -> 2026-10-04T124016323260 | 2 changed | quiet |
| 2026-10-04 | `remote/io.github.linxule/mcp-music-studio` | 2026-10-03T135709729687 -> 2026-10-04T124013585433 | 7 changed | quiet |
| 2026-10-04 | `remote/com.meettempi/tempi` | 2026-10-02T182605263293 -> 2026-10-04T124012403515 | 4 changed | quiet |
| 2026-10-04 | `remote/com.tkawen/intelligence-gateway` | 2026-10-04T062407242980 -> 2026-10-04T123955982057 | 4 added | quiet |
| 2026-10-04 | `remote/io.github.worklittle/jobs` | 2026-10-04T054851675887 -> 2026-10-04T123954288653 | 1 changed | quiet |
| 2026-10-04 | `remote/com.ruzora/ruzora` | 2026-09-23T162724041836 -> 2026-10-04T123932116520 | 7 changed (every tool) | quiet |
| 2026-10-04 | `remote/ai.greenlandai/greenlandai` | 2026-10-04T054645413143 -> 2026-10-04T123931847164 | 1 added | quiet |
| 2026-10-04 | `remote/tech.monarkgate/monark` | 2026-09-25T120236803259 -> 2026-10-04T123916056036 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.truefixr/atlascast-truefixr` | 2026-10-04T054611323867 -> 2026-10-04T123902324539 | 6 changed (every tool) | review |
| 2026-10-04 | `remote/io.github.aristiun/aribot` | 2026-10-04T054609789989 -> 2026-10-04T123900703022 | 2 added | quiet |
| 2026-10-04 | `remote/com.hergertsynthora/synthora-x402` | 2026-10-03T192853223454 -> 2026-10-04T123854736965 | 1 changed, 41 added, 23 removed | review |
| 2026-10-04 | `remote/com.hireahelper/mcp` | 2026-09-29T003553196372 -> 2026-10-04T123845565936 | 16 added | quiet |
| 2026-10-04 | `remote/io.guestgraph/mental-model` | 2026-10-02T182502698925 -> 2026-10-04T123844243310 | 1 changed | quiet |
| 2026-10-04 | `remote/com.goaimoat/ai-visibility` | 2026-09-23T162647692963 -> 2026-10-04T123842657585 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.jmrplens/libgen-mcp` | 2026-09-23T202239811850 -> 2026-10-04T123838236518 | 3 changed | quiet |
| 2026-10-04 | `remote/io.github.makimmigration/mak-immigration-source-guide` | 2026-10-01T133754803624 -> 2026-10-04T123835063867 | 3 changed (every tool) | quiet |
| 2026-10-04 | `remote/io.insourcia/insourcia` | 2026-10-03T192845171671 -> 2026-10-04T123835556206 | 2 changed | quiet |
| 2026-10-04 | `remote/io.github.ogasurfproject-jpg/horizon-shield` | 2026-10-03T054730366502 -> 2026-10-04T123831610860 | 1 changed | quiet |
| 2026-10-04 | `remote/dev.horizonshield/horizon-shield` | 2026-10-03T054730433968 -> 2026-10-04T123831557776 | 1 changed | quiet |
| 2026-10-04 | `remote/io.companygraph/mental-model` | 2026-10-02T182447249170 -> 2026-10-04T123829581538 | 1 changed | quiet |
| 2026-10-04 | `remote/com.donebear/donebear` | 2026-10-03T054736935533 -> 2026-10-04T123826278732 | 1 changed | quiet |
| 2026-10-04 | `remote/com.ayurak/aribot-mcp` | 2026-10-04T054627594359 -> 2026-10-04T123816845300 | 2 added | quiet |
| 2026-10-04 | `remote/cz.cenaodhad/cenaodhad` | 2026-09-27T065706795305 -> 2026-10-04T123817897978 | 4 changed, 2 added | quiet |
| 2026-10-04 | `remote/kr.ibtcc/competition-ratio` | 2026-09-23T162552282245 -> 2026-10-04T123806859253 | 1 changed, 4 added, 1 removed | quiet |
| 2026-10-04 | `remote/ch.blust/mental-model` | 2026-10-02T182357326653 -> 2026-10-04T123755323290 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 14246 substantive, 4841 that changed only numbers (a catalogue counter ticking, a date), 276 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 10193 | 5683 | 4510 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `caseyjhand.com` | 72 | 72 | 0 | 0 |
| `sistaminuten.se` | 68 | 2 | 0 | 66 |
| `afbudsrejser.dk` | 67 | 2 | 0 | 65 |
| `akkilahdot.fi` | 67 | 2 | 0 | 65 |
| `restplass.no` | 67 | 2 | 0 | 65 |
| `socialloop.ai` | 65 | 65 | 0 | 0 |
| `dayze.com` | 63 | 63 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| 2102 other operators | 5788 | 5442 | 331 | 15 |
