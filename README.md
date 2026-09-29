# MCP server tool changes

Last change observed 2026-09-29T07:38:43+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

13021 changes to a tool definition: 379 npm releases (133 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 12642 readings of hosted servers that found their tools changed; 66 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-09-29 | `remote/fi.akkilahdot/travel-search` | 2026-09-29T061655461447 -> 2026-09-29T073844227482 | 1 changed | quiet |
| 2026-09-29 | `remote/com.anahana/content-mcp` | 2026-09-23T162935954278 -> 2026-09-29T073845920929 | 2 added | quiet |
| 2026-09-29 | `remote/io.github.huruki-geo/voxeldraft` | 2026-09-23T162925807082 -> 2026-09-29T073829951700 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.trip2g/trip2g` | 2026-09-23T162917918814 -> 2026-09-29T073813966546 | 2 changed | quiet |
| 2026-09-29 | `remote/com.swarmmemo/bulletin` | 2026-09-26T114259914639 -> 2026-09-29T073748253870 | 11 changed, 9 added (every tool) | quiet |
| 2026-09-29 | `remote/insure.spot/insurance-research` | 2026-09-26T045515502220 -> 2026-09-29T073738829930 | 5 changed | quiet |
| 2026-09-29 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-29T061649371691 -> 2026-09-29T073730865212 | 1 changed | quiet |
| 2026-09-29 | `remote/com.innergcomplete/shearquery` | 2026-09-29T061648203636 -> 2026-09-29T073720278902 | 12 added | quiet |
| 2026-09-29 | `remote/com.remoshift/jobs` | 2026-09-29T061643740505 -> 2026-09-29T073642554402 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.reinlainer/postmd-mcp-server` | 2026-09-23T162822677417 -> 2026-09-29T073624020932 | 2 changed | quiet |
| 2026-09-29 | `remote/com.nessgate/nessgate` | 2026-09-23T162757031122 -> 2026-09-29T073543007919 | 2 added | quiet |
| 2026-09-29 | `remote/com.neblla/neblla` | 2026-09-28T170333588688 -> 2026-09-29T073541274767 | 2 changed, 25 added | quiet |
| 2026-09-29 | `remote/com.multicinesortega/cartelera` | 2026-09-28T142407355463 -> 2026-09-29T073538683683 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.aboul3ata/mudpie-public` | 2026-09-26T114142785146 -> 2026-09-29T073535383223 | 1 added | quiet |
| 2026-09-29 | `remote/com.rubrkit/rubrkit` | 2026-09-24T120443992216 -> 2026-09-29T073512164452 | 1 added, 1 removed | quiet |
| 2026-09-29 | `remote/no.restplass/travel-search` | 2026-09-29T061703818442 -> 2026-09-29T073511272172 | 1 changed | quiet |
| 2026-09-29 | `remote/com.primecutsnursery/public-data` | 2026-09-23T163140500409 -> 2026-09-29T073509820506 | 2 changed | quiet |
| 2026-09-29 | `remote/io.ocolo.www/project-requests` | 2026-09-28T142317172713 -> 2026-09-29T073507965985 | 1 changed | quiet |
| 2026-09-29 | `remote/de.drgsystem/medical-catalogs` | 2026-09-23T163131674253 -> 2026-09-29T073458569001 | 14 changed, 2 added | quiet |
| 2026-09-29 | `remote/dk.afbudsrejser/travel-search` | 2026-09-29T061702020477 -> 2026-09-29T073450566394 | 1 changed | quiet |
| 2026-09-29 | `remote/com.senzing/mcp` | 2026-09-24T202554790629 -> 2026-09-29T073449558602 | 1 changed | quiet |
| 2026-09-29 | `remote/com.sednasystem/genesis` | 2026-09-28T104042922791 -> 2026-09-29T073448599010 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.bytevirts/viewmax` | 2026-09-23T163103767630 -> 2026-09-29T073439676582 | 14 changed (every tool) | review |
| 2026-09-29 | `remote/fi.ophis/mcp` | 2026-09-23T162715628281 -> 2026-09-29T073430268940 | 4 changed | quiet |
| 2026-09-29 | `remote/net.qsig.x402/mcp` | 2026-09-23T161041011296 -> 2026-09-29T073422118461 | 1 changed, 2 added | quiet |
| 2026-09-29 | `remote/io.github.bnmbnmai/bnm-data-shop` | 2026-09-26T045422778578 -> 2026-09-29T073434747998 | 3 changed, 1 added | quiet |
| 2026-09-29 | `remote/se.sistaminuten/travel-search` | 2026-09-29T061705162924 -> 2026-09-29T073413649024 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-09-29T061655023363 -> 2026-09-29T073400857436 | 15 changed | review |
| 2026-09-29 | `remote/com.luxurylodgingpm.stay/luxury-lodging` | 2026-09-28T170339547749 -> 2026-09-29T073359154153 | 6 changed (every tool) | quiet |
| 2026-09-29 | `remote/com.spacexploration/listings` | 2026-09-23T163010794568 -> 2026-09-29T073354596950 | 1 changed | quiet |
| 2026-09-29 | `remote/team.leanscale/gtm-knowledge` | 2026-09-23T162701190355 -> 2026-09-29T073349435849 | 2 changed | quiet |
| 2026-09-29 | `remote/com.kernelcad/kernelcad` | 2026-09-25T120327990504 -> 2026-09-29T073344714878 | 23 changed | quiet |
| 2026-09-29 | `remote/com.kenwea.www/marketplace` | 2026-09-23T162700147757 -> 2026-09-29T073344386662 | 18 changed, 10 added, 12 removed (every tool) | quiet |
| 2026-09-29 | `remote/net.webhooktest/webhook-tester` | 2026-09-23T161012540009 -> 2026-09-29T073340946107 | 1 changed | quiet |
| 2026-09-29 | `remote/org.texs/tapercraft` | 2026-09-26T231053802458 -> 2026-09-29T073335260893 | 4 changed | quiet |
| 2026-09-29 | `remote/com.interzoid/mcp-server` | 2026-09-23T202223221145 -> 2026-09-29T073333991241 | 2 added | review |
| 2026-09-29 | `remote/club.goodleads/new-business-owner-contacts` | 2026-09-23T162647225802 -> 2026-09-29T073323833237 | 1 changed | quiet |
| 2026-09-29 | `remote/cl.tuki/travel-mcp` | 2026-09-23T160959348178 -> 2026-09-29T073321692321 | 1 added | quiet |
| 2026-09-29 | `remote/ai.forkmate/forkmate` | 2026-09-24T120205323327 -> 2026-09-29T073319503048 | 11 changed | quiet |
| 2026-09-29 | `remote/com.recipes-daily/recipes` | 2026-09-23T162937955834 -> 2026-09-29T073316527064 | 1 changed, 1 added | quiet |
| 2026-09-29 | `remote/games.moddable.tools/moddable-games-tools` | 2026-09-23T160954826866 -> 2026-09-29T073314905743 | 10 changed | quiet |
| 2026-09-29 | `remote/ua.com.quintadb/mcp` | 2026-09-24T202453399518 -> 2026-09-29T073313237232 | 1 changed | quiet |
| 2026-09-29 | `remote/com.eventescapes/event-escapes` | 2026-09-24T202512010305 -> 2026-09-29T073319995054 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.steffanricardo/the-dutch-directory` | 2026-09-23T160948908897 -> 2026-09-29T073306620345 | 2 changed | quiet |
| 2026-09-29 | `remote/io.stocksonchain/stocks-on-chain` | 2026-09-23T160943440010 -> 2026-09-29T073259715703 | 1 added | quiet |
| 2026-09-29 | `remote/com.donebear/donebear` | 2026-09-24T205520073354 -> 2026-09-29T073315413986 | 14 changed | quiet |
| 2026-09-29 | `remote/com.lazyweb/discovery` | 2026-09-26T114341113444 -> 2026-09-29T073251044877 | 1 added | quiet |
| 2026-09-29 | `remote/store.scvd/general-store` | 2026-09-24T202554116740 -> 2026-09-29T073244070737 | 1 changed | quiet |
| 2026-09-29 | `remote/com.orbylon/readiness` | 2026-09-24T120308698287 -> 2026-09-29T073242451869 | 1 removed | quiet |
| 2026-09-29 | `remote/io.github.LE-VAI/designesy-org` | 2026-09-23T160838721103 -> 2026-09-29T073239828146 | 17 changed (every tool) | quiet |
| 2026-09-29 | `remote/io.github.BUYMYAGENT-TECHNOLOGIES-INC/marketplace` | 2026-09-23T160836235817 -> 2026-09-29T073236985567 | 1 added | quiet |
| 2026-09-29 | `remote/io.github.ArneFfm/nowyourlink` | 2026-09-23T162858528262 -> 2026-09-29T073234687476 | 5 changed (every tool) | quiet |
| 2026-09-29 | `remote/io.github.joelp22-maker/referencesource` | 2026-09-23T160914183466 -> 2026-09-29T073225033021 | 1 changed | quiet |
| 2026-09-29 | `remote/ru.quintadb/mcp` | 2026-09-24T202540239255 -> 2026-09-29T073222240885 | 1 changed | quiet |
| 2026-09-29 | `remote/ca.maplev/tesla-collision-parts` | 2026-09-23T160909333248 -> 2026-09-29T073220512048 | 4 changed (every tool) | quiet |
| 2026-09-29 | `remote/com.predictionmarketspicks/quant` | 2026-09-26T132431533007 -> 2026-09-29T073212338760 | 1 added | quiet |
| 2026-09-29 | `remote/io.github.Fizzl13/plaintext-wallet-checker` | 2026-09-23T160939427588 -> 2026-09-29T073208573042 | 1 added | quiet |
| 2026-09-29 | `remote/app.luckdrop/luckdrop` | 2026-09-23T162557866432 -> 2026-09-29T073210368862 | 5 changed (every tool) | quiet |
| 2026-09-29 | `remote/com.trustycap/trustycap` | 2026-09-23T162823621292 -> 2026-09-29T073207038485 | 2 changed | quiet |
| 2026-09-29 | `remote/au.com.totalparks/mcp` | 2026-09-26T045213049563 -> 2026-09-29T073205439322 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 9722 substantive, 3150 that changed only numbers (a catalogue counter ticking, a date), 149 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 7023 | 4048 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `caseyjhand.com` | 56 | 56 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| `sistaminuten.se` | 38 | 2 | 0 | 36 |
| `afbudsrejser.dk` | 37 | 2 | 0 | 35 |
| `akkilahdot.fi` | 37 | 2 | 0 | 35 |
| `restplass.no` | 37 | 2 | 0 | 35 |
| `socialloop.ai` | 37 | 37 | 0 | 0 |
| `fastmcp.app` | 29 | 29 | 0 | 0 |
| `dayze.com` | 28 | 28 | 0 | 0 |
| 1248 other operators | 2883 | 2700 | 175 | 8 |
