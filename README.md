# MCP server tool changes

Last change observed 2026-10-01T15:42:59+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

15907 changes to a tool definition: 459 npm releases (213 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 15448 readings of hosted servers that found their tools changed; 133 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-10-01 | `remote/no.restplass/travel-search` | 2026-10-01T134245687080 -> 2026-10-01T154301160024 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.tjcgraham-rgb/gaip-supplier-watch` | 2026-10-01T063528922075 -> 2026-10-01T154300207785 | 1 changed | quiet |
| 2026-10-01 | `remote/dk.afbudsrejser/travel-search` | 2026-10-01T134228629283 -> 2026-10-01T154257689954 | 1 changed | quiet |
| 2026-10-01 | `remote/se.sistaminuten/travel-search` | 2026-10-01T134440490890 -> 2026-10-01T154253810215 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.tjcgraham-rgb/gaip-trust-assurance` | 2026-10-01T063535486350 -> 2026-10-01T154254561587 | 1 changed, 1 added | quiet |
| 2026-10-01 | `remote/io.github.tjcgraham-rgb/gaip-integration-protocol` | 2026-10-01T134427203739 -> 2026-10-01T154253079659 | 1 changed | quiet |
| 2026-10-01 | `remote/com.straelo/relay` | 2026-09-29T210452743000 -> 2026-10-01T154249842433 | 1 added | quiet |
| 2026-10-01 | `remote/eu.madeinro/rotv-mcp` | 2026-10-01T134347159259 -> 2026-10-01T154248641200 | 2 changed | quiet |
| 2026-10-01 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-01T063531551066 -> 2026-10-01T154246290727 | 3 changed | quiet |
| 2026-10-01 | `remote/io.github.tjcgraham-rgb/gaip-witness` | 2026-10-01T063601523718 -> 2026-10-01T154247820184 | 3 changed, 1 added | quiet |
| 2026-10-01 | `remote/fi.akkilahdot/travel-search` | 2026-10-01T134611384714 -> 2026-10-01T154243695256 | 1 changed | quiet |
| 2026-10-01 | `remote/store.scvd/general-store` | 2026-09-29T073244070737 -> 2026-10-01T154242860200 | 1 changed | review |
| 2026-10-01 | `remote/com.peerpush/peerpush` | 2026-10-01T134127422500 -> 2026-10-01T154240490067 | 8 changed | quiet |
| 2026-10-01 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-01T134458638793 -> 2026-10-01T154238222280 | 1 changed | quiet |
| 2026-10-01 | `remote/com.midvash/bible` | 2026-10-01T133902413172 -> 2026-10-01T154237424581 | 3 changed | quiet |
| 2026-10-01 | `remote/io.github.tareq7/muslim-prayer-mcp` | 2026-10-01T134046567252 -> 2026-10-01T154236848434 | 5 changed (every tool) | quiet |
| 2026-10-01 | `remote/io.github.deviljin17/remode` | 2026-10-01T134424044554 -> 2026-10-01T154236005794 | 4 changed | quiet |
| 2026-10-01 | `remote/com.remoshift/jobs` | 2026-10-01T134424205402 -> 2026-10-01T154236741144 | 1 changed | quiet |
| 2026-10-01 | `remote/dev.uptimepage/uptimepage` | 2026-10-01T134111038680 -> 2026-10-01T154236875264 | 1 changed | quiet |
| 2026-10-01 | `remote/com.songstoyoureyes/catalog` | 2026-10-01T134052317235 -> 2026-10-01T154233235087 | 8 changed (every tool) | quiet |
| 2026-10-01 | `remote/io.ppc/postclick-landing-page-cro` | 2026-10-01T134232305666 -> 2026-10-01T154230368812 | 4 changed | quiet |
| 2026-10-01 | `remote/io.github.peter120525-cmd/lawmadi-os` | 2026-09-30T152227957406 -> 2026-10-01T154228874069 | 10 changed | quiet |
| 2026-10-01 | `remote/dev.genhttp/lambda` | 2026-10-01T133655311415 -> 2026-10-01T154227276997 | 1 changed | quiet |
| 2026-10-01 | `remote/com.kernelcad/kernelcad` | 2026-09-30T152219952881 -> 2026-10-01T154226895228 | 2 changed | quiet |
| 2026-10-01 | `remote/com.thisisdelightful/games-research-starter-pack` | 2026-10-01T063514524783 -> 2026-10-01T154226894735 | 2 changed | quiet |
| 2026-10-01 | `remote/ai.forkmate/forkmate` | 2026-10-01T063544921940 -> 2026-10-01T154223622543 | 9 changed, 2 added, 3 removed (every tool) | quiet |
| 2026-10-01 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-01T133515091286 -> 2026-10-01T154219882164 | 3 changed | quiet |
| 2026-10-01 | `remote/io.github.hermoso-ai/hermoso` | 2026-10-01T063510625211 -> 2026-10-01T154218438412 | 1 added | quiet |
| 2026-10-01 | `remote/com.dayze/life-context` | 2026-10-01T133439405371 -> 2026-10-01T154215573800 | 3 added | quiet |
| 2026-10-01 | `remote/io.github.WellApp-ai/well-mcp` | 2026-10-01T133320095944 -> 2026-10-01T154214126537 | 4 changed, 3 added, 1 removed | quiet |
| 2026-10-01 | `remote/eu.sirenic/sirenic` | 2026-09-30T210219756358 -> 2026-10-01T154216137474 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-10-01T133354598100 -> 2026-10-01T154211632657 | 1 changed | quiet |
| 2026-10-01 | `remote/directory.nohumans/registry` | 2026-09-30T210220774699 -> 2026-10-01T154210936271 | 1 changed | quiet |
| 2026-10-01 | `remote/com.uplika/uplika` | 2026-10-01T133330628496 -> 2026-10-01T154211020057 | 1 changed | quiet |
| 2026-10-01 | `remote/com.difficat/difficat` | 2026-09-30T152151729619 -> 2026-10-01T154210823835 | 4 changed | quiet |
| 2026-10-01 | `remote/io.github.stea4lth/flipvo-agent-tools` | 2026-09-30T210219777327 -> 2026-10-01T154209526709 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.0xinsider/mcp` | 2026-10-01T133028881021 -> 2026-10-01T154206705978 | 2 changed | quiet |
| 2026-10-01 | `remote/io.github.parkyucheol-del/alphapipeline` | 2026-09-29T072404886200 -> 2026-10-01T154206608483 | 1 added | quiet |
| 2026-10-01 | `remote/app.agentbit/mcp` | 2026-10-01T133018033805 -> 2026-10-01T154206336148 | 1 changed | quiet |
| 2026-10-01 | `remote/io.zerogex/gamma-levels` | 2026-09-24T120515618964 -> 2026-10-01T134654263120 | 1 changed | quiet |
| 2026-10-01 | `remote/io.usefulapi/zendesk` | 2026-09-23T163000894073 -> 2026-10-01T134653702472 | 19 changed (every tool) | quiet |
| 2026-10-01 | `remote/io.usefulapi/youcanbookme` | 2026-09-23T162959892546 -> 2026-10-01T134652203991 | 18 changed (every tool) | quiet |
| 2026-10-01 | `remote/com.theprotoclinical/commerce` | 2026-09-23T162955461681 -> 2026-10-01T134642572985 | 9 changed | quiet |
| 2026-10-01 | `remote/dev.primitive/email` | 2026-09-23T162950212453 -> 2026-10-01T134634223894 | 1 changed | quiet |
| 2026-10-01 | `remote/de.llms-txt-generator/llms-txt` | 2026-09-23T162947200866 -> 2026-10-01T134631213336 | 4 changed (every tool) | quiet |
| 2026-10-01 | `remote/com.hemmabo/hemmabo-mcp-server` | 2026-09-23T162943220796 -> 2026-10-01T134627219573 | 6 changed, 7 removed (every tool) | quiet |
| 2026-10-01 | `remote/io.github.tjcgraham-rgb/gaip-procurement-verify` | 2026-09-29T003621131326 -> 2026-10-01T134625774911 | 1 changed | quiet |
| 2026-10-01 | `remote/au.com.arthr/mcp` | 2026-09-23T162934319671 -> 2026-10-01T134612311067 | 4 changed | quiet |
| 2026-10-01 | `remote/fi.akkilahdot/travel-search` | 2026-10-01T063600069174 -> 2026-10-01T134611384714 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.kor-jongwon/witan` | 2026-10-01T063600299163 -> 2026-10-01T134606076932 | 1 changed, 7 added | quiet |
| 2026-10-01 | `remote/com.webmcp-tool/agent-readiness` | 2026-09-25T120559281147 -> 2026-10-01T134558470518 | 5 changed (every tool) | quiet |
| 2026-10-01 | `remote/com.waitingforpower/energy-permitting-tracker` | 2026-09-25T120553041841 -> 2026-10-01T134554141754 | 2 changed | quiet |
| 2026-10-01 | `remote/cloud.verifi/human-verification` | 2026-09-23T162923154497 -> 2026-10-01T134548562237 | 4 changed (every tool) | quiet |
| 2026-10-01 | `remote/ai.verticalmarketplace/vertical-marketplace` | 2026-09-27T070025686219 -> 2026-10-01T134548045774 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.sharan01x/usetested` | 2026-10-01T063557897392 -> 2026-10-01T134543976239 | 3 added | review |
| 2026-10-01 | `remote/io.github.helphub369/utility-matrix` | 2026-09-28T073150096147 -> 2026-10-01T134545068769 | 10 changed | quiet |
| 2026-10-01 | `remote/com.useslop/mcp` | 2026-09-27T055103448104 -> 2026-10-01T134544526880 | 1 changed, 1 added | quiet |
| 2026-10-01 | `remote/com.trip1/mcp` | 2026-09-28T104325846758 -> 2026-10-01T134534872728 | 4 changed, 2 added (every tool) | quiet |
| 2026-10-01 | `remote/io.github.Schoasch/backtesting-arena` | 2026-09-29T113434075189 -> 2026-10-01T134532878032 | 2 changed | quiet |
| 2026-10-01 | `remote/com.swarmmemo/bulletin` | 2026-10-01T063557344971 -> 2026-10-01T134514794832 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 12485 substantive, 3213 that changed only numbers (a catalogue counter ticking, a date), 209 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 8467 | 5492 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `caseyjhand.com` | 66 | 66 | 0 | 0 |
| `sistaminuten.se` | 52 | 2 | 0 | 50 |
| `afbudsrejser.dk` | 51 | 2 | 0 | 49 |
| `akkilahdot.fi` | 51 | 2 | 0 | 49 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| `restplass.no` | 51 | 2 | 0 | 49 |
| `socialloop.ai` | 51 | 51 | 0 | 0 |
| `dayze.com` | 43 | 43 | 0 | 0 |
| 1620 other operators | 4162 | 3912 | 238 | 12 |
