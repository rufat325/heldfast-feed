# MCP server tool changes

Last change observed 2026-09-27T19:54:03+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9409 npm servers from the official MCP registry (154 daily, the rest weekly) and 18576 hosted endpoints (daily).

12097 changes to a tool definition: 347 npm releases (101 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 11750 readings of hosted servers that found their tools changed; 26 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-09-27 | `remote/com.zoningsignal/observatory` | 2026-09-27T070127155902 -> 2026-09-27T195404718171 | 1 changed | quiet |
| 2026-09-27 | `remote/fi.akkilahdot/travel-search` | 2026-09-27T155123960184 -> 2026-09-27T195402865585 | 1 changed | quiet |
| 2026-09-27 | `remote/com.goedvps.app.wodan-posture/wodan-posture` | 2026-09-27T105412091435 -> 2026-09-27T195403419327 | 1 added | review |
| 2026-09-27 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-27T155043414774 -> 2026-09-27T195359085702 | 1 changed | quiet |
| 2026-09-27 | `remote/com.odilelabs/odile` | 2026-09-27T154947354776 -> 2026-09-27T195355025846 | 3 changed | quiet |
| 2026-09-27 | `remote/world.agentindex/x402` | 2026-09-27T153031760329 -> 2026-09-27T195353381201 | 1 changed, 4 added | quiet |
| 2026-09-27 | `remote/se.sistaminuten/travel-search` | 2026-09-27T155222481617 -> 2026-09-27T195351922521 | 1 changed | quiet |
| 2026-09-27 | `remote/no.restplass/travel-search` | 2026-09-27T160723519625 -> 2026-09-27T195351406901 | 1 changed | quiet |
| 2026-09-27 | `remote/com.youspot/youspot` | 2026-09-26T045553472632 -> 2026-09-27T195351536372 | 1 removed | quiet |
| 2026-09-27 | `remote/dk.afbudsrejser/travel-search` | 2026-09-27T160707306377 -> 2026-09-27T195350439664 | 1 changed | quiet |
| 2026-09-27 | `remote/ai.senaro/personal-finance` | 2026-09-25T120357432569 -> 2026-09-27T195350302509 | 3 changed | quiet |
| 2026-09-27 | `remote/nl.marketingburos/marketingburos` | 2026-09-26T114042211720 -> 2026-09-27T195348624285 | 1 added | quiet |
| 2026-09-27 | `remote/io.github.taux-io/twse-mcp` | 2026-09-27T105258285288 -> 2026-09-27T195348907158 | 9 changed (every tool) | quiet |
| 2026-09-27 | `remote/io.github.SKalinin909/tradingcalc` | 2026-09-26T114318913930 -> 2026-09-27T195353900064 | 1 added | review |
| 2026-09-27 | `remote/cc.thecolony/mcp-server` | 2026-09-26T231109481699 -> 2026-09-27T195348518701 | 13 changed | quiet |
| 2026-09-27 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-09-27T160624623741 -> 2026-09-27T195346906452 | 15 changed | review |
| 2026-09-27 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-09-27T103811255312 -> 2026-09-27T195345294427 | 1 changed, 3 added | quiet |
| 2026-09-27 | `remote/io.github.moralito311-andr/andreax` | 2026-09-27T152810273387 -> 2026-09-27T195344677442 | 2 changed, 1 added | review |
| 2026-09-27 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt` | 2026-09-27T055047567820 -> 2026-09-27T195340767788 | 3 changed, 1 added | quiet |
| 2026-09-27 | `remote/dev.mcphost/mcphost` | 2026-09-27T153107221351 -> 2026-09-27T195341383835 | 1 changed, 2 added | quiet |
| 2026-09-27 | `remote/com.editalmd/editalmd` | 2026-09-27T154514319100 -> 2026-09-27T195341262600 | 59 changed (every tool) | quiet |
| 2026-09-27 | `remote/io.orbitwan/orbitwan` | 2026-09-26T231048708707 -> 2026-09-27T195340314486 | 1 changed, 1 added | quiet |
| 2026-09-27 | `remote/com.tkawen/intelligence-gateway` | 2026-09-27T155244656981 -> 2026-09-27T195340426550 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.medprice-ai/mcp-medprice-ai` | 2026-09-27T065708126587 -> 2026-09-27T195338730562 | 1 changed | quiet |
| 2026-09-27 | `remote/so.darwin/darwin` | 2026-09-25T120339036056 -> 2026-09-27T195338042862 | 1 changed, 1 added | quiet |
| 2026-09-27 | `remote/ch.blust/mental-model` | 2026-09-27T110740919168 -> 2026-09-27T195338449755 | 1 changed | quiet |
| 2026-09-27 | `remote/dev.workers.mars-economic.mars-economic-agent-gateway/mars-economic` | 2026-09-27T105013835883 -> 2026-09-27T195339008109 | 1 changed | quiet |
| 2026-09-27 | `remote/com.googleapis.compute/mcp` | 2026-09-27T152155031217 -> 2026-09-27T195338479302 | 10 changed | quiet |
| 2026-09-27 | `remote/io.github.LayUp-Sport/sports-booking` | 2026-09-26T113952413068 -> 2026-09-27T195336916312 | 1 changed, 1 added | quiet |
| 2026-09-27 | `remote/com.mart402/extract` | 2026-09-27T065607533189 -> 2026-09-27T195334732955 | 1 changed | quiet |
| 2026-09-27 | `remote/com.jojapi/product-barcode-api` | 2026-09-26T231100918722 -> 2026-09-27T195336551915 | 1 changed | quiet |
| 2026-09-27 | `remote/br.app.classificado/meta-agent-tools` | 2026-09-26T192534406571 -> 2026-09-27T195341401286 | 31 changed (every tool) | quiet |
| 2026-09-27 | `remote/net.isitdns/isitdns` | 2026-09-27T134814565652 -> 2026-09-27T195334218995 | 5 changed | quiet |
| 2026-09-27 | `remote/fr.humanmirror/x402` | 2026-09-27T104939185500 -> 2026-09-27T195334137966 | 2 added | quiet |
| 2026-09-27 | `remote/io.github.Its-fortunatefolly/hubvibe` | 2026-09-27T104938926577 -> 2026-09-27T195333991933 | 36 changed, 5 added | quiet |
| 2026-09-27 | `remote/io.companygraph/mental-model` | 2026-09-27T110746651162 -> 2026-09-27T195334670003 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.tettertotter/fundinglandscape` | 2026-09-27T141919337358 -> 2026-09-27T195332402018 | 1 changed | quiet |
| 2026-09-27 | `remote/com.getyoutubetranscript/youtube-transcript-and-youtube-search` | 2026-09-27T065742461339 -> 2026-09-27T195333776759 | 1 added | quiet |
| 2026-09-27 | `remote/com.agenttrafficlab/atl` | 2026-09-27T103411373079 -> 2026-09-27T195332732254 | 1 added | quiet |
| 2026-09-27 | `remote/io.github.jbiggs77/bizinsured` | 2026-09-26T044750469748 -> 2026-09-27T195332408499 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.afredenslund/fredenslund-workshop-tools` | 2026-09-27T103224066550 -> 2026-09-27T195329218247 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.pscale-commons/bsp-mcp` | 2026-09-26T044737340249 -> 2026-09-27T195328467128 | 1 changed | quiet |
| 2026-09-27 | `remote/com.brainonbnb/bobai` | 2026-09-27T065321384058 -> 2026-09-27T195328157231 | 2 changed | review |
| 2026-09-27 | `remote/io.github.lonniev/cypher-mcp` | 2026-09-27T154517347570 -> 2026-09-27T195328318411 | 54 added | quiet |
| 2026-09-27 | `remote/com.commsharbor/commsharbor` | 2026-09-26T044752759101 -> 2026-09-27T195328875099 | 139 changed (every tool) | quiet |
| 2026-09-27 | `remote/online.x-402/mcp` | 2026-09-27T112406386959 -> 2026-09-27T195325885621 | 2 added | review |
| 2026-09-27 | `remote/io.github.whiteknightonhorse/apibase` | 2026-09-27T103158007599 -> 2026-09-27T195326470708 | 4 added | quiet |
| 2026-09-27 | `remote/com.phasefolio/phasefolio` | 2026-09-27T132323960645 -> 2026-09-27T195326245602 | 1 changed | quiet |
| 2026-09-27 | `remote/eu.sirenic/sirenic` | 2026-09-27T103114549386 -> 2026-09-27T195326566424 | 11 changed | quiet |
| 2026-09-27 | `remote/com.stevesignals.api/steve-guard` | 2026-09-27T055144008838 -> 2026-09-27T195325410374 | 1 changed | quiet |
| 2026-09-27 | `remote/app.flaim/mcp` | 2026-09-27T055035183419 -> 2026-09-27T195323681056 | 1 changed | quiet |
| 2026-09-27 | `remote/directory.nohumans/registry` | 2026-09-27T055004370005 -> 2026-09-27T195323069940 | 1 changed | quiet |
| 2026-09-27 | `remote/news.prh/revenue-agent` | 2026-09-27T065127829100 -> 2026-09-27T195322534161 | 1 added | review |
| 2026-09-27 | `remote/io.github.onetapstudiogames/1f3d9` | 2026-09-27T110038637995 -> 2026-09-27T195321343620 | 2 changed | quiet |
| 2026-09-27 | `remote/io.github.47620-xyz/solana-data` | 2026-09-27T151759578646 -> 2026-09-27T195322281890 | 7 changed, 5 added | review |
| 2026-09-27 | `remote/com.ashareapi/ashare-data-api` | 2026-09-26T113452327133 -> 2026-09-27T195323154572 | 1 changed | quiet |
| 2026-09-27 | `remote/com.agents-agents-agents/parley` | 2026-09-27T065133731307 -> 2026-09-27T195321411878 | 1 changed, 1 added | quiet |
| 2026-09-27 | `remote/app.agentbit/mcp` | 2026-09-27T154216956879 -> 2026-09-27T195322843263 | 3 added | quiet |
| 2026-09-27 | `remote/io.agentlot/marketplace` | 2026-09-26T231032104013 -> 2026-09-27T195319815889 | 7 added | quiet |
| 2026-09-27 | `remote/com.agentalog/meta-agent-tools` | 2026-09-26T192526746998 -> 2026-09-27T195320348185 | 31 changed (every tool) | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 8887 substantive, 3100 that changed only numbers (a catalogue counter ticking, a date), 110 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 7017 | 4042 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `caseyjhand.com` | 55 | 55 | 0 | 0 |
| `daedalmap.com` | 47 | 47 | 0 | 0 |
| `sistaminuten.se` | 29 | 2 | 0 | 27 |
| `afbudsrejser.dk` | 28 | 2 | 0 | 26 |
| `akkilahdot.fi` | 28 | 2 | 0 | 26 |
| `restplass.no` | 28 | 2 | 0 | 26 |
| `socialloop.ai` | 28 | 28 | 0 | 0 |
| `assetfare.dev` | 20 | 20 | 0 | 0 |
| `dayze.com` | 20 | 20 | 0 | 0 |
| 954 other operators | 2032 | 1902 | 125 | 5 |
