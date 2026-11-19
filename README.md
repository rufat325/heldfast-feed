# MCP server tool changes

Last change observed 2026-11-19T02:04:52+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

114628 changes to a tool definition: 4625 npm releases (4379 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 110003 readings of hosted servers that found their tools changed; 4401 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-19 | `remote/io.github.liad142/yedapo` | 2026-11-18T080231528894 -> 2026-11-19T020453830084 | 2 changed (every tool) | quiet |
| 2026-11-19 | `remote/no.restplass/travel-search` | 2026-11-18T174125494879 -> 2026-11-19T020451372171 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.openaccountants/openaccountants` | 2026-11-18T161839592743 -> 2026-11-19T020451699871 | 1 changed | quiet |
| 2026-11-19 | `remote/com.kulicadvisory/aictionbot-werkbank` | 2026-11-18T135808531255 -> 2026-11-19T020449871681 | 98 changed | quiet |
| 2026-11-19 | `remote/dk.afbudsrejser/travel-search` | 2026-11-18T174115543642 -> 2026-11-19T020444385278 | 1 changed | quiet |
| 2026-11-19 | `remote/com.25karats/storefront` | 2026-11-18T135720172434 -> 2026-11-19T020443732819 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.Voopa-Corp/render-check` | 2026-11-18T161658548447 -> 2026-11-19T020443078684 | 2 added | quiet |
| 2026-11-19 | `remote/fun.trnch/trnch-elysium` | 2026-11-17T135700339037 -> 2026-11-19T020441779106 | 3 changed, 2 added | quiet |
| 2026-11-19 | `remote/fun.trnch/trnch` | 2026-11-18T135614716416 -> 2026-11-19T020440986720 | 4 changed, 2 added | quiet |
| 2026-11-19 | `remote/ai.trydock/dock` | 2026-11-18T080211650462 -> 2026-11-19T020441350864 | 5 changed, 1 added | review |
| 2026-11-19 | `remote/com.tradeassi/mcp` | 2026-11-18T135608890373 -> 2026-11-19T020440074767 | 2 changed | quiet |
| 2026-11-19 | `remote/fyi.toothache/dentists` | 2026-11-18T174107741373 -> 2026-11-19T020440547454 | 1 changed | quiet |
| 2026-11-19 | `remote/dev.zambo/zambo` | 2026-11-18T135948004260 -> 2026-11-19T020438570836 | 1 changed | quiet |
| 2026-11-19 | `remote/com.youspot/youspot` | 2026-11-17T234400337032 -> 2026-11-19T020438917463 | 5 changed | quiet |
| 2026-11-19 | `remote/io.github.blink1217/quant-swarm.2` | 2026-11-18T135511664001 -> 2026-11-19T020436054504 | 4 changed | quiet |
| 2026-11-19 | `remote/at.space-core/game` | 2026-11-18T174057375086 -> 2026-11-19T020436654251 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-18T080204149916 -> 2026-11-19T020435977746 | 2 changed | quiet |
| 2026-11-19 | `remote/io.github.Friezaaaa/smartfetch` | 2026-11-18T174055494614 -> 2026-11-19T020435469161 | 12 changed (every tool) | quiet |
| 2026-11-19 | `remote/com.mikefluff/mikefluff` | 2026-11-18T135822615440 -> 2026-11-19T020435216307 | 5 added | quiet |
| 2026-11-19 | `remote/com.aguasto.www/tools` | 2026-11-18T161722295035 -> 2026-11-19T020433310137 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.wwwnlab/rest-area` | 2026-11-17T164431389985 -> 2026-11-19T020432477284 | 1 changed | quiet |
| 2026-11-19 | `remote/gg.reliquary/reliquary` | 2026-11-18T161240319715 -> 2026-11-19T020432726553 | 1 changed | quiet |
| 2026-11-19 | `remote/com.radarbg/radar-tools` | 2026-11-18T135254476598 -> 2026-11-19T020432187957 | 1 added | quiet |
| 2026-11-19 | `remote/com.qrcodedinosaur/qr-codes` | 2026-11-18T080151498871 -> 2026-11-19T020433614582 | 3 changed | quiet |
| 2026-11-19 | `remote/io.github.Playpowerpolitics/powerplayers` | 2026-11-18T080148257016 -> 2026-11-19T020428276843 | 1 changed | quiet |
| 2026-11-19 | `remote/dev.magmite/pay` | 2026-11-18T174038172619 -> 2026-11-19T020427857416 | 1 added | quiet |
| 2026-11-19 | `remote/io.github.fredxhansson-cmyk/noniner` | 2026-11-18T135108406620 -> 2026-11-19T020424812444 | 19 changed, 77 added, 1 removed (every tool) | quiet |
| 2026-11-19 | `remote/uk.co.mygrocerypal/grocery-prices` | 2026-11-18T080139269414 -> 2026-11-19T020423757710 | 3 changed | quiet |
| 2026-11-19 | `remote/com.usvipublicrecords/newspapers` | 2026-11-18T135100529913 -> 2026-11-19T020424415984 | 2 changed | quiet |
| 2026-11-19 | `remote/io.github.blink1217/quant-swarm` | 2026-11-18T161502010290 -> 2026-11-19T020420923353 | 1 changed | quiet |
| 2026-11-19 | `remote/biz.valuein/mcp` | 2026-11-18T174020838267 -> 2026-11-19T020420370454 | 34 changed | quiet |
| 2026-11-19 | `remote/app.sunsetstrip/gta6` | 2026-11-18T135513900046 -> 2026-11-19T020420192280 | 1 changed, 2 added | review |
| 2026-11-19 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-11-17T135636832131 -> 2026-11-19T020419031247 | 3 changed | quiet |
| 2026-11-19 | `remote/app.tourpro/mcp` | 2026-11-17T164048499728 -> 2026-11-19T020418920620 | 4 changed | quiet |
| 2026-11-19 | `remote/nl.theseo/theseo-mcp` | 2026-11-17T234251241994 -> 2026-11-19T020418724529 | 1 changed | quiet |
| 2026-11-19 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-11-18T080134777910 -> 2026-11-19T020417219547 | 1 changed | quiet |
| 2026-11-19 | `remote/now.salesjobs/mcp` | 2026-11-18T135356599313 -> 2026-11-19T020417072386 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.smarterweather/weather` | 2026-11-18T080128342677 -> 2026-11-19T020416513653 | 1 changed | quiet |
| 2026-11-19 | `remote/dev.sec-api/server` | 2026-11-17T164405656022 -> 2026-11-19T020416586041 | 1 changed | quiet |
| 2026-11-19 | `remote/ai.signal8/mcp` | 2026-11-18T134921278139 -> 2026-11-19T020417147115 | 2 changed | quiet |
| 2026-11-19 | `remote/ai.sendraven/mcp` | 2026-11-17T234248514111 -> 2026-11-19T020416393559 | 2 changed | quiet |
| 2026-11-19 | `remote/net.pendingdelete/mcp` | 2026-11-18T080126638296 -> 2026-11-19T020423974598 | 1 changed | quiet |
| 2026-11-19 | `remote/io.lexlint/lexlint` | 2026-11-17T031516195301 -> 2026-11-19T020411871923 | 2 changed | quiet |
| 2026-11-19 | `remote/com.provyan/provyan` | 2026-11-17T135626052000 -> 2026-11-19T020411049253 | 4 added | quiet |
| 2026-11-19 | `remote/com.housingcomps/compbasis` | 2026-11-18T134754331492 -> 2026-11-19T020410716184 | 2 changed, 1 added | quiet |
| 2026-11-19 | `remote/co.lovie/company-formation` | 2026-11-18T160651093154 -> 2026-11-19T020411097156 | 5 changed, 5 added | quiet |
| 2026-11-19 | `remote/io.github.farenberglord-star/orb-studio` | 2026-11-18T161116946918 -> 2026-11-19T020408372353 | 2 added | quiet |
| 2026-11-19 | `remote/io.dropyour/dropyour` | 2026-11-18T160542805148 -> 2026-11-19T020408784662 | 4 changed | quiet |
| 2026-11-19 | `remote/com.othermindset/campus` | 2026-11-18T173934142665 -> 2026-11-19T020407641730 | 2 changed | quiet |
| 2026-11-19 | `remote/com.notematics/notematics` | 2026-11-17T164145081092 -> 2026-11-19T020407052904 | 3 changed | quiet |
| 2026-11-19 | `remote/co.deadbrands/arena` | 2026-11-18T173959880188 -> 2026-11-19T020407082147 | 2 changed | quiet |
| 2026-11-19 | `remote/md.mostlyright/datasets` | 2026-11-18T173926412711 -> 2026-11-19T020405004871 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.Red-Center-Studio/nocode-migrator` | 2026-11-17T135613405906 -> 2026-11-19T020405444077 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.AnthonyPuggs/ausecon-mcp-server` | 2026-11-18T134648733696 -> 2026-11-19T020404422727 | 7 changed | quiet |
| 2026-11-19 | `remote/ai.certscore/mcp-light` | 2026-11-18T134702395650 -> 2026-11-19T020405781345 | 3 changed | quiet |
| 2026-11-19 | `remote/tools.datapad/math-board` | 2026-11-17T163627940953 -> 2026-11-19T020403072900 | 3 changed | quiet |
| 2026-11-19 | `remote/pe.vira.mcp/peru-data` | 2026-11-17T164016914915 -> 2026-11-19T020401575343 | 15 changed (every tool) | quiet |
| 2026-11-19 | `remote/io.taifoon/coordination-layer.1` | 2026-11-18T135936856276 -> 2026-11-19T020401569959 | 1 changed | review |
| 2026-11-19 | `remote/io.github.Wei-LienWU/pit-fundamentals` | 2026-11-17T164928136426 -> 2026-11-19T020400797894 | 1 changed | quiet |
| 2026-11-19 | `remote/hk.liki/liki` | 2026-11-17T031514310416 -> 2026-11-19T020400495112 | 6 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 72595 substantive, 40939 that changed only numbers (a catalogue counter ticking, a date), 1094 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 61815 | 23462 | 38353 | 0 |
| `a2awire.com` | 3240 | 3240 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 471 | 471 | 0 | 0 |
| `civai.co` | 368 | 368 | 0 | 0 |
| `modevc.com` | 349 | 349 | 0 | 0 |
| `revmesh2074.workers.dev` | 311 | 270 | 41 | 0 |
| `sistaminuten.se` | 255 | 6 | 0 | 249 |
| `afbudsrejser.dk` | 254 | 6 | 0 | 248 |
| `akkilahdot.fi` | 254 | 6 | 0 | 248 |
| `restplass.no` | 254 | 6 | 0 | 248 |
| `socialloop.ai` | 245 | 245 | 0 | 0 |
| 10192 other operators | 44471 | 41825 | 2545 | 101 |
