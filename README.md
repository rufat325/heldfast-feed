# MCP server tool changes

Last change observed 2026-10-25T13:24:38+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

49856 changes to a tool definition: 2189 npm releases (1943 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 47667 readings of hosted servers that found their tools changed; 2592 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-25 | `remote/io.github.eamwhite1/agent-trust` | 2026-10-25T052258299269 -> 2026-10-25T132438974724 | 4 changed | quiet |
| 2026-10-25 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-10-24T224634685795 -> 2026-10-25T132435618143 | 5 changed, 20 added | quiet |
| 2026-10-25 | `remote/cc.thecolony/mcp-server` | 2026-10-24T190423950720 -> 2026-10-25T132517412136 | 4 changed, 7 added | quiet |
| 2026-10-25 | `remote/com.zinvyl/marketplace` | 2026-10-25T102720016043 -> 2026-10-25T132428445900 | 1 changed | quiet |
| 2026-10-25 | `remote/studio.gradients/mcp` | 2026-10-25T115819321464 -> 2026-10-25T132425245148 | 1 changed | quiet |
| 2026-10-25 | `remote/fi.akkilahdot/travel-search` | 2026-10-25T115801182796 -> 2026-10-25T132424541734 | 1 changed | quiet |
| 2026-10-25 | `remote/co.civai.nova/support-agent-admin` | 2026-10-25T115538457363 -> 2026-10-25T132423866587 | 2 added | quiet |
| 2026-10-25 | `remote/io.github.sharan01x/usetested` | 2026-10-24T190429876990 -> 2026-10-25T132422526959 | 1 changed | quiet |
| 2026-10-25 | `remote/com.tkawen/intelligence-gateway` | 2026-10-25T115430308620 -> 2026-10-25T132421400632 | 1 changed | quiet |
| 2026-10-25 | `remote/no.restplass/travel-search` | 2026-10-25T115923200637 -> 2026-10-25T132419885562 | 1 changed | quiet |
| 2026-10-25 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-10-25T115939333322 -> 2026-10-25T132420442558 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-25T102507149803 -> 2026-10-25T132418219591 | 1 changed | quiet |
| 2026-10-25 | `remote/com.meridiandispatch/travel-guides` | 2026-10-25T052302343003 -> 2026-10-25T132418273731 | 1 changed | quiet |
| 2026-10-25 | `remote/dk.afbudsrejser/travel-search` | 2026-10-25T115840751227 -> 2026-10-25T132418638778 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.birdwell/runescape-wiki-mcp` | 2026-10-25T115603829239 -> 2026-10-25T132415411001 | 6 changed, 2 removed | quiet |
| 2026-10-25 | `remote/com.remoshift/jobs` | 2026-10-25T115553181733 -> 2026-10-25T132415677679 | 1 changed | quiet |
| 2026-10-25 | `remote/com.trustbaselab/rcb-data` | 2026-10-24T125755865524 -> 2026-10-25T132414932882 | 2 added | quiet |
| 2026-10-25 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-10-25T120058023712 -> 2026-10-25T132413527198 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.eamwhite1/xrpl-referee` | 2026-10-25T052304569005 -> 2026-10-25T132413167381 | 4 changed | quiet |
| 2026-10-25 | `remote/se.sistaminuten/travel-search` | 2026-10-25T120044708343 -> 2026-10-25T132412107601 | 1 changed | quiet |
| 2026-10-25 | `remote/io.taifoon/coordination-layer.1` | 2026-10-25T102526210796 -> 2026-10-25T132412473355 | 1 changed | review |
| 2026-10-25 | `remote/ai.subpay/tool-finder` | 2026-10-25T102358649027 -> 2026-10-25T132411420662 | 1 changed | quiet |
| 2026-10-25 | `remote/ca.movahedi/privacy` | 2026-10-24T112636077246 -> 2026-10-25T132408495074 | 1 changed | quiet |
| 2026-10-25 | `remote/com.kernelcad/kernelcad` | 2026-10-25T052245135295 -> 2026-10-25T132401796655 | 3 changed | quiet |
| 2026-10-25 | `remote/io.github.smithdavedesign/botchelor` | 2026-10-24T224558008944 -> 2026-10-25T132402457439 | 1 changed | quiet |
| 2026-10-25 | `remote/travel.phiphiparadise/booking` | 2026-10-25T102236360308 -> 2026-10-25T132359453116 | 2 changed | quiet |
| 2026-10-25 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-10-24T190341967200 -> 2026-10-25T132359099001 | 2 changed | quiet |
| 2026-10-25 | `remote/co.civai.nova/google-docs-agent` | 2026-10-25T115650736235 -> 2026-10-25T132401464612 | 2 added | quiet |
| 2026-10-25 | `remote/dev.pages.freetier-agent-api/freetier-agent-api` | 2026-10-25T114947334059 -> 2026-10-25T132353253836 | 1 changed, 4 added | review |
| 2026-10-25 | `remote/ai.analyticslegends/sap-analytics` | 2026-10-24T224550727079 -> 2026-10-25T132354295956 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.joelbarmettlerUZH/slidev-mcp` | 2026-10-24T112452213382 -> 2026-10-25T132352387230 | 2 changed | quiet |
| 2026-10-25 | `remote/com.aiapplyd/aiapplyd` | 2026-10-25T101907667726 -> 2026-10-25T132353064826 | 9 changed, 24 added, 8 removed | quiet |
| 2026-10-25 | `remote/io.github.tdavidson/mcp-hemrock` | 2026-10-24T112351481068 -> 2026-10-25T132348876138 | 3 changed | quiet |
| 2026-10-25 | `remote/io.github.peter120525-cmd/lawmadi-os` | 2026-10-25T115156338314 -> 2026-10-25T132349563267 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.Nutshell2000/agent-data-tools-prices` | 2026-10-25T052225682978 -> 2026-10-25T132350024470 | 11 changed | review |
| 2026-10-25 | `remote/cc.hlist/hlist-ai-tools` | 2026-10-24T224604272101 -> 2026-10-25T132347764249 | 1 changed | quiet |
| 2026-10-25 | `remote/online.sasame/research` | 2026-10-25T101835833294 -> 2026-10-25T132344918914 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-25T115015782011 -> 2026-10-25T132340962842 | 2 changed | quiet |
| 2026-10-25 | `remote/io.github.giuseppesocci-bot/kalicart-global` | 2026-10-25T115139359782 -> 2026-10-25T132342180062 | 1 changed | quiet |
| 2026-10-25 | `remote/io.taifoon/coordination-layer` | 2026-10-25T101542123701 -> 2026-10-25T132345280151 | 1 changed | review |
| 2026-10-25 | `remote/com.ce-net/ce-net` | 2026-10-25T114813233385 -> 2026-10-25T132342858248 | 1 changed, 3 added | quiet |
| 2026-10-25 | `remote/io.github.giuseppesocci-bot/kalicart-global.1` | 2026-10-25T114916601669 -> 2026-10-25T132338533322 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.whiteknightonhorse/apibase` | 2026-10-24T224553805129 -> 2026-10-25T132332958545 | 3 added, 3 removed | quiet |
| 2026-10-25 | `remote/io.github.morvs-ai/morvs` | 2026-10-25T101412830426 -> 2026-10-25T132328549579 | 4 added | quiet |
| 2026-10-25 | `remote/io.github.kburrus64-max/anansi-haven` | 2026-10-25T101248140289 -> 2026-10-25T132326084354 | 3 changed | review |
| 2026-10-25 | `remote/io.github.Nutshell2000/agent-data-tools-utilities` | 2026-10-25T052223744230 -> 2026-10-25T132327108902 | 17 changed, 1 added | review |
| 2026-10-25 | `remote/io.github.Nutshell2000/agent-data-tools-ai` | 2026-10-25T052224180704 -> 2026-10-25T132326244637 | 14 changed | review |
| 2026-10-25 | `remote/io.github.Nutshell2000/agent-data-tools-everyday` | 2026-10-25T052222842632 -> 2026-10-25T132325851242 | 4 changed | review |
| 2026-10-25 | `remote/io.github.Nutshell2000/agent-data-tools-chain` | 2026-10-25T052222532159 -> 2026-10-25T132326730943 | 63 changed | review |
| 2026-10-25 | `remote/io.github.Nutshell2000/agent-data-tools` | 2026-10-25T052222674632 -> 2026-10-25T132327158602 | 127 changed, 1 added | review |
| 2026-10-25 | `remote/io.github.Nutshell2000/agent-data-tools-web` | 2026-10-25T052224108350 -> 2026-10-25T132325008511 | 8 changed | review |
| 2026-10-25 | `remote/io.github.Nutshell2000/agent-data-tools-compliance` | 2026-10-24T111352554570 -> 2026-10-25T132322920667 | 10 changed | review |
| 2026-10-25 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-10-25T102532529774 -> 2026-10-25T120058023712 | 1 changed | quiet |
| 2026-10-25 | `remote/ai.usedby/usedby` | 2026-10-24T125808196711 -> 2026-10-25T120056066945 | 1 changed | quiet |
| 2026-10-25 | `remote/se.sistaminuten/travel-search` | 2026-10-25T102523670100 -> 2026-10-25T120044708343 | 1 changed | quiet |
| 2026-10-25 | `remote/si.zazidljiva/mcp` | 2026-09-28T142420632434 -> 2026-10-25T120041637933 | 1 changed | quiet |
| 2026-10-25 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-10-25T102607305944 -> 2026-10-25T115939333322 | 1 changed | quiet |
| 2026-10-25 | `remote/no.restplass/travel-search` | 2026-10-25T102553881915 -> 2026-10-25T115923200637 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.openaccountants/openaccountants` | 2026-10-17T122830576701 -> 2026-10-25T115920443970 | 1 changed | quiet |
| 2026-10-25 | `remote/dk.afbudsrejser/travel-search` | 2026-10-25T102518922105 -> 2026-10-25T115840751227 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 31782 substantive, 17437 that changed only numbers (a catalogue counter ticking, a date), 637 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 26731 | 10363 | 16368 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 775 | 775 | 0 | 0 |
| `caseyjhand.com` | 220 | 220 | 0 | 0 |
| `sistaminuten.se` | 151 | 4 | 0 | 147 |
| `afbudsrejser.dk` | 150 | 4 | 0 | 146 |
| `akkilahdot.fi` | 150 | 4 | 0 | 146 |
| `restplass.no` | 150 | 4 | 0 | 146 |
| `socialloop.ai` | 145 | 145 | 0 | 0 |
| `remoshift.com` | 120 | 8 | 112 | 0 |
| `fundinglandscape.com` | 115 | 74 | 41 | 0 |
| `openkrill.app` | 111 | 111 | 0 | 0 |
| 5609 other operators | 18697 | 17729 | 916 | 52 |
