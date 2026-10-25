# MCP server tool changes

Last change observed 2026-10-25T10:29:59+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

49736 changes to a tool definition: 2189 npm releases (1943 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 47547 readings of hosted servers that found their tools changed; 2579 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-25 | `remote/io.github.HuangGoodmanAgency/edgar-and-edgarette` | 2026-10-17T060401632469 -> 2026-10-25T102959349585 | 2 added | quiet |
| 2026-10-25 | `remote/io.engineeringleaders/elc-trade` | 2026-10-21T122149868287 -> 2026-10-25T102943403798 | 7 changed, 1 added | quiet |
| 2026-10-25 | `remote/com.basischarts/basis` | 2026-10-23T135154339780 -> 2026-10-25T102933092309 | 2 changed | quiet |
| 2026-10-25 | `remote/dev.upfork/upfork` | 2026-10-17T060256716493 -> 2026-10-25T102858733576 | 1 changed, 14 added | quiet |
| 2026-10-25 | `remote/io.github.pcaiano/toolscout` | 2026-10-21T122105778184 -> 2026-10-25T102854075285 | 2 changed | quiet |
| 2026-10-25 | `remote/dev.tanod/util` | 2026-10-17T110758080532 -> 2026-10-25T102831063678 | 1 changed, 2 added | quiet |
| 2026-10-25 | `remote/live.status/status-live` | 2026-10-22T105749634394 -> 2026-10-25T102813006526 | 3 changed | quiet |
| 2026-10-25 | `remote/com.kindoflost.staff-scheduling/shift-scheduler` | 2026-09-28T142228085557 -> 2026-10-25T102810730737 | 1 changed, 1 added | quiet |
| 2026-10-25 | `remote/eu.skimetric/skimetric` | 2026-10-17T060151107928 -> 2026-10-25T102756761605 | 3 changed | quiet |
| 2026-10-25 | `remote/za.co.simcloud/simcloud` | 2026-09-29T113510770718 -> 2026-10-25T102757890451 | 2 changed | quiet |
| 2026-10-25 | `remote/com.shipshapedata/shipshape-data` | 2026-10-24T112647217840 -> 2026-10-25T102748842837 | 1 changed | quiet |
| 2026-10-25 | `remote/com.kindoflost.routing/fleet-route-optimizer` | 2026-10-06T110024445324 -> 2026-10-25T102723516168 | 1 changed, 1 added | quiet |
| 2026-10-25 | `remote/io.github.cyanheads/ris-austria-mcp-server` | 2026-10-24T224628189624 -> 2026-10-25T102720323991 | 1 changed | quiet |
| 2026-10-25 | `remote/com.zinvyl/marketplace` | 2026-10-25T052305112160 -> 2026-10-25T102720016043 | 8 changed | quiet |
| 2026-10-25 | `remote/io.github.seekdaseek/agentfeed` | 2026-10-21T122240697109 -> 2026-10-25T102716121138 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.Bosacks/magneta-contract-risk` | 2026-10-20T201155042793 -> 2026-10-25T102715596108 | 2 changed | review |
| 2026-10-25 | `remote/io.github.safeswapglobal-prog/safeswapglobal-mcp` | 2026-10-19T135002002614 -> 2026-10-25T102709466973 | 2 changed, 1 added (every tool) | quiet |
| 2026-10-25 | `remote/io.github.cyanheads/pubmed-mcp-server` | 2026-10-23T120403624425 -> 2026-10-25T102701679639 | 6 changed, 1 added | quiet |
| 2026-10-25 | `remote/io.peanutbutterjelly/deals` | 2026-09-28T142637137957 -> 2026-10-25T102703728887 | 5 changed (every tool) | quiet |
| 2026-10-25 | `remote/io.github.imokokok/insight-oracle` | 2026-10-19T155755438387 -> 2026-10-25T102701021777 | 13 changed, 5 added | quiet |
| 2026-10-25 | `remote/studio.gradients/mcp` | 2026-10-25T052303646928 -> 2026-10-25T102651568457 | 1 changed | quiet |
| 2026-10-25 | `remote/com.polarjay/polarjay` | 2026-10-17T060044716778 -> 2026-10-25T102649264052 | 5 changed (every tool) | quiet |
| 2026-10-25 | `remote/fi.akkilahdot/travel-search` | 2026-10-25T052302556033 -> 2026-10-25T102632108297 | 1 changed | quiet |
| 2026-10-25 | `remote/com.ownerspec/mcp` | 2026-10-03T121057933288 -> 2026-10-25T102625126992 | 8 changed, 5 added (every tool) | quiet |
| 2026-10-25 | `remote/io.github.cyanheads/oecd-mcp-server` | 2026-09-23T160700450511 -> 2026-10-25T102616353491 | 3 changed | quiet |
| 2026-10-25 | `remote/com.vuntum/mcp` | 2026-10-06T110333260637 -> 2026-10-25T102616543503 | 1 changed, 1 added | quiet |
| 2026-10-25 | `remote/co.civai.nova/support-agent-admin` | 2026-10-25T052249937838 -> 2026-10-25T102612609518 | 2 added | quiet |
| 2026-10-25 | `remote/law.northend/dpa` | 2026-10-17T060004158276 -> 2026-10-25T102610792707 | 10 changed | quiet |
| 2026-10-25 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-10-21T122209231376 -> 2026-10-25T102607305944 | 2 changed | quiet |
| 2026-10-25 | `remote/com.uxcontinuum/ship-check` | 2026-10-17T055858146621 -> 2026-10-25T102603201540 | 1 added | review |
| 2026-10-25 | `remote/io.github.cyanheads/usda-mcp-server` | 2026-09-23T162920848805 -> 2026-10-25T102602002557 | 3 changed | quiet |
| 2026-10-25 | `remote/io.github.aaronte/useqr-mcp` | 2026-09-23T162920873219 -> 2026-10-25T102602215848 | 3 changed (every tool) | quiet |
| 2026-10-25 | `remote/io.github.cyanheads/usaspending-mcp-server` | 2026-10-17T055856304709 -> 2026-10-25T102601598469 | 15 changed | quiet |
| 2026-10-25 | `remote/com.stayportland/mcp` | 2026-09-23T163146129545 -> 2026-10-25T102558480284 | 10 changed | quiet |
| 2026-10-25 | `remote/com.nadveo/service-booking` | 2026-10-23T120259606791 -> 2026-10-25T102556529396 | 1 changed | quiet |
| 2026-10-25 | `remote/no.restplass/travel-search` | 2026-10-25T052303839958 -> 2026-10-25T102553881915 | 1 changed | quiet |
| 2026-10-25 | `remote/com.monsathletics/mons` | 2026-10-21T121805594433 -> 2026-10-25T102546842330 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.cryptoduke01/gloam` | 2026-10-25T052301702090 -> 2026-10-25T102539370376 | 1 changed | quiet |
| 2026-10-25 | `remote/com.metraipolis/knowledge-commons` | 2026-10-22T105530303949 -> 2026-10-25T102535664269 | 4 changed | quiet |
| 2026-10-25 | `remote/com.findbroadbanddeals/broadband-deals` | 2026-10-19T135836503602 -> 2026-10-25T102534971465 | 1 changed | quiet |
| 2026-10-25 | `remote/dev.tanod/web` | 2026-10-24T190428792771 -> 2026-10-25T102533610687 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-10-21T122416545747 -> 2026-10-25T102532529774 | 2 changed | quiet |
| 2026-10-25 | `remote/com.whiteautoandmedia/catalog` | 2026-10-17T055628932312 -> 2026-10-25T102534166496 | 3 changed (every tool) | quiet |
| 2026-10-25 | `remote/ch.swisslivingindex/swiss-living-index` | 2026-10-17T185347380605 -> 2026-10-25T102527772608 | 72 changed (every tool) | quiet |
| 2026-10-25 | `remote/io.taifoon/coordination-layer.1` | 2026-10-25T052303266733 -> 2026-10-25T102526210796 | 1 changed | review |
| 2026-10-25 | `remote/se.sistaminuten/travel-search` | 2026-10-25T052304004614 -> 2026-10-25T102523670100 | 1 changed | quiet |
| 2026-10-25 | `remote/ai.postquick.www/postquickai` | 2026-10-19T135508735128 -> 2026-10-25T102520416348 | 1 changed | quiet |
| 2026-10-25 | `remote/dk.afbudsrejser/travel-search` | 2026-10-25T052300406873 -> 2026-10-25T102518922105 | 1 changed | quiet |
| 2026-10-25 | `remote/live.status/campgrounds` | 2026-10-17T055816874920 -> 2026-10-25T102516858690 | 3 changed (every tool) | quiet |
| 2026-10-25 | `remote/com.zeamprism/prism-mcp` | 2026-10-17T055907984347 -> 2026-10-25T102518479269 | 13 changed | quiet |
| 2026-10-25 | `remote/app.sallim/korea-stay` | 2026-10-21T202501654779 -> 2026-10-25T102518696545 | 1 changed | quiet |
| 2026-10-25 | `remote/app.housefile/licensing` | 2026-10-23T120929560273 -> 2026-10-25T102514205388 | 1 changed | quiet |
| 2026-10-25 | `remote/com.whenisbins/bin-collections` | 2026-10-17T060414085717 -> 2026-10-25T102511350311 | 4 changed (every tool) | quiet |
| 2026-10-25 | `remote/ch.spickme/swiss-public-transport` | 2026-10-18T190050438738 -> 2026-10-25T102512511761 | 6 changed (every tool) | quiet |
| 2026-10-25 | `remote/app.wenbu/mcp` | 2026-10-06T110248895889 -> 2026-10-25T102510555938 | 6 changed, 1 added (every tool) | quiet |
| 2026-10-25 | `remote/io.github.cyanheads/socrata-mcp-server` | 2026-09-23T162853777460 -> 2026-10-25T102507603032 | 1 changed | quiet |
| 2026-10-25 | `remote/com.feode/feode-mcp` | 2026-10-17T055601643045 -> 2026-10-25T102508463727 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-25T052256454699 -> 2026-10-25T102507149803 | 1 changed | quiet |
| 2026-10-25 | `remote/io.engineeringleaders/elc-partnership-builder` | 2026-10-21T122349204840 -> 2026-10-25T102509735388 | 8 changed | quiet |
| 2026-10-25 | `remote/io.slopit/slopit` | 2026-10-21T122022567234 -> 2026-10-25T102504177232 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 31678 substantive, 17429 that changed only numbers (a catalogue counter ticking, a date), 629 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 26718 | 10350 | 16368 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 775 | 775 | 0 | 0 |
| `caseyjhand.com` | 220 | 220 | 0 | 0 |
| `sistaminuten.se` | 149 | 4 | 0 | 145 |
| `afbudsrejser.dk` | 148 | 4 | 0 | 144 |
| `akkilahdot.fi` | 148 | 4 | 0 | 144 |
| `restplass.no` | 148 | 4 | 0 | 144 |
| `socialloop.ai` | 144 | 144 | 0 | 0 |
| `remoshift.com` | 118 | 8 | 110 | 0 |
| `fundinglandscape.com` | 113 | 72 | 41 | 0 |
| `openkrill.app` | 111 | 111 | 0 | 0 |
| 5605 other operators | 18603 | 17641 | 910 | 52 |
