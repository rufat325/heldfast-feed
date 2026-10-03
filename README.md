# MCP server tool changes

Last change observed 2026-10-03T12:15:58+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

18784 changes to a tool definition: 627 npm releases (381 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 18157 readings of hosted servers that found their tools changed; 185 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-10-03 | `remote/ai.zairalabs/guide` | 2026-09-23T163000150747 -> 2026-10-03T121559285519 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.switchwize/switchwize-mcp` | 2026-09-25T120618915601 -> 2026-10-03T121553035339 | 2 changed | quiet |
| 2026-10-03 | `remote/com.immersivecommons/floor10` | 2026-09-23T162945053559 -> 2026-10-03T121621519905 | 2 changed | quiet |
| 2026-10-03 | `remote/com.hemmabo/hemmabo-mcp-server` | 2026-10-01T134627219573 -> 2026-10-03T121539037880 | 6 changed (every tool) | quiet |
| 2026-10-03 | `remote/io.github.SoapyRED/freightutils` | 2026-09-23T162942017964 -> 2026-10-03T121534937822 | 1 changed | quiet |
| 2026-10-03 | `remote/fi.akkilahdot/travel-search` | 2026-10-03T054748663076 -> 2026-10-03T121525614663 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.thinksuitesolution-coder/visibilityai` | 2026-09-24T202744395235 -> 2026-10-03T121515293933 | 3 added | quiet |
| 2026-10-03 | `remote/ru.vedarai/mcp` | 2026-10-02T130108199836 -> 2026-10-03T121514009988 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.OmniAISystems/govomniai-machine-services` | 2026-09-28T142558308470 -> 2026-10-03T121508838073 | 4 added, 2 removed | review |
| 2026-10-03 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-03T054748099315 -> 2026-10-03T121454437881 | 1 changed | quiet |
| 2026-10-03 | `remote/com.tablejourney/food-travel` | 2026-09-30T210251087749 -> 2026-10-03T121449118936 | 4 changed, 2 added | quiet |
| 2026-10-03 | `remote/ch.swisslivingindex/swiss-living-index` | 2026-09-23T162902388316 -> 2026-10-03T121448003812 | 17 added | quiet |
| 2026-10-03 | `remote/com.penguindriver/stock` | 2026-09-28T142536150128 -> 2026-10-03T121441082649 | 7 added | quiet |
| 2026-10-03 | `remote/io.github.dtajitdinov-aris/sphere-marketplace` | 2026-10-03T054746775288 -> 2026-10-03T121441191946 | 1 added, 1 removed | quiet |
| 2026-10-03 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-03T054744613837 -> 2026-10-03T121432995622 | 1 changed | quiet |
| 2026-10-03 | `remote/com.penguindriver/shop` | 2026-10-02T080746086519 -> 2026-10-03T121426648226 | 3 added | quiet |
| 2026-10-03 | `remote/io.github.zambodotdev/zambo` | 2026-09-26T132441449037 -> 2026-10-03T121419603874 | 13 changed, 6 added (every tool) | quiet |
| 2026-10-03 | `remote/dev.zambo/zambo` | 2026-09-28T142417627299 -> 2026-10-03T121419737923 | 13 changed, 6 added (every tool) | quiet |
| 2026-10-03 | `remote/com.seqbench/workbench` | 2026-10-02T210131795346 -> 2026-10-03T121419431566 | 3 added | quiet |
| 2026-10-03 | `remote/io.github.Fizzl13/x402-doctor` | 2026-09-29T131734183659 -> 2026-10-03T121413275113 | 1 added | quiet |
| 2026-10-03 | `remote/com.remoshift/jobs` | 2026-10-03T054743576118 -> 2026-10-03T121400703941 | 1 changed | quiet |
| 2026-10-03 | `remote/com.symbaiex.www/evidence` | 2026-09-23T163147077988 -> 2026-10-03T121353441333 | 1 changed | quiet |
| 2026-10-03 | `remote/no.restplass/travel-search` | 2026-10-03T054743569309 -> 2026-10-03T121348815781 | 1 changed | quiet |
| 2026-10-03 | `remote/ai.go-rocket/go-rocket` | 2026-09-28T142346323526 -> 2026-10-03T121345079899 | 2 changed, 2 added | review |
| 2026-10-03 | `remote/io.github.conversoriaecnae/conversor-iae-cnae` | 2026-09-23T160838124045 -> 2026-10-03T121338621650 | 19 changed (every tool) | quiet |
| 2026-10-03 | `remote/io.deeplead/deeplead` | 2026-10-02T130812253057 -> 2026-10-03T121336741314 | 3 changed | quiet |
| 2026-10-03 | `remote/io.github.CryptoSuess/basealpha` | 2026-09-26T045516370310 -> 2026-10-03T121334479898 | 1 changed | quiet |
| 2026-10-03 | `remote/net.clickwise/product-catalog` | 2026-09-29T113303117731 -> 2026-10-03T121333767072 | 7 changed | quiet |
| 2026-10-03 | `remote/io.github.JakubTrousil/agentsjunction` | 2026-09-24T202822796575 -> 2026-10-03T121352489352 | 23 changed (every tool) | quiet |
| 2026-10-03 | `remote/dk.afbudsrejser/travel-search` | 2026-10-03T054742595143 -> 2026-10-03T121332003410 | 1 changed | quiet |
| 2026-10-03 | `remote/com.datakoot/us-weather-forecast-alerts` | 2026-09-23T163109848751 -> 2026-10-03T121326021096 | 6 changed (every tool) | quiet |
| 2026-10-03 | `remote/io.github.physics-star-cat/whatbreaks-mot` | 2026-09-23T160829998282 -> 2026-10-03T121321605293 | 2 changed (every tool) | quiet |
| 2026-10-03 | `remote/io.github.bytevirts/viewmax` | 2026-09-29T073439676582 -> 2026-10-03T121322430758 | 9 changed | quiet |
| 2026-10-03 | `remote/io.github.FTHTrading/genesis402-mcp` | 2026-09-30T152243783191 -> 2026-10-03T121256039001 | 1 changed, 1 added | quiet |
| 2026-10-03 | `remote/dev.workers.panda198271.tw-stock-themes/stock-themes` | 2026-09-28T142304160739 -> 2026-10-03T121255585321 | 7 added | quiet |
| 2026-10-03 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-10-03T054738929677 -> 2026-10-03T121243481387 | 15 changed | review |
| 2026-10-03 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-03T054738098015 -> 2026-10-03T121239601108 | 2 changed | quiet |
| 2026-10-03 | `remote/com.spacexploration/listings` | 2026-09-29T073354596950 -> 2026-10-03T121238327351 | 15 changed (every tool) | quiet |
| 2026-10-03 | `remote/io.github.springrolldev/springroll` | 2026-09-26T114221080160 -> 2026-10-03T121219884947 | 2 added | quiet |
| 2026-10-03 | `remote/app.sprkly/sprkly` | 2026-09-24T120352629987 -> 2026-10-03T121221241360 | 2 changed | quiet |
| 2026-10-03 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-02T182835010683 -> 2026-10-03T121218445946 | 1 changed | quiet |
| 2026-10-03 | `remote/com.minimindslab.mcp/tools` | 2026-09-27T154836135873 -> 2026-10-03T121216835333 | 1 added | quiet |
| 2026-10-03 | `remote/jp.renkeimap/renkeimap-info` | 2026-09-23T162939781460 -> 2026-10-03T121208701146 | 1 changed, 1 added | quiet |
| 2026-10-03 | `remote/com.sigistry/plugin-catalog` | 2026-09-23T160748175233 -> 2026-10-03T121205524522 | 1 added | quiet |
| 2026-10-03 | `remote/com.shipshapedata/shipshape-data` | 2026-10-02T130420701388 -> 2026-10-03T121201803922 | 1 changed | quiet |
| 2026-10-03 | `remote/com.jobmojito/jobmojito` | 2026-09-29T131225180911 -> 2026-10-03T121203406115 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.quantustik/mcp` | 2026-09-23T162931936636 -> 2026-10-03T121201281658 | 6 changed, 18 removed | quiet |
| 2026-10-03 | `remote/io.github.daniel3303/equibles` | 2026-09-28T055525069811 -> 2026-10-03T121143778884 | 2 changed | quiet |
| 2026-10-03 | `remote/com.datakoot/federal-register-rules` | 2026-09-23T160730963678 -> 2026-10-03T121135937582 | 5 changed (every tool) | quiet |
| 2026-10-03 | `remote/io.github.salemalem/npmscan` | 2026-10-02T182710570857 -> 2026-10-03T121128978776 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.Quantabble/ap-science-diagnostics` | 2026-09-23T160727181005 -> 2026-10-03T121127745049 | 2 changed (every tool) | quiet |
| 2026-10-03 | `remote/io.github.Perufitlife/postwire-mcp` | 2026-10-02T182742014309 -> 2026-10-03T121137577665 | 5 changed, 2 added | quiet |
| 2026-10-03 | `remote/io.github.samuelzcom/chauffeur-booking` | 2026-10-03T054743984212 -> 2026-10-03T121118181807 | 5 changed (every tool) | quiet |
| 2026-10-03 | `remote/com.plainrouter/mcp` | 2026-09-30T210248484672 -> 2026-10-03T121113379546 | 1 changed | quiet |
| 2026-10-03 | `remote/app.netlify.meinlem/nexo` | 2026-09-29T073217411095 -> 2026-10-03T121114017178 | 3 changed, 8 added | quiet |
| 2026-10-03 | `remote/io.corpusiq/multi-source-mcp` | 2026-09-29T073215118464 -> 2026-10-03T121111715945 | 41 changed | quiet |
| 2026-10-03 | `remote/ai.tunnelmind/data` | 2026-09-23T162603465175 -> 2026-10-03T121103060131 | 1 changed, 5 added | review |
| 2026-10-03 | `remote/ai.tickerscout/ticker-scout` | 2026-09-23T162818805286 -> 2026-10-03T121059802065 | 1 changed | quiet |
| 2026-10-03 | `remote/io.thegavel/gavel` | 2026-09-23T162817624154 -> 2026-10-03T121059095253 | 1 changed | quiet |
| 2026-10-03 | `remote/com.ownerspec/mcp` | 2026-09-23T160706897829 -> 2026-10-03T121057933288 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 13754 substantive, 4780 that changed only numbers (a catalogue counter ticking, a date), 250 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 10160 | 5677 | 4483 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `caseyjhand.com` | 66 | 66 | 0 | 0 |
| `sistaminuten.se` | 62 | 2 | 0 | 60 |
| `afbudsrejser.dk` | 61 | 2 | 0 | 59 |
| `akkilahdot.fi` | 61 | 2 | 0 | 59 |
| `restplass.no` | 61 | 2 | 0 | 59 |
| `socialloop.ai` | 60 | 60 | 0 | 0 |
| `dayze.com` | 55 | 55 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| 1973 other operators | 5285 | 4975 | 297 | 13 |
