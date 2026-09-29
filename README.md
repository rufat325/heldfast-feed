# MCP server tool changes

Last change observed 2026-09-29T15:08:10+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

13271 changes to a tool definition: 384 npm releases (138 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 12887 readings of hosted servers that found their tools changed; 78 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-09-29 | `remote/fi.akkilahdot/travel-search` | 2026-09-29T131600819332 -> 2026-09-29T150811544614 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.kor-jongwon/witan` | 2026-09-29T101945632409 -> 2026-09-29T150812554117 | 1 added | quiet |
| 2026-09-29 | `remote/se.sistaminuten/travel-search` | 2026-09-29T131719853984 -> 2026-09-29T150808636873 | 1 changed | quiet |
| 2026-09-29 | `remote/no.restplass/travel-search` | 2026-09-29T131803368376 -> 2026-09-29T150804363604 | 1 changed | quiet |
| 2026-09-29 | `remote/com.autoridaddigital.www/geo` | 2026-09-28T142312559171 -> 2026-09-29T150804414015 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-29T131509507177 -> 2026-09-29T150802287087 | 1 changed | quiet |
| 2026-09-29 | `remote/page.ship/ship-page` | 2026-09-27T152813119058 -> 2026-09-29T150801655910 | 2 changed | quiet |
| 2026-09-29 | `remote/dk.afbudsrejser/travel-search` | 2026-09-29T131739584243 -> 2026-09-29T150801826519 | 1 changed | quiet |
| 2026-09-29 | `remote/com.seqbench/workbench` | 2026-09-29T131458791967 -> 2026-09-29T150800476128 | 1 changed | quiet |
| 2026-09-29 | `remote/com.underpricedai/underpriced-ai` | 2026-09-28T170347490273 -> 2026-09-29T150758942825 | 1 changed | quiet |
| 2026-09-29 | `remote/com.remoshift/jobs` | 2026-09-29T131439668408 -> 2026-09-29T150755960450 | 1 changed | quiet |
| 2026-09-29 | `remote/com.nessgate/nessgate` | 2026-09-29T103748654553 -> 2026-09-29T150749133288 | 2 changed | quiet |
| 2026-09-29 | `remote/org.nsgoods/nsgoods-workbench-mcp` | 2026-09-27T141919879443 -> 2026-09-29T150741750013 | 3 changed | quiet |
| 2026-09-29 | `remote/com.shotpulled/shotpulled` | 2026-09-28T104000325503 -> 2026-09-29T150738628104 | 12 changed | quiet |
| 2026-09-29 | `remote/com.gojinko.mcp/jinko` | 2026-09-29T003552749962 -> 2026-09-29T150736543531 | 2 changed | quiet |
| 2026-09-29 | `remote/io.github.Perufitlife/postwire-mcp` | 2026-09-28T142125557153 -> 2026-09-29T150733545168 | 2 changed | quiet |
| 2026-09-29 | `remote/com.pontofato/pontofato` | 2026-09-29T061625324944 -> 2026-09-29T150733194483 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.cammac-creator/openswissdata` | 2026-09-28T170326553118 -> 2026-09-29T150731428913 | 3 added | quiet |
| 2026-09-29 | `remote/md.mostlyright/datasets` | 2026-09-29T131359553459 -> 2026-09-29T150728118118 | 2 changed | quiet |
| 2026-09-29 | `remote/io.insourcia/insourcia` | 2026-09-29T113107916818 -> 2026-09-29T150729134426 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.leanrads/leanriq` | 2026-09-28T103812863519 -> 2026-09-29T150728507542 | 12 added | quiet |
| 2026-09-29 | `remote/com.avokata/avokata` | 2026-09-29T131225747898 -> 2026-09-29T150729162357 | 2 changed | quiet |
| 2026-09-29 | `remote/com.vertodigital/mcp` | 2026-09-29T103535528348 -> 2026-09-29T150725924521 | 1 changed | quiet |
| 2026-09-29 | `remote/com.datailo/datailo` | 2026-09-27T120505620402 -> 2026-09-29T150726505549 | 1 changed | quiet |
| 2026-09-29 | `remote/de.marjanmarkelj/saxsoc-public-info` | 2026-09-28T141739481189 -> 2026-09-29T150725855163 | 3 changed, 1 added, 4 removed (every tool) | quiet |
| 2026-09-29 | `remote/ai.sacs/sacs-mcp` | 2026-09-28T141939134010 -> 2026-09-29T150722825701 | 1 changed, 1 added | quiet |
| 2026-09-29 | `remote/net.isitdns/isitdns` | 2026-09-29T131028187375 -> 2026-09-29T150719125719 | 7 changed (every tool) | quiet |
| 2026-09-29 | `remote/com.cymetica/event-trader-mcp` | 2026-09-29T130825970882 -> 2026-09-29T150717979915 | 2 changed, 6 added | quiet |
| 2026-09-29 | `remote/io.github.jgaethle10/findmypart` | 2026-09-28T141545825484 -> 2026-09-29T150716373141 | 1 changed, 1 added | quiet |
| 2026-09-29 | `remote/com.compensationprofessional/discovery` | 2026-09-29T130814330612 -> 2026-09-29T150716067197 | 2 changed | quiet |
| 2026-09-29 | `remote/io.github.tettertotter/fundinglandscape` | 2026-09-29T130912588951 -> 2026-09-29T150716857603 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.tradewr333-lgtm/degenscan-intel` | 2026-09-28T170306908877 -> 2026-09-29T150713474748 | 4 added | quiet |
| 2026-09-29 | `remote/io.github.kylehawke-stack/locationlists` | 2026-09-29T131118097731 -> 2026-09-29T150714061873 | 9 changed | quiet |
| 2026-09-29 | `remote/com.cymetica/event-trader-research` | 2026-09-29T130854900369 -> 2026-09-29T150714043674 | 2 changed, 4 added | quiet |
| 2026-09-29 | `remote/io.github.troothllc/trooth-network` | 2026-09-28T141309563686 -> 2026-09-29T150710611232 | 4 changed (every tool) | quiet |
| 2026-09-29 | `remote/com.dayze/life-context.1` | 2026-09-29T061614003235 -> 2026-09-29T150710349576 | 2 changed | quiet |
| 2026-09-29 | `remote/com.dayze/life-context` | 2026-09-29T061613916767 -> 2026-09-29T150711087609 | 2 changed | quiet |
| 2026-09-29 | `remote/io.github.jgaethle10/evercraft-clip` | 2026-09-29T003547247885 -> 2026-09-29T150708786900 | 1 added | quiet |
| 2026-09-29 | `remote/app.flaim/mcp` | 2026-09-29T003527652144 -> 2026-09-29T150701416601 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.belegante-byte/aetherx-mcp` | 2026-09-29T112310726619 -> 2026-09-29T150700028727 | 1 added | quiet |
| 2026-09-29 | `remote/io.github.Avi-ADAM/1lev1` | 2026-09-29T072408243552 -> 2026-09-29T150700324217 | 2 changed | quiet |
| 2026-09-29 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-09-28T170307631436 -> 2026-09-29T150659455833 | 2 changed | quiet |
| 2026-09-29 | `remote/dev.protogrid/registry` | 2026-09-28T170308456445 -> 2026-09-29T150657799624 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.stea4lth/flipvo-agent-tools` | 2026-09-28T141030109425 -> 2026-09-29T150657007014 | 2 changed, 1 added | review |
| 2026-09-29 | `remote/xyz.apexfaucet/apex-x1` | 2026-09-29T061603191042 -> 2026-09-29T150657676638 | 1 added | quiet |
| 2026-09-29 | `remote/xyz.apexfaucet/apex-arc` | 2026-09-28T141012543468 -> 2026-09-29T150656809355 | 1 added | quiet |
| 2026-09-29 | `remote/io.github.TWolf01/agentsgather` | 2026-09-29T130338484008 -> 2026-09-29T150657435706 | 19 changed, 2 added | quiet |
| 2026-09-29 | `remote/io.github.faisal-maverick/aayat-ai` | 2026-09-29T130236758591 -> 2026-09-29T150654877896 | 13 changed | quiet |
| 2026-09-29 | `remote/no.restplass/travel-search` | 2026-09-29T113446824575 -> 2026-09-29T131803368376 | 1 changed | quiet |
| 2026-09-29 | `remote/com.youspot/youspot` | 2026-09-29T061642095763 -> 2026-09-29T131739702093 | 1 changed | quiet |
| 2026-09-29 | `remote/dk.afbudsrejser/travel-search` | 2026-09-29T113428746182 -> 2026-09-29T131739584243 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.Fizzl13/x402-doctor` | 2026-09-28T170424616410 -> 2026-09-29T131734183659 | 2 added | review |
| 2026-09-29 | `remote/com.zernote/zernote` | 2026-09-23T161046153713 -> 2026-09-29T131732134286 | 3 added | quiet |
| 2026-09-29 | `remote/com.zaimhub/catalog` | 2026-09-23T161045544767 -> 2026-09-29T131732362389 | 1 changed | quiet |
| 2026-09-29 | `remote/se.sistaminuten/travel-search` | 2026-09-29T113551744770 -> 2026-09-29T131719853984 | 1 changed | quiet |
| 2026-09-29 | `remote/dog.swoleeswoge/swogeagentic` | 2026-09-29T061658505250 -> 2026-09-29T131640395061 | 1 changed | quiet |
| 2026-09-29 | `remote/ru.zavod-stanki/cnc-catalog` | 2026-09-24T202805671044 -> 2026-09-29T131633404521 | 1 changed | quiet |
| 2026-09-29 | `remote/ru.zavod-stanki/cnc-catalog.1` | 2026-09-24T202530104515 -> 2026-09-29T131625624730 | 1 changed | quiet |
| 2026-09-29 | `remote/cc.thecolony/mcp-server` | 2026-09-27T195348518701 -> 2026-09-29T131612193027 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.Lorenzino69/easypdf` | 2026-09-23T162939147170 -> 2026-09-29T131608407530 | 1 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 9931 substantive, 3163 that changed only numbers (a catalogue counter ticking, a date), 177 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 7023 | 4048 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `caseyjhand.com` | 56 | 56 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| `sistaminuten.se` | 45 | 2 | 0 | 43 |
| `afbudsrejser.dk` | 44 | 2 | 0 | 42 |
| `akkilahdot.fi` | 44 | 2 | 0 | 42 |
| `restplass.no` | 44 | 2 | 0 | 42 |
| `socialloop.ai` | 44 | 44 | 0 | 0 |
| `dayze.com` | 30 | 30 | 0 | 0 |
| `fastmcp.app` | 29 | 29 | 0 | 0 |
| 1293 other operators | 3096 | 2900 | 188 | 8 |
