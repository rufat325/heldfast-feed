# MCP server tool changes

Last change observed 2026-10-26T13:39:28+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

52564 changes to a tool definition: 2293 npm releases (2047 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 50271 readings of hosted servers that found their tools changed; 2737 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-26 | `remote/xn--3ds443g.xn--s7y/duan-online` | 2026-10-17T185402935212 -> 2026-10-26T133929927228 | 1 changed | quiet |
| 2026-10-26 | `remote/io.github.vanakenj45/x402-agent-api` | 2026-10-19T135522929643 -> 2026-10-26T133922591157 | 2 changed | review |
| 2026-10-26 | `remote/ai.usedby/usedby` | 2026-10-25T191849450703 -> 2026-10-26T133920435468 | 3 changed, 1 added | quiet |
| 2026-10-26 | `remote/io.taifoon/coordination-layer.1` | 2026-10-26T052257124574 -> 2026-10-26T133915989900 | 1 changed | review |
| 2026-10-26 | `remote/ai.snowsure/snow` | 2026-10-23T200842811666 -> 2026-10-26T133912998115 | 1 changed | quiet |
| 2026-10-26 | `remote/se.sistaminuten/travel-search` | 2026-10-26T052256753882 -> 2026-10-26T133911843790 | 1 changed | quiet |
| 2026-10-26 | `remote/com.onecoworking.www/mcp` | 2026-10-19T135508307852 -> 2026-10-26T133904850222 | 1 changed, 2 added | quiet |
| 2026-10-26 | `remote/io.github.junoventures/graciebarrajiujitsu-site` | 2026-09-23T161027128641 -> 2026-10-26T133854580458 | 1 changed | quiet |
| 2026-10-26 | `remote/io.github.junoventures/filipe-coffee` | 2026-09-23T161026218452 -> 2026-10-26T133850862362 | 1 changed | quiet |
| 2026-10-26 | `remote/com.followontours/cricket-travel` | 2026-10-12T181443141969 -> 2026-10-26T133851031437 | 8 changed (every tool) | quiet |
| 2026-10-26 | `remote/io.github.alex0xhodler/defi-garden` | 2026-10-06T110145129725 -> 2026-10-26T133846575928 | 1 changed | quiet |
| 2026-10-26 | `remote/ai.yentaknows/directory` | 2026-10-22T110329479888 -> 2026-10-26T133826127248 | 2 changed | quiet |
| 2026-10-26 | `remote/io.github.wegravel/zensei-mcp` | 2026-10-06T110337195234 -> 2026-10-26T133819742258 | 4 changed, 8 added (every tool) | quiet |
| 2026-10-26 | `remote/io.github.junoventures/vilamadalena-sampa-br` | 2026-09-23T161008335930 -> 2026-10-26T133806635632 | 1 changed | quiet |
| 2026-10-26 | `remote/io.github.junoventures/vilabuarque-sampa-br` | 2026-09-23T161008302177 -> 2026-10-26T133806174647 | 1 changed | quiet |
| 2026-10-26 | `remote/no.restplass/travel-search` | 2026-10-26T052302625230 -> 2026-10-26T133803916694 | 1 changed | quiet |
| 2026-10-26 | `remote/app.postel/postel` | 2026-10-06T110329818283 -> 2026-10-26T133801309104 | 6 changed, 2 added | quiet |
| 2026-10-26 | `remote/com.usanaru/schools` | 2026-10-22T105855100449 -> 2026-10-26T133753671646 | 1 changed | quiet |
| 2026-10-26 | `remote/io.github.cryptoduke01/gloam` | 2026-10-25T225212344393 -> 2026-10-26T133747071952 | 5 changed | quiet |
| 2026-10-26 | `remote/com.naxytra/xytara-mcp-executor` | 2026-10-20T104419126307 -> 2026-10-26T133745987950 | 14 added | review |
| 2026-10-26 | `remote/dev.trudex/trudex.1` | 2026-10-24T112823976907 -> 2026-10-26T133741295472 | 1 changed | quiet |
| 2026-10-26 | `remote/io.github.junoventures/dojoplus-co` | 2026-10-03T121336679073 -> 2026-10-26T133737292506 | 1 changed | quiet |
| 2026-10-26 | `remote/com.droneclearthailand/droneclear-thailand` | 2026-10-17T060431977335 -> 2026-10-26T133738412414 | 2 changed (every tool) | quiet |
| 2026-10-26 | `remote/dk.afbudsrejser/travel-search` | 2026-10-26T052259123876 -> 2026-10-26T133725826284 | 1 changed | quiet |
| 2026-10-26 | `remote/io.github.junoventures/tatuape-sampa-br` | 2026-09-23T160854408485 -> 2026-10-26T133742092797 | 1 changed | quiet |
| 2026-10-26 | `remote/com.rightshold/rightshold` | 2026-10-20T232808413120 -> 2026-10-26T133712193081 | 1 changed | quiet |
| 2026-10-26 | `remote/com.tabzoola/pricing` | 2026-10-18T224000420903 -> 2026-10-26T133708354311 | 1 changed | quiet |
| 2026-10-26 | `remote/ai.svtr/aidb` | 2026-10-20T104207949601 -> 2026-10-26T133709600215 | 1 changed | quiet |
| 2026-10-26 | `remote/io.github.junoventures/vilamariana-sampa-br` | 2026-09-23T163103978236 -> 2026-10-26T133702851137 | 1 changed | quiet |
| 2026-10-26 | `remote/com.sssnack/sssnack` | 2026-10-19T211957349161 -> 2026-10-26T133654434537 | 4 changed | quiet |
| 2026-10-26 | `remote/dev.sparkpay/sparkpay` | 2026-09-27T131111592577 -> 2026-10-26T133650101555 | 25 changed (every tool) | quiet |
| 2026-10-26 | `remote/is.envelop.unisafe/insight` | 2026-10-22T110157781325 -> 2026-10-26T133647294359 | 1 added | quiet |
| 2026-10-26 | `remote/io.engineeringleaders/elc-trade` | 2026-10-25T102943403798 -> 2026-10-26T133644220130 | 1 changed | quiet |
| 2026-10-26 | `remote/dev.sitemcp/site-mcp` | 2026-09-30T060126448452 -> 2026-10-26T133641996023 | 4 changed, 2 added | review |
| 2026-10-26 | `remote/com.trustbaselab/rcb-data` | 2026-10-26T052255461650 -> 2026-10-26T133638014334 | 1 changed | quiet |
| 2026-10-26 | `remote/ai.trydock/dock` | 2026-10-25T052256456529 -> 2026-10-26T133637756161 | 2 changed | quiet |
| 2026-10-26 | `remote/io.github.CustomBlinds/cb-shop` | 2026-10-23T120701389593 -> 2026-10-26T133635645045 | 5 changed | quiet |
| 2026-10-26 | `remote/com.shipshapedata/shipshape-data-docs` | 2026-10-25T102327908544 -> 2026-10-26T133634439366 | 1 changed | quiet |
| 2026-10-26 | `remote/com.anthonyhunts/shaart-agency` | 2026-09-29T061636672445 -> 2026-10-26T133630570825 | 1 changed | quiet |
| 2026-10-26 | `remote/com.adrenalinelist/adventures` | 2026-10-17T060328540743 -> 2026-10-26T133628708063 | 4 changed (every tool) | quiet |
| 2026-10-26 | `remote/info.workingproxysites/provider-directory` | 2026-10-06T110232035606 -> 2026-10-26T133623703930 | 1 changed | quiet |
| 2026-10-26 | `remote/ru.zavod-stanki/cnc-catalog` | 2026-10-17T060006052920 -> 2026-10-26T133623406598 | 2 changed | quiet |
| 2026-10-26 | `remote/in.co.yogamag/yogamag` | 2026-10-19T135619726997 -> 2026-10-26T133621058254 | 6 added | quiet |
| 2026-10-26 | `remote/io.github.speeedy10/foxify-x402-agent-commerce-payment-preflight` | 2026-09-24T120514856235 -> 2026-10-26T133618872802 | 3 changed (every tool) | quiet |
| 2026-10-26 | `remote/io.github.physics-star-cat/whatbreaks-mot` | 2026-10-03T121321605293 -> 2026-10-26T133617262079 | 2 changed (every tool) | quiet |
| 2026-10-26 | `remote/org.thealibrary/thea` | 2026-10-25T191902829841 -> 2026-10-26T133612032570 | 1 changed | quiet |
| 2026-10-26 | `remote/io.github.Z4KARY/upgrowth-mcp` | 2026-10-23T120710208994 -> 2026-10-26T133613225037 | 1 changed | quiet |
| 2026-10-26 | `remote/ai.robowrite/mcp` | 2026-10-17T055952653705 -> 2026-10-26T133556218487 | 2 changed | quiet |
| 2026-10-26 | `remote/ru.quintadb/mcp` | 2026-10-19T135204046884 -> 2026-10-26T133551401351 | 1 changed | quiet |
| 2026-10-26 | `remote/design.overflow/mcp` | 2026-10-24T190436310713 -> 2026-10-26T133549760075 | 1 changed | quiet |
| 2026-10-26 | `remote/io.github.imokokok/insight-oracle` | 2026-10-25T225103979101 -> 2026-10-26T133549392050 | 1 changed, 5 added | review |
| 2026-10-26 | `remote/fr.synergieloc/immobilier` | 2026-10-26T052252603966 -> 2026-10-26T133547872559 | 1 changed, 11 added | quiet |
| 2026-10-26 | `remote/com.sunshineatlas/sunshine-atlas` | 2026-10-17T060323705781 -> 2026-10-26T133541803330 | 2 changed | quiet |
| 2026-10-26 | `remote/com.programscape/programscape` | 2026-10-23T200822298685 -> 2026-10-26T133540670440 | 3 changed | quiet |
| 2026-10-26 | `remote/es.proceres/proceres` | 2026-10-19T135151815071 -> 2026-10-26T133538657355 | 6 changed, 17 added | quiet |
| 2026-10-26 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-10-25T225143008469 -> 2026-10-26T133534613926 | 4 removed | quiet |
| 2026-10-26 | `remote/studio.gradients/mcp` | 2026-10-26T052336747288 -> 2026-10-26T133533268991 | 1 changed | quiet |
| 2026-10-26 | `remote/io.github.junoventures/genesis-social` | 2026-09-23T162941847054 -> 2026-10-26T133530351302 | 1 changed | quiet |
| 2026-10-26 | `remote/ru.zavod-stanki/cnc-catalog.1` | 2026-10-17T060316896785 -> 2026-10-26T133531539696 | 2 changed | quiet |
| 2026-10-26 | `remote/at.space-core/game` | 2026-10-25T102344180986 -> 2026-10-26T133523157631 | 13 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 34409 substantive, 17499 that changed only numbers (a catalogue counter ticking, a date), 656 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 28526 | 12158 | 16368 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 891 | 891 | 0 | 0 |
| `caseyjhand.com` | 231 | 231 | 0 | 0 |
| `sistaminuten.se` | 155 | 4 | 0 | 151 |
| `afbudsrejser.dk` | 154 | 4 | 0 | 150 |
| `akkilahdot.fi` | 154 | 4 | 0 | 150 |
| `restplass.no` | 154 | 4 | 0 | 150 |
| `socialloop.ai` | 149 | 149 | 0 | 0 |
| `remoshift.com` | 124 | 8 | 116 | 0 |
| `fundinglandscape.com` | 119 | 77 | 42 | 0 |
| `openkrill.app` | 112 | 112 | 0 | 0 |
| 5767 other operators | 19454 | 18426 | 973 | 55 |
