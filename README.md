# MCP server tool changes

Last change observed 2026-10-01T06:36:00+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

13821 changes to a tool definition: 384 npm releases (138 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 13437 readings of hosted servers that found their tools changed; 103 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-10-01 | `remote/io.github.tjcgraham-rgb/gaip-witness` | 2026-09-29T003621494940 -> 2026-10-01T063601523718 | 2 changed | quiet |
| 2026-10-01 | `remote/io.github.tjcgraham-rgb/gaip-integration-repair` | 2026-09-29T003620519402 -> 2026-10-01T063601350729 | 1 changed | quiet |
| 2026-10-01 | `remote/fi.akkilahdot/travel-search` | 2026-09-30T210256388300 -> 2026-10-01T063600069174 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.kor-jongwon/witan` | 2026-09-30T152248926741 -> 2026-10-01T063600299163 | 4 changed | quiet |
| 2026-10-01 | `remote/io.github.sharan01x/usetested` | 2026-09-30T152245933217 -> 2026-10-01T063557897392 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-30T210249859658 -> 2026-10-01T063555893374 | 1 changed, 2 added | quiet |
| 2026-10-01 | `remote/io.github.IO31-WEB/synapse-lounge` | 2026-09-29T003614578455 -> 2026-10-01T063556515606 | 1 changed | quiet |
| 2026-10-01 | `remote/com.synapticrelay/board.1` | 2026-09-29T003613422463 -> 2026-10-01T063556975690 | 1 changed | quiet |
| 2026-10-01 | `remote/com.swarmmemo/bulletin` | 2026-09-30T060127828325 -> 2026-10-01T063557344971 | 27 changed, 15 added (every tool) | quiet |
| 2026-10-01 | `remote/com.remoshift/jobs` | 2026-09-30T210245345218 -> 2026-10-01T063553594085 | 1 changed | quiet |
| 2026-10-01 | `remote/com.radar-cnpj/radar-cnpj` | 2026-09-30T210245815211 -> 2026-10-01T063554292821 | 3 changed | quiet |
| 2026-10-01 | `remote/com.multicinesortega/cartelera` | 2026-09-30T210240964747 -> 2026-10-01T063553595700 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.neus/neus-mcp` | 2026-09-29T073407071123 -> 2026-10-01T063550679405 | 9 removed | quiet |
| 2026-10-01 | `remote/io.github.magichourhq/magic-hour` | 2026-09-30T060109300954 -> 2026-10-01T063550624736 | 23 changed, 2 removed | quiet |
| 2026-10-01 | `remote/com.jojapi/swift-ai` | 2026-09-30T060108616514 -> 2026-10-01T063549936493 | 1 changed | quiet |
| 2026-10-01 | `remote/ai.forkmate/forkmate` | 2026-09-30T060105144599 -> 2026-10-01T063544921940 | 5 changed | quiet |
| 2026-10-01 | `remote/se.sistaminuten/travel-search` | 2026-09-30T210307431548 -> 2026-10-01T063537939463 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.tjcgraham-rgb/gaip-buyer-assurance` | 2026-09-29T003625091072 -> 2026-10-01T063536468198 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.tjcgraham-rgb/gaip-broker` | 2026-09-30T060137121350 -> 2026-10-01T063536656185 | 4 changed (every tool) | quiet |
| 2026-10-01 | `remote/com.youspot/youspot` | 2026-09-29T210523236133 -> 2026-10-01T063535958502 | 2 added | quiet |
| 2026-10-01 | `remote/io.github.tjcgraham-rgb/gaip-trust-assurance` | 2026-09-29T003618890475 -> 2026-10-01T063535486350 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.LE-VAI/designesy-org` | 2026-09-29T073239828146 -> 2026-10-01T063534645930 | 1 changed | quiet |
| 2026-10-01 | `remote/fun.lesgooo/lesgooo` | 2026-09-30T210229546350 -> 2026-10-01T063536122319 | 17 changed | quiet |
| 2026-10-01 | `remote/io.github.si-imtiaz/leadquasar` | 2026-09-30T210229557330 -> 2026-10-01T063537322792 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.kaminariouji/x402-audit-agent` | 2026-09-29T003549252157 -> 2026-10-01T063539464991 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.SKalinin909/tradingcalc` | 2026-09-30T152242557065 -> 2026-10-01T063539112627 | 2 changed | quiet |
| 2026-10-01 | `remote/com.thenewengineer/hvac` | 2026-09-29T210511736354 -> 2026-10-01T063533557407 | 2 added | quiet |
| 2026-10-01 | `remote/net.hotelrefund/price-tracker` | 2026-09-30T060057819972 -> 2026-10-01T063534446755 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-09-30T210254082425 -> 2026-10-01T063531551066 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.jamie7893/keelen` | 2026-09-30T060100084890 -> 2026-10-01T063534946472 | 1 changed | quiet |
| 2026-10-01 | `remote/com.thefomite/fomite` | 2026-09-30T060128257073 -> 2026-10-01T063531837946 | 1 changed | quiet |
| 2026-10-01 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-09-30T060141576023 -> 2026-10-01T063532257358 | 1 changed | quiet |
| 2026-10-01 | `remote/io.taifoon/coordination-layer` | 2026-09-30T152326050483 -> 2026-10-01T063528641783 | 1 changed | quiet |
| 2026-10-01 | `remote/no.restplass/travel-search` | 2026-09-30T210258971180 -> 2026-10-01T063528452391 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.tjcgraham-rgb/gaip-supplier-watch` | 2026-09-29T003627163795 -> 2026-10-01T063528922075 | 1 changed | quiet |
| 2026-10-01 | `remote/com.primecutsnursery/public-data` | 2026-09-30T210257788857 -> 2026-10-01T063528088221 | 1 changed | quiet |
| 2026-10-01 | `remote/ca.maplev/tesla-collision-parts` | 2026-09-29T073220512048 -> 2026-10-01T063531079150 | 1 changed | quiet |
| 2026-10-01 | `remote/dk.afbudsrejser/travel-search` | 2026-09-30T210255803670 -> 2026-10-01T063527567132 | 1 changed | quiet |
| 2026-10-01 | `remote/com.pontofato/pontofato` | 2026-09-30T210248965884 -> 2026-10-01T063528857075 | 1 changed | quiet |
| 2026-10-01 | `remote/ai.wem3/wem-price-compare` | 2026-09-30T210255833820 -> 2026-10-01T063527398083 | 2 changed | quiet |
| 2026-10-01 | `remote/io.github.simonplmak-cloud/vision-driven-design` | 2026-09-30T152315326297 -> 2026-10-01T063526359563 | 15 changed (every tool) | quiet |
| 2026-10-01 | `remote/io.github.lbailey94/whitemagic-mcp` | 2026-09-30T152218616634 -> 2026-10-01T063525574847 | 6 changed | quiet |
| 2026-10-01 | `remote/dev.mcphost/mcphost` | 2026-09-30T210245124672 -> 2026-10-01T063526623272 | 1 changed, 5 added | quiet |
| 2026-10-01 | `remote/com.meettempi/tempi` | 2026-09-30T210242972512 -> 2026-10-01T063526008883 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-09-30T210251193118 -> 2026-10-01T063523458208 | 15 changed | review |
| 2026-10-01 | `remote/ai.metabind/banking-assistant` | 2026-09-30T060104007071 -> 2026-10-01T063524345942 | 9 changed (every tool) | quiet |
| 2026-10-01 | `remote/io.soundchecklive/live-event-quotes` | 2026-09-29T210447257313 -> 2026-10-01T063523755496 | 16 changed (every tool) | quiet |
| 2026-10-01 | `remote/io.github.proofable/mcp` | 2026-09-29T072846562354 -> 2026-10-01T063522687747 | 9 removed | quiet |
| 2026-10-01 | `remote/io.github.Kindora-PBC/foundation-discovery` | 2026-09-29T073000061750 -> 2026-10-01T063523144744 | 1 changed | quiet |
| 2026-10-01 | `remote/ai.rokha/rokha` | 2026-09-29T210454828222 -> 2026-10-01T063523542295 | 4 added | quiet |
| 2026-10-01 | `remote/io.github.pipeworx-io/nasa-ads` | 2026-09-29T073025045288 -> 2026-10-01T063525971573 | 5 changed | quiet |
| 2026-10-01 | `remote/com.qumge/skills` | 2026-09-30T152302197311 -> 2026-10-01T063522286984 | 1 changed, 1 added | quiet |
| 2026-10-01 | `remote/io.github.pipeworx-io/gprofiler` | 2026-09-29T073008200348 -> 2026-10-01T063525757607 | 5 changed | quiet |
| 2026-10-01 | `remote/io.github.pipeworx-io/fca-shorts` | 2026-09-29T072949836319 -> 2026-10-01T063525866631 | 5 changed | quiet |
| 2026-10-01 | `remote/io.github.Project-Gifted1/pg1-threat-intel` | 2026-09-30T210244254736 -> 2026-10-01T063521563711 | 4 changed | quiet |
| 2026-10-01 | `remote/com.jojapi/product-barcode-api` | 2026-09-30T060125304159 -> 2026-10-01T063522027816 | 2 changed | quiet |
| 2026-10-01 | `remote/io.github.pipeworx-io/dropbox` | 2026-09-29T072943779986 -> 2026-10-01T063528831571 | 5 changed | quiet |
| 2026-10-01 | `remote/io.github.proplineapi/propline-mcp` | 2026-09-30T210238464151 -> 2026-10-01T063518786858 | 2 changed | quiet |
| 2026-10-01 | `remote/ai.skillsinput/mcp` | 2026-09-30T060122835618 -> 2026-10-01T063519393068 | 1 changed | quiet |
| 2026-10-01 | `remote/io.orbitwan/orbitwan` | 2026-09-30T152241234159 -> 2026-10-01T063519548057 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 10424 substantive, 3197 that changed only numbers (a catalogue counter ticking, a date), 200 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 7032 | 4057 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `caseyjhand.com` | 56 | 56 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| `sistaminuten.se` | 50 | 2 | 0 | 48 |
| `afbudsrejser.dk` | 49 | 2 | 0 | 47 |
| `akkilahdot.fi` | 49 | 2 | 0 | 47 |
| `restplass.no` | 49 | 2 | 0 | 47 |
| `socialloop.ai` | 49 | 49 | 0 | 0 |
| `fastmcp.app` | 41 | 41 | 0 | 0 |
| `dayze.com` | 40 | 40 | 0 | 0 |
| 1353 other operators | 3590 | 3357 | 222 | 11 |
