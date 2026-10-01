# MCP server tool changes

Last change observed 2026-10-01T13:46:53+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

15868 changes to a tool definition: 459 npm releases (213 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 15409 readings of hosted servers that found their tools changed; 132 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
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
| 2026-10-01 | `remote/io.usefulapi/stream` | 2026-09-23T162858825360 -> 2026-10-01T134509731902 | 13 changed (every tool) | quiet |
| 2026-10-01 | `remote/io.usefulapi/statuspal` | 2026-09-23T162857376208 -> 2026-10-01T134506629974 | 11 changed (every tool) | quiet |
| 2026-10-01 | `remote/io.github.JacobiusMakes/stienhardt-store` | 2026-09-23T162857734149 -> 2026-10-01T134506492611 | 9 changed | quiet |
| 2026-10-01 | `remote/app.sallim/korea-stay` | 2026-09-26T045514429637 -> 2026-10-01T134508313421 | 1 changed | quiet |
| 2026-10-01 | `remote/io.usefulapi/spikesh` | 2026-09-23T162855893517 -> 2026-10-01T134503970036 | 16 changed (every tool) | quiet |
| 2026-10-01 | `remote/io.usefulapi/speechmatics` | 2026-09-23T162855827367 -> 2026-10-01T134503383482 | 7 changed (every tool) | quiet |
| 2026-10-01 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-01T063555893374 -> 2026-10-01T134458638793 | 4 changed, 3 added | quiet |
| 2026-10-01 | `remote/xn--3ds443g.xn--s7y/duan-online` | 2026-09-30T210307530159 -> 2026-10-01T134451005411 | 10 changed (every tool) | quiet |
| 2026-10-01 | `remote/io.usefulapi/sendgrid` | 2026-09-23T162844349273 -> 2026-10-01T134443774971 | 11 changed (every tool) | quiet |
| 2026-10-01 | `remote/se.sistaminuten/travel-search` | 2026-10-01T063537939463 -> 2026-10-01T134440490890 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.michal-lefler/secureflows-mcp` | 2026-09-23T161035206065 -> 2026-10-01T134440613859 | 2 changed | quiet |
| 2026-10-01 | `remote/com.searchfragments/search-fragments` | 2026-09-29T210506999726 -> 2026-10-01T134441369113 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.causa-prima-ai/scribo` | 2026-09-23T162842141548 -> 2026-10-01T134439500187 | 1 changed | quiet |
| 2026-10-01 | `remote/io.usefulapi/scalingo` | 2026-09-23T162840543104 -> 2026-10-01T134436865741 | 21 changed (every tool) | quiet |
| 2026-10-01 | `remote/com.ponito/product-intelligence` | 2026-09-23T161033438063 -> 2026-10-01T134437167438 | 2 changed | quiet |
| 2026-10-01 | `remote/io.github.girapphe/memostem` | 2026-09-23T161032696394 -> 2026-10-01T134434787914 | 10 changed (every tool) | quiet |
| 2026-10-01 | `remote/io.github.maxschnee74-source/alpinelead` | 2026-09-23T160901875138 -> 2026-10-01T134429446877 | 1 added | quiet |
| 2026-10-01 | `remote/com.zeroacquire/zeroacquire` | 2026-09-23T160901909053 -> 2026-10-01T134429312504 | 2 added | quiet |
| 2026-10-01 | `remote/io.github.gparientee/gp-intel` | 2026-09-23T161027092887 -> 2026-10-01T134426974859 | 5 changed | quiet |
| 2026-10-01 | `remote/io.github.tjcgraham-rgb/gaip-outcome-value` | 2026-09-29T003625993257 -> 2026-10-01T134427779338 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.tjcgraham-rgb/gaip-integration-protocol` | 2026-09-29T003625404627 -> 2026-10-01T134427203739 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.tjcgraham-rgb/gaip-art-intelligence` | 2026-09-29T003625482687 -> 2026-10-01T134427236582 | 1 changed | quiet |
| 2026-10-01 | `remote/io.github.deviljin17/remode` | 2026-09-26T192555315501 -> 2026-10-01T134424044554 | 1 changed | quiet |
| 2026-10-01 | `remote/com.remoshift/jobs` | 2026-10-01T063553594085 -> 2026-10-01T134424205402 | 1 changed | quiet |
| 2026-10-01 | `remote/dev.desvela/registry` | 2026-09-23T162832926303 -> 2026-10-01T134423484727 | 1 changed | quiet |
| 2026-10-01 | `remote/com.followontours/cricket-travel` | 2026-09-26T045433476471 -> 2026-10-01T134424190713 | 2 changed, 1 added | quiet |
| 2026-10-01 | `remote/io.github.kwizzlesurp10-ctrl/x402-mcp` | 2026-09-23T160858778647 -> 2026-10-01T134422827300 | 1 added | quiet |
| 2026-10-01 | `remote/com.recipebooq/recipebooq` | 2026-09-26T231113588721 -> 2026-10-01T134421026496 | 8 changed, 3 added, 6 removed (every tool) | quiet |
| 2026-10-01 | `remote/io.usefulapi/raisely` | 2026-09-23T162829347069 -> 2026-10-01T134419484899 | 23 changed (every tool) | quiet |
| 2026-10-01 | `remote/com.radar-cnpj/radar-cnpj` | 2026-10-01T063554292821 -> 2026-10-01T134418797572 | 1 changed | quiet |
| 2026-10-01 | `remote/com.autoridaddigital.www/geo` | 2026-09-29T150804414015 -> 2026-10-01T134417184386 | 2 changed | quiet |
| 2026-10-01 | `remote/io.github.KilianPA/pryx` | 2026-09-28T142447317868 -> 2026-10-01T134412843726 | 2 changed, 1 added (every tool) | quiet |
| 2026-10-01 | `remote/io.github.michal-lefler/secure-flows` | 2026-09-23T160851683743 -> 2026-10-01T134411561545 | 2 changed | quiet |
| 2026-10-01 | `remote/help.servicebuddy/mcp` | 2026-09-23T160851877707 -> 2026-10-01T134411116928 | 1 added | quiet |
| 2026-10-01 | `remote/app.shotlee/shotlee` | 2026-09-27T153456974512 -> 2026-10-01T134411499045 | 2 changed | quiet |
| 2026-10-01 | `remote/com.resollo/agent-api` | 2026-09-23T160851265174 -> 2026-10-01T134410201622 | 3 changed | quiet |
| 2026-10-01 | `remote/app.roamward/roamward-mcp` | 2026-09-23T160850990056 -> 2026-10-01T134410634994 | 4 changed (every tool) | quiet |
| 2026-10-01 | `remote/com.predictionmarketspicks/weather` | 2026-09-23T162822938188 -> 2026-10-01T134407801477 | 6 changed (every tool) | quiet |
| 2026-10-01 | `remote/io.github.falsalama/proper-job` | 2026-09-24T120445120646 -> 2026-10-01T134406686747 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 12453 substantive, 3211 that changed only numbers (a catalogue counter ticking, a date), 204 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 8467 | 5492 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `caseyjhand.com` | 66 | 66 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| `sistaminuten.se` | 51 | 2 | 0 | 49 |
| `afbudsrejser.dk` | 50 | 2 | 0 | 48 |
| `akkilahdot.fi` | 50 | 2 | 0 | 48 |
| `restplass.no` | 50 | 2 | 0 | 48 |
| `socialloop.ai` | 50 | 50 | 0 | 0 |
| `dayze.com` | 42 | 42 | 0 | 0 |
| 1620 other operators | 4129 | 3882 | 236 | 11 |
