# MCP server tool changes

Last change observed 2026-10-03T13:57:38+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

18823 changes to a tool definition: 627 npm releases (381 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 18196 readings of hosted servers that found their tools changed; 186 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-10-03 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-03T121218445946 -> 2026-10-03T135739414202 | 5 changed | quiet |
| 2026-10-03 | `remote/se.sistaminuten/travel-search` | 2026-10-03T120126924348 -> 2026-10-03T135738819137 | 1 changed | quiet |
| 2026-10-03 | `remote/no.restplass/travel-search` | 2026-10-03T121348815781 -> 2026-10-03T135738347853 | 1 changed | quiet |
| 2026-10-03 | `remote/dk.afbudsrejser/travel-search` | 2026-10-03T121332003410 -> 2026-10-03T135736331848 | 1 changed | quiet |
| 2026-10-03 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-03T120100544280 -> 2026-10-03T135735695755 | 1 added | quiet |
| 2026-10-03 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-10-03T121243481387 -> 2026-10-03T135731447184 | 15 changed | review |
| 2026-10-03 | `remote/app.meistron/meistron` | 2026-10-02T080455917988 -> 2026-10-03T135726023666 | 2 removed | quiet |
| 2026-10-03 | `remote/re.parcellai/parcellaire` | 2026-10-03T115924203874 -> 2026-10-03T135727616655 | 1 added | quiet |
| 2026-10-03 | `remote/com.streaming-lens.mcp/streaming-radar` | 2026-10-01T134002586803 -> 2026-10-03T135720589181 | 2 changed | quiet |
| 2026-10-03 | `remote/io.orbitwan/orbitwan` | 2026-10-03T121031795307 -> 2026-10-03T135720019119 | 2 changed | quiet |
| 2026-10-03 | `remote/fi.akkilahdot/travel-search` | 2026-10-03T121525614663 -> 2026-10-03T135718637240 | 1 changed | quiet |
| 2026-10-03 | `remote/ru.vedarai/mcp` | 2026-10-03T121514009988 -> 2026-10-03T135718511041 | 1 changed | quiet |
| 2026-10-03 | `remote/com.dimhour/catalog` | 2026-10-02T071737673432 -> 2026-10-03T135715410710 | 3 changed | quiet |
| 2026-10-03 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-03T121432995622 -> 2026-10-03T135712622467 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.Poiuyhje/eqvps` | 2026-10-03T120904848191 -> 2026-10-03T135713952691 | 4 changed, 3 added | quiet |
| 2026-10-03 | `remote/com.remoshift/jobs` | 2026-10-03T121400703941 -> 2026-10-03T135711737161 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.peter120525-cmd/lawmadi-os` | 2026-10-03T054723948733 -> 2026-10-03T135711408143 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.Kotaro-Studio/kurashigram` | 2026-10-03T120855269660 -> 2026-10-03T135710316367 | 1 changed | quiet |
| 2026-10-03 | `remote/net.clickwise/product-catalog` | 2026-10-03T121333767072 -> 2026-10-03T135709344480 | 1 changed | quiet |
| 2026-10-03 | `remote/io.github.linxule/mcp-music-studio` | 2026-10-02T210129404228 -> 2026-10-03T135709729687 | 3 changed | quiet |
| 2026-10-03 | `remote/com.penguindriver/hub` | 2026-10-03T120745894826 -> 2026-10-03T135707124982 | 6 changed, 14 added | quiet |
| 2026-10-03 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-03T115425310557 -> 2026-10-03T135704647421 | 1 changed | quiet |
| 2026-10-03 | `remote/org.electionindex/elections` | 2026-10-03T115407310097 -> 2026-10-03T135703149907 | 2 changed | quiet |
| 2026-10-03 | `remote/ai.mapmap/mapmap` | 2026-10-02T061620089692 -> 2026-10-03T135704975852 | 2 added | quiet |
| 2026-10-03 | `remote/com.kernelcad/kernelcad` | 2026-10-01T154226895228 -> 2026-10-03T135703784296 | 11 changed | quiet |
| 2026-10-03 | `remote/cloud.dchub/mcp-server` | 2026-10-03T115352663407 -> 2026-10-03T135702363603 | 14 changed | quiet |
| 2026-10-03 | `remote/com.dayze/life-context.1` | 2026-10-03T115349916774 -> 2026-10-03T135702027001 | 1 changed | quiet |
| 2026-10-03 | `remote/com.dayze/life-context` | 2026-10-03T115349864825 -> 2026-10-03T135701661770 | 1 changed | quiet |
| 2026-10-03 | `remote/io.astrotune/jyotish-vedic-astrology` | 2026-10-01T063512504547 -> 2026-10-03T135701561716 | 1 changed | quiet |
| 2026-10-03 | `remote/com.thefilmradar/filmlab` | 2026-10-03T121105703573 -> 2026-10-03T135659655842 | 1 changed, 1 added | quiet |
| 2026-10-03 | `remote/com.uplika/uplika` | 2026-10-03T115246774162 -> 2026-10-03T135658226031 | 1 changed | quiet |
| 2026-10-03 | `remote/eu.sirenic/sirenic` | 2026-10-03T115248676966 -> 2026-10-03T135659599742 | 1 changed | quiet |
| 2026-10-03 | `remote/com.growvib/growvib` | 2026-10-03T114940873326 -> 2026-10-03T135657169997 | 2 added | quiet |
| 2026-10-03 | `remote/io.github.ABTdomain/domainkits-mcp` | 2026-10-03T114941605645 -> 2026-10-03T135655073686 | 2 changed | quiet |
| 2026-10-03 | `remote/io.github.0xinsider/mcp` | 2026-10-02T210059359599 -> 2026-10-03T135654745517 | 2 changed | quiet |
| 2026-10-03 | `remote/io.sslip.128.221.67.45.agent-exec/agent-exec` | 2026-10-02T070950466919 -> 2026-10-03T135654272000 | 5 added | quiet |
| 2026-10-03 | `remote/dev.workers.panda198271.agent-hub-tw/agent-hub` | 2026-10-03T114804233877 -> 2026-10-03T135652751592 | 12 changed, 29 added | quiet |
| 2026-10-03 | `remote/org.448c.agent-exec/agent-exec` | 2026-10-02T070956931794 -> 2026-10-03T135652745209 | 5 added | quiet |
| 2026-10-03 | `remote/com.a2a2p/a2a2p` | 2026-10-01T063507100414 -> 2026-10-03T135641454684 | 1 changed | quiet |
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

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 13783 substantive, 4786 that changed only numbers (a catalogue counter ticking, a date), 254 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 10160 | 5677 | 4483 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `caseyjhand.com` | 66 | 66 | 0 | 0 |
| `sistaminuten.se` | 63 | 2 | 0 | 61 |
| `afbudsrejser.dk` | 62 | 2 | 0 | 60 |
| `akkilahdot.fi` | 62 | 2 | 0 | 60 |
| `restplass.no` | 62 | 2 | 0 | 60 |
| `socialloop.ai` | 61 | 61 | 0 | 0 |
| `dayze.com` | 57 | 57 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| 1974 other operators | 5317 | 5001 | 303 | 13 |
