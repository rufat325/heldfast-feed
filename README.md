# MCP server tool changes

Last change observed 2026-09-28T05:55:35+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9409 npm servers from the official MCP registry (154 daily, the rest weekly) and 18576 hosted endpoints (daily).

12216 changes to a tool definition: 347 npm releases (101 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 11869 readings of hosted servers that found their tools changed; 32 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-09-28 | `remote/com.zoningsignal/observatory` | 2026-09-27T195404718171 -> 2026-09-28T055536408246 | 1 changed | quiet |
| 2026-09-28 | `remote/fi.akkilahdot/travel-search` | 2026-09-27T232606472915 -> 2026-09-28T055534946406 | 1 changed | quiet |
| 2026-09-28 | `remote/no.restplass/travel-search` | 2026-09-27T232620095903 -> 2026-09-28T055533894215 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-27T232602514735 -> 2026-09-28T055532736960 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.Schoasch/backtesting-arena` | 2026-09-26T114314426637 -> 2026-09-28T055533461379 | 3 changed | quiet |
| 2026-09-28 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-09-27T232604179271 -> 2026-09-28T055533984059 | 1 changed | quiet |
| 2026-09-28 | `remote/dk.afbudsrejser/travel-search` | 2026-09-27T232618778700 -> 2026-09-28T055533160174 | 1 changed | quiet |
| 2026-09-28 | `remote/com.remoshift/jobs` | 2026-09-27T232600679535 -> 2026-09-28T055531873509 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.Andyxcg/agentshop-reports` | 2026-09-26T114339135827 -> 2026-09-28T055531590663 | 1 changed | quiet |
| 2026-09-28 | `remote/com.sonarconnections/sonar-connections` | 2026-09-27T154928134828 -> 2026-09-28T055527561884 | 4 changed | quiet |
| 2026-09-28 | `remote/se.sistaminuten/travel-search` | 2026-09-27T232558420784 -> 2026-09-28T055527334110 | 1 changed | quiet |
| 2026-09-28 | `remote/com.qumge/skills` | 2026-09-26T192546510368 -> 2026-09-28T055527602013 | 6 changed, 11 added, 8 removed (every tool) | quiet |
| 2026-09-28 | `remote/com.brianbooms/quiet-menders` | 2026-09-26T231052464310 -> 2026-09-28T055526664430 | 3 changed, 20 added | review |
| 2026-09-28 | `remote/app.sallim/korea-realty` | 2026-09-27T141923117025 -> 2026-09-28T055529782603 | 1 changed | quiet |
| 2026-09-28 | `remote/com.jojapi/swift-ai` | 2026-09-27T055056803993 -> 2026-09-28T055525670946 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.daniel3303/equibles` | 2026-09-26T192543809412 -> 2026-09-28T055525069811 | 7 changed | quiet |
| 2026-09-28 | `remote/com.thefomite/fomite` | 2026-09-27T055048383671 -> 2026-09-28T055524348952 | 1 changed | quiet |
| 2026-09-28 | `remote/com.gojinko.mcp/jinko` | 2026-09-27T055055851833 -> 2026-09-28T055524230265 | 3 changed | quiet |
| 2026-09-28 | `remote/sh.tibia/tibiawiki-mcp` | 2026-09-27T232607255439 -> 2026-09-28T055523859386 | 2 changed | quiet |
| 2026-09-28 | `remote/io.github.si-imtiaz/leadquasar` | 2026-09-27T232549858721 -> 2026-09-28T055523618599 | 2 changed | quiet |
| 2026-09-28 | `remote/net.hotelrefund/price-tracker` | 2026-09-27T055054617670 -> 2026-09-28T055522323233 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.moralito311-andr/andreax` | 2026-09-27T232552120389 -> 2026-09-28T055521557296 | 3 added | quiet |
| 2026-09-28 | `remote/io.github.danafitkowski/cpp-cpm-engine` | 2026-09-27T152631928977 -> 2026-09-28T055520302778 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.toshihiroshishido/revenuescope-mcp` | 2026-09-27T232549763722 -> 2026-09-28T055519589501 | 1 changed | quiet |
| 2026-09-28 | `remote/com.tapeperp/tape` | 2026-09-27T070050478995 -> 2026-09-28T055518714398 | 1 changed | review |
| 2026-09-28 | `remote/com.rhylthyme/rhylthyme` | 2026-09-26T192534165081 -> 2026-09-28T055519703901 | 9 changed | quiet |
| 2026-09-28 | `remote/services.ottoai/otto` | 2026-09-27T070047043550 -> 2026-09-28T055519188157 | 3 changed | quiet |
| 2026-09-28 | `remote/io.github.Kotaro-Studio/kurashigram` | 2026-09-27T055147938612 -> 2026-09-28T055518312996 | 1 changed | quiet |
| 2026-09-28 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-09-27T055020719158 -> 2026-09-28T055520147548 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt` | 2026-09-27T195340767788 -> 2026-09-28T055518758473 | 91 changed | quiet |
| 2026-09-28 | `remote/com.plainrouter/mcp` | 2026-09-27T232551536243 -> 2026-09-28T055518419566 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.jamboree777/nightwatch` | 2026-09-26T045256823361 -> 2026-09-28T055517791170 | 1 added | review |
| 2026-09-28 | `remote/dev.mcphost/mcphost` | 2026-09-27T232548094483 -> 2026-09-28T055516117136 | 1 changed, 1 added | quiet |
| 2026-09-28 | `remote/com.chateaupedia/chateaux` | 2026-09-27T055145456113 -> 2026-09-28T055514556808 | 1 changed | quiet |
| 2026-09-28 | `remote/net.isitdns/isitdns` | 2026-09-27T232542763208 -> 2026-09-28T055513244062 | 7 changed | quiet |
| 2026-09-28 | `remote/io.github.Its-fortunatefolly/hubvibe` | 2026-09-27T232542076869 -> 2026-09-28T055513184561 | 1 added | quiet |
| 2026-09-28 | `remote/io.github.tjcgraham-rgb/gaip-broker` | 2026-09-27T232541406738 -> 2026-09-28T055511992837 | 5 changed, 3 added | quiet |
| 2026-09-28 | `remote/io.github.hermoso-ai/hermoso` | 2026-09-26T044717394052 -> 2026-09-28T055513757419 | 3 changed | quiet |
| 2026-09-28 | `remote/kr.xdata/xdata-mcp` | 2026-09-26T231038643361 -> 2026-09-28T055513401229 | 5 changed | quiet |
| 2026-09-28 | `remote/com.agenttrafficlab/atl` | 2026-09-27T232541297839 -> 2026-09-28T055511263252 | 4 changed (every tool) | quiet |
| 2026-09-28 | `remote/se.klassio/eu-customs-tariff-eudr` | 2026-09-27T232540035326 -> 2026-09-28T055509659744 | 1 changed | quiet |
| 2026-09-28 | `remote/com.dayze/life-context.1` | 2026-09-27T134635419672 -> 2026-09-28T055510148540 | 5 changed | quiet |
| 2026-09-28 | `remote/com.dayze/life-context` | 2026-09-27T134635037313 -> 2026-09-28T055509994673 | 5 changed | quiet |
| 2026-09-28 | `remote/io.github.odaiin/assetfare-bridge` | 2026-09-27T123958369066 -> 2026-09-28T055509930453 | 2 changed | quiet |
| 2026-09-28 | `remote/com.clinkforge/clink-forge` | 2026-09-27T055143062553 -> 2026-09-28T055508969458 | 9 added, 1 removed | review |
| 2026-09-28 | `remote/com.astranl/mcp` | 2026-09-26T044742213325 -> 2026-09-28T055508440949 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.whiteknightonhorse/apibase` | 2026-09-27T195326470708 -> 2026-09-28T055509217024 | 4 added, 12 removed | quiet |
| 2026-09-28 | `remote/io.github.QAInsights/jmeter-docs` | 2026-09-27T232538302268 -> 2026-09-28T055507784302 | 1 changed, 1 added | quiet |
| 2026-09-28 | `remote/com.uplika/uplika` | 2026-09-27T232537499374 -> 2026-09-28T055508414430 | 2 changed | quiet |
| 2026-09-28 | `remote/com.olympus-bets/olympus-bets-analytics` | 2026-09-26T044733207837 -> 2026-09-28T055507911389 | 1 changed, 2 added | quiet |
| 2026-09-28 | `remote/io.github.ciinkwia/agent-tool-finder` | 2026-09-26T044749226934 -> 2026-09-28T055506472536 | 6 added | quiet |
| 2026-09-28 | `remote/com.trustverum/public-reading` | 2026-09-27T141902786331 -> 2026-09-28T055506725225 | 2 changed | quiet |
| 2026-09-28 | `remote/app.flaim/mcp` | 2026-09-27T195323681056 -> 2026-09-28T055505659427 | 10 changed | quiet |
| 2026-09-28 | `remote/ai.timeplex/booking` | 2026-09-27T103118398644 -> 2026-09-28T055506188321 | 4 changed | quiet |
| 2026-09-28 | `remote/io.github.odaiin/assetfare` | 2026-09-27T123955141076 -> 2026-09-28T055507088406 | 2 changed | quiet |
| 2026-09-28 | `remote/com.phasefolio/phasefolio` | 2026-09-27T195326245602 -> 2026-09-28T055504653931 | 6 changed | quiet |
| 2026-09-28 | `remote/br.com.adoteca/adoteca` | 2026-09-26T044530809313 -> 2026-09-28T055505409905 | 1 added | quiet |
| 2026-09-28 | `remote/app.nanocorp.bidswarm/bidswarm` | 2026-09-27T065433411824 -> 2026-09-28T055505289040 | 1 added | quiet |
| 2026-09-28 | `remote/io.github.onetapstudiogames/1f3d9` | 2026-09-27T195321343620 -> 2026-09-28T055504379100 | 3 changed | quiet |
| 2026-09-28 | `remote/io.github.47620-xyz/solana-data` | 2026-09-27T232534477798 -> 2026-09-28T055504873122 | 10 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 8987 substantive, 3110 that changed only numbers (a catalogue counter ticking, a date), 119 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 7017 | 4042 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `caseyjhand.com` | 55 | 55 | 0 | 0 |
| `daedalmap.com` | 47 | 47 | 0 | 0 |
| `sistaminuten.se` | 31 | 2 | 0 | 29 |
| `afbudsrejser.dk` | 30 | 2 | 0 | 28 |
| `akkilahdot.fi` | 30 | 2 | 0 | 28 |
| `restplass.no` | 30 | 2 | 0 | 28 |
| `socialloop.ai` | 30 | 30 | 0 | 0 |
| `assetfare.dev` | 22 | 22 | 0 | 0 |
| `dayze.com` | 22 | 22 | 0 | 0 |
| 955 other operators | 2137 | 1996 | 135 | 6 |
