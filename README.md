# MCP server tool changes

Last change observed 2026-09-28T14:26:28+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

12567 changes to a tool definition: 370 npm releases (124 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 12197 readings of hosted servers that found their tools changed; 45 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-09-28 | `remote/io.github.aanari/loacare-healthcare-pricing` | 2026-09-24T202756592350 -> 2026-09-28T142630046367 | 3 changed | quiet |
| 2026-09-28 | `remote/fi.akkilahdot/travel-search` | 2026-09-28T104349552972 -> 2026-09-28T142614151978 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.nicoletterankin/orb-platform` | 2026-09-23T162734158073 -> 2026-09-28T142612053403 | 13 changed, 1 added (every tool) | quiet |
| 2026-09-28 | `remote/com.tablejourney/food-travel` | 2026-09-23T162903216784 -> 2026-09-28T142541866419 | 10 changed (every tool) | quiet |
| 2026-09-28 | `remote/io.github.IO31-WEB/synapse-lounge` | 2026-09-25T120533526844 -> 2026-09-28T142542887807 | 61 changed | quiet |
| 2026-09-28 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-28T104255115525 -> 2026-09-28T142527460954 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.bartosz-kuc/skanfirmy` | 2026-09-27T105328061676 -> 2026-09-28T142521870470 | 3 changed | quiet |
| 2026-09-28 | `remote/com.searchfragments/search-fragments` | 2026-09-25T120514033230 -> 2026-09-28T142510933823 | 1 changed | quiet |
| 2026-09-28 | `remote/com.remoshift/jobs` | 2026-09-28T104227368670 -> 2026-09-28T142455431031 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.maixmeduret/pillr` | 2026-09-24T120343075509 -> 2026-09-28T142435843174 | 1 changed | quiet |
| 2026-09-28 | `remote/com.youspot/youspot` | 2026-09-28T073244893888 -> 2026-09-28T142417167778 | 4 changed, 3 added | quiet |
| 2026-09-28 | `remote/com.neblla/neblla` | 2026-09-23T162756609069 -> 2026-09-28T142409271503 | 2 changed, 3 added | quiet |
| 2026-09-28 | `remote/com.multicinesortega/cartelera` | 2026-09-27T232558451957 -> 2026-09-28T142407355463 | 1 changed | quiet |
| 2026-09-28 | `remote/se.sistaminuten/travel-search` | 2026-09-28T104352121709 -> 2026-09-28T142335306572 | 1 changed | quiet |
| 2026-09-28 | `remote/world.agentindex/x402` | 2026-09-28T104302021100 -> 2026-09-28T142333019050 | 1 added | quiet |
| 2026-09-28 | `remote/com.shipstatic/mcp` | 2026-09-27T065812549187 -> 2026-09-28T142329433120 | 1 changed | quiet |
| 2026-09-28 | `remote/no.restplass/travel-search` | 2026-09-28T104249419868 -> 2026-09-28T142319948565 | 1 changed | quiet |
| 2026-09-28 | `remote/com.contrie/contrie` | 2026-09-25T120556092447 -> 2026-09-28T142315953673 | 1 changed | quiet |
| 2026-09-28 | `remote/com.autoridaddigital.www/geo` | 2026-09-28T104333448101 -> 2026-09-28T142312559171 | 5 changed (every tool) | quiet |
| 2026-09-28 | `remote/com.ugcpocket/ugc-pocket` | 2026-09-28T073137777722 -> 2026-09-28T142305890425 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.CodePhantom-1/ddmarketer-mcp` | 2026-09-28T104236003034 -> 2026-09-28T142304611507 | 4 changed (every tool) | quiet |
| 2026-09-28 | `remote/dk.afbudsrejser/travel-search` | 2026-09-28T104231553151 -> 2026-09-28T142258546949 | 1 changed | quiet |
| 2026-09-28 | `remote/com.cordering/whitelabel-ordering` | 2026-09-23T163115331816 -> 2026-09-28T142256193949 | 10 changed (every tool) | quiet |
| 2026-09-28 | `remote/ai.wem3/wem-price-compare` | 2026-09-28T073146550875 -> 2026-09-28T142252785998 | 4 changed | quiet |
| 2026-09-28 | `remote/com.suomiatlas/area-statistics` | 2026-09-25T120424127778 -> 2026-09-28T142234826475 | 1 changed | quiet |
| 2026-09-28 | `remote/com.tradeassi/mcp` | 2026-09-27T065940439447 -> 2026-09-28T142231046185 | 1 changed | quiet |
| 2026-09-28 | `remote/nl.sportpoeder/agent` | 2026-09-23T160802198135 -> 2026-09-28T142234449289 | 3 added | quiet |
| 2026-09-28 | `remote/ai.ssid/ssid-mcp` | 2026-09-23T160942556751 -> 2026-09-28T142211813171 | 1 changed | review |
| 2026-09-28 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-09-28T104151126776 -> 2026-09-28T142200652306 | 15 changed | review |
| 2026-09-28 | `remote/com.rightaichoice/mcp` | 2026-09-23T160733408454 -> 2026-09-28T142149499307 | 1 added | quiet |
| 2026-09-28 | `remote/pro.aicut/aicut` | 2026-09-23T162611147561 -> 2026-09-28T142144781509 | 2 changed | quiet |
| 2026-09-28 | `remote/io.github.89rat/code402` | 2026-09-23T160523819727 -> 2026-09-28T142138817006 | 1 changed, 11 added, 7 removed | quiet |
| 2026-09-28 | `remote/com.smklog/parcel-shipping-rates` | 2026-09-28T073027205562 -> 2026-09-28T142137482382 | 2 changed | quiet |
| 2026-09-28 | `remote/com.plainrouter/mcp` | 2026-09-28T055518419566 -> 2026-09-28T142120896171 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.kaminariouji/x402-audit-agent` | 2026-09-25T120226908304 -> 2026-09-28T142116539859 | 5 added | quiet |
| 2026-09-28 | `remote/io.github.kleaphq/kleap` | 2026-09-25T120223779858 -> 2026-09-28T142111482964 | 1 changed | quiet |
| 2026-09-28 | `remote/app.sallim/korea-realty` | 2026-09-28T055529782603 -> 2026-09-28T142111070907 | 1 changed | quiet |
| 2026-09-28 | `remote/com.organikpi/organikpi` | 2026-09-23T160706386941 -> 2026-09-28T142105014795 | 1 changed, 1 added, 1 removed | quiet |
| 2026-09-28 | `remote/com.printinglabs/printing-labs` | 2026-09-23T162924159209 -> 2026-09-28T142101936362 | 2 changed | quiet |
| 2026-09-28 | `remote/com.ogstamp/og` | 2026-09-23T160701497174 -> 2026-09-28T142057786975 | 2 changed | quiet |
| 2026-09-28 | `remote/io.github.moralito311-andr/andreax` | 2026-09-28T104141766865 -> 2026-09-28T142058496152 | 3 added | quiet |
| 2026-09-28 | `remote/com.overlap-ai/overlap` | 2026-09-23T160858673298 -> 2026-09-28T142104420289 | 7 changed (every tool) | quiet |
| 2026-09-28 | `remote/io.github.YugantM/hvtracker-mcp` | 2026-09-23T162532403254 -> 2026-09-28T142053577657 | 4 changed | quiet |
| 2026-09-28 | `remote/com.sanbernardorefugio/refugio-san-bernardo` | 2026-09-28T103756770163 -> 2026-09-28T142044423109 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.lbailey94/whitemagic-mcp` | 2026-09-25T120307636755 -> 2026-09-28T142012434233 | 3 changed | quiet |
| 2026-09-28 | `remote/com.zylalabs/api-hub` | 2026-09-23T160823886236 -> 2026-09-28T142011685032 | 1 changed | quiet |
| 2026-09-28 | `remote/com.thecrowdspace/crowdspace` | 2026-09-28T103945478145 -> 2026-09-28T141955200295 | 2 changed | quiet |
| 2026-09-28 | `remote/io.github.AndreiDrang/tokenbel-mcp` | 2026-09-23T160801630013 -> 2026-09-28T141938171593 | 19 changed (every tool) | review |
| 2026-09-28 | `remote/app.quantcalc/retirement-engine` | 2026-09-23T162757815467 -> 2026-09-28T141927672800 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.yzlee/opcmenu` | 2026-09-26T192545105801 -> 2026-09-28T141919947029 | 5 changed, 19 added | quiet |
| 2026-09-28 | `remote/co.lovie/company-formation` | 2026-09-23T162726393776 -> 2026-09-28T141858770290 | 25 changed, 2 added | quiet |
| 2026-09-28 | `remote/com.metricduck/financial-analysis` | 2026-09-27T055043289873 -> 2026-09-28T141841257041 | 2 changed | quiet |
| 2026-09-28 | `remote/travel.kismet/mcp-server` | 2026-09-23T160723774290 -> 2026-09-28T141834258948 | 2 added | quiet |
| 2026-09-28 | `remote/io.github.CoinRithm/mcp-trading` | 2026-09-28T072810733185 -> 2026-09-28T141830328699 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.danafitkowski/cpp-cpm-engine` | 2026-09-28T055520302778 -> 2026-09-28T141825732291 | 1 changed | quiet |
| 2026-09-28 | `remote/com.dexpaprika/dexpaprika` | 2026-09-28T103925653301 -> 2026-09-28T141814849349 | 3 changed | quiet |
| 2026-09-28 | `remote/com.dataart/case-studies` | 2026-09-28T103902147108 -> 2026-09-28T141750333101 | 1 changed | quiet |
| 2026-09-28 | `remote/ai.maxcv/resume` | 2026-09-23T162629867708 -> 2026-09-28T141738056463 | 1 changed | quiet |
| 2026-09-28 | `remote/com.jagannathahora/vedic-astrology` | 2026-09-23T160450087892 -> 2026-09-28T141730610471 | 2 changed | quiet |
| 2026-09-28 | `remote/io.github.peter120525-cmd/lawmadi-os` | 2026-09-27T232600727465 -> 2026-09-28T141721386099 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 9305 substantive, 3130 that changed only numbers (a catalogue counter ticking, a date), 132 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 7017 | 4042 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `caseyjhand.com` | 56 | 56 | 0 | 0 |
| `daedalmap.com` | 47 | 47 | 0 | 0 |
| `sistaminuten.se` | 34 | 2 | 0 | 32 |
| `afbudsrejser.dk` | 33 | 2 | 0 | 31 |
| `akkilahdot.fi` | 33 | 2 | 0 | 31 |
| `restplass.no` | 33 | 2 | 0 | 31 |
| `socialloop.ai` | 33 | 33 | 0 | 0 |
| `civai.co` | 24 | 24 | 0 | 0 |
| `dayze.com` | 24 | 24 | 0 | 0 |
| 1093 other operators | 2468 | 2306 | 155 | 7 |
