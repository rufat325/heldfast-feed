# MCP server tool changes

Last change observed 2026-10-21T23:46:08+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

40303 changes to a tool definition: 1694 npm releases (1448 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 38609 readings of hosted servers that found their tools changed; 2330 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-21 | `remote/io.github.ak10082247-max/x402-agent-tollbooth` | 2026-10-19T135909360694 -> 2026-10-21T234608315702 | 4 changed (every tool) | quiet |
| 2026-10-21 | `remote/dev.xpansion/xfms` | 2026-10-21T052516449348 -> 2026-10-21T234609231896 | 1 changed | quiet |
| 2026-10-21 | `remote/no.restplass/travel-search` | 2026-10-21T202602271062 -> 2026-10-21T234607054532 | 1 changed | quiet |
| 2026-10-21 | `remote/com.meridiandispatch/travel-guides` | 2026-10-19T052438895865 -> 2026-10-21T234606155205 | 1 changed | quiet |
| 2026-10-21 | `remote/dk.afbudsrejser/travel-search` | 2026-10-21T202557146412 -> 2026-10-21T234602276586 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-10-20T104127748818 -> 2026-10-21T234550045563 | 5 changed, 1 added | review |
| 2026-10-21 | `remote/app.sallim/korea-realty` | 2026-10-21T141121141777 -> 2026-10-21T234542512932 | 3 changed | quiet |
| 2026-10-21 | `remote/fun.pumpdata/pumpdata` | 2026-10-20T052328322675 -> 2026-10-21T234537627678 | 7 changed, 1 added | quiet |
| 2026-10-21 | `remote/io.github.cloakmaster/pact0` | 2026-10-21T202518736534 -> 2026-10-21T234533189298 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.fredxhansson-cmyk/noniner` | 2026-10-20T232742087626 -> 2026-10-21T234531569967 | 5 added | quiet |
| 2026-10-21 | `remote/com.moonshotlab1/inventory` | 2026-10-21T202513695952 -> 2026-10-21T234529567655 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.GrayWolf8-creator/gw8-signal-api` | 2026-10-21T202508736545 -> 2026-10-21T234521730215 | 18 changed, 1 added | review |
| 2026-10-21 | `remote/io.github.smarterweather/weather` | 2026-10-21T121708971508 -> 2026-10-21T234501096654 | 3 changed | quiet |
| 2026-10-21 | `remote/io.github.yzlee/opcmenu` | 2026-10-19T211900737678 -> 2026-10-21T234455530446 | 3 changed | quiet |
| 2026-10-21 | `remote/cc.hlist/hlist-ai-tools` | 2026-10-20T052249285827 -> 2026-10-21T234310949200 | 1 changed | quiet |
| 2026-10-21 | `remote/io.taifoon/coordination-layer.1` | 2026-10-21T202608383804 -> 2026-10-21T234245159297 | 1 changed | review |
| 2026-10-21 | `remote/se.sistaminuten/travel-search` | 2026-10-21T202606924635 -> 2026-10-21T234244394648 | 1 changed | quiet |
| 2026-10-21 | `remote/dev.primitive/email` | 2026-10-21T052303454393 -> 2026-10-21T234239967841 | 2 changed | quiet |
| 2026-10-21 | `remote/io.github.Licium-ai/licium` | 2026-10-21T122216588619 -> 2026-10-21T234238622232 | 2 changed | review |
| 2026-10-21 | `remote/com.mintlify/searchmcp` | 2026-10-19T212025437457 -> 2026-10-21T234238617960 | 1 changed | quiet |
| 2026-10-21 | `remote/studio.gradients/mcp` | 2026-10-21T202520792500 -> 2026-10-21T234237666374 | 1 changed | quiet |
| 2026-10-21 | `remote/fi.akkilahdot/travel-search` | 2026-10-21T202518149491 -> 2026-10-21T234235343105 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.muaviamohammed/mizan` | 2026-10-21T202545788786 -> 2026-10-21T234228596708 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.getDynamoi/dynamoi` | 2026-10-21T202421279703 -> 2026-10-21T234234720792 | 1 changed | quiet |
| 2026-10-21 | `remote/ai.weio/site-check` | 2026-10-21T141138024531 -> 2026-10-21T234223368925 | 3 added, 2 removed | quiet |
| 2026-10-21 | `remote/io.github.sorindecu/vibeshipped` | 2026-10-21T052252980614 -> 2026-10-21T234221951778 | 16 changed (every tool) | quiet |
| 2026-10-21 | `remote/com.digitalundergroundstore/marketplace` | 2026-10-19T134728373196 -> 2026-10-21T234218735406 | 1 changed | quiet |
| 2026-10-21 | `remote/io.szum/charts` | 2026-10-21T122041956608 -> 2026-10-21T234218421989 | 13 changed | quiet |
| 2026-10-21 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-21T141121293203 -> 2026-10-21T234216491631 | 2 changed | quiet |
| 2026-10-21 | `remote/io.github.jennipro-engineering/ghost-market-web` | 2026-10-21T122006806619 -> 2026-10-21T234213241955 | 1 changed | quiet |
| 2026-10-21 | `remote/com.session-exchange/sessions` | 2026-10-19T211936771789 -> 2026-10-21T234212319006 | 1 changed, 11 removed | quiet |
| 2026-10-21 | `remote/com.sellerprofitdoctor/free-tools` | 2026-10-20T201120356359 -> 2026-10-21T234211238385 | 2 changed | quiet |
| 2026-10-21 | `remote/io.github.fredxhansson-cmyk/fuze` | 2026-10-20T232659187930 -> 2026-10-21T234217412657 | 5 added | quiet |
| 2026-10-21 | `remote/io.github.ak10082247-max/rugshield-402` | 2026-10-21T141112240333 -> 2026-10-21T234208034450 | 14 changed (every tool) | quiet |
| 2026-10-21 | `remote/com.remoshift/jobs` | 2026-10-21T202450211012 -> 2026-10-21T234207614750 | 1 changed | quiet |
| 2026-10-21 | `remote/world.tokenbank/tokenbank` | 2026-10-19T134954557169 -> 2026-10-21T234203493935 | 1 added | quiet |
| 2026-10-21 | `remote/co.schoolscope/mcp` | 2026-10-20T103848226429 -> 2026-10-21T234202096331 | 7 changed (every tool) | quiet |
| 2026-10-21 | `remote/io.github.priors-agents/priors-read` | 2026-10-21T121732607159 -> 2026-10-21T234200378475 | 2 added | quiet |
| 2026-10-21 | `remote/pl.klyo/games` | 2026-10-21T202442933543 -> 2026-10-21T234159317697 | 1 changed | quiet |
| 2026-10-21 | `remote/io.taifoon/coordination-layer` | 2026-10-21T202416103972 -> 2026-10-21T234206469170 | 1 changed | review |
| 2026-10-21 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-10-21T202502223540 -> 2026-10-21T234157060889 | 1 changed | review |
| 2026-10-21 | `remote/com.negativeresistance/cure-protocol` | 2026-10-21T202436930740 -> 2026-10-21T234157880130 | 5 changed | quiet |
| 2026-10-21 | `remote/fr.comontel/forfaits` | 2026-10-21T202410527741 -> 2026-10-21T234156255217 | 3 changed, 3 added | quiet |
| 2026-10-21 | `remote/com.soundza/soundza.1` | 2026-10-21T202426516695 -> 2026-10-21T234146712795 | 1 changed, 1 added | quiet |
| 2026-10-21 | `remote/ws.overflo/overflows` | 2026-10-19T134709037323 -> 2026-10-21T234143960242 | 5 changed | quiet |
| 2026-10-21 | `remote/ai.makememoneynomistakes/scoreboard` | 2026-10-20T052242636854 -> 2026-10-21T234143239094 | 1 changed | quiet |
| 2026-10-21 | `remote/com.pyxmark/pyxmark` | 2026-10-19T135009982624 -> 2026-10-21T234142352929 | 1 changed | quiet |
| 2026-10-21 | `remote/tech.kaiku/kaiku.1` | 2026-10-21T202418226977 -> 2026-10-21T234140804128 | 3 changed, 5 added | quiet |
| 2026-10-21 | `remote/io.github.hail-hq/hail-mcp` | 2026-10-21T202421988685 -> 2026-10-21T234137209626 | 9 changed | quiet |
| 2026-10-21 | `remote/com.hireahelper/mcp` | 2026-10-21T141042995119 -> 2026-10-21T234136492083 | 16 added | quiet |
| 2026-10-21 | `remote/com.intakra/buying-signal-review` | 2026-10-21T202443181160 -> 2026-10-21T234141741585 | 12 removed | quiet |
| 2026-10-21 | `remote/com.bota-chat/bota` | 2026-10-21T121535660978 -> 2026-10-21T234132337567 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-21T202423655508 -> 2026-10-21T234127893928 | 2 changed | quiet |
| 2026-10-21 | `remote/com.lebaneselegislation/mcp` | 2026-10-20T135331396862 -> 2026-10-21T234125090206 | 3 changed | quiet |
| 2026-10-21 | `remote/com.exchangerebel/exchangerebel` | 2026-10-20T135320628543 -> 2026-10-21T234126247654 | 2 added | quiet |
| 2026-10-21 | `remote/ai.inite/atlas` | 2026-10-21T141035731137 -> 2026-10-21T234124314784 | 2 changed | quiet |
| 2026-10-21 | `remote/com.dayze/life-context.1` | 2026-10-21T202411395363 -> 2026-10-21T234119106913 | 1 changed | quiet |
| 2026-10-21 | `remote/com.dayze/life-context` | 2026-10-21T202410779395 -> 2026-10-21T234118281593 | 1 changed | quiet |
| 2026-10-21 | `remote/xyz.filingdelta/filingdelta` | 2026-10-19T134227957199 -> 2026-10-21T234114261609 | 11 changed (every tool) | quiet |
| 2026-10-21 | `remote/com.carhauler247/car-shipping-quotes` | 2026-10-19T134220076837 -> 2026-10-21T234111820282 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 25485 substantive, 14269 that changed only numbers (a catalogue counter ticking, a date), 549 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 20653 | 7232 | 13421 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 171 | 171 | 0 | 0 |
| `sistaminuten.se` | 131 | 4 | 0 | 127 |
| `afbudsrejser.dk` | 130 | 4 | 0 | 126 |
| `akkilahdot.fi` | 130 | 4 | 0 | 126 |
| `restplass.no` | 130 | 4 | 0 | 126 |
| `socialloop.ai` | 126 | 126 | 0 | 0 |
| `remoshift.com` | 101 | 6 | 95 | 0 |
| `fundinglandscape.com` | 99 | 64 | 35 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| 4951 other operators | 15541 | 14779 | 718 | 44 |
