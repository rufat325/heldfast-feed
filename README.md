# MCP server tool changes

Last change observed 2026-09-29T21:05:21+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

13381 changes to a tool definition: 384 npm releases (138 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 12997 readings of hosted servers that found their tools changed; 86 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-09-29 | `remote/com.youspot/youspot` | 2026-09-29T131739702093 -> 2026-09-29T210523236133 | 1 changed, 2 added | quiet |
| 2026-09-29 | `remote/fi.akkilahdot/travel-search` | 2026-09-29T150811544614 -> 2026-09-29T210517826751 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.kor-jongwon/witan` | 2026-09-29T150812554117 -> 2026-09-29T210518920769 | 22 changed (every tool) | quiet |
| 2026-09-29 | `remote/se.sistaminuten/travel-search` | 2026-09-29T150808636873 -> 2026-09-29T210514960164 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.lonniev/tollbooth-sample` | 2026-09-29T003615021112 -> 2026-09-29T210514186560 | 3 changed | quiet |
| 2026-09-29 | `remote/com.tickerinside/tickerinside-mcp` | 2026-09-29T101907831545 -> 2026-09-29T210513325765 | 5 changed | quiet |
| 2026-09-29 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-09-29T003614178285 -> 2026-09-29T210512824716 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.nimitt-IN/india-cyber-regulations` | 2026-09-28T142314515634 -> 2026-09-29T210512398244 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.lonniev/tollbooth-authority-newengland` | 2026-09-29T061634128686 -> 2026-09-29T210512494673 | 3 changed | quiet |
| 2026-09-29 | `remote/io.github.TRDEFI/liquidity` | 2026-09-28T142335429090 -> 2026-09-29T210512724738 | 6 changed (every tool) | quiet |
| 2026-09-29 | `remote/info.yank/yank` | 2026-09-28T142334144664 -> 2026-09-29T210511144122 | 1 changed | quiet |
| 2026-09-29 | `remote/com.swarmmemo/bulletin` | 2026-09-29T131523635064 -> 2026-09-29T210512012862 | 3 added | quiet |
| 2026-09-29 | `remote/io.taifoon/coordination-layer` | 2026-09-28T170355633238 -> 2026-09-29T210509951310 | 11 added | review |
| 2026-09-29 | `remote/com.thenewengineer/hvac` | 2026-09-28T142252512576 -> 2026-09-29T210511736354 | 1 changed, 3 added | quiet |
| 2026-09-29 | `remote/cc.thecolony/mcp-server` | 2026-09-29T131612193027 -> 2026-09-29T210511615078 | 1 changed, 7 added | quiet |
| 2026-09-29 | `remote/no.restplass/travel-search` | 2026-09-29T150804363604 -> 2026-09-29T210509288559 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-29T150802287087 -> 2026-09-29T210509396083 | 1 changed | quiet |
| 2026-09-29 | `remote/family.fuci.www/fuci` | 2026-09-28T142310039363 -> 2026-09-29T210508247765 | 1 added | review |
| 2026-09-29 | `remote/com.innergcomplete/shearquery` | 2026-09-29T080337438991 -> 2026-09-29T210513799596 | 4 changed, 2 added | quiet |
| 2026-09-29 | `remote/com.searchfragments/search-fragments` | 2026-09-29T003609769004 -> 2026-09-29T210506999726 | 3 changed (every tool) | quiet |
| 2026-09-29 | `remote/io.github.SKalinin909/tradingcalc` | 2026-09-27T195353900064 -> 2026-09-29T210510879897 | 75 changed (every tool) | quiet |
| 2026-09-29 | `remote/dk.afbudsrejser/travel-search` | 2026-09-29T150801826519 -> 2026-09-29T210506237804 | 1 changed | quiet |
| 2026-09-29 | `remote/com.ryufin/stocks` | 2026-09-29T003608930648 -> 2026-09-29T210505891648 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.taux-io/twse-mcp` | 2026-09-28T073135649884 -> 2026-09-29T210504475680 | 2 changed | quiet |
| 2026-09-29 | `remote/io.github.davisvillelabs/scopeproof` | 2026-09-28T142157006824 -> 2026-09-29T210503555770 | 3 added, 3 removed | quiet |
| 2026-09-29 | `remote/com.remoshift/jobs` | 2026-09-29T150755960450 -> 2026-09-29T210503698304 | 1 changed | quiet |
| 2026-09-29 | `remote/com.radar-cnpj/radar-cnpj` | 2026-09-29T061644233713 -> 2026-09-29T210504032087 | 2 changed | quiet |
| 2026-09-29 | `remote/com.tradeassi/mcp` | 2026-09-28T142231046185 -> 2026-09-29T210502239789 | 10 changed, 7 added | review |
| 2026-09-29 | `remote/com.ribqa/sentinel-aleph` | 2026-09-29T131511619142 -> 2026-09-29T210501906511 | 1 changed | quiet |
| 2026-09-29 | `remote/com.asksakina/islamic-knowledge` | 2026-09-28T142147953374 -> 2026-09-29T210500994603 | 4 changed (every tool) | quiet |
| 2026-09-29 | `remote/pl.klyo/games` | 2026-09-29T003604784057 -> 2026-09-29T210502292852 | 1 changed, 1 added | quiet |
| 2026-09-29 | `remote/io.github.lonniev/roastify-mcp` | 2026-09-29T003610539214 -> 2026-09-29T210500198123 | 3 changed | quiet |
| 2026-09-29 | `remote/io.github.bnmbnmai/bnm-data-shop` | 2026-09-29T073434747998 -> 2026-09-29T210518353797 | 4 changed, 3 added | quiet |
| 2026-09-29 | `remote/com.opointo/opointo` | 2026-09-28T142424231564 -> 2026-09-29T210459607033 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-09-29T113337292549 -> 2026-09-29T210459225485 | 15 changed | review |
| 2026-09-29 | `remote/io.github.Perufitlife/postwire-mcp` | 2026-09-29T150733545168 -> 2026-09-29T210458675426 | 2 changed | quiet |
| 2026-09-29 | `remote/com.pontofato/pontofato` | 2026-09-29T150733194483 -> 2026-09-29T210459598445 | 1 changed | quiet |
| 2026-09-29 | `remote/io.scoutrail/scoutrail` | 2026-09-28T073055259281 -> 2026-09-29T210457093411 | 1 changed | quiet |
| 2026-09-29 | `remote/com.pinsvit/api` | 2026-09-28T073133835428 -> 2026-09-29T210457183604 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.lonniev/schwab-mcp` | 2026-09-29T003615558724 -> 2026-09-29T210455880121 | 3 changed | quiet |
| 2026-09-29 | `remote/io.github.lonniev/personalbrain-mcp` | 2026-09-29T003606062235 -> 2026-09-29T210454974391 | 3 changed | quiet |
| 2026-09-29 | `remote/io.github.Payotte-com/payotte-mcp` | 2026-09-29T131433114437 -> 2026-09-29T210454857714 | 3 added | review |
| 2026-09-29 | `remote/io.github.lonniev/optionality-mcp` | 2026-09-29T003559466495 -> 2026-09-29T210455576731 | 3 changed | quiet |
| 2026-09-29 | `remote/ai.rokha/rokha` | 2026-09-29T061648242153 -> 2026-09-29T210454828222 | 2 added | quiet |
| 2026-09-29 | `remote/com.straelo/relay` | 2026-09-29T131544713038 -> 2026-09-29T210452743000 | 7 removed | quiet |
| 2026-09-29 | `remote/io.github.magichourhq/magic-hour` | 2026-09-29T061630249601 -> 2026-09-29T210450836651 | 7 changed | quiet |
| 2026-09-29 | `remote/com.meettempi/tempi` | 2026-09-28T170333286154 -> 2026-09-29T210451250750 | 1 changed | quiet |
| 2026-09-29 | `remote/com.vertodigital/mcp` | 2026-09-29T150725924521 -> 2026-09-29T210449373421 | 6 changed (every tool) | quiet |
| 2026-09-29 | `remote/com.handsforagents/hands` | 2026-09-29T101509366088 -> 2026-09-29T210449540766 | 1 changed | quiet |
| 2026-09-29 | `remote/io.soundchecklive/live-event-quotes` | 2026-09-28T141945359687 -> 2026-09-29T210447257313 | 1 added | quiet |
| 2026-09-29 | `remote/com.spaghettiandsummits/outdoors` | 2026-09-28T103938230416 -> 2026-09-29T210446846044 | 1 added, 1 removed | quiet |
| 2026-09-29 | `remote/pro.particle/particle-pro` | 2026-09-29T073026236248 -> 2026-09-29T210446054211 | 1 changed | quiet |
| 2026-09-29 | `remote/net.praegant/landhaus` | 2026-09-27T112820497695 -> 2026-09-29T210446265051 | 2 changed | quiet |
| 2026-09-29 | `remote/com.metricduck/financial-analysis` | 2026-09-28T141841257041 -> 2026-09-29T210444458434 | 3 changed | quiet |
| 2026-09-29 | `remote/io.github.si-imtiaz/leadquasar` | 2026-09-29T003548837352 -> 2026-09-29T210444373743 | 2 changed | quiet |
| 2026-09-29 | `remote/io.github.proplineapi/propline-mcp` | 2026-09-27T152720178568 -> 2026-09-29T210442683463 | 2 added | quiet |
| 2026-09-29 | `remote/com.freqblog/music-metadata` | 2026-09-27T103451682759 -> 2026-09-29T210443017559 | 2 changed | quiet |
| 2026-09-29 | `remote/com.graceroad-group/graceroad` | 2026-09-28T142037094523 -> 2026-09-29T210440935862 | 3 changed (every tool) | quiet |
| 2026-09-29 | `remote/io.github.ricksporto/freshproof` | 2026-09-28T072602157636 -> 2026-09-29T210440553884 | 2 changed | quiet |
| 2026-09-29 | `remote/co.lovie/company-formation` | 2026-09-28T141858770290 -> 2026-09-29T210439821329 | 24 changed, 5 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 10033 substantive, 3167 that changed only numbers (a catalogue counter ticking, a date), 181 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 7023 | 4048 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `caseyjhand.com` | 56 | 56 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| `sistaminuten.se` | 46 | 2 | 0 | 44 |
| `afbudsrejser.dk` | 45 | 2 | 0 | 43 |
| `akkilahdot.fi` | 45 | 2 | 0 | 43 |
| `restplass.no` | 45 | 2 | 0 | 43 |
| `socialloop.ai` | 45 | 45 | 0 | 0 |
| `fastmcp.app` | 37 | 37 | 0 | 0 |
| `dayze.com` | 32 | 32 | 0 | 0 |
| 1307 other operators | 3191 | 2991 | 192 | 8 |
