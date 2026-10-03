# MCP server tool changes

Last change observed 2026-10-03T23:21:55+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

18972 changes to a tool definition: 627 npm releases (381 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 18345 readings of hosted servers that found their tools changed; 197 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-10-03 | `remote/se.sistaminuten/travel-search` | 2026-10-03T192911608226 -> 2026-10-03T232155958624 | 1 changed | quiet |
| 2026-10-03 | `remote/world.agentindex/x402` | 2026-10-03T192913500419 -> 2026-10-03T232155580830 | 10 changed | quiet |
| 2026-10-03 | `remote/no.restplass/travel-search` | 2026-10-03T192912324155 -> 2026-10-03T232154076295 | 1 changed | quiet |
| 2026-10-03 | `remote/io.taifoon/coordination-layer` | 2026-10-03T192912987039 -> 2026-10-03T232153787028 | 2 added | quiet |
| 2026-10-03 | `remote/com.primecutsnursery/public-data` | 2026-10-01T063528088221 -> 2026-10-03T232152980441 | 1 changed | quiet |
| 2026-10-03 | `remote/ir.cbest/lighting` | 2026-10-03T192910247195 -> 2026-10-03T232152480244 | 1 changed | quiet |
| 2026-10-03 | `remote/dk.afbudsrejser/travel-search` | 2026-10-03T192910933882 -> 2026-10-03T232151975723 | 1 changed | quiet |
| 2026-10-03 | `remote/ai.wem3/wem-price-compare` | 2026-10-02T061629020762 -> 2026-10-03T232151043259 | 8 changed | quiet |
| 2026-10-03 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-10-03T192905787154 -> 2026-10-03T232149147831 | 15 changed | review |
| 2026-10-03 | `remote/com.spacexploration/listings` | 2026-10-03T121238327351 -> 2026-10-03T232148470558 | 1 changed | quiet |
| 2026-10-03 | `remote/com.immersivecommons/floor10` | 2026-10-03T192918315378 -> 2026-10-03T232146458434 | 1 changed, 1 added | quiet |
| 2026-10-03 | `remote/ai.rokha/rokha` | 2026-10-03T192903276009 -> 2026-10-03T232146414342 | 2 changed | quiet |
| 2026-10-03 | `remote/fi.akkilahdot/travel-search` | 2026-10-03T192917455142 -> 2026-10-03T232145676682 | 1 changed | quiet |
| 2026-10-03 | `remote/ai.satohub/onchain-agents` | 2026-10-02T150329183438 -> 2026-10-03T232142925545 | 3 changed | quiet |
| 2026-10-03 | `remote/io.corpusiq/multi-source-mcp` | 2026-10-03T192857190000 -> 2026-10-03T232142579081 | 1 changed | quiet |
| 2026-10-03 | `remote/com.tradestarinsider/edgar-insider-signals` | 2026-10-03T192857722511 -> 2026-10-03T232142500001 | 2 added, 1 removed | quiet |
| 2026-10-03 | `remote/com.plainrouter/mcp` | 2026-10-03T121113379546 -> 2026-10-03T232142047399 | 4 changed | quiet |
| 2026-10-03 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-03T192909904193 -> 2026-10-03T232138026218 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.jamboree777/nightwatch` | 2026-10-03T054734728305 -> 2026-10-03T232136855920 | 2 changed | quiet |
| 2026-10-03 | `remote/io.github.SidneyBissoli/medical-terminologies-mcp` | 2026-10-03T192853484786 -> 2026-10-03T232138120387 | 2 changed, 1 added | quiet |
| 2026-10-03 | `remote/com.innergcomplete/shearquery` | 2026-10-02T061624603555 -> 2026-10-03T232137025877 | 14 added | review |
| 2026-10-03 | `remote/io.github.worklittle/jobs` | 2026-10-03T192851759365 -> 2026-10-03T232136452389 | 1 added | quiet |
| 2026-10-03 | `remote/io.github.deviljin17/remode` | 2026-10-01T154236005794 -> 2026-10-03T232136199708 | 2 changed | quiet |
| 2026-10-03 | `remote/com.remoshift/jobs` | 2026-10-03T192908407949 -> 2026-10-03T232136254059 | 1 changed | quiet |
| 2026-10-03 | `remote/ai.greenlandai/greenlandai` | 2026-10-02T071751451057 -> 2026-10-03T232137696038 | 3 added | quiet |
| 2026-10-03 | `remote/ai.genomicintelligence/genomic-intelligence` | 2026-10-03T054728225175 -> 2026-10-03T232136131214 | 3 changed | quiet |
| 2026-10-03 | `remote/io.github.lemonaide152/meld` | 2026-10-03T192905580393 -> 2026-10-03T232138597409 | 3 changed (every tool) | quiet |
| 2026-10-03 | `remote/dev.mcphost/mcphost` | 2026-10-03T192900589815 -> 2026-10-03T232135295630 | 1 changed | quiet |
| 2026-10-03 | `remote/com.commerceforagents/commerceforagents` | 2026-10-02T130345087776 -> 2026-10-03T232134535118 | 1 added | quiet |
| 2026-10-03 | `remote/com.obriym-crm/mcp` | 2026-10-01T134338734551 -> 2026-10-03T232133456115 | 9 changed, 5 added | quiet |
| 2026-10-03 | `remote/io.github.naief9961-tech/naif-fixgraph` | 2026-10-03T192905703298 -> 2026-10-03T232134491389 | 23 changed, 1 added | quiet |
| 2026-10-03 | `remote/com.multicinesortega/cartelera` | 2026-10-03T054741962877 -> 2026-10-03T232133749100 | 1 changed | quiet |
| 2026-10-03 | `remote/com.usecarscout/mcp` | 2026-10-02T061618387566 -> 2026-10-03T232131519666 | 7 changed | quiet |
| 2026-10-03 | `remote/io.github.tang-vu/keryx` | 2026-10-02T130249534777 -> 2026-10-03T232131897080 | 1 changed | quiet |
| 2026-10-03 | `remote/org.billcommons/bill-commons` | 2026-10-02T071723445414 -> 2026-10-03T232126211207 | 1 changed | quiet |
| 2026-10-03 | `remote/ai.forkmate/forkmate` | 2026-10-03T054736320041 -> 2026-10-03T232125246490 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.hermoso-ai/hermoso` | 2026-10-03T054715336516 -> 2026-10-03T232123924416 | 5 changed | quiet |
| 2026-10-03 | `remote/io.github.Poiuyhje/eqvps` | 2026-10-03T135713952691 -> 2026-10-03T232125708696 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.Clipform/mcp-server` | 2026-10-02T210122499010 -> 2026-10-03T232125347988 | 6 changed | quiet |
| 2026-10-03 | `remote/com.danielsdesignstudio/mirror-ai-citability` | 2026-10-01T133846985185 -> 2026-10-03T232124460578 | 1 changed | quiet |
| 2026-10-03 | `remote/online.x-402/mcp` | 2026-10-01T133320128626 -> 2026-10-03T232122169214 | 2 added | quiet |
| 2026-10-03 | `remote/io.github.seankarltonlee/tickermint` | 2026-10-01T133317455481 -> 2026-10-03T232122050235 | 1 changed | quiet |
| 2026-10-03 | `remote/eu.sirenic/sirenic` | 2026-10-03T192833956522 -> 2026-10-03T232123583418 | 1 changed | quiet |
| 2026-10-03 | `remote/org.lexiara/lexiara` | 2026-10-03T192846891116 -> 2026-10-03T232120730944 | 1 changed | quiet |
| 2026-10-03 | `remote/io.pingroom/pingroom` | 2026-10-01T133310349356 -> 2026-10-03T232121544432 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-03T135704647421 -> 2026-10-03T232121566993 | 1 changed | quiet |
| 2026-10-03 | `remote/com.getyoutubetranscript/youtube-transcript-and-youtube-search` | 2026-10-03T054720246767 -> 2026-10-03T232121607876 | 1 changed | quiet |
| 2026-10-03 | `remote/dev.hatchloop/sms-whatsapp-messaging` | 2026-10-01T212445362208 -> 2026-10-03T232119883751 | 2 changed | quiet |
| 2026-10-03 | `remote/dev.hatchloop/agent-broker` | 2026-10-01T212445486996 -> 2026-10-03T232120051361 | 9 changed | quiet |
| 2026-10-03 | `remote/dev.workers.agent-utilities.agent-utilities/agent-utilities` | 2026-10-01T132956537426 -> 2026-10-03T232116547457 | 1 added | quiet |
| 2026-10-03 | `remote/com.agencygrowth/agencygrowth` | 2026-10-02T181603621576 -> 2026-10-03T232116784485 | 7 added | quiet |
| 2026-10-03 | `remote/com.editalmd/editalmd` | 2026-10-02T125402043569 -> 2026-10-03T232115066075 | 1 added | quiet |
| 2026-10-03 | `remote/io.github.beepboop2025/undertow` | 2026-10-03T115213816264 -> 2026-10-03T232110835324 | 1 added | quiet |
| 2026-10-03 | `remote/com.dayze/life-context.1` | 2026-10-03T192833970246 -> 2026-10-03T232110457410 | 6 changed, 8 added | quiet |
| 2026-10-03 | `remote/com.dayze/life-context` | 2026-10-03T192834070679 -> 2026-10-03T232110256237 | 6 changed, 8 added | quiet |
| 2026-10-03 | `remote/cloud.dchub/mcp-server` | 2026-10-03T192835880758 -> 2026-10-03T232112411860 | 92 changed (every tool) | quiet |
| 2026-10-03 | `remote/com.askmatchbox/matchbox` | 2026-10-03T192839133555 -> 2026-10-03T232108254913 | 2 changed | quiet |
| 2026-10-03 | `remote/io.github.whiteknightonhorse/apibase` | 2026-10-03T192837572092 -> 2026-10-03T232106834620 | 9 removed | quiet |
| 2026-10-03 | `remote/com.prereason/mcp` | 2026-10-03T192835763622 -> 2026-10-03T232104843409 | 2 changed | quiet |
| 2026-10-03 | `remote/com.aisenseapi/free-public-tools` | 2026-10-03T192828245457 -> 2026-10-03T232104640515 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 13913 substantive, 4796 that changed only numbers (a catalogue counter ticking, a date), 263 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 10160 | 5677 | 4483 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `caseyjhand.com` | 66 | 66 | 0 | 0 |
| `sistaminuten.se` | 65 | 2 | 0 | 63 |
| `afbudsrejser.dk` | 64 | 2 | 0 | 62 |
| `akkilahdot.fi` | 64 | 2 | 0 | 62 |
| `restplass.no` | 64 | 2 | 0 | 62 |
| `socialloop.ai` | 63 | 63 | 0 | 0 |
| `dayze.com` | 61 | 61 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| 1975 other operators | 5452 | 5125 | 313 | 14 |
