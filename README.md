# MCP server tool changes

Last change observed 2026-10-17T22:45:19+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10495 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 23695 hosted endpoints (read daily, and every four hours while they keep changing).

30491 changes to a tool definition: 1052 npm releases (806 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 29439 readings of hosted servers that found their tools changed; 2065 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-17 | `remote/com.youspot/youspot` | 2026-10-17T070655350296 -> 2026-10-17T224521612779 | 1 removed | quiet |
| 2026-10-17 | `remote/com.satellitequotes/satellitequotes` | 2026-10-17T060408894491 -> 2026-10-17T224515218506 | 2 changed | quiet |
| 2026-10-17 | `remote/com.rightshold/rightshold` | 2026-10-17T185351306814 -> 2026-10-17T224514579463 | 1 changed | quiet |
| 2026-10-17 | `remote/ai.weio/site-check` | 2026-10-17T060317944703 -> 2026-10-17T224502591122 | 3 added | quiet |
| 2026-10-17 | `remote/ch.antevo/trademark` | 2026-10-17T110815914080 -> 2026-10-17T224455668637 | 1 changed, 12 added | review |
| 2026-10-17 | `remote/com.santismm/knowledge` | 2026-10-17T185329713778 -> 2026-10-17T224433804711 | 1 changed | quiet |
| 2026-10-17 | `remote/rs.rides/airport-transfers` | 2026-10-17T185328510154 -> 2026-10-17T224431994518 | 1 changed | quiet |
| 2026-10-17 | `remote/com.quintadb/mcp` | 2026-10-17T060103874187 -> 2026-10-17T224429255716 | 2 changed, 1 added | quiet |
| 2026-10-17 | `remote/no.restplass/travel-search` | 2026-10-17T185411670964 -> 2026-10-17T224423103453 | 1 changed | quiet |
| 2026-10-17 | `remote/se.sistaminuten/travel-search` | 2026-10-17T185357576657 -> 2026-10-17T224417955539 | 1 changed | quiet |
| 2026-10-17 | `remote/io.kolmo.www/kolmo-mcp-server` | 2026-10-17T055610062698 -> 2026-10-17T224416522440 | 1 changed | quiet |
| 2026-10-17 | `remote/dk.afbudsrejser/travel-search` | 2026-10-17T185403150999 -> 2026-10-17T224414764687 | 1 changed | quiet |
| 2026-10-17 | `remote/app.openkrill/outreach-desk` | 2026-10-17T060021344439 -> 2026-10-17T224413400763 | 3 changed | quiet |
| 2026-10-17 | `remote/io.github.nimbusbci/nimbus-mcp` | 2026-10-17T055959744979 -> 2026-10-17T224409292090 | 3 changed | quiet |
| 2026-10-17 | `remote/io.github.TGM-Ventures/tgmcharts` | 2026-10-17T055504328896 -> 2026-10-17T224407464891 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.vassiliylakhonin/agenda-intelligence-md.2` | 2026-10-17T055924024850 -> 2026-10-17T224401370277 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.boriskendev/stormap` | 2026-10-17T185348110569 -> 2026-10-17T224401521667 | 1 added | quiet |
| 2026-10-17 | `remote/dev.pages.smithtalks/smithtalks` | 2026-10-17T060308146466 -> 2026-10-17T224359939507 | 1 changed | quiet |
| 2026-10-17 | `remote/com.gccdomestic/gccdomestic` | 2026-10-17T055936494147 -> 2026-10-17T224358024738 | 2 changed | quiet |
| 2026-10-17 | `remote/io.github.lbailey94/whitemagic-mcp` | 2026-10-17T055843188983 -> 2026-10-17T224356360409 | 1 changed | quiet |
| 2026-10-17 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-10-17T055924538523 -> 2026-10-17T224356365162 | 5 changed | quiet |
| 2026-10-17 | `remote/io.github.privatelawattorneys/wiki-private-law` | 2026-10-17T055917350779 -> 2026-10-17T224356339489 | 4 changed | quiet |
| 2026-10-17 | `remote/fi.akkilahdot/travel-search` | 2026-10-17T185401055684 -> 2026-10-17T224355313416 | 1 changed | quiet |
| 2026-10-17 | `remote/ai.rokha/rokha` | 2026-10-17T155955780067 -> 2026-10-17T224353125286 | 1 added | quiet |
| 2026-10-17 | `remote/ru.quintadb/mcp` | 2026-10-17T055415075057 -> 2026-10-17T224354732015 | 2 changed, 1 added | quiet |
| 2026-10-17 | `remote/com.tkawen/intelligence-gateway` | 2026-10-17T122737697562 -> 2026-10-17T224354074803 | 1 changed | quiet |
| 2026-10-17 | `remote/app.traderspy/traderspy` | 2026-10-17T155906969377 -> 2026-10-17T224353379274 | 2 changed | quiet |
| 2026-10-17 | `remote/us.srv.vehcdj664efetfrsolne5umanq/quoteproof-mcp` | 2026-10-17T160005562315 -> 2026-10-17T224352525044 | 1 added | quiet |
| 2026-10-17 | `remote/io.github.veredamonte-glitch/verithic` | 2026-10-17T122857766510 -> 2026-10-17T224353331705 | 3 changed | quiet |
| 2026-10-17 | `remote/ua.com.quintadb/mcp` | 2026-10-17T060201646104 -> 2026-10-17T224351571680 | 2 changed, 1 added | quiet |
| 2026-10-17 | `remote/io.github.OmniAISystems/govomniai-machine-services` | 2026-10-17T055853671914 -> 2026-10-17T224350036934 | 1 changed, 1 added | quiet |
| 2026-10-17 | `remote/io.github.richardsolomou/praetorium` | 2026-10-17T060147728139 -> 2026-10-17T224348788138 | 5 changed | quiet |
| 2026-10-17 | `remote/gg.plazmi/plazmi` | 2026-10-17T055357407136 -> 2026-10-17T224348244889 | 1 changed | quiet |
| 2026-10-17 | `remote/cc.squatch/mcp` | 2026-10-17T055815191212 -> 2026-10-17T224348622232 | 1 changed, 3 removed | quiet |
| 2026-10-17 | `remote/com.petnecto/pets` | 2026-10-17T110528038104 -> 2026-10-17T224347017439 | 1 changed, 1 added | quiet |
| 2026-10-17 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-17T155957188698 -> 2026-10-17T224346264935 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.vassiliylakhonin/agenda-intelligence-md.1` | 2026-10-17T055346398053 -> 2026-10-17T224343602775 | 4 changed | quiet |
| 2026-10-17 | `remote/com.preshiftiq/shiftiq-mcp` | 2026-10-17T155900907788 -> 2026-10-17T224344792404 | 9 changed | quiet |
| 2026-10-17 | `remote/com.swarmmemo/bulletin.1` | 2026-10-17T055825423843 -> 2026-10-17T224344343743 | 1 changed | quiet |
| 2026-10-17 | `remote/com.swarmmemo/bulletin` | 2026-10-17T055825402498 -> 2026-10-17T224344057623 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.dtajitdinov-aris/sphere-marketplace` | 2026-10-17T122845600781 -> 2026-10-17T224344143898 | 2 changed | quiet |
| 2026-10-17 | `remote/app.onehaus/haus` | 2026-10-17T055740788254 -> 2026-10-17T224342736543 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-17T185343546531 -> 2026-10-17T224340532266 | 1 changed | quiet |
| 2026-10-17 | `remote/how.mise/mise` | 2026-10-17T185326087732 -> 2026-10-17T224340218632 | 24 changed, 1 added (every tool) | quiet |
| 2026-10-17 | `remote/com.risetive/mcp` | 2026-10-17T055729322206 -> 2026-10-17T224336853659 | 1 changed | quiet |
| 2026-10-17 | `remote/com.remoshift/jobs` | 2026-10-17T185338220721 -> 2026-10-17T224335564831 | 1 changed | quiet |
| 2026-10-17 | `remote/dev.uptimepage/uptimepage` | 2026-10-17T055246888648 -> 2026-10-17T224335946719 | 4 changed | quiet |
| 2026-10-17 | `remote/world.tokenbank/tokenbank` | 2026-10-17T185311552270 -> 2026-10-17T224332958231 | 1 changed | quiet |
| 2026-10-17 | `remote/dev.pages.project100-7vk/project100` | 2026-10-17T055711602540 -> 2026-10-17T224333238933 | 1 added | review |
| 2026-10-17 | `remote/me.phor/phorme-training` | 2026-10-17T055651730779 -> 2026-10-17T224328722317 | 2 changed, 4 added | quiet |
| 2026-10-17 | `remote/com.parcellaunch/parcellaunch` | 2026-10-17T055646159163 -> 2026-10-17T224327751884 | 1 changed | review |
| 2026-10-17 | `remote/ch.opencaselaw/swiss-caselaw` | 2026-10-17T055944445297 -> 2026-10-17T224328817413 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.77777R7/octocrawl` | 2026-10-17T155930867561 -> 2026-10-17T224326848059 | 1 changed | quiet |
| 2026-10-17 | `remote/gl.parse/mcp` | 2026-10-17T072936284017 -> 2026-10-17T224327699947 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.nomadstays/mcp-server` | 2026-10-17T055158251342 -> 2026-10-17T224326381950 | 1 changed | quiet |
| 2026-10-17 | `remote/com.neblla/neblla` | 2026-10-17T155929777026 -> 2026-10-17T224322667667 | 11 changed, 2 added | quiet |
| 2026-10-17 | `remote/com.multicinesortega/cartelera` | 2026-10-17T110947919257 -> 2026-10-17T224323233827 | 1 changed | quiet |
| 2026-10-17 | `remote/ai.greenlandai/greenlandai` | 2026-10-17T055917046149 -> 2026-10-17T224323380603 | 40 changed, 2 added, 3 removed (every tool) | quiet |
| 2026-10-17 | `remote/com.etfiq/etfiq` | 2026-10-17T185306337868 -> 2026-10-17T224320385342 | 1 changed | quiet |
| 2026-10-17 | `remote/io.echelongraph/echelongraph-mcp` | 2026-10-17T055903117292 -> 2026-10-17T224319468553 | 16 changed (every tool) | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 21888 substantive, 8145 that changed only numbers (a catalogue counter ticking, a date), 458 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 14726 | 7201 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 126 | 126 | 0 | 0 |
| `sistaminuten.se` | 111 | 4 | 0 | 107 |
| `afbudsrejser.dk` | 110 | 4 | 0 | 106 |
| `akkilahdot.fi` | 110 | 4 | 0 | 106 |
| `restplass.no` | 110 | 4 | 0 | 106 |
| `socialloop.ai` | 107 | 107 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `fundinglandscape.com` | 81 | 49 | 32 | 0 |
| `remoshift.com` | 81 | 6 | 75 | 0 |
| 3803 other operators | 11838 | 11292 | 513 | 33 |
