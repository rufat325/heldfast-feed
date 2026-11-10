# MCP server tool changes

Last change observed 2026-11-10T22:02:31+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

88084 changes to a tool definition: 3831 npm releases (3585 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 84253 readings of hosted servers that found their tools changed; 3724 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-10 | `remote/se.sistaminuten/travel-search` | 2026-11-10T153002644782 -> 2026-11-10T220232654664 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.andzar22/offstereo` | 2026-11-10T130414212901 -> 2026-11-10T220230282706 | 2 changed | quiet |
| 2026-11-10 | `remote/com.onlyworlds/mcp` | 2026-11-10T152952764371 -> 2026-11-10T220230713495 | 2 changed | quiet |
| 2026-11-10 | `remote/no.restplass/travel-search` | 2026-11-10T153041086779 -> 2026-11-10T220225945632 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.Andrii-Tiurin/mono-esim` | 2026-11-09T170403059953 -> 2026-11-10T220225426419 | 8 changed | quiet |
| 2026-11-10 | `remote/io.escrova/escrova` | 2026-11-09T170231529255 -> 2026-11-10T220226276426 | 3 changed | quiet |
| 2026-11-10 | `remote/com.coverage-rights/coverage-rights` | 2026-11-10T152929252989 -> 2026-11-10T220224489153 | 10 changed (every tool) | quiet |
| 2026-11-10 | `remote/com.blitzreels/blitzreels` | 2026-11-09T170225381355 -> 2026-11-10T220226552341 | 8 changed | quiet |
| 2026-11-10 | `remote/com.iscabox/iscabox` | 2026-11-10T153025541653 -> 2026-11-10T220225742701 | 2 changed | quiet |
| 2026-11-10 | `remote/io.deeplead/deeplead` | 2026-11-10T153011722066 -> 2026-11-10T220222339864 | 2 changed | quiet |
| 2026-11-10 | `remote/ai.whatsupin/events` | 2026-11-10T152902235314 -> 2026-11-10T220221514062 | 2 changed | quiet |
| 2026-11-10 | `remote/io.github.christianscode1994/volatiai-mcp` | 2026-11-10T152843640873 -> 2026-11-10T220219882621 | 1 changed | quiet |
| 2026-11-10 | `remote/dk.afbudsrejser/travel-search` | 2026-11-10T152957171029 -> 2026-11-10T220220097791 | 1 changed | quiet |
| 2026-11-10 | `remote/com.warminboxes/deliverability-tools` | 2026-11-10T152851950754 -> 2026-11-10T220220810764 | 1 changed | quiet |
| 2026-11-10 | `remote/app.wieldr/radar` | 2026-11-09T191533963009 -> 2026-11-10T220218137783 | 1 changed | quiet |
| 2026-11-10 | `remote/uk.co.reliness/uk-data` | 2026-11-10T152815849798 -> 2026-11-10T220215647127 | 4 added | quiet |
| 2026-11-10 | `remote/com.useaiblocks/library` | 2026-11-09T170244782028 -> 2026-11-10T220214700813 | 8 changed | quiet |
| 2026-11-10 | `remote/ai.uetr/uetr.ai` | 2026-11-09T170235751203 -> 2026-11-10T220218210253 | 2 changed | quiet |
| 2026-11-10 | `remote/fun.trnch/trnch` | 2026-11-10T152907111836 -> 2026-11-10T220212489191 | 1 changed | quiet |
| 2026-11-10 | `remote/com.trackerhacker/mcp` | 2026-11-10T130406374614 -> 2026-11-10T220212074256 | 6 changed | quiet |
| 2026-11-10 | `remote/dev.tanod/tanod` | 2026-11-10T152707644493 -> 2026-11-10T220208867626 | 4 changed | quiet |
| 2026-11-10 | `remote/dev.tanod/docs` | 2026-11-10T130353858582 -> 2026-11-10T220208630043 | 1 changed | quiet |
| 2026-11-10 | `remote/dev.tanod/agents` | 2026-11-10T152706860181 -> 2026-11-10T220207943816 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.majidkabir/sootcase` | 2026-11-10T152629792747 -> 2026-11-10T220201300630 | 5 changed | quiet |
| 2026-11-10 | `remote/io.github.MorrisMoe/soulintime` | 2026-11-09T165944985106 -> 2026-11-10T220201216551 | 2 changed | quiet |
| 2026-11-10 | `remote/agency.zoll/ausfuhr` | 2026-11-09T191559538338 -> 2026-11-10T220201678122 | 2 changed | quiet |
| 2026-11-10 | `remote/fr.synergieloc/immobilier` | 2026-11-10T152808799066 -> 2026-11-10T220157425101 | 8 added | quiet |
| 2026-11-10 | `remote/si.scriptura/scriptura` | 2026-11-10T152550042068 -> 2026-11-10T220155666632 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.kfx2026/sanyu-research` | 2026-11-10T152546879423 -> 2026-11-10T220158238918 | 24 changed, 2 added, 2 removed | quiet |
| 2026-11-10 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-10T130401582529 -> 2026-11-10T220155788683 | 1 added | quiet |
| 2026-11-10 | `remote/uk.renewably/gb-electricity-prices-and-tariffs` | 2026-11-09T165844978798 -> 2026-11-10T220153341057 | 8 changed | quiet |
| 2026-11-10 | `remote/ai.robowrite/mcp` | 2026-11-09T071638143944 -> 2026-11-10T220152140519 | 2 added | quiet |
| 2026-11-10 | `remote/com.youspot/youspot` | 2026-11-10T153336585260 -> 2026-11-10T220149706076 | 19 changed | quiet |
| 2026-11-10 | `remote/io.github.shapeweld/shapeweld` | 2026-11-09T170032456541 -> 2026-11-10T220146924451 | 5 changed (every tool) | quiet |
| 2026-11-10 | `remote/xyz.pokeka/card-prices` | 2026-11-09T165801035296 -> 2026-11-10T220145237932 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.HuangGoodmanAgency/edgar-and-edgarette` | 2026-11-09T170151188076 -> 2026-11-10T220144944502 | 1 added | quiet |
| 2026-11-10 | `remote/io.github.Seifollahi/markolis` | 2026-11-10T030045071584 -> 2026-11-10T220145799353 | 3 changed | quiet |
| 2026-11-10 | `remote/ing.rentseek/evidence` | 2026-11-09T165943917146 -> 2026-11-10T220142896221 | 1 changed | quiet |
| 2026-11-10 | `remote/cz.iustoria/pruvodci` | 2026-11-09T191531455719 -> 2026-11-10T220145215044 | 2 changed, 1 added | quiet |
| 2026-11-10 | `remote/se.aigine/redact` | 2026-11-09T165936524134 -> 2026-11-10T220142546833 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-10T130351251207 -> 2026-11-10T220143195276 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.bostanyshop-rgb/growtsy` | 2026-11-08T135812049792 -> 2026-11-10T220142428761 | 1 changed | quiet |
| 2026-11-10 | `remote/studio.gradients/mcp` | 2026-11-10T152936307543 -> 2026-11-10T220142302044 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.fmind/portfolio` | 2026-11-10T030029740139 -> 2026-11-10T220141596740 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.pbchrist/iconic-agent-marketplace` | 2026-11-10T030006220711 -> 2026-11-10T220141513360 | 3 added | quiet |
| 2026-11-10 | `remote/com.psychologieetserenite/catalogue` | 2026-11-10T130348935341 -> 2026-11-10T220140910003 | 8 changed | quiet |
| 2026-11-10 | `remote/com.eventualclimate/premium-lock` | 2026-11-10T130347675870 -> 2026-11-10T220139974179 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.MikhailSagalaev/openradar` | 2026-11-09T165726277245 -> 2026-11-10T220140531239 | 1 changed | quiet |
| 2026-11-10 | `remote/io.suverse.versum/catalog` | 2026-11-10T130347239443 -> 2026-11-10T220138516942 | 15 changed (every tool) | quiet |
| 2026-11-10 | `remote/io.github.brawlaphant/vealth` | 2026-11-09T071606964338 -> 2026-11-10T220137533444 | 2 changed | quiet |
| 2026-11-10 | `remote/com.daystoic/daystoic` | 2026-11-09T170253802468 -> 2026-11-10T220137004710 | 3 added | quiet |
| 2026-11-10 | `remote/co.civai.nova/mcp-firecrawl` | 2026-11-10T130327915293 -> 2026-11-10T220138346399 | 2 changed | quiet |
| 2026-11-10 | `remote/co.civai.nova/mcp-bgpt-tweet-downloader` | 2026-11-09T165708150358 -> 2026-11-10T220136290654 | 1 added, 1 removed | quiet |
| 2026-11-10 | `remote/co.civai.nova/mcp-bgpt-jiji-recon` | 2026-11-09T165707924296 -> 2026-11-10T220136271308 | 1 added, 23 removed | quiet |
| 2026-11-10 | `remote/co.civai.nova/mcp-bgpt-clannit` | 2026-11-09T165707879305 -> 2026-11-10T220135786982 | 1 added, 11 removed | quiet |
| 2026-11-10 | `remote/com.nibiashara/directory` | 2026-11-09T165656990527 -> 2026-11-10T220134987104 | 1 changed, 2 removed | quiet |
| 2026-11-10 | `remote/co.civai.nova/mcp-bgpt-chowdeck` | 2026-11-09T165707780753 -> 2026-11-10T220135649487 | 1 added, 24 removed | quiet |
| 2026-11-10 | `remote/co.civai.nova/mcp-bgpt-cardpeer` | 2026-11-09T165707673808 -> 2026-11-10T220135606200 | 1 added, 6 removed | quiet |
| 2026-11-10 | `remote/io.github.omercelik/tuneviva` | 2026-11-09T170007312298 -> 2026-11-10T220134216229 | 3 changed (every tool) | quiet |
| 2026-11-10 | `remote/fi.akkilahdot/travel-search` | 2026-11-10T152911324734 -> 2026-11-10T220134669919 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 54038 substantive, 33107 that changed only numbers (a catalogue counter ticking, a date), 939 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 46983 | 15900 | 31083 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1975 | 1975 | 0 | 0 |
| `caseyjhand.com` | 364 | 364 | 0 | 0 |
| `civai.co` | 259 | 259 | 0 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `sistaminuten.se` | 220 | 6 | 0 | 214 |
| `afbudsrejser.dk` | 219 | 6 | 0 | 213 |
| `akkilahdot.fi` | 219 | 6 | 0 | 213 |
| `restplass.no` | 219 | 6 | 0 | 213 |
| `socialloop.ai` | 211 | 211 | 0 | 0 |
| `revmesh2074.workers.dev` | 208 | 185 | 23 | 0 |
| 8561 other operators | 34608 | 32521 | 2001 | 86 |
