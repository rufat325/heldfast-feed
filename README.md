# MCP server tool changes

Last change observed 2026-11-10T03:00:51+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

84928 changes to a tool definition: 3727 npm releases (3481 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 81201 readings of hosted servers that found their tools changed; 3670 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-10 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-11-09T071625594178 -> 2026-11-10T030052146476 | 1 added | quiet |
| 2026-11-10 | `remote/com.superstables/superstables.1` | 2026-11-09T170353394663 -> 2026-11-10T030051728435 | 2 changed | quiet |
| 2026-11-10 | `remote/io.github.Wei-LienWU/pit-fundamentals` | 2026-11-09T170308271693 -> 2026-11-10T030050517238 | 1 changed, 3 removed | quiet |
| 2026-11-10 | `remote/eu.trisonia/concerts` | 2026-11-09T170310026195 -> 2026-11-10T030051663651 | 1 changed | quiet |
| 2026-11-10 | `remote/se.sistaminuten/travel-search` | 2026-11-09T191512074307 -> 2026-11-10T030050026046 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.andzar22/offstereo` | 2026-11-09T191509855382 -> 2026-11-10T030047531634 | 3 changed, 1 added | quiet |
| 2026-11-10 | `remote/com.onlyworlds/mcp` | 2026-11-09T170249155392 -> 2026-11-10T030048614964 | 9 changed | quiet |
| 2026-11-10 | `remote/design.overflow/mcp` | 2026-11-09T170335249348 -> 2026-11-10T030051073892 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-11-09T170239946710 -> 2026-11-10T030046485320 | 4 changed | quiet |
| 2026-11-10 | `remote/io.github.JcJamet/ia-qa-eval` | 2026-11-09T170239846285 -> 2026-11-10T030046901726 | 3 changed | quiet |
| 2026-11-10 | `remote/de.fortsu/mcp` | 2026-11-09T170235665616 -> 2026-11-10T030046164505 | 2 changed | quiet |
| 2026-11-10 | `remote/io.github.Seifollahi/markolis` | 2026-11-09T170327056421 -> 2026-11-10T030045071584 | 1 changed | quiet |
| 2026-11-10 | `remote/studio.gradients/mcp` | 2026-11-09T191550477724 -> 2026-11-10T030040923668 | 1 changed | quiet |
| 2026-11-10 | `remote/uk.co.fortsu/mcp` | 2026-11-09T170303342109 -> 2026-11-10T030041685357 | 2 changed | quiet |
| 2026-11-10 | `remote/io.github.christianscode1994/volatiai-mcp` | 2026-11-09T170139331234 -> 2026-11-10T030037923741 | 2 added | quiet |
| 2026-11-10 | `remote/de.firma/rechner` | 2026-11-09T170302292761 -> 2026-11-10T030040137500 | 14 changed, 1 added (every tool) | quiet |
| 2026-11-10 | `remote/com.wcspoints/wsdc-points` | 2026-11-09T170150304045 -> 2026-11-10T030039285298 | 1 changed, 3 added | quiet |
| 2026-11-10 | `remote/app.vercel.watchesinstock-mcp/watches-in-stock` | 2026-11-09T170148307588 -> 2026-11-10T030038823632 | 9 changed | quiet |
| 2026-11-10 | `remote/dev.workers.moneytools.x402-pay-precheck/pay-precheck` | 2026-11-09T170225109048 -> 2026-11-10T030037634010 | 114 changed, 3 added | quiet |
| 2026-11-10 | `remote/io.github.moelayyan90/xguard` | 2026-11-08T135745656137 -> 2026-11-10T030035149097 | 3 added | quiet |
| 2026-11-10 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-11-09T071602336191 -> 2026-11-10T030036264800 | 1 added | quiet |
| 2026-11-10 | `remote/io.github.liad142/yedapo` | 2026-11-09T071602634619 -> 2026-11-10T030034718234 | 2 changed (every tool) | quiet |
| 2026-11-10 | `remote/com.starcovery/mcp` | 2026-11-09T170423055716 -> 2026-11-10T030035909713 | 8 changed | quiet |
| 2026-11-10 | `remote/no.restplass/travel-search` | 2026-11-09T191543143895 -> 2026-11-10T030033964889 | 1 changed | quiet |
| 2026-11-10 | `remote/dev.moneytools/tools` | 2026-11-09T170049724278 -> 2026-11-10T030033010006 | 114 changed, 2 added | review |
| 2026-11-10 | `remote/cn.com.bioinformatics/weishengxin` | 2026-11-09T170243037418 -> 2026-11-10T030036349295 | 1 changed, 5 added | quiet |
| 2026-11-10 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-09T071633498270 -> 2026-11-10T030031390819 | 1 changed | quiet |
| 2026-11-10 | `remote/fi.akkilahdot/travel-search` | 2026-11-09T191545482008 -> 2026-11-10T030032420952 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-09T170128656164 -> 2026-11-10T030031382018 | 2 changed | quiet |
| 2026-11-10 | `remote/com.thefomite/fomite` | 2026-11-09T071558556578 -> 2026-11-10T030031436399 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.lewisororke/l50-uk-tenders` | 2026-11-09T170027258203 -> 2026-11-10T030029401130 | 2 added | quiet |
| 2026-11-10 | `remote/io.github.fmind/portfolio` | 2026-11-08T204942383210 -> 2026-11-10T030029740139 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-09T191542428534 -> 2026-11-10T030031181576 | 24 added | review |
| 2026-11-10 | `remote/es.fortsu/mcp` | 2026-11-09T170127690261 -> 2026-11-10T030031023942 | 2 changed | quiet |
| 2026-11-10 | `remote/com.vuntum/mcp` | 2026-11-08T135717132307 -> 2026-11-10T030030313261 | 1 added | quiet |
| 2026-11-10 | `remote/ru.vedarai/mcp` | 2026-11-08T153907238880 -> 2026-11-10T030029456202 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-09T191539678508 -> 2026-11-10T030032913075 | 2 changed | quiet |
| 2026-11-10 | `remote/dev.tanod/tanod` | 2026-11-09T191449624068 -> 2026-11-10T030029078775 | 1 added | quiet |
| 2026-11-10 | `remote/net.swaptitan/swaptitan` | 2026-11-08T135645986169 -> 2026-11-10T030027103318 | 1 changed | quiet |
| 2026-11-10 | `remote/dk.afbudsrejser/travel-search` | 2026-11-09T191535142866 -> 2026-11-10T030026291133 | 1 changed | quiet |
| 2026-11-10 | `remote/io.suverse.versum/catalog` | 2026-11-09T170032315110 -> 2026-11-10T030032443824 | 2 changed | quiet |
| 2026-11-10 | `remote/io.github.BurettoSofuto/smogrank` | 2026-11-08T135626137682 -> 2026-11-10T030023848566 | 1 changed | quiet |
| 2026-11-10 | `remote/com.idosgames/platform` | 2026-11-09T191442044304 -> 2026-11-10T030023337505 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.ohad6k/viberaven-guides` | 2026-11-08T153902705467 -> 2026-11-10T030022948337 | 4 changed | quiet |
| 2026-11-10 | `remote/global.uain/network` | 2026-11-09T191529077177 -> 2026-11-10T030019857301 | 8 changed, 5 removed (every tool) | quiet |
| 2026-11-10 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-09T170104054571 -> 2026-11-10T030021889697 | 1 changed | quiet |
| 2026-11-10 | `remote/com.tetheredtrust/tethered-trust` | 2026-11-09T170056734902 -> 2026-11-10T030019289059 | 1 changed | quiet |
| 2026-11-10 | `remote/dev.workers.rugsight.rugsight/rugsight` | 2026-11-09T165857266006 -> 2026-11-10T030018235883 | 1 changed | quiet |
| 2026-11-10 | `remote/com.trackerhacker/mcp` | 2026-11-09T170216710602 -> 2026-11-10T030018571065 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.exquad/thecablecode` | 2026-11-09T071606108208 -> 2026-11-10T030018728406 | 3 changed | quiet |
| 2026-11-10 | `remote/dev.tesseralytics/hyperliquid-data` | 2026-11-09T165933598200 -> 2026-11-10T030019106985 | 7 changed | quiet |
| 2026-11-10 | `remote/com.forevenza.services/tendmark` | 2026-11-09T170139932891 -> 2026-11-10T030016495437 | 4 added | quiet |
| 2026-11-10 | `remote/com.forevenza.services/quarterline` | 2026-11-09T165828444263 -> 2026-11-10T030016095583 | 4 added | quiet |
| 2026-11-10 | `remote/net.stabledomains/registrar` | 2026-11-09T170026746230 -> 2026-11-10T030015462743 | 12 changed | quiet |
| 2026-11-10 | `remote/com.forevenza.services/stillleaf` | 2026-11-09T170111943066 -> 2026-11-10T030014758158 | 4 added | quiet |
| 2026-11-10 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-09T191522214927 -> 2026-11-10T030012452861 | 1 changed | quiet |
| 2026-11-10 | `remote/com.statisticsoftheworld/sotw` | 2026-11-09T191520459975 -> 2026-11-10T030012970192 | 1 changed | quiet |
| 2026-11-10 | `remote/dev.sourcepost/directory` | 2026-11-09T191509038899 -> 2026-11-10T030012641755 | 1 changed | quiet |
| 2026-11-10 | `remote/com.predictionmarketspicks/quant` | 2026-11-09T165811051297 -> 2026-11-10T030012257318 | 1 changed, 1 added | quiet |
| 2026-11-10 | `remote/com.postthisdeal/handpicked-deals` | 2026-11-09T165807571779 -> 2026-11-10T030014650690 | 4 changed (every tool) | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 52784 substantive, 31219 that changed only numbers (a catalogue counter ticking, a date), 925 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 45137 | 15898 | 29239 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1843 | 1843 | 0 | 0 |
| `caseyjhand.com` | 359 | 359 | 0 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `civai.co` | 234 | 234 | 0 | 0 |
| `sistaminuten.se` | 217 | 6 | 0 | 211 |
| `afbudsrejser.dk` | 216 | 6 | 0 | 210 |
| `akkilahdot.fi` | 216 | 6 | 0 | 210 |
| `restplass.no` | 216 | 6 | 0 | 210 |
| `socialloop.ai` | 208 | 208 | 0 | 0 |
| `revmesh2074.workers.dev` | 197 | 174 | 23 | 0 |
| 8322 other operators | 33486 | 31445 | 1957 | 84 |
