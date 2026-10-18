# MCP server tool changes

Last change observed 2026-10-18T12:51:09+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10495 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 23695 hosted endpoints (read daily, and every four hours while they keep changing).

32500 changes to a tool definition: 1188 npm releases (942 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 31312 readings of hosted servers that found their tools changed; 2092 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-18 | `remote/no.restplass/travel-search` | 2026-10-18T113414100701 -> 2026-10-18T125110772277 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.Fizzl13/x402-doctor` | 2026-10-17T060420311410 -> 2026-10-18T125104323141 | 6 changed | quiet |
| 2026-10-18 | `remote/se.sistaminuten/travel-search` | 2026-10-18T113504797314 -> 2026-10-18T125102100855 | 1 changed | quiet |
| 2026-10-18 | `remote/fi.akkilahdot/travel-search` | 2026-10-18T113251061459 -> 2026-10-18T125101539126 | 1 changed | quiet |
| 2026-10-18 | `remote/dk.afbudsrejser/travel-search` | 2026-10-18T113342685871 -> 2026-10-18T125059459527 | 1 changed | quiet |
| 2026-10-18 | `remote/tips.suggestionbox/suggestionbox` | 2026-10-17T055457548506 -> 2026-10-18T125046912904 | 2 changed (every tool) | quiet |
| 2026-10-18 | `remote/app.steadywrk/mcp-dispatch` | 2026-10-18T113155151762 -> 2026-10-18T125044882228 | 1 changed, 1 added | quiet |
| 2026-10-18 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-18T113147480162 -> 2026-10-18T125043495277 | 1 changed | quiet |
| 2026-10-18 | `remote/com.siliconfloor/silicon-floor` | 2026-10-17T055444962098 -> 2026-10-18T125042552012 | 1 changed | quiet |
| 2026-10-18 | `remote/com.remoshift/jobs` | 2026-10-18T113109443534 -> 2026-10-18T125039456652 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.wygogogo19/robotbase-mcp` | 2026-10-17T155958029702 -> 2026-10-18T125038402384 | 6 added | quiet |
| 2026-10-18 | `remote/com.plainrecords/us-recalls-food-products-vehicles` | 2026-10-17T185331094588 -> 2026-10-18T125033549748 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.Fizzl13/presign-guard` | 2026-10-17T060148124230 -> 2026-10-18T125032594656 | 5 changed | quiet |
| 2026-10-18 | `remote/io.github.nimbusbci/nimbus-mcp` | 2026-10-17T224409292090 -> 2026-10-18T125016106320 | 3 changed, 1 added | quiet |
| 2026-10-18 | `remote/com.hireahelper/mcp` | 2026-10-17T155911948598 -> 2026-10-18T125012392921 | 16 added | quiet |
| 2026-10-18 | `remote/io.github.daniel3303/equibles` | 2026-10-18T112813037388 -> 2026-10-18T125009621368 | 2 changed, 1 added | quiet |
| 2026-10-18 | `remote/tech.kaiku/kaiku.1` | 2026-10-18T112920471558 -> 2026-10-18T124956076677 | 2 changed | quiet |
| 2026-10-18 | `remote/app.himalayas/mcp` | 2026-10-18T112910088672 -> 2026-10-18T124954970690 | 4 changed, 2 added | quiet |
| 2026-10-18 | `remote/io.github.qxxx5vyd77-byte/directors-lookbook` | 2026-10-17T224309592510 -> 2026-10-18T124952577416 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.Fizzl13/ichimoku-signal` | 2026-10-17T055220749401 -> 2026-10-18T124948920108 | 5 changed | quiet |
| 2026-10-18 | `remote/io.github.Dahliyaal/justicelibre` | 2026-10-17T055735449913 -> 2026-10-18T124949738061 | 6 changed | quiet |
| 2026-10-18 | `remote/co.ainumbers/tools` | 2026-10-18T112816336159 -> 2026-10-18T124948561980 | 2 changed | quiet |
| 2026-10-18 | `remote/store.getsoma/soma-brewing` | 2026-10-17T055156009954 -> 2026-10-18T124944239617 | 1 changed | quiet |
| 2026-10-18 | `remote/com.faceabot/capability-network` | 2026-10-17T185237618830 -> 2026-10-18T124940173788 | 1 added | quiet |
| 2026-10-18 | `remote/com.payperfax/fax` | 2026-10-17T054545560563 -> 2026-10-18T124928238073 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.UnityNodes/canton-ccpedia` | 2026-10-18T051209313532 -> 2026-10-18T124921480741 | 2 changed | quiet |
| 2026-10-18 | `remote/io.github.cyanheads/brapi-mcp-server` | 2026-10-18T112419975682 -> 2026-10-18T124918778630 | 5 changed | quiet |
| 2026-10-18 | `remote/com.avahit/catalog` | 2026-10-18T112338453835 -> 2026-10-18T124918625198 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.pressa-dev/pressa` | 2026-10-18T112252062495 -> 2026-10-18T124911253891 | 2 changed | quiet |
| 2026-10-18 | `remote/com.prereason/mcp` | 2026-10-18T112251837874 -> 2026-10-18T124910815718 | 1 changed | quiet |
| 2026-10-18 | `remote/com.car-gene/genealogy` | 2026-10-17T105548735032 -> 2026-10-18T124904994401 | 1 changed | quiet |
| 2026-10-18 | `remote/ai.betslipdoctor/mcp` | 2026-10-18T112059339096 -> 2026-10-18T124901900730 | 3 changed, 1 added | quiet |
| 2026-10-18 | `remote/com.currencyguard/guard-pricing` | 2026-10-17T105542212231 -> 2026-10-18T124859971634 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.jonahthan433/cortexcloud` | 2026-10-17T105541588408 -> 2026-10-18T124901373560 | 17 added, 4 removed | review |
| 2026-10-18 | `remote/ai.analyticslegends/sap-analytics` | 2026-10-17T054159443277 -> 2026-10-18T124859026479 | 2 changed | quiet |
| 2026-10-18 | `remote/io.github.agentstacktech/agentstack` | 2026-10-17T065207161696 -> 2026-10-18T124853794528 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.mytomclinic/agent-financial-advisor` | 2026-10-17T053848925961 -> 2026-10-18T124850162289 | 1 changed, 1 added | review |
| 2026-10-18 | `remote/io.github.Nutshell2000/agent-data-tools` | 2026-10-18T111929868593 -> 2026-10-18T124848660829 | 30 changed, 117 added, 2 removed (every tool) | review |
| 2026-10-18 | `remote/dev.zambo/zambo` | 2026-10-18T051353382124 -> 2026-10-18T113517731801 | 35 changed (every tool) | quiet |
| 2026-10-18 | `remote/io.github.zambodotdev/zambo` | 2026-10-18T051353316366 -> 2026-10-18T113517759556 | 35 changed (every tool) | quiet |
| 2026-10-18 | `remote/io.github.kwizzlesurp10-ctrl/x402-mcp` | 2026-10-01T134422827300 -> 2026-10-18T113512273096 | 1 changed | quiet |
| 2026-10-18 | `remote/io.taifoon/coordination-layer.1` | 2026-10-18T051349738204 -> 2026-10-18T113507051892 | 2 changed | review |
| 2026-10-18 | `remote/se.sistaminuten/travel-search` | 2026-10-18T051348177487 -> 2026-10-18T113504797314 | 1 changed | quiet |
| 2026-10-18 | `remote/eu.skavio/paid-micro-apis` | 2026-10-17T070518267367 -> 2026-10-18T113505580564 | 3 changed | quiet |
| 2026-10-18 | `remote/ai.myporta/myporta` | 2026-10-17T055613253831 -> 2026-10-18T113457787732 | 1 changed | quiet |
| 2026-10-18 | `remote/coach.marian/mentoring-inquiry-builder` | 2026-10-09T153647411777 -> 2026-10-18T113457366909 | 4 changed | quiet |
| 2026-10-18 | `remote/no.apier/mcp` | 2026-10-17T055555369890 -> 2026-10-18T113435235185 | 1 changed | quiet |
| 2026-10-18 | `remote/de.wostrom/catalog` | 2026-09-23T202524677799 -> 2026-10-18T113432304620 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.suprraz/webzum` | 2026-10-06T110222315003 -> 2026-10-18T113416811180 | 1 changed | quiet |
| 2026-10-18 | `remote/com.voxodds/voxodds` | 2026-10-01T134401959709 -> 2026-10-18T113415588708 | 6 changed | quiet |
| 2026-10-18 | `remote/no.restplass/travel-search` | 2026-10-18T051542321767 -> 2026-10-18T113414100701 | 1 changed | quiet |
| 2026-10-18 | `remote/ai.pulsegate/provenance` | 2026-10-07T001333588400 -> 2026-10-18T113412731917 | 3 changed (every tool) | quiet |
| 2026-10-18 | `remote/com.meridiandispatch/travel-guides` | 2026-10-07T001331054018 -> 2026-10-18T113407145263 | 9 changed, 4 added (every tool) | quiet |
| 2026-10-18 | `remote/com.vibe-fixer/vibefix` | 2026-10-07T063345656497 -> 2026-10-18T113404921501 | 2 changed, 3 added | quiet |
| 2026-10-18 | `remote/fr.comparr/comparr` | 2026-09-28T142304018099 -> 2026-10-18T113350085556 | 3 changed | quiet |
| 2026-10-18 | `remote/com.cintrasupply/cintra-quote` | 2026-10-08T135515370702 -> 2026-10-18T113348040220 | 3 changed | quiet |
| 2026-10-18 | `remote/io.github.lonniev/tollbooth-shortlinks` | 2026-09-23T160950848524 -> 2026-10-18T113345896873 | 4 changed (every tool) | quiet |
| 2026-10-18 | `remote/io.github.lonniev/tollbooth-oauth2-collector` | 2026-09-23T160812076750 -> 2026-10-18T113345251517 | 4 changed (every tool) | quiet |
| 2026-10-18 | `remote/dk.afbudsrejser/travel-search` | 2026-10-18T051530650154 -> 2026-10-18T113342685871 | 1 changed | quiet |
| 2026-10-18 | `remote/de.wopool/catalog` | 2026-09-23T202534482925 -> 2026-10-18T113340191574 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 22366 substantive, 9663 that changed only numbers (a catalogue counter ticking, a date), 471 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 16224 | 7212 | 9012 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 143 | 143 | 0 | 0 |
| `sistaminuten.se` | 114 | 4 | 0 | 110 |
| `afbudsrejser.dk` | 113 | 4 | 0 | 109 |
| `akkilahdot.fi` | 113 | 4 | 0 | 109 |
| `restplass.no` | 113 | 4 | 0 | 109 |
| `socialloop.ai` | 110 | 110 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `remoshift.com` | 84 | 6 | 78 | 0 |
| `fundinglandscape.com` | 83 | 50 | 33 | 0 |
| 3963 other operators | 12312 | 11738 | 540 | 34 |
