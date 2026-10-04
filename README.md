# MCP server tool changes

Last change observed 2026-10-04T14:25:00+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 19746 hosted endpoints (read daily, and every four hours while they keep changing).

19404 changes to a tool definition: 696 npm releases (450 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 18708 readings of hosted servers that found their tools changed; 221 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-04 | `remote/io.github.JakubTrousil/agentsjunction` | 2026-10-04T124321519022 -> 2026-10-04T142502708762 | 4 changed, 3 added | quiet |
| 2026-10-04 | `remote/fi.akkilahdot/travel-search` | 2026-10-04T124234174015 -> 2026-10-04T142500245127 | 1 changed | quiet |
| 2026-10-04 | `remote/dev.workers.panda198271.tw-stock-themes/stock-themes` | 2026-10-03T121255585321 -> 2026-10-04T142500091790 | 2 added | quiet |
| 2026-10-04 | `remote/io.taifoon/coordination-layer` | 2026-10-04T124325382653 -> 2026-10-04T142458171530 | 1 added | quiet |
| 2026-10-04 | `remote/no.restplass/travel-search` | 2026-10-04T124320343852 -> 2026-10-04T142458273003 | 1 changed | quiet |
| 2026-10-04 | `remote/dk.afbudsrejser/travel-search` | 2026-10-04T124259958649 -> 2026-10-04T142455676119 | 1 changed | quiet |
| 2026-10-04 | `remote/ai.wem3/wem-price-compare` | 2026-10-03T232151043259 -> 2026-10-04T142454973957 | 11 changed (every tool) | quiet |
| 2026-10-04 | `remote/com.penguindriver/stock` | 2026-10-03T121441082649 -> 2026-10-04T142454518448 | 2 added | quiet |
| 2026-10-04 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-04T062335866971 -> 2026-10-04T142453606003 | 1 changed | quiet |
| 2026-10-04 | `remote/com.quintadb/mcp` | 2026-10-04T124136784752 -> 2026-10-04T142453713777 | 1 changed | quiet |
| 2026-10-04 | `remote/se.sistaminuten/travel-search` | 2026-10-04T124305840087 -> 2026-10-04T142452783442 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-10-04T062338601347 -> 2026-10-04T142450749057 | 15 changed | review |
| 2026-10-04 | `remote/io.github.Perufitlife/postwire-mcp` | 2026-10-04T124122639644 -> 2026-10-04T142451116668 | 8 changed, 1 added | review |
| 2026-10-04 | `remote/uk.co.gigstamp/gigstamp` | 2026-10-04T055153849286 -> 2026-10-04T142451278459 | 1 changed | quiet |
| 2026-10-04 | `remote/ua.com.quintadb/mcp` | 2026-10-04T124133991121 -> 2026-10-04T142449636250 | 1 changed | quiet |
| 2026-10-04 | `remote/ru.quintadb/mcp` | 2026-10-04T124112340845 -> 2026-10-04T142445850936 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.presendapp/presend-mcp` | 2026-10-03T054744884575 -> 2026-10-04T142443176818 | 1 changed | quiet |
| 2026-10-04 | `remote/com.predictionmarketspicks/quant` | 2026-10-04T055000355368 -> 2026-10-04T142444032798 | 1 changed | quiet |
| 2026-10-04 | `remote/com.hireahelper/mcp` | 2026-10-04T123845565936 -> 2026-10-04T142443333858 | 16 removed | quiet |
| 2026-10-04 | `remote/com.shotpulled/shotpulled` | 2026-10-03T121050765311 -> 2026-10-04T142442316865 | 5 changed | quiet |
| 2026-10-04 | `remote/com.narrowhighway/concordance` | 2026-10-03T054742691124 -> 2026-10-04T142441458298 | 1 changed | quiet |
| 2026-10-04 | `remote/pro.aicut/aicut` | 2026-10-03T192853678036 -> 2026-10-04T142439287873 | 51 changed, 3 added (every tool) | quiet |
| 2026-10-04 | `remote/cz.cenaodhad/cenaodhad` | 2026-10-04T123817897978 -> 2026-10-04T142442870744 | 8 changed (every tool) | quiet |
| 2026-10-04 | `remote/io.github.davisvillelabs/localproof` | 2026-10-02T071705769793 -> 2026-10-04T142438049046 | 7 changed | review |
| 2026-10-04 | `remote/io.github.Kopaev/openvan-travel` | 2026-10-02T071603171527 -> 2026-10-04T142439128555 | 3 changed | quiet |
| 2026-10-04 | `remote/com.subastech/subastas-judiciales` | 2026-10-02T182524220895 -> 2026-10-04T142439147349 | 32 changed (every tool) | quiet |
| 2026-10-04 | `remote/com.penguindriver/life` | 2026-10-03T121053529006 -> 2026-10-04T142437567380 | 4 added | quiet |
| 2026-10-04 | `remote/ai.greenlandai/greenlandai` | 2026-10-04T123931847164 -> 2026-10-04T142439349860 | 1 changed | quiet |
| 2026-10-04 | `remote/com.penguindriver/hub` | 2026-10-03T135707124982 -> 2026-10-04T142429424205 | 10 added | quiet |
| 2026-10-04 | `remote/dev.fastdrop/fastdrop` | 2026-10-02T182155234319 -> 2026-10-04T142427785933 | 4 added | quiet |
| 2026-10-04 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-04T123548924973 -> 2026-10-04T142426445678 | 3 changed | quiet |
| 2026-10-04 | `remote/io.github.arhancanli/canli-validation-mcp` | 2026-10-04T123457727570 -> 2026-10-04T142425386023 | 16 changed, 2 added (every tool) | quiet |
| 2026-10-04 | `remote/io.github.jamhimself/robinx-mcp` | 2026-10-02T181958942761 -> 2026-10-04T142424026018 | 24 changed | quiet |
| 2026-10-04 | `remote/exchange.ravn/ravn` | 2026-10-04T123431661211 -> 2026-10-04T142423327634 | 2 changed | quiet |
| 2026-10-04 | `remote/com.difficat/difficat` | 2026-10-04T123416053548 -> 2026-10-04T142421812865 | 10 changed, 2 added (every tool) | quiet |
| 2026-10-04 | `remote/io.tapeline/tapeline` | 2026-10-04T062321429169 -> 2026-10-04T142421595405 | 1 changed, 1 removed | quiet |
| 2026-10-04 | `remote/info.3dcms/mcp` | 2026-10-02T061600056607 -> 2026-10-04T142417912519 | 13 changed (every tool) | quiet |
| 2026-10-04 | `remote/com.aisenseapi/free-public-tools` | 2026-10-04T123148006038 -> 2026-10-04T142418902600 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.whiteknightonhorse/apibase` | 2026-10-04T123401562813 -> 2026-10-04T142416794183 | 5 added | quiet |
| 2026-10-04 | `remote/dev.workers.panda198271.agent-hub-tw/agent-hub` | 2026-10-03T135652751592 -> 2026-10-04T142416666021 | 10 added | quiet |
| 2026-10-04 | `remote/app.agentbit/mcp` | 2026-10-04T123134803498 -> 2026-10-04T142413483741 | 1 changed | quiet |
| 2026-10-04 | `remote/com.ifa-wisdom/library` | 2026-09-23T160843207938 -> 2026-10-04T124336226882 | 7 changed (every tool) | quiet |
| 2026-10-04 | `remote/io.taifoon/coordination-layer` | 2026-10-03T232153787028 -> 2026-10-04T124325382653 | 10 added | review |
| 2026-10-04 | `remote/io.github.JakubTrousil/agentsjunction` | 2026-10-03T121352489352 -> 2026-10-04T124321519022 | 2 added | quiet |
| 2026-10-04 | `remote/no.restplass/travel-search` | 2026-10-04T062343299823 -> 2026-10-04T124320343852 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.sajeetharan/devglobe` | 2026-09-23T163129707106 -> 2026-10-04T124307237698 | 1 changed | quiet |
| 2026-10-04 | `remote/se.sistaminuten/travel-search` | 2026-10-04T062403870230 -> 2026-10-04T124305840087 | 1 changed | quiet |
| 2026-10-04 | `remote/dk.afbudsrejser/travel-search` | 2026-10-04T062341021730 -> 2026-10-04T124259958649 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.ogasurfproject-jpg/horizon-shield-webmcp` | 2026-09-27T065956129605 -> 2026-10-04T124253085635 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.cyanheads/usgs-water-mcp-server` | 2026-09-25T120620161269 -> 2026-10-04T124245095092 | 2 changed | quiet |
| 2026-10-04 | `remote/com.thenewengineer/hvac` | 2026-10-02T210153062801 -> 2026-10-04T124242977538 | 1 changed | quiet |
| 2026-10-04 | `remote/cc.thecolony/mcp-server` | 2026-10-02T130502173782 -> 2026-10-04T124241329758 | 1 changed, 1 added | quiet |
| 2026-10-04 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-03T135735695755 -> 2026-10-04T124236773827 | 1 added | quiet |
| 2026-10-04 | `remote/fi.akkilahdot/travel-search` | 2026-10-04T062340183318 -> 2026-10-04T124234174015 | 1 changed | quiet |
| 2026-10-04 | `remote/io.github.thinksuitesolution-coder/visibilityai` | 2026-10-03T121515293933 -> 2026-10-04T124221114896 | 1 added | quiet |
| 2026-10-04 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-03T135739414202 -> 2026-10-04T124219132385 | 1 changed, 1 added | quiet |
| 2026-10-04 | `remote/com.shipshapedata/shipshape-data` | 2026-10-03T121201803922 -> 2026-10-04T124204790984 | 1 changed | quiet |
| 2026-10-04 | `remote/cn.savantcat/ai-compliance` | 2026-09-23T163105447435 -> 2026-10-04T124157083300 | 2 added | quiet |
| 2026-10-04 | `remote/cn.savantcat/geo-cn` | 2026-09-24T120340404939 -> 2026-10-04T124152746000 | 3 added | quiet |
| 2026-10-04 | `remote/io.github.kotinder/roomcomm` | 2026-10-01T212519104306 -> 2026-10-04T124144645585 | 11 changed (every tool) | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 14281 substantive, 4843 that changed only numbers (a catalogue counter ticking, a date), 280 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 10193 | 5683 | 4510 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `caseyjhand.com` | 72 | 72 | 0 | 0 |
| `sistaminuten.se` | 69 | 2 | 0 | 67 |
| `afbudsrejser.dk` | 68 | 2 | 0 | 66 |
| `akkilahdot.fi` | 68 | 2 | 0 | 66 |
| `restplass.no` | 68 | 2 | 0 | 66 |
| `socialloop.ai` | 66 | 66 | 0 | 0 |
| `dayze.com` | 63 | 63 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| 2102 other operators | 5824 | 5476 | 333 | 15 |
