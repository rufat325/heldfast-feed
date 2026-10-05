# MCP server tool changes

Last change observed 2026-10-05T17:27:43+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10128 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 21701 hosted endpoints (read daily, and every four hours while they keep changing).

19691 changes to a tool definition: 696 npm releases (450 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 18995 readings of hosted servers that found their tools changed; 237 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-05 | `remote/com.immersivecommons/floor10` | 2026-10-03T232146458434 -> 2026-10-05T172751883007 | 1 changed | quiet |
| 2026-10-05 | `remote/io.github.tjcgraham-rgb/gaip-witness` | 2026-10-04T055049332333 -> 2026-10-05T172752737484 | 1 changed | quiet |
| 2026-10-05 | `remote/tennis.courts/nyc-tennis-courts` | 2026-10-03T054749714746 -> 2026-10-05T172744668976 | 3 changed | quiet |
| 2026-10-05 | `remote/io.github.SoapyRED/freightutils` | 2026-10-03T121534937822 -> 2026-10-05T172746940369 | 25 changed (every tool) | quiet |
| 2026-10-05 | `remote/fi.akkilahdot/travel-search` | 2026-10-05T061634770921 -> 2026-10-05T172742499649 | 1 changed | quiet |
| 2026-10-05 | `remote/ch.swisslivingindex/swiss-living-index` | 2026-10-03T121448003812 -> 2026-10-05T172729060848 | 6 added | quiet |
| 2026-10-05 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-05T061630315260 -> 2026-10-05T172723189589 | 91 changed | quiet |
| 2026-10-05 | `remote/cc.roboparts/roboparts` | 2026-10-05T061627431223 -> 2026-10-05T172719934165 | 2 added | quiet |
| 2026-10-05 | `remote/com.remoshift/jobs` | 2026-10-05T061626626129 -> 2026-10-05T172716084744 | 1 changed | quiet |
| 2026-10-05 | `remote/xn--3ds443g.xn--s7y/duan-online` | 2026-10-05T061623175971 -> 2026-10-05T172659706730 | 6 changed (every tool) | quiet |
| 2026-10-05 | `remote/io.github.naief9961-tech/naif-fixgraph` | 2026-10-03T232134491389 -> 2026-10-05T172702832354 | 4 added, 25 removed | quiet |
| 2026-10-05 | `remote/se.sistaminuten/travel-search` | 2026-10-05T061622263202 -> 2026-10-05T172659369194 | 1 changed | quiet |
| 2026-10-05 | `remote/io.github.Travisswop/swop` | 2026-10-04T195014794124 -> 2026-10-05T172657756291 | 23 removed | quiet |
| 2026-10-05 | `remote/ru.quintadb/mcp` | 2026-10-04T142445850936 -> 2026-10-05T172655386069 | 9 added | quiet |
| 2026-10-05 | `remote/io.github.presendapp/presend-mcp` | 2026-10-04T195008856147 -> 2026-10-05T172652465612 | 1 changed | quiet |
| 2026-10-05 | `remote/io.github.Piloxa/piloxa` | 2026-10-03T115926973244 -> 2026-10-05T172651809060 | 3 changed (every tool) | quiet |
| 2026-10-05 | `remote/sh.stipple/stipple-tenders` | 2026-10-04T055122603940 -> 2026-10-05T172651772290 | 1 changed | quiet |
| 2026-10-05 | `remote/no.restplass/travel-search` | 2026-10-05T061631064628 -> 2026-10-05T172649755891 | 1 changed | quiet |
| 2026-10-05 | `remote/io.github.worklittle/jobs` | 2026-10-04T123954288653 -> 2026-10-05T172648721941 | 9 changed, 8 added, 8 removed (every tool) | quiet |
| 2026-10-05 | `remote/com.kernelcad/kernelcad` | 2026-10-03T192858920006 -> 2026-10-05T172653681838 | 2 changed | quiet |
| 2026-10-05 | `remote/dk.afbudsrejser/travel-search` | 2026-10-05T061629214627 -> 2026-10-05T172648416866 | 1 changed | quiet |
| 2026-10-05 | `remote/ai.wem3/wem-price-compare` | 2026-10-04T195023987112 -> 2026-10-05T172648149942 | 7 changed | quiet |
| 2026-10-05 | `remote/sh.stipple/openwarrant` | 2026-10-04T055227305876 -> 2026-10-05T172648854387 | 1 changed | quiet |
| 2026-10-05 | `remote/world.tokenbank/tokenbank` | 2026-10-03T115809530290 -> 2026-10-05T172646894609 | 1 changed | quiet |
| 2026-10-05 | `remote/io.github.tjcgraham-rgb/gaip-trust-assurance` | 2026-10-04T055210396777 -> 2026-10-05T172650209656 | 1 changed | quiet |
| 2026-10-05 | `remote/com.hireahelper/mcp` | 2026-10-04T142443333858 -> 2026-10-05T172649010179 | 16 added | quiet |
| 2026-10-05 | `remote/com.spacexploration/listings` | 2026-10-05T061626236100 -> 2026-10-05T172644993280 | 1 changed | quiet |
| 2026-10-05 | `remote/xyz.pflow.sim/whatif` | 2026-10-03T192912869717 -> 2026-10-05T172642246918 | 1 added | quiet |
| 2026-10-05 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-04T233807683863 -> 2026-10-05T172642547855 | 3 changed | review |
| 2026-10-05 | `remote/ai.rokha/rokha` | 2026-10-04T233758489890 -> 2026-10-05T172642781921 | 1 added | quiet |
| 2026-10-05 | `remote/ua.com.quintadb/mcp` | 2026-10-04T142449636250 -> 2026-10-05T172643856370 | 9 added | quiet |
| 2026-10-05 | `remote/com.shipshapedata/shipshape-data` | 2026-10-04T124204790984 -> 2026-10-05T172641557145 | 1 changed | quiet |
| 2026-10-05 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-10-04T194958931034 -> 2026-10-05T172639315540 | 1 changed | quiet |
| 2026-10-05 | `remote/com.quintadb/mcp` | 2026-10-04T142453713777 -> 2026-10-05T172640265541 | 9 added | quiet |
| 2026-10-05 | `remote/io.github.Perufitlife/postwire-mcp` | 2026-10-04T233802637933 -> 2026-10-05T172638187995 | 1 changed, 2 added | quiet |
| 2026-10-05 | `remote/com.tradestarinsider/edgar-insider-signals` | 2026-10-03T232142500001 -> 2026-10-05T172639093294 | 8 changed, 1 added, 5 removed (every tool) | quiet |
| 2026-10-05 | `remote/io.github.samuelzcom/chauffeur-booking` | 2026-10-03T121118181807 -> 2026-10-05T172644134384 | 1 changed | quiet |
| 2026-10-05 | `remote/io.insourcia/insourcia` | 2026-10-04T123835556206 -> 2026-10-05T172638006247 | 1 removed | quiet |
| 2026-10-05 | `remote/io.github.yzlee/opcmenu` | 2026-10-05T061618205540 -> 2026-10-05T172645978387 | 2 changed | quiet |
| 2026-10-05 | `remote/io.github.Clipform/mcp-server` | 2026-10-04T233745643799 -> 2026-10-05T172640257507 | 5 changed | quiet |
| 2026-10-05 | `remote/com.invoicevista/invoicevista` | 2026-10-03T115711856068 -> 2026-10-05T172638242732 | 1 changed | quiet |
| 2026-10-05 | `remote/app.pixly/pixly` | 2026-10-04T195018634355 -> 2026-10-05T172638588289 | 1 changed | quiet |
| 2026-10-05 | `remote/com.holdingsintel/mcp` | 2026-10-04T054648852385 -> 2026-10-05T172635702329 | 3 changed | quiet |
| 2026-10-05 | `remote/io.github.TotesMagotes/mcp-server-auth` | 2026-10-04T195005718336 -> 2026-10-05T172633799499 | 15 changed, 1 added | quiet |
| 2026-10-05 | `remote/com.tkawen/intelligence-gateway` | 2026-10-05T061626042192 -> 2026-10-05T172638426341 | 1 changed | quiet |
| 2026-10-05 | `remote/so.darwin/darwin` | 2026-10-04T195006672961 -> 2026-10-05T172633873725 | 10 changed | quiet |
| 2026-10-05 | `remote/com.streaming-lens.mcp/streaming-radar` | 2026-10-03T135720589181 -> 2026-10-05T172633751330 | 3 changed | quiet |
| 2026-10-05 | `remote/com.dimhour/catalog` | 2026-10-03T192850330142 -> 2026-10-05T172634251694 | 3 changed | quiet |
| 2026-10-05 | `remote/com.avokata/avokata` | 2026-10-03T192847912338 -> 2026-10-05T172634156913 | 1 changed | quiet |
| 2026-10-05 | `remote/com.thefilmradar/filmlab` | 2026-10-05T061615847209 -> 2026-10-05T172639121774 | 6 changed | review |
| 2026-10-05 | `remote/com.kapruka/kapruka-mcp` | 2026-10-03T120924323087 -> 2026-10-05T172631415296 | 2 changed | quiet |
| 2026-10-05 | `remote/com.jojapi/product-barcode-api` | 2026-10-03T054724521538 -> 2026-10-05T172633045688 | 1 changed | quiet |
| 2026-10-05 | `remote/com.jithox/jithox` | 2026-10-05T061610715079 -> 2026-10-05T172631244363 | 3 changed | quiet |
| 2026-10-05 | `remote/com.aiapplyd/aiapplyd` | 2026-10-04T195004703379 -> 2026-10-05T172634779254 | 5 changed | quiet |
| 2026-10-05 | `remote/io.github.Poiuyhje/eqvps` | 2026-10-04T233745290717 -> 2026-10-05T172631298576 | 1 changed | review |
| 2026-10-05 | `remote/com.hergertsynthora/synthora-x402` | 2026-10-04T233747151698 -> 2026-10-05T172631849015 | 15 changed, 15 removed | review |
| 2026-10-05 | `remote/net.gradetv/grade` | 2026-10-04T054509890362 -> 2026-10-05T172630614429 | 3 added | quiet |
| 2026-10-05 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-04T233739498154 -> 2026-10-05T172629339033 | 1 changed | quiet |
| 2026-10-05 | `remote/io.github.tang-vu/keryx` | 2026-10-03T232131897080 -> 2026-10-05T172631612286 | 2 changed | quiet |
| 2026-10-05 | `remote/io.github.Dahliyaal/justicelibre` | 2026-10-04T195001296034 -> 2026-10-05T172630470928 | 3 changed, 13 added, 36 removed (every tool) | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 14506 substantive, 4887 that changed only numbers (a catalogue counter ticking, a date), 298 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 10219 | 5684 | 4535 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `sistaminuten.se` | 73 | 2 | 0 | 71 |
| `afbudsrejser.dk` | 72 | 2 | 0 | 70 |
| `akkilahdot.fi` | 72 | 2 | 0 | 70 |
| `caseyjhand.com` | 72 | 72 | 0 | 0 |
| `restplass.no` | 72 | 2 | 0 | 70 |
| `socialloop.ai` | 70 | 70 | 0 | 0 |
| `dayze.com` | 63 | 63 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| 2103 other operators | 6065 | 5696 | 352 | 17 |
