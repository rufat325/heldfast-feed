# MCP server tool changes

Last change observed 2026-10-03T05:47:56+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

18491 changes to a tool definition: 545 npm releases (299 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 17946 readings of hosted servers that found their tools changed; 170 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-10-03 | `remote/xn--3ds443g.xn--s7y/duan-online` | 2026-10-01T134451005411 -> 2026-10-03T054757881534 | 2 changed | quiet |
| 2026-10-03 | `remote/se.sistaminuten/travel-search` | 2026-10-02T210148407547 -> 2026-10-03T054756608617 | 1 changed | quiet |
| 2026-10-03 | `remote/tennis.courts/nyc-tennis-courts` | 2026-10-02T072219137385 -> 2026-10-03T054749714746 | 3 changed | quiet |
| 2026-10-03 | `remote/fi.akkilahdot/travel-search` | 2026-10-02T210139594821 -> 2026-10-03T054748663076 | 1 changed | quiet |
| 2026-10-03 | `remote/tech.viewprinter/viewprinter` | 2026-10-02T210137916770 -> 2026-10-03T054747906608 | 7 changed | quiet |
| 2026-10-03 | `remote/com.youspot/youspot` | 2026-10-02T210158057865 -> 2026-10-03T054748706303 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-01T212500203845 -> 2026-10-03T054748099315 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.presendapp/presend-mcp` | 2026-10-02T150327180709 -> 2026-10-03T054744884575 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.dtajitdinov-aris/sphere-marketplace` | 2026-10-02T182749986406 -> 2026-10-03T054746775288 | 1 added, 1 removed | quiet |
| 2026-10-03 | `remote/io.github.Jaywestphilly/stock-bloc` | 2026-10-02T182752958635 -> 2026-10-03T054745683407 | 9 changed | quiet |
| 2026-10-03 | `remote/com.swarmmemo/bulletin` | 2026-10-02T130043523211 -> 2026-10-03T054746577688 | 1 changed | quiet |
| 2026-10-03 | `remote/com.predictionmarketspicks/quant` | 2026-10-02T130042233428 -> 2026-10-03T054745713003 | 33 changed (every tool) | quiet |
| 2026-10-03 | `remote/com.makometrics/mako-metrics` | 2026-10-02T210154103198 -> 2026-10-03T054745367452 | 1 changed | quiet |
| 2026-10-03 | `remote/science.pith/pith` | 2026-10-02T080604894811 -> 2026-10-03T054744328251 | 1 changed | quiet |
| 2026-10-03 | `remote/org.opentaskrelay/open-task-relay` | 2026-10-01T134211130893 -> 2026-10-03T054745037735 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-02T210132562801 -> 2026-10-03T054744613837 | 4 changed | quiet |
| 2026-10-03 | `remote/no.restplass/travel-search` | 2026-10-02T210133748473 -> 2026-10-03T054743569309 | 1 changed | quiet |
| 2026-10-03 | `remote/com.remoshift/jobs` | 2026-10-02T210130667614 -> 2026-10-03T054743576118 | 1 changed | quiet |
| 2026-10-03 | `remote/de.honestdog/honestdog` | 2026-10-01T212507654868 -> 2026-10-03T054743440285 | 5 changed (every tool) | quiet |
| 2026-10-03 | `remote/com.predictionmarketspicks/weather` | 2026-10-02T125936374828 -> 2026-10-03T054743145385 | 6 changed (every tool) | quiet |
| 2026-10-03 | `remote/com.predictionmarketspicks/fantasy-draft` | 2026-10-02T125936216511 -> 2026-10-03T054743215999 | 8 changed (every tool) | quiet |
| 2026-10-03 | `remote/com.predictionmarketspicks/commodities` | 2026-10-02T125936271100 -> 2026-10-03T054742944298 | 8 changed (every tool) | quiet |
| 2026-10-03 | `remote/com.narrowhighway/concordance` | 2026-10-01T212502376246 -> 2026-10-03T054742691124 | 97 changed (every tool) | quiet |
| 2026-10-03 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-02T061625284876 -> 2026-10-03T054743271458 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.cnghockey/sats4ai` | 2026-10-02T061625681197 -> 2026-10-03T054742215122 | 1 changed | quiet |
| 2026-10-03 | `remote/dk.afbudsrejser/travel-search` | 2026-10-02T210132369860 -> 2026-10-03T054742595143 | 1 changed | quiet |
| 2026-10-03 | `remote/com.multicinesortega/cartelera` | 2026-10-02T210128513534 -> 2026-10-03T054741962877 | 1 changed | quiet |
| 2026-10-03 | `remote/xyz.trusteed/mcp-gateway` | 2026-10-02T061627270174 -> 2026-10-03T054741253391 | 1 added | quiet |
| 2026-10-03 | `remote/ai.switchapp/switch` | 2026-10-02T061621252768 -> 2026-10-03T054740213074 | 1 added | quiet |
| 2026-10-03 | `remote/io.github.samuelzcom/chauffeur-booking` | 2026-10-02T130341499692 -> 2026-10-03T054743984212 | 5 changed (every tool) | quiet |
| 2026-10-03 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-10-02T150312321190 -> 2026-10-03T054738929677 | 15 changed | review |
| 2026-10-03 | `remote/com.luxurylodgingpm.stay/luxury-lodging` | 2026-10-02T210127498077 -> 2026-10-03T054738744060 | 2 changed | quiet |
| 2026-10-03 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-02T210127161409 -> 2026-10-03T054738098015 | 2 changed | quiet |
| 2026-10-03 | `remote/app.pixly/pixly` | 2026-10-02T210145041111 -> 2026-10-03T054739410038 | 25 changed | quiet |
| 2026-10-03 | `remote/io.github.sam1siam/ruagentic-directory` | 2026-10-02T072013289036 -> 2026-10-03T054737522666 | 2 changed, 5 added (every tool) | quiet |
| 2026-10-03 | `remote/com.jojapi/swift-ai` | 2026-10-02T061617361989 -> 2026-10-03T054737619805 | 1 changed | quiet |
| 2026-10-03 | `remote/com.straelo/relay` | 2026-10-01T154249842433 -> 2026-10-03T054736497042 | 1 changed | quiet |
| 2026-10-03 | `remote/com.gojinko.mcp/jinko` | 2026-10-02T182459949657 -> 2026-10-03T054736706528 | 2 changed | quiet |
| 2026-10-03 | `remote/com.donebear/donebear` | 2026-10-02T210121304144 -> 2026-10-03T054736935533 | 2 added | quiet |
| 2026-10-03 | `remote/app.sallim/korea-realty` | 2026-10-02T150311460598 -> 2026-10-03T054737509251 | 3 changed | quiet |
| 2026-10-03 | `remote/ai.rokha/rokha` | 2026-10-02T182805298963 -> 2026-10-03T054736800163 | 7 changed | quiet |
| 2026-10-03 | `remote/ai.forkmate/forkmate` | 2026-10-01T154223622543 -> 2026-10-03T054736320041 | 2 changed | quiet |
| 2026-10-03 | `remote/io.github.Smartoire/paxaver-mcp` | 2026-10-02T071836783178 -> 2026-10-03T054734415507 | 1 changed, 25 added, 20 removed | quiet |
| 2026-10-03 | `remote/trade.loomdesk/loomdesk` | 2026-10-01T212443458435 -> 2026-10-03T054734316372 | 1 changed, 3 removed | quiet |
| 2026-10-03 | `remote/pro.particle/particle-pro` | 2026-10-02T061616964202 -> 2026-10-03T054734790800 | 2 changed | quiet |
| 2026-10-03 | `remote/io.github.federico2001/openglass-mcp` | 2026-10-02T061617253899 -> 2026-10-03T054733875805 | 1 added | quiet |
| 2026-10-03 | `remote/gl.parse/mcp` | 2026-10-01T134032137834 -> 2026-10-03T054734719418 | 31 changed, 20 added (every tool) | quiet |
| 2026-10-03 | `remote/io.github.jamie7893/keelen` | 2026-10-02T150305306660 -> 2026-10-03T054732664534 | 42 changed (every tool) | quiet |
| 2026-10-03 | `remote/io.github.jamboree777/nightwatch` | 2026-10-02T150322564846 -> 2026-10-03T054734728305 | 1 changed | quiet |
| 2026-10-03 | `remote/com.metricduck/financial-analysis` | 2026-10-02T150317854609 -> 2026-10-03T054732810861 | 1 changed | quiet |
| 2026-10-03 | `remote/ai.muffed/muffed` | 2026-10-02T071911268680 -> 2026-10-03T054734305255 | 7 changed | quiet |
| 2026-10-03 | `remote/store.getsoma/soma-brewing` | 2026-10-02T125519411922 -> 2026-10-03T054731466654 | 1 added | quiet |
| 2026-10-03 | `remote/net.hotelrefund/price-tracker` | 2026-10-02T150303543508 -> 2026-10-03T054731852472 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt` | 2026-10-02T061609804627 -> 2026-10-03T054730845541 | 1 changed | quiet |
| 2026-10-03 | `remote/dev.horizonshield/horizon-shield` | 2026-10-02T182428259407 -> 2026-10-03T054730433968 | 1 changed, 15 removed | quiet |
| 2026-10-03 | `remote/com.tradestarinsider/edgar-insider-signals` | 2026-10-01T133942677073 -> 2026-10-03T054732284754 | 4 changed | quiet |
| 2026-10-03 | `remote/io.github.ogasurfproject-jpg/horizon-shield` | 2026-10-02T182428217968 -> 2026-10-03T054730366502 | 1 changed, 15 removed | quiet |
| 2026-10-03 | `remote/io.orbitwan/orbitwan` | 2026-10-02T130430411210 -> 2026-10-03T054730689689 | 2 changed, 1 added | quiet |
| 2026-10-03 | `remote/io.github.yzlee/opcmenu` | 2026-10-02T210122212951 -> 2026-10-03T054733422652 | 2 changed | quiet |
| 2026-10-03 | `remote/com.multilocale/multilocale` | 2026-10-02T071809016356 -> 2026-10-03T054729572595 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 13493 substantive, 4752 that changed only numbers (a catalogue counter ticking, a date), 246 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 10138 | 5671 | 4467 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `caseyjhand.com` | 66 | 66 | 0 | 0 |
| `sistaminuten.se` | 61 | 2 | 0 | 59 |
| `afbudsrejser.dk` | 60 | 2 | 0 | 58 |
| `akkilahdot.fi` | 60 | 2 | 0 | 58 |
| `restplass.no` | 60 | 2 | 0 | 58 |
| `socialloop.ai` | 59 | 59 | 0 | 0 |
| `dayze.com` | 53 | 53 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| 1843 other operators | 5021 | 4723 | 285 | 13 |
