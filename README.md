# MCP server tool changes

Last change observed 2026-10-25T12:00:57+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

49804 changes to a tool definition: 2189 npm releases (1943 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 47615 readings of hosted servers that found their tools changed; 2580 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-25 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-10-25T102532529774 -> 2026-10-25T120058023712 | 1 changed | quiet |
| 2026-10-25 | `remote/ai.usedby/usedby` | 2026-10-24T125808196711 -> 2026-10-25T120056066945 | 1 changed | quiet |
| 2026-10-25 | `remote/se.sistaminuten/travel-search` | 2026-10-25T102523670100 -> 2026-10-25T120044708343 | 1 changed | quiet |
| 2026-10-25 | `remote/si.zazidljiva/mcp` | 2026-09-28T142420632434 -> 2026-10-25T120041637933 | 1 changed | quiet |
| 2026-10-25 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-10-25T102607305944 -> 2026-10-25T115939333322 | 1 changed | quiet |
| 2026-10-25 | `remote/no.restplass/travel-search` | 2026-10-25T102553881915 -> 2026-10-25T115923200637 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.openaccountants/openaccountants` | 2026-10-17T122830576701 -> 2026-10-25T115920443970 | 1 changed | quiet |
| 2026-10-25 | `remote/dk.afbudsrejser/travel-search` | 2026-10-25T102518922105 -> 2026-10-25T115840751227 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.imokokok/insight-oracle` | 2026-10-25T102701021777 -> 2026-10-25T115827594171 | 2 added | quiet |
| 2026-10-25 | `remote/studio.gradients/mcp` | 2026-10-25T102651568457 -> 2026-10-25T115819321464 | 1 changed | quiet |
| 2026-10-25 | `remote/xyz.trusteed/mcp-gateway` | 2026-10-21T122047994788 -> 2026-10-25T115805292683 | 1 changed | quiet |
| 2026-10-25 | `remote/fi.akkilahdot/travel-search` | 2026-10-25T102632108297 -> 2026-10-25T115801182796 | 1 changed | quiet |
| 2026-10-25 | `remote/fr.synergieloc/immobilier` | 2026-10-25T052256724706 -> 2026-10-25T115728297941 | 2 changed | quiet |
| 2026-10-25 | `remote/com.swarmmemo/bulletin.1` | 2026-10-25T052257415633 -> 2026-10-25T115658790777 | 2 changed | quiet |
| 2026-10-25 | `remote/com.swarmmemo/bulletin` | 2026-10-25T052257102206 -> 2026-10-25T115658540624 | 1 changed | quiet |
| 2026-10-25 | `remote/co.civai.nova/google-docs-agent` | 2026-10-10T202050200364 -> 2026-10-25T115650736235 | 2 removed | quiet |
| 2026-10-25 | `remote/com.missyera/missyera` | 2026-10-20T232751585732 -> 2026-10-25T115631945830 | 8 changed, 5 added | quiet |
| 2026-10-25 | `remote/ing.rentseek/evidence` | 2026-10-24T112756158187 -> 2026-10-25T115616063589 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.birdwell/runescape-wiki-mcp` | 2026-10-25T102429652273 -> 2026-10-25T115603829239 | 8 changed, 2 added, 2 removed | quiet |
| 2026-10-25 | `remote/com.remoshift/jobs` | 2026-10-25T102420592826 -> 2026-10-25T115553181733 | 1 changed | quiet |
| 2026-10-25 | `remote/co.civai.nova/support-agent-admin` | 2026-10-25T102612609518 -> 2026-10-25T115538457363 | 2 removed | quiet |
| 2026-10-25 | `remote/com.pondchat/pondchat` | 2026-10-25T102351489614 -> 2026-10-25T115528135075 | 2 changed, 2 added, 1 removed | quiet |
| 2026-10-25 | `remote/co.civai.nova/google-sheets-agent` | 2026-10-10T202105893335 -> 2026-10-25T115513015516 | 2 removed | quiet |
| 2026-10-25 | `remote/dev.turva/turva-mcp` | 2026-10-23T120203333403 -> 2026-10-25T115432739115 | 1 changed | quiet |
| 2026-10-25 | `remote/com.tkawen/intelligence-gateway` | 2026-10-21T121716241688 -> 2026-10-25T115430308620 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.industrial-platform-ai/link-extractor` | 2026-10-17T055051864662 -> 2026-10-25T115333313367 | 1 changed | quiet |
| 2026-10-25 | `remote/tech.kaiku/kaiku.1` | 2026-10-25T102343447352 -> 2026-10-25T115324545510 | 2 changed, 2 added | quiet |
| 2026-10-25 | `remote/io.echelongraph/echelongraph-mcp` | 2026-10-17T224319468553 -> 2026-10-25T115309935047 | 16 changed (every tool) | quiet |
| 2026-10-25 | `remote/com.hireahelper/mcp` | 2026-10-25T102112788149 -> 2026-10-25T115300450980 | 16 removed | quiet |
| 2026-10-25 | `remote/ai.dotsy/mcp` | 2026-10-25T102306510264 -> 2026-10-25T115251595717 | 1 added | quiet |
| 2026-10-25 | `remote/io.github.peter120525-cmd/lawmadi-os` | 2026-10-25T101836672517 -> 2026-10-25T115156338314 | 1 changed | quiet |
| 2026-10-25 | `remote/com.thefilmradar/filmlab` | 2026-10-24T190404944165 -> 2026-10-25T115155933991 | 6 changed | quiet |
| 2026-10-25 | `remote/io.github.giuseppesocci-bot/kalicart-global` | 2026-10-23T115857840112 -> 2026-10-25T115139359782 | 2 changed | quiet |
| 2026-10-25 | `remote/io.github.pipeworx-io/prospeo` | 2026-10-18T112649706013 -> 2026-10-25T115119699736 | 7 changed, 1 added | quiet |
| 2026-10-25 | `remote/io.github.pipeworx-io/pride` | 2026-10-18T112649741526 -> 2026-10-25T115117070597 | 7 changed, 1 added | quiet |
| 2026-10-25 | `remote/io.github.pipeworx-io/prh-fi` | 2026-10-18T112649604175 -> 2026-10-25T115117097170 | 7 changed, 1 added | quiet |
| 2026-10-25 | `remote/io.github.pipeworx-io/predicthq` | 2026-10-18T112649285941 -> 2026-10-25T115116917711 | 7 changed, 1 added | quiet |
| 2026-10-25 | `remote/io.github.pipeworx-io/powo` | 2026-10-18T112649306478 -> 2026-10-25T115117006444 | 7 changed, 1 added | quiet |
| 2026-10-25 | `remote/io.github.pipeworx-io/podcastindex` | 2026-10-18T112648890960 -> 2026-10-25T115117040098 | 7 changed, 1 added | quiet |
| 2026-10-25 | `remote/io.github.pipeworx-io/pod-researcher` | 2026-10-18T112648913603 -> 2026-10-25T115116984736 | 7 changed, 1 added | quiet |
| 2026-10-25 | `remote/io.github.pipeworx-io/plos` | 2026-10-18T112648633606 -> 2026-10-25T115116024227 | 7 changed, 1 added | quiet |
| 2026-10-25 | `remote/io.github.pipeworx-io/phoenix-number` | 2026-10-20T103511466145 -> 2026-10-25T115116034912 | 7 changed, 1 added | quiet |
| 2026-10-25 | `remote/io.github.pipeworx-io/password` | 2026-10-24T112045852507 -> 2026-10-25T115115110391 | 5 changed | quiet |
| 2026-10-25 | `remote/io.github.pipeworx-io/pagespeed-insights` | 2026-10-24T112045959115 -> 2026-10-25T115114670067 | 5 changed | quiet |
| 2026-10-25 | `remote/io.github.mooshee/govgazette` | 2026-10-17T055200749915 -> 2026-10-25T115051503716 | 4 changed | quiet |
| 2026-10-25 | `remote/io.github.pipeworx-io/shopgoodwill` | 2026-10-24T112204360543 -> 2026-10-25T115043708612 | 5 changed | quiet |
| 2026-10-25 | `remote/io.github.pipeworx-io/seon` | 2026-10-22T105129487791 -> 2026-10-25T115036796892 | 5 changed | quiet |
| 2026-10-25 | `remote/io.github.edtool79-collab/hirepulse-gateway` | 2026-10-25T102045366246 -> 2026-10-25T115034236018 | 8 changed | quiet |
| 2026-10-25 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-25T101638621764 -> 2026-10-25T115015782011 | 2 changed | quiet |
| 2026-10-25 | `remote/dev.pages.freetier-agent-api/freetier-agent-api` | 2026-10-25T101731470616 -> 2026-10-25T114947334059 | 1 changed | review |
| 2026-10-25 | `remote/com.examova/mcp` | 2026-10-02T182158623633 -> 2026-10-25T114932037094 | 4 changed, 8 added, 1 removed (every tool) | quiet |
| 2026-10-25 | `remote/io.github.giuseppesocci-bot/kalicart-global.1` | 2026-10-23T115648106823 -> 2026-10-25T114916601669 | 2 changed | quiet |
| 2026-10-25 | `remote/io.github.ContentWriterco/compabase` | 2026-10-17T054413083581 -> 2026-10-25T114829777662 | 1 added | quiet |
| 2026-10-25 | `remote/com.cooperemail/cooper-email` | 2026-10-25T101633979027 -> 2026-10-25T114817341138 | 11 changed, 1 added | quiet |
| 2026-10-25 | `remote/com.ce-net/ce-net` | 2026-10-25T052235554708 -> 2026-10-25T114813233385 | 3 changed, 1 added | quiet |
| 2026-10-25 | `remote/io.github.voidly-ai/voidly-hosted` | 2026-10-24T111719354050 -> 2026-10-25T114722578957 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.magiccadai/magicon` | 2026-10-22T120729500566 -> 2026-10-25T114641530338 | 2 changed | quiet |
| 2026-10-25 | `remote/com.logimu/shopping-mcp` | 2026-10-25T101324347561 -> 2026-10-25T114537806557 | 3 changed | quiet |
| 2026-10-25 | `remote/br.com.all4clinic/clinic-software` | 2026-10-17T054027183889 -> 2026-10-25T114517584198 | 2 added | quiet |
| 2026-10-25 | `remote/ai.betslipdoctor/mcp` | 2026-10-24T050446329313 -> 2026-10-25T114514751162 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 31740 substantive, 17431 that changed only numbers (a catalogue counter ticking, a date), 633 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 26731 | 10363 | 16368 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 775 | 775 | 0 | 0 |
| `caseyjhand.com` | 220 | 220 | 0 | 0 |
| `sistaminuten.se` | 150 | 4 | 0 | 146 |
| `afbudsrejser.dk` | 149 | 4 | 0 | 145 |
| `akkilahdot.fi` | 149 | 4 | 0 | 145 |
| `restplass.no` | 149 | 4 | 0 | 145 |
| `socialloop.ai` | 144 | 144 | 0 | 0 |
| `remoshift.com` | 119 | 8 | 111 | 0 |
| `fundinglandscape.com` | 114 | 73 | 41 | 0 |
| `openkrill.app` | 111 | 111 | 0 | 0 |
| 5608 other operators | 18652 | 17689 | 911 | 52 |
