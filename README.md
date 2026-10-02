# MCP server tool changes

Last change observed 2026-10-02T13:08:30+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

16661 changes to a tool definition: 538 npm releases (292 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 16123 readings of hosted servers that found their tools changed; 161 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-10-02 | `remote/io.taifoon/coordination-layer` | 2026-10-01T212529056137 -> 2026-10-02T130832931637 | 1 changed, 2 added | quiet |
| 2026-10-02 | `remote/no.restplass/travel-search` | 2026-10-02T080855420550 -> 2026-10-02T130824641036 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.tjcgraham-rgb/gaip-supplier-watch` | 2026-10-01T154300207785 -> 2026-10-02T130819002137 | 1 changed | quiet |
| 2026-10-02 | `remote/io.deeplead/deeplead` | 2026-10-02T072136078915 -> 2026-10-02T130812253057 | 2 added | review |
| 2026-10-02 | `remote/com.detextit.www/detextit` | 2026-10-02T061629536204 -> 2026-10-02T130812032952 | 2 added | quiet |
| 2026-10-02 | `remote/dk.afbudsrejser/travel-search` | 2026-10-02T080835418417 -> 2026-10-02T130806780176 | 1 changed | quiet |
| 2026-10-02 | `remote/com.wizeb/ai-native-index` | 2026-09-23T163114975845 -> 2026-10-02T130803301249 | 1 changed | quiet |
| 2026-10-02 | `remote/de.urlaub-smart/planner` | 2026-10-01T212525847313 -> 2026-10-02T130747304155 | 4 changed | quiet |
| 2026-10-02 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-10-02T080740713367 -> 2026-10-02T130708962230 | 15 changed | review |
| 2026-10-02 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-02T080735008116 -> 2026-10-02T130703822338 | 2 changed | quiet |
| 2026-10-02 | `remote/com.scentverdict/fragrances` | 2026-09-23T202435318084 -> 2026-10-02T130640571444 | 4 changed | quiet |
| 2026-10-02 | `remote/com.rewindmap/rewindmap` | 2026-09-28T142122021317 -> 2026-10-02T130630996444 | 1 added | quiet |
| 2026-10-02 | `remote/com.sulvo.publisher-revenue-audit/audit` | 2026-09-23T162927501153 -> 2026-10-02T130617185157 | 41 changed (every tool) | quiet |
| 2026-10-02 | `remote/es.cesaryague/paki-curator` | 2026-10-02T061618411302 -> 2026-10-02T130552793637 | 2 changed | quiet |
| 2026-10-02 | `remote/io.github.salemalem/npmscan` | 2026-10-01T134014299788 -> 2026-10-02T130541351939 | 3 changed | quiet |
| 2026-10-02 | `remote/cc.thecolony/mcp-server` | 2026-10-02T061629905741 -> 2026-10-02T130502173782 | 3 changed, 1 added | quiet |
| 2026-10-02 | `remote/ai.intuitek.the-stall/the-stall` | 2026-10-02T061628411748 -> 2026-10-02T130500845443 | 5 changed | review |
| 2026-10-02 | `remote/com.talval/research` | 2026-09-29T101103472496 -> 2026-10-02T130500776772 | 7 changed (every tool) | quiet |
| 2026-10-02 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-01T154246290727 -> 2026-10-02T130434517841 | 17 added | quiet |
| 2026-10-02 | `remote/io.orbitwan/orbitwan` | 2026-10-02T061616530875 -> 2026-10-02T130430411210 | 2 changed | quiet |
| 2026-10-02 | `remote/xyz.pflow.sim/whatif` | 2026-10-02T080627596829 -> 2026-10-02T130425461736 | 4 changed, 2 added | quiet |
| 2026-10-02 | `remote/com.shipshapedata/shipshape-data` | 2026-09-23T160746355407 -> 2026-10-02T130420701388 | 1 changed | quiet |
| 2026-10-02 | `remote/com.courtdelta/court-delta` | 2026-09-23T162702668013 -> 2026-10-02T130346367840 | 2 changed | quiet |
| 2026-10-02 | `remote/co.cookie-compliance/cookie-consent` | 2026-10-01T133833665362 -> 2026-10-02T130346322118 | 4 changed | quiet |
| 2026-10-02 | `remote/com.commerceforagents/commerceforagents` | 2026-09-28T141822302916 -> 2026-10-02T130345087776 | 1 added | quiet |
| 2026-10-02 | `remote/com.pontofato/pontofato` | 2026-10-01T134136696417 -> 2026-10-02T130337710514 | 1 changed | quiet |
| 2026-10-02 | `remote/com.atom/premium-domains` | 2026-10-01T212504402699 -> 2026-10-02T130334535817 | 4 changed | quiet |
| 2026-10-02 | `remote/io.github.samuelzcom/chauffeur-booking` | 2026-09-27T103718621082 -> 2026-10-02T130341499692 | 5 changed (every tool) | quiet |
| 2026-10-02 | `remote/com.appskyline/appskyline` | 2026-10-02T071718510111 -> 2026-10-02T130333134448 | 1 changed | quiet |
| 2026-10-02 | `remote/com.peerpush/peerpush` | 2026-10-01T154240490067 -> 2026-10-02T130329338109 | 8 changed | quiet |
| 2026-10-02 | `remote/io.github.julian-martin89/pkg-oracle` | 2026-09-23T162633460993 -> 2026-10-02T130315546058 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.Skyline-Roofing/oracle-api` | 2026-09-27T153150385481 -> 2026-10-02T130315372303 | 5 changed (every tool) | quiet |
| 2026-10-02 | `remote/ai.upgradeagent/upgrade-agent` | 2026-09-23T161038249014 -> 2026-10-02T130307251938 | 1 changed, 2 added | quiet |
| 2026-10-02 | `remote/se.sistaminuten/travel-search` | 2026-10-02T080813120995 -> 2026-10-02T130303948062 | 1 changed | quiet |
| 2026-10-02 | `remote/ai.snowsure/snow` | 2026-10-02T072251806076 -> 2026-10-02T130303543291 | 1 changed | quiet |
| 2026-10-02 | `remote/io.kolmo.www/kolmo-mcp-server` | 2026-09-26T045436009681 -> 2026-10-02T130253849471 | 2 changed | quiet |
| 2026-10-02 | `remote/io.github.tjcgraham-rgb/gaip-integration-protocol` | 2026-10-02T061638295824 -> 2026-10-02T130253731734 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.tang-vu/keryx` | 2026-10-01T212501999318 -> 2026-10-02T130249534777 | 1 added | quiet |
| 2026-10-02 | `remote/exchange.merx/mcp` | 2026-09-23T160641321350 -> 2026-10-02T130242584739 | 7 changed | quiet |
| 2026-10-02 | `remote/com.tkawen/intelligence-gateway` | 2026-10-02T080437662318 -> 2026-10-02T130217877116 | 1 changed | quiet |
| 2026-10-02 | `remote/com.reqbeat/hiring-signals` | 2026-09-23T160606736094 -> 2026-10-02T130159429286 | 4 changed | quiet |
| 2026-10-02 | `remote/io.github.pipeworx-io/zillow` | 2026-09-27T065518937191 -> 2026-10-02T130158139786 | 5 changed | quiet |
| 2026-10-02 | `remote/io.github.pipeworx-io/youtube` | 2026-09-27T065518819309 -> 2026-10-02T130158546488 | 5 changed | quiet |
| 2026-10-02 | `remote/io.github.pipeworx-io/yesterdays-number` | 2026-09-27T065518954537 -> 2026-10-02T130158735012 | 5 changed | quiet |
| 2026-10-02 | `remote/io.github.pipeworx-io/worldbank-procurement` | 2026-09-27T065518412845 -> 2026-10-02T130157718816 | 5 changed | quiet |
| 2026-10-02 | `remote/io.github.pipeworx-io/wordnik` | 2026-09-27T065518161896 -> 2026-10-02T130156789961 | 5 changed | quiet |
| 2026-10-02 | `remote/io.github.pipeworx-io/whoisxml` | 2026-09-27T065517812344 -> 2026-10-02T130156519367 | 5 changed | quiet |
| 2026-10-02 | `remote/io.github.pipeworx-io/whiskyhunter` | 2026-09-27T065517833751 -> 2026-10-02T130157679663 | 5 changed | quiet |
| 2026-10-02 | `remote/io.github.pipeworx-io/weather-gc-ca` | 2026-09-27T065517719150 -> 2026-10-02T130155203258 | 5 changed | quiet |
| 2026-10-02 | `remote/io.github.pipeworx-io/watchmode` | 2026-10-01T133648605430 -> 2026-10-02T130154746314 | 1 changed | quiet |
| 2026-10-02 | `remote/com.riddle/creator` | 2026-09-23T162953011073 -> 2026-10-02T130148294032 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.tjcgraham-rgb/gaip-witness` | 2026-10-02T061637849889 -> 2026-10-02T130137066893 | 1 changed | quiet |
| 2026-10-02 | `remote/com.jojapi/product-barcode-api` | 2026-10-02T061617470871 -> 2026-10-02T130124602302 | 1 changed | quiet |
| 2026-10-02 | `remote/fi.akkilahdot/travel-search` | 2026-10-02T080849825360 -> 2026-10-02T130123207497 | 1 changed | quiet |
| 2026-10-02 | `remote/com.giftstoprint/poster-connector` | 2026-09-23T160537150640 -> 2026-10-02T130114572971 | 4 changed, 1 added (every tool) | quiet |
| 2026-10-02 | `remote/ru.vedarai/mcp` | 2026-09-30T060134324213 -> 2026-10-02T130108199836 | 2 changed | quiet |
| 2026-10-02 | `remote/io.github.sharan01x/usetested` | 2026-10-01T134543976239 -> 2026-10-02T130105345889 | 1 changed | quiet |
| 2026-10-02 | `remote/app.repopilot/repopilot` | 2026-10-01T134247600534 -> 2026-10-02T130100713183 | 2 changed | quiet |
| 2026-10-02 | `remote/io.github.Schoasch/backtesting-arena` | 2026-10-01T212501214482 -> 2026-10-02T130057040509 | 3 changed | quiet |
| 2026-10-02 | `remote/io.github.presendapp/presend-mcp` | 2026-10-01T212504970710 -> 2026-10-02T130041972541 | 3 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 13197 substantive, 3235 that changed only numbers (a catalogue counter ticking, a date), 229 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 8642 | 5667 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `caseyjhand.com` | 66 | 66 | 0 | 0 |
| `sistaminuten.se` | 57 | 2 | 0 | 55 |
| `afbudsrejser.dk` | 56 | 2 | 0 | 54 |
| `akkilahdot.fi` | 56 | 2 | 0 | 54 |
| `restplass.no` | 56 | 2 | 0 | 54 |
| `socialloop.ai` | 55 | 55 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| `dayze.com` | 47 | 47 | 0 | 0 |
| 1810 other operators | 4713 | 4441 | 260 | 12 |
