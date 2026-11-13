# MCP server tool changes

Last change observed 2026-11-13T12:42:11+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

95984 changes to a tool definition: 4082 npm releases (3836 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 91902 readings of hosted servers that found their tools changed; 4017 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-13 | `remote/no.restplass/travel-search` | 2026-11-13T120006420817 -> 2026-11-13T124212585844 | 1 changed | quiet |
| 2026-11-13 | `remote/io.taifoon/coordination-layer.1` | 2026-11-13T120025355232 -> 2026-11-13T124216301396 | 1 changed | quiet |
| 2026-11-13 | `remote/se.sistaminuten/travel-search` | 2026-11-13T120017072847 -> 2026-11-13T124210647185 | 1 changed | quiet |
| 2026-11-13 | `remote/dk.afbudsrejser/travel-search` | 2026-11-13T115925818316 -> 2026-11-13T124208785382 | 1 changed | quiet |
| 2026-11-13 | `remote/io.escrova/escrova` | 2026-11-13T013220194288 -> 2026-11-13T124208295941 | 1 changed | quiet |
| 2026-11-13 | `remote/fi.akkilahdot/travel-search` | 2026-11-13T120541756270 -> 2026-11-13T124207518504 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-13T013229406026 -> 2026-11-13T124207643124 | 16 added | quiet |
| 2026-11-13 | `remote/ru.vedarai/mcp` | 2026-11-13T120502741156 -> 2026-11-13T124204803212 | 1 changed | quiet |
| 2026-11-13 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-13T120406439421 -> 2026-11-13T124200850656 | 2 changed | quiet |
| 2026-11-13 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-13T115735507763 -> 2026-11-13T124156354704 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.spree/ecommerce-docs` | 2026-11-12T154752061521 -> 2026-11-13T124154623379 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-13T120302881641 -> 2026-11-13T124154281958 | 1 changed | quiet |
| 2026-11-13 | `remote/com.remoshift/jobs` | 2026-11-13T120150857448 -> 2026-11-13T124144811794 | 1 changed | quiet |
| 2026-11-13 | `remote/ai.surfingdog/search` | 2026-11-12T074728442278 -> 2026-11-13T124140164310 | 6 changed | quiet |
| 2026-11-13 | `remote/com.newruntime/archive` | 2026-11-13T115956411885 -> 2026-11-13T124135655206 | 3 changed | quiet |
| 2026-11-13 | `remote/now.salesjobs/mcp` | 2026-11-13T115629767052 -> 2026-11-13T124133678023 | 1 changed | quiet |
| 2026-11-13 | `remote/dev.rackrates/ledger` | 2026-11-12T154510183917 -> 2026-11-13T124132244556 | 1 changed, 2 added | quiet |
| 2026-11-13 | `remote/com.ortexo/mcp` | 2026-11-13T013150464695 -> 2026-11-13T124126546136 | 1 changed | quiet |
| 2026-11-13 | `remote/co.lovie/company-formation` | 2026-11-11T145135793022 -> 2026-11-13T124124050626 | 7 changed | quiet |
| 2026-11-13 | `remote/so.darwin/darwin` | 2026-11-12T154200019672 -> 2026-11-13T124219024822 | 2 changed | quiet |
| 2026-11-13 | `remote/com.apptiller/apptiller` | 2026-11-11T164048411560 -> 2026-11-13T124117021549 | 1 added | quiet |
| 2026-11-13 | `remote/com.tkawen/intelligence-gateway` | 2026-11-13T115325448882 -> 2026-11-13T124115050145 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.bitcoinresearchkit/bitview` | 2026-11-11T145012307371 -> 2026-11-13T124113538969 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.Dahliyaal/justicelibre` | 2026-11-13T115018498338 -> 2026-11-13T124109385322 | 3 changed | quiet |
| 2026-11-13 | `remote/kr.co.knockwatch/coin-check` | 2026-11-11T071314969919 -> 2026-11-13T124100989863 | 5 changed (every tool) | quiet |
| 2026-11-13 | `remote/app.vercel.fork-for-agents/fork` | 2026-11-13T115111059470 -> 2026-11-13T124057438746 | 1 changed | quiet |
| 2026-11-13 | `remote/social.flayr/flayr` | 2026-11-13T114743333621 -> 2026-11-13T124054716073 | 17 changed | quiet |
| 2026-11-13 | `remote/com.coordinalo/mcp-server` | 2026-11-11T144152604284 -> 2026-11-13T124044934770 | 1 changed | quiet |
| 2026-11-13 | `remote/dev.taifoon.coord/text-digest-1170141` | 2026-11-13T114621490517 -> 2026-11-13T124050687057 | 1 changed | quiet |
| 2026-11-13 | `remote/com.cultmath/decision-briefs` | 2026-11-13T013112665950 -> 2026-11-13T124039595329 | 20 changed, 6 added | quiet |
| 2026-11-13 | `remote/com.awesomeindie/mcp` | 2026-11-11T144021174978 -> 2026-11-13T124036439827 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.herve-coulon/tax-retirement` | 2026-11-13T114441726031 -> 2026-11-13T124033795897 | 2 changed | quiet |
| 2026-11-13 | `remote/com.calcbright/calcbright` | 2026-11-13T114500011888 -> 2026-11-13T124030819180 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.0xinsider/mcp` | 2026-11-13T114010697841 -> 2026-11-13T124024093538 | 1 changed | quiet |
| 2026-11-13 | `remote/jp.cloneai.ai/agent-hub` | 2026-11-13T113945159940 -> 2026-11-13T124025322151 | 2 changed | quiet |
| 2026-11-13 | `remote/com.agenticfinancegraph/agentic-finance-graph` | 2026-11-13T113941387129 -> 2026-11-13T124023641364 | 1 added | quiet |
| 2026-11-13 | `remote/com.hashn/hashn` | 2026-11-12T170734366092 -> 2026-11-13T124019229502 | 2 changed, 2 added | quiet |
| 2026-11-13 | `remote/io.github.agentstacktech/agentstack` | 2026-11-11T071213077597 -> 2026-11-13T124018435174 | 1 changed | quiet |
| 2026-11-13 | `remote/com.chaink9/chaink9` | 2026-11-12T152717127580 -> 2026-11-13T124016026993 | 14 changed | quiet |
| 2026-11-13 | `remote/com.zinvyl/marketplace` | 2026-11-02T163801369002 -> 2026-11-13T120658809472 | 13 changed | quiet |
| 2026-11-13 | `remote/ai.zairalabs/guide` | 2026-11-07T133749588955 -> 2026-11-13T120655719384 | 2 changed | quiet |
| 2026-11-13 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/sanctions-kyb-compliance` | 2026-11-09T170404856287 -> 2026-11-13T120644711663 | 11 changed (every tool) | quiet |
| 2026-11-13 | `remote/com.plyparts/ply` | 2026-11-12T155327658631 -> 2026-11-13T120623595628 | 5 changed | quiet |
| 2026-11-13 | `remote/com.peptul/peptul` | 2026-09-23T162949718956 -> 2026-11-13T120623470273 | 1 changed | quiet |
| 2026-11-13 | `remote/design.overflow/mcp` | 2026-11-12T155326655332 -> 2026-11-13T120622670353 | 1 changed | quiet |
| 2026-11-13 | `remote/com.hemmabo/hemmabo-mcp-server` | 2026-10-17T055940740461 -> 2026-11-13T120606432938 | 1 changed | quiet |
| 2026-11-13 | `remote/studio.gradients/mcp` | 2026-11-13T013230115281 -> 2026-11-13T120605996984 | 1 changed | quiet |
| 2026-11-13 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-13T013229015356 -> 2026-11-13T120549220791 | 2 changed, 1 added | quiet |
| 2026-11-13 | `remote/fi.akkilahdot/travel-search` | 2026-11-13T013228902691 -> 2026-11-13T120541756270 | 1 changed | quiet |
| 2026-11-13 | `remote/com.webmcp-tool/agent-readiness` | 2026-10-01T134558470518 -> 2026-11-13T120522642282 | 2 changed | quiet |
| 2026-11-13 | `remote/io.github.WattCoin-Org/wattcoin-mcp-server` | 2026-11-03T144925655873 -> 2026-11-13T120518737463 | 1 changed | quiet |
| 2026-11-13 | `remote/com.vuntum/mcp` | 2026-11-11T071402383803 -> 2026-11-13T120516327282 | 1 removed | quiet |
| 2026-11-13 | `remote/direct.vote/vote-direct` | 2026-10-19T212008526967 -> 2026-11-13T120514027935 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.suanrongbaicai/vibecodepicks` | 2026-11-06T214831609433 -> 2026-11-13T120507050391 | 4 changed, 14 added | quiet |
| 2026-11-13 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-13T013227891955 -> 2026-11-13T120506687732 | 3 changed | quiet |
| 2026-11-13 | `remote/ru.vedarai/mcp` | 2026-11-13T013227585137 -> 2026-11-13T120502741156 | 2 changed | quiet |
| 2026-11-13 | `remote/pl.topaimuza/ranking` | 2026-10-26T133415165735 -> 2026-11-13T120425436210 | 1 changed | quiet |
| 2026-11-13 | `remote/com.ticketsea/ticketsea` | 2026-10-24T050524193501 -> 2026-11-13T120410906503 | 3 changed | quiet |
| 2026-11-13 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-13T013223601551 -> 2026-11-13T120406439421 | 2 changed | quiet |
| 2026-11-13 | `remote/com.tamingdns/mcp` | 2026-11-12T155051549403 -> 2026-11-13T120345422205 | 19 changed (every tool) | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 59874 substantive, 35123 that changed only numbers (a catalogue counter ticking, a date), 987 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 50678 | 17757 | 32921 | 0 |
| `a2awire.com` | 2375 | 2375 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 402 | 402 | 0 | 0 |
| `civai.co` | 317 | 317 | 0 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `revmesh2074.workers.dev` | 239 | 209 | 30 | 0 |
| `sistaminuten.se` | 230 | 6 | 0 | 224 |
| `afbudsrejser.dk` | 229 | 6 | 0 | 223 |
| `akkilahdot.fi` | 229 | 6 | 0 | 223 |
| `restplass.no` | 229 | 6 | 0 | 223 |
| `socialloop.ai` | 221 | 221 | 0 | 0 |
| 9248 other operators | 38236 | 35970 | 2172 | 94 |
