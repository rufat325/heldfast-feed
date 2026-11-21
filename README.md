# MCP server tool changes

Last change observed 2026-11-21T21:57:52+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

124125 changes to a tool definition: 4965 npm releases (4719 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 119160 readings of hosted servers that found their tools changed; 4629 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-21 | `remote/studio.gradients/mcp` | 2026-11-21T151140004619 -> 2026-11-21T215753467032 | 1 changed | quiet |
| 2026-11-21 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-21T151125361139 -> 2026-11-21T215752755912 | 1 changed | quiet |
| 2026-11-21 | `remote/fi.akkilahdot/travel-search` | 2026-11-21T151117493525 -> 2026-11-21T215751942601 | 1 changed | quiet |
| 2026-11-21 | `remote/com.weverlabs/agentic-rails` | 2026-11-21T130618437817 -> 2026-11-21T215757272056 | 8 added | quiet |
| 2026-11-21 | `remote/io.github.zikriz/wallet-doctor-x402` | 2026-11-21T151052440515 -> 2026-11-21T215749906457 | 3 changed | review |
| 2026-11-21 | `remote/io.github.christianscode1994/volatiai` | 2026-11-21T130611430329 -> 2026-11-21T215749698672 | 5 added | quiet |
| 2026-11-21 | `remote/ru.vedarai/mcp` | 2026-11-21T130613516340 -> 2026-11-21T215752053597 | 1 changed | quiet |
| 2026-11-21 | `remote/com.tamingdns/mcp` | 2026-11-21T150925108034 -> 2026-11-21T215745077485 | 3 changed | quiet |
| 2026-11-21 | `remote/com.stayotter/stay-otter` | 2026-11-19T020328870081 -> 2026-11-21T215743958711 | 1 changed | quiet |
| 2026-11-21 | `remote/io.github.pugarte7/spanish-top-tech-companies` | 2026-11-21T130605477922 -> 2026-11-21T215743053994 | 1 changed | quiet |
| 2026-11-21 | `remote/com.veridionmarkets/disclosures` | 2026-11-21T130649144079 -> 2026-11-21T215743463741 | 5 changed | quiet |
| 2026-11-21 | `remote/com.theagentcolosseum/agent-colosseum` | 2026-11-20T160036940032 -> 2026-11-21T215743989221 | 6 changed (every tool) | quiet |
| 2026-11-21 | `remote/com.achivx/stablescan` | 2026-11-20T160119940634 -> 2026-11-21T215743599024 | 1 changed | quiet |
| 2026-11-21 | `remote/xyz.tereno/tereno` | 2026-11-19T162307736004 -> 2026-11-21T215742299704 | 23 changed (every tool) | quiet |
| 2026-11-21 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-21T150843170995 -> 2026-11-21T215742080613 | 1 changed | quiet |
| 2026-11-21 | `remote/se.sistaminuten/travel-search` | 2026-11-21T151144039223 -> 2026-11-21T215741513699 | 1 changed | quiet |
| 2026-11-21 | `remote/io.github.Shicodiez/crypto-regime-mcp` | 2026-11-19T135841276159 -> 2026-11-21T215741656289 | 3 added | quiet |
| 2026-11-21 | `remote/org.omenz.www/agent-tools` | 2026-11-21T130646159334 -> 2026-11-21T215739176260 | 7 changed | quiet |
| 2026-11-21 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-11-19T123847093786 -> 2026-11-21T215750727819 | 18 changed, 1 added | quiet |
| 2026-11-21 | `remote/io.github.JcJamet/ia-qa-security` | 2026-11-19T123846937278 -> 2026-11-21T215750404162 | 2 changed | quiet |
| 2026-11-21 | `remote/com.remoshift/jobs` | 2026-11-21T150732134854 -> 2026-11-21T215736907723 | 1 changed | quiet |
| 2026-11-21 | `remote/com.rabbitimport/rabbit` | 2026-11-21T150721216218 -> 2026-11-21T215736736614 | 1 changed | quiet |
| 2026-11-21 | `remote/io.github.yschimke/compose-preview` | 2026-11-21T130601677558 -> 2026-11-21T215735311789 | 55 removed | quiet |
| 2026-11-21 | `remote/no.restplass/travel-search` | 2026-11-21T151119324752 -> 2026-11-21T215732268087 | 1 changed | quiet |
| 2026-11-21 | `remote/io.github.linxule/vellum` | 2026-11-19T123721799184 -> 2026-11-21T215733433892 | 6 changed (every tool) | quiet |
| 2026-11-21 | `remote/xyz.urbangametheory/urban-game-theory` | 2026-11-21T130641745421 -> 2026-11-21T215733666164 | 4 changed | quiet |
| 2026-11-21 | `remote/com.tryrankwise/rankwise` | 2026-11-20T105358049117 -> 2026-11-21T215730728556 | 3 changed | quiet |
| 2026-11-21 | `remote/com.juzpost/mcp` | 2026-11-21T130557378090 -> 2026-11-21T215731320105 | 3 changed | quiet |
| 2026-11-21 | `remote/dk.afbudsrejser/travel-search` | 2026-11-21T151027687659 -> 2026-11-21T215729474425 | 1 changed | quiet |
| 2026-11-21 | `remote/com.multicinesortega/cartelera` | 2026-11-21T130556642824 -> 2026-11-21T215727844997 | 1 changed | quiet |
| 2026-11-21 | `remote/no.momentsapp/events` | 2026-11-21T130555912552 -> 2026-11-21T215726736174 | 1 changed | quiet |
| 2026-11-21 | `remote/ai.trydock/dock` | 2026-11-21T014810030375 -> 2026-11-21T215725429133 | 2 changed | quiet |
| 2026-11-21 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-21T130554655035 -> 2026-11-21T215725859061 | 691 changed | quiet |
| 2026-11-21 | `remote/com.trackerhacker/mcp` | 2026-11-20T172212715965 -> 2026-11-21T215724440187 | 3 changed, 3 added | quiet |
| 2026-11-21 | `remote/com.trooprally/trooprally` | 2026-11-21T150438378171 -> 2026-11-21T215722650684 | 10 changed | quiet |
| 2026-11-21 | `remote/com.toiseai/toise` | 2026-11-21T150432910425 -> 2026-11-21T215723045567 | 8 changed | quiet |
| 2026-11-21 | `remote/io.github.roomi-fields/osc-bridge` | 2026-11-21T014914531971 -> 2026-11-21T215722436767 | 1 changed | quiet |
| 2026-11-21 | `remote/io.github.boriskendev/stormap` | 2026-11-20T105635690586 -> 2026-11-21T215721192406 | 1 changed | quiet |
| 2026-11-21 | `remote/com.luxurylodgingpm.stay/luxury-lodging` | 2026-11-19T123549628287 -> 2026-11-21T215721208748 | 1 changed | quiet |
| 2026-11-21 | `remote/com.stocklens/stocklens` | 2026-11-21T130550105671 -> 2026-11-21T215720841194 | 8 changed | quiet |
| 2026-11-21 | `remote/com.requstory/mcp` | 2026-11-21T150704193451 -> 2026-11-21T215721729000 | 1 changed | quiet |
| 2026-11-21 | `remote/dev.qrdx/qrdx` | 2026-11-20T104946019708 -> 2026-11-21T215720019911 | 1 changed | quiet |
| 2026-11-21 | `remote/app.qrcodecreator/qr-codes` | 2026-11-21T014758728926 -> 2026-11-21T215719740926 | 2 changed | quiet |
| 2026-11-21 | `remote/dev.zambo/zambo` | 2026-11-21T130621146037 -> 2026-11-21T215718190227 | 2 changed | quiet |
| 2026-11-21 | `remote/com.ortexo/mcp` | 2026-11-21T014911196525 -> 2026-11-21T215718415911 | 7 changed | quiet |
| 2026-11-21 | `remote/com.straelo/relay` | 2026-11-21T150656214779 -> 2026-11-21T215717293763 | 2 changed | quiet |
| 2026-11-21 | `remote/ai.ohmyfin/sanctions` | 2026-11-20T172108645940 -> 2026-11-21T215718325865 | 1 changed | quiet |
| 2026-11-21 | `remote/com.radarbg/radar-tools` | 2026-11-21T130547527764 -> 2026-11-21T215718279165 | 4 added | quiet |
| 2026-11-21 | `remote/com.qrcodedinosaur/qr-codes` | 2026-11-21T014803367789 -> 2026-11-21T215717247274 | 2 changed | quiet |
| 2026-11-21 | `remote/app.sallim/korea-realty` | 2026-11-21T150646450528 -> 2026-11-21T215718377674 | 2 changed | quiet |
| 2026-11-21 | `remote/ai.marketcode/marketcode` | 2026-11-20T104850653985 -> 2026-11-21T215718546326 | 7 changed | quiet |
| 2026-11-21 | `remote/dev.ioconnex/price-tracker-mcp` | 2026-11-21T150623424056 -> 2026-11-21T215714729728 | 1 changed | quiet |
| 2026-11-21 | `remote/io.outil/outil` | 2026-11-21T014756031634 -> 2026-11-21T215717224705 | 1 added | quiet |
| 2026-11-21 | `remote/io.github.richardsolomou/praetorium` | 2026-11-20T105430639662 -> 2026-11-21T215716559234 | 1 changed | quiet |
| 2026-11-21 | `remote/io.github.iPAYX-Technologies/mcp-fx-audit` | 2026-11-20T104828108553 -> 2026-11-21T215713733846 | 4 changed (every tool) | quiet |
| 2026-11-21 | `remote/io.github.Eno654/oxyo-mcp` | 2026-11-21T150545475908 -> 2026-11-21T215715132240 | 2 changed | quiet |
| 2026-11-21 | `remote/io.github.Anon2052/price-tracker-mcp` | 2026-11-21T150622718002 -> 2026-11-21T215714357546 | 1 changed | quiet |
| 2026-11-21 | `remote/com.kurodyne/catalog` | 2026-11-20T104840357356 -> 2026-11-21T215715041428 | 1 changed | quiet |
| 2026-11-21 | `remote/ai.overwing/mcp` | 2026-11-21T150543604596 -> 2026-11-21T215714317713 | 4 added | quiet |
| 2026-11-21 | `remote/io.github.orcalayer/orcalayer-mcp` | 2026-11-21T014759433542 -> 2026-11-21T215711612325 | 1 changed | review |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 81853 substantive, 41123 that changed only numbers (a catalogue counter ticking, a date), 1149 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 67416 | 29061 | 38355 | 0 |
| `a2awire.com` | 3571 | 3571 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 487 | 487 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 401 | 401 | 0 | 0 |
| `revmesh2074.workers.dev` | 360 | 306 | 54 | 0 |
| `sistaminuten.se` | 267 | 6 | 0 | 261 |
| `afbudsrejser.dk` | 266 | 6 | 0 | 260 |
| `akkilahdot.fi` | 266 | 6 | 0 | 260 |
| `restplass.no` | 266 | 6 | 0 | 260 |
| `socialloop.ai` | 257 | 257 | 0 | 0 |
| 10683 other operators | 47747 | 44925 | 2714 | 108 |
