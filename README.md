# MCP server tool changes

Last change observed 2026-11-18T14:00:22+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

114109 changes to a tool definition: 4621 npm releases (4375 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 109488 readings of hosted servers that found their tools changed; 4367 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-18 | `remote/io.github.zerocrewai/zerocrew-directory` | 2026-11-03T145041002646 -> 2026-11-18T140023594292 | 1 added | quiet |
| 2026-11-18 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/sanctions-kyb-compliance` | 2026-11-13T120644711663 -> 2026-11-18T140018392221 | 1 changed | quiet |
| 2026-11-18 | `remote/xn--3ds443g.xn--s7y/duan-online` | 2026-11-17T234415314258 -> 2026-11-18T140016139446 | 4 changed | quiet |
| 2026-11-18 | `remote/uk.co.speedi/availability` | 2026-11-06T144949865503 -> 2026-11-18T140002558018 | 5 changed (every tool) | quiet |
| 2026-11-18 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-11-14T114955206130 -> 2026-11-18T140004068594 | 7 changed, 1 removed | quiet |
| 2026-11-18 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/email-uptime-web-reader` | 2026-11-13T120034265634 -> 2026-11-18T140003706508 | 1 changed | quiet |
| 2026-11-18 | `remote/watch.pcprice/used-prices` | 2026-10-27T145855849708 -> 2026-11-18T135951405729 | 1 changed | quiet |
| 2026-11-18 | `remote/ai.usedby/usedby` | 2026-11-17T164933687291 -> 2026-11-18T135950026259 | 2 changed | quiet |
| 2026-11-18 | `remote/dev.zambo/zambo` | 2026-11-12T155017194967 -> 2026-11-18T135948004260 | 37 changed (every tool) | review |
| 2026-11-18 | `remote/ai.modulos/demo-booking` | 2026-11-17T164941973665 -> 2026-11-18T135945954785 | 3 changed | quiet |
| 2026-11-18 | `remote/io.github.aanari/loacare-healthcare-pricing` | 2026-11-12T155319018631 -> 2026-11-18T135945268716 | 4 changed | quiet |
| 2026-11-18 | `remote/com.yachtcharterquotes/site` | 2026-11-12T155015779524 -> 2026-11-18T135943602668 | 2 changed | quiet |
| 2026-11-18 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-11-14T115025340309 -> 2026-11-18T135941558391 | 7 changed, 1 removed | quiet |
| 2026-11-18 | `remote/xyz.tereno/tereno` | 2026-11-15T071625856915 -> 2026-11-18T135940122375 | 5 added | review |
| 2026-11-18 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-service-search` | 2026-11-13T120040200122 -> 2026-11-18T135940620064 | 1 changed | quiet |
| 2026-11-18 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/cve-package-domain-security` | 2026-11-13T120040235180 -> 2026-11-18T135941289942 | 1 changed | quiet |
| 2026-11-18 | `remote/io.taifoon/coordination-layer.1` | 2026-11-18T080251121118 -> 2026-11-18T135936856276 | 3 changed | review |
| 2026-11-18 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/sec-filings-tenders` | 2026-11-13T120028379281 -> 2026-11-18T135933340926 | 1 changed | quiet |
| 2026-11-18 | `remote/com.immersivecommons/floor10` | 2026-11-03T145020720172 -> 2026-11-18T135934612329 | 36 changed (every tool) | quiet |
| 2026-11-18 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/fx-rates-news-weather-data` | 2026-11-13T120028665710 -> 2026-11-18T135932929188 | 1 changed | quiet |
| 2026-11-18 | `remote/studio.gradients/mcp` | 2026-11-18T080321818516 -> 2026-11-18T135930413508 | 1 changed | quiet |
| 2026-11-18 | `remote/se.sistaminuten/travel-search` | 2026-11-18T080251491026 -> 2026-11-18T135921819850 | 1 changed | quiet |
| 2026-11-18 | `remote/com.evalgate/evalgate` | 2026-11-12T155258852807 -> 2026-11-18T135922537116 | 5 added | quiet |
| 2026-11-18 | `remote/cn.tandiu/data` | 2026-11-07T133459487503 -> 2026-11-18T135915116496 | 1 changed | quiet |
| 2026-11-18 | `remote/dev.buddylists.www/buddylists` | 2026-09-23T162935461411 -> 2026-11-18T135905345865 | 1 changed | quiet |
| 2026-11-18 | `remote/com.starcovery/mcp` | 2026-11-14T183359964199 -> 2026-11-18T135904412282 | 1 changed | quiet |
| 2026-11-18 | `remote/fi.akkilahdot/travel-search` | 2026-11-18T080306183857 -> 2026-11-18T135855704807 | 1 changed | quiet |
| 2026-11-18 | `remote/de.mapumi/wunschzettel` | 2026-11-18T080304589144 -> 2026-11-18T135851897100 | 3 changed | quiet |
| 2026-11-18 | `remote/org.omenz.www/agent-tools` | 2026-11-18T080247165291 -> 2026-11-18T135911132345 | 38 changed, 9 added | review |
| 2026-11-18 | `remote/io.github.a21ai/worth` | 2026-10-31T130342971294 -> 2026-11-18T135851192756 | 3 changed (every tool) | quiet |
| 2026-11-18 | `remote/no.restplass/travel-search` | 2026-11-18T080228201075 -> 2026-11-18T135849372869 | 1 changed | quiet |
| 2026-11-18 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-18T080303215649 -> 2026-11-18T135847243158 | 1 changed | quiet |
| 2026-11-18 | `remote/ai.pulsegate/provenance` | 2026-10-18T113412731917 -> 2026-11-18T135844629201 | 2 changed | quiet |
| 2026-11-18 | `remote/com.whenworksforyou/wwfy` | 2026-10-17T055914233300 -> 2026-11-18T135838365862 | 2 changed | quiet |
| 2026-11-18 | `remote/io.ocolo.www/project-requests` | 2026-11-06T144831739600 -> 2026-11-18T135836660829 | 1 changed | quiet |
| 2026-11-18 | `remote/io.whatic/datasheets` | 2026-11-07T133630910060 -> 2026-11-18T135836756910 | 1 changed | quiet |
| 2026-11-18 | `remote/in.nebulatech/nebula` | 2026-11-02T163612125544 -> 2026-11-18T135834090887 | 2 changed | quiet |
| 2026-11-18 | `remote/io.kolmo.www/kolmo-mcp-server` | 2026-11-08T135848255293 -> 2026-11-18T135831316633 | 4 changed | quiet |
| 2026-11-18 | `remote/io.github.seasonsagents-art/webaz` | 2026-11-14T140126288514 -> 2026-11-18T135830306308 | 2 changed | quiet |
| 2026-11-18 | `remote/io.github.AKzar1el/mcp-web-validator` | 2026-09-23T162927825295 -> 2026-11-18T135830529762 | 8 changed, 1 added (every tool) | quiet |
| 2026-11-18 | `remote/com.kaicalls/kaicalls` | 2026-11-17T234401793437 -> 2026-11-18T135827258858 | 5 changed | quiet |
| 2026-11-18 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-11-17T164817825318 -> 2026-11-18T135822378601 | 10 changed, 1 added | quiet |
| 2026-11-18 | `remote/io.github.JcJamet/ia-qa-security` | 2026-11-17T164817760084 -> 2026-11-18T135822936394 | 4 changed, 1 added | quiet |
| 2026-11-18 | `remote/io.github.JcJamet/ia-qa-eval` | 2026-11-10T030046901726 -> 2026-11-18T135822480105 | 5 changed | quiet |
| 2026-11-18 | `remote/com.mikefluff/mikefluff` | 2026-10-19T135237490040 -> 2026-11-18T135822615440 | 3 changed | quiet |
| 2026-11-18 | `remote/au.vetjobs/vetjobs` | 2026-11-02T163543147439 -> 2026-11-18T135816491744 | 1 changed | quiet |
| 2026-11-18 | `remote/com.gaurmon/gaurmon` | 2026-11-09T170236652058 -> 2026-11-18T135816524441 | 1 changed | quiet |
| 2026-11-18 | `remote/net.fatstack/registry` | 2026-09-26T045432462112 -> 2026-11-18T135808060163 | 1 removed | quiet |
| 2026-11-18 | `remote/com.kulicadvisory/aictionbot-werkbank` | 2026-11-17T164925488169 -> 2026-11-18T135808531255 | 8 changed | quiet |
| 2026-11-18 | `remote/io.github.cyanheads/uniprot-mcp-server` | 2026-11-04T150436377428 -> 2026-11-18T135801376093 | 3 changed | quiet |
| 2026-11-18 | `remote/io.github.JcJamet/ia-qa-data` | 2026-11-08T135815272617 -> 2026-11-18T135801141834 | 1 changed | quiet |
| 2026-11-18 | `remote/gg.unicum/wot-stats` | 2026-11-14T183356959016 -> 2026-11-18T135801034788 | 2 changed | quiet |
| 2026-11-18 | `remote/com.iscabox/iscabox` | 2026-11-11T230929395620 -> 2026-11-18T135802444623 | 1 changed | quiet |
| 2026-11-18 | `remote/com.coveragecat/insurance` | 2026-11-12T074739728373 -> 2026-11-18T135756225501 | 2 changed | quiet |
| 2026-11-18 | `remote/travel.trip720/trip720` | 2026-11-12T155132168588 -> 2026-11-18T135747692807 | 1 changed | quiet |
| 2026-11-18 | `remote/ai.arcreport/ask` | 2026-11-17T031617223476 -> 2026-11-18T135746653978 | 4 changed | quiet |
| 2026-11-18 | `remote/com.anchorterminal/anchor-terminal` | 2026-11-15T212136112197 -> 2026-11-18T135745205064 | 23 changed (every tool) | quiet |
| 2026-11-18 | `remote/fr.dikoo/dikoo` | 2026-11-17T164802696790 -> 2026-11-18T135739611755 | 1 changed | quiet |
| 2026-11-18 | `remote/io.github.tighovh88-png/antarum` | 2026-11-16T163224685993 -> 2026-11-18T135723580124 | 1 changed | quiet |
| 2026-11-18 | `remote/com.aguasto.www/tools` | 2026-11-02T163835820389 -> 2026-11-18T135726784401 | 3 changed, 1 added (every tool) | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 72124 substantive, 40904 that changed only numbers (a catalogue counter ticking, a date), 1081 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 61815 | 23462 | 38353 | 0 |
| `a2awire.com` | 3240 | 3240 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 471 | 471 | 0 | 0 |
| `civai.co` | 368 | 368 | 0 | 0 |
| `modevc.com` | 349 | 349 | 0 | 0 |
| `revmesh2074.workers.dev` | 302 | 261 | 41 | 0 |
| `sistaminuten.se` | 252 | 6 | 0 | 246 |
| `afbudsrejser.dk` | 251 | 6 | 0 | 245 |
| `akkilahdot.fi` | 251 | 6 | 0 | 245 |
| `restplass.no` | 251 | 6 | 0 | 245 |
| `socialloop.ai` | 243 | 243 | 0 | 0 |
| 10151 other operators | 43975 | 41365 | 2510 | 100 |
