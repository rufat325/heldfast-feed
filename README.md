# MCP server tool changes

Last change observed 2026-09-27T23:26:19+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9409 npm servers from the official MCP registry (154 daily, the rest weekly) and 18576 hosted endpoints (daily).

12154 changes to a tool definition: 347 npm releases (101 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 11807 readings of hosted servers that found their tools changed; 28 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-09-27 | `remote/world.agentindex/x402` | 2026-09-27T195353381201 -> 2026-09-27T232624329648 | 1 changed | quiet |
| 2026-09-27 | `remote/no.restplass/travel-search` | 2026-09-27T195351406901 -> 2026-09-27T232620095903 | 1 changed | quiet |
| 2026-09-27 | `remote/dk.afbudsrejser/travel-search` | 2026-09-27T195350439664 -> 2026-09-27T232618778700 | 1 changed | quiet |
| 2026-09-27 | `remote/com.luxurylodgingpm.stay/luxury-lodging` | 2026-09-27T105232328739 -> 2026-09-27T232612683182 | 3 changed | quiet |
| 2026-09-27 | `remote/sh.tibia/tibiawiki-mcp` | 2026-09-26T132437610789 -> 2026-09-27T232607255439 | 1 changed | quiet |
| 2026-09-27 | `remote/fi.akkilahdot/travel-search` | 2026-09-27T195402865585 -> 2026-09-27T232606472915 | 1 changed | quiet |
| 2026-09-27 | `remote/io.orbitwan/orbitwan` | 2026-09-27T195340314486 -> 2026-09-27T232605740695 | 1 added | quiet |
| 2026-09-27 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-09-27T105345940463 -> 2026-09-27T232604179271 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-27T195359085702 -> 2026-09-27T232602514735 | 1 changed | quiet |
| 2026-09-27 | `remote/com.remoshift/jobs` | 2026-09-27T055101802916 -> 2026-09-27T232600679535 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.peter120525-cmd/lawmadi-os` | 2026-09-27T055149880109 -> 2026-09-27T232600727465 | 1 changed | quiet |
| 2026-09-27 | `remote/se.sistaminuten/travel-search` | 2026-09-27T195351922521 -> 2026-09-27T232558420784 | 1 changed | quiet |
| 2026-09-27 | `remote/com.thisisdelightful/games-research-starter-pack` | 2026-09-27T110608783713 -> 2026-09-27T232558633030 | 1 changed | quiet |
| 2026-09-27 | `remote/com.youspot/youspot` | 2026-09-27T195351536372 -> 2026-09-27T232557669154 | 2 changed, 1 added | quiet |
| 2026-09-27 | `remote/com.multicinesortega/cartelera` | 2026-09-27T154938308346 -> 2026-09-27T232558451957 | 1 changed | quiet |
| 2026-09-27 | `remote/com.freelanceclearing/marketplace` | 2026-09-26T044839369731 -> 2026-09-27T232557488288 | 2 changed | quiet |
| 2026-09-27 | `remote/io.verifymcp/mcp` | 2026-09-25T120411411977 -> 2026-09-27T232556959893 | 1 changed | quiet |
| 2026-09-27 | `remote/com.vibe-fixer/vibefix` | 2026-09-26T114307620572 -> 2026-09-27T232555857380 | 1 added | quiet |
| 2026-09-27 | `remote/study.vela/corpus` | 2026-09-25T120442988780 -> 2026-09-27T232555238848 | 1 changed | quiet |
| 2026-09-27 | `remote/ru.activatedai/activated-ai` | 2026-09-27T072629517842 -> 2026-09-27T232553004207 | 3 changed | quiet |
| 2026-09-27 | `remote/com.jobmojito/jobmojito` | 2026-09-25T120325220619 -> 2026-09-27T232554141659 | 29 changed (every tool) | quiet |
| 2026-09-27 | `remote/io.github.moralito311-andr/andreax` | 2026-09-27T195344677442 -> 2026-09-27T232552120389 | 2 changed, 4 added | review |
| 2026-09-27 | `remote/com.plainrouter/mcp` | 2026-09-27T055020507623 -> 2026-09-27T232551536243 | 4 changed, 3 added, 3 removed | quiet |
| 2026-09-27 | `remote/systems.phion/evidence-engine` | 2026-09-27T065947074237 -> 2026-09-27T232549970305 | 7 changed, 1 added | quiet |
| 2026-09-27 | `remote/io.github.toshihiroshishido/revenuescope-mcp` | 2026-09-27T110858802819 -> 2026-09-27T232549763722 | 6 changed, 1 added | quiet |
| 2026-09-27 | `remote/io.github.si-imtiaz/leadquasar` | 2026-09-27T110715646848 -> 2026-09-27T232549858721 | 2 changed | quiet |
| 2026-09-27 | `remote/dev.mcphost/mcphost` | 2026-09-27T195341383835 -> 2026-09-27T232548094483 | 3 added | quiet |
| 2026-09-27 | `remote/com.myhairmailtools/agent-tools` | 2026-09-27T070030893357 -> 2026-09-27T232547336180 | 3 changed (every tool) | quiet |
| 2026-09-27 | `remote/ai.hostingbrain/intelligence` | 2026-09-26T045057900270 -> 2026-09-27T232547783525 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.schneidavie/fund-momentum` | 2026-09-27T152254327472 -> 2026-09-27T232547361114 | 2 changed | quiet |
| 2026-09-27 | `remote/com.viberooster/hatch` | 2026-09-26T045215024214 -> 2026-09-27T232545794193 | 2 changed | quiet |
| 2026-09-27 | `remote/xyz.apexfaucet/apex-x1` | 2026-09-27T131949587950 -> 2026-09-27T232546124585 | 1 changed, 1 added | quiet |
| 2026-09-27 | `remote/ch.blust/mental-model` | 2026-09-27T195338449755 -> 2026-09-27T232545973189 | 1 changed | quiet |
| 2026-09-27 | `remote/com.movingplace/mcp` | 2026-09-27T155200049331 -> 2026-09-27T232543989243 | 16 removed | quiet |
| 2026-09-27 | `remote/com.editalmd/editalmd` | 2026-09-27T195341262600 -> 2026-09-27T232545698058 | 5 changed, 1 added | quiet |
| 2026-09-27 | `remote/net.isitdns/isitdns` | 2026-09-27T195334218995 -> 2026-09-27T232542763208 | 2 changed, 3 added | quiet |
| 2026-09-27 | `remote/io.github.tacticalnoot/agent-embassy` | 2026-09-26T231031605200 -> 2026-09-27T232543326739 | 18 changed (every tool) | quiet |
| 2026-09-27 | `remote/com.googleapis.compute/mcp` | 2026-09-27T195338479302 -> 2026-09-27T232543221640 | 10 changed | quiet |
| 2026-09-27 | `remote/io.github.Its-fortunatefolly/hubvibe` | 2026-09-27T195333991933 -> 2026-09-27T232542076869 | 5 changed | quiet |
| 2026-09-27 | `remote/ai.hyperscale0/hyperscale-tenant-tools` | 2026-09-27T154705936411 -> 2026-09-27T232543484407 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.tjcgraham-rgb/gaip-broker` | 2026-09-27T065627307839 -> 2026-09-27T232541406738 | 12 changed, 1 added (every tool) | quiet |
| 2026-09-27 | `remote/io.companygraph/mental-model` | 2026-09-27T195334670003 -> 2026-09-27T232542448304 | 1 changed | quiet |
| 2026-09-27 | `remote/com.agenttrafficlab/atl` | 2026-09-27T195332732254 -> 2026-09-27T232541297839 | 3 changed | quiet |
| 2026-09-27 | `remote/se.klassio/eu-customs-tariff-eudr` | 2026-09-27T130554936333 -> 2026-09-27T232540035326 | 1 changed | quiet |
| 2026-09-27 | `remote/com.factanker/factanker` | 2026-09-27T152341526516 -> 2026-09-27T232540515251 | 3 changed, 1 added | quiet |
| 2026-09-27 | `remote/com.askmatchbox/matchbox` | 2026-09-26T231046941641 -> 2026-09-27T232540122098 | 2 changed | quiet |
| 2026-09-27 | `remote/net.aginx/aginxbrowser` | 2026-09-26T192525120654 -> 2026-09-27T232540884284 | 3 changed, 1 added | quiet |
| 2026-09-27 | `remote/io.github.fetchsandbox/mcp` | 2026-09-25T120027539628 -> 2026-09-27T232538532591 | 2 changed | quiet |
| 2026-09-27 | `remote/io.github.social-freak-ltd/socialfetch` | 2026-09-26T044703538297 -> 2026-09-27T232538851134 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.QAInsights/jmeter-docs` | 2026-09-27T065508291770 -> 2026-09-27T232538302268 | 1 changed, 2 added | quiet |
| 2026-09-27 | `remote/com.uplika/uplika` | 2026-09-27T065410759766 -> 2026-09-27T232537499374 | 2 changed | quiet |
| 2026-09-27 | `remote/ai.weftly/weftly` | 2026-09-27T065408108668 -> 2026-09-27T232537544750 | 1 changed, 1 removed | quiet |
| 2026-09-27 | `remote/work.resumebooster/jobs` | 2026-09-26T044739895646 -> 2026-09-27T232536311616 | 6 changed | quiet |
| 2026-09-27 | `remote/io.github.CDCStream/captapi` | 2026-09-27T102934382590 -> 2026-09-27T232535497360 | 1 changed | review |
| 2026-09-27 | `remote/com.aiengineerprofessional/engineerpro-library` | 2026-09-26T044531834905 -> 2026-09-27T232535868119 | 3 added | quiet |
| 2026-09-27 | `remote/io.github.47620-xyz/solana-data` | 2026-09-27T195322281890 -> 2026-09-27T232534477798 | 3 added | quiet |
| 2026-09-27 | `remote/news.prh/revenue-agent` | 2026-09-27T195322534161 -> 2026-09-27T232533224264 | 2 changed (every tool) | quiet |
| 2026-09-27 | `remote/com.zoningsignal/observatory` | 2026-09-27T070127155902 -> 2026-09-27T195404718171 | 1 changed | quiet |
| 2026-09-27 | `remote/fi.akkilahdot/travel-search` | 2026-09-27T155123960184 -> 2026-09-27T195402865585 | 1 changed | quiet |
| 2026-09-27 | `remote/com.goedvps.app.wodan-posture/wodan-posture` | 2026-09-27T105412091435 -> 2026-09-27T195403419327 | 1 added | review |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 8936 substantive, 3104 that changed only numbers (a catalogue counter ticking, a date), 114 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 7017 | 4042 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `caseyjhand.com` | 55 | 55 | 0 | 0 |
| `daedalmap.com` | 47 | 47 | 0 | 0 |
| `sistaminuten.se` | 30 | 2 | 0 | 28 |
| `afbudsrejser.dk` | 29 | 2 | 0 | 27 |
| `akkilahdot.fi` | 29 | 2 | 0 | 27 |
| `restplass.no` | 29 | 2 | 0 | 27 |
| `socialloop.ai` | 29 | 29 | 0 | 0 |
| `assetfare.dev` | 20 | 20 | 0 | 0 |
| `dayze.com` | 20 | 20 | 0 | 0 |
| 955 other operators | 2084 | 1950 | 129 | 5 |
