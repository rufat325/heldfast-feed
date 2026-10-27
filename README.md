# MCP server tool changes

Last change observed 2026-10-27T21:02:35+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

55721 changes to a tool definition: 2384 npm releases (2138 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 53337 readings of hosted servers that found their tools changed; 2835 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-27 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-10-27T145913159587 -> 2026-10-27T210236352173 | 1 changed, 1 added | quiet |
| 2026-10-27 | `remote/no.restplass/travel-search` | 2026-10-27T145910603890 -> 2026-10-27T210234305559 | 1 changed | quiet |
| 2026-10-27 | `remote/dev.pressmark/pressmark` | 2026-10-26T211532912207 -> 2026-10-27T210233463635 | 6 changed (every tool) | quiet |
| 2026-10-27 | `remote/io.deeplead/deeplead` | 2026-10-27T112518891832 -> 2026-10-27T210232038622 | 1 changed | quiet |
| 2026-10-27 | `remote/dk.afbudsrejser/travel-search` | 2026-10-27T145907085269 -> 2026-10-27T210230412140 | 1 changed | quiet |
| 2026-10-27 | `remote/com.whenisbins/bin-collections` | 2026-10-25T102511350311 -> 2026-10-27T210230271238 | 4 changed (every tool) | quiet |
| 2026-10-27 | `remote/io.github.Ockram4444/agentcompute` | 2026-10-27T145903554815 -> 2026-10-27T210223646724 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-10-27T145928035689 -> 2026-10-27T210221519310 | 1 changed, 1 added | quiet |
| 2026-10-27 | `remote/io.taifoon/coordination-layer.1` | 2026-10-27T124557689752 -> 2026-10-27T210219076370 | 1 changed | review |
| 2026-10-27 | `remote/xyz.trusteed/mcp-gateway` | 2026-10-26T211524019145 -> 2026-10-27T210223484083 | 1 changed | quiet |
| 2026-10-27 | `remote/se.sistaminuten/travel-search` | 2026-10-27T145925327113 -> 2026-10-27T210218276586 | 1 changed | quiet |
| 2026-10-27 | `remote/com.zinvyl/marketplace` | 2026-10-27T145905673499 -> 2026-10-27T210214291968 | 13 changed | quiet |
| 2026-10-27 | `remote/com.nythosx.tools/agent-tools` | 2026-10-27T124118751570 -> 2026-10-27T210215209427 | 1 changed, 2 added | review |
| 2026-10-27 | `remote/io.github.yappmaniac/grocery-price-snapshots` | 2026-10-27T112301281755 -> 2026-10-27T210211612801 | 1 added | quiet |
| 2026-10-27 | `remote/xyz.urbangametheory/urban-game-theory` | 2026-10-27T145914096124 -> 2026-10-27T210206250778 | 1 changed | quiet |
| 2026-10-27 | `remote/studio.gradients/mcp` | 2026-10-27T145853669856 -> 2026-10-27T210205208947 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.xzntexe/yruz-x402` | 2026-10-27T124233973362 -> 2026-10-27T210203814695 | 1 changed | quiet |
| 2026-10-27 | `remote/fr.synergieloc/immobilier` | 2026-10-27T112333597358 -> 2026-10-27T210205457328 | 14 added | quiet |
| 2026-10-27 | `remote/fi.akkilahdot/travel-search` | 2026-10-27T145850087403 -> 2026-10-27T210202175744 | 1 changed | quiet |
| 2026-10-27 | `remote/com.techfabric/techfabric` | 2026-10-27T112443457790 -> 2026-10-27T210206045584 | 1 changed, 1 added | quiet |
| 2026-10-27 | `remote/io.github.CodeWever/wever-labs-products` | 2026-10-25T052301574689 -> 2026-10-27T210200371111 | 2 added | quiet |
| 2026-10-27 | `remote/io.github.Timothymycompc/solana-pulse-gateway` | 2026-10-27T112305169237 -> 2026-10-27T210157412477 | 1 changed | quiet |
| 2026-10-27 | `remote/com.textforagents/downloadbridge-browser-download-delivery` | 2026-10-26T133716455533 -> 2026-10-27T210158306420 | 1 changed | quiet |
| 2026-10-27 | `remote/lol.wukong.world/agent-world` | 2026-10-26T211520621032 -> 2026-10-27T210157929401 | 3 changed, 9 added | quiet |
| 2026-10-27 | `remote/io.github.SecondShotAI/verifylite` | 2026-10-27T145845813468 -> 2026-10-27T210157931583 | 1 added | quiet |
| 2026-10-27 | `remote/io.github.tokenzero-ai/tokenzero` | 2026-10-27T054110421779 -> 2026-10-27T210154724126 | 1 changed | quiet |
| 2026-10-27 | `remote/pro.sebbi/governance` | 2026-10-27T054049874149 -> 2026-10-27T210153323515 | 1 changed | quiet |
| 2026-10-27 | `remote/dev.upfork/upfork` | 2026-10-27T145855856662 -> 2026-10-27T210152953692 | 3 changed, 2 added | quiet |
| 2026-10-27 | `remote/co.totalcms/docs` | 2026-10-26T133534227101 -> 2026-10-27T210151533871 | 4 changed | quiet |
| 2026-10-27 | `remote/com.swarmmemo/bulletin.1` | 2026-10-27T112104383981 -> 2026-10-27T210150478759 | 1 changed | quiet |
| 2026-10-27 | `remote/com.swarmmemo/bulletin` | 2026-10-27T112104131064 -> 2026-10-27T210149856913 | 1 changed | quiet |
| 2026-10-27 | `remote/com.stayotter/stay-otter` | 2026-10-27T145837314828 -> 2026-10-27T210148261022 | 2 changed, 1 added | quiet |
| 2026-10-27 | `remote/io.github.CSteenkamp/realtap` | 2026-10-26T133415728262 -> 2026-10-27T210147594818 | 6 added | quiet |
| 2026-10-27 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-27T145835141929 -> 2026-10-27T210145157257 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.Fizzl13/presign-guard` | 2026-10-27T145839786002 -> 2026-10-27T210143016733 | 6 changed | quiet |
| 2026-10-27 | `remote/link.snip/snip` | 2026-10-27T054113118623 -> 2026-10-27T210141707271 | 10 changed | quiet |
| 2026-10-27 | `remote/dev.polyfork/polyfork` | 2026-10-26T133350259938 -> 2026-10-27T210142052852 | 7 changed | quiet |
| 2026-10-27 | `remote/io.github.cloakmaster/pact0` | 2026-10-26T052244309066 -> 2026-10-27T210138848340 | 2 changed, 1 added | quiet |
| 2026-10-27 | `remote/com.skinwinking/agent-tollgate` | 2026-10-27T112140262741 -> 2026-10-27T210139340972 | 1 changed | quiet |
| 2026-10-27 | `remote/es.proceres/proceres` | 2026-10-27T112027244530 -> 2026-10-27T210137211644 | 5 changed | quiet |
| 2026-10-27 | `remote/io.github.jakegallen/poascan` | 2026-10-27T145838945860 -> 2026-10-27T210136274770 | 4 added | quiet |
| 2026-10-27 | `remote/io.github.imiraoui/rentreboot` | 2026-10-26T133233882582 -> 2026-10-27T210137222861 | 1 added, 1 removed | quiet |
| 2026-10-27 | `remote/com.remoshift/jobs` | 2026-10-27T145828492743 -> 2026-10-27T210137186005 | 1 changed | quiet |
| 2026-10-27 | `remote/gg.remix/remix-games` | 2026-10-26T133350558327 -> 2026-10-27T210134926378 | 2 changed | quiet |
| 2026-10-27 | `remote/eu.nulegal/recht` | 2026-10-27T112040307666 -> 2026-10-27T210134811336 | 6 changed | quiet |
| 2026-10-27 | `remote/dev.rackrates/ledger` | 2026-10-26T153151864621 -> 2026-10-27T210135538423 | 2 changed | quiet |
| 2026-10-27 | `remote/com.moaibuy/moa` | 2026-10-27T112034654616 -> 2026-10-27T210135540412 | 3 changed | quiet |
| 2026-10-27 | `remote/io.github.scraping-api-plans/web-data-plan-finder` | 2026-10-27T123921303295 -> 2026-10-27T210136346977 | 3 changed | quiet |
| 2026-10-27 | `remote/io.github.mooshee/pressmark` | 2026-10-26T211456648793 -> 2026-10-27T210130712010 | 6 changed (every tool) | quiet |
| 2026-10-27 | `remote/io.github.canoydario847-cloud/privi-quantum` | 2026-10-27T054105653612 -> 2026-10-27T210130805600 | 9 added | quiet |
| 2026-10-27 | `remote/ai.thestrat/thestrat` | 2026-10-26T133208565036 -> 2026-10-27T210130316027 | 1 added | quiet |
| 2026-10-27 | `remote/dev.monowire/patchwire` | 2026-10-26T133141648427 -> 2026-10-27T210130655686 | 1 changed | quiet |
| 2026-10-27 | `remote/com.plainrouter/mcp` | 2026-10-27T123808304755 -> 2026-10-27T210130340027 | 1 changed | quiet |
| 2026-10-27 | `remote/io.pitchboom/pitchboom` | 2026-10-26T153144935600 -> 2026-10-27T210128780259 | 3 changed | quiet |
| 2026-10-27 | `remote/io.github.Civops-Platform/open-signals` | 2026-10-27T145820884795 -> 2026-10-27T210127632649 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.Toramo747/mycelix` | 2026-10-27T054048363161 -> 2026-10-27T210125703378 | 5 changed | quiet |
| 2026-10-27 | `remote/com.othermindset/campus` | 2026-10-26T133248933577 -> 2026-10-27T210124990957 | 2 changed | quiet |
| 2026-10-27 | `remote/me.miow/miow` | 2026-10-26T133412679149 -> 2026-10-27T210124534085 | 2 changed, 4 added | quiet |
| 2026-10-27 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-10-27T145814165293 -> 2026-10-27T210123789813 | 1 changed | quiet |
| 2026-10-27 | `remote/network.mercatura/mercatura` | 2026-10-27T054022972296 -> 2026-10-27T210123371498 | 2 changed, 7 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 35585 substantive, 19453 that changed only numbers (a catalogue counter ticking, a date), 683 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 30394 | 12161 | 18233 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 891 | 891 | 0 | 0 |
| `caseyjhand.com` | 238 | 238 | 0 | 0 |
| `sistaminuten.se` | 162 | 5 | 0 | 157 |
| `afbudsrejser.dk` | 161 | 5 | 0 | 156 |
| `akkilahdot.fi` | 161 | 5 | 0 | 156 |
| `restplass.no` | 161 | 5 | 0 | 156 |
| `socialloop.ai` | 155 | 155 | 0 | 0 |
| `remoshift.com` | 131 | 8 | 123 | 0 |
| `revmesh2074.workers.dev` | 129 | 116 | 13 | 0 |
| `fundinglandscape.com` | 124 | 79 | 45 | 0 |
| 6107 other operators | 20673 | 19576 | 1039 | 58 |
