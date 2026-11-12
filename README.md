# MCP server tool changes

Last change observed 2026-11-12T15:54:02+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

94890 changes to a tool definition: 4016 npm releases (3770 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 90874 readings of hosted servers that found their tools changed; 3841 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-12 | `remote/io.github.yappmaniac/grocery-price-snapshots` | 2026-11-09T170411762508 -> 2026-11-12T155402864249 | 2 added | quiet |
| 2026-11-12 | `remote/com.yardstickoutfitters/mcp` | 2026-10-20T232825286825 -> 2026-11-12T155403106836 | 2 changed | quiet |
| 2026-11-12 | `remote/ai.revuo/revuo` | 2026-09-23T162952226211 -> 2026-11-12T155334117707 | 1 changed, 1 added | quiet |
| 2026-11-12 | `remote/fr.publicoffre/marches-publics` | 2026-11-02T163719661251 -> 2026-11-12T155330649448 | 1 changed | quiet |
| 2026-11-12 | `remote/io.github.everest-an/protocol-banks` | 2026-11-02T163225937211 -> 2026-11-12T155330311341 | 11 changed, 12 added (every tool) | quiet |
| 2026-11-12 | `remote/com.plyparts/ply` | 2026-11-08T135840254261 -> 2026-11-12T155327658631 | 6 changed | quiet |
| 2026-11-12 | `remote/com.patchmcp/patch` | 2026-11-09T191552340614 -> 2026-11-12T155326270466 | 8 changed, 5 removed | quiet |
| 2026-11-12 | `remote/design.overflow/mcp` | 2026-11-11T150132047214 -> 2026-11-12T155326655332 | 1 changed | quiet |
| 2026-11-12 | `remote/com.metaintro/job-search` | 2026-11-09T170328103645 -> 2026-11-12T155321241859 | 2 changed | quiet |
| 2026-11-12 | `remote/io.github.aanari/loacare-healthcare-pricing` | 2026-10-29T212907307698 -> 2026-11-12T155319018631 | 2 changed | quiet |
| 2026-11-12 | `remote/com.kaicalls/kaicalls.1` | 2026-11-08T135825667815 -> 2026-11-12T155316905942 | 2 changed | quiet |
| 2026-11-12 | `remote/studio.gradients/mcp` | 2026-11-12T074802514671 -> 2026-11-12T155305782058 | 1 changed | quiet |
| 2026-11-12 | `remote/com.evalgate/evalgate` | 2026-11-09T170259716115 -> 2026-11-12T155258852807 | 12 changed (every tool) | quiet |
| 2026-11-12 | `remote/fi.akkilahdot/travel-search` | 2026-11-12T074759664468 -> 2026-11-12T155240708470 | 1 changed | quiet |
| 2026-11-12 | `remote/com.whichmadvisor/site` | 2026-10-06T110340430145 -> 2026-11-12T155224874640 | 1 changed | quiet |
| 2026-11-12 | `remote/com.whichfieldsoftware/site` | 2026-10-06T110340472257 -> 2026-11-12T155223587527 | 1 changed | quiet |
| 2026-11-12 | `remote/io.github.seasonsagents-art/webaz` | 2026-11-12T074757144853 -> 2026-11-12T155208582628 | 1 changed | quiet |
| 2026-11-12 | `remote/com.wallchartbook/site` | 2026-09-23T162927225297 -> 2026-11-12T155204562416 | 2 changed | quiet |
| 2026-11-12 | `remote/io.github.SecondShotAI/verifylite` | 2026-11-02T163540010027 -> 2026-11-12T155153290690 | 1 changed | quiet |
| 2026-11-12 | `remote/ru.vedarai/mcp` | 2026-11-12T074758597597 -> 2026-11-12T155151858189 | 1 changed, 1 added | quiet |
| 2026-11-12 | `remote/app.vaultbags/vaultbags` | 2026-10-30T132942539934 -> 2026-11-12T155149641940 | 1 changed | quiet |
| 2026-11-12 | `remote/io.github.cyanheads/usaspending-mcp-server` | 2026-11-04T150440423493 -> 2026-11-12T155146816685 | 17 changed | quiet |
| 2026-11-12 | `remote/uk.co.underpinningcosts/site` | 2026-10-06T110323250521 -> 2026-11-12T155143716869 | 1 changed | quiet |
| 2026-11-12 | `remote/gg.unicum/wot-stats` | 2026-11-11T230921011736 -> 2026-11-12T155143053672 | 1 changed | quiet |
| 2026-11-12 | `remote/com.undassay/und-assay` | 2026-11-02T163529702546 -> 2026-11-12T155142163483 | 2 changed | quiet |
| 2026-11-12 | `remote/io.github.cyanheads/un-comtrade-mcp-server` | 2026-11-05T115428952591 -> 2026-11-12T155141598213 | 8 changed | quiet |
| 2026-11-12 | `remote/com.yearendo/site` | 2026-09-23T163153762646 -> 2026-11-12T155138091245 | 2 changed | quiet |
| 2026-11-12 | `remote/com.uibrik/components` | 2026-11-10T220129757916 -> 2026-11-12T155139625742 | 1 changed | quiet |
| 2026-11-12 | `remote/travel.trip720/trip720` | 2026-11-09T170135368664 -> 2026-11-12T155132168588 | 5 changed, 3 added, 3 removed (every tool) | quiet |
| 2026-11-12 | `remote/uk.co.transportstatementcost/site` | 2026-11-02T163520892031 -> 2026-11-12T155130104518 | 1 changed | quiet |
| 2026-11-12 | `remote/io.github.Schoasch/backtesting-arena` | 2026-10-30T210629844177 -> 2026-11-12T155128302990 | 4 changed | quiet |
| 2026-11-12 | `remote/ai.workonit/mcp` | 2026-11-05T222256478214 -> 2026-11-12T155129912154 | 1 changed | quiet |
| 2026-11-12 | `remote/me.wehome/stays` | 2026-11-02T163635363808 -> 2026-11-12T155126440976 | 1 changed | quiet |
| 2026-11-12 | `remote/com.yangopen/mcp` | 2026-10-31T130331579129 -> 2026-11-12T155119240663 | 1 changed, 1 added, 1 removed | quiet |
| 2026-11-12 | `remote/uk.co.tm44quote/site` | 2026-10-06T110305544663 -> 2026-11-12T155118898192 | 1 changed | quiet |
| 2026-11-12 | `remote/io.github.ysgjay/token-command-center` | 2026-11-06T144736506957 -> 2026-11-12T155118372190 | 1 changed | quiet |
| 2026-11-12 | `remote/com.xlifflane/site` | 2026-09-23T161042298429 -> 2026-11-12T155117644750 | 2 changed | quiet |
| 2026-11-12 | `remote/com.tieoutly/site` | 2026-09-23T162909692785 -> 2026-11-12T155114739510 | 2 changed | quiet |
| 2026-11-12 | `remote/com.tickmarko/site` | 2026-09-23T162909270219 -> 2026-11-12T155114381830 | 2 changed | quiet |
| 2026-11-12 | `remote/cloud.pandy/tickets` | 2026-11-02T163503370276 -> 2026-11-12T155112692586 | 4 changed (every tool) | quiet |
| 2026-11-12 | `remote/com.starcovery/mcp` | 2026-11-10T030035909713 -> 2026-11-12T155109260172 | 1 changed | review |
| 2026-11-12 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-11T230917024193 -> 2026-11-12T155108651999 | 2 changed | quiet |
| 2026-11-12 | `remote/no.restplass/travel-search` | 2026-11-12T074746698340 -> 2026-11-12T155103302182 | 1 changed | quiet |
| 2026-11-12 | `remote/com.texassolarcostcalculator/site` | 2026-10-06T110257430401 -> 2026-11-12T155102716323 | 1 changed | quiet |
| 2026-11-12 | `remote/com.praxikon/praxikon` | 2026-11-03T145047809401 -> 2026-11-12T155100796895 | 1 changed | quiet |
| 2026-11-12 | `remote/app.postel/postel` | 2026-11-05T222250714237 -> 2026-11-12T155059448102 | 3 changed | quiet |
| 2026-11-12 | `remote/com.thehappyhamper/laundry` | 2026-11-02T163445378237 -> 2026-11-12T155055272033 | 1 changed | quiet |
| 2026-11-12 | `remote/com.tamingdns/mcp` | 2026-11-11T230911765656 -> 2026-11-12T155051549403 | 1 added | quiet |
| 2026-11-12 | `remote/ai.makeviral/makeviral` | 2026-11-11T230928005761 -> 2026-11-12T155050796951 | 2 changed | quiet |
| 2026-11-12 | `remote/com.tachovo/site` | 2026-09-23T162904405352 -> 2026-11-12T155050976783 | 2 changed | quiet |
| 2026-11-12 | `remote/uk.co.tachocalibration/site` | 2026-10-06T110252039723 -> 2026-11-12T155050270237 | 1 changed | quiet |
| 2026-11-12 | `remote/com.swiftprobate/probate` | 2026-11-06T144828279878 -> 2026-11-12T155049305923 | 8 changed, 2 added | quiet |
| 2026-11-12 | `remote/com.kulicadvisory/aictionbot-werkbank` | 2026-11-05T115711391409 -> 2026-11-12T155047414844 | 1 changed, 20 added | quiet |
| 2026-11-12 | `remote/uk.swiftedge/orderflow` | 2026-11-09T170044139012 -> 2026-11-12T155045751528 | 2 changed, 1 added | quiet |
| 2026-11-12 | `remote/com.swellcabin/surf` | 2026-11-11T230910327267 -> 2026-11-12T155044946557 | 3 changed | quiet |
| 2026-11-12 | `remote/se.sistaminuten/travel-search` | 2026-11-12T074742951240 -> 2026-11-12T155044439003 | 1 changed | quiet |
| 2026-11-12 | `remote/app.ironledger/strength-calculators` | 2026-10-19T135842971091 -> 2026-11-12T155042191836 | 2 added | quiet |
| 2026-11-12 | `remote/io.github.nsudhanva/sudhanva-public-profile` | 2026-09-27T065955986154 -> 2026-11-12T155039445097 | 3 changed, 1 added (every tool) | quiet |
| 2026-11-12 | `remote/io.github.cryptosun/proximens-oracle` | 2026-11-11T230857784961 -> 2026-11-12T155038324517 | 5 changed | quiet |
| 2026-11-12 | `remote/uk.co.structuralreportcost/site` | 2026-10-06T110247068071 -> 2026-11-12T155037831376 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 58857 substantive, 35064 that changed only numbers (a catalogue counter ticking, a date), 969 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 50678 | 17757 | 32921 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 2242 | 2242 | 0 | 0 |
| `caseyjhand.com` | 402 | 402 | 0 | 0 |
| `civai.co` | 314 | 314 | 0 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `revmesh2074.workers.dev` | 239 | 209 | 30 | 0 |
| `sistaminuten.se` | 226 | 6 | 0 | 220 |
| `afbudsrejser.dk` | 225 | 6 | 0 | 219 |
| `akkilahdot.fi` | 225 | 6 | 0 | 219 |
| `restplass.no` | 225 | 6 | 0 | 219 |
| `socialloop.ai` | 217 | 217 | 0 | 0 |
| 9134 other operators | 37298 | 35093 | 2113 | 92 |
