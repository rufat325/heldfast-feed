# MCP server tool changes

Last change observed 2026-10-01T21:25:26+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

16010 changes to a tool definition: 459 npm releases (213 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 15551 readings of hosted servers that found their tools changed; 137 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-10-01 | `remote/io.taifoon/coordination-layer` | 2026-10-01T134253721006 -> 2026-10-01T212529056137 | 2 added | quiet |
| 2026-10-01 | `remote/no.restplass/travel-search` | 2026-10-01T154301160024 -> 2026-10-01T212527181875 | 1 changed | quiet |
| 2026-10-01 | `remote/com.detextit.www/detextit` | 2026-10-01T134232911885 -> 2026-10-01T212524830558 | 1 added | quiet |
| 2026-10-01 | `remote/dk.afbudsrejser/travel-search` | 2026-10-01T154257689954 -> 2026-10-01T212524773882 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.simonplmak-cloud/vision-driven-design` | 2026-10-01T063526359563 -> 2026-10-01T212522913693 | 15 changed (every tool) | quiet |
| 2026-10-01 | `remote/ai.wem3/wem-price-compare` | 2026-10-01T063527398083 -> 2026-10-01T212523557063 | 4 changed | quiet |
| 2026-10-01 | `remote/de.urlaub-smart/planner` | 2026-10-01T134213252927 -> 2026-10-01T212525847313 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-10-01T134135682628 -> 2026-10-01T212520367137 | 15 changed | review |
| 2026-10-01 | `remote/se.sistaminuten/travel-search` | 2026-10-01T154253810215 -> 2026-10-01T212519354272 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.kotinder/roomcomm` | 2026-10-01T134102599548 -> 2026-10-01T212519104306 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.tjcgraham-rgb/gaip-integration-protocol` | 2026-10-01T154253079659 -> 2026-10-01T212519968898 | 2 added | quiet |
| 2026-10-01 | `remote/com.qumge/skills` | 2026-10-01T063522286984 -> 2026-10-01T212516501076 | 3 changed | quiet |
| 2026-10-01 | `remote/com.pasteapply/mcp` | 2026-10-01T134025332231 -> 2026-10-01T212516161241 | 1 changed | quiet |
| 2026-10-01 | `remote/eu.madeinro/rotv-mcp` | 2026-10-01T154248641200 -> 2026-10-01T212513867620 | 2 changed | quiet |
| 2026-10-01 | `remote/com.vaanzari/commerce` | 2026-10-01T134353825719 -> 2026-10-01T212513600893 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.brawlaphant/vealth` | 2026-09-30T210300382823 -> 2026-10-01T212511208895 | 2 changed | quiet |
| 2026-10-01 | `remote/io.github.SKalinin909/tradingcalc` | 2026-10-01T134344648536 -> 2026-10-01T212515524968 | 2 changed | quiet |
| 2026-10-01 | `remote/io.github.realopengroup/mcp-server` | 2026-10-01T133925561478 -> 2026-10-01T212510457765 | 9 changed | quiet |
| 2026-10-01 | `remote/io.github.nirholas/threews-3d-studio-free` | 2026-10-01T134307591844 -> 2026-10-01T212510137857 | 3 added | quiet |
| 2026-10-01 | `remote/io.github.yzlee/opcmenu` | 2026-10-01T063523579330 -> 2026-10-01T212513667095 | 3 changed | quiet |
| 2026-10-01 | `remote/io.github.cryptoconspiracy/vurto-swap` | 2026-10-01T134325012815 -> 2026-10-01T212509879515 | 4 added | quiet |
| 2026-10-01 | `remote/co.lovie/company-formation` | 2026-09-29T210439821329 -> 2026-10-01T212508588543 | 5 changed | quiet |
| 2026-10-01 | `remote/watch.sbox/sbox-watch` | 2026-10-01T134301543125 -> 2026-10-01T212508879298 | 2 changed | quiet |
| 2026-10-01 | `remote/store.scvd/general-store` | 2026-10-01T154242860200 -> 2026-10-01T212509138980 | 7 changed | quiet |
| 2026-10-01 | `remote/de.honestdog/honestdog` | 2026-10-01T134222663894 -> 2026-10-01T212507654868 | 5 changed (every tool) | quiet |
| 2026-10-01 | `remote/ai.satohub/onchain-agents` | 2026-09-30T060123737078 -> 2026-10-01T212506917483 | 2 changed | quiet |
| 2026-10-01 | `remote/io.github.presendapp/presend-mcp` | 2026-10-01T134228135894 -> 2026-10-01T212504970710 | 1 changed | quiet |
| 2026-10-01 | `remote/com.predictionmarketspicks/quant` | 2026-09-30T060121259145 -> 2026-10-01T212505633091 | 12 changed | quiet |
| 2026-10-01 | `remote/fi.akkilahdot/travel-search` | 2026-10-01T154243695256 -> 2026-10-01T212504047572 | 1 changed | quiet |
| 2026-10-01 | `remote/cz.pinflower/flowers` | 2026-10-01T134226624075 -> 2026-10-01T212508817373 | 9 changed (every tool) | quiet |
| 2026-10-01 | `remote/com.qevrulan/lockzone` | 2026-09-30T152229225714 -> 2026-10-01T212503938107 | 2 changed | quiet |
| 2026-10-01 | `remote/com.atom/premium-domains` | 2026-10-01T133822006501 -> 2026-10-01T212504402699 | 3 changed | quiet |
| 2026-10-01 | `remote/io.github.Flotapponnier/openchainbench` | 2026-10-01T134209516923 -> 2026-10-01T212503118523 | 3 changed, 3 added, 1 removed (every tool) | quiet |
| 2026-10-01 | `remote/com.goedvps.app.wodan-posture/wodan-posture` | 2026-09-30T210256533209 -> 2026-10-01T212504123910 | 1 added | quiet |
| 2026-10-01 | `remote/com.narrowhighway/concordance` | 2026-10-01T134148479664 -> 2026-10-01T212502376246 | 3 added, 1 removed | quiet |
| 2026-10-01 | `remote/cloud.coredls.vigia/vigia` | 2026-09-29T003617385537 -> 2026-10-01T212503114734 | 3 added | quiet |
| 2026-10-01 | `remote/app.pixly/pixly` | 2026-10-01T134133075003 -> 2026-10-01T212503286060 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.tang-vu/keryx` | 2026-10-01T133741571551 -> 2026-10-01T212501999318 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.Schoasch/backtesting-arena` | 2026-10-01T134532878032 -> 2026-10-01T212501214482 | 4 changed | quiet |
| 2026-10-01 | `remote/com.veterical/veterical` | 2026-09-30T152218798435 -> 2026-10-01T212500291437 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-09-30T152243202527 -> 2026-10-01T212500203845 | 1 changed | quiet |
| 2026-10-01 | `remote/pl.swiadectwo-energetyczne24/zamowienia` | 2026-09-30T210250772190 -> 2026-10-01T212458891517 | 1 changed | quiet |
| 2026-10-01 | `remote/com.freelanceclearing/marketplace` | 2026-09-29T210429704416 -> 2026-10-01T212458776770 | 1 changed | quiet |
| 2026-10-01 | `remote/dev.mcphost/mcphost` | 2026-10-01T134030764079 -> 2026-10-01T212457507621 | 2 changed, 6 added | quiet |
| 2026-10-01 | `remote/com.searchfragments/search-fragments` | 2026-10-01T134441369113 -> 2026-10-01T212457130041 | 3 changed (every tool) | quiet |
| 2026-10-01 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-10-01T134020176970 -> 2026-10-01T212455990399 | 1 changed | quiet |
| 2026-10-01 | `remote/com.remoshift/jobs` | 2026-10-01T154236741144 -> 2026-10-01T212456183253 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.valuein/mcp-sec-edgar` | 2026-10-01T134014803176 -> 2026-10-01T212459508676 | 1 changed | quiet |
| 2026-10-01 | `remote/com.cymetica/event-trader-research` | 2026-10-01T063514254715 -> 2026-10-01T212456498599 | 1 changed | quiet |
| 2026-10-01 | `remote/com.predictionmarketspicks/weather` | 2026-10-01T134407801477 -> 2026-10-01T212455149629 | 2 changed | quiet |
| 2026-10-01 | `remote/com.predictionmarketspicks/commodities` | 2026-09-30T060119632593 -> 2026-10-01T212455098325 | 3 changed | quiet |
| 2026-10-01 | `remote/com.invoicevista/invoicevista` | 2026-09-30T152213463352 -> 2026-10-01T212455539887 | 1 changed | quiet |
| 2026-10-01 | `remote/estate.guthmann/mcp` | 2026-09-29T100829431533 -> 2026-10-01T212454752512 | 1 changed | quiet |
| 2026-10-01 | `remote/com.multicinesortega/cartelera` | 2026-10-01T063553595700 -> 2026-10-01T212453965610 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.nivethaug/dreamagent` | 2026-10-01T133937576940 -> 2026-10-01T212452429174 | 1 added | quiet |
| 2026-10-01 | `remote/ing.crank/crank` | 2026-10-01T133931579291 -> 2026-10-01T212451735785 | 3 changed | quiet |
| 2026-10-01 | `remote/fi.ophis/mcp` | 2026-09-29T103649335026 -> 2026-10-01T212450206891 | 2 changed | quiet |
| 2026-10-01 | `remote/eu.sirenic/sirenic` | 2026-10-01T154216137474 -> 2026-10-01T212451477347 | 14 changed | quiet |
| 2026-10-01 | `remote/org.pumppill/token-safety` | 2026-09-30T060101022659 -> 2026-10-01T212448713430 | 4 changed | quiet |
| 2026-10-01 | `remote/io.github.magichourhq/magic-hour` | 2026-10-01T063550624736 -> 2026-10-01T212448745941 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 12580 substantive, 3217 that changed only numbers (a catalogue counter ticking, a date), 213 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 8467 | 5492 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `caseyjhand.com` | 66 | 66 | 0 | 0 |
| `sistaminuten.se` | 53 | 2 | 0 | 51 |
| `afbudsrejser.dk` | 52 | 2 | 0 | 50 |
| `akkilahdot.fi` | 52 | 2 | 0 | 50 |
| `restplass.no` | 52 | 2 | 0 | 50 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| `socialloop.ai` | 51 | 51 | 0 | 0 |
| `dayze.com` | 45 | 45 | 0 | 0 |
| 1620 other operators | 4259 | 4005 | 242 | 12 |
