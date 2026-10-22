# MCP server tool changes

Last change observed 2026-10-22T23:39:44+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

42796 changes to a tool definition: 1838 npm releases (1592 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 40958 readings of hosted servers that found their tools changed; 2390 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-22 | `remote/ai.usedby/usedby` | 2026-10-22T202102118861 -> 2026-10-22T233947796808 | 1 changed | quiet |
| 2026-10-22 | `remote/se.sistaminuten/travel-search` | 2026-10-22T202101577997 -> 2026-10-22T233944844089 | 1 changed | quiet |
| 2026-10-22 | `remote/io.taifoon/coordination-layer.1` | 2026-10-22T202101408000 -> 2026-10-22T233944866106 | 1 changed | review |
| 2026-10-22 | `remote/com.theprotoclinical/commerce` | 2026-10-21T122232046114 -> 2026-10-22T233941206989 | 2 changed | quiet |
| 2026-10-22 | `remote/com.mintlify/searchmcp` | 2026-10-21T234238617960 -> 2026-10-22T233940384027 | 3 changed (every tool) | quiet |
| 2026-10-22 | `remote/studio.gradients/mcp` | 2026-10-22T202103341448 -> 2026-10-22T233939994929 | 1 changed | quiet |
| 2026-10-22 | `remote/no.restplass/travel-search` | 2026-10-22T202203764181 -> 2026-10-22T233939757568 | 1 changed | quiet |
| 2026-10-22 | `remote/fi.akkilahdot/travel-search` | 2026-10-22T202102519202 -> 2026-10-22T233938726543 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.CodeWever/wever-labs-products` | 2026-10-22T202102313309 -> 2026-10-22T233938067665 | 2 changed | quiet |
| 2026-10-22 | `remote/dk.afbudsrejser/travel-search` | 2026-10-22T202201979438 -> 2026-10-22T233937192863 | 1 changed | quiet |
| 2026-10-22 | `remote/com.transitmcp/transit-mcp` | 2026-10-22T202100037937 -> 2026-10-22T233936853367 | 2 changed | quiet |
| 2026-10-22 | `remote/io.github.zambodotdev/zambo` | 2026-10-20T201155815754 -> 2026-10-22T233935270363 | 35 changed (every tool) | quiet |
| 2026-10-22 | `remote/dev.zambo/zambo` | 2026-10-20T201156306148 -> 2026-10-22T233935433298 | 35 changed (every tool) | quiet |
| 2026-10-22 | `remote/com.youspot/youspot` | 2026-10-21T202510356705 -> 2026-10-22T233935621172 | 2 changed | quiet |
| 2026-10-22 | `remote/com.underpricedai/underpriced-ai` | 2026-10-22T202159493625 -> 2026-10-22T233934873435 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.muaviamohammed/mizan` | 2026-10-22T202052512617 -> 2026-10-22T233936826270 | 1 changed | quiet |
| 2026-10-22 | `remote/com.tradeassi/mcp` | 2026-10-20T201156714123 -> 2026-10-22T233933120410 | 2 changed, 2 added | quiet |
| 2026-10-22 | `remote/com.tablejourney/food-travel` | 2026-10-22T202058093972 -> 2026-10-22T233933697113 | 1 changed, 1 added | quiet |
| 2026-10-22 | `remote/com.swarmmemo/bulletin` | 2026-10-22T202057416627 -> 2026-10-22T233933553742 | 2 added, 92 removed | quiet |
| 2026-10-22 | `remote/io.github.JacobiusMakes/stienhardt-store` | 2026-10-21T122035198771 -> 2026-10-22T233932645909 | 2 changed | quiet |
| 2026-10-22 | `remote/ai.satohub/onchain-agents` | 2026-10-22T202046502396 -> 2026-10-22T233933166278 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-22T202055308091 -> 2026-10-22T233932018753 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-10-22T052605788844 -> 2026-10-22T233929949328 | 6 removed | quiet |
| 2026-10-22 | `remote/io.github.Timothymycompc/solana-pulse-gateway` | 2026-10-20T052337185539 -> 2026-10-22T233928155214 | 2 changed | quiet |
| 2026-10-22 | `remote/io.github.jennipro-engineering/ghost-market-web` | 2026-10-22T202101564832 -> 2026-10-22T233925745098 | 1 changed | quiet |
| 2026-10-22 | `remote/com.remoshift/jobs` | 2026-10-22T202052483537 -> 2026-10-22T233927214983 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.wygogogo19/robotbase-mcp` | 2026-10-22T105954815171 -> 2026-10-22T233925797265 | 1 changed, 1 added | quiet |
| 2026-10-22 | `remote/fun.pumpdata/pumpdata` | 2026-10-22T202149497502 -> 2026-10-22T233923153424 | 1 changed | quiet |
| 2026-10-22 | `remote/app.sallim/korea-realty` | 2026-10-22T202151592462 -> 2026-10-22T233925111700 | 7 changed, 1 added | quiet |
| 2026-10-22 | `remote/world.tokenbank/tokenbank` | 2026-10-21T234203493935 -> 2026-10-22T233923267362 | 1 changed | quiet |
| 2026-10-22 | `remote/online.pageaudit/pageaudit` | 2026-10-21T052234261499 -> 2026-10-22T233922120558 | 1 changed | quiet |
| 2026-10-22 | `remote/com.stockfilm/mcp-server` | 2026-10-21T121800867317 -> 2026-10-22T233921333617 | 4 changed | review |
| 2026-10-22 | `remote/com.plainrouter/mcp` | 2026-10-21T121900477098 -> 2026-10-22T233921716628 | 7 added, 7 removed | quiet |
| 2026-10-22 | `remote/com.moonshotlab1/inventory` | 2026-10-22T202145691822 -> 2026-10-22T233919067500 | 1 changed | quiet |
| 2026-10-22 | `remote/com.neblla/neblla` | 2026-10-22T105622705188 -> 2026-10-22T233918728267 | 119 changed, 38 added, 1 removed (every tool) | quiet |
| 2026-10-22 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-10-22T202029713261 -> 2026-10-22T233916573142 | 1 changed | review |
| 2026-10-22 | `remote/com.mcpcheckup/mcp` | 2026-10-20T201123829310 -> 2026-10-22T233917137375 | 3 changed | quiet |
| 2026-10-22 | `remote/com.negativeresistance/cure-protocol` | 2026-10-21T234157880130 -> 2026-10-22T233915465396 | 1 changed | quiet |
| 2026-10-22 | `remote/com.googleapis.memorystore/mcp` | 2026-10-22T202045769888 -> 2026-10-22T233915450647 | 4 changed | quiet |
| 2026-10-22 | `remote/com.modmillennialdesigns/modmillennialdesigns` | 2026-10-21T121802767322 -> 2026-10-22T233913256650 | 2 changed | quiet |
| 2026-10-22 | `remote/io.github.choaticpixels/wicked-mcp` | 2026-10-22T202046001258 -> 2026-10-22T233911715297 | 4 added | quiet |
| 2026-10-22 | `remote/com.webinarignition/mcp` | 2026-10-22T140833909160 -> 2026-10-22T233910321287 | 1 changed | quiet |
| 2026-10-22 | `remote/ai.makememoneynomistakes/scoreboard` | 2026-10-22T202019833054 -> 2026-10-22T233907817394 | 6 changed | review |
| 2026-10-22 | `remote/io.github.hail-hq/hail-mcp` | 2026-10-21T234137209626 -> 2026-10-22T233908495957 | 4 changed | quiet |
| 2026-10-22 | `remote/io.github.dstrausser83/db-collab-hub` | 2026-10-22T202037707695 -> 2026-10-22T233906414926 | 3 changed | quiet |
| 2026-10-22 | `remote/ai.certscore/mcp-light` | 2026-10-22T105553479573 -> 2026-10-22T233906240687 | 3 changed | quiet |
| 2026-10-22 | `remote/io.github.OV3RK177/kairos-signal` | 2026-10-22T105136965021 -> 2026-10-22T233905629388 | 5 added | quiet |
| 2026-10-22 | `remote/com.kairossignal/kairos-signal` | 2026-10-22T105137003318 -> 2026-10-22T233905456055 | 5 added | quiet |
| 2026-10-22 | `remote/io.github.mzizi-dev/mzizi-mcp` | 2026-10-21T121624318233 -> 2026-10-22T233904160008 | 3 changed | quiet |
| 2026-10-22 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-22T202012987258 -> 2026-10-22T233902480752 | 2 changed | quiet |
| 2026-10-22 | `remote/io.github.Yahhi/aimyear-mcp` | 2026-10-20T135337410870 -> 2026-10-22T233902503445 | 3 changed, 8 added | quiet |
| 2026-10-22 | `remote/com.movingplace/mcp` | 2026-10-22T140825996645 -> 2026-10-22T233902426331 | 16 removed | quiet |
| 2026-10-22 | `remote/com.jabbertoon/cartoon-studio` | 2026-10-21T121417642642 -> 2026-10-22T233859489803 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.lgs1520/agent-procurement-manager` | 2026-10-22T202030993874 -> 2026-10-22T233858357289 | 1 added | quiet |
| 2026-10-22 | `remote/com.algotrada.cubicle/cubicle` | 2026-10-21T121055724015 -> 2026-10-22T233858707615 | 2 changed, 3 added | quiet |
| 2026-10-22 | `remote/co.ainumbers/tools` | 2026-10-22T202029200757 -> 2026-10-22T233858421899 | 2 changed | quiet |
| 2026-10-22 | `remote/ai.capitalcompany/capital-company` | 2026-10-21T202402004578 -> 2026-10-22T233854920800 | 1 changed | quiet |
| 2026-10-22 | `remote/com.basketwatchireland/basketwatch` | 2026-10-21T202356052935 -> 2026-10-22T233853777832 | 1 changed | quiet |
| 2026-10-22 | `remote/io.taifoon/coordination-layer` | 2026-10-22T202109692400 -> 2026-10-22T233856705293 | 1 changed | review |
| 2026-10-22 | `remote/io.github.edtool79-collab/hirepulse-gateway` | 2026-10-22T202024372394 -> 2026-10-22T233852203359 | 8 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 27887 substantive, 14332 that changed only numbers (a catalogue counter ticking, a date), 577 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 22156 | 8734 | 13422 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 654 | 654 | 0 | 0 |
| `caseyjhand.com` | 174 | 174 | 0 | 0 |
| `sistaminuten.se` | 137 | 4 | 0 | 133 |
| `afbudsrejser.dk` | 136 | 4 | 0 | 132 |
| `akkilahdot.fi` | 136 | 4 | 0 | 132 |
| `restplass.no` | 136 | 4 | 0 | 132 |
| `socialloop.ai` | 132 | 132 | 0 | 0 |
| `remoshift.com` | 107 | 8 | 99 | 0 |
| `fundinglandscape.com` | 105 | 70 | 35 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| 5127 other operators | 16485 | 15661 | 776 | 48 |
