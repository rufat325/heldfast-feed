# MCP server tool changes

Last change observed 2026-10-03T19:29:17+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

18911 changes to a tool definition: 627 npm releases (381 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 18284 readings of hosted servers that found their tools changed; 195 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-10-03 | `remote/com.immersivecommons/floor10` | 2026-10-03T121621519905 -> 2026-10-03T192918315378 | 1 added | quiet |
| 2026-10-03 | `remote/com.hemmabo/hemmabo-mcp-server` | 2026-10-03T121539037880 -> 2026-10-03T192917733985 | 2 changed | review |
| 2026-10-03 | `remote/fi.akkilahdot/travel-search` | 2026-10-03T135718637240 -> 2026-10-03T192917455142 | 1 changed | quiet |
| 2026-10-03 | `remote/com.waitingforpower/energy-permitting-tracker` | 2026-10-02T061629960460 -> 2026-10-03T192915604897 | 1 changed, 2 removed | quiet |
| 2026-10-03 | `remote/xyz.pflow.sim/whatif` | 2026-10-02T210150190656 -> 2026-10-03T192912869717 | 1 changed | quiet |
| 2026-10-03 | `remote/com.useslop/mcp` | 2026-10-01T134544526880 -> 2026-10-03T192913938005 | 3 added | quiet |
| 2026-10-03 | `remote/world.agentindex/x402` | 2026-10-02T072221943997 -> 2026-10-03T192913500419 | 25 added | quiet |
| 2026-10-03 | `remote/com.synapticrelay/board.1` | 2026-10-02T182800129906 -> 2026-10-03T192912659794 | 1 changed | quiet |
| 2026-10-03 | `remote/se.sistaminuten/travel-search` | 2026-10-03T135738819137 -> 2026-10-03T192911608226 | 1 changed | quiet |
| 2026-10-03 | `remote/no.restplass/travel-search` | 2026-10-03T135738347853 -> 2026-10-03T192912324155 | 1 changed | quiet |
| 2026-10-03 | `remote/io.taifoon/coordination-layer` | 2026-10-02T183021905118 -> 2026-10-03T192912987039 | 4 changed | quiet |
| 2026-10-03 | `remote/io.github.Jaywestphilly/stock-bloc` | 2026-10-03T054745683407 -> 2026-10-03T192911210854 | 1 added | review |
| 2026-10-03 | `remote/ir.cbest/lighting` | 2026-10-01T134232083092 -> 2026-10-03T192910247195 | 1 changed | quiet |
| 2026-10-03 | `remote/com.datakoot/federal-register-rules` | 2026-10-03T121135937582 -> 2026-10-03T192909983249 | 5 changed (every tool) | quiet |
| 2026-10-03 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-03T135712622467 -> 2026-10-03T192909904193 | 5 changed | quiet |
| 2026-10-03 | `remote/io.github.Perufitlife/postwire-mcp` | 2026-10-03T121137577665 -> 2026-10-03T192909356144 | 1 changed | quiet |
| 2026-10-03 | `remote/dk.afbudsrejser/travel-search` | 2026-10-03T135736331848 -> 2026-10-03T192910933882 | 1 changed | quiet |
| 2026-10-03 | `remote/com.datakoot/us-weather-forecast-alerts` | 2026-10-03T121326021096 -> 2026-10-03T192908429948 | 6 changed (every tool) | quiet |
| 2026-10-03 | `remote/io.github.mangelmartinezfer-hue/returncheck` | 2026-10-02T182715337519 -> 2026-10-03T192907962134 | 1 changed | quiet |
| 2026-10-03 | `remote/com.searchfragments/search-fragments` | 2026-10-01T212457130041 -> 2026-10-03T192909353707 | 1 changed | quiet |
| 2026-10-03 | `remote/com.remoshift/jobs` | 2026-10-03T135711737161 -> 2026-10-03T192908407949 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-10-03T135731447184 -> 2026-10-03T192905787154 | 15 changed | review |
| 2026-10-03 | `remote/com.recipebooq/recipebooq` | 2026-10-02T061623476077 -> 2026-10-03T192907319691 | 1 changed | quiet |
| 2026-10-03 | `remote/com.voyagehacks/travel` | 2026-10-01T134402121269 -> 2026-10-03T192904552097 | 11 changed | quiet |
| 2026-10-03 | `remote/com.opointo/opointo` | 2026-10-02T061622475375 -> 2026-10-03T192905060463 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.naief9961-tech/naif-fixgraph` | 2026-10-02T071955548346 -> 2026-10-03T192905703298 | 1 changed, 2 added | quiet |
| 2026-10-03 | `remote/com.vaanzari/commerce` | 2026-10-01T212513600893 -> 2026-10-03T192904103548 | 4 changed | quiet |
| 2026-10-03 | `remote/jp.renkeimap/renkeimap-info` | 2026-10-03T121208701146 -> 2026-10-03T192903495435 | 1 added | quiet |
| 2026-10-03 | `remote/ai.rokha/rokha` | 2026-10-03T054736800163 -> 2026-10-03T192903276009 | 2 changed | quiet |
| 2026-10-03 | `remote/io.github.tareq7/muslim-prayer-mcp` | 2026-10-03T121036767767 -> 2026-10-03T192902361527 | 5 changed (every tool) | quiet |
| 2026-10-03 | `remote/io.github.lemonaide152/meld` | 2026-10-02T182644580600 -> 2026-10-03T192905580393 | 1 changed | quiet |
| 2026-10-03 | `remote/dev.mcphost/mcphost` | 2026-10-02T061619887836 -> 2026-10-03T192900589815 | 12 changed (every tool) | quiet |
| 2026-10-03 | `remote/com.datakoot/cve-vulnerability-lookup` | 2026-10-03T120005518052 -> 2026-10-03T192859745752 | 5 changed (every tool) | quiet |
| 2026-10-03 | `remote/io.corpusiq/multi-source-mcp` | 2026-10-03T121111715945 -> 2026-10-03T192857190000 | 114 changed | quiet |
| 2026-10-03 | `remote/com.kernelcad/kernelcad` | 2026-10-03T135703784296 -> 2026-10-03T192858920006 | 7 changed, 1 added | quiet |
| 2026-10-03 | `remote/com.tradestarinsider/edgar-insider-signals` | 2026-10-03T054732284754 -> 2026-10-03T192857722511 | 5 changed | quiet |
| 2026-10-03 | `remote/com.datakoot/npm-pypi-crates-packages` | 2026-10-03T115918801584 -> 2026-10-03T192854787838 | 6 changed (every tool) | quiet |
| 2026-10-03 | `remote/io.github.quotor/home-auto-insurance-quotes` | 2026-10-02T071829348977 -> 2026-10-03T192855946416 | 3 changed | quiet |
| 2026-10-03 | `remote/pro.aicut/aicut` | 2026-10-02T150309256706 -> 2026-10-03T192853678036 | 1 changed | quiet |
| 2026-10-03 | `remote/io.orbitwan/orbitwan` | 2026-10-03T135720019119 -> 2026-10-03T192854535839 | 1 changed | quiet |
| 2026-10-03 | `remote/com.thefilmradar/filmlab` | 2026-10-03T135659655842 -> 2026-10-03T192853719763 | 4 changed, 1 added | review |
| 2026-10-03 | `remote/ai.tunnelmind/data` | 2026-10-03T121103060131 -> 2026-10-03T192853014371 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.worklittle/jobs` | 2026-10-03T115830418060 -> 2026-10-03T192851759365 | 1 changed, 2 added | quiet |
| 2026-10-03 | `remote/io.github.SidneyBissoli/medical-terminologies-mcp` | 2026-10-02T182605442409 -> 2026-10-03T192853484786 | 5 changed | quiet |
| 2026-10-03 | `remote/com.hergertsynthora/synthora-x402` | 2026-10-02T080345659612 -> 2026-10-03T192853223454 | 7 added, 32 removed | review |
| 2026-10-03 | `remote/so.darwin/darwin` | 2026-10-02T210114887721 -> 2026-10-03T192849477116 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.RidioDevelopment/socialcrawl` | 2026-10-02T071857182936 -> 2026-10-03T192849199156 | 1 changed, 6 added, 9 removed | review |
| 2026-10-03 | `remote/com.dimhour/catalog` | 2026-10-03T135715410710 -> 2026-10-03T192850330142 | 8 changed | quiet |
| 2026-10-03 | `remote/io.github.tcador/787daily` | 2026-10-02T210120973621 -> 2026-10-03T192848660239 | 1 changed | quiet |
| 2026-10-03 | `remote/com.gocodebook/codes` | 2026-10-03T121021791515 -> 2026-10-03T192848476712 | 2 changed | quiet |
| 2026-10-03 | `remote/io.github.RightOnPar-LLC/meshmarket` | 2026-10-01T133822053568 -> 2026-10-03T192847956585 | 7 changed, 1 added | quiet |
| 2026-10-03 | `remote/com.datakoot/fx-currency-exchange-rates` | 2026-10-03T120827496775 -> 2026-10-03T192847427090 | 3 changed | quiet |
| 2026-10-03 | `remote/org.lexiara/lexiara` | 2026-10-03T120814022206 -> 2026-10-03T192846891116 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-10-01T212455990399 -> 2026-10-03T192846303961 | 2 changed | review |
| 2026-10-03 | `remote/com.avokata/avokata` | 2026-10-03T120938209757 -> 2026-10-03T192847912338 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.foxxx009/x402-tools-mcp` | 2026-10-03T054721246017 -> 2026-10-03T192848796785 | 10 changed | review |
| 2026-10-03 | `remote/io.insourcia/insourcia` | 2026-10-01T134004222489 -> 2026-10-03T192845171671 | 1 added | quiet |
| 2026-10-03 | `remote/io.github.DevDizzle/gammarips` | 2026-10-03T054727223112 -> 2026-10-03T192843408182 | 2 changed | quiet |
| 2026-10-03 | `remote/io.github.Dahliyaal/justicelibre` | 2026-10-03T120851820224 -> 2026-10-03T192844835985 | 33 changed | quiet |
| 2026-10-03 | `remote/com.elkassabgidata/elkassabgidata` | 2026-10-02T071309547508 -> 2026-10-03T192844113465 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 13861 substantive, 4791 that changed only numbers (a catalogue counter ticking, a date), 259 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 10160 | 5677 | 4483 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `caseyjhand.com` | 66 | 66 | 0 | 0 |
| `sistaminuten.se` | 64 | 2 | 0 | 62 |
| `afbudsrejser.dk` | 63 | 2 | 0 | 61 |
| `akkilahdot.fi` | 63 | 2 | 0 | 61 |
| `restplass.no` | 63 | 2 | 0 | 61 |
| `socialloop.ai` | 62 | 62 | 0 | 0 |
| `dayze.com` | 59 | 59 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| 1974 other operators | 5398 | 5076 | 308 | 14 |
