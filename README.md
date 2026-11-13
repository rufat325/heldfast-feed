# MCP server tool changes

Last change observed 2026-11-13T12:06:57+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

95945 changes to a tool definition: 4082 npm releases (3836 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 91863 readings of hosted servers that found their tools changed; 4017 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-13 | `remote/network.lucie/sync` | 2026-11-13T013221279845 -> 2026-11-13T120343165904 | 2 changed | quiet |
| 2026-11-13 | `remote/com.swellcabin/surf` | 2026-11-12T155044946557 -> 2026-11-13T120339131812 | 6 changed, 1 added | quiet |
| 2026-11-13 | `remote/eu.gridgarden/studio` | 2026-10-30T132851579404 -> 2026-11-13T120331776733 | 1 changed | quiet |
| 2026-11-13 | `remote/ai.stimhaus/emma-for-agents` | 2026-10-17T055819509216 -> 2026-11-13T120345579444 | 2 added | quiet |
| 2026-11-13 | `remote/com.stayotter/stay-otter` | 2026-11-06T144657532331 -> 2026-11-13T120322171045 | 1 changed | quiet |
| 2026-11-13 | `remote/com.softwiro/templates` | 2026-11-09T170016140090 -> 2026-11-13T120304437208 | 2 added | review |
| 2026-11-13 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-13T013217711373 -> 2026-11-13T120302881641 | 1 changed | quiet |
| 2026-11-13 | `remote/com.i2dev/snap` | 2026-10-31T202104577292 -> 2026-11-13T120300785755 | 1 changed | quiet |
| 2026-11-13 | `remote/com.innergcomplete/shearquery` | 2026-10-19T211936187236 -> 2026-11-13T120241211617 | 1 changed, 6 added | review |
| 2026-11-13 | `remote/dev.sharenotes/notes` | 2026-11-07T133434020911 -> 2026-11-13T120240509501 | 1 changed | quiet |
| 2026-11-13 | `remote/com.serviche/sergio` | 2026-11-11T230903207177 -> 2026-11-13T120236593453 | 1 changed, 1 added | quiet |
| 2026-11-13 | `remote/com.seqbench/workbench` | 2026-11-12T154915820526 -> 2026-11-13T120231250645 | 5 changed | quiet |
| 2026-11-13 | `remote/uk.co.seoarchitecturefirm/site` | 2026-11-11T145810310139 -> 2026-11-13T120229594383 | 2 changed | quiet |
| 2026-11-13 | `remote/io.github.bnth09productions-maker/scrapling-x402-store` | 2026-11-13T013212385000 -> 2026-11-13T120217461516 | 11 added | quiet |
| 2026-11-13 | `remote/org.room-ly/roomly` | 2026-11-12T154838194262 -> 2026-11-13T120201203984 | 1 changed | review |
| 2026-11-13 | `remote/com.remoshift/jobs` | 2026-11-05T010645539094 -> 2026-11-13T120150857448 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.scraping-api-plans/web-data-plan-finder` | 2026-11-13T013207144708 -> 2026-11-13T120105496911 | 9 changed | quiet |
| 2026-11-13 | `remote/com.aiw3b.planlimits/plan-fit` | 2026-11-02T163157950140 -> 2026-11-13T120102811333 | 1 changed | quiet |
| 2026-11-13 | `remote/uk.co.petcareatlas/atlas` | 2026-11-06T144455622016 -> 2026-11-13T120054973254 | 1 changed | quiet |
| 2026-11-13 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-service-search` | 2026-11-09T170437163659 -> 2026-11-13T120040200122 | 4 changed | quiet |
| 2026-11-13 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/evm-wallet-onchain` | 2026-11-09T170436884868 -> 2026-11-13T120040347513 | 12 changed (every tool) | quiet |
| 2026-11-13 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/cve-package-domain-security` | 2026-11-09T170436410928 -> 2026-11-13T120040235180 | 9 changed (every tool) | quiet |
| 2026-11-13 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/email-uptime-web-reader` | 2026-11-09T170317568967 -> 2026-11-13T120034265634 | 5 changed (every tool) | quiet |
| 2026-11-13 | `remote/dev.workers.moneytools.x402-pay-precheck/pay-precheck` | 2026-11-13T013223470963 -> 2026-11-13T120030198224 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.Fizzl13/x402-doctor` | 2026-11-13T013223124259 -> 2026-11-13T120029284112 | 1 changed | quiet |
| 2026-11-13 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/sec-filings-tenders` | 2026-11-09T170224649190 -> 2026-11-13T120028379281 | 3 changed (every tool) | quiet |
| 2026-11-13 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/fx-rates-news-weather-data` | 2026-11-09T170223508854 -> 2026-11-13T120028665710 | 8 changed (every tool) | quiet |
| 2026-11-13 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/agent-memory-utils` | 2026-11-09T170222235914 -> 2026-11-13T120028527745 | 8 changed | quiet |
| 2026-11-13 | `remote/io.vascue/public-knowledge-search` | 2026-10-27T112600044966 -> 2026-11-13T120027076878 | 1 changed | quiet |
| 2026-11-13 | `remote/xyz.tereno/tereno` | 2026-11-09T170305643335 -> 2026-11-13T120022877965 | 2 added | quiet |
| 2026-11-13 | `remote/com.vedutum/vedutum` | 2026-11-12T155005268187 -> 2026-11-13T120026146347 | 1 changed | quiet |
| 2026-11-13 | `remote/codes.onv/onv-mcp` | 2026-11-09T165748932134 -> 2026-11-13T120024787909 | 3 changed, 4 added | quiet |
| 2026-11-13 | `remote/io.taifoon/coordination-layer.1` | 2026-11-13T013227941011 -> 2026-11-13T120025355232 | 1 changed | quiet |
| 2026-11-13 | `remote/com.theaimeters/theaimeters` | 2026-10-17T060501895590 -> 2026-11-13T120019505331 | 1 added | quiet |
| 2026-11-13 | `remote/se.sistaminuten/travel-search` | 2026-11-13T013221516391 -> 2026-11-13T120017072847 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.homeaccount7/signaldock` | 2026-11-13T013223488634 -> 2026-11-13T120014655678 | 9 changed | quiet |
| 2026-11-13 | `remote/com.reqosupply/quote` | 2026-09-23T161034566720 -> 2026-11-13T120013652336 | 4 changed | quiet |
| 2026-11-13 | `remote/com.obriym-crm/mcp` | 2026-11-13T013157640604 -> 2026-11-13T120013491059 | 5 changed, 1 added | quiet |
| 2026-11-13 | `remote/ai.postquick.www/postquickai` | 2026-11-02T163430268448 -> 2026-11-13T120008673773 | 2 changed, 1 removed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 59845 substantive, 35117 that changed only numbers (a catalogue counter ticking, a date), 983 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 50678 | 17757 | 32921 | 0 |
| `a2awire.com` | 2375 | 2375 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 402 | 402 | 0 | 0 |
| `civai.co` | 317 | 317 | 0 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `revmesh2074.workers.dev` | 239 | 209 | 30 | 0 |
| `sistaminuten.se` | 229 | 6 | 0 | 223 |
| `afbudsrejser.dk` | 228 | 6 | 0 | 222 |
| `akkilahdot.fi` | 228 | 6 | 0 | 222 |
| `restplass.no` | 228 | 6 | 0 | 222 |
| `socialloop.ai` | 220 | 220 | 0 | 0 |
| 9247 other operators | 38202 | 35942 | 2166 | 94 |
