# MCP server tool changes

Last change observed 2026-09-29T06:17:04+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

12855 changes to a tool definition: 370 npm releases (124 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 12485 readings of hosted servers that found their tools changed; 57 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-09-29 | `remote/se.sistaminuten/travel-search` | 2026-09-29T003626463444 -> 2026-09-29T061705162924 | 1 changed | quiet |
| 2026-09-29 | `remote/no.restplass/travel-search` | 2026-09-29T003625946965 -> 2026-09-29T061703818442 | 1 changed | quiet |
| 2026-09-29 | `remote/dk.afbudsrejser/travel-search` | 2026-09-29T003624202162 -> 2026-09-29T061702020477 | 1 changed | quiet |
| 2026-09-29 | `remote/com.contrie/contrie` | 2026-09-29T003621663789 -> 2026-09-29T061659986627 | 3 changed | quiet |
| 2026-09-29 | `remote/dog.swoleeswoge/swogeagentic` | 2026-09-29T003620269922 -> 2026-09-29T061658505250 | 4 added | review |
| 2026-09-29 | `remote/io.github.lonniev/tollbooth-authority-northamerica` | 2026-09-29T003620081737 -> 2026-09-29T061656396760 | 1 added | quiet |
| 2026-09-29 | `remote/fi.akkilahdot/travel-search` | 2026-09-29T003617741445 -> 2026-09-29T061655461447 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-09-29T003618825206 -> 2026-09-29T061655023363 | 15 changed | review |
| 2026-09-29 | `remote/fr.synergieloc/immobilier` | 2026-09-29T003620849049 -> 2026-09-29T061656484421 | 1 changed, 4 added | quiet |
| 2026-09-29 | `remote/io.github.lonniev/tollbooth-authority` | 2026-09-29T003614241820 -> 2026-09-29T061652153921 | 1 added | quiet |
| 2026-09-29 | `remote/com.tickerinside/tickerinside-mcp` | 2026-09-29T003613867050 -> 2026-09-29T061651208004 | 1 changed | review |
| 2026-09-29 | `remote/com.igods/space-monkey` | 2026-09-29T003614264924 -> 2026-09-29T061651196221 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-29T003612400876 -> 2026-09-29T061649371691 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.SiliconAnalysts/silicon-analysts` | 2026-09-28T073111117653 -> 2026-09-29T061649084344 | 2 changed | quiet |
| 2026-09-29 | `remote/ai.satohub/onchain-agents` | 2026-09-27T141933950921 -> 2026-09-29T061649411357 | 6 changed | quiet |
| 2026-09-29 | `remote/com.innergcomplete/shearquery` | 2026-09-29T003610312533 -> 2026-09-29T061648203636 | 2 changed, 5 added | quiet |
| 2026-09-29 | `remote/ai.rokha/rokha` | 2026-09-28T142126680965 -> 2026-09-29T061648242153 | 2 changed, 5 added | quiet |
| 2026-09-29 | `remote/com.straelo/relay` | 2026-09-28T142113751402 -> 2026-09-29T061647472946 | 1 changed, 1 added | quiet |
| 2026-09-29 | `remote/com.qumge/skills` | 2026-09-28T170334632536 -> 2026-09-29T061646811045 | 3 changed | quiet |
| 2026-09-29 | `remote/fyi.reviewtimes/review-times` | 2026-09-28T142457076810 -> 2026-09-29T061644407998 | 1 changed, 1 removed | quiet |
| 2026-09-29 | `remote/com.remoshift/jobs` | 2026-09-29T003606598740 -> 2026-09-29T061643740505 | 1 changed | quiet |
| 2026-09-29 | `remote/com.radar-cnpj/radar-cnpj` | 2026-09-28T073045791197 -> 2026-09-29T061644233713 | 4 added | quiet |
| 2026-09-29 | `remote/io.github.moralito311-andr/andreax` | 2026-09-29T003606355313 -> 2026-09-29T061643399040 | 1 changed, 8 added | review |
| 2026-09-29 | `remote/com.youspot/youspot` | 2026-09-28T142417167778 -> 2026-09-29T061642095763 | 3 changed | quiet |
| 2026-09-29 | `remote/io.github.Lazige/modelcostcomparison` | 2026-09-28T142014155284 -> 2026-09-29T061641054831 | 6 changed (every tool) | quiet |
| 2026-09-29 | `remote/io.github.SidneyBissoli/medical-terminologies-mcp` | 2026-09-28T073047767765 -> 2026-09-29T061639157183 | 4 changed | quiet |
| 2026-09-29 | `remote/com.anthonyhunts/shaart-agency` | 2026-09-28T142334071474 -> 2026-09-29T061636672445 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.mlolahq/mlola-ui` | 2026-09-28T142309291691 -> 2026-09-29T061638951385 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.lonniev/tollbooth-authority-newengland` | 2026-09-29T003613073603 -> 2026-09-29T061634128686 | 1 added | quiet |
| 2026-09-29 | `remote/io.github.FTHTrading/genesis402-mcp` | 2026-09-28T142304980891 -> 2026-09-29T061634442590 | 14 changed (every tool) | quiet |
| 2026-09-29 | `remote/ai.switchapp/switch` | 2026-09-27T055058361429 -> 2026-09-29T061633442025 | 2 changed | quiet |
| 2026-09-29 | `remote/ai.senaro/personal-finance` | 2026-09-27T195350302509 -> 2026-09-29T061632018596 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.magichourhq/magic-hour` | 2026-09-27T065744797832 -> 2026-09-29T061630249601 | 29 changed | quiet |
| 2026-09-29 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-09-27T195345294427 -> 2026-09-29T061629105535 | 2 added | quiet |
| 2026-09-29 | `remote/io.github.baronsigma/factrail` | 2026-09-29T003553365445 -> 2026-09-29T061629719034 | 7 changed (every tool) | quiet |
| 2026-09-29 | `remote/io.github.89rat/code402` | 2026-09-28T142138817006 -> 2026-09-29T061625874365 | 1 added | quiet |
| 2026-09-29 | `remote/com.pontofato/pontofato` | 2026-09-28T073018465869 -> 2026-09-29T061625324944 | 4 added | quiet |
| 2026-09-29 | `remote/com.plainrouter/mcp` | 2026-09-29T003601728336 -> 2026-09-29T061625139609 | 2 added, 2 removed | quiet |
| 2026-09-29 | `remote/io.github.Its-fortunatefolly/hubvibe` | 2026-09-29T003544822524 -> 2026-09-29T061621665450 | 1 changed | quiet |
| 2026-09-29 | `remote/com.gangwaze/cruise` | 2026-09-28T141556469317 -> 2026-09-29T061621573581 | 13 changed (every tool) | quiet |
| 2026-09-29 | `remote/io.github.raphaelbgr/rugshield` | 2026-09-29T003543875607 -> 2026-09-29T061620190736 | 3 changed | quiet |
| 2026-09-29 | `remote/com.editalmd/editalmd` | 2026-09-27T232545698058 -> 2026-09-29T061617623094 | 4 added | quiet |
| 2026-09-29 | `remote/io.github.Kopaev/openvan-travel` | 2026-09-28T170344166445 -> 2026-09-29T061616013551 | 2 added | quiet |
| 2026-09-29 | `remote/com.carathunter/diamond-prices` | 2026-09-28T141432334975 -> 2026-09-29T061617409658 | 2 changed | quiet |
| 2026-09-29 | `remote/io.github.JunHwan-Kwon/deepbom` | 2026-09-28T072548070484 -> 2026-09-29T061613436328 | 1 changed | quiet |
| 2026-09-29 | `remote/com.dayze/life-context.1` | 2026-09-29T003536537927 -> 2026-09-29T061614003235 | 3 changed, 4 added | quiet |
| 2026-09-29 | `remote/com.dayze/life-context` | 2026-09-29T003536379671 -> 2026-09-29T061613916767 | 3 changed, 4 added | quiet |
| 2026-09-29 | `remote/cloud.dchub/mcp-server` | 2026-09-29T003537098558 -> 2026-09-29T061615077258 | 13 changed | quiet |
| 2026-09-29 | `remote/io.github.lonniev/cypher-mcp` | 2026-09-27T195328318411 -> 2026-09-29T061613527765 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.CoinRithm/mcp-trading` | 2026-09-28T141830328699 -> 2026-09-29T061612159903 | 1 changed | quiet |
| 2026-09-29 | `remote/com.astranl/mcp` | 2026-09-29T003535508806 -> 2026-09-29T061612126596 | 6 changed | quiet |
| 2026-09-29 | `remote/io.github.whiteknightonhorse/apibase` | 2026-09-28T141314654113 -> 2026-09-29T061610043718 | 4 removed | quiet |
| 2026-09-29 | `remote/com.agenttrafficlab/atl` | 2026-09-28T170335222235 -> 2026-09-29T061610660681 | 2 changed | quiet |
| 2026-09-29 | `remote/com.trustverum/public-reading` | 2026-09-28T055506725225 -> 2026-09-29T061609516466 | 1 changed | quiet |
| 2026-09-29 | `remote/kr.xdata/xdata-mcp` | 2026-09-28T141353158417 -> 2026-09-29T061609822421 | 2 added | quiet |
| 2026-09-29 | `remote/io.github.gosadu/loophole-tape` | 2026-09-28T103344168214 -> 2026-09-29T061609015052 | 2 changed | quiet |
| 2026-09-29 | `remote/com.gisfinder/directory` | 2026-09-28T140938286934 -> 2026-09-29T061608297958 | 1 added | quiet |
| 2026-09-29 | `remote/io.tokenbooks/tokenbooks` | 2026-09-29T003542653104 -> 2026-09-29T061609373182 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.89rat/openfang-rail` | 2026-09-27T152746283139 -> 2026-09-29T061606224368 | 1 added | quiet |
| 2026-09-29 | `remote/xyz.558686.gpt55/token-gateway` | 2026-09-28T170330995723 -> 2026-09-29T061612602930 | 3 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 9566 substantive, 3144 that changed only numbers (a catalogue counter ticking, a date), 145 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 7017 | 4042 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `caseyjhand.com` | 56 | 56 | 0 | 0 |
| `daedalmap.com` | 47 | 47 | 0 | 0 |
| `sistaminuten.se` | 37 | 2 | 0 | 35 |
| `afbudsrejser.dk` | 36 | 2 | 0 | 34 |
| `akkilahdot.fi` | 36 | 2 | 0 | 34 |
| `restplass.no` | 36 | 2 | 0 | 34 |
| `socialloop.ai` | 36 | 36 | 0 | 0 |
| `fastmcp.app` | 29 | 29 | 0 | 0 |
| `dayze.com` | 28 | 28 | 0 | 0 |
| 1167 other operators | 2732 | 2555 | 169 | 8 |
