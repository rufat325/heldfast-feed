# MCP server tool changes

Last change observed 2026-11-11T23:09:49+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

91499 changes to a tool definition: 3941 npm releases (3695 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 87558 readings of hosted servers that found their tools changed; 3796 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-11 | `remote/com.yazilimkocu/erp` | 2026-11-09T170404575514 -> 2026-11-11T230952741415 | 1 added | quiet |
| 2026-11-11 | `remote/com.yazilimkocu/crm` | 2026-11-09T170404463014 -> 2026-11-11T230952608345 | 1 added | quiet |
| 2026-11-11 | `remote/ai.robowrite/mcp` | 2026-11-11T071421410035 -> 2026-11-11T230946836492 | 1 changed | quiet |
| 2026-11-11 | `remote/io.github.PettyMiggzy/oversize-escort-hub` | 2026-11-09T170334534634 -> 2026-11-11T230941817241 | 2 changed | quiet |
| 2026-11-11 | `remote/studio.gradients/mcp` | 2026-11-11T164206802937 -> 2026-11-11T230934744772 | 1 changed | quiet |
| 2026-11-11 | `remote/com.yazilimkocu/ajan` | 2026-11-09T170435554792 -> 2026-11-11T230932592114 | 1 added | quiet |
| 2026-11-11 | `remote/no.restplass/travel-search` | 2026-11-11T164114662557 -> 2026-11-11T230930131373 | 1 changed | quiet |
| 2026-11-11 | `remote/loans.sbaexpress.www/sbaexpress-loans` | 2026-11-09T170416224994 -> 2026-11-11T230936197947 | 1 changed, 11 added | quiet |
| 2026-11-11 | `remote/com.nomosprotocol/nomos` | 2026-11-09T170405848331 -> 2026-11-11T230929287218 | 1 changed | quiet |
| 2026-11-11 | `remote/ai.makeviral/makeviral` | 2026-11-09T170359580371 -> 2026-11-11T230928005761 | 11 added | quiet |
| 2026-11-11 | `remote/com.iscabox/iscabox` | 2026-11-10T220225742701 -> 2026-11-11T230929395620 | 1 changed | quiet |
| 2026-11-11 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-10T152919313429 -> 2026-11-11T230927535975 | 1 changed | quiet |
| 2026-11-11 | `remote/io.deeplead/deeplead` | 2026-11-10T220222339864 -> 2026-11-11T230926384187 | 7 changed | quiet |
| 2026-11-11 | `remote/fi.akkilahdot/travel-search` | 2026-11-11T164203942620 -> 2026-11-11T230925974969 | 1 changed | quiet |
| 2026-11-11 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-11T071403872420 -> 2026-11-11T230927108218 | 24 added | quiet |
| 2026-11-11 | `remote/dk.afbudsrejser/travel-search` | 2026-11-11T164108406465 -> 2026-11-11T230923782952 | 1 changed | quiet |
| 2026-11-11 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-11T164200101373 -> 2026-11-11T230923694954 | 1 changed | quiet |
| 2026-11-11 | `remote/io.github.itsryanarmani/winecellarbuilders` | 2026-11-09T170323260791 -> 2026-11-11T230922017724 | 11 changed (every tool) | quiet |
| 2026-11-11 | `remote/io.github.itsryanarmani/voiceagents` | 2026-11-09T170300051572 -> 2026-11-11T230920680168 | 11 changed (every tool) | quiet |
| 2026-11-11 | `remote/gg.unicum/wot-stats` | 2026-11-10T220130644351 -> 2026-11-11T230921011736 | 1 changed, 2 added | quiet |
| 2026-11-11 | `remote/dev.zambo/zambo` | 2026-11-10T153336720371 -> 2026-11-11T230918042228 | 1 added | quiet |
| 2026-11-11 | `remote/ai.trydock/dock` | 2026-11-11T145736529916 -> 2026-11-11T230916859022 | 1 changed | quiet |
| 2026-11-11 | `remote/com.trackerhacker/mcp` | 2026-11-11T145729881314 -> 2026-11-11T230916417941 | 22 changed, 4 added | quiet |
| 2026-11-11 | `remote/io.github.itsryanarmani/tmsclinics` | 2026-11-09T170209609702 -> 2026-11-11T230915697163 | 11 changed (every tool) | quiet |
| 2026-11-11 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-11T145931258963 -> 2026-11-11T230917024193 | 2 changed | quiet |
| 2026-11-11 | `remote/com.yazilimkocu/pazaryeri` | 2026-11-09T170221201698 -> 2026-11-11T230916064339 | 1 added | quiet |
| 2026-11-11 | `remote/com.tamingdns/mcp` | 2026-11-11T164148892958 -> 2026-11-11T230911765656 | 1 changed, 3 added | quiet |
| 2026-11-11 | `remote/com.swellcabin/surf` | 2026-11-11T145909212968 -> 2026-11-11T230910327267 | 1 changed | quiet |
| 2026-11-11 | `remote/com.googleapis.stitch/mcp` | 2026-11-11T145858926869 -> 2026-11-11T230908811585 | 7 changed | quiet |
| 2026-11-11 | `remote/net.stabledomains/registrar` | 2026-11-11T145851846472 -> 2026-11-11T230907487580 | 4 changed | review |
| 2026-11-11 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-11T150008969702 -> 2026-11-11T230908279667 | 1 changed | quiet |
| 2026-11-11 | `remote/com.spacexploration/listings` | 2026-11-11T145627011770 -> 2026-11-11T230905751611 | 1 changed | quiet |
| 2026-11-11 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-11T164142328688 -> 2026-11-11T230904453049 | 1 changed | quiet |
| 2026-11-11 | `remote/io.github.itsryanarmani/soberbars` | 2026-11-09T170052307430 -> 2026-11-11T230905727063 | 11 changed (every tool) | quiet |
| 2026-11-11 | `remote/io.github.itsryanarmani/sleepstudies` | 2026-11-09T170012992274 -> 2026-11-11T230903976028 | 11 changed (every tool) | quiet |
| 2026-11-11 | `remote/com.zaimhub/catalog` | 2026-11-10T153036582230 -> 2026-11-11T230904208849 | 4 changed | quiet |
| 2026-11-11 | `remote/io.github.QDThead/signal-lab` | 2026-11-11T145824302507 -> 2026-11-11T230902180048 | 3 changed | quiet |
| 2026-11-11 | `remote/com.yazilimkocu/yapayzeka` | 2026-11-09T170315986830 -> 2026-11-11T230900927292 | 1 added | quiet |
| 2026-11-11 | `remote/com.xmlvalid/xmlvalid` | 2026-11-09T170323173412 -> 2026-11-11T230902411348 | 4 changed | quiet |
| 2026-11-11 | `remote/io.suverse.versum/catalog` | 2026-11-11T164115978613 -> 2026-11-11T230902402065 | 1 changed | quiet |
| 2026-11-11 | `remote/com.yazilimkocu/belediye` | 2026-11-09T170315888099 -> 2026-11-11T230900862808 | 1 added | quiet |
| 2026-11-11 | `remote/com.serviche/sergio` | 2026-11-10T152639991045 -> 2026-11-11T230903207177 | 1 changed, 1 added | quiet |
| 2026-11-11 | `remote/se.sistaminuten/travel-search` | 2026-11-11T164135611535 -> 2026-11-11T230858656816 | 1 changed | quiet |
| 2026-11-11 | `remote/io.github.itsryanarmani/robotaxis` | 2026-11-09T165955651893 -> 2026-11-11T230859716762 | 11 changed (every tool) | quiet |
| 2026-11-11 | `remote/io.github.miradero/renderior` | 2026-11-11T071428201097 -> 2026-11-11T230856776718 | 1 added | quiet |
| 2026-11-11 | `remote/io.github.cryptosun/proximens-oracle` | 2026-11-09T170255031150 -> 2026-11-11T230857784961 | 3 changed | quiet |
| 2026-11-11 | `remote/se.aigine/redact` | 2026-11-11T145504863577 -> 2026-11-11T230857585249 | 3 changed (every tool) | quiet |
| 2026-11-11 | `remote/org.room-ly/roomly` | 2026-11-10T220109474394 -> 2026-11-11T230854945883 | 1 changed | quiet |
| 2026-11-11 | `remote/com.menloinsurance/mcp` | 2026-11-11T150002949500 -> 2026-11-11T230903358479 | 2 changed | quiet |
| 2026-11-11 | `remote/com.mailbypony/mail-by-pony` | 2026-11-09T191509592610 -> 2026-11-11T230855166463 | 1 changed, 1 added | quiet |
| 2026-11-11 | `remote/io.ringler/ringler` | 2026-11-10T220108715134 -> 2026-11-11T230854105632 | 4 changed | quiet |
| 2026-11-11 | `remote/com.eventualclimate/premium-lock` | 2026-11-10T220139974179 -> 2026-11-11T230854188167 | 7 changed (every tool) | quiet |
| 2026-11-11 | `remote/io.github.itsryanarmani/privatedock` | 2026-11-09T165914185119 -> 2026-11-11T230854789511 | 11 changed (every tool) | quiet |
| 2026-11-11 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-11T071415882892 -> 2026-11-11T230854407801 | 1 changed, 2 added | quiet |
| 2026-11-11 | `remote/io.github.richardsolomou/praetorium` | 2026-11-11T145440686928 -> 2026-11-11T230853884276 | 10 changed, 28 added | quiet |
| 2026-11-11 | `remote/io.escrova/escrova` | 2026-11-11T164131397110 -> 2026-11-11T230853266995 | 1 changed | quiet |
| 2026-11-11 | `remote/io.github.exquad/thecablecode` | 2026-11-11T164106229486 -> 2026-11-11T230852777365 | 2 changed | quiet |
| 2026-11-11 | `remote/com.coveragecat/insurance` | 2026-11-11T145944294123 -> 2026-11-11T230851673263 | 1 changed | quiet |
| 2026-11-11 | `remote/no.pristavla/pristavla` | 2026-11-11T071334225880 -> 2026-11-11T230850964621 | 1 changed | quiet |
| 2026-11-11 | `remote/com.blitzreels/blitzreels` | 2026-11-11T071420024736 -> 2026-11-11T230852594783 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 57360 substantive, 33180 that changed only numbers (a catalogue counter ticking, a date), 959 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 48830 | 17746 | 31084 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 2108 | 2108 | 0 | 0 |
| `caseyjhand.com` | 383 | 383 | 0 | 0 |
| `civai.co` | 309 | 309 | 0 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `revmesh2074.workers.dev` | 230 | 202 | 28 | 0 |
| `sistaminuten.se` | 224 | 6 | 0 | 218 |
| `afbudsrejser.dk` | 223 | 6 | 0 | 217 |
| `akkilahdot.fi` | 223 | 6 | 0 | 217 |
| `restplass.no` | 223 | 6 | 0 | 217 |
| `socialloop.ai` | 215 | 215 | 0 | 0 |
| 8819 other operators | 35932 | 33774 | 2068 | 90 |
