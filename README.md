# MCP server tool changes

Last change observed 2026-09-29T08:31:19+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

13056 changes to a tool definition: 380 npm releases (134 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 12676 readings of hosted servers that found their tools changed; 67 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-09-29 | `remote/fi.akkilahdot/travel-search` | 2026-09-29T080505381454 -> 2026-09-29T083120282707 | 1 changed | quiet |
| 2026-09-29 | `remote/no.restplass/travel-search` | 2026-09-29T080035144972 -> 2026-09-29T083035637477 | 1 changed | quiet |
| 2026-09-29 | `remote/se.sistaminuten/travel-search` | 2026-09-29T080038352564 -> 2026-09-29T083025377391 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-29T080347917861 -> 2026-09-29T083023012540 | 1 changed | quiet |
| 2026-09-29 | `remote/dk.afbudsrejser/travel-search` | 2026-09-29T080012568469 -> 2026-09-29T083015874935 | 1 changed | quiet |
| 2026-09-29 | `remote/com.talval/research` | 2026-09-23T160804958553 -> 2026-09-29T082958904772 | 7 changed (every tool) | quiet |
| 2026-09-29 | `remote/xyz.signomy/civitae` | 2026-09-23T163005044903 -> 2026-09-29T082920984536 | 1 added | quiet |
| 2026-09-29 | `remote/es.cesaryague/paki-curator` | 2026-09-28T170332335787 -> 2026-09-29T082825602947 | 1 changed | quiet |
| 2026-09-29 | `remote/io.orbitwan/orbitwan` | 2026-09-29T003606684889 -> 2026-09-29T082711376497 | 2 added | quiet |
| 2026-09-29 | `remote/com.movingplace/mcp` | 2026-09-29T075454176794 -> 2026-09-29T082654798181 | 16 added | quiet |
| 2026-09-29 | `remote/io.github.Ahmet11159/x402-agent-services` | 2026-09-29T003552835594 -> 2026-09-29T082559978593 | 4 changed | quiet |
| 2026-09-29 | `remote/com.airsidelabs/aviation-tools` | 2026-09-23T160513903576 -> 2026-09-29T082553522807 | 2 added | quiet |
| 2026-09-29 | `remote/io.github.tettertotter/fundinglandscape` | 2026-09-29T003541234274 -> 2026-09-29T082342730881 | 3 changed | quiet |
| 2026-09-29 | `remote/dev.ffpipe/ffpipe` | 2026-09-23T160506485518 -> 2026-09-29T082337226200 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.whiteknightonhorse/apibase` | 2026-09-29T061610043718 -> 2026-09-29T082245665677 | 2 added | quiet |
| 2026-09-29 | `remote/io.github.JSONbored/metagraphed` | 2026-09-28T103458277994 -> 2026-09-29T082209319092 | 1 changed, 2 added | quiet |
| 2026-09-29 | `remote/com.persuadioai/mcp` | 2026-09-28T055502479067 -> 2026-09-29T082159104235 | 2 changed | quiet |
| 2026-09-29 | `remote/com.marketintelligenceapi.api/market-intelligence` | 2026-09-29T072439303736 -> 2026-09-29T081943738402 | 2 added | review |
| 2026-09-29 | `remote/fi.akkilahdot/travel-search` | 2026-09-29T073844227482 -> 2026-09-29T080505381454 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-29T073730865212 -> 2026-09-29T080347917861 | 1 changed | quiet |
| 2026-09-29 | `remote/com.innergcomplete/shearquery` | 2026-09-29T073720278902 -> 2026-09-29T080337438991 | 1 added | quiet |
| 2026-09-29 | `gdharness` | 1.1.21 -> 1.1.22 | 13 changed | quiet |
| 2026-09-29 | `remote/com.remoshift/jobs` | 2026-09-29T073642554402 -> 2026-09-29T080301513408 | 1 changed | quiet |
| 2026-09-29 | `remote/se.sistaminuten/travel-search` | 2026-09-29T073413649024 -> 2026-09-29T080038352564 | 1 changed | quiet |
| 2026-09-29 | `remote/no.restplass/travel-search` | 2026-09-29T073511272172 -> 2026-09-29T080035144972 | 1 changed | quiet |
| 2026-09-29 | `remote/com.kenwea.www/marketplace` | 2026-09-29T073344386662 -> 2026-09-29T080022464251 | 12 changed | quiet |
| 2026-09-29 | `remote/dk.afbudsrejser/travel-search` | 2026-09-29T073450566394 -> 2026-09-29T080012568469 | 1 changed | quiet |
| 2026-09-29 | `remote/com.ribqa/sentinel-aleph` | 2026-09-29T073042733834 -> 2026-09-29T075705509421 | 1 changed | quiet |
| 2026-09-29 | `remote/com.movingplace/mcp` | 2026-09-29T072831121954 -> 2026-09-29T075454176794 | 16 removed | quiet |
| 2026-09-29 | `remote/com.coverbureau/mcp` | 2026-09-23T162350901401 -> 2026-09-29T075422771938 | 3 changed (every tool) | quiet |
| 2026-09-29 | `remote/co.huggingface/hf-mcp-server.1` | 2026-09-23T160442010297 -> 2026-09-29T075319682696 | 1 changed | quiet |
| 2026-09-29 | `remote/ai.clearvoyance/clearvoyance` | 2026-09-28T141439900572 -> 2026-09-29T075228823771 | 4 changed | quiet |
| 2026-09-29 | `remote/com.difficat/difficat` | 2026-09-28T141329692027 -> 2026-09-29T075208868767 | 3 changed, 1 added | quiet |
| 2026-09-29 | `remote/help.awning/awning` | 2026-09-25T115914204456 -> 2026-09-29T075051900638 | 16 changed, 2 added | quiet |
| 2026-09-29 | `remote/io.github.faisal-maverick/aayat-ai` | 2026-09-29T061601398882 -> 2026-09-29T074843438595 | 2 changed | quiet |
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

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 9748 substantive, 3151 that changed only numbers (a catalogue counter ticking, a date), 157 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 7023 | 4048 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `caseyjhand.com` | 56 | 56 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| `sistaminuten.se` | 40 | 2 | 0 | 38 |
| `afbudsrejser.dk` | 39 | 2 | 0 | 37 |
| `akkilahdot.fi` | 39 | 2 | 0 | 37 |
| `restplass.no` | 39 | 2 | 0 | 37 |
| `socialloop.ai` | 39 | 39 | 0 | 0 |
| `fastmcp.app` | 29 | 29 | 0 | 0 |
| `dayze.com` | 28 | 28 | 0 | 0 |
| 1256 other operators | 2908 | 2724 | 176 | 8 |
