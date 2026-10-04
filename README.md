# MCP server tool changes

Last change observed 2026-10-04T06:24:05+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 19746 hosted endpoints (read daily, and every four hours while they keep changing).

19236 changes to a tool definition: 692 npm releases (446 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 18544 readings of hosted servers that found their tools changed; 215 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-04 | `remote/com.tkawen/intelligence-gateway` | 2026-10-02T182616164208 -> 2026-10-04T062407242980 | 4 removed | quiet |
| 2026-10-04 | `remote/se.sistaminuten/travel-search` | 2026-10-04T055210591867 -> 2026-10-04T062403870230 | 1 changed | quiet |
| 2026-10-04 | `remote/com.koskamo/koskamo` | 2026-10-04T054548459453 -> 2026-10-04T062358887973 | 8 changed (every tool) | quiet |
| 2026-10-04 | `remote/io.github.UltraStarz/x402-extract` | 2026-10-04T054355363025 -> 2026-10-04T062356078958 | 2 added | review |
| 2026-10-04 | `remote/no.restplass/travel-search` | 2026-10-04T055117562807 -> 2026-10-04T062343299823 | 1 changed | quiet |
| 2026-10-04 | `remote/dk.afbudsrejser/travel-search` | 2026-10-04T055057428250 -> 2026-10-04T062341021730 | 1 changed | quiet |
| 2026-10-04 | `remote/fi.akkilahdot/travel-search` | 2026-10-04T055032372584 -> 2026-10-04T062340183318 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-10-04T055001386760 -> 2026-10-04T062338601347 | 15 changed | review |
| 2026-10-04 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-04T054946332948 -> 2026-10-04T062335866971 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.marcioyoshida/outage-me` | 2026-10-04T054845068481 -> 2026-10-04T062333192967 | 1 added | quiet |
| 2026-10-04 | `remote/dev.workers.mars-economic.mars-economic-agent-gateway/mars-economic` | 2026-10-04T054612014281 -> 2026-10-04T062334065469 | 1 added | quiet |
| 2026-10-04 | `remote/com.thefilmradar/filmlab` | 2026-10-04T054546886525 -> 2026-10-04T062326543137 | 1 changed | quiet |
| 2026-10-04 | `remote/dev.fetchgate/fetchgate` | 2026-10-04T054348065567 -> 2026-10-04T062324295789 | 1 changed | quiet |
| 2026-10-04 | `remote/com.googleapis.bigtableadmin/mcp` | 2026-10-03T192831593708 -> 2026-10-04T062322909968 | 3 changed | quiet |
| 2026-10-04 | `remote/io.tapeline/tapeline` | 2026-10-03T054712891192 -> 2026-10-04T062321429169 | 1 changed, 3 removed | quiet |
| 2026-10-04 | `remote/io.github.hermoso-ai/hermoso` | 2026-10-03T232123924416 -> 2026-10-04T062320934702 | 59 changed | quiet |
| 2026-10-04 | `remote/sh.stipple/openwarrant` | 2026-09-28T073234600533 -> 2026-10-04T055227305876 | 1 changed | quiet |
| 2026-10-04 | `remote/se.sistaminuten/travel-search` | 2026-10-03T232155958624 -> 2026-10-04T055210591867 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.tjcgraham-rgb/gaip-trust-assurance` | 2026-10-01T154254561587 -> 2026-10-04T055210396777 | 1 changed | quiet |
| 2026-10-04 | `remote/uk.co.gigstamp/gigstamp` | 2026-09-28T104340798402 -> 2026-10-04T055153849286 | 3 changed | quiet |
| 2026-10-04 | `remote/io.github.shoutsid-lab/webcap` | 2026-09-28T142321981131 -> 2026-10-04T055144468838 | 1 changed | quiet |
| 2026-10-04 | `remote/ai.undetectedgpt/humanizer` | 2026-09-24T202627862029 -> 2026-10-04T055125236202 | 1 changed | quiet |
| 2026-10-04 | `remote/sh.stipple/stipple-tenders` | 2026-09-28T073212425619 -> 2026-10-04T055122603940 | 1 changed | quiet |
| 2026-10-04 | `remote/no.restplass/travel-search` | 2026-10-03T232154076295 -> 2026-10-04T055117562807 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.openaccountants/openaccountants` | 2026-09-23T163139804995 -> 2026-10-04T055114706272 | 1 changed | quiet |
| 2026-10-04 | `remote/com.toolfound/toolfound` | 2026-10-02T210153056408 -> 2026-10-04T055114545780 | 4 added | quiet |
| 2026-10-04 | `remote/uk.co.transitradar/transitradar` | 2026-09-29T003617447737 -> 2026-10-04T055113669127 | 1 changed, 2 added | quiet |
| 2026-10-04 | `remote/world.tidelight/tidelight` | 2026-09-23T160810520138 -> 2026-10-04T055109595155 | 2 changed, 2 added | quiet |
| 2026-10-04 | `remote/com.finerxfinder/finerx` | 2026-09-23T163132283010 -> 2026-10-04T055105706945 | 3 changed, 4 added | quiet |
| 2026-10-04 | `remote/com.thefomite/fomite` | 2026-10-03T120028085851 -> 2026-10-04T055103512140 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.CodePhantom-1/ddmarketer-mcp` | 2026-09-28T142304611507 -> 2026-10-04T055101666229 | 1 changed | quiet |
| 2026-10-04 | `remote/dk.afbudsrejser/travel-search` | 2026-10-03T232151975723 -> 2026-10-04T055057428250 | 1 changed | quiet |
| 2026-10-04 | `remote/com.sssnack/sssnack` | 2026-09-27T070355018966 -> 2026-10-04T055053705357 | 8 changed, 2 added | quiet |
| 2026-10-04 | `remote/com.ikeytz/website` | 2026-09-26T114340789734 -> 2026-10-04T055049664899 | 10 changed | quiet |
| 2026-10-04 | `remote/io.github.modern-ai-inc/w0-mcp-server` | 2026-09-23T163106463750 -> 2026-10-04T055046501740 | 1 changed, 1 added | quiet |
| 2026-10-04 | `remote/io.github.tjcgraham-rgb/gaip-witness` | 2026-10-02T130137066893 -> 2026-10-04T055049332333 | 1 changed | quiet |
| 2026-10-04 | `remote/ar.com.consignatarias/cattle-market` | 2026-09-23T162936771856 -> 2026-10-04T055037685841 | 4 changed | quiet |
| 2026-10-04 | `remote/io.github.upforge-dev/upforge` | 2026-09-26T051335379107 -> 2026-10-04T055040696213 | 1 added | quiet |
| 2026-10-04 | `remote/io.github.Embassy-of-the-Free-Mind/sourcelibrary` | 2026-09-24T202743478937 -> 2026-10-04T055035495916 | 1 changed | quiet |
| 2026-10-04 | `remote/com.universalagentforum/forum` | 2026-09-27T160650091254 -> 2026-10-04T055035277498 | 1 changed | quiet |
| 2026-10-04 | `remote/page.twocents/twocents` | 2026-09-23T163054335294 -> 2026-10-04T055034100617 | 2 changed | quiet |
| 2026-10-04 | `remote/fi.akkilahdot/travel-search` | 2026-10-03T232145676682 -> 2026-10-04T055032372584 | 1 changed | quiet |
| 2026-10-04 | `remote/ai.verticalmarketplace/vertical-marketplace` | 2026-10-02T061629093941 -> 2026-10-04T055020489609 | 5 changed, 1 added | quiet |
| 2026-10-04 | `remote/io.github.portneymk/stochastic-parrot` | 2026-09-23T163043711719 -> 2026-10-04T055018426249 | 4 added | quiet |
| 2026-10-04 | `remote/dev.workers.panda198271.tw-game-release/game-release` | 2026-09-28T142556869273 -> 2026-10-04T055015681689 | 5 added | quiet |
| 2026-10-04 | `remote/com.serdaroztetik/call-me` | 2026-09-23T160742291699 -> 2026-10-04T055014825730 | 2 changed | quiet |
| 2026-10-04 | `remote/io.github.cyanheads/sanctions-screening-mcp-server` | 2026-09-26T045350933482 -> 2026-10-04T055007223482 | 7 changed (every tool) | quiet |
| 2026-10-04 | `remote/io.github.Kabrawala/pubsec-sales-mcp` | 2026-09-23T160907593798 -> 2026-10-04T055006070844 | 1 changed | quiet |
| 2026-10-04 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-03T054743271458 -> 2026-10-04T055007013376 | 1 changed | quiet |
| 2026-10-04 | `remote/com.tickerinside/tickerinside-mcp` | 2026-09-30T060129548571 -> 2026-10-04T055005254474 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-10-03T232149147831 -> 2026-10-04T055001386760 | 15 changed | review |
| 2026-10-04 | `remote/com.luxurylodgingpm.stay/luxury-lodging` | 2026-10-03T054738744060 -> 2026-10-04T054959680415 | 1 changed | quiet |
| 2026-10-04 | `remote/com.predictionmarketspicks/quant` | 2026-10-03T054745713003 -> 2026-10-04T055000355368 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.89rat/code402` | 2026-09-29T061625874365 -> 2026-10-04T054953854342 | 8 changed | quiet |
| 2026-10-04 | `remote/com.quietstance/workflow-assessment` | 2026-09-30T152230209454 -> 2026-10-04T054951057837 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-03T232138026218 -> 2026-10-04T054946332948 | 1 changed | quiet |
| 2026-10-04 | `remote/com.neuronto/x402-payments-facilitator` | 2026-09-23T160853235712 -> 2026-10-04T054947994294 | 2 added | quiet |
| 2026-10-04 | `remote/io.github.SiliconAnalysts/silicon-analysts` | 2026-09-29T061649084344 -> 2026-10-04T054941277406 | 1 changed | review |
| 2026-10-04 | `remote/org.opentaskrelay/open-task-relay` | 2026-10-03T115914515301 -> 2026-10-04T054940703140 | 2 changed | quiet |
| 2026-10-04 | `remote/cloud.nttzen.secdb/zen-secdb` | 2026-09-27T065902521547 -> 2026-10-04T054942701694 | 11 changed (every tool) | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 14151 substantive, 4814 that changed only numbers (a catalogue counter ticking, a date), 271 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 10171 | 5681 | 4490 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `caseyjhand.com` | 69 | 69 | 0 | 0 |
| `sistaminuten.se` | 67 | 2 | 0 | 65 |
| `afbudsrejser.dk` | 66 | 2 | 0 | 64 |
| `akkilahdot.fi` | 66 | 2 | 0 | 64 |
| `restplass.no` | 66 | 2 | 0 | 64 |
| `socialloop.ai` | 65 | 65 | 0 | 0 |
| `dayze.com` | 63 | 63 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| 2089 other operators | 5690 | 5352 | 324 | 14 |
