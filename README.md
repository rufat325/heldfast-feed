# MCP server tool changes

Last change observed 2026-09-30T06:01:46+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

13496 changes to a tool definition: 384 npm releases (138 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 13112 readings of hosted servers that found their tools changed; 88 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-09-30 | `remote/io.github.mlolahq/mlola-ui` | 2026-09-29T061638951385 -> 2026-09-30T060149735722 | 1 changed | quiet |
| 2026-09-30 | `remote/io.github.FTHTrading/genesis402-mcp` | 2026-09-29T061634442590 -> 2026-09-30T060147388240 | 1 changed | quiet |
| 2026-09-30 | `remote/us.thistripbtw/trips` | 2026-09-28T073122519876 -> 2026-09-30T060145603555 | 1 changed | quiet |
| 2026-09-30 | `remote/io.taifoon/coordination-layer` | 2026-09-29T210509951310 -> 2026-09-30T060144249530 | 4 changed | quiet |
| 2026-09-30 | `remote/no.restplass/travel-search` | 2026-09-29T210509288559 -> 2026-09-30T060143709015 | 1 changed | quiet |
| 2026-09-30 | `remote/io.stackcut/stackcut` | 2026-09-28T142227354482 -> 2026-09-30T060141989702 | 3 added | quiet |
| 2026-09-30 | `remote/dk.afbudsrejser/travel-search` | 2026-09-29T210506237804 -> 2026-09-30T060141073013 | 1 changed | quiet |
| 2026-09-30 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-09-29T003606948434 -> 2026-09-30T060141576023 | 1 changed | quiet |
| 2026-09-30 | `remote/io.github.davisvillelabs/scopeproof` | 2026-09-29T210503555770 -> 2026-09-30T060139848636 | 3 added, 3 removed | quiet |
| 2026-09-30 | `remote/io.github.cnghockey/sats4ai` | 2026-09-28T073041769916 -> 2026-09-30T060140115973 | 1 changed | quiet |
| 2026-09-30 | `remote/se.sistaminuten/travel-search` | 2026-09-29T210514960164 -> 2026-09-30T060138520153 | 1 changed | quiet |
| 2026-09-30 | `remote/io.github.lonniev/tollbooth-authority-northamerica` | 2026-09-29T061656396760 -> 2026-09-30T060137681641 | 3 changed | quiet |
| 2026-09-30 | `remote/io.github.bnmbnmai/bnm-data-shop` | 2026-09-29T210518353797 -> 2026-09-30T060154619646 | 4 changed, 2 added | quiet |
| 2026-09-30 | `remote/io.github.lonniev/taxsort-mcp` | 2026-09-29T003619640223 -> 2026-09-30T060136870534 | 3 changed | quiet |
| 2026-09-30 | `remote/fi.akkilahdot/travel-search` | 2026-09-29T210517826751 -> 2026-09-30T060135687287 | 1 changed | quiet |
| 2026-09-30 | `remote/io.github.tjcgraham-rgb/gaip-broker` | 2026-09-29T003624427780 -> 2026-09-30T060137121350 | 1 changed | quiet |
| 2026-09-30 | `remote/com.plainrouter/mcp` | 2026-09-29T061625139609 -> 2026-09-30T060135733718 | 1 changed | quiet |
| 2026-09-30 | `remote/com.contrie/contrie` | 2026-09-29T061659986627 -> 2026-09-30T060133816716 | 1 added | quiet |
| 2026-09-30 | `remote/com.blitzreels/blitzreels` | 2026-09-28T170400298826 -> 2026-09-30T060139872226 | 10 changed, 46 added | quiet |
| 2026-09-30 | `remote/tech.viewprinter/viewprinter` | 2026-09-29T003616273708 -> 2026-09-30T060132952326 | 1 changed | quiet |
| 2026-09-30 | `remote/ru.vedarai/mcp` | 2026-09-29T131547806736 -> 2026-09-30T060134324213 | 5 changed | quiet |
| 2026-09-30 | `remote/io.railagent/railagent` | 2026-09-28T142107983159 -> 2026-09-30T060130271739 | 1 changed | quiet |
| 2026-09-30 | `remote/dev.mcphost/mcphost` | 2026-09-28T055516117136 -> 2026-09-30T060131747669 | 135 changed | quiet |
| 2026-09-30 | `remote/io.github.lonniev/tollbooth-authority` | 2026-09-29T061652153921 -> 2026-09-30T060133079183 | 3 changed | quiet |
| 2026-09-30 | `remote/io.github.lbailey94/whitemagic-mcp` | 2026-09-28T142012434233 -> 2026-09-30T060129252037 | 1 added | quiet |
| 2026-09-30 | `remote/com.tickerinside/tickerinside-mcp` | 2026-09-29T210513325765 -> 2026-09-30T060129548571 | 1 changed | quiet |
| 2026-09-30 | `remote/com.thefomite/fomite` | 2026-09-29T003616588162 -> 2026-09-30T060128257073 | 1 changed | quiet |
| 2026-09-30 | `remote/io.github.steffanricardo/the-dutch-directory` | 2026-09-29T101139866576 -> 2026-09-30T060128679610 | 15 changed (every tool) | quiet |
| 2026-09-30 | `remote/dev.sitemcp/site-mcp` | 2026-09-28T142205372602 -> 2026-09-30T060126448452 | 2 changed | quiet |
| 2026-09-30 | `remote/com.swarmmemo/bulletin` | 2026-09-29T210512012862 -> 2026-09-30T060127828325 | 27 changed (every tool) | quiet |
| 2026-09-30 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-29T210509396083 -> 2026-09-30T060125794058 | 2 changed, 26 added | quiet |
| 2026-09-30 | `remote/insure.spot/insurance-research` | 2026-09-29T073738829930 -> 2026-09-30T060129125569 | 2 changed | quiet |
| 2026-09-30 | `remote/io.github.untitledfinancial/dpx` | 2026-09-28T072932101074 -> 2026-09-30T060123687415 | 1 added | quiet |
| 2026-09-30 | `remote/io.github.SidneyBissoli/sih-br-mcp` | 2026-09-28T142519517582 -> 2026-09-30T060124548937 | 1 changed | quiet |
| 2026-09-30 | `remote/com.jojapi/product-barcode-api` | 2026-09-28T072831218732 -> 2026-09-30T060125304159 | 1 changed | quiet |
| 2026-09-30 | `remote/com.sourcey/sourcey` | 2026-09-28T072922613541 -> 2026-09-30T060123097047 | 1 changed | quiet |
| 2026-09-30 | `remote/com.innergcomplete/shearquery` | 2026-09-29T210513799596 -> 2026-09-30T060126559877 | 6 changed, 3 added | quiet |
| 2026-09-30 | `remote/ai.skillsinput/mcp` | 2026-09-28T141940024290 -> 2026-09-30T060122835618 | 1 changed | quiet |
| 2026-09-30 | `remote/ai.satohub/onchain-agents` | 2026-09-29T061649411357 -> 2026-09-30T060123737078 | 34 changed, 1 added | quiet |
| 2026-09-30 | `remote/io.github.yzlee/opcmenu` | 2026-09-29T003608302834 -> 2026-09-30T060127338935 | 6 changed | quiet |
| 2026-09-30 | `remote/io.github.kylehawke-stack/locationlists` | 2026-09-29T210438498014 -> 2026-09-30T060120263211 | 9 changed | quiet |
| 2026-09-30 | `remote/com.predictionmarketspicks/quant` | 2026-09-29T073212338760 -> 2026-09-30T060121259145 | 32 changed | quiet |
| 2026-09-30 | `remote/com.hardcopylabs/hardcopy` | 2026-09-28T141844756524 -> 2026-09-30T060119971886 | 3 changed, 1 added | quiet |
| 2026-09-30 | `remote/co.macrocyber/attack-surface` | 2026-09-28T141754045879 -> 2026-09-30T060120907382 | 1 changed | quiet |
| 2026-09-30 | `remote/de.livaglow/livaglow-shop` | 2026-09-28T103747854500 -> 2026-09-30T060120700378 | 1 changed | quiet |
| 2026-09-30 | `remote/com.remoshift/jobs` | 2026-09-29T210503698304 -> 2026-09-30T060120556877 | 1 changed | quiet |
| 2026-09-30 | `remote/com.radar-cnpj/radar-cnpj` | 2026-09-29T210504032087 -> 2026-09-30T060120517361 | 1 changed, 1 added | quiet |
| 2026-09-30 | `remote/so.darwin/darwin` | 2026-09-29T210438368666 -> 2026-09-30T060119274371 | 2 added, 1 removed | quiet |
| 2026-09-30 | `remote/com.predictionmarketspicks/commodities` | 2026-09-28T142441346728 -> 2026-09-30T060119632593 | 7 changed | quiet |
| 2026-09-30 | `remote/ai.agent-bev/bev-door` | 2026-09-28T141809498573 -> 2026-09-30T060117478520 | 9 changed (every tool) | quiet |
| 2026-09-30 | `remote/pl.klyo/games` | 2026-09-29T210502292852 -> 2026-09-30T060119179040 | 1 changed | quiet |
| 2026-09-30 | `remote/io.github.foxxx009/x402-tools-mcp` | 2026-09-28T072604588711 -> 2026-09-30T060119731347 | 5 added | quiet |
| 2026-09-30 | `remote/io.github.Russ4102/fixragent` | 2026-09-28T141555234109 -> 2026-09-30T060115424414 | 3 changed (every tool) | quiet |
| 2026-09-30 | `remote/com.opointo/opointo` | 2026-09-29T210459607033 -> 2026-09-30T060117618752 | 1 changed, 2 added | quiet |
| 2026-09-30 | `remote/io.github.moralito311-andr/andreax` | 2026-09-29T073200978448 -> 2026-09-30T060117527532 | 1 changed, 3 added | quiet |
| 2026-09-30 | `remote/io.github.fetchsandbox/mcp` | 2026-09-29T210432552710 -> 2026-09-30T060114994138 | 1 changed | quiet |
| 2026-09-30 | `remote/com.multicinesortega/cartelera` | 2026-09-29T073538683683 -> 2026-09-30T060115415504 | 1 changed | quiet |
| 2026-09-30 | `remote/io.github.steffanricardo/the-dutch-directory.1` | 2026-09-29T101625980794 -> 2026-09-30T060113694653 | 15 changed (every tool) | quiet |
| 2026-09-30 | `remote/ai.switchapp/switch` | 2026-09-29T101620640090 -> 2026-09-30T060112494297 | 4 changed, 2 added | quiet |
| 2026-09-30 | `remote/com.shipstatic/mcp` | 2026-09-29T113209248163 -> 2026-09-30T060112034905 | 5 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 10135 substantive, 3175 that changed only numbers (a catalogue counter ticking, a date), 186 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 7023 | 4048 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `caseyjhand.com` | 56 | 56 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| `sistaminuten.se` | 47 | 2 | 0 | 45 |
| `afbudsrejser.dk` | 46 | 2 | 0 | 44 |
| `akkilahdot.fi` | 46 | 2 | 0 | 44 |
| `restplass.no` | 46 | 2 | 0 | 44 |
| `socialloop.ai` | 46 | 46 | 0 | 0 |
| `fastmcp.app` | 41 | 41 | 0 | 0 |
| `dayze.com` | 34 | 34 | 0 | 0 |
| 1323 other operators | 3295 | 3086 | 200 | 9 |
