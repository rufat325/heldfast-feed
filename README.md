# MCP server tool changes

Last change observed 2026-11-22T07:32:56+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

124283 changes to a tool definition: 4965 npm releases (4719 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 119318 readings of hosted servers that found their tools changed; 4639 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-22 | `remote/io.github.bostanyshop-rgb/growtsy` | 2026-11-21T151152611311 -> 2026-11-22T073257039135 | 2 changed | quiet |
| 2026-11-22 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-21T014916045169 -> 2026-11-22T073258065020 | 2 changed | quiet |
| 2026-11-22 | `remote/io.github.nirholas/threews-3d-studio-free` | 2026-11-21T014909427785 -> 2026-11-22T073253302004 | 5 added | quiet |
| 2026-11-22 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-21T014909407611 -> 2026-11-22T073254412937 | 2 changed, 5 added | quiet |
| 2026-11-22 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-11-21T014904261584 -> 2026-11-22T073249875107 | 1 changed | quiet |
| 2026-11-22 | `remote/app.pitbi/pitbi` | 2026-11-21T215653793438 -> 2026-11-22T073247198127 | 3 changed | quiet |
| 2026-11-22 | `remote/dev.pdfops/pdfops-mcp` | 2026-11-21T215650097538 -> 2026-11-22T073245169413 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.Red-Center-Studio/nocode-migrator` | 2026-11-21T150624554685 -> 2026-11-22T073243715472 | 2 changed | quiet |
| 2026-11-22 | `remote/com.midasiteurope/civil-nx` | 2026-11-21T150553323129 -> 2026-11-22T073242031399 | 2 changed | quiet |
| 2026-11-22 | `remote/io.soundchecklive/live-event-quotes` | 2026-11-21T014850125042 -> 2026-11-22T073239308832 | 8 changed | quiet |
| 2026-11-22 | `remote/studio.gradients/mcp` | 2026-11-21T215753467032 -> 2026-11-22T073232351937 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.SoapyRED/freightutils` | 2026-11-21T151135838334 -> 2026-11-22T073232903176 | 1 changed | quiet |
| 2026-11-22 | `remote/co.ibda/ibda` | 2026-11-21T130613529972 -> 2026-11-22T073231845266 | 1 changed | quiet |
| 2026-11-22 | `remote/fi.akkilahdot/travel-search` | 2026-11-21T215751942601 -> 2026-11-22T073231866377 | 1 changed | quiet |
| 2026-11-22 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-21T215752755912 -> 2026-11-22T073231520588 | 3 changed | quiet |
| 2026-11-22 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-21T014933238475 -> 2026-11-22T073230636540 | 1 changed | quiet |
| 2026-11-22 | `remote/com.weverlabs/agentic-rails` | 2026-11-21T215757272056 -> 2026-11-22T073237515636 | 8 added, 1 removed | quiet |
| 2026-11-22 | `remote/io.github.nirholas/threews-grok` | 2026-11-21T014929037608 -> 2026-11-22T073227220419 | 5 added | quiet |
| 2026-11-22 | `remote/com.tamingdns/mcp` | 2026-11-21T215745077485 -> 2026-11-22T073225652069 | 3 changed | quiet |
| 2026-11-22 | `remote/io.shiptrail/shiptrail` | 2026-11-21T014925876229 -> 2026-11-22T073222752465 | 4 changed | quiet |
| 2026-11-22 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-21T215742080613 -> 2026-11-22T073223783647 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.Shicodiez/crypto-regime-mcp` | 2026-11-21T215741656289 -> 2026-11-22T073223088320 | 2 removed | quiet |
| 2026-11-22 | `remote/com.serviche/sergio` | 2026-11-21T150816638006 -> 2026-11-22T073228190977 | 1 changed | quiet |
| 2026-11-22 | `remote/sh.rentadomain/rentadomain` | 2026-11-21T150733891514 -> 2026-11-22T073221164718 | 1 changed | quiet |
| 2026-11-22 | `remote/com.remoshift/jobs` | 2026-11-21T215736907723 -> 2026-11-22T073220030044 | 1 changed | quiet |
| 2026-11-22 | `remote/com.jojapi/product-barcode-api` | 2026-11-21T130550107157 -> 2026-11-22T073223384577 | 1 changed | quiet |
| 2026-11-22 | `remote/co.productaura/productaura.1` | 2026-11-20T155915662796 -> 2026-11-22T073218284271 | 1 changed | review |
| 2026-11-22 | `remote/codes.onv/onv-mcp` | 2026-11-21T150622974326 -> 2026-11-22T073215154265 | 50 added, 1 removed | review |
| 2026-11-22 | `remote/io.github.yuli3/oiyo-news.1` | 2026-11-21T150540478151 -> 2026-11-22T073212828548 | 1 changed | quiet |
| 2026-11-22 | `remote/com.multicinesortega/cartelera` | 2026-11-21T215727844997 -> 2026-11-22T073212974866 | 1 changed | quiet |
| 2026-11-22 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-21T215725859061 -> 2026-11-22T073210649964 | 4 changed | quiet |
| 2026-11-22 | `remote/com.sonarconnections/sonar-connections` | 2026-11-21T130551596473 -> 2026-11-22T073209511589 | 3 changed | quiet |
| 2026-11-22 | `remote/se.sistaminuten/travel-search` | 2026-11-21T215741513699 -> 2026-11-22T073207717557 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.ChanMeng666/archlang-mcp` | 2026-11-20T154930371743 -> 2026-11-22T073210044081 | 1 changed | quiet |
| 2026-11-22 | `remote/org.omenz.www/agent-tools` | 2026-11-21T215739176260 -> 2026-11-22T073206539447 | 1 added | quiet |
| 2026-11-22 | `remote/io.github.roomi-fields/osc-bridge` | 2026-11-21T215722436767 -> 2026-11-22T073207594856 | 6 changed | quiet |
| 2026-11-22 | `remote/com.onlyworlds/mcp` | 2026-11-21T151123808011 -> 2026-11-22T073206643225 | 2 changed | quiet |
| 2026-11-22 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-11-21T215750727819 -> 2026-11-22T073206085786 | 9 changed, 1 added | quiet |
| 2026-11-22 | `remote/io.github.JcJamet/ia-qa-security` | 2026-11-21T215750404162 -> 2026-11-22T073205888224 | 3 changed | quiet |
| 2026-11-22 | `remote/com.herbertandphyllis/mcp` | 2026-11-20T155958819630 -> 2026-11-22T073205411564 | 1 changed | quiet |
| 2026-11-22 | `remote/dev.qrdx/qrdx` | 2026-11-21T215720019911 -> 2026-11-22T073205189338 | 2 changed | quiet |
| 2026-11-22 | `remote/com.cm7brasil.www/mcp` | 2026-11-21T151045346811 -> 2026-11-22T073203987805 | 2 changed, 2 added | quiet |
| 2026-11-22 | `remote/com.ortexo/mcp` | 2026-11-21T215718415911 -> 2026-11-22T073203633210 | 11 changed | quiet |
| 2026-11-22 | `remote/io.github.MKagesawa/masadeals` | 2026-11-21T130539255705 -> 2026-11-22T073203207044 | 1 changed | quiet |
| 2026-11-22 | `remote/com.vet402/vet402` | 2026-11-21T130641356669 -> 2026-11-22T073201885457 | 2 changed, 1 added | quiet |
| 2026-11-22 | `remote/org.verifiedhandles/verified-handles` | 2026-11-21T150936657286 -> 2026-11-22T073202507843 | 3 changed | quiet |
| 2026-11-22 | `remote/app.usesnippet/snippet` | 2026-11-20T105413068056 -> 2026-11-22T073201163166 | 18 changed (every tool) | quiet |
| 2026-11-22 | `remote/ai.llpro/campus` | 2026-11-21T215626566658 -> 2026-11-22T073203880395 | 12 added | review |
| 2026-11-22 | `remote/net.swaptitan/swaptitan` | 2026-11-21T150818589814 -> 2026-11-22T073158921482 | 2 changed | quiet |
| 2026-11-22 | `remote/io.github.daniel3303/equibles` | 2026-11-21T215712936945 -> 2026-11-22T073201222130 | 3 changed | quiet |
| 2026-11-22 | `remote/com.thefomite/fomite` | 2026-11-21T014803668879 -> 2026-11-22T073159905784 | 1 changed | quiet |
| 2026-11-22 | `remote/xyz.sofinancelab/sofinance` | 2026-11-21T130634605807 -> 2026-11-22T073158590619 | 1 changed | quiet |
| 2026-11-22 | `remote/fun.make/makefun` | 2026-11-21T215702321596 -> 2026-11-22T073154764703 | 15 changed | quiet |
| 2026-11-22 | `remote/io.github.si-imtiaz/leadquasar` | 2026-11-20T104602579920 -> 2026-11-22T073154313178 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.f-tiger/getecoback-climate-weather` | 2026-11-20T104345360273 -> 2026-11-22T073155689476 | 1 added, 1 removed | quiet |
| 2026-11-22 | `remote/app.qrcodecreator/qr-codes` | 2026-11-21T215719740926 -> 2026-11-22T073153461487 | 1 changed | quiet |
| 2026-11-22 | `remote/nl.opahaardhout/opahaardhout` | 2026-11-21T150533655513 -> 2026-11-22T073151552421 | 1 changed | quiet |
| 2026-11-22 | `remote/net.hotelrefund/price-tracker` | 2026-11-21T014822204461 -> 2026-11-22T073150724090 | 1 changed | quiet |
| 2026-11-22 | `remote/io.outil/outil` | 2026-11-21T215717224705 -> 2026-11-22T073153422437 | 1 changed, 17 added | quiet |
| 2026-11-22 | `remote/fr.ip73/ip73` | 2026-11-21T215657780533 -> 2026-11-22T073151507236 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 81992 substantive, 41138 that changed only numbers (a catalogue counter ticking, a date), 1153 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 67416 | 29061 | 38355 | 0 |
| `a2awire.com` | 3571 | 3571 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 487 | 487 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 401 | 401 | 0 | 0 |
| `revmesh2074.workers.dev` | 360 | 306 | 54 | 0 |
| `sistaminuten.se` | 268 | 6 | 0 | 262 |
| `afbudsrejser.dk` | 267 | 6 | 0 | 261 |
| `akkilahdot.fi` | 267 | 6 | 0 | 261 |
| `restplass.no` | 267 | 6 | 0 | 261 |
| `socialloop.ai` | 258 | 258 | 0 | 0 |
| 10683 other operators | 47900 | 45063 | 2729 | 108 |
