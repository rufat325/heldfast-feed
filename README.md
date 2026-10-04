# MCP server tool changes

Last change observed 2026-10-04T19:50:27+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 19746 hosted endpoints (read daily, and every four hours while they keep changing).

19478 changes to a tool definition: 696 npm releases (450 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 18782 readings of hosted servers that found their tools changed; 226 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-04 | `remote/io.github.JakubTrousil/agentsjunction` | 2026-10-04T142502708762 -> 2026-10-04T195028694714 | 2 changed | quiet |
| 2026-10-04 | `remote/world.agentindex/x402` | 2026-10-03T232155580830 -> 2026-10-04T195028795233 | 1 changed, 3 added | quiet |
| 2026-10-04 | `remote/no.restplass/travel-search` | 2026-10-04T142458273003 -> 2026-10-04T195027263237 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.Uuriko/project-room` | 2026-10-02T061630393302 -> 2026-10-04T195026483579 | 2 changed | quiet |
| 2026-10-04 | `remote/fi.akkilahdot/travel-search` | 2026-10-04T142500245127 -> 2026-10-04T195026649679 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-03T121454437881 -> 2026-10-04T195025592459 | 1 changed | quiet |
| 2026-10-04 | `remote/dk.afbudsrejser/travel-search` | 2026-10-04T142455676119 -> 2026-10-04T195025062415 | 1 changed | quiet |
| 2026-10-04 | `remote/ai.wem3/wem-price-compare` | 2026-10-04T142454973957 -> 2026-10-04T195023987112 | 9 changed | quiet |
| 2026-10-04 | `remote/com.serdaroztetik/call-me` | 2026-10-04T055014825730 -> 2026-10-04T195022757945 | 6 changed (every tool) | quiet |
| 2026-10-04 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-04T142453606003 -> 2026-10-04T195021147214 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-10-04T142450749057 -> 2026-10-04T195020393052 | 15 changed | review |
| 2026-10-04 | `remote/io.github.Perufitlife/postwire-mcp` | 2026-10-04T142451116668 -> 2026-10-04T195019380771 | 6 changed | quiet |
| 2026-10-04 | `remote/com.innergcomplete/shearquery` | 2026-10-04T054941241698 -> 2026-10-04T195019887166 | 2 changed, 1 added | quiet |
| 2026-10-04 | `remote/com.remoshift/jobs` | 2026-10-04T124104529703 -> 2026-10-04T195019597963 | 1 changed | quiet |
| 2026-10-04 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-03T121239601108 -> 2026-10-04T195018703942 | 2 changed | quiet |
| 2026-10-04 | `remote/com.plainrouter/mcp` | 2026-10-04T124117873310 -> 2026-10-04T195018959972 | 2 added, 2 removed | quiet |
| 2026-10-04 | `remote/app.pixly/pixly` | 2026-10-03T054739410038 -> 2026-10-04T195018634355 | 3 changed | quiet |
| 2026-10-04 | `remote/se.sistaminuten/travel-search` | 2026-10-04T142452783442 -> 2026-10-04T195017393401 | 1 changed | quiet |
| 2026-10-04 | `remote/com.obriym-crm/mcp` | 2026-10-03T232133456115 -> 2026-10-04T195016898318 | 6 changed | quiet |
| 2026-10-04 | `remote/io.github.Travisswop/swop` | 2026-10-04T054755828598 -> 2026-10-04T195014794124 | 3 changed | quiet |
| 2026-10-04 | `remote/app.sallim/korea-realty` | 2026-10-03T054737509251 -> 2026-10-04T195017486982 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.tjcgraham-rgb/gaip-broker` | 2026-10-02T061635512478 -> 2026-10-04T195017464278 | 3 changed | quiet |
| 2026-10-04 | `remote/io.github.jamboree777/nightwatch` | 2026-10-04T054858430564 -> 2026-10-04T195014877211 | 1 changed | quiet |
| 2026-10-04 | `remote/dev.mcphost/mcphost` | 2026-10-04T054836258395 -> 2026-10-04T195013629346 | 11 changed | quiet |
| 2026-10-04 | `remote/io.guestgraph/mental-model` | 2026-10-04T123844243310 -> 2026-10-04T195013222537 | 1 changed | quiet |
| 2026-10-04 | `remote/com.viberooster/hatch` | 2026-10-02T182614348193 -> 2026-10-04T195009577349 | 1 changed, 1 added | quiet |
| 2026-10-04 | `remote/io.orbitwan/orbitwan` | 2026-10-03T192854535839 -> 2026-10-04T195009944452 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.presendapp/presend-mcp` | 2026-10-04T142443176818 -> 2026-10-04T195008856147 | 40 changed (every tool) | quiet |
| 2026-10-04 | `remote/cz.cenaodhad/cenaodhad` | 2026-10-04T142442870744 -> 2026-10-04T195011827587 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.yzlee/opcmenu` | 2026-10-04T054725094997 -> 2026-10-04T195012333544 | 1 changed, 2 removed | quiet |
| 2026-10-04 | `remote/com.thefilmradar/filmlab` | 2026-10-04T123745770670 -> 2026-10-04T195009705752 | 2 added | quiet |
| 2026-10-04 | `remote/com.pinsvit/api` | 2026-10-03T115929599135 -> 2026-10-04T195009401899 | 1 changed | quiet |
| 2026-10-04 | `remote/ai.tunnelmind/data` | 2026-10-03T192853014371 -> 2026-10-04T195008486690 | 1 changed | quiet |
| 2026-10-04 | `remote/com.narrowhighway/concordance` | 2026-10-04T142441458298 -> 2026-10-04T195006634717 | 1 changed | quiet |
| 2026-10-04 | `remote/com.movingplace/mcp` | 2026-10-02T150310281110 -> 2026-10-04T195006350861 | 16 added | quiet |
| 2026-10-04 | `remote/ai.greenlandai/greenlandai` | 2026-10-04T142439349860 -> 2026-10-04T195007492689 | 3 changed, 1 added | quiet |
| 2026-10-04 | `remote/so.darwin/darwin` | 2026-10-04T054627940260 -> 2026-10-04T195006672961 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.TotesMagotes/mcp-server-auth` | 2026-10-02T182515980625 -> 2026-10-04T195005718336 | 1 changed | quiet |
| 2026-10-04 | `remote/io.companygraph/mental-model` | 2026-10-04T123829581538 -> 2026-10-04T195003853672 | 1 changed | quiet |
| 2026-10-04 | `remote/com.aiapplyd/aiapplyd` | 2026-10-02T080343280833 -> 2026-10-04T195004703379 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.tcador/787daily` | 2026-10-03T192848660239 -> 2026-10-04T195001615352 | 1 changed | quiet |
| 2026-10-04 | `remote/dev.homespun/homespun` | 2026-10-03T121032967451 -> 2026-10-04T195003852226 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.Dahliyaal/justicelibre` | 2026-10-04T054521909369 -> 2026-10-04T195001296034 | 8 changed | quiet |
| 2026-10-04 | `remote/com.koskamo/koskamo` | 2026-10-04T123739716741 -> 2026-10-04T195000865040 | 2 changed | quiet |
| 2026-10-04 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-10-03T192846303961 -> 2026-10-04T194958931034 | 1 changed | review |
| 2026-10-04 | `remote/com.freelanceclearing/marketplace` | 2026-10-02T061610819508 -> 2026-10-04T194959424161 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.bosmdavid-gif/dropthehassle` | 2026-10-03T115405802535 -> 2026-10-04T194958204281 | 2 changed | quiet |
| 2026-10-04 | `remote/ai.mysiren/siren` | 2026-10-03T115727185894 -> 2026-10-04T194959742440 | 1 changed, 1 added | review |
| 2026-10-04 | `remote/io.github.UltraStarz/x402-extract` | 2026-10-04T062356078958 -> 2026-10-04T194956494677 | 1 added | review |
| 2026-10-04 | `remote/build.naru/contract-compass` | 2026-10-03T054719384514 -> 2026-10-04T194958482884 | 1 changed | quiet |
| 2026-10-04 | `remote/com.buckybuild/bucky` | 2026-10-02T182049224573 -> 2026-10-04T194955683947 | 1 changed | quiet |
| 2026-10-04 | `remote/ch.blust/mental-model` | 2026-10-04T123755323290 -> 2026-10-04T194956515722 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.2016judea/small-business-intelligence` | 2026-10-02T182050555322 -> 2026-10-04T194954273635 | 1 added | quiet |
| 2026-10-04 | `remote/dev.workers.mars-economic.mars-economic-agent-gateway/mars-economic` | 2026-10-04T123730156439 -> 2026-10-04T194958303800 | 2 added | quiet |
| 2026-10-04 | `remote/io.github.hermoso-ai/hermoso` | 2026-10-04T062320934702 -> 2026-10-04T194953717036 | 3 changed | review |
| 2026-10-04 | `remote/app.apick/convert` | 2026-10-02T125201922446 -> 2026-10-04T194955456846 | 2 changed, 3 added | quiet |
| 2026-10-04 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-10-03T192839039740 -> 2026-10-04T194953002112 | 2 changed | quiet |
| 2026-10-04 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-04T142426445678 -> 2026-10-04T194951595036 | 2 changed | quiet |
| 2026-10-04 | `remote/io.github.seankarltonlee/tickermint` | 2026-10-03T232122050235 -> 2026-10-04T194952262217 | 1 changed | quiet |
| 2026-10-04 | `remote/directory.nohumans/registry` | 2026-10-04T123357405805 -> 2026-10-04T194951505904 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 14346 substantive, 4847 that changed only numbers (a catalogue counter ticking, a date), 285 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 10193 | 5683 | 4510 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `caseyjhand.com` | 72 | 72 | 0 | 0 |
| `sistaminuten.se` | 70 | 2 | 0 | 68 |
| `afbudsrejser.dk` | 69 | 2 | 0 | 67 |
| `akkilahdot.fi` | 69 | 2 | 0 | 67 |
| `restplass.no` | 69 | 2 | 0 | 67 |
| `socialloop.ai` | 67 | 67 | 0 | 0 |
| `dayze.com` | 63 | 63 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| 2102 other operators | 5893 | 5540 | 337 | 16 |
