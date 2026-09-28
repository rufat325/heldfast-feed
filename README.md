# MCP server tool changes

Last change observed 2026-09-28T17:04:23+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

12645 changes to a tool definition: 370 npm releases (124 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 12275 readings of hosted servers that found their tools changed; 48 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-09-28 | `remote/io.github.Fizzl13/x402-doctor` | 2026-09-28T142411167068 -> 2026-09-28T170424616410 | 1 added | quiet |
| 2026-09-28 | `remote/io.applayer/tango` | 2026-09-26T231112040571 -> 2026-09-28T170412415555 | 97 changed, 2 added, 1 removed (every tool) | quiet |
| 2026-09-28 | `remote/com.suomiatlas/area-statistics` | 2026-09-28T142234826475 -> 2026-09-28T170411998613 | 1 changed | quiet |
| 2026-09-28 | `remote/se.sistaminuten/travel-search` | 2026-09-28T142335306572 -> 2026-09-28T170405273471 | 1 changed | quiet |
| 2026-09-28 | `remote/style.quartermaster/menswear-outfits` | 2026-09-28T142138013368 -> 2026-09-28T170403487232 | 5 changed (every tool) | quiet |
| 2026-09-28 | `remote/io.github.tjcgraham-rgb/gaip-outcome-value` | 2026-09-28T142324308307 -> 2026-09-28T170407646944 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.tjcgraham-rgb/gaip-integration-protocol` | 2026-09-28T142323852928 -> 2026-09-28T170403906385 | 2 changed | quiet |
| 2026-09-28 | `remote/io.github.tjcgraham-rgb/gaip-buyer-assurance` | 2026-09-28T142323313653 -> 2026-09-28T170406975965 | 3 changed (every tool) | quiet |
| 2026-09-28 | `remote/io.github.tjcgraham-rgb/gaip-witness` | 2026-09-28T142626129115 -> 2026-09-28T170403907951 | 4 changed | quiet |
| 2026-09-28 | `remote/io.github.tjcgraham-rgb/gaip-procurement-verify` | 2026-09-28T142625978607 -> 2026-09-28T170403193679 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.tjcgraham-rgb/gaip-integration-repair` | 2026-09-28T142626060980 -> 2026-09-28T170403881955 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.tjcgraham-rgb/gaip-broker` | 2026-09-28T103647873111 -> 2026-09-28T170404016979 | 11 changed, 1 added | quiet |
| 2026-09-28 | `remote/fi.akkilahdot/travel-search` | 2026-09-28T142614151978 -> 2026-09-28T170359687025 | 1 changed | quiet |
| 2026-09-28 | `remote/com.goedvps.app.wodan-posture/wodan-posture` | 2026-09-27T195403419327 -> 2026-09-28T170359825177 | 1 added | review |
| 2026-09-28 | `remote/tech.viewprinter/viewprinter` | 2026-09-26T045542488837 -> 2026-09-28T170357905128 | 6 changed, 6 added, 9 removed | quiet |
| 2026-09-28 | `remote/com.blitzreels/blitzreels` | 2026-09-27T105449152814 -> 2026-09-28T170400298826 | 2 changed | quiet |
| 2026-09-28 | `remote/world.agentindex/x402` | 2026-09-28T142333019050 -> 2026-09-28T170357441226 | 1 changed | quiet |
| 2026-09-28 | `remote/io.taifoon/coordination-layer` | 2026-09-28T142327447171 -> 2026-09-28T170355633238 | 1 changed, 1 added | quiet |
| 2026-09-28 | `remote/no.restplass/travel-search` | 2026-09-28T142319948565 -> 2026-09-28T170355108487 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.tjcgraham-rgb/gaip-supplier-watch` | 2026-09-28T142312123934 -> 2026-09-28T170356652292 | 3 changed | quiet |
| 2026-09-28 | `remote/dk.afbudsrejser/travel-search` | 2026-09-28T142258546949 -> 2026-09-28T170352328816 | 1 changed | quiet |
| 2026-09-28 | `remote/us.stratly/townsquare` | 2026-09-28T142536464809 -> 2026-09-28T170350518591 | 1 changed, 2 added | quiet |
| 2026-09-28 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-28T142527460954 -> 2026-09-28T170349981137 | 18 changed | quiet |
| 2026-09-28 | `remote/com.underpricedai/underpriced-ai` | 2026-09-27T065944891426 -> 2026-09-28T170347490273 | 5 changed | review |
| 2026-09-28 | `remote/com.tttkmbb/calcgrid` | 2026-09-28T142235116752 -> 2026-09-28T170346188271 | 2 changed, 10 added | quiet |
| 2026-09-28 | `remote/io.github.Kopaev/openvan-travel` | 2026-09-27T112815669662 -> 2026-09-28T170344166445 | 18 changed (every tool) | quiet |
| 2026-09-28 | `remote/com.remoshift/jobs` | 2026-09-28T142455431031 -> 2026-09-28T170343984308 | 1 changed | quiet |
| 2026-09-28 | `remote/com.luxurylodgingpm.stay/luxury-lodging` | 2026-09-27T232612683182 -> 2026-09-28T170339547749 | 2 changed | quiet |
| 2026-09-28 | `remote/ai.gondola/gondola` | 2026-09-26T045118261726 -> 2026-09-28T170338588594 | 1 changed | quiet |
| 2026-09-28 | `remote/com.agenttrafficlab/atl` | 2026-09-28T055511263252 -> 2026-09-28T170335222235 | 1 changed | quiet |
| 2026-09-28 | `remote/com.qumge/skills` | 2026-09-28T073028094581 -> 2026-09-28T170334632536 | 2 changed | quiet |
| 2026-09-28 | `remote/io.github.Fizzl13/presign-guard` | 2026-09-28T142058871355 -> 2026-09-28T170334151304 | 1 added | quiet |
| 2026-09-28 | `remote/com.neblla/neblla` | 2026-09-28T142409271503 -> 2026-09-28T170333588688 | 1 changed, 1 added | quiet |
| 2026-09-28 | `remote/com.meettempi/tempi` | 2026-09-28T142018820860 -> 2026-09-28T170333286154 | 1 changed | quiet |
| 2026-09-28 | `remote/es.cesaryague/paki-curator` | 2026-09-26T045250417585 -> 2026-09-28T170332335787 | 7 changed (every tool) | quiet |
| 2026-09-28 | `remote/io.github.RagingOrangutan/rootvine-mcp` | 2026-09-28T141917721793 -> 2026-09-28T170330194508 | 1 changed | quiet |
| 2026-09-28 | `remote/com.stocklens/stocklens` | 2026-09-26T045317542970 -> 2026-09-28T170328638279 | 1 changed | quiet |
| 2026-09-28 | `remote/ai.humanproblems/humanproblems` | 2026-09-28T141718648304 -> 2026-09-28T170329059926 | 1 changed, 2 added | quiet |
| 2026-09-28 | `remote/com.penguindriver/hub` | 2026-09-28T141717391717 -> 2026-09-28T170328775352 | 6 added | quiet |
| 2026-09-28 | `remote/xyz.558686.gpt55/token-gateway` | 2026-09-26T231057749770 -> 2026-09-28T170330995723 | 4 changed | quiet |
| 2026-09-28 | `remote/io.github.cammac-creator/openswissdata` | 2026-09-26T045123479520 -> 2026-09-28T170326553118 | 3 changed, 5 removed (every tool) | quiet |
| 2026-09-28 | `remote/io.github.federico2001/openglass-mcp` | 2026-09-28T141859933473 -> 2026-09-28T170326194606 | 4 changed, 1 added | quiet |
| 2026-09-28 | `remote/com.hireahelper/mcp` | 2026-09-27T124551690633 -> 2026-09-28T170323499768 | 16 added | quiet |
| 2026-09-28 | `remote/com.handsforagents/hands` | 2026-09-28T103946512522 -> 2026-09-28T170324733016 | 4 changed | quiet |
| 2026-09-28 | `remote/io.github.Ahmet11159/x402-agent-services` | 2026-09-28T141756668892 -> 2026-09-28T170321037126 | 1 changed | quiet |
| 2026-09-28 | `remote/dev.workers.bhazarstudio.datoqa/official-public-holidays` | 2026-09-28T141514956255 -> 2026-09-28T170321467472 | 5 changed (every tool) | quiet |
| 2026-09-28 | `remote/dev.workers.bhazarstudio.datoqa/economic-indicators` | 2026-09-28T141514722959 -> 2026-09-28T170323092201 | 13 changed (every tool) | quiet |
| 2026-09-28 | `remote/co.marketmayhem/mcp` | 2026-09-28T141737347328 -> 2026-09-28T170317566620 | 4 added | quiet |
| 2026-09-28 | `remote/io.github.kaminariouji/x402-audit-agent` | 2026-09-28T142116539859 -> 2026-09-28T170317721341 | 1 added | quiet |
| 2026-09-28 | `remote/io.github.Fizzl13/ichimoku-signal` | 2026-09-28T142055523471 -> 2026-09-28T170315291407 | 1 added | quiet |
| 2026-09-28 | `remote/com.campiamo/campsites` | 2026-09-28T141445691407 -> 2026-09-28T170314634041 | 4 changed | quiet |
| 2026-09-28 | `remote/io.github.Its-fortunatefolly/hubvibe` | 2026-09-28T141626367612 -> 2026-09-28T170311942703 | 3 added | quiet |
| 2026-09-28 | `remote/com.freelanceclearing/marketplace` | 2026-09-27T232557488288 -> 2026-09-28T170311130473 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.tettertotter/fundinglandscape` | 2026-09-28T141515906051 -> 2026-09-28T170309776503 | 4 changed | quiet |
| 2026-09-28 | `remote/io.github.jgaethle10/evercraft-machine-commerce` | 2026-09-28T141515843580 -> 2026-09-28T170309579589 | 4 changed, 1 added | quiet |
| 2026-09-28 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-09-28T141348249974 -> 2026-09-28T170307631436 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.tradewr333-lgtm/degenscan-intel` | 2026-09-28T141511966954 -> 2026-09-28T170306908877 | 1 added | quiet |
| 2026-09-28 | `remote/dev.workers.bhazarstudio.datoqa/historical-exchange-rates` | 2026-09-28T141508371422 -> 2026-09-28T170307424160 | 6 changed (every tool) | quiet |
| 2026-09-28 | `remote/dev.protogrid/registry` | 2026-09-28T141341533994 -> 2026-09-28T170308456445 | 5 changed (every tool) | quiet |
| 2026-09-28 | `remote/com.cymetica/event-trader-research` | 2026-09-28T141502810757 -> 2026-09-28T170308177478 | 4 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 9378 substantive, 3131 that changed only numbers (a catalogue counter ticking, a date), 136 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 7017 | 4042 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `caseyjhand.com` | 56 | 56 | 0 | 0 |
| `daedalmap.com` | 47 | 47 | 0 | 0 |
| `sistaminuten.se` | 35 | 2 | 0 | 33 |
| `afbudsrejser.dk` | 34 | 2 | 0 | 32 |
| `akkilahdot.fi` | 34 | 2 | 0 | 32 |
| `restplass.no` | 34 | 2 | 0 | 32 |
| `socialloop.ai` | 34 | 34 | 0 | 0 |
| `civai.co` | 24 | 24 | 0 | 0 |
| `dayze.com` | 24 | 24 | 0 | 0 |
| 1119 other operators | 2541 | 2378 | 156 | 7 |
