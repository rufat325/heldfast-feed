# MCP server tool changes

Last change observed 2026-09-30T21:03:06+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

13717 changes to a tool definition: 384 npm releases (138 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 13333 readings of hosted servers that found their tools changed; 101 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-09-30 | `remote/xn--3ds443g.xn--s7y/duan-online` | 2026-09-28T142344905096 -> 2026-09-30T210307530159 | 1 changed | quiet |
| 2026-09-30 | `remote/se.sistaminuten/travel-search` | 2026-09-30T152247624236 -> 2026-09-30T210307431548 | 1 changed | quiet |
| 2026-09-30 | `remote/world.agentindex/x402` | 2026-09-30T152329465841 -> 2026-09-30T210301776609 | 2 changed, 2 removed | quiet |
| 2026-09-30 | `remote/io.github.brawlaphant/vealth` | 2026-09-28T073141103227 -> 2026-09-30T210300382823 | 2 added | quiet |
| 2026-09-30 | `remote/no.restplass/travel-search` | 2026-09-30T152325323884 -> 2026-09-30T210258971180 | 1 changed | quiet |
| 2026-09-30 | `remote/com.primecutsnursery/public-data` | 2026-09-29T073509820506 -> 2026-09-30T210257788857 | 1 changed | quiet |
| 2026-09-30 | `remote/io.github.worklore/worklore` | 2026-09-28T073202168699 -> 2026-09-30T210256364576 | 1 added | quiet |
| 2026-09-30 | `remote/fi.akkilahdot/travel-search` | 2026-09-30T152247316597 -> 2026-09-30T210256388300 | 1 changed | quiet |
| 2026-09-30 | `remote/dk.afbudsrejser/travel-search` | 2026-09-30T152320358308 -> 2026-09-30T210255803670 | 1 changed | quiet |
| 2026-09-30 | `remote/com.goedvps.app.wodan-posture/wodan-posture` | 2026-09-30T152247175576 -> 2026-09-30T210256533209 | 1 changed, 1 added | quiet |
| 2026-09-30 | `remote/org.windowsticker/window-sticker` | 2026-09-28T142254774955 -> 2026-09-30T210256222563 | 1 changed | quiet |
| 2026-09-30 | `remote/com.suomiatlas/area-statistics` | 2026-09-28T170411998613 -> 2026-09-30T210256365320 | 7 changed | quiet |
| 2026-09-30 | `remote/ai.wem3/wem-price-compare` | 2026-09-29T003623577973 -> 2026-09-30T210255833820 | 6 changed | quiet |
| 2026-09-30 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-09-30T152235299876 -> 2026-09-30T210254082425 | 3 added | review |
| 2026-09-30 | `remote/io.github.cnghockey/sats4ai` | 2026-09-30T060140115973 -> 2026-09-30T210253139953 | 1 changed | quiet |
| 2026-09-30 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-09-30T152304883094 -> 2026-09-30T210251193118 | 15 changed | review |
| 2026-09-30 | `remote/com.tablejourney/food-travel` | 2026-09-28T142541866419 -> 2026-09-30T210251087749 | 5 changed | quiet |
| 2026-09-30 | `remote/pl.swiadectwo-energetyczne24/zamowienia` | 2026-09-28T073128466376 -> 2026-09-30T210250772190 | 2 changed | quiet |
| 2026-09-30 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-30T152238575094 -> 2026-09-30T210249859658 | 3 changed | quiet |
| 2026-09-30 | `remote/io.github.Perufitlife/postwire-mcp` | 2026-09-29T210458675426 -> 2026-09-30T210249204235 | 7 changed | quiet |
| 2026-09-30 | `remote/page.ship/ship-page` | 2026-09-29T150801655910 -> 2026-09-30T210248928299 | 1 changed | quiet |
| 2026-09-30 | `remote/com.innergcomplete/shearquery` | 2026-09-30T152242146835 -> 2026-09-30T210248083995 | 5 added | quiet |
| 2026-09-30 | `remote/com.pontofato/pontofato` | 2026-09-30T152229091691 -> 2026-09-30T210248965884 | 1 changed | quiet |
| 2026-09-30 | `remote/com.plainrouter/mcp` | 2026-09-30T060135733718 -> 2026-09-30T210248484672 | 1 changed | quiet |
| 2026-09-30 | `remote/cz.rychlahypo/mortgages` | 2026-09-28T142503043926 -> 2026-09-30T210246789321 | 3 changed | quiet |
| 2026-09-30 | `remote/com.saylorinnovations/data` | 2026-09-30T152235985339 -> 2026-09-30T210246236564 | 4 changed, 12 removed | quiet |
| 2026-09-30 | `remote/com.remoshift/jobs` | 2026-09-30T152233203230 -> 2026-09-30T210245345218 | 1 changed | quiet |
| 2026-09-30 | `remote/com.radar-cnpj/radar-cnpj` | 2026-09-30T152232866669 -> 2026-09-30T210245815211 | 3 changed | quiet |
| 2026-09-30 | `remote/io.github.Project-Gifted1/pg1-threat-intel` | 2026-09-29T101121400254 -> 2026-09-30T210244254736 | 1 added | quiet |
| 2026-09-30 | `remote/dev.mcphost/mcphost` | 2026-09-30T152220960390 -> 2026-09-30T210245124672 | 135 changed | quiet |
| 2026-09-30 | `remote/com.vertodigital/mcp` | 2026-09-29T210449373421 -> 2026-09-30T210241678634 | 6 changed (every tool) | quiet |
| 2026-09-30 | `remote/com.meettempi/tempi` | 2026-09-30T060112989068 -> 2026-09-30T210242972512 | 8 changed (every tool) | quiet |
| 2026-09-30 | `remote/click.ciromaciel/tools` | 2026-09-29T003554325511 -> 2026-09-30T210241274122 | 1 changed | quiet |
| 2026-09-30 | `remote/com.multicinesortega/cartelera` | 2026-09-30T060115415504 -> 2026-09-30T210240964747 | 1 changed | quiet |
| 2026-09-30 | `remote/io.github.yzlee/opcmenu` | 2026-09-30T060127338935 -> 2026-09-30T210241730959 | 2 changed | quiet |
| 2026-09-30 | `remote/io.github.proplineapi/propline-mcp` | 2026-09-29T210442683463 -> 2026-09-30T210238464151 | 2 changed | quiet |
| 2026-09-30 | `remote/team.leanscale/gtm-knowledge` | 2026-09-29T073349435849 -> 2026-09-30T210235923289 | 1 changed | quiet |
| 2026-09-30 | `remote/pro.particle/particle-pro` | 2026-09-29T210446054211 -> 2026-09-30T210236522509 | 1 changed | quiet |
| 2026-09-30 | `remote/com.bluepillow/hotels` | 2026-09-29T113119146800 -> 2026-09-30T210236837896 | 2 changed | quiet |
| 2026-09-30 | `remote/com.metricduck/financial-analysis` | 2026-09-29T210444458434 -> 2026-09-30T210235482488 | 2 changed | quiet |
| 2026-09-30 | `remote/io.insourcia/insourcia` | 2026-09-30T152212962736 -> 2026-09-30T210235792798 | 2 changed | quiet |
| 2026-09-30 | `remote/org.golfcore/golfcore` | 2026-09-30T060102122457 -> 2026-09-30T210233511688 | 2 changed | quiet |
| 2026-09-30 | `remote/io.github.Ahmet11159/x402-agent-services` | 2026-09-29T082559978593 -> 2026-09-30T210232476450 | 1 changed | quiet |
| 2026-09-30 | `remote/pro.aicut/aicut` | 2026-09-30T152213253084 -> 2026-09-30T210231097079 | 45 changed | quiet |
| 2026-09-30 | `remote/gr.bestprice/mcp` | 2026-09-30T152211130655 -> 2026-09-30T210233728961 | 4 changed (every tool) | quiet |
| 2026-09-30 | `remote/com.howtomakemoneyonsnapchat/creator-monetization` | 2026-09-30T152202046394 -> 2026-09-30T210231895461 | 1 changed | quiet |
| 2026-09-30 | `remote/app.apiguru/amazon-data` | 2026-09-30T152209489636 -> 2026-09-30T210231474629 | 10 changed | quiet |
| 2026-09-30 | `remote/app.luckdrop/luckdrop` | 2026-09-29T073210368862 -> 2026-09-30T210231091953 | 1 changed | quiet |
| 2026-09-30 | `remote/io.github.si-imtiaz/leadquasar` | 2026-09-30T152210885332 -> 2026-09-30T210229557330 | 2 changed | quiet |
| 2026-09-30 | `remote/fun.lesgooo/lesgooo` | 2026-09-28T142120401611 -> 2026-09-30T210229546350 | 2 changed, 6 added | quiet |
| 2026-09-30 | `remote/io.github.AAAZZZR/livermore` | 2026-09-30T152209048314 -> 2026-09-30T210230936354 | 1 changed | quiet |
| 2026-09-30 | `remote/com.dtmframe/dtmframe` | 2026-09-30T152157514249 -> 2026-09-30T210228440330 | 5 changed (every tool) | quiet |
| 2026-09-30 | `remote/io.github.leanrads/leanriq` | 2026-09-30T152208555966 -> 2026-09-30T210228507497 | 6 changed | quiet |
| 2026-09-30 | `remote/io.github.tradewr333-lgtm/degenscan-intel` | 2026-09-30T152215842353 -> 2026-09-30T210225184317 | 23 changed, 1 added (every tool) | quiet |
| 2026-09-30 | `remote/io.github.raphaelbgr/rugshield` | 2026-09-29T061620190736 -> 2026-09-30T210225162740 | 5 changed (every tool) | quiet |
| 2026-09-30 | `remote/io.github.DigbyO/colour-memory` | 2026-09-29T003536780303 -> 2026-09-30T210225601778 | 1 changed | quiet |
| 2026-09-30 | `remote/io.github.tettertotter/fundinglandscape` | 2026-09-30T152201501669 -> 2026-09-30T210224680135 | 3 changed | quiet |
| 2026-09-30 | `remote/org.electionindex/elections` | 2026-09-30T152159958401 -> 2026-09-30T210222941526 | 2 changed | quiet |
| 2026-09-30 | `remote/et.bina/binasmart` | 2026-09-30T152213545896 -> 2026-09-30T210225497363 | 1 changed | quiet |
| 2026-09-30 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt` | 2026-09-30T152201701906 -> 2026-09-30T210221029499 | 3 changed, 9 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 10335 substantive, 3186 that changed only numbers (a catalogue counter ticking, a date), 196 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 7023 | 4048 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `caseyjhand.com` | 56 | 56 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| `sistaminuten.se` | 49 | 2 | 0 | 47 |
| `afbudsrejser.dk` | 48 | 2 | 0 | 46 |
| `akkilahdot.fi` | 48 | 2 | 0 | 46 |
| `restplass.no` | 48 | 2 | 0 | 46 |
| `socialloop.ai` | 48 | 48 | 0 | 0 |
| `fastmcp.app` | 41 | 41 | 0 | 0 |
| `dayze.com` | 38 | 38 | 0 | 0 |
| 1351 other operators | 3502 | 3280 | 211 | 11 |
