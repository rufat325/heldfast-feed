# MCP server tool changes

Last change observed 2026-10-07T15:49:58+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10128 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 21701 hosted endpoints (read daily, and every four hours while they keep changing).

22756 changes to a tool definition: 789 npm releases (543 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 21967 readings of hosted servers that found their tools changed; 313 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-07 | `remote/com.zinvyl/marketplace` | 2026-10-06T184124919837 -> 2026-10-07T155001812650 | 3 changed, 1 added | quiet |
| 2026-10-07 | `remote/io.github.Dcroyalty/xrplhub` | 2026-10-07T001237620057 -> 2026-10-07T154958674157 | 1 added, 3 removed | review |
| 2026-10-07 | `remote/no.restplass/travel-search` | 2026-10-07T063325572685 -> 2026-10-07T154952439370 | 1 changed | quiet |
| 2026-10-07 | `remote/fi.akkilahdot/travel-search` | 2026-10-07T063426302823 -> 2026-10-07T154952405085 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.CodeWever/wever-labs-products` | 2026-10-06T184114869566 -> 2026-10-07T154950384107 | 4 added | review |
| 2026-10-07 | `remote/io.github.webweaver-nexus/webweaver-mcp-server` | 2026-10-06T110221358878 -> 2026-10-07T154949442367 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.oaleviola/arroway` | 2026-10-06T110318077938 -> 2026-10-07T154947552234 | 19 changed (every tool) | quiet |
| 2026-10-07 | `remote/dk.afbudsrejser/travel-search` | 2026-10-07T063320948257 -> 2026-10-07T154947679131 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.josifb/whichlib` | 2026-10-06T110250003436 -> 2026-10-07T154946401878 | 3 changed (every tool) | quiet |
| 2026-10-07 | `remote/cc.thecolony/mcp-server` | 2026-10-06T133929937688 -> 2026-10-07T154946795278 | 1 changed, 1 added | quiet |
| 2026-10-07 | `remote/io.github.VoiceScapee/voicescape` | 2026-10-07T063318904986 -> 2026-10-07T154945311635 | 3 changed, 1 added | quiet |
| 2026-10-07 | `remote/xn--3ds443g.xn--s7y/duan-online` | 2026-10-05T172659706730 -> 2026-10-07T154946231808 | 1 changed | quiet |
| 2026-10-07 | `remote/se.sistaminuten/travel-search` | 2026-10-07T063315638638 -> 2026-10-07T154942835387 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-07T001227569399 -> 2026-10-07T154942319866 | 5 changed, 36 removed | quiet |
| 2026-10-07 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-07T063415506006 -> 2026-10-07T154943096493 | 1 changed | quiet |
| 2026-10-07 | `remote/com.tickerz/tickerz` | 2026-10-07T063314961636 -> 2026-10-07T154941511595 | 1 changed, 1 added | quiet |
| 2026-10-07 | `remote/com.swarmmemo/bulletin` | 2026-10-07T063414813978 -> 2026-10-07T154942690073 | 75 changed, 5 added (every tool) | quiet |
| 2026-10-07 | `remote/app.openkrill/site-check` | 2026-10-06T110100421112 -> 2026-10-07T154940184701 | 1 changed | quiet |
| 2026-10-07 | `remote/com.shipshapedata/shipshape-data` | 2026-10-06T110052802084 -> 2026-10-07T154939717958 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.dtajitdinov-aris/sphere-marketplace` | 2026-10-06T133820111206 -> 2026-10-07T154941533458 | 1 added, 1 removed | review |
| 2026-10-07 | `remote/com.tiamatcrypto.sweetai/agent-intel` | 2026-10-07T063314404309 -> 2026-10-07T154940221807 | 2 added | quiet |
| 2026-10-07 | `remote/com.achivx/stablescan` | 2026-10-06T110240330858 -> 2026-10-07T154939032143 | 8 changed (every tool) | quiet |
| 2026-10-07 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-07T063409223418 -> 2026-10-07T154937473844 | 3 changed | quiet |
| 2026-10-07 | `remote/io.github.send21io/mcp` | 2026-10-06T110042901245 -> 2026-10-07T154937827024 | 3 changed, 1 added | quiet |
| 2026-10-07 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-07T001315020218 -> 2026-10-07T154936755025 | 2 changed | quiet |
| 2026-10-07 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-06T184107421368 -> 2026-10-07T154938771433 | 1 added | quiet |
| 2026-10-07 | `remote/ai.shorti/shorti` | 2026-10-07T063408069611 -> 2026-10-07T154937111305 | 5 changed | quiet |
| 2026-10-07 | `remote/io.github.simonmak-ascent/vision-driven-design` | 2026-10-06T110122193479 -> 2026-10-07T154934485079 | 13 changed | quiet |
| 2026-10-07 | `remote/app.openkrill/buyersignals` | 2026-10-06T110144034786 -> 2026-10-07T154934490800 | 2 changed | quiet |
| 2026-10-07 | `remote/au.publicdata/mcp` | 2026-10-06T110004418312 -> 2026-10-07T154933541951 | 3 changed | quiet |
| 2026-10-07 | `remote/io.github.Perufitlife/postwire-mcp` | 2026-10-05T172638187995 -> 2026-10-07T154932462529 | 2 changed | quiet |
| 2026-10-07 | `remote/dev.workers.fhi-llc-1118.polished-truth-c514/fhi-x402-security-tools` | 2026-10-06T184006067727 -> 2026-10-07T154932707691 | 2 changed | review |
| 2026-10-07 | `remote/io.roraima/guest` | 2026-10-06T110119248294 -> 2026-10-07T154933363329 | 2 changed | quiet |
| 2026-10-07 | `remote/io.github.samuelzcom/chauffeur-booking` | 2026-10-07T063330678477 -> 2026-10-07T154936671730 | 5 changed (every tool) | quiet |
| 2026-10-07 | `remote/com.remoshift/jobs` | 2026-10-07T063401972522 -> 2026-10-07T154931473986 | 1 changed | quiet |
| 2026-10-07 | `remote/com.ai2fin/ai2fin-tax-mcp` | 2026-10-06T110058188932 -> 2026-10-07T154930974461 | 5 changed | quiet |
| 2026-10-07 | `remote/app.pixly/pixly` | 2026-10-07T063324616929 -> 2026-10-07T154932711226 | 1 changed | quiet |
| 2026-10-07 | `remote/com.quietstance/productive-opportunity-development` | 2026-10-07T001216414706 -> 2026-10-07T154930513246 | 6 changed | quiet |
| 2026-10-07 | `remote/app.sallim/korea-realty` | 2026-10-05T061625266136 -> 2026-10-07T154931680568 | 2 changed, 1 added | quiet |
| 2026-10-07 | `remote/dev.proxylang/translate` | 2026-10-06T110145597257 -> 2026-10-07T154929736336 | 2 added | quiet |
| 2026-10-07 | `remote/fyi.smartfin/smartfin` | 2026-10-06T110048344766 -> 2026-10-07T154927803513 | 1 changed | quiet |
| 2026-10-07 | `remote/app.openkrill/postkit` | 2026-10-06T110138599385 -> 2026-10-07T154927500774 | 1 changed | quiet |
| 2026-10-07 | `remote/com.shipshapedata/shipshape-data-docs` | 2026-10-06T110044003181 -> 2026-10-07T154926761674 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.Project-Gifted1/pg1-threat-intel` | 2026-10-06T110031004948 -> 2026-10-07T154925879274 | 1 added | quiet |
| 2026-10-07 | `remote/app.openkrill/seo-audit` | 2026-10-06T110039389878 -> 2026-10-07T154924694811 | 1 added | quiet |
| 2026-10-07 | `remote/dev.mcphost/mcphost` | 2026-10-06T183953959585 -> 2026-10-07T154923481469 | 1 changed | quiet |
| 2026-10-07 | `remote/com.scribiz/mcp` | 2026-10-06T110035929776 -> 2026-10-07T154925349492 | 1 changed | quiet |
| 2026-10-07 | `remote/co.civai.nova/research-agent` | 2026-10-07T063300521768 -> 2026-10-07T154922844902 | 2 removed | quiet |
| 2026-10-07 | `remote/co.civai.nova/google-sheets-agent` | 2026-10-07T063300422639 -> 2026-10-07T154922666798 | 2 removed | quiet |
| 2026-10-07 | `remote/io.github.daveabear/rwa-data-mcp` | 2026-10-07T001221076749 -> 2026-10-07T154922659482 | 1 added | quiet |
| 2026-10-07 | `remote/com.obriym-crm/mcp` | 2026-10-06T184046170606 -> 2026-10-07T154922856601 | 13 added | quiet |
| 2026-10-07 | `remote/com.nearbypermits/permits` | 2026-10-06T110003105358 -> 2026-10-07T154921881508 | 1 changed | quiet |
| 2026-10-07 | `remote/app.railway.up.rent-check-production/irish-rent-check` | 2026-10-06T110017291009 -> 2026-10-07T154921809743 | 2 added | quiet |
| 2026-10-07 | `remote/fun.publish/mcp` | 2026-10-06T110006136089 -> 2026-10-07T154919906453 | 2 changed | quiet |
| 2026-10-07 | `remote/com.vertodigital/mcp` | 2026-10-06T105841740370 -> 2026-10-07T154921217020 | 1 changed | quiet |
| 2026-10-07 | `remote/com.thmenu/thmenu` | 2026-10-06T105930530153 -> 2026-10-07T154917124777 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.Piloxa/piloxa` | 2026-10-07T001212969530 -> 2026-10-07T154916301441 | 1 added | quiet |
| 2026-10-07 | `remote/ai.switchapp/switch` | 2026-10-07T001205649895 -> 2026-10-07T154916273178 | 1 added | quiet |
| 2026-10-07 | `remote/io.github.LienDeadline/liendeadline-mcp` | 2026-10-07T001158506851 -> 2026-10-07T154915632320 | 1 changed | quiet |
| 2026-10-07 | `remote/re.parcellai/parcellaire` | 2026-10-07T001212414759 -> 2026-10-07T154916387450 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 15965 substantive, 6457 that changed only numbers (a catalogue counter ticking, a date), 334 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 11736 | 5690 | 6046 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `sistaminuten.se` | 81 | 2 | 0 | 79 |
| `afbudsrejser.dk` | 80 | 2 | 0 | 78 |
| `akkilahdot.fi` | 80 | 2 | 0 | 78 |
| `restplass.no` | 80 | 2 | 0 | 78 |
| `socialloop.ai` | 78 | 78 | 0 | 0 |
| `caseyjhand.com` | 74 | 74 | 0 | 0 |
| `dayze.com` | 65 | 65 | 0 | 0 |
| `remoshift.com` | 56 | 2 | 54 | 0 |
| 2811 other operators | 7564 | 7186 | 357 | 21 |
