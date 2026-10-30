# MCP server tool changes

Last change observed 2026-10-30T06:32:04+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

61946 changes to a tool definition: 2574 npm releases (2328 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 59372 readings of hosted servers that found their tools changed; 2993 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-30 | `remote/com.techfabric/techfabric` | 2026-10-28T062238617862 -> 2026-10-30T063206324627 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-10-29T212836115327 -> 2026-10-30T063203996540 | 2 changed | quiet |
| 2026-10-30 | `remote/io.github.brawlaphant/vealth` | 2026-10-29T212831604701 -> 2026-10-30T063201195806 | 3 changed | quiet |
| 2026-10-30 | `remote/se.sistaminuten/travel-search` | 2026-10-29T212918128991 -> 2026-10-30T063159575235 | 1 changed | quiet |
| 2026-10-30 | `remote/io.taifoon/coordination-layer.1` | 2026-10-29T212919034822 -> 2026-10-30T063200235181 | 1 changed | review |
| 2026-10-30 | `remote/com.menloinsurance/mcp` | 2026-10-29T104510777526 -> 2026-10-30T063159096531 | 6 changed | quiet |
| 2026-10-30 | `remote/cc.thecolony/mcp-server` | 2026-10-28T062221582238 -> 2026-10-30T063159748121 | 2 changed | quiet |
| 2026-10-30 | `remote/sg.tanatasa/tanatasa` | 2026-10-28T062218132739 -> 2026-10-30T063157720621 | 13 changed, 3 added (every tool) | review |
| 2026-10-30 | `remote/dev.tanod/images` | 2026-10-29T133334716847 -> 2026-10-30T063159430624 | 2 added | quiet |
| 2026-10-30 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-29T212827475153 -> 2026-10-30T063156058555 | 2 changed | quiet |
| 2026-10-30 | `remote/it.expatliving/data` | 2026-10-29T133853917413 -> 2026-10-30T063158019710 | 1 added | quiet |
| 2026-10-30 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-29T063223568786 -> 2026-10-30T063154062806 | 1 changed | quiet |
| 2026-10-30 | `remote/io.roxskin/hyrox` | 2026-10-29T212823031478 -> 2026-10-30T063153013288 | 1 changed | quiet |
| 2026-10-30 | `remote/com.probativegrowth/legal-marketing-data.5` | 2026-10-29T063220291521 -> 2026-10-30T063151596666 | 1 changed | quiet |
| 2026-10-30 | `remote/com.probativegrowth/legal-marketing-data.3` | 2026-10-29T063219836110 -> 2026-10-30T063151626864 | 1 changed | quiet |
| 2026-10-30 | `remote/ai.popdot/popdot-mcp` | 2026-10-28T153300438875 -> 2026-10-30T063150757141 | 5 changed | quiet |
| 2026-10-30 | `remote/no.restplass/travel-search` | 2026-10-29T212909735480 -> 2026-10-30T063149097364 | 1 changed | quiet |
| 2026-10-30 | `remote/com.negativeresistance/cure-protocol` | 2026-10-29T212817085422 -> 2026-10-30T063146960127 | 2 added | quiet |
| 2026-10-30 | `remote/com.meridiandispatch/travel-guides` | 2026-10-29T212906401188 -> 2026-10-30T063147920604 | 3 changed | quiet |
| 2026-10-30 | `remote/io.github.SKalinin909/tradingcalc` | 2026-10-29T212903655211 -> 2026-10-30T063145759429 | 1 changed | quiet |
| 2026-10-30 | `remote/com.xn--5kvtwv52d/jizhineng-mcp-gateway` | 2026-10-29T063235113600 -> 2026-10-30T063147829817 | 2 added | quiet |
| 2026-10-30 | `remote/io.github.alanwang100/jizhineng-mcp` | 2026-10-29T063215208033 -> 2026-10-30T063146808379 | 2 added | quiet |
| 2026-10-30 | `remote/com.xn--5kvtwv52d/jizhineng-mcp` | 2026-10-29T063214541081 -> 2026-10-30T063146224404 | 2 added | quiet |
| 2026-10-30 | `remote/com.thefomite/fomite` | 2026-10-29T153752275858 -> 2026-10-30T063144947515 | 1 changed | quiet |
| 2026-10-30 | `remote/studio.gradients/mcp` | 2026-10-29T212905022038 -> 2026-10-30T063143345509 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.warpfreight/warp-agent-mcp` | 2026-10-29T103933187463 -> 2026-10-30T063143093546 | 4 added | quiet |
| 2026-10-30 | `remote/io.github.SoapyRED/freightutils` | 2026-10-29T212905614919 -> 2026-10-30T063143507435 | 25 changed (every tool) | quiet |
| 2026-10-30 | `remote/dev.tanod/document-to-markdown` | 2026-10-29T104329614007 -> 2026-10-30T063143677304 | 1 changed | quiet |
| 2026-10-30 | `remote/dev.tanod/docs` | 2026-10-29T063217974285 -> 2026-10-30T063144462167 | 1 changed | quiet |
| 2026-10-30 | `remote/dev.tanod/agents` | 2026-10-29T133654671641 -> 2026-10-30T063144592367 | 2 added | quiet |
| 2026-10-30 | `remote/org.walkably/walkably` | 2026-10-28T212329868418 -> 2026-10-30T063142580754 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.valuein/mcp-sec-edgar` | 2026-10-29T212812118513 -> 2026-10-30T063142941533 | 2 changed | quiet |
| 2026-10-30 | `remote/dk.afbudsrejser/travel-search` | 2026-10-29T212901565037 -> 2026-10-30T063143827625 | 1 changed | quiet |
| 2026-10-30 | `remote/dev.tanod/tanod` | 2026-10-29T153751936716 -> 2026-10-30T063145935599 | 1 changed, 7 added | quiet |
| 2026-10-30 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-10-29T212903120756 -> 2026-10-30T063142530643 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-10-29T104500933117 -> 2026-10-30T063141098271 | 1 changed | quiet |
| 2026-10-30 | `remote/fi.akkilahdot/travel-search` | 2026-10-29T212903711720 -> 2026-10-30T063141708229 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.CodeWever/wever-labs-products` | 2026-10-29T212900937272 -> 2026-10-30T063140750648 | 6 added | quiet |
| 2026-10-30 | `remote/ru.vedarai/mcp` | 2026-10-29T212900548899 -> 2026-10-30T063141020608 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.Agentic-Private-Office/rco-a2a` | 2026-10-29T103852243973 -> 2026-10-30T063139346825 | 2 changed, 3 added (every tool) | quiet |
| 2026-10-30 | `remote/com.problee/problee` | 2026-10-28T062142835356 -> 2026-10-30T063139229230 | 1 added | quiet |
| 2026-10-30 | `remote/si.thinkhard/prompt-tools` | 2026-10-29T104402600253 -> 2026-10-30T063138619185 | 3 added | quiet |
| 2026-10-30 | `remote/io.github.yayabough/tolca` | 2026-10-28T133003892429 -> 2026-10-30T063138402554 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.martinPisacreta/textokit-mcp` | 2026-10-28T062152921804 -> 2026-10-30T063138377347 | 1 changed | review |
| 2026-10-30 | `remote/ca.tonbot.tolca/tolca` | 2026-10-28T133003281531 -> 2026-10-30T063138116192 | 3 changed | quiet |
| 2026-10-30 | `remote/ai.trydock/dock` | 2026-10-29T104456221100 -> 2026-10-30T063138030534 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.CYAN-ECLIPSE-TECHNOLOGIES-LLC/white-report` | 2026-10-28T212446598545 -> 2026-10-30T063138204063 | 12 changed (every tool) | quiet |
| 2026-10-30 | `remote/com.spocont/ifrCoworker` | 2026-10-29T132802596372 -> 2026-10-30T063138216593 | 3 changed | quiet |
| 2026-10-30 | `remote/com.jojapi/product-barcode-api` | 2026-10-29T063205370471 -> 2026-10-30T063137661919 | 2 changed | quiet |
| 2026-10-30 | `remote/fr.synergieloc/immobilier` | 2026-10-29T212848411964 -> 2026-10-30T063137951235 | 20 added | quiet |
| 2026-10-30 | `remote/com.textforagents/dark-pool-for-agent-work` | 2026-10-28T133249987637 -> 2026-10-30T063136215255 | 1 changed | quiet |
| 2026-10-30 | `remote/ai.dotsy/mcp` | 2026-10-29T063204105104 -> 2026-10-30T063136077532 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-29T212851571780 -> 2026-10-30T063134850247 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.ronrey/federation` | 2026-10-29T103718523709 -> 2026-10-30T063135097560 | 1 changed | quiet |
| 2026-10-30 | `remote/com.swarmmemo/bulletin.1` | 2026-10-29T212853719392 -> 2026-10-30T063136173736 | 13 changed | quiet |
| 2026-10-30 | `remote/com.swarmmemo/bulletin` | 2026-10-29T212853395871 -> 2026-10-30T063135889400 | 2 changed | quiet |
| 2026-10-30 | `remote/com.strongsaga/gear-lookup` | 2026-10-28T062149325298 -> 2026-10-30T063139834490 | 2 changed | quiet |
| 2026-10-30 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-29T153803612581 -> 2026-10-30T063135149082 | 3 changed | quiet |
| 2026-10-30 | `remote/com.comos-federation/gateway` | 2026-10-29T103718362132 -> 2026-10-30T063134798214 | 1 changed | quiet |
| 2026-10-30 | `remote/io.simplyprint/simplyprint` | 2026-10-29T104349428170 -> 2026-10-30T063134683029 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 41648 substantive, 19573 that changed only numbers (a catalogue counter ticking, a date), 725 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 34063 | 15829 | 18234 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1126 | 1126 | 0 | 0 |
| `caseyjhand.com` | 272 | 272 | 0 | 0 |
| `sistaminuten.se` | 172 | 6 | 0 | 166 |
| `afbudsrejser.dk` | 171 | 6 | 0 | 165 |
| `akkilahdot.fi` | 171 | 6 | 0 | 165 |
| `restplass.no` | 171 | 6 | 0 | 165 |
| `socialloop.ai` | 165 | 165 | 0 | 0 |
| `remoshift.com` | 141 | 10 | 131 | 0 |
| `fundinglandscape.com` | 131 | 83 | 48 | 0 |
| `revmesh2074.workers.dev` | 129 | 116 | 13 | 0 |
| 6459 other operators | 22893 | 21682 | 1147 | 64 |
