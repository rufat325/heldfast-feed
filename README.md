# MCP server tool changes

Last change observed 2026-11-10T15:33:35+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

87790 changes to a tool definition: 3831 npm releases (3585 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 83959 readings of hosted servers that found their tools changed; 3708 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-10 | `remote/dev.zambo/zambo` | 2026-11-07T203338741694 -> 2026-11-10T153336720371 | 36 changed (every tool) | quiet |
| 2026-11-10 | `remote/com.youspot/youspot` | 2026-11-06T144937773864 -> 2026-11-10T153336585260 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.eamwhite1/agent-trust` | 2026-11-03T195520916339 -> 2026-11-10T153333252570 | 1 changed | quiet |
| 2026-11-10 | `remote/xyz.x402helper/mcp` | 2026-11-10T130358888157 -> 2026-11-10T153331100910 | 2 changed | quiet |
| 2026-11-10 | `remote/io.github.kwizzlesurp10-ctrl/x402-mcp` | 2026-11-07T063958755200 -> 2026-11-10T153326804657 | 2 changed | quiet |
| 2026-11-10 | `remote/com.rightshold/rightshold` | 2026-11-06T072813830751 -> 2026-11-10T153304014148 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.joegra2003/metamodel` | 2026-09-23T160846577246 -> 2026-11-10T153250756064 | 3 changed, 1 removed (every tool) | quiet |
| 2026-11-10 | `remote/com.whirrwork/whirrwork` | 2026-11-07T133400808234 -> 2026-11-10T153157226396 | 1 added | quiet |
| 2026-11-10 | `remote/com.trygoppa/goppa` | 2026-11-05T115323830195 -> 2026-11-10T153104902724 | 2 changed | quiet |
| 2026-11-10 | `remote/world.agentindex/x402` | 2026-10-21T122211246556 -> 2026-11-10T153105014183 | 2 added | quiet |
| 2026-11-10 | `remote/com.triremes/triremes` | 2026-11-05T010647163174 -> 2026-11-10T153102585834 | 1 changed | quiet |
| 2026-11-10 | `remote/kr.pe.trading/community` | 2026-11-06T144737080746 -> 2026-11-10T153058797624 | 19 changed | quiet |
| 2026-11-10 | `remote/net.tichat.tradehub/tradehub.1` | 2026-11-05T222208226821 -> 2026-11-10T153058126948 | 4 changed, 1 added | quiet |
| 2026-11-10 | `remote/co.totalcms/docs` | 2026-10-29T063228167174 -> 2026-11-10T153055674244 | 3 changed | quiet |
| 2026-11-10 | `remote/io.github.bowenerchen/cipherhub` | 2026-11-06T072813258806 -> 2026-11-10T153054426859 | 1 changed | quiet |
| 2026-11-10 | `remote/no.restplass/travel-search` | 2026-11-10T130421487590 -> 2026-11-10T153041086779 | 1 changed | quiet |
| 2026-11-10 | `remote/com.tieredtravel/travel` | 2026-11-04T150511970343 -> 2026-11-10T153040968315 | 4 changed (every tool) | quiet |
| 2026-11-10 | `remote/com.zaimhub/catalog` | 2026-09-29T131732362389 -> 2026-11-10T153036582230 | 2 changed | quiet |
| 2026-11-10 | `remote/com.themassprint/massprint` | 2026-11-10T130340894018 -> 2026-11-10T153034380018 | 2 changed | quiet |
| 2026-11-10 | `remote/com.thejohnsislander/the-johns-islander` | 2026-11-05T222204708176 -> 2026-11-10T153032779143 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.exquad/thecablecode` | 2026-11-10T030018728406 -> 2026-11-10T153030883724 | 1 changed | quiet |
| 2026-11-10 | `remote/com.meridiandispatch/travel-guides` | 2026-11-07T133847862961 -> 2026-11-10T153029773670 | 3 changed | quiet |
| 2026-11-10 | `remote/xn--3ds443g.xn--s7y/duan-online` | 2026-11-04T150831218846 -> 2026-11-10T153029087384 | 5 changed, 1 added | quiet |
| 2026-11-10 | `remote/io.github.cadi27tech/3descu-quote` | 2026-10-19T135627748590 -> 2026-11-10T153030438218 | 1 changed | quiet |
| 2026-11-10 | `remote/com.thailandstayplan/thailand-stay-plan` | 2026-11-02T163702659297 -> 2026-11-10T153029890635 | 1 changed, 5 added | quiet |
| 2026-11-10 | `remote/com.iscabox/iscabox` | 2026-11-07T203340411782 -> 2026-11-10T153025541653 | 4 changed | quiet |
| 2026-11-10 | `remote/io.github.theguysaccount/tellscreen` | 2026-11-02T163655972919 -> 2026-11-10T153020280006 | 4 added, 4 removed | quiet |
| 2026-11-10 | `remote/il.co.taseli/taseli.1` | 2026-11-09T165925540184 -> 2026-11-10T153017470093 | 1 changed | quiet |
| 2026-11-10 | `remote/com.finn.www/auto` | 2026-11-09T170345203627 -> 2026-11-10T153016707298 | 2 changed | quiet |
| 2026-11-10 | `remote/com.tapeperp/tape` | 2026-10-31T130118768049 -> 2026-11-10T153014905057 | 11 changed (every tool) | quiet |
| 2026-11-10 | `remote/io.github.t0ll-xyz/toll` | 2026-11-09T165919614172 -> 2026-11-10T153010824028 | 1 added | quiet |
| 2026-11-10 | `remote/io.deeplead/deeplead` | 2026-11-07T133807856096 -> 2026-11-10T153011722066 | 1 changed, 2 added | review |
| 2026-11-10 | `remote/se.sistaminuten/travel-search` | 2026-11-10T130416153981 -> 2026-11-10T153002644782 | 1 changed | quiet |
| 2026-11-10 | `remote/dk.afbudsrejser/travel-search` | 2026-11-10T130415129365 -> 2026-11-10T152957171029 | 1 changed | quiet |
| 2026-11-10 | `remote/com.quantum-expectations/quantum-expectations` | 2026-10-28T133457317251 -> 2026-11-10T152957435883 | 13 changed (every tool) | quiet |
| 2026-11-10 | `remote/com.dharmikvibes/studio` | 2026-10-26T133501681147 -> 2026-11-10T152957394242 | 2 added | quiet |
| 2026-11-10 | `remote/ai.subpay/document-reader` | 2026-10-17T060213634734 -> 2026-11-10T152956634365 | 1 changed | quiet |
| 2026-11-10 | `remote/com.onlyworlds/mcp` | 2026-11-10T130414819496 -> 2026-11-10T152952764371 | 3 changed | quiet |
| 2026-11-10 | `remote/com.niubiagent/niubiagent` | 2026-10-17T055613616605 -> 2026-11-10T152951384648 | 2 added | quiet |
| 2026-11-10 | `remote/io.github.northsideventuresllc-sketch/northside-intelligence` | 2026-09-28T142631760702 -> 2026-11-10T152948069087 | 1 changed | review |
| 2026-11-10 | `remote/io.github.Standard-Trade/trade-evidence` | 2026-11-07T133239337723 -> 2026-11-10T152946131167 | 3 changed, 2 added | quiet |
| 2026-11-10 | `remote/de.llms-txt-generator/llms-txt` | 2026-10-01T134631213336 -> 2026-11-10T152945357154 | 1 changed | quiet |
| 2026-11-10 | `remote/org.warriorsfund/wounded-warriors` | 2026-10-21T202554890863 -> 2026-11-10T152941345679 | 2 changed | quiet |
| 2026-11-10 | `remote/com.jobcrawls/connector` | 2026-11-05T222229027889 -> 2026-11-10T152941335688 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-11-10T130336116585 -> 2026-11-10T152939799967 | 1 changed, 17 removed | quiet |
| 2026-11-10 | `remote/com.hoteldiscount24/hotels` | 2026-11-05T115536151493 -> 2026-11-10T152937618394 | 1 added | quiet |
| 2026-11-10 | `remote/studio.gradients/mcp` | 2026-11-10T130428255568 -> 2026-11-10T152936307543 | 1 changed | quiet |
| 2026-11-10 | `remote/pro.germanexam/germanexam` | 2026-10-29T133838803880 -> 2026-11-10T152936019735 | 2 changed | quiet |
| 2026-11-10 | `remote/io.github.sniffpup/sniffpup` | 2026-11-03T024224979598 -> 2026-11-10T152930663676 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.kkfir13/valuedge` | 2026-11-03T144934398470 -> 2026-11-10T152930111292 | 2 changed, 13 added | quiet |
| 2026-11-10 | `remote/com.coverage-rights/coverage-rights` | 2026-11-04T150713280320 -> 2026-11-10T152929252989 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.EasyGerber/easygerber` | 2026-11-03T122636076720 -> 2026-11-10T152925428351 | 7 changed | quiet |
| 2026-11-10 | `remote/io.github.roman-rr/trading-signals` | 2026-11-05T150723738766 -> 2026-11-10T152920252209 | 1 changed | quiet |
| 2026-11-10 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-06T072827377142 -> 2026-11-10T152919313429 | 1 changed | quiet |
| 2026-11-10 | `remote/co.shopwithin/within` | 2026-11-02T163549156252 -> 2026-11-10T152915845072 | 11 changed, 15 added (every tool) | quiet |
| 2026-11-10 | `remote/fi.akkilahdot/travel-search` | 2026-11-10T130421219703 -> 2026-11-10T152911324734 | 1 changed | quiet |
| 2026-11-10 | `remote/ai.trydock/dock` | 2026-11-08T000127917588 -> 2026-11-10T152908134829 | 4 changed | quiet |
| 2026-11-10 | `remote/com.trustbaselab/rcb-data` | 2026-10-30T132853705563 -> 2026-11-10T152909549307 | 4 added | quiet |
| 2026-11-10 | `remote/fun.trnch/trnch` | 2026-11-06T144705378643 -> 2026-11-10T152907111836 | 1 changed | quiet |
| 2026-11-10 | `remote/ai.whatsupin/events` | 2026-11-06T072803537223 -> 2026-11-10T152902235314 | 6 changed (every tool) | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 53759 substantive, 33097 that changed only numbers (a catalogue counter ticking, a date), 934 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 46983 | 15900 | 31083 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1975 | 1975 | 0 | 0 |
| `caseyjhand.com` | 364 | 364 | 0 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `civai.co` | 236 | 236 | 0 | 0 |
| `sistaminuten.se` | 219 | 6 | 0 | 213 |
| `afbudsrejser.dk` | 218 | 6 | 0 | 212 |
| `akkilahdot.fi` | 218 | 6 | 0 | 212 |
| `restplass.no` | 218 | 6 | 0 | 212 |
| `socialloop.ai` | 210 | 210 | 0 | 0 |
| `revmesh2074.workers.dev` | 201 | 178 | 23 | 0 |
| 8507 other operators | 34349 | 32273 | 1991 | 85 |
