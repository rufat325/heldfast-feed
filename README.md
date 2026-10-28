# MCP server tool changes

Last change observed 2026-10-28T13:39:29+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

58498 changes to a tool definition: 2482 npm releases (2236 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 56016 readings of hosted servers that found their tools changed; 2887 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-28 | `remote/io.github.rezearcher/tech-risk` | 2026-10-24T112914448322 -> 2026-10-28T133930147505 | 2 changed | quiet |
| 2026-10-28 | `remote/io.github.xlw-pro/qimenmind` | 2026-10-19T135243262708 -> 2026-10-28T133910206707 | 2 changed (every tool) | quiet |
| 2026-10-28 | `remote/com.quailos/quailos` | 2026-10-21T202508026596 -> 2026-10-28T133914347459 | 2 changed | quiet |
| 2026-10-28 | `remote/nl.prijsprofeet/prijsprofeet` | 2026-10-20T104358559893 -> 2026-10-28T133909876926 | 1 changed | quiet |
| 2026-10-28 | `remote/dev.hackshop/hackshop-mcp` | 2026-10-17T060346020161 -> 2026-10-28T133835676448 | 10 changed (every tool) | quiet |
| 2026-10-28 | `remote/de.wotablet/catalog` | 2026-09-23T202425537483 -> 2026-10-28T133814822216 | 2 changed, 1 added (every tool) | quiet |
| 2026-10-28 | `remote/de.wosolar/catalog` | 2026-09-23T202425554114 -> 2026-10-28T133814862547 | 2 changed, 1 added (every tool) | quiet |
| 2026-10-28 | `remote/de.woroller/catalog` | 2026-09-23T202425425344 -> 2026-10-28T133814232429 | 2 changed, 1 added (every tool) | quiet |
| 2026-10-28 | `remote/io.github.cyanheads/wikidata-mcp-server` | 2026-10-17T060320731265 -> 2026-10-28T133803575862 | 1 changed | quiet |
| 2026-10-28 | `remote/io.github.sorindecu/vibeshipped` | 2026-10-22T202106293168 -> 2026-10-28T133736148860 | 7 changed, 2 added, 9 removed (every tool) | quiet |
| 2026-10-28 | `remote/com.vibe-fixer/vibefix` | 2026-10-22T140854603557 -> 2026-10-28T133733339703 | 3 changed | review |
| 2026-10-28 | `remote/com.veritahire/hiring-intelligence` | 2026-10-17T060303030317 -> 2026-10-28T133732815227 | 2 changed, 2 added | quiet |
| 2026-10-28 | `remote/com.veritahire/jobs` | 2026-10-17T060303097063 -> 2026-10-28T133732819420 | 3 changed, 1 added | quiet |
| 2026-10-28 | `remote/io.github.withgrokbot/verified-catalog.1` | 2026-10-23T200819026513 -> 2026-10-28T133731670764 | 2 changed | quiet |
| 2026-10-28 | `remote/com.traydstar/marketplace` | 2026-10-19T135143086690 -> 2026-10-28T133704225118 | 3 changed | quiet |
| 2026-10-28 | `remote/dev.tanod/util` | 2026-10-25T102831063678 -> 2026-10-28T133620726773 | 5 changed | quiet |
| 2026-10-28 | `remote/dev.tanod/images` | 2026-10-17T110757086635 -> 2026-10-28T133614827202 | 12 changed | quiet |
| 2026-10-28 | `remote/ai.surfingdog/search` | 2026-10-28T062217235767 -> 2026-10-28T133603512742 | 1 changed | quiet |
| 2026-10-28 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-26T211506397272 -> 2026-10-28T133535955467 | 3 changed | quiet |
| 2026-10-28 | `remote/io.github.tinbox-labs/spawnpop` | 2026-10-27T054113122527 -> 2026-10-28T133536285408 | 2 changed | review |
| 2026-10-28 | `remote/app.vercel.ora-x402-gateway/sensations-mergulho` | 2026-09-23T161043954640 -> 2026-10-28T133522507927 | 1 added | quiet |
| 2026-10-28 | `remote/io.github.cirralink-stack/kevaremesh` | 2026-10-08T135553207682 -> 2026-10-28T133522859227 | 1 changed, 3 added | quiet |
| 2026-10-28 | `remote/io.slide-deck/mcp` | 2026-10-17T060153896674 -> 2026-10-28T133525070652 | 2 changed | quiet |
| 2026-10-28 | `remote/xn--3ds443g.xn--s7y/duan-online` | 2026-10-26T133929927228 -> 2026-10-28T133519297232 | 6 changed (every tool) | quiet |
| 2026-10-28 | `remote/io.github.ak10082247-max/x402-agent-tollbooth` | 2026-10-21T234608315702 -> 2026-10-28T133515386537 | 4 changed (every tool) | quiet |
| 2026-10-28 | `remote/com.theflowersdirectory/flowers` | 2026-10-21T122203286961 -> 2026-10-28T133509940796 | 9 changed (every tool) | quiet |
| 2026-10-28 | `remote/com.tabflows/site` | 2026-10-17T060501011749 -> 2026-10-28T133509141466 | 1 changed | quiet |
| 2026-10-28 | `remote/com.starcovery/mcp` | 2026-10-24T224632772929 -> 2026-10-28T133505083144 | 3 changed | quiet |
| 2026-10-28 | `remote/io.taifoon/coordination-layer.1` | 2026-10-28T062231495497 -> 2026-10-28T133504832869 | 1 changed | review |
| 2026-10-28 | `remote/com.shipshapedata/shipshape-data` | 2026-10-27T112130734353 -> 2026-10-28T133504171441 | 1 changed | quiet |
| 2026-10-28 | `remote/ai.snowsure/snow` | 2026-10-26T133912998115 -> 2026-10-28T133502175193 | 2 changed | quiet |
| 2026-10-28 | `remote/eu.skavio/paid-micro-apis` | 2026-10-20T201135384107 -> 2026-10-28T133502010612 | 13 changed | quiet |
| 2026-10-28 | `remote/com.rycrentals/deals` | 2026-10-26T133805313930 -> 2026-10-28T133502011651 | 1 changed | quiet |
| 2026-10-28 | `remote/se.sistaminuten/travel-search` | 2026-10-28T062229730783 -> 2026-10-28T133502244354 | 1 changed | quiet |
| 2026-10-28 | `remote/no.restplass/travel-search` | 2026-10-28T062236628544 -> 2026-10-28T133500220973 | 1 changed | quiet |
| 2026-10-28 | `remote/com.quantum-expectations/quantum-expectations` | 2026-10-24T112931596285 -> 2026-10-28T133457317251 | 2 changed | quiet |
| 2026-10-28 | `remote/com.praxikon/praxikon` | 2026-10-24T113108001401 -> 2026-10-28T133500202705 | 2 changed | quiet |
| 2026-10-28 | `remote/app.postel/postel` | 2026-10-26T133801309104 -> 2026-10-28T133456729138 | 3 changed | quiet |
| 2026-10-28 | `remote/io.github.beepboop2025/narcoscope` | 2026-10-17T055613182515 -> 2026-10-28T133451168850 | 5 changed | quiet |
| 2026-10-28 | `remote/com.mapsharvest/maps-harvest` | 2026-10-19T135847690853 -> 2026-10-28T133449577760 | 3 changed (every tool) | quiet |
| 2026-10-28 | `remote/io.github.Tomalarrrr/cyclesite-mcp-server` | 2026-10-20T104328809951 -> 2026-10-28T133435282389 | 29 changed | quiet |
| 2026-10-28 | `remote/com.electionsmcp/electionsmcp` | 2026-10-17T060433976478 -> 2026-10-28T133432390841 | 2 changed | quiet |
| 2026-10-28 | `remote/com.answeringprices/pricing` | 2026-10-19T135438245977 -> 2026-10-28T133426590667 | 4 changed (every tool) | quiet |
| 2026-10-28 | `remote/de.wovitamine/catalog` | 2026-09-23T202525004868 -> 2026-10-28T133422466131 | 2 changed, 1 added (every tool) | quiet |
| 2026-10-28 | `remote/de.wostrom/catalog` | 2026-10-18T113432304620 -> 2026-10-28T133422843255 | 2 changed, 1 added (every tool) | quiet |
| 2026-10-28 | `remote/io.github.cnghockey/sats4ai` | 2026-10-22T105710889565 -> 2026-10-28T133420392817 | 14 changed | quiet |
| 2026-10-28 | `remote/de.wohandy/catalog` | 2026-09-23T202523445549 -> 2026-10-28T133418629172 | 2 changed, 1 added (every tool) | quiet |
| 2026-10-28 | `remote/de.wogrill/catalog` | 2026-09-23T202523049375 -> 2026-10-28T133418150429 | 2 changed, 1 added (every tool) | quiet |
| 2026-10-28 | `remote/de.woebike/catalog` | 2026-09-23T202523059873 -> 2026-10-28T133418806076 | 2 changed, 1 added (every tool) | quiet |
| 2026-10-28 | `remote/de.alcometer/mcp` | 2026-10-17T060422778584 -> 2026-10-28T133418968986 | 3 added | quiet |
| 2026-10-28 | `remote/dk.afbudsrejser/travel-search` | 2026-10-28T062229104200 -> 2026-10-28T133416061250 | 1 changed | quiet |
| 2026-10-28 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-26T052255774552 -> 2026-10-28T133415953691 | 5 removed | quiet |
| 2026-10-28 | `remote/io.saascity/saascity` | 2026-10-24T112624116682 -> 2026-10-28T133418402844 | 3 added | quiet |
| 2026-10-28 | `remote/de.wouhr/catalog` | 2026-09-23T202535914220 -> 2026-10-28T133412543193 | 2 changed, 1 added (every tool) | quiet |
| 2026-10-28 | `remote/de.wosneaker/catalog` | 2026-09-23T202535895597 -> 2026-10-28T133412123355 | 2 changed, 1 added (every tool) | quiet |
| 2026-10-28 | `remote/de.wopool/catalog` | 2026-10-18T113340191574 -> 2026-10-28T133410316640 | 2 changed, 1 added (every tool) | quiet |
| 2026-10-28 | `remote/io.github.witanmarkets/witan` | 2026-10-24T113023397754 -> 2026-10-28T133409234096 | 1 changed | quiet |
| 2026-10-28 | `remote/rs.rides/airport-transfers` | 2026-10-19T052401810373 -> 2026-10-28T133357347178 | 1 changed | quiet |
| 2026-10-28 | `remote/io.github.voicehook-ai/voicehook` | 2026-10-27T124343597598 -> 2026-10-28T133358078212 | 3 changed | quiet |
| 2026-10-28 | `remote/io.github.shashwatgtm/revenue-enablement-mcp` | 2026-10-19T135013334851 -> 2026-10-28T133355130580 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 38317 substantive, 19489 that changed only numbers (a catalogue counter ticking, a date), 692 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 32228 | 13994 | 18234 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1009 | 1009 | 0 | 0 |
| `caseyjhand.com` | 244 | 244 | 0 | 0 |
| `sistaminuten.se` | 164 | 5 | 0 | 159 |
| `afbudsrejser.dk` | 163 | 5 | 0 | 158 |
| `akkilahdot.fi` | 163 | 5 | 0 | 158 |
| `restplass.no` | 163 | 5 | 0 | 158 |
| `socialloop.ai` | 157 | 157 | 0 | 0 |
| `remoshift.com` | 133 | 8 | 125 | 0 |
| `revmesh2074.workers.dev` | 129 | 116 | 13 | 0 |
| `fundinglandscape.com` | 126 | 80 | 46 | 0 |
| 6301 other operators | 21478 | 20348 | 1071 | 59 |
