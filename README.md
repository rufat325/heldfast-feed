# MCP server tool changes

Last change observed 2026-10-02T15:03:38+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

16708 changes to a tool definition: 538 npm releases (292 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 16170 readings of hosted servers that found their tools changed; 163 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-10-02 | `remote/se.sistaminuten/travel-search` | 2026-10-02T130303948062 -> 2026-10-02T150339990824 | 1 changed | quiet |
| 2026-10-02 | `remote/ai.upgradeagent/upgrade-agent` | 2026-10-02T130307251938 -> 2026-10-02T150339666137 | 6 changed | quiet |
| 2026-10-02 | `remote/xyz.pflow.sim/whatif` | 2026-10-02T130425461736 -> 2026-10-02T150332612767 | 9 changed | quiet |
| 2026-10-02 | `remote/fi.akkilahdot/travel-search` | 2026-10-02T130123207497 -> 2026-10-02T150330611285 | 1 changed | quiet |
| 2026-10-02 | `remote/ai.satohub/onchain-agents` | 2026-10-02T061625005691 -> 2026-10-02T150329183438 | 2 changed | quiet |
| 2026-10-02 | `remote/io.github.presendapp/presend-mcp` | 2026-10-02T130041972541 -> 2026-10-02T150327180709 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.IO31-WEB/synapse-lounge` | 2026-10-01T063556515606 -> 2026-10-02T150327438634 | 7 changed | quiet |
| 2026-10-02 | `remote/io.github.dtajitdinov-aris/sphere-marketplace` | 2026-10-02T072127319421 -> 2026-10-02T150326136113 | 3 changed, 8 added, 8 removed | quiet |
| 2026-10-02 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-02T130028356642 -> 2026-10-02T150324111974 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.isaacaskew/venunite-events` | 2026-10-02T071920818146 -> 2026-10-02T150322922317 | 1 changed | quiet |
| 2026-10-02 | `remote/com.seqbench/workbench` | 2026-10-02T072107887128 -> 2026-10-02T150322678319 | 2 changed | quiet |
| 2026-10-02 | `remote/com.remoshift/jobs` | 2026-10-02T125952435480 -> 2026-10-02T150322789774 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.jamboree777/nightwatch` | 2026-10-02T071704814674 -> 2026-10-02T150322564846 | 4 added | review |
| 2026-10-02 | `remote/io.github.tareq7/muslim-prayer-mcp` | 2026-10-02T080505759542 -> 2026-10-02T150320822793 | 1 changed | quiet |
| 2026-10-02 | `remote/no.restplass/travel-search` | 2026-10-02T130824641036 -> 2026-10-02T150318105800 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.linxule/mcp-music-studio` | 2026-10-02T071953196326 -> 2026-10-02T150319724614 | 3 changed, 2 added | quiet |
| 2026-10-02 | `remote/com.metricduck/financial-analysis` | 2026-10-02T061615651204 -> 2026-10-02T150317854609 | 20 changed | quiet |
| 2026-10-02 | `remote/dk.afbudsrejser/travel-search` | 2026-10-02T130806780176 -> 2026-10-02T150316799928 | 1 changed | quiet |
| 2026-10-02 | `remote/com.peppolstatus/api` | 2026-10-02T125802613293 -> 2026-10-02T150316449328 | 1 changed | quiet |
| 2026-10-02 | `remote/dev.turva/turva-mcp` | 2026-10-01T134010778299 -> 2026-10-02T150314793747 | 1 changed | quiet |
| 2026-10-02 | `remote/com.tkawen/intelligence-gateway` | 2026-10-02T130217877116 -> 2026-10-02T150315434547 | 1 changed | quiet |
| 2026-10-02 | `remote/io.soundchecklive/live-event-quotes` | 2026-10-01T063523755496 -> 2026-10-02T150312662857 | 2 changed | quiet |
| 2026-10-02 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-10-02T130708962230 -> 2026-10-02T150312321190 | 15 changed | review |
| 2026-10-02 | `remote/com.luxurylodgingpm.stay/luxury-lodging` | 2026-10-01T134133624351 -> 2026-10-02T150312248337 | 6 changed (every tool) | quiet |
| 2026-10-02 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-02T130703822338 -> 2026-10-02T150311203148 | 2 changed | quiet |
| 2026-10-02 | `remote/com.movingplace/mcp` | 2026-10-02T080403215274 -> 2026-10-02T150310281110 | 16 removed | quiet |
| 2026-10-02 | `remote/pro.aicut/aicut` | 2026-10-02T125632036612 -> 2026-10-02T150309256706 | 2 changed | quiet |
| 2026-10-02 | `remote/io.github.Its-fortunatefolly/hubvibe` | 2026-10-01T063518368682 -> 2026-10-02T150309337189 | 1 changed | quiet |
| 2026-10-02 | `remote/app.sallim/korea-realty` | 2026-10-02T061620807440 -> 2026-10-02T150311460598 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-02T125413861517 -> 2026-10-02T150308205457 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.joeyaflores/ourpr-courses` | 2026-10-02T071934851037 -> 2026-10-02T150307400791 | 1 changed | quiet |
| 2026-10-02 | `remote/org.electionindex/elections` | 2026-10-01T212443567115 -> 2026-10-02T150306028755 | 2 changed | quiet |
| 2026-10-02 | `remote/app.eurocomply/compliance` | 2026-10-02T071452275968 -> 2026-10-02T150307521755 | 2 added | quiet |
| 2026-10-02 | `remote/io.github.jamie7893/keelen` | 2026-10-01T212441061109 -> 2026-10-02T150305306660 | 2 changed | quiet |
| 2026-10-02 | `remote/net.hotelrefund/price-tracker` | 2026-10-02T061611111504 -> 2026-10-02T150303543508 | 1 changed | quiet |
| 2026-10-02 | `remote/com.dayze/life-context.1` | 2026-10-02T080033213702 -> 2026-10-02T150305040860 | 2 changed | quiet |
| 2026-10-02 | `remote/com.dayze/life-context` | 2026-10-02T080033066013 -> 2026-10-02T150304496557 | 2 changed | quiet |
| 2026-10-02 | `remote/com.isoligne/index` | 2026-10-01T133738193098 -> 2026-10-02T150306482267 | 5 changed (every tool) | quiet |
| 2026-10-02 | `remote/com.googleapis.bigtableadmin/mcp` | 2026-10-02T125244335025 -> 2026-10-02T150301462536 | 3 changed | quiet |
| 2026-10-02 | `remote/io.github.CSOAI-ORG/gspc` | 2026-09-30T152157343579 -> 2026-10-02T150259688760 | 2 changed | quiet |
| 2026-10-02 | `remote/com.cymetica/event-trader-mcp` | 2026-10-01T212439360909 -> 2026-10-02T150301232132 | 2 changed | quiet |
| 2026-10-02 | `remote/ai.councilof/gspc` | 2026-09-30T152156806815 -> 2026-10-02T150259425447 | 2 changed | quiet |
| 2026-10-02 | `remote/exchange.ravn/ravn` | 2026-10-02T061604201578 -> 2026-10-02T150256479010 | 1 changed | quiet |
| 2026-10-02 | `remote/com.revdoku/revdoku` | 2026-09-30T210222498554 -> 2026-10-02T150257059201 | 1 changed, 7 added | quiet |
| 2026-10-02 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-10-01T154211632657 -> 2026-10-02T150259411289 | 2 changed | quiet |
| 2026-10-02 | `remote/com.cymetica/event-trader-research` | 2026-10-01T212456498599 -> 2026-10-02T150253667036 | 2 changed | quiet |
| 2026-10-02 | `remote/cloud.theprotocol/registry` | 2026-10-02T125150261269 -> 2026-10-02T150246927187 | 53 changed | quiet |
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

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 13236 substantive, 3239 that changed only numbers (a catalogue counter ticking, a date), 233 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 8642 | 5667 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `caseyjhand.com` | 66 | 66 | 0 | 0 |
| `sistaminuten.se` | 58 | 2 | 0 | 56 |
| `afbudsrejser.dk` | 57 | 2 | 0 | 55 |
| `akkilahdot.fi` | 57 | 2 | 0 | 55 |
| `restplass.no` | 57 | 2 | 0 | 55 |
| `socialloop.ai` | 56 | 56 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| `dayze.com` | 49 | 49 | 0 | 0 |
| 1811 other operators | 4753 | 4477 | 264 | 12 |
