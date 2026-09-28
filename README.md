# MCP server tool changes

Last change observed 2026-09-28T07:33:41+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9409 npm servers from the official MCP registry (154 daily, the rest weekly) and 18576 hosted endpoints (daily).

12366 changes to a tool definition: 354 npm releases (108 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 12012 readings of hosted servers that found their tools changed; 38 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-09-28 | `remote/se.sistaminuten/travel-search` | 2026-09-28T055527334110 -> 2026-09-28T073343377982 | 1 changed | quiet |
| 2026-09-28 | `remote/fr.vigi-sky/vigisky` | 2026-09-23T161008475196 -> 2026-09-28T073304798304 | 4 added | quiet |
| 2026-09-28 | `remote/com.youspot/youspot` | 2026-09-27T232557669154 -> 2026-09-28T073244893888 | 1 changed | quiet |
| 2026-09-28 | `remote/com.thefilmmap/filming-locations` | 2026-09-23T160949199874 -> 2026-09-28T073236904922 | 1 changed | quiet |
| 2026-09-28 | `remote/sh.stipple/openwarrant` | 2026-09-23T160853508570 -> 2026-09-28T073234600533 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.seekdaseek/agentfeed` | 2026-09-26T045620833894 -> 2026-09-28T073232191598 | 12 changed | quiet |
| 2026-09-28 | `remote/com.igods/space-monkey` | 2026-09-23T160941207364 -> 2026-09-28T073226296413 | 1 added | quiet |
| 2026-09-28 | `remote/world.agentindex/x402` | 2026-09-27T232624329648 -> 2026-09-28T073217920760 | 1 added | quiet |
| 2026-09-28 | `remote/za.co.netbrainis/catalogue` | 2026-09-23T160849759340 -> 2026-09-28T073220697693 | 3 changed | quiet |
| 2026-09-28 | `remote/com.myhuiban.www/conference-partner` | 2026-09-23T160846713111 -> 2026-09-28T073215750472 | 1 changed | quiet |
| 2026-09-28 | `remote/sh.stipple/stipple-tenders` | 2026-09-23T163146743497 -> 2026-09-28T073212425619 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.delicious28/sealmaker-mcp` | 2026-09-23T163142651226 -> 2026-09-28T073207852367 | 1 changed | quiet |
| 2026-09-28 | `remote/no.restplass/travel-search` | 2026-09-28T055533894215 -> 2026-09-28T073206633291 | 1 changed | quiet |
| 2026-09-28 | `remote/fi.akkilahdot/travel-search` | 2026-09-28T055534946406 -> 2026-09-28T073206069408 | 1 changed | quiet |
| 2026-09-28 | `remote/com.whichtrim/vehicle-records` | 2026-09-23T162929506313 -> 2026-09-28T073159336655 | 1 added | quiet |
| 2026-09-28 | `remote/io.github.CodePhantom-1/ddmarketer-mcp` | 2026-09-23T163129026406 -> 2026-09-28T073155859252 | 1 changed | quiet |
| 2026-09-28 | `remote/com.voyscout/price-history` | 2026-09-24T120446608962 -> 2026-09-28T073155103971 | 2 changed | quiet |
| 2026-09-28 | `remote/dk.afbudsrejser/travel-search` | 2026-09-28T055533160174 -> 2026-09-28T073151138315 | 1 changed | quiet |
| 2026-09-28 | `remote/ai.wem3/wem-price-compare` | 2026-09-24T202605100289 -> 2026-09-28T073146550875 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.brawlaphant/vealth` | 2026-09-24T205546788409 -> 2026-09-28T073141103227 | 5 added | quiet |
| 2026-09-28 | `remote/io.github.benian-technologies/pinpoint-dealership-tools` | 2026-09-25T120440660240 -> 2026-09-28T073139297482 | 1 changed | quiet |
| 2026-09-28 | `remote/com.ugcpocket/ugc-pocket` | 2026-09-23T160819563478 -> 2026-09-28T073137777722 | 2 changed, 6 removed (every tool) | quiet |
| 2026-09-28 | `remote/io.github.taux-io/twse-mcp` | 2026-09-27T195348907158 -> 2026-09-28T073135649884 | 2 changed | quiet |
| 2026-09-28 | `remote/io.github.SidneyBissoli/uis-mcp-server` | 2026-09-24T120416365322 -> 2026-09-28T073136135279 | 5 changed (every tool) | quiet |
| 2026-09-28 | `remote/com.thecastlemap/castles` | 2026-09-24T120428552814 -> 2026-09-28T073134496939 | 1 changed | quiet |
| 2026-09-28 | `remote/com.pinsvit/api` | 2026-09-23T160858863067 -> 2026-09-28T073133835428 | 6 changed, 6 added | quiet |
| 2026-09-28 | `remote/pl.swiadectwo-energetyczne24/zamowienia` | 2026-09-23T162902215288 -> 2026-09-28T073128466376 | 3 changed, 7 removed | quiet |
| 2026-09-28 | `remote/io.github.moralito311-andr/andreax` | 2026-09-28T055521557296 -> 2026-09-28T073125363146 | 1 changed, 2 added | quiet |
| 2026-09-28 | `remote/us.thistripbtw/trips` | 2026-09-25T120431469055 -> 2026-09-28T073122519876 | 1 changed | quiet |
| 2026-09-28 | `remote/org.oravan/mcp` | 2026-09-23T160849549580 -> 2026-09-28T073120969557 | 2 changed | quiet |
| 2026-09-28 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-28T055532736960 -> 2026-09-28T073115999453 | 1 changed | quiet |
| 2026-09-28 | `remote/fr.synergieloc/immobilier` | 2026-09-23T202459780868 -> 2026-09-28T073114394112 | 1 changed, 9 added | quiet |
| 2026-09-28 | `remote/io.github.SiliconAnalysts/silicon-analysts` | 2026-09-23T162849819221 -> 2026-09-28T073111117653 | 6 changed, 2 added, 1 removed | quiet |
| 2026-09-28 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-09-27T195346906452 -> 2026-09-28T073109473434 | 15 changed | review |
| 2026-09-28 | `remote/com.innergcomplete/shearquery` | 2026-09-23T162850143104 -> 2026-09-28T073109015141 | 27 added | quiet |
| 2026-09-28 | `remote/com.nabarfinder/nabarfinder` | 2026-09-23T160839514847 -> 2026-09-28T073102286258 | 1 changed | quiet |
| 2026-09-28 | `remote/fr.scorelook/capucine` | 2026-09-23T162842032204 -> 2026-09-28T073100562051 | 4 added | quiet |
| 2026-09-28 | `remote/ai.agentlookups/counterscript` | 2026-09-23T162838482332 -> 2026-09-28T073056103291 | 1 changed | quiet |
| 2026-09-28 | `remote/io.scoutrail/scoutrail` | 2026-09-23T162954651284 -> 2026-09-28T073055259281 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.roman-rr/trading-signals` | 2026-09-23T160749533552 -> 2026-09-28T073054458184 | 5 changed (every tool) | quiet |
| 2026-09-28 | `remote/io.github.SidneyBissoli/medical-terminologies-mcp` | 2026-09-23T160828187116 -> 2026-09-28T073047767765 | 33 changed (every tool) | quiet |
| 2026-09-28 | `remote/com.radar-cnpj/radar-cnpj` | 2026-09-23T202354642932 -> 2026-09-28T073045791197 | 17 changed (every tool) | quiet |
| 2026-09-28 | `remote/io.github.cnghockey/sats4ai` | 2026-09-23T202331815693 -> 2026-09-28T073041769916 | 6 changed | quiet |
| 2026-09-28 | `remote/io.github.tlefko/central-command` | 2026-09-23T160734935368 -> 2026-09-28T073038958307 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.RNVizion/rnv-color-mcp` | 2026-09-23T160733551920 -> 2026-09-28T073036638793 | 2 changed | quiet |
| 2026-09-28 | `remote/com.smklog/parcel-shipping-rates` | 2026-09-23T160727639276 -> 2026-09-28T073027205562 | 2 changed | quiet |
| 2026-09-28 | `remote/com.qumge/skills` | 2026-09-28T055527602013 -> 2026-09-28T073028094581 | 2 changed | quiet |
| 2026-09-28 | `remote/pl.klyo/games` | 2026-09-24T120333816267 -> 2026-09-28T073025779484 | 1 changed | quiet |
| 2026-09-28 | `remote/online.pageaudit/pageaudit` | 2026-09-23T202336444727 -> 2026-09-28T073024758157 | 20 changed (every tool) | quiet |
| 2026-09-28 | `remote/io.github.jdhart81/regulatory-radar` | 2026-09-23T160808571477 -> 2026-09-28T073024361144 | 1 changed, 1 added | quiet |
| 2026-09-28 | `remote/io.github.cyanheads/pubmed-mcp-server` | 2026-09-23T160725974172 -> 2026-09-28T073024260317 | 10 changed | quiet |
| 2026-09-28 | `remote/io.github.isaacaskew/venunite-events` | 2026-09-24T202443380128 -> 2026-09-28T073023023780 | 2 changed (every tool) | quiet |
| 2026-09-28 | `remote/ai.agentlookups/overassessed` | 2026-09-23T162808228341 -> 2026-09-28T073022384242 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.prof-1t/postlyra-mcp` | 2026-09-23T162920962138 -> 2026-09-28T073020438735 | 2 changed | quiet |
| 2026-09-28 | `remote/com.fractionalteams/portal` | 2026-09-23T162920147748 -> 2026-09-28T073019266883 | 1 changed | quiet |
| 2026-09-28 | `remote/com.pontofato/pontofato` | 2026-09-23T202311511621 -> 2026-09-28T073018465869 | 14 changed (every tool) | quiet |
| 2026-09-28 | `remote/com.tutorializer/tutorializer` | 2026-09-23T160804075839 -> 2026-09-28T073018610257 | 23 changed (every tool) | quiet |
| 2026-09-28 | `remote/com.supovia/supovia` | 2026-09-23T160758089255 -> 2026-09-28T073009402955 | 14 changed (every tool) | quiet |
| 2026-09-28 | `remote/io.github.mason0501/pairgora` | 2026-09-25T120337569110 -> 2026-09-28T073006305126 | 11 changed | quiet |
| 2026-09-28 | `remote/com.octurasolutions/site-tools` | 2026-09-23T162900535351 -> 2026-09-28T072959635952 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 9127 substantive, 3116 that changed only numbers (a catalogue counter ticking, a date), 123 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 7017 | 4042 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `caseyjhand.com` | 56 | 56 | 0 | 0 |
| `daedalmap.com` | 47 | 47 | 0 | 0 |
| `sistaminuten.se` | 32 | 2 | 0 | 30 |
| `afbudsrejser.dk` | 31 | 2 | 0 | 29 |
| `akkilahdot.fi` | 31 | 2 | 0 | 29 |
| `restplass.no` | 31 | 2 | 0 | 29 |
| `socialloop.ai` | 31 | 31 | 0 | 0 |
| `dayze.com` | 24 | 24 | 0 | 0 |
| `assetfare.dev` | 22 | 22 | 0 | 0 |
| 1034 other operators | 2279 | 2132 | 141 | 6 |
