# MCP server tool changes

Last change observed 2026-11-11T16:42:05+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

91214 changes to a tool definition: 3941 npm releases (3695 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 87273 readings of hosted servers that found their tools changed; 3784 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps and signed with Sigstore: [checkpoints/](checkpoints). To check a day, rebuild the manifest of the commit it names, compare it with `manifest_sha256`, then verify the proof (the full steps, and what each one trusts, are in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints)):

```bash
day=2026-09-28
commit=$(python3 -c "import json; print(json.load(open('checkpoints/$day.json'))['feed_commit'])")
mkdir ../at && git -c core.autocrlf=false archive "$commit" | tar -x -C ../at
(cd ../at && find . -type f ! -path './checkpoints/*' -printf '%P\0' \
  | LC_ALL=C sort -z | xargs -0 sha256sum | sha256sum)   # = manifest_sha256
pip install opentimestamps-client && ots verify checkpoints/$day.json.ots
```

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-11-11 | `remote/studio.gradients/mcp` | 2026-11-11T150117004957 -> 2026-11-11T164206802937 | 1 changed | quiet |
| 2026-11-11 | `remote/fi.akkilahdot/travel-search` | 2026-11-11T150055787693 -> 2026-11-11T164203942620 | 1 changed | quiet |
| 2026-11-11 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-11T150027763006 -> 2026-11-11T164200101373 | 3 changed | quiet |
| 2026-11-11 | `remote/com.tamingdns/mcp` | 2026-11-11T145914713997 -> 2026-11-11T164148892958 | 2 added | quiet |
| 2026-11-11 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-11T145839781728 -> 2026-11-11T164142328688 | 1 changed | quiet |
| 2026-11-11 | `remote/se.sistaminuten/travel-search` | 2026-11-11T150018387525 -> 2026-11-11T164135611535 | 1 changed | quiet |
| 2026-11-11 | `remote/io.escrova/escrova` | 2026-11-11T071419539634 -> 2026-11-11T164131397110 | 1 changed | quiet |
| 2026-11-11 | `remote/coffee.pwned/pwned-coffee` | 2026-11-09T165854291971 -> 2026-11-11T164129717391 | 1 changed | quiet |
| 2026-11-11 | `remote/news.truecrime/case-archive` | 2026-11-09T170100828253 -> 2026-11-11T164120409626 | 11 added | review |
| 2026-11-11 | `remote/io.suverse.versum/catalog` | 2026-11-11T145910247839 -> 2026-11-11T164115978613 | 1 changed | quiet |
| 2026-11-11 | `remote/no.restplass/travel-search` | 2026-11-11T145920951614 -> 2026-11-11T164114662557 | 1 changed | quiet |
| 2026-11-11 | `remote/dev.tanod/tanod` | 2026-11-11T145733548294 -> 2026-11-11T164114608773 | 1 added | quiet |
| 2026-11-11 | `remote/io.github.cryptoconspiracy/vurto-swap` | 2026-11-11T071403530295 -> 2026-11-11T164110216275 | 1 changed, 8 added | quiet |
| 2026-11-11 | `remote/net.tichat.tradehub/tradehub.1` | 2026-11-11T145836579909 -> 2026-11-11T164109746541 | 3 changed | quiet |
| 2026-11-11 | `remote/dk.afbudsrejser/travel-search` | 2026-11-11T145828733487 -> 2026-11-11T164108406465 | 1 changed | quiet |
| 2026-11-11 | `remote/eu.tradedashboard/eu-trade-explorer` | 2026-11-09T165629612419 -> 2026-11-11T164110295910 | 15 changed | quiet |
| 2026-11-11 | `remote/io.github.exquad/thecablecode` | 2026-11-11T145813279831 -> 2026-11-11T164106229486 | 2 changed | quiet |
| 2026-11-11 | `remote/ai.surfingdog/search` | 2026-11-10T130338661703 -> 2026-11-11T164103463971 | 1 changed | quiet |
| 2026-11-11 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-10T220155788683 -> 2026-11-11T164057772275 | 1 removed | quiet |
| 2026-11-11 | `remote/xyz.pokeka/card-prices` | 2026-11-11T145506264325 -> 2026-11-11T164050206494 | 1 changed | quiet |
| 2026-11-11 | `remote/app.seatsherpa/rides` | 2026-11-10T130353213667 -> 2026-11-11T164049672267 | 5 changed | quiet |
| 2026-11-11 | `remote/io.github.ThomasFindlay/beautyspark-mcp` | 2026-11-10T152005883339 -> 2026-11-11T164048554509 | 1 changed | quiet |
| 2026-11-11 | `remote/com.apptiller/apptiller` | 2026-11-11T145131248287 -> 2026-11-11T164048411560 | 56 changed (every tool) | quiet |
| 2026-11-11 | `remote/vn.algolab/mcp.1` | 2026-11-11T145117428697 -> 2026-11-11T164048071403 | 2 changed | quiet |
| 2026-11-11 | `remote/com.straelo/relay` | 2026-11-10T030003627567 -> 2026-11-11T164045869574 | 3 changed | quiet |
| 2026-11-11 | `remote/io.github.RyanCardin15/noaa-tides-and-currents-mcp` | 2026-11-11T145451084021 -> 2026-11-11T164044894370 | 5 added | quiet |
| 2026-11-11 | `remote/land.fabrica/mcp-testnet` | 2026-11-11T145103780706 -> 2026-11-11T164044425556 | 1 changed | quiet |
| 2026-11-11 | `remote/fun.make/makefun` | 2026-11-11T145051188503 -> 2026-11-11T164042798817 | 2 changed | quiet |
| 2026-11-11 | `remote/com.plainrouter/mcp` | 2026-11-10T152725656834 -> 2026-11-11T164043353969 | 3 changed | quiet |
| 2026-11-11 | `remote/app.liquidvision/derivatives` | 2026-11-11T145039905778 -> 2026-11-11T164040758392 | 1 added | quiet |
| 2026-11-11 | `remote/io.github.leanrads/leanriq` | 2026-11-11T144957383491 -> 2026-11-11T164034036338 | 3 changed | quiet |
| 2026-11-11 | `remote/dev.notavibe/mcp` | 2026-11-11T145412089670 -> 2026-11-11T164033214916 | 3 changed | quiet |
| 2026-11-11 | `remote/com.mylatinlife/data` | 2026-11-11T145349558968 -> 2026-11-11T164032090803 | 4 added | quiet |
| 2026-11-11 | `remote/app.trustydata/trustydata` | 2026-11-11T145253867054 -> 2026-11-11T164032415913 | 2 changed | quiet |
| 2026-11-11 | `remote/markets.groundhog/weather` | 2026-11-11T144911546714 -> 2026-11-11T164026877034 | 1 changed | quiet |
| 2026-11-11 | `remote/com.productclank/productclank` | 2026-11-11T145212223368 -> 2026-11-11T164027335122 | 1 changed | quiet |
| 2026-11-11 | `remote/services.ottoai/otto` | 2026-11-11T145201372840 -> 2026-11-11T164025887461 | 3 changed | quiet |
| 2026-11-11 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-11-10T220120515202 -> 2026-11-11T164024303230 | 1 changed | review |
| 2026-11-11 | `remote/com.geppettorobotdirectory/geppetto-robot-directory` | 2026-11-09T165012324143 -> 2026-11-11T164024562129 | 4 changed | quiet |
| 2026-11-11 | `remote/ai.sendraven/mcp` | 2026-11-10T220120499847 -> 2026-11-11T164024275367 | 3 added | quiet |
| 2026-11-11 | `remote/com.luneresearch/lune` | 2026-11-09T165418325056 -> 2026-11-11T164023866635 | 9 changed | quiet |
| 2026-11-11 | `remote/com.squirrelscan/squirrelscan` | 2026-11-11T145230127731 -> 2026-11-11T164024779914 | 2 changed | quiet |
| 2026-11-11 | `remote/app.vercel.fork-for-agents/fork` | 2026-11-11T144410584648 -> 2026-11-11T164022782079 | 1 changed | quiet |
| 2026-11-11 | `remote/net.pendingdelete/mcp` | 2026-11-11T145204273023 -> 2026-11-11T164020248389 | 1 changed | quiet |
| 2026-11-11 | `remote/ru.pandawed/pandawed` | 2026-11-09T165556655976 -> 2026-11-11T164021025277 | 7 changed (every tool) | quiet |
| 2026-11-11 | `remote/kr.co.internettrend/internettrend-try` | 2026-11-10T220116838819 -> 2026-11-11T164021688747 | 1 changed | quiet |
| 2026-11-11 | `remote/land.fabrica/mcp` | 2026-11-11T145047589326 -> 2026-11-11T164018177196 | 1 changed | quiet |
| 2026-11-11 | `remote/com.onlinealarmkur/date-calculator-mcp` | 2026-11-11T145139681161 -> 2026-11-11T164016817326 | 4 changed (every tool) | quiet |
| 2026-11-11 | `remote/com.ncstatutes/ncgs` | 2026-11-11T145128199875 -> 2026-11-11T164016173608 | 1 changed, 2 added | quiet |
| 2026-11-11 | `remote/com.dominickprevete/dscr-lender-data` | 2026-11-11T144308981351 -> 2026-11-11T164016094398 | 2 changed | quiet |
| 2026-11-11 | `remote/ai.agentgates/compute` | 2026-11-11T144936926563 -> 2026-11-11T164012925514 | 1 changed | quiet |
| 2026-11-11 | `remote/io.github.ckangas2/abstractinator` | 2026-11-11T144934167750 -> 2026-11-11T164012709480 | 1 changed | quiet |
| 2026-11-11 | `remote/com.davelalande/camps` | 2026-11-10T215952944986 -> 2026-11-11T164010805770 | 3 added | quiet |
| 2026-11-11 | `remote/com.etfiq/etfiq` | 2026-11-10T152133130219 -> 2026-11-11T164009812066 | 1 changed | quiet |
| 2026-11-11 | `remote/io.dropyour/dropyour` | 2026-11-11T145049143247 -> 2026-11-11T164010329385 | 1 changed | quiet |
| 2026-11-11 | `remote/co.deadbrands/arena` | 2026-11-11T145038993693 -> 2026-11-11T164010562146 | 1 changed, 4 added | quiet |
| 2026-11-11 | `remote/com.bottleyourbrand/print-shop` | 2026-11-10T152137739256 -> 2026-11-11T164006152207 | 2 changed | quiet |
| 2026-11-11 | `remote/me.chargingnear/mcp` | 2026-11-11T071231110023 -> 2026-11-11T164002133230 | 3 changed | quiet |
| 2026-11-11 | `remote/fr.marcel-retraite/marcel` | 2026-11-10T025924121726 -> 2026-11-11T164002556620 | 1 changed | quiet |
| 2026-11-11 | `remote/app.luala/luala` | 2026-11-10T130307794900 -> 2026-11-11T164001181721 | 7 changed, 1 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 57088 substantive, 33171 that changed only numbers (a catalogue counter ticking, a date), 955 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 48830 | 17746 | 31084 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 2108 | 2108 | 0 | 0 |
| `caseyjhand.com` | 383 | 383 | 0 | 0 |
| `civai.co` | 286 | 286 | 0 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `revmesh2074.workers.dev` | 225 | 197 | 28 | 0 |
| `sistaminuten.se` | 223 | 6 | 0 | 217 |
| `afbudsrejser.dk` | 222 | 6 | 0 | 216 |
| `akkilahdot.fi` | 222 | 6 | 0 | 216 |
| `restplass.no` | 222 | 6 | 0 | 216 |
| `socialloop.ai` | 214 | 214 | 0 | 0 |
| 8790 other operators | 35680 | 33531 | 2059 | 90 |
