# MCP server tool changes

Last change observed 2026-11-26T22:00:41+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 18238 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 43073 hosted endpoints (read daily, and every four hours while they keep changing).

142395 changes to a tool definition: 5525 npm releases (5279 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 136870 readings of hosted servers that found their tools changed; 5191 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-26 | `remote/se.sistaminuten/travel-search` | 2026-11-26T172934075994 -> 2026-11-26T220042895706 | 1 changed | quiet |
| 2026-11-26 | `remote/studio.gradients/mcp` | 2026-11-26T173059508613 -> 2026-11-26T220041872257 | 1 changed | quiet |
| 2026-11-26 | `remote/fi.akkilahdot/travel-search` | 2026-11-26T173030894181 -> 2026-11-26T220041594670 | 1 changed | quiet |
| 2026-11-26 | `remote/com.weverlabs/agentic-rails` | 2026-11-26T090025992480 -> 2026-11-26T220048392969 | 8 added | quiet |
| 2026-11-26 | `remote/tech.upto/up-to-tech` | 2026-11-26T004759586378 -> 2026-11-26T220036080519 | 2 changed | quiet |
| 2026-11-26 | `remote/com.tofubofu/ai-visibility` | 2026-11-26T172650521353 -> 2026-11-26T220033651211 | 1 changed | quiet |
| 2026-11-26 | `remote/com.swishrjobs/swishrjobs` | 2026-11-26T172618171468 -> 2026-11-26T220030577946 | 2 changed, 3 added | quiet |
| 2026-11-26 | `remote/ai.stimhaus/emma-for-agents` | 2026-11-24T170017300443 -> 2026-11-26T220031910300 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-26T172734242499 -> 2026-11-26T220027611368 | 1 changed | quiet |
| 2026-11-26 | `remote/com.idosgames/platform` | 2026-11-26T004523851207 -> 2026-11-26T220028045209 | 2 changed | quiet |
| 2026-11-26 | `remote/pl.podziemieanalityczne/dane` | 2026-11-26T134726727010 -> 2026-11-26T220025327960 | 3 changed | quiet |
| 2026-11-26 | `remote/no.restplass/travel-search` | 2026-11-26T173144222665 -> 2026-11-26T220025431275 | 1 changed | quiet |
| 2026-11-26 | `remote/com.caelaralabs/seo` | 2026-11-26T004521989999 -> 2026-11-26T220025556330 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.davidgringras/scrutica` | 2026-11-25T150323608746 -> 2026-11-26T220024658652 | 1 changed | quiet |
| 2026-11-26 | `remote/net.repleader/mcp` | 2026-11-26T004725412953 -> 2026-11-26T220023835414 | 5 changed | quiet |
| 2026-11-26 | `remote/com.roadcutco/roadcut` | 2026-11-26T135103215127 -> 2026-11-26T220023271726 | 1 changed | quiet |
| 2026-11-26 | `remote/dk.afbudsrejser/travel-search` | 2026-11-26T173045276426 -> 2026-11-26T220022508173 | 1 changed | quiet |
| 2026-11-26 | `remote/com.breadboardhub/circuits` | 2026-11-25T105944763619 -> 2026-11-26T220022601032 | 1 changed, 3 added | quiet |
| 2026-11-26 | `remote/pl.finwire/data` | 2026-11-26T172425404311 -> 2026-11-26T220022820891 | 20 changed | quiet |
| 2026-11-26 | `remote/com.vidreno/mcp` | 2026-11-26T173012998711 -> 2026-11-26T220020985484 | 8 changed | quiet |
| 2026-11-26 | `remote/com.rabbitimport/rabbit` | 2026-11-26T135041110747 -> 2026-11-26T220022769128 | 14 changed | quiet |
| 2026-11-26 | `remote/com.commlo/commute-network` | 2026-11-25T174539283810 -> 2026-11-26T220019878012 | 2 changed | quiet |
| 2026-11-26 | `remote/io.trylode/lode` | 2026-11-26T004440233370 -> 2026-11-26T220019575737 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.jimmybr-PDX/rugradar` | 2026-11-25T110446989557 -> 2026-11-26T220017561451 | 4 changed, 4 removed | quiet |
| 2026-11-26 | `remote/gg.pixly/mcp` | 2026-11-24T165716110740 -> 2026-11-26T220019424012 | 2 changed | quiet |
| 2026-11-26 | `remote/com.trackerhacker/mcp` | 2026-11-26T172929960608 -> 2026-11-26T220018425236 | 3 changed, 1 added | quiet |
| 2026-11-26 | `remote/com.ticketfairy/ticket-fairy-public-events` | 2026-11-26T085909552463 -> 2026-11-26T220016887374 | 11 changed | quiet |
| 2026-11-26 | `remote/com.paidhandshake/exchange` | 2026-11-26T004511828440 -> 2026-11-26T220017427526 | 1 added | quiet |
| 2026-11-26 | `remote/io.github.HuangGoodmanAgency/edgar-and-edgarette` | 2026-11-24T165552041502 -> 2026-11-26T220014090720 | 3 added | quiet |
| 2026-11-26 | `remote/co.civai.nova/mcp-firecrawl` | 2026-11-26T134938584867 -> 2026-11-26T220016077700 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-26T172859197460 -> 2026-11-26T220014235746 | 1 changed | quiet |
| 2026-11-26 | `remote/com.mystarletter/human-design-chart` | 2026-11-24T165548760388 -> 2026-11-26T220013863753 | 1 added | quiet |
| 2026-11-26 | `remote/com.multicinesortega/cartelera` | 2026-11-26T085903533252 -> 2026-11-26T220014843862 | 1 changed | quiet |
| 2026-11-26 | `remote/io.simplyprint/simplyprint` | 2026-11-25T174424846254 -> 2026-11-26T220011933490 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.Ipayx-stellar/fx-audit` | 2026-11-24T050422593327 -> 2026-11-26T220011801137 | 4 changed, 1 added (every tool) | quiet |
| 2026-11-26 | `remote/com.whizbrew/whizbrew` | 2026-11-26T134620939334 -> 2026-11-26T220011560026 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-26T085903938211 -> 2026-11-26T220008978628 | 1 changed, 3 added | quiet |
| 2026-11-26 | `remote/ai.rokha/rokha` | 2026-11-26T134338155451 -> 2026-11-26T220009047264 | 2 changed | review |
| 2026-11-26 | `remote/com.toiseai/toise` | 2026-11-26T172239692142 -> 2026-11-26T220007692164 | 1 added | quiet |
| 2026-11-26 | `remote/com.tapeperp/tape` | 2026-11-26T172634120689 -> 2026-11-26T220006562065 | 4 changed | quiet |
| 2026-11-26 | `remote/com.rivalsweeper/signals` | 2026-11-26T134743820813 -> 2026-11-26T220007650192 | 1 added | quiet |
| 2026-11-26 | `remote/gg.reliquary/reliquary` | 2026-11-25T174329147152 -> 2026-11-26T220006593785 | 4 added | quiet |
| 2026-11-26 | `remote/com.sulihuli/catalog` | 2026-11-26T004624745473 -> 2026-11-26T220006244124 | 4 changed, 2 added, 2 removed | quiet |
| 2026-11-26 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-11-26T172036927970 -> 2026-11-26T220004928615 | 1 changed | quiet |
| 2026-11-26 | `remote/com.radarbg/radar-tools` | 2026-11-26T172616994836 -> 2026-11-26T220007491640 | 2 added | quiet |
| 2026-11-26 | `remote/com.nomidmdm/nomid-mdm` | 2026-11-24T165209215219 -> 2026-11-26T220005375863 | 1 changed | quiet |
| 2026-11-26 | `remote/com.caelaralabs/social` | 2026-11-26T004623698500 -> 2026-11-26T220004017385 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.richardsolomou/praetorium` | 2026-11-26T134247215946 -> 2026-11-26T220003763222 | 8 changed | quiet |
| 2026-11-26 | `remote/io.kompare/search` | 2026-11-26T004504800494 -> 2026-11-26T220003398484 | 4 changed (every tool) | quiet |
| 2026-11-26 | `remote/io.github.cnghockey/sats4ai` | 2026-11-26T085859470311 -> 2026-11-26T220003500155 | 2 changed | quiet |
| 2026-11-26 | `remote/io.github.echopai/echopai-mcp` | 2026-11-26T134632031949 -> 2026-11-26T220005180434 | 6 changed | quiet |
| 2026-11-26 | `remote/io.github.adamgraymon/agent-finops-budget-spend-guard` | 2026-11-26T085857015869 -> 2026-11-26T215959532126 | 1 changed | review |
| 2026-11-26 | `remote/io.github.magichourhq/magic-hour` | 2026-11-26T004623027327 -> 2026-11-26T215959290388 | 32 changed | quiet |
| 2026-11-26 | `remote/com.kurodyne/catalog` | 2026-11-25T150246317643 -> 2026-11-26T215958202265 | 1 changed | quiet |
| 2026-11-26 | `remote/ai.codegene/codegene` | 2026-11-26T171856851349 -> 2026-11-26T215955818686 | 1 changed, 2 added | quiet |
| 2026-11-26 | `remote/io.github.iPAYX-Technologies/mcp-fx-audit` | 2026-11-24T050258873726 -> 2026-11-26T215955293563 | 4 changed, 1 added (every tool) | quiet |
| 2026-11-26 | `remote/com.caelaralabs/media` | 2026-11-26T004417282265 -> 2026-11-26T215955313532 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.farenberglord-star/orb-studio` | 2026-11-26T172307592165 -> 2026-11-26T215956572083 | 1 added | quiet |
| 2026-11-26 | `remote/pl.kiedysport/sport` | 2026-11-26T085851029708 -> 2026-11-26T215952324968 | 1 changed | quiet |
| 2026-11-26 | `remote/com.midasiteurope/civil-nx` | 2026-11-26T172207431260 -> 2026-11-26T215951974710 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 95930 substantive, 45228 that changed only numbers (a catalogue counter ticking, a date), 1237 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 78619 | 36545 | 42074 | 0 |
| `a2awire.com` | 3972 | 3972 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 546 | 546 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 403 | 403 | 0 | 0 |
| `revmesh2074.workers.dev` | 370 | 315 | 55 | 0 |
| `sistaminuten.se` | 288 | 7 | 0 | 281 |
| `afbudsrejser.dk` | 287 | 7 | 0 | 280 |
| `akkilahdot.fi` | 287 | 7 | 0 | 280 |
| `restplass.no` | 287 | 7 | 0 | 280 |
| `socialloop.ai` | 278 | 278 | 0 | 0 |
| 11677 other operators | 54237 | 51022 | 3099 | 116 |
