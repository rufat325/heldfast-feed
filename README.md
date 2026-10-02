# MCP server tool changes

Last change observed 2026-10-02T06:16:35+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

16093 changes to a tool definition: 459 npm releases (213 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 15634 readings of hosted servers that found their tools changed; 141 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-10-02 | `remote/se.sistaminuten/travel-search` | 2026-10-01T212519354272 -> 2026-10-02T061636515684 | 1 changed | quiet |
| 2026-10-02 | `remote/com.youspot/youspot` | 2026-10-01T063535958502 -> 2026-10-02T061633542180 | 1 changed, 4 added | quiet |
| 2026-10-02 | `remote/io.github.tjcgraham-rgb/gaip-witness` | 2026-10-01T154247820184 -> 2026-10-02T061637849889 | 2 changed, 9 added | quiet |
| 2026-10-02 | `remote/io.github.tjcgraham-rgb/gaip-integration-protocol` | 2026-10-01T212519968898 -> 2026-10-02T061638295824 | 4 added | quiet |
| 2026-10-02 | `remote/io.github.tjcgraham-rgb/gaip-broker` | 2026-10-01T063536656185 -> 2026-10-02T061635512478 | 1 changed | quiet |
| 2026-10-02 | `remote/no.restplass/travel-search` | 2026-10-01T212527181875 -> 2026-10-02T061630369874 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.kor-jongwon/witan` | 2026-10-01T134606076932 -> 2026-10-02T061631706560 | 2 changed, 1 added | quiet |
| 2026-10-02 | `remote/io.github.Uuriko/project-room` | 2026-09-30T152325107925 -> 2026-10-02T061630393302 | 2 changed | quiet |
| 2026-10-02 | `remote/fi.akkilahdot/travel-search` | 2026-10-01T212504047572 -> 2026-10-02T061630947282 | 1 changed | quiet |
| 2026-10-02 | `remote/com.detextit.www/detextit` | 2026-10-01T212524830558 -> 2026-10-02T061629536204 | 1 changed | quiet |
| 2026-10-02 | `remote/dk.afbudsrejser/travel-search` | 2026-10-01T212524773882 -> 2026-10-02T061629511440 | 1 changed | quiet |
| 2026-10-02 | `remote/com.waitingforpower/energy-permitting-tracker` | 2026-10-01T134554141754 -> 2026-10-02T061629960460 | 2 changed | quiet |
| 2026-10-02 | `remote/ai.wem3/wem-price-compare` | 2026-10-01T212523557063 -> 2026-10-02T061629020762 | 1 changed | quiet |
| 2026-10-02 | `remote/ai.verticalmarketplace/vertical-marketplace` | 2026-10-01T134548045774 -> 2026-10-02T061629093941 | 3 changed, 4 added | quiet |
| 2026-10-02 | `remote/io.github.SKalinin909/tradingcalc` | 2026-10-01T212515524968 -> 2026-10-02T061628629348 | 1 added | quiet |
| 2026-10-02 | `remote/cc.thecolony/mcp-server` | 2026-09-30T152244033132 -> 2026-10-02T061629905741 | 2 changed | quiet |
| 2026-10-02 | `remote/ai.intuitek.the-stall/the-stall` | 2026-10-01T134301842308 -> 2026-10-02T061628411748 | 2 changed | quiet |
| 2026-10-02 | `remote/io.github.cryptoconspiracy/vurto-swap` | 2026-10-01T212509879515 -> 2026-10-02T061627121902 | 1 changed | quiet |
| 2026-10-02 | `remote/com.thefomite/fomite` | 2026-10-01T063531837946 -> 2026-10-02T061627572938 | 1 changed | quiet |
| 2026-10-02 | `remote/xyz.pflow.sim/whatif` | 2026-10-01T134230984280 -> 2026-10-02T061626593753 | 8 changed, 4 added | quiet |
| 2026-10-02 | `remote/xyz.trusteed/mcp-gateway` | 2026-09-30T152312112662 -> 2026-10-02T061627270174 | 4 changed | quiet |
| 2026-10-02 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-01T063532257358 -> 2026-10-02T061625284876 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-01T154238222280 -> 2026-10-02T061625513796 | 13 changed, 1 added | quiet |
| 2026-10-02 | `remote/io.github.cnghockey/sats4ai` | 2026-09-30T210253139953 -> 2026-10-02T061625681197 | 2 changed | quiet |
| 2026-10-02 | `remote/insure.spot/insurance-research` | 2026-09-30T060129125569 -> 2026-10-02T061630896245 | 2 changed | quiet |
| 2026-10-02 | `remote/com.swarmmemo/bulletin` | 2026-10-01T134514794832 -> 2026-10-02T061627148937 | 42 changed (every tool) | quiet |
| 2026-10-02 | `remote/com.innergcomplete/shearquery` | 2026-09-30T210248083995 -> 2026-10-02T061624603555 | 1 added | quiet |
| 2026-10-02 | `remote/ai.satohub/onchain-agents` | 2026-10-01T212506917483 -> 2026-10-02T061625005691 | 1 changed | quiet |
| 2026-10-02 | `remote/com.remoshift/jobs` | 2026-10-01T212456183253 -> 2026-10-02T061624074229 | 1 changed | quiet |
| 2026-10-02 | `remote/com.qevrulan/lockzone` | 2026-10-01T212503938107 -> 2026-10-02T061624158552 | 1 changed, 1 added | quiet |
| 2026-10-02 | `remote/com.recipebooq/recipebooq` | 2026-10-01T134421026496 -> 2026-10-02T061623476077 | 4 changed | quiet |
| 2026-10-02 | `remote/com.radar-cnpj/radar-cnpj` | 2026-10-01T134418797572 -> 2026-10-02T061624144333 | 1 added | review |
| 2026-10-02 | `remote/com.opointo/opointo` | 2026-10-01T134346251554 -> 2026-10-02T061622475375 | 4 changed | quiet |
| 2026-10-02 | `remote/com.multicinesortega/cartelera` | 2026-10-01T212453965610 -> 2026-10-02T061623229363 | 1 changed | quiet |
| 2026-10-02 | `remote/app.pixly/pixly` | 2026-10-01T212503286060 -> 2026-10-02T061623413570 | 1 changed, 1 added | quiet |
| 2026-10-02 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-10-01T212520367137 -> 2026-10-02T061622185338 | 15 changed | review |
| 2026-10-02 | `remote/ai.switchapp/switch` | 2026-10-01T134249941662 -> 2026-10-02T061621252768 | 2 changed | quiet |
| 2026-10-02 | `remote/io.railagent/railagent` | 2026-09-30T060130271739 -> 2026-10-02T061619093234 | 3 changed | quiet |
| 2026-10-02 | `remote/dev.mcphost/mcphost` | 2026-10-01T212457507621 -> 2026-10-02T061619887836 | 135 removed | quiet |
| 2026-10-02 | `remote/com.myrmigo/myrmigo` | 2026-10-01T134216251187 -> 2026-10-02T061619445108 | 1 changed | quiet |
| 2026-10-02 | `remote/app.sallim/korea-realty` | 2026-10-01T134048268420 -> 2026-10-02T061620807440 | 6 changed | quiet |
| 2026-10-02 | `remote/ai.rokha/rokha` | 2026-10-01T063523542295 -> 2026-10-02T061619916342 | 8 changed, 24 added | review |
| 2026-10-02 | `remote/es.cesaryague/paki-curator` | 2026-10-01T134024869730 -> 2026-10-02T061618411302 | 1 changed | quiet |
| 2026-10-02 | `remote/com.usecarscout/mcp` | 2026-10-01T134011951155 -> 2026-10-02T061618387566 | 3 changed | quiet |
| 2026-10-02 | `remote/ai.mapmap/mapmap` | 2026-10-01T134210522672 -> 2026-10-02T061620089692 | 1 changed | quiet |
| 2026-10-02 | `remote/pro.particle/particle-pro` | 2026-09-30T210236522509 -> 2026-10-02T061616964202 | 2 changed | quiet |
| 2026-10-02 | `remote/com.jojapi/swift-ai` | 2026-10-01T063549936493 -> 2026-10-02T061617361989 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.federico2001/openglass-mcp` | 2026-09-30T060105348979 -> 2026-10-02T061617253899 | 3 changed | quiet |
| 2026-10-02 | `remote/com.trustycap/trustycap` | 2026-09-30T152247325932 -> 2026-10-02T061618110454 | 4 changed | quiet |
| 2026-10-02 | `remote/com.metricduck/financial-analysis` | 2026-09-30T210235482488 -> 2026-10-02T061615651204 | 1 changed | quiet |
| 2026-10-02 | `remote/com.jojapi/product-barcode-api` | 2026-10-01T133913521565 -> 2026-10-02T061617470871 | 1 changed | quiet |
| 2026-10-02 | `remote/ai.skillsinput/mcp` | 2026-10-01T063519393068 -> 2026-10-02T061615930611 | 1 changed | quiet |
| 2026-10-02 | `remote/io.orbitwan/orbitwan` | 2026-10-01T063519548057 -> 2026-10-02T061616530875 | 2 added | quiet |
| 2026-10-02 | `remote/com.avnester.mcp/property-intelligence` | 2026-10-01T134118028932 -> 2026-10-02T061616939717 | 3 changed | quiet |
| 2026-10-02 | `remote/fun.lesgooo/lesgooo` | 2026-10-01T212442527313 -> 2026-10-02T061614151111 | 12 changed | quiet |
| 2026-10-02 | `remote/com.crossingkeyintelligence/crossingkey-mcp` | 2026-09-30T152209744717 -> 2026-10-02T061614789814 | 12 changed, 9 added, 1 removed (every tool) | quiet |
| 2026-10-02 | `remote/io.github.Ahmet11159/x402-agent-services` | 2026-09-30T210232476450 -> 2026-10-02T061612285619 | 1 removed | quiet |
| 2026-10-02 | `remote/net.hotelrefund/price-tracker` | 2026-10-01T063534446755 -> 2026-10-02T061611111504 | 2 changed, 3 added | quiet |
| 2026-10-02 | `remote/com.ksaworks/goldseam` | 2026-10-01T133707650663 -> 2026-10-02T061611282731 | 27 changed | quiet |
| 2026-10-02 | `remote/com.freelanceclearing/marketplace` | 2026-10-01T212458776770 -> 2026-10-02T061610819508 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 12651 substantive, 3225 that changed only numbers (a catalogue counter ticking, a date), 217 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 8467 | 5492 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `caseyjhand.com` | 66 | 66 | 0 | 0 |
| `sistaminuten.se` | 54 | 2 | 0 | 52 |
| `afbudsrejser.dk` | 53 | 2 | 0 | 51 |
| `akkilahdot.fi` | 53 | 2 | 0 | 51 |
| `restplass.no` | 53 | 2 | 0 | 51 |
| `socialloop.ai` | 52 | 52 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| `dayze.com` | 45 | 45 | 0 | 0 |
| 1620 other operators | 4337 | 4075 | 250 | 12 |
