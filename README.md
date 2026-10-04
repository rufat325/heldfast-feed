# MCP server tool changes

Last change observed 2026-10-04T23:38:14+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 19746 hosted endpoints (read daily, and every four hours while they keep changing).

19526 changes to a tool definition: 696 npm releases (450 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 18830 readings of hosted servers that found their tools changed; 230 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-04 | `remote/dev.zambo/zambo` | 2026-10-03T121419737923 -> 2026-10-04T233814844835 | 1 changed | review |
| 2026-10-04 | `remote/io.github.zambodotdev/zambo` | 2026-10-03T121419603874 -> 2026-10-04T233814465294 | 1 changed | review |
| 2026-10-04 | `remote/com.youspot/youspot` | 2026-10-03T054748706303 -> 2026-10-04T233814965304 | 6 changed, 1 added | quiet |
| 2026-10-04 | `remote/cc.thecolony/mcp-server` | 2026-10-04T124241329758 -> 2026-10-04T233810043852 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-04T124219132385 -> 2026-10-04T233807683863 | 20 changed | quiet |
| 2026-10-04 | `remote/se.sistaminuten/travel-search` | 2026-10-04T195017393401 -> 2026-10-04T233807089063 | 1 changed | quiet |
| 2026-10-04 | `remote/no.restplass/travel-search` | 2026-10-04T195027263237 -> 2026-10-04T233806001089 | 1 changed | quiet |
| 2026-10-04 | `remote/dk.afbudsrejser/travel-search` | 2026-10-04T195025062415 -> 2026-10-04T233804564221 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.Perufitlife/postwire-mcp` | 2026-10-04T195019380771 -> 2026-10-04T233802637933 | 3 changed | quiet |
| 2026-10-04 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-10-04T195020393052 -> 2026-10-04T233801251680 | 15 changed | review |
| 2026-10-04 | `remote/fi.akkilahdot/travel-search` | 2026-10-04T195026649679 -> 2026-10-04T233800917229 | 1 changed | quiet |
| 2026-10-04 | `remote/com.luxurylodgingpm.stay/luxury-lodging` | 2026-10-04T054959680415 -> 2026-10-04T233800714346 | 1 changed | quiet |
| 2026-10-04 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-04T195018703942 -> 2026-10-04T233800273687 | 2 changed | quiet |
| 2026-10-04 | `remote/io.github.SidneyBissoli/senado-br-mcp-cloudflare` | 2026-10-02T182731142437 -> 2026-10-04T233800787059 | 69 changed (every tool) | quiet |
| 2026-10-04 | `remote/com.plainrouter/mcp` | 2026-10-04T195018959972 -> 2026-10-04T233801520503 | 3 changed | quiet |
| 2026-10-04 | `remote/ai.rokha/rokha` | 2026-10-04T054927814516 -> 2026-10-04T233758489890 | 3 added | quiet |
| 2026-10-04 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-04T195021147214 -> 2026-10-04T233756004777 | 1 changed | quiet |
| 2026-10-04 | `remote/com.trustycap/trustycap` | 2026-10-02T071851370949 -> 2026-10-04T233754982382 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.quotor/home-auto-insurance-quotes` | 2026-10-03T192855946416 -> 2026-10-04T233753603122 | 2 changed | quiet |
| 2026-10-04 | `remote/com.remoshift/jobs` | 2026-10-04T195019597963 -> 2026-10-04T233754008546 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.yzlee/opcmenu` | 2026-10-04T195012333544 -> 2026-10-04T233756324277 | 4 changed | quiet |
| 2026-10-04 | `remote/com.usecarscout/mcp` | 2026-10-03T232131519666 -> 2026-10-04T233752331895 | 2 changed | quiet |
| 2026-10-04 | `remote/com.tkawen/intelligence-gateway` | 2026-10-04T123955982057 -> 2026-10-04T233754132874 | 1 changed | quiet |
| 2026-10-04 | `remote/com.subastech/subastas-judiciales` | 2026-10-04T142439147349 -> 2026-10-04T233752606263 | 6 changed, 5 removed | quiet |
| 2026-10-04 | `remote/io.github.linxule/mcp-music-studio` | 2026-10-04T124013585433 -> 2026-10-04T233750818476 | 1 changed | quiet |
| 2026-10-04 | `remote/com.multicinesortega/cartelera` | 2026-10-04T054827167572 -> 2026-10-04T233751062227 | 1 changed | quiet |
| 2026-10-04 | `remote/ai.greenlandai/greenlandai` | 2026-10-04T195007492689 -> 2026-10-04T233750498275 | 2 changed, 1 added | quiet |
| 2026-10-04 | `remote/com.ruzora/ruzora` | 2026-10-04T123932116520 -> 2026-10-04T233748410242 | 2 changed | quiet |
| 2026-10-04 | `remote/com.movingplace/mcp` | 2026-10-04T195006350861 -> 2026-10-04T233747896194 | 16 removed | quiet |
| 2026-10-04 | `remote/com.commerceforagents/commerceforagents` | 2026-10-03T232134535118 -> 2026-10-04T233748273246 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.truefixr/atlascast-truefixr` | 2026-10-04T123902324539 -> 2026-10-04T233746649323 | 1 changed | quiet |
| 2026-10-04 | `remote/com.hergertsynthora/synthora-x402` | 2026-10-04T123854736965 -> 2026-10-04T233747151698 | 2 added | review |
| 2026-10-04 | `remote/io.github.Poiuyhje/eqvps` | 2026-10-03T232125708696 -> 2026-10-04T233745290717 | 3 changed | quiet |
| 2026-10-04 | `remote/io.github.Clipform/mcp-server` | 2026-10-03T232125347988 -> 2026-10-04T233745643799 | 3 changed | quiet |
| 2026-10-04 | `remote/com.thefilmradar/filmlab` | 2026-10-04T195009705752 -> 2026-10-04T233742947054 | 2 changed | quiet |
| 2026-10-04 | `remote/io.github.hermoso-ai/hermoso` | 2026-10-04T194953717036 -> 2026-10-04T233740272796 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-04T194951595036 -> 2026-10-04T233739498154 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.physics-star-cat/databutler-uk-rates` | 2026-10-03T115421615671 -> 2026-10-04T233737704609 | 1 changed | quiet |
| 2026-10-04 | `remote/com.cve-security/cve-intelligence` | 2026-10-04T194948163283 -> 2026-10-04T233736389135 | 1 changed | quiet |
| 2026-10-04 | `remote/com.googleapis.bigtableadmin/mcp` | 2026-10-04T194946096866 -> 2026-10-04T233734405989 | 3 changed | quiet |
| 2026-10-04 | `remote/com.prereason/mcp` | 2026-10-04T054138049614 -> 2026-10-04T233734129505 | 1 added | quiet |
| 2026-10-04 | `remote/com.hookdetector/hookdetector` | 2026-10-03T114948467808 -> 2026-10-04T233733194561 | 1 changed | quiet |
| 2026-10-04 | `remote/holdings.proof/mcp-server` | 2026-10-02T071307841507 -> 2026-10-04T233733897719 | 25 changed | quiet |
| 2026-10-04 | `remote/com.zfinia.api/intelligence` | 2026-10-04T054214741931 -> 2026-10-04T233734797346 | 4 added | quiet |
| 2026-10-04 | `remote/cc.rockpool.ai-deals/ai-deals-sentinel` | 2026-10-03T054716290122 -> 2026-10-04T233731345628 | 2 changed | quiet |
| 2026-10-04 | `remote/directory.nohumans/registry` | 2026-10-04T194951505904 -> 2026-10-04T233730534669 | 1 changed | quiet |
| 2026-10-04 | `remote/com.aisenseapi/free-public-tools` | 2026-10-04T194943258643 -> 2026-10-04T233731101444 | 5 added | quiet |
| 2026-10-04 | `remote/biz.nibiashara/shelves` | 2026-10-04T123137292008 -> 2026-10-04T233728941312 | 1 changed | quiet |
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

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 14386 substantive, 4850 that changed only numbers (a catalogue counter ticking, a date), 290 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 10193 | 5683 | 4510 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `caseyjhand.com` | 72 | 72 | 0 | 0 |
| `sistaminuten.se` | 71 | 2 | 0 | 69 |
| `afbudsrejser.dk` | 70 | 2 | 0 | 68 |
| `akkilahdot.fi` | 70 | 2 | 0 | 68 |
| `restplass.no` | 70 | 2 | 0 | 68 |
| `socialloop.ai` | 68 | 68 | 0 | 0 |
| `dayze.com` | 63 | 63 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| 2102 other operators | 5936 | 5579 | 340 | 17 |
