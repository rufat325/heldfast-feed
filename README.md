# MCP server tool changes

Last change observed 2026-11-11T07:14:58+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

88349 changes to a tool definition: 3831 npm releases (3585 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 84518 readings of hosted servers that found their tools changed; 3738 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-11 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-11-10T030036264800 -> 2026-11-11T071459461049 | 1 removed | quiet |
| 2026-11-11 | `remote/io.github.liad142/yedapo` | 2026-11-10T030034718234 -> 2026-11-11T071500090089 | 2 changed (every tool) | quiet |
| 2026-11-11 | `remote/no.restplass/travel-search` | 2026-11-10T220225945632 -> 2026-11-11T071457298003 | 1 changed | quiet |
| 2026-11-11 | `remote/io.github.Andrii-Tiurin/mono-esim` | 2026-11-10T220225426419 -> 2026-11-11T071456271448 | 5 added | quiet |
| 2026-11-11 | `remote/io.github.cryptoduke01/gloam` | 2026-11-09T170349509752 -> 2026-11-11T071454042656 | 6 changed | quiet |
| 2026-11-11 | `remote/io.github.jklop3841/agentarchitect-network` | 2026-11-09T170325030210 -> 2026-11-11T071451831647 | 3 added | quiet |
| 2026-11-11 | `remote/dk.afbudsrejser/travel-search` | 2026-11-10T220220097791 -> 2026-11-11T071451754124 | 1 changed | quiet |
| 2026-11-11 | `remote/com.163yu/hetianyu` | 2026-11-10T130416898761 -> 2026-11-11T071452839922 | 1 changed, 2 added | quiet |
| 2026-11-11 | `remote/io.github.Ockram4444/agentcompute` | 2026-11-09T170232207320 -> 2026-11-11T071446507654 | 9 changed, 1 added | quiet |
| 2026-11-11 | `remote/fun.trnch/trnch` | 2026-11-10T220212489191 -> 2026-11-11T071445080958 | 3 changed | quiet |
| 2026-11-11 | `remote/com.supapark/agent-api` | 2026-11-10T152802026026 -> 2026-11-11T071439045264 | 1 changed | quiet |
| 2026-11-11 | `remote/io.github.shivamselam/seminara` | 2026-11-10T152659994700 -> 2026-11-11T071432104691 | 1 added | quiet |
| 2026-11-11 | `remote/com.youspot/youspot` | 2026-11-10T220149706076 -> 2026-11-11T071432825132 | 4 changed | quiet |
| 2026-11-11 | `remote/io.github.homeaccount7/signaldock` | 2026-11-09T170203392231 -> 2026-11-11T071430433247 | 12 changed (every tool) | quiet |
| 2026-11-11 | `remote/io.github.miradero/renderior` | 2026-11-10T030003822933 -> 2026-11-11T071428201097 | 1 added | quiet |
| 2026-11-11 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-11-10T030052146476 -> 2026-11-11T071428235226 | 1 removed | quiet |
| 2026-11-11 | `remote/se.sistaminuten/travel-search` | 2026-11-10T220232654664 -> 2026-11-11T071425435926 | 1 changed | quiet |
| 2026-11-11 | `remote/io.taifoon/coordination-layer.1` | 2026-11-09T071620204048 -> 2026-11-11T071425918426 | 1 changed | quiet |
| 2026-11-11 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-10T220143195276 -> 2026-11-11T071426804656 | 2 changed | quiet |
| 2026-11-11 | `remote/com.onlyworlds/mcp` | 2026-11-10T220230713495 -> 2026-11-11T071423384122 | 2 changed | quiet |
| 2026-11-11 | `remote/io.suverse.versum/catalog` | 2026-11-10T220138516942 -> 2026-11-11T071422155044 | 3 changed | quiet |
| 2026-11-11 | `remote/ai.robowrite/mcp` | 2026-11-10T220152140519 -> 2026-11-11T071421410035 | 2 changed | quiet |
| 2026-11-11 | `remote/com.partstable/partstable` | 2026-11-10T130340887171 -> 2026-11-11T071421724340 | 1 changed | quiet |
| 2026-11-11 | `remote/io.pokeinvest/prices` | 2026-11-09T170338543748 -> 2026-11-11T071420446595 | 1 changed | quiet |
| 2026-11-11 | `remote/io.escrova/escrova` | 2026-11-10T220226276426 -> 2026-11-11T071419539634 | 10 added | quiet |
| 2026-11-11 | `remote/com.triremes/triremes` | 2026-11-10T153102585834 -> 2026-11-11T071417916555 | 4 changed (every tool) | quiet |
| 2026-11-11 | `remote/com.blitzreels/blitzreels` | 2026-11-10T220226552341 -> 2026-11-11T071420024736 | 1 changed | quiet |
| 2026-11-11 | `remote/co.civai.nova/mcp-bgpt-polymarket` | 2026-11-10T220132003608 -> 2026-11-11T071417598761 | 18 added, 1 removed | quiet |
| 2026-11-11 | `remote/co.civai.nova/mcp-bgpt-giglogistics` | 2026-11-10T220131936088 -> 2026-11-11T071417474045 | 1 added, 1 removed | quiet |
| 2026-11-11 | `remote/co.civai.nova/mcp-apple_developer` | 2026-11-10T220131752358 -> 2026-11-11T071417552548 | 55 added, 1 removed | quiet |
| 2026-11-11 | `remote/co.civai.nova/mcp-apple_ads` | 2026-11-10T220131550335 -> 2026-11-11T071417475840 | 25 added, 1 removed | quiet |
| 2026-11-11 | `remote/co.civai.nova/mcp-android_developer` | 2026-11-10T220131256067 -> 2026-11-11T071416902589 | 38 added, 1 removed | quiet |
| 2026-11-11 | `remote/fi.northpoint/marketing-compliance` | 2026-11-10T152441675265 -> 2026-11-11T071416858185 | 1 added | quiet |
| 2026-11-11 | `remote/co.totalcms/docs` | 2026-11-10T153055674244 -> 2026-11-11T071417223685 | 3 changed | quiet |
| 2026-11-11 | `remote/ai.whatsupin/events` | 2026-11-10T220221514062 -> 2026-11-11T071416078641 | 1 changed | quiet |
| 2026-11-11 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-10T220131764132 -> 2026-11-11T071415882892 | 2 changed, 2 added | quiet |
| 2026-11-11 | `remote/ro.simoshop/catalog` | 2026-11-09T170115402386 -> 2026-11-11T071414793595 | 2 changed, 1 added (every tool) | quiet |
| 2026-11-11 | `remote/il.co.taseli/taseli.1` | 2026-11-10T153017470093 -> 2026-11-11T071412281195 | 1 changed | quiet |
| 2026-11-11 | `remote/studio.gradients/mcp` | 2026-11-10T220142302044 -> 2026-11-11T071411673043 | 1 changed | quiet |
| 2026-11-11 | `remote/com.whywontai/ai-visibility` | 2026-11-10T220123884870 -> 2026-11-11T071410105541 | 3 changed | quiet |
| 2026-11-11 | `remote/com.thefomite/fomite` | 2026-11-10T030031436399 -> 2026-11-11T071408576833 | 1 changed | quiet |
| 2026-11-11 | `remote/com.teppek/teppek` | 2026-11-10T220123565662 -> 2026-11-11T071409093900 | 1 changed | quiet |
| 2026-11-11 | `remote/network.skv/skv` | 2026-11-10T030012415863 -> 2026-11-11T071408286445 | 3 changed | quiet |
| 2026-11-11 | `remote/io.github.bucharitesh/qrdx` | 2026-11-09T165607832334 -> 2026-11-11T071405858212 | 3 changed, 2 added | quiet |
| 2026-11-11 | `remote/fi.akkilahdot/travel-search` | 2026-11-10T220134669919 -> 2026-11-11T071404930378 | 1 changed | quiet |
| 2026-11-11 | `remote/cn.com.bioinformatics/weishengxin` | 2026-11-10T130425541423 -> 2026-11-11T071410506200 | 1 changed | quiet |
| 2026-11-11 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-11-10T030008546566 -> 2026-11-11T071404140187 | 1 changed | quiet |
| 2026-11-11 | `remote/net.pendingdelete/mcp` | 2026-11-10T130323055654 -> 2026-11-11T071403047380 | 1 changed | quiet |
| 2026-11-11 | `remote/io.github.oon4am-eng/hold` | 2026-11-10T130419961606 -> 2026-11-11T071402658793 | 2 changed, 2 added | quiet |
| 2026-11-11 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-10T030031390819 -> 2026-11-11T071403253430 | 1 changed | quiet |
| 2026-11-11 | `remote/io.github.cryptoconspiracy/vurto-swap` | 2026-11-10T130351624778 -> 2026-11-11T071403530295 | 7 changed | quiet |
| 2026-11-11 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-10T220134527123 -> 2026-11-11T071403872420 | 24 added | review |
| 2026-11-11 | `remote/ai.rollingedition/books` | 2026-11-09T165743995183 -> 2026-11-11T071402662988 | 1 added | quiet |
| 2026-11-11 | `remote/com.vuntum/mcp` | 2026-11-10T030030313261 -> 2026-11-11T071402383803 | 13 added | quiet |
| 2026-11-11 | `remote/ru.vedarai/mcp` | 2026-11-10T220131983248 -> 2026-11-11T071401966882 | 1 changed | quiet |
| 2026-11-11 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-10T220131486455 -> 2026-11-11T071400900516 | 3 changed | quiet |
| 2026-11-11 | `remote/au.com.nationaldigital/website` | 2026-11-10T152238201104 -> 2026-11-11T071400887967 | 1 changed | quiet |
| 2026-11-11 | `remote/io.github.quartzondev/qr-branding` | 2026-11-10T220118252920 -> 2026-11-11T071404694936 | 1 added | quiet |
| 2026-11-11 | `remote/io.github.Steven3265/moyneross` | 2026-11-10T130319654619 -> 2026-11-11T071359714596 | 2 changed | quiet |
| 2026-11-11 | `remote/com.midgardfinance/drugs` | 2026-11-10T152231720571 -> 2026-11-11T071400093501 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 54280 substantive, 33125 that changed only numbers (a catalogue counter ticking, a date), 944 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 46983 | 15900 | 31083 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1975 | 1975 | 0 | 0 |
| `caseyjhand.com` | 364 | 364 | 0 | 0 |
| `civai.co` | 282 | 282 | 0 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `sistaminuten.se` | 221 | 6 | 0 | 215 |
| `afbudsrejser.dk` | 220 | 6 | 0 | 214 |
| `akkilahdot.fi` | 220 | 6 | 0 | 214 |
| `restplass.no` | 220 | 6 | 0 | 214 |
| `revmesh2074.workers.dev` | 214 | 191 | 23 | 0 |
| `socialloop.ai` | 212 | 212 | 0 | 0 |
| 8592 other operators | 34839 | 32733 | 2019 | 87 |
