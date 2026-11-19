# MCP server tool changes

Last change observed 2026-11-19T13:59:13+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

117388 changes to a tool definition: 4732 npm releases (4486 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 112656 readings of hosted servers that found their tools changed; 4442 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-19 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-11-18T140004068594 -> 2026-11-19T135915478426 | 1 changed, 1 added | quiet |
| 2026-11-19 | `remote/se.sistaminuten/travel-search` | 2026-11-19T123915373874 -> 2026-11-19T135912666283 | 1 changed | quiet |
| 2026-11-19 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-11-18T135941558391 -> 2026-11-19T135908642618 | 1 changed, 1 added | quiet |
| 2026-11-19 | `remote/no.restplass/travel-search` | 2026-11-19T123903826542 -> 2026-11-19T135905638841 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.utilify-io/utilify-mcp` | 2026-11-19T020351301512 -> 2026-11-19T135905640379 | 1 changed, 4 added | quiet |
| 2026-11-19 | `remote/news.truecrime/case-archive` | 2026-11-19T123653153478 -> 2026-11-19T135903392897 | 2 changed | review |
| 2026-11-19 | `remote/dk.afbudsrejser/travel-search` | 2026-11-19T123816020713 -> 2026-11-19T135900406628 | 1 changed | quiet |
| 2026-11-19 | `remote/studio.gradients/mcp` | 2026-11-19T124040324912 -> 2026-11-19T135858876977 | 1 changed | quiet |
| 2026-11-19 | `remote/fi.akkilahdot/travel-search` | 2026-11-19T124001906848 -> 2026-11-19T135856390523 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.AKzar1el/mcp-web-validator` | 2026-11-18T135830529762 -> 2026-11-19T135852356982 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.t0ll-xyz/toll` | 2026-11-17T234330287277 -> 2026-11-19T135851304179 | 1 added | quiet |
| 2026-11-19 | `remote/ru.vargov/vargov-design` | 2026-11-19T123904961661 -> 2026-11-19T135851736672 | 2 changed | quiet |
| 2026-11-19 | `remote/com.pikasim/pikasim` | 2026-11-19T123335838730 -> 2026-11-19T135849240312 | 2 added | quiet |
| 2026-11-19 | `remote/at.space-core/game` | 2026-11-19T020436654251 -> 2026-11-19T135847646519 | 1 changed | quiet |
| 2026-11-19 | `remote/com.swellcabin/surf` | 2026-11-19T123736269830 -> 2026-11-19T135844225401 | 4 changed | quiet |
| 2026-11-19 | `remote/uk.co.extreme-media.snow/em-snow` | 2026-11-19T123700087703 -> 2026-11-19T135842842788 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-19T123659989642 -> 2026-11-19T135842534225 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.Shicodiez/crypto-regime-mcp` | 2026-11-19T123641697497 -> 2026-11-19T135841276159 | 2 changed | review |
| 2026-11-19 | `remote/io.github.Kromatic-Innovation/neumann` | 2026-11-17T031525219407 -> 2026-11-19T135837620073 | 5 changed | quiet |
| 2026-11-19 | `remote/com.remoshift/jobs` | 2026-11-19T123534960179 -> 2026-11-19T135837952224 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.richardsolomou/praetorium` | 2026-11-19T123344964449 -> 2026-11-19T135839047563 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.joseanu/presupuestos-red` | 2026-11-19T123347337391 -> 2026-11-19T135838820016 | 3 changed | quiet |
| 2026-11-19 | `remote/io.github.Playpowerpolitics/powerplayers` | 2026-11-19T123342197251 -> 2026-11-19T135837099646 | 2 added | quiet |
| 2026-11-19 | `remote/io.github.LusoCryptoLabs/ckb-pulse` | 2026-11-18T135429727986 -> 2026-11-19T135840113958 | 4 added | quiet |
| 2026-11-19 | `remote/io.github.nukafever-lab/nukafever` | 2026-11-18T135114361351 -> 2026-11-19T135833934543 | 1 changed, 3 added | quiet |
| 2026-11-19 | `remote/io.github.lx1112/agent-data-api` | 2026-11-19T123253117643 -> 2026-11-19T135834818398 | 4 added | quiet |
| 2026-11-19 | `remote/com.scrapeunblocker/scrapeunblocker-mcp-remote` | 2026-11-19T122922673696 -> 2026-11-19T135830722129 | 7 changed | quiet |
| 2026-11-19 | `remote/io.github.dzhng/bento` | 2026-11-18T160417004424 -> 2026-11-19T135829410481 | 5 changed | quiet |
| 2026-11-19 | `remote/com.sonarconnections/sonar-connections` | 2026-11-19T123252901699 -> 2026-11-19T135826467374 | 1 changed | quiet |
| 2026-11-19 | `remote/com.stocklens/stocklens` | 2026-11-17T135556323646 -> 2026-11-19T135824619461 | 7 changed | quiet |
| 2026-11-19 | `remote/market.populardemand/popular-demand` | 2026-11-19T123124951060 -> 2026-11-19T135824652800 | 2 changed | quiet |
| 2026-11-19 | `remote/io.github.MKagesawa/masadeals` | 2026-11-19T122623796319 -> 2026-11-19T135820776174 | 1 changed | quiet |
| 2026-11-19 | `remote/com.masteringfinancialmarkets/mfm` | 2026-11-19T020336319616 -> 2026-11-19T135821063410 | 1 changed | quiet |
| 2026-11-19 | `remote/com.lightbringer/connector` | 2026-11-17T163932397181 -> 2026-11-19T135820976287 | 11 changed, 3 added, 1 removed | quiet |
| 2026-11-19 | `remote/ai.llpro/campus` | 2026-11-19T122603954986 -> 2026-11-19T135820381180 | 1 changed | quiet |
| 2026-11-19 | `remote/pl.horseback/horseback` | 2026-11-17T163354305880 -> 2026-11-19T135818229845 | 3 changed | quiet |
| 2026-11-19 | `remote/ai.deployit/product-expert` | 2026-11-17T163802852056 -> 2026-11-19T135817368866 | 2 changed | quiet |
| 2026-11-19 | `remote/ai.guestlogic/guest-logic` | 2026-11-19T122407590888 -> 2026-11-19T135814584549 | 4 changed, 5 added | quiet |
| 2026-11-19 | `remote/com.360dialog/mcp` | 2026-11-19T122801363242 -> 2026-11-19T135814140434 | 83 removed | quiet |
| 2026-11-19 | `remote/fr.ip73/ip73` | 2026-11-19T122634416758 -> 2026-11-19T135808022347 | 2 changed | quiet |
| 2026-11-19 | `remote/com.decisionscalc/calculators` | 2026-11-19T122157124190 -> 2026-11-19T135808439341 | 1 changed | quiet |
| 2026-11-19 | `remote/com.dcblueprint/data-centres` | 2026-11-18T173823936096 -> 2026-11-19T135808443173 | 2 changed | quiet |
| 2026-11-19 | `remote/dev.taifoon.coord/text-digest-1170141` | 2026-11-19T122129723997 -> 2026-11-19T135816664491 | 1 changed | quiet |
| 2026-11-19 | `remote/site.goat-lighthouse/market-news` | 2026-11-19T122535908564 -> 2026-11-19T135805139022 | 4 changed | quiet |
| 2026-11-19 | `remote/app.vercel.fork-for-agents/fork` | 2026-11-19T122324212996 -> 2026-11-19T135804610928 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.singularitybpjade/balance-engine` | 2026-11-17T162451504361 -> 2026-11-19T135800975054 | 5 changed, 1 added | quiet |
| 2026-11-19 | `remote/ai.signalry/countersign` | 2026-11-18T080118363180 -> 2026-11-19T135758693404 | 2 changed | quiet |
| 2026-11-19 | `remote/com.spurvik/eu-ai-act` | 2026-11-19T122105557094 -> 2026-11-19T135758712876 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-11-19T020219643617 -> 2026-11-19T135759698943 | 2 changed | quiet |
| 2026-11-19 | `remote/io.taifoon/coordination-layer` | 2026-11-19T122126224188 -> 2026-11-19T135800670313 | 1 changed | review |
| 2026-11-19 | `remote/com.oroboros-design.angel/checkout-guard` | 2026-11-19T121431723554 -> 2026-11-19T135752615841 | 1 changed | quiet |
| 2026-11-19 | `remote/com.astranl/mcp` | 2026-11-19T121922776247 -> 2026-11-19T135752457324 | 1 changed | quiet |
| 2026-11-19 | `remote/com.astranl/coordination-protocol` | 2026-11-19T121922700956 -> 2026-11-19T135752352517 | 1 changed | quiet |
| 2026-11-19 | `remote/com.apptierlist/apptierlist` | 2026-11-19T020225793484 -> 2026-11-19T135751413987 | 4 changed | quiet |
| 2026-11-19 | `remote/io.sslip.128.221.67.45.agent-exec/agent-exec` | 2026-11-19T020205263733 -> 2026-11-19T135751266988 | 1 added | quiet |
| 2026-11-19 | `remote/io.github.TorlettiJoaquin/ar-tools` | 2026-11-18T080018419652 -> 2026-11-19T135747495357 | 2 changed | quiet |
| 2026-11-19 | `remote/io.github.rajeswaran140/crowvault` | 2026-11-19T121556008846 -> 2026-11-19T135746359592 | 1 changed | quiet |
| 2026-11-19 | `remote/xyz.belfortagent/belfort-data` | 2026-11-19T121541766425 -> 2026-11-19T135744862089 | 12 added | quiet |
| 2026-11-19 | `remote/io.github.0xinsider/mcp` | 2026-11-19T121525474170 -> 2026-11-19T135743760635 | 2 changed | review |
| 2026-11-19 | `remote/com.oroboros-design.angel/tradesignal` | 2026-11-19T121520207614 -> 2026-11-19T135744565178 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 75306 substantive, 40980 that changed only numbers (a catalogue counter ticking, a date), 1102 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 63683 | 25330 | 38353 | 0 |
| `a2awire.com` | 3305 | 3305 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 471 | 471 | 0 | 0 |
| `civai.co` | 369 | 369 | 0 | 0 |
| `modevc.com` | 349 | 349 | 0 | 0 |
| `revmesh2074.workers.dev` | 319 | 274 | 45 | 0 |
| `sistaminuten.se` | 257 | 6 | 0 | 251 |
| `afbudsrejser.dk` | 256 | 6 | 0 | 250 |
| `akkilahdot.fi` | 256 | 6 | 0 | 250 |
| `restplass.no` | 256 | 6 | 0 | 250 |
| `socialloop.ai` | 247 | 247 | 0 | 0 |
| 10349 other operators | 45279 | 42596 | 2582 | 101 |
