# MCP server tool changes

Last change observed 2026-09-29T00:36:26+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

12782 changes to a tool definition: 370 npm releases (124 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 12412 readings of hosted servers that found their tools changed; 53 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-09-29 | `remote/world.agentindex/x402` | 2026-09-28T170357441226 -> 2026-09-29T003629317635 | 1 added | quiet |
| 2026-09-29 | `remote/se.sistaminuten/travel-search` | 2026-09-28T170405273471 -> 2026-09-29T003626463444 | 1 changed | quiet |
| 2026-09-29 | `remote/no.restplass/travel-search` | 2026-09-28T170355108487 -> 2026-09-29T003625946965 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.tjcgraham-rgb/gaip-supplier-watch` | 2026-09-28T170356652292 -> 2026-09-29T003627163795 | 6 changed (every tool) | quiet |
| 2026-09-29 | `remote/io.github.Uuriko/project-room` | 2026-09-28T142316358482 -> 2026-09-29T003625881517 | 4 changed (every tool) | quiet |
| 2026-09-29 | `remote/com.projectthunder/site` | 2026-09-28T142332601620 -> 2026-09-29T003625808574 | 2 changed | quiet |
| 2026-09-29 | `remote/dk.afbudsrejser/travel-search` | 2026-09-28T170352328816 -> 2026-09-29T003624202162 | 1 changed | quiet |
| 2026-09-29 | `remote/ai.wem3/wem-price-compare` | 2026-09-28T142252785998 -> 2026-09-29T003623577973 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.tjcgraham-rgb/gaip-outcome-value` | 2026-09-28T170407646944 -> 2026-09-29T003625993257 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.tjcgraham-rgb/gaip-integration-protocol` | 2026-09-28T170403906385 -> 2026-09-29T003625404627 | 7 changed (every tool) | quiet |
| 2026-09-29 | `remote/io.github.tjcgraham-rgb/gaip-buyer-assurance` | 2026-09-28T170406975965 -> 2026-09-29T003625091072 | 3 changed (every tool) | quiet |
| 2026-09-29 | `remote/io.github.tjcgraham-rgb/gaip-broker` | 2026-09-28T170404016979 -> 2026-09-29T003624427780 | 4 added, 28 removed | quiet |
| 2026-09-29 | `remote/io.github.tjcgraham-rgb/gaip-art-intelligence` | 2026-09-28T142323411648 -> 2026-09-29T003625482687 | 1 changed | quiet |
| 2026-09-29 | `remote/xyz.trusteed/mcp-gateway` | 2026-09-28T104214995179 -> 2026-09-29T003622121499 | 5 changed | quiet |
| 2026-09-29 | `remote/com.contrie/contrie` | 2026-09-28T142315953673 -> 2026-09-29T003621663789 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.lonniev/tollbooth-authority-northamerica` | 2026-09-27T152940897879 -> 2026-09-29T003620081737 | 1 changed | quiet |
| 2026-09-29 | `remote/dog.swoleeswoge/swogeagentic` | 2026-09-28T142258217965 -> 2026-09-29T003620269922 | 7 added | quiet |
| 2026-09-29 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-09-28T142200652306 -> 2026-09-29T003618825206 | 15 changed | review |
| 2026-09-29 | `remote/io.github.lonniev/taxsort-mcp` | 2026-09-27T152929458463 -> 2026-09-29T003619640223 | 1 changed | quiet |
| 2026-09-29 | `remote/fr.synergieloc/immobilier` | 2026-09-28T073114394112 -> 2026-09-29T003620849049 | 66 changed (every tool) | quiet |
| 2026-09-29 | `remote/io.github.tjcgraham-rgb/gaip-witness` | 2026-09-28T170403907951 -> 2026-09-29T003621494940 | 10 changed (every tool) | quiet |
| 2026-09-29 | `remote/io.github.tjcgraham-rgb/gaip-procurement-verify` | 2026-09-28T170403193679 -> 2026-09-29T003621131326 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.tjcgraham-rgb/gaip-opportunity-broker` | 2026-09-28T142626198932 -> 2026-09-29T003621044173 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.tjcgraham-rgb/gaip-integration-repair` | 2026-09-28T170403881955 -> 2026-09-29T003620519402 | 2 changed (every tool) | quiet |
| 2026-09-29 | `remote/fi.akkilahdot/travel-search` | 2026-09-28T170359687025 -> 2026-09-29T003617741445 | 1 changed | quiet |
| 2026-09-29 | `remote/uk.co.transitradar/transitradar` | 2026-09-28T142234911948 -> 2026-09-29T003617447737 | 7 changed | quiet |
| 2026-09-29 | `remote/tech.viewprinter/viewprinter` | 2026-09-28T170357905128 -> 2026-09-29T003616273708 | 1 changed | quiet |
| 2026-09-29 | `remote/com.thefomite/fomite` | 2026-09-28T055524348952 -> 2026-09-29T003616588162 | 1 changed | quiet |
| 2026-09-29 | `remote/cloud.coredls.vigia/vigia` | 2026-09-28T142603568187 -> 2026-09-29T003617385537 | 1 changed, 1 added | quiet |
| 2026-09-29 | `remote/ai.synthfolk/directory` | 2026-09-28T142217051563 -> 2026-09-29T003615987318 | 4 added | quiet |
| 2026-09-29 | `remote/io.github.tjcgraham-rgb/gaip-trust-assurance` | 2026-09-28T142347288276 -> 2026-09-29T003618890475 | 5 changed (every tool) | quiet |
| 2026-09-29 | `remote/io.github.lonniev/schwab-mcp` | 2026-09-27T152904081140 -> 2026-09-29T003615558724 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.lonniev/tollbooth-sample` | 2026-09-27T133004101014 -> 2026-09-29T003615021112 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.lonniev/tollbooth-authority` | 2026-09-27T152839523707 -> 2026-09-29T003614241820 | 1 changed | quiet |
| 2026-09-29 | `remote/com.tickerinside/tickerinside-mcp` | 2026-09-28T142547261282 -> 2026-09-29T003613867050 | 2 added | quiet |
| 2026-09-29 | `remote/com.igods/space-monkey` | 2026-09-28T073226296413 -> 2026-09-29T003614264924 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-09-28T055533984059 -> 2026-09-29T003614178285 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.IO31-WEB/synapse-lounge` | 2026-09-28T142542887807 -> 2026-09-29T003614578455 | 3 changed, 11 added, 77 removed (every tool) | quiet |
| 2026-09-29 | `remote/com.synapticrelay/board.1` | 2026-09-28T142542146246 -> 2026-09-29T003613422463 | 1 changed, 1 added | quiet |
| 2026-09-29 | `remote/us.stratly/townsquare` | 2026-09-28T170350518591 -> 2026-09-29T003612004907 | 3 added | quiet |
| 2026-09-29 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-28T170349981137 -> 2026-09-29T003612400876 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.lonniev/tollbooth-authority-newengland` | 2026-09-27T153345848853 -> 2026-09-29T003613073603 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.joeyaflores/ourpr-courses` | 2026-09-28T142040682508 -> 2026-09-29T003611314228 | 2 changed | quiet |
| 2026-09-29 | `remote/io.github.lonniev/roastify-mcp` | 2026-09-27T152840044388 -> 2026-09-29T003610539214 | 1 changed | quiet |
| 2026-09-29 | `remote/com.innergcomplete/shearquery` | 2026-09-28T073109015141 -> 2026-09-29T003610312533 | 27 added | quiet |
| 2026-09-29 | `remote/io.github.jaymiller-cmg/mortgage-hawaii` | 2026-09-28T142132481980 -> 2026-09-29T003609673422 | 1 changed | quiet |
| 2026-09-29 | `remote/com.searchfragments/search-fragments` | 2026-09-28T142510933823 -> 2026-09-29T003609769004 | 1 changed | quiet |
| 2026-09-29 | `remote/com.saylorinnovations/data` | 2026-09-28T142505494609 -> 2026-09-29T003607717244 | 1 changed | quiet |
| 2026-09-29 | `remote/com.ryufin/stocks` | 2026-09-28T142503177760 -> 2026-09-29T003608930648 | 1 changed | quiet |
| 2026-09-29 | `remote/com.risetive/mcp` | 2026-09-28T142458397260 -> 2026-09-29T003607223281 | 2 changed | quiet |
| 2026-09-29 | `remote/io.github.lonniev/personalbrain-mcp` | 2026-09-27T152814320977 -> 2026-09-29T003606062235 | 1 changed | quiet |
| 2026-09-29 | `remote/com.remoshift/jobs` | 2026-09-28T170343984308 -> 2026-09-29T003606598740 | 1 changed | quiet |
| 2026-09-29 | `remote/io.orbitwan/orbitwan` | 2026-09-27T232605740695 -> 2026-09-29T003606684889 | 1 added | quiet |
| 2026-09-29 | `remote/io.github.yzlee/opcmenu` | 2026-09-28T141919947029 -> 2026-09-29T003608302834 | 16 changed, 18 added | quiet |
| 2026-09-29 | `remote/io.github.moralito311-andr/andreax` | 2026-09-28T142058496152 -> 2026-09-29T003606355313 | 5 added | quiet |
| 2026-09-29 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-09-28T055520147548 -> 2026-09-29T003606948434 | 1 changed | quiet |
| 2026-09-29 | `remote/pl.klyo/games` | 2026-09-28T073025779484 -> 2026-09-29T003604784057 | 1 changed | quiet |
| 2026-09-29 | `remote/com.ribqa/sentinel-aleph` | 2026-09-28T142148542971 -> 2026-09-29T003604263675 | 10 changed, 3 added (every tool) | quiet |
| 2026-09-29 | `remote/com.nabarfinder/nabarfinder` | 2026-09-28T073102286258 -> 2026-09-29T003604704241 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.terradev-cloud/prism` | 2026-09-28T142127213849 -> 2026-09-29T003602019714 | 3 removed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 9500 substantive, 3142 that changed only numbers (a catalogue counter ticking, a date), 140 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 7017 | 4042 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `caseyjhand.com` | 56 | 56 | 0 | 0 |
| `daedalmap.com` | 47 | 47 | 0 | 0 |
| `sistaminuten.se` | 36 | 2 | 0 | 34 |
| `afbudsrejser.dk` | 35 | 2 | 0 | 33 |
| `akkilahdot.fi` | 35 | 2 | 0 | 33 |
| `restplass.no` | 35 | 2 | 0 | 33 |
| `socialloop.ai` | 35 | 35 | 0 | 0 |
| `dayze.com` | 26 | 26 | 0 | 0 |
| `fastmcp.app` | 25 | 25 | 0 | 0 |
| 1155 other operators | 2670 | 2496 | 167 | 7 |
