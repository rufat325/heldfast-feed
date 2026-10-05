# MCP server tool changes

Last change observed 2026-10-05T06:16:35+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 19746 hosted endpoints (read daily, and every four hours while they keep changing).

19603 changes to a tool definition: 696 npm releases (450 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 18907 readings of hosted servers that found their tools changed; 232 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-05 | `remote/com.youspot/youspot` | 2026-10-04T233814965304 -> 2026-10-05T061636981249 | 3 added | quiet |
| 2026-10-05 | `remote/fi.akkilahdot/travel-search` | 2026-10-04T233800917229 -> 2026-10-05T061634770921 | 1 changed | quiet |
| 2026-10-05 | `remote/world.agentindex/x402` | 2026-10-04T195028795233 -> 2026-10-05T061632540754 | 1 changed | review |
| 2026-10-05 | `remote/no.restplass/travel-search` | 2026-10-04T233806001089 -> 2026-10-05T061631064628 | 1 changed | quiet |
| 2026-10-05 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-04T055007013376 -> 2026-10-05T061630386108 | 1 changed | quiet |
| 2026-10-05 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-04T233756004777 -> 2026-10-05T061630315260 | 1 changed | quiet |
| 2026-10-05 | `remote/io.github.SiliconAnalysts/silicon-analysts` | 2026-10-04T054941277406 -> 2026-10-05T061629336772 | 1 added | quiet |
| 2026-10-05 | `remote/dk.afbudsrejser/travel-search` | 2026-10-04T233804564221 -> 2026-10-05T061629214627 | 1 changed | quiet |
| 2026-10-05 | `remote/com.innergcomplete/shearquery` | 2026-10-04T195019887166 -> 2026-10-05T061628227787 | 10 added | quiet |
| 2026-10-05 | `remote/cc.roboparts/roboparts` | 2026-10-04T124110159318 -> 2026-10-05T061627431223 | 2 added | quiet |
| 2026-10-05 | `remote/com.spacexploration/listings` | 2026-10-03T232148470558 -> 2026-10-05T061626236100 | 8 changed | quiet |
| 2026-10-05 | `remote/com.remoshift/jobs` | 2026-10-04T233754008546 -> 2026-10-05T061626626129 | 1 changed | quiet |
| 2026-10-05 | `remote/dev.mcphost/mcphost` | 2026-10-04T195013629346 -> 2026-10-05T061626517900 | 1 changed | quiet |
| 2026-10-05 | `remote/com.tkawen/intelligence-gateway` | 2026-10-04T233754132874 -> 2026-10-05T061626042192 | 1 changed | quiet |
| 2026-10-05 | `remote/app.sallim/korea-realty` | 2026-10-04T195017486982 -> 2026-10-05T061625266136 | 1 changed | quiet |
| 2026-10-05 | `remote/xn--3ds443g.xn--s7y/duan-online` | 2026-10-03T054757881534 -> 2026-10-05T061623175971 | 6 changed, 4 removed (every tool) | quiet |
| 2026-10-05 | `remote/se.sistaminuten/travel-search` | 2026-10-04T233807089063 -> 2026-10-05T061622263202 | 1 changed | quiet |
| 2026-10-05 | `remote/io.github.manavmishra/zero-slop` | 2026-10-04T054811841966 -> 2026-10-05T061621972652 | 1 changed | quiet |
| 2026-10-05 | `remote/com.multicinesortega/cartelera` | 2026-10-04T233751062227 -> 2026-10-05T061623690080 | 1 changed | quiet |
| 2026-10-05 | `remote/com.thefomite/fomite` | 2026-10-04T055103512140 -> 2026-10-05T061620804947 | 1 changed | quiet |
| 2026-10-05 | `remote/io.github.salemalem/npmscan` | 2026-10-03T121128978776 -> 2026-10-05T061621038381 | 1 changed | quiet |
| 2026-10-05 | `remote/com.sssnack/sssnack` | 2026-10-04T055053705357 -> 2026-10-05T061621341282 | 1 changed | quiet |
| 2026-10-05 | `remote/com.mcpcheckup/mcp` | 2026-10-04T054819828760 -> 2026-10-05T061620761488 | 3 changed | quiet |
| 2026-10-05 | `remote/com.jojapi/swift-ai` | 2026-10-04T054651694276 -> 2026-10-05T061620525937 | 1 changed | quiet |
| 2026-10-05 | `remote/io.github.pipeworx-io/zippopotam` | 2026-10-03T120729903060 -> 2026-10-05T061617240340 | 4 changed | quiet |
| 2026-10-05 | `remote/io.github.pipeworx-io/yc-rejection` | 2026-10-03T120711946206 -> 2026-10-05T061617255487 | 4 changed | quiet |
| 2026-10-05 | `remote/io.github.pipeworx-io/wmata` | 2026-10-03T120709367908 -> 2026-10-05T061617076098 | 4 changed | quiet |
| 2026-10-05 | `remote/io.github.pipeworx-io/wikidata-sparql` | 2026-10-03T120650701788 -> 2026-10-05T061616851865 | 4 changed | quiet |
| 2026-10-05 | `remote/io.github.pipeworx-io/who-tb` | 2026-10-03T120650426154 -> 2026-10-05T061616741236 | 4 changed | quiet |
| 2026-10-05 | `remote/io.github.pipeworx-io/waqi` | 2026-10-03T120644350455 -> 2026-10-05T061616399990 | 4 changed | quiet |
| 2026-10-05 | `remote/io.github.pipeworx-io/vizier` | 2026-10-03T120630751880 -> 2026-10-05T061616462921 | 4 changed | quiet |
| 2026-10-05 | `remote/io.github.pipeworx-io/vermont-code` | 2026-10-03T120629995890 -> 2026-10-05T061616526091 | 4 changed | quiet |
| 2026-10-05 | `remote/io.github.pipeworx-io/uuid` | 2026-10-03T120630071041 -> 2026-10-05T061616195132 | 4 changed | quiet |
| 2026-10-05 | `remote/io.github.pipeworx-io/usno-astronomy` | 2026-10-03T120629825194 -> 2026-10-05T061616119777 | 4 changed | quiet |
| 2026-10-05 | `remote/io.github.pipeworx-io/usaspending` | 2026-10-03T120624016544 -> 2026-10-05T061615733058 | 5 changed | quiet |
| 2026-10-05 | `remote/io.github.pipeworx-io/uk-tribunals` | 2026-10-03T120610192575 -> 2026-10-05T061615753868 | 4 changed | quiet |
| 2026-10-05 | `remote/io.github.pipeworx-io/uk-charity-commission` | 2026-10-03T120609622076 -> 2026-10-05T061615574760 | 4 changed | quiet |
| 2026-10-05 | `remote/com.donebear/donebear` | 2026-10-04T123826278732 -> 2026-10-05T061617705251 | 8 changed | quiet |
| 2026-10-05 | `remote/io.github.yzlee/opcmenu` | 2026-10-04T233756324277 -> 2026-10-05T061618205540 | 29 changed, 21 added | quiet |
| 2026-10-05 | `remote/io.github.pipeworx-io/tx-procurement` | 2026-10-03T120603586249 -> 2026-10-05T061615628414 | 4 changed | quiet |
| 2026-10-05 | `remote/io.github.pipeworx-io/treasury-fiscal` | 2026-10-03T120549316987 -> 2026-10-05T061615386136 | 4 changed | quiet |
| 2026-10-05 | `remote/com.thefilmradar/filmlab` | 2026-10-04T233742947054 -> 2026-10-05T061615847209 | 1 changed | quiet |
| 2026-10-05 | `remote/io.github.pipeworx-io/travel-feeds` | 2026-10-04T123649491934 -> 2026-10-05T061614723463 | 4 changed | quiet |
| 2026-10-05 | `remote/io.github.pipeworx-io/swisstransport` | 2026-10-04T054458228340 -> 2026-10-05T061614738411 | 4 changed | quiet |
| 2026-10-05 | `remote/ai.greenlandai/greenlandai` | 2026-10-04T233750498275 -> 2026-10-05T061615398247 | 2 changed | quiet |
| 2026-10-05 | `remote/net.hotelrefund/price-tracker` | 2026-10-04T054512309092 -> 2026-10-05T061612875798 | 1 changed | quiet |
| 2026-10-05 | `remote/io.github.pipeworx-io/seatgeek` | 2026-10-04T054455451837 -> 2026-10-05T061614684587 | 4 changed | quiet |
| 2026-10-05 | `remote/io.github.pipeworx-io/nosdeputes-fr` | 2026-10-04T054447178023 -> 2026-10-05T061614752672 | 4 changed | quiet |
| 2026-10-05 | `remote/io.github.pipeworx-io/dostuff` | 2026-10-04T054433078755 -> 2026-10-05T061615061336 | 4 changed | quiet |
| 2026-10-05 | `remote/cn.narracore/screenplay-formatter` | 2026-10-03T115728380800 -> 2026-10-05T061615270390 | 14 changed (every tool) | quiet |
| 2026-10-05 | `remote/io.github.pipeworx-io/walkscore` | 2026-10-03T120955680981 -> 2026-10-05T061612256997 | 4 changed | quiet |
| 2026-10-05 | `remote/io.github.UltraStarz/x402-extract` | 2026-10-04T194956494677 -> 2026-10-05T061612572799 | 1 changed, 3 added | quiet |
| 2026-10-05 | `remote/io.github.pipeworx-io/twilio` | 2026-10-04T054450688352 -> 2026-10-05T061612239916 | 4 changed | quiet |
| 2026-10-05 | `remote/io.github.pipeworx-io/token-risk` | 2026-10-04T054450042099 -> 2026-10-05T061612210210 | 4 changed | quiet |
| 2026-10-05 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt` | 2026-10-04T054348583910 -> 2026-10-05T061610578742 | 4 changed | quiet |
| 2026-10-05 | `remote/com.jithox/jithox` | 2026-10-04T054534781997 -> 2026-10-05T061610715079 | 3 changed | quiet |
| 2026-10-05 | `remote/ai.agentlookups/groundtruth` | 2026-10-04T054344314761 -> 2026-10-05T061610417420 | 1 changed, 1 added, 1 removed | quiet |
| 2026-10-05 | `remote/co.bitcoinyield/yields` | 2026-10-04T194947759219 -> 2026-10-05T061608833434 | 1 changed | quiet |
| 2026-10-05 | `remote/io.github.whiteknightonhorse/apibase` | 2026-10-04T194948453859 -> 2026-10-05T061609007190 | 4 removed | quiet |
| 2026-10-05 | `remote/io.github.troothllc/trooth-network` | 2026-10-03T115251114796 -> 2026-10-05T061607797646 | 6 changed (every tool) | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 14430 substantive, 4879 that changed only numbers (a catalogue counter ticking, a date), 294 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 10217 | 5684 | 4533 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `caseyjhand.com` | 72 | 72 | 0 | 0 |
| `sistaminuten.se` | 72 | 2 | 0 | 70 |
| `afbudsrejser.dk` | 71 | 2 | 0 | 69 |
| `akkilahdot.fi` | 71 | 2 | 0 | 69 |
| `restplass.no` | 71 | 2 | 0 | 69 |
| `socialloop.ai` | 69 | 69 | 0 | 0 |
| `dayze.com` | 63 | 63 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| 2102 other operators | 5984 | 5621 | 346 | 17 |
