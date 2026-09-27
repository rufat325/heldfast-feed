# MCP server tool changes

Last change observed 2026-09-27T15:34:55+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9409 npm servers from the official MCP registry (154 daily, the rest weekly) and 18576 hosted endpoints (daily).

12015 changes to a tool definition: 347 npm releases (101 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 11668 readings of hosted servers that found their tools changed; 17 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-09-27 | `remote/app.shotlee/shotlee` | 2026-09-23T160851830337 -> 2026-09-27T153456974512 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.lonniev/tollbooth-authority-newengland` | 2026-09-23T160812031004 -> 2026-09-27T153345848853 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.Skyline-Roofing/oracle-api` | 2026-09-23T160704859107 -> 2026-09-27T153150385481 | 3 changed, 1 added | quiet |
| 2026-09-27 | `remote/io.github.lonniev/optionality-mcp` | 2026-09-23T160705061811 -> 2026-09-27T153150672635 | 1 changed | quiet |
| 2026-09-27 | `remote/dev.mcphost/mcphost` | 2026-09-27T120856254978 -> 2026-09-27T153107221351 | 4 added | quiet |
| 2026-09-27 | `remote/com.tipranks/tipranks` | 2026-09-23T160622962981 -> 2026-09-27T153044454812 | 11 changed | review |
| 2026-09-27 | `remote/world.agentindex/x402` | 2026-09-26T045458962346 -> 2026-09-27T153031760329 | 18 changed (every tool) | quiet |
| 2026-09-27 | `remote/no.restplass/travel-search` | 2026-09-27T141927079276 -> 2026-09-27T153021314123 | 1 changed | quiet |
| 2026-09-27 | `remote/com.rekvira/rekvira` | 2026-09-27T120818450649 -> 2026-09-27T153025862877 | 1 changed | quiet |
| 2026-09-27 | `remote/dk.afbudsrejser/travel-search` | 2026-09-27T141925950330 -> 2026-09-27T153005315943 | 1 changed | quiet |
| 2026-09-27 | `remote/se.sistaminuten/travel-search` | 2026-09-27T141941311538 -> 2026-09-27T153003339715 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.lonniev/tollbooth-authority-northamerica` | 2026-09-23T163046752764 -> 2026-09-27T152940897879 | 1 changed | quiet |
| 2026-09-27 | `remote/com.voxodds/voxodds` | 2026-09-23T161009295055 -> 2026-09-27T152935172972 | 3 changed | quiet |
| 2026-09-27 | `remote/io.github.lonniev/taxsort-mcp` | 2026-09-23T163031329410 -> 2026-09-27T152929458463 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-09-27T131051121285 -> 2026-09-27T152922619523 | 15 changed | review |
| 2026-09-27 | `remote/fi.akkilahdot/travel-search` | 2026-09-27T141932678065 -> 2026-09-27T152907535270 | 1 changed | quiet |
| 2026-09-27 | `remote/org.btcdecoded/intelligence` | 2026-09-24T120117562367 -> 2026-09-27T152905447581 | 2 changed | quiet |
| 2026-09-27 | `remote/io.github.lonniev/schwab-mcp` | 2026-09-23T162954065873 -> 2026-09-27T152904081140 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.stevologic/security-recipes` | 2026-09-23T160932043127 -> 2026-09-27T152851564026 | 75 changed (every tool) | quiet |
| 2026-09-27 | `remote/io.github.lonniev/tollbooth-authority` | 2026-09-23T162910803741 -> 2026-09-27T152839523707 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.lonniev/roastify-mcp` | 2026-09-23T160923289684 -> 2026-09-27T152840044388 | 1 changed | quiet |
| 2026-09-27 | `remote/com.pasteapply/mcp` | 2026-09-27T065823324602 -> 2026-09-27T152824000045 | 2 changed | quiet |
| 2026-09-27 | `remote/io.github.presendapp/presend-mcp` | 2026-09-26T192536331357 -> 2026-09-27T152819983397 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-27T141928499700 -> 2026-09-27T152819330019 | 1 changed | quiet |
| 2026-09-27 | `remote/com.plainfreight/quotes` | 2026-09-27T135130876555 -> 2026-09-27T152816499809 | 5 changed (every tool) | quiet |
| 2026-09-27 | `remote/io.github.lonniev/personalbrain-mcp` | 2026-09-23T160855867737 -> 2026-09-27T152814320977 | 1 changed | quiet |
| 2026-09-27 | `remote/page.ship/ship-page` | 2026-09-23T162848297799 -> 2026-09-27T152813119058 | 2 changed | quiet |
| 2026-09-27 | `remote/io.github.moralito311-andr/andreax` | 2026-09-27T131021747178 -> 2026-09-27T152810273387 | 2 changed, 1 added | review |
| 2026-09-27 | `remote/io.github.89rat/openfang-rail` | 2026-09-23T160436540641 -> 2026-09-27T152746283139 | 12 changed (every tool) | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/zippopotam` | 2026-09-24T211859602119 -> 2026-09-27T152729416778 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/zendesk` | 2026-09-24T211859418800 -> 2026-09-27T152728924332 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/yc-rejection` | 2026-09-24T211859136309 -> 2026-09-27T152728854655 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/xome` | 2026-09-24T211859075754 -> 2026-09-27T152728254056 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/xero` | 2026-09-24T211858909775 -> 2026-09-27T152728145285 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/worldbank-projects` | 2026-09-24T211858827997 -> 2026-09-27T152728432730 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/worldbank-climate` | 2026-09-24T211858687591 -> 2026-09-27T152727645964 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/words` | 2026-09-24T211858608322 -> 2026-09-27T152727776274 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/wolfram-alpha` | 2026-09-24T211858400707 -> 2026-09-27T152727550781 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/wmata` | 2026-09-24T211858460545 -> 2026-09-27T152727118746 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/wikiviews` | 2026-09-24T211858191458 -> 2026-09-27T152727099891 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/wikiquote` | 2026-09-24T211858167698 -> 2026-09-27T152726652989 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/wikipedia` | 2026-09-24T211857984171 -> 2026-09-27T152726522381 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/wikipathways` | 2026-09-24T211857936245 -> 2026-09-27T152727034079 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/wikifeed` | 2026-09-24T211857770329 -> 2026-09-27T152726179884 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/wikidata-sparql` | 2026-09-24T211857482310 -> 2026-09-27T152725686487 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/who-tb` | 2026-09-24T211857244933 -> 2026-09-27T152725959362 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/who-gho` | 2026-09-24T211857045759 -> 2026-09-27T152726021161 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/wger` | 2026-09-24T211856853921 -> 2026-09-27T152725198603 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/west-virginia-code` | 2026-09-24T211856631878 -> 2026-09-27T152725025335 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.proplineapi/propline-mcp` | 2026-09-27T055151268867 -> 2026-09-27T152720178568 | 2 changed | quiet |
| 2026-09-27 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-09-26T231045972224 -> 2026-09-27T152632857112 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.danafitkowski/cpp-cpm-engine` | 2026-09-23T162703491736 -> 2026-09-27T152631928977 | 3 changed | quiet |
| 2026-09-27 | `remote/ai.oobeprotocol.sap.mcp/sap-mcp` | 2026-09-26T132452926521 -> 2026-09-27T152622996496 | 4 changed | quiet |
| 2026-09-27 | `remote/com.hiddenswap/swap` | 2026-09-23T162547371846 -> 2026-09-27T152512026473 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.lonniev/goodearth-mcp` | 2026-09-23T162539576376 -> 2026-09-27T152503008037 | 1 changed | quiet |
| 2026-09-27 | `remote/com.factanker/factanker` | 2026-09-23T160504337103 -> 2026-09-27T152341526516 | 4 changed, 4 added | quiet |
| 2026-09-27 | `remote/io.github.lonniev/excalibur-mcp` | 2026-09-23T160505434969 -> 2026-09-27T152340503374 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.lonniev/cypher-mcp` | 2026-09-23T160436160120 -> 2026-09-27T152313059147 | 1 changed | quiet |
| 2026-09-27 | `remote/com.cve-security/cve-intelligence` | 2026-09-23T160435949407 -> 2026-09-27T152312275593 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.schneidavie/fund-momentum` | 2026-09-24T202058407571 -> 2026-09-27T152254327472 | 2 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 8820 substantive, 3094 that changed only numbers (a catalogue counter ticking, a date), 101 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 7016 | 4041 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `caseyjhand.com` | 55 | 55 | 0 | 0 |
| `daedalmap.com` | 47 | 47 | 0 | 0 |
| `sistaminuten.se` | 27 | 2 | 0 | 25 |
| `afbudsrejser.dk` | 26 | 2 | 0 | 24 |
| `akkilahdot.fi` | 26 | 2 | 0 | 24 |
| `restplass.no` | 26 | 2 | 0 | 24 |
| `socialloop.ai` | 26 | 26 | 0 | 0 |
| `assetfare.dev` | 20 | 20 | 0 | 0 |
| `dayze.com` | 20 | 20 | 0 | 0 |
| 949 other operators | 1961 | 1838 | 119 | 4 |
