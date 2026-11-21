# MCP server tool changes

Last change observed 2026-11-21T01:49:35+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

121307 changes to a tool definition: 4852 npm releases (4606 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 116455 readings of hosted servers that found their tools changed; 4575 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-21 | `remote/today.thekorean/news` | 2026-11-20T172149033601 -> 2026-11-21T014937251510 | 4 changed, 5 added | quiet |
| 2026-11-21 | `remote/com.kaicalls/kaicalls.1` | 2026-11-19T124046823725 -> 2026-11-21T014935131348 | 1 changed | quiet |
| 2026-11-21 | `remote/studio.gradients/mcp` | 2026-11-20T172144054678 -> 2026-11-21T014934259813 | 1 changed | quiet |
| 2026-11-21 | `remote/app.hyperwave.www/wavetable-tools` | 2026-11-19T124042443104 -> 2026-11-21T014934250120 | 1 changed | quiet |
| 2026-11-21 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-20T074959766448 -> 2026-11-21T014933238475 | 1 changed | quiet |
| 2026-11-21 | `remote/fi.akkilahdot/travel-search` | 2026-11-20T172143211491 -> 2026-11-21T014934040884 | 1 changed | quiet |
| 2026-11-21 | `remote/com.weverlabs/agentic-rails` | 2026-11-19T231839611462 -> 2026-11-21T014939295922 | 8 added | quiet |
| 2026-11-21 | `remote/io.github.nirholas/threews-grok` | 2026-11-20T105556751487 -> 2026-11-21T014929037608 | 1 changed | quiet |
| 2026-11-21 | `remote/net.stabledomains/registrar` | 2026-11-20T160118567801 -> 2026-11-21T014927820827 | 1 added | quiet |
| 2026-11-21 | `remote/io.shiptrail/shiptrail` | 2026-11-20T105422938171 -> 2026-11-21T014925876229 | 9 changed (every tool) | quiet |
| 2026-11-21 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-20T172131598003 -> 2026-11-21T014926958840 | 1 changed | quiet |
| 2026-11-21 | `remote/io.github.LusoCryptoLabs/ckb-pulse` | 2026-11-19T231821403224 -> 2026-11-21T014925736600 | 1 changed | quiet |
| 2026-11-21 | `remote/dev.zambo/zambo` | 2026-11-20T105724312501 -> 2026-11-21T014921112549 | 5 changed | quiet |
| 2026-11-21 | `remote/com.youspot/youspot` | 2026-11-20T074945721235 -> 2026-11-21T014921196309 | 2 changed | quiet |
| 2026-11-21 | `remote/io.github.Fractal-Neurons/pacta` | 2026-11-19T231812596211 -> 2026-11-21T014918937138 | 1 changed, 1 added | quiet |
| 2026-11-21 | `remote/com.multicinesortega/cartelera` | 2026-11-20T074941391452 -> 2026-11-21T014918289855 | 1 changed | quiet |
| 2026-11-21 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-20T172116193191 -> 2026-11-21T014916161875 | 2 changed | quiet |
| 2026-11-21 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-20T105621665931 -> 2026-11-21T014916045169 | 3 changed | quiet |
| 2026-11-21 | `remote/io.github.bostanyshop-rgb/growtsy` | 2026-11-20T105622815243 -> 2026-11-21T014915167760 | 10 changed | quiet |
| 2026-11-21 | `remote/io.github.roomi-fields/osc-bridge` | 2026-11-20T155624429006 -> 2026-11-21T014914531971 | 2 changed | quiet |
| 2026-11-21 | `remote/com.stocklens/stocklens` | 2026-11-19T135824619461 -> 2026-11-21T014912478517 | 7 changed | quiet |
| 2026-11-21 | `remote/io.github.brawlaphant/vealth` | 2026-11-20T074935414600 -> 2026-11-21T014911740102 | 1 changed, 3 added | quiet |
| 2026-11-21 | `remote/com.ortexo/mcp` | 2026-11-20T172109448585 -> 2026-11-21T014911196525 | 4 changed, 1 added | quiet |
| 2026-11-21 | `remote/ai.mapmap/mapmap` | 2026-11-20T155450429580 -> 2026-11-21T014911624240 | 1 changed | quiet |
| 2026-11-21 | `remote/io.github.nirholas/threews-3d-studio-free` | 2026-11-20T105435588258 -> 2026-11-21T014909427785 | 1 changed | quiet |
| 2026-11-21 | `remote/io.github.magichourhq/magic-hour` | 2026-11-20T074928870854 -> 2026-11-21T014910079029 | 2 changed | quiet |
| 2026-11-21 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-20T172128651779 -> 2026-11-21T014909407611 | 2 changed, 4 added | quiet |
| 2026-11-21 | `remote/io.github.t0ll-xyz/toll` | 2026-11-19T135851304179 -> 2026-11-21T014908204671 | 1 added | quiet |
| 2026-11-21 | `remote/com.kitsdeals/deals` | 2026-11-19T123024454372 -> 2026-11-21T014908683327 | 2 changed | quiet |
| 2026-11-21 | `remote/com.kernelcad/kernelcad` | 2026-11-20T104836750766 -> 2026-11-21T014909428531 | 2 changed | quiet |
| 2026-11-21 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-11-19T020419031247 -> 2026-11-21T014906446235 | 1 changed | quiet |
| 2026-11-21 | `remote/io.github.Embassy-of-the-Free-Mind/sourcelibrary` | 2026-11-20T155748578287 -> 2026-11-21T014906700928 | 1 changed | quiet |
| 2026-11-21 | `remote/com.simplyglobal/visitor-insurance` | 2026-11-20T105327467117 -> 2026-11-21T014905477853 | 1 changed | quiet |
| 2026-11-21 | `remote/now.salesjobs/mcp` | 2026-11-19T020417072386 -> 2026-11-21T014904798814 | 1 changed | quiet |
| 2026-11-21 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-11-20T074930394683 -> 2026-11-21T014904261584 | 1 changed | quiet |
| 2026-11-21 | `remote/com.imagiolabs.www/imagio-relay` | 2026-11-20T172117940053 -> 2026-11-21T014902268774 | 16 changed | review |
| 2026-11-21 | `remote/io.github.canoydario847-cloud/privi-quantum` | 2026-11-20T155509583455 -> 2026-11-21T014901071873 | 1 added | quiet |
| 2026-11-21 | `remote/com.provyan/provyan` | 2026-11-20T074926066360 -> 2026-11-21T014901281467 | 1 changed | quiet |
| 2026-11-21 | `remote/io.prospre/nutrients` | 2026-11-20T105101470187 -> 2026-11-21T014859612822 | 1 changed | quiet |
| 2026-11-21 | `remote/io.github.OptimNow/ai-pricing-hub` | 2026-11-20T105113909518 -> 2026-11-21T014859312395 | 1 changed | quiet |
| 2026-11-21 | `remote/io.github.Kromatic-Innovation/neumann` | 2026-11-19T135837620073 -> 2026-11-21T014857456607 | 8 changed | quiet |
| 2026-11-21 | `remote/io.github.Red-Center-Studio/nocode-migrator` | 2026-11-20T155328195468 -> 2026-11-21T014857288025 | 1 changed | quiet |
| 2026-11-21 | `remote/space.canopy/sales` | 2026-11-19T122852523558 -> 2026-11-21T014852162629 | 1 changed | quiet |
| 2026-11-21 | `remote/com.boxerbook/boxing` | 2026-11-20T104723813233 -> 2026-11-21T014852754927 | 3 changed | quiet |
| 2026-11-21 | `remote/io.soundchecklive/live-event-quotes` | 2026-11-19T122931052661 -> 2026-11-21T014850125042 | 2 changed | quiet |
| 2026-11-21 | `remote/cloud.somewhere/platform` | 2026-11-20T074917056514 -> 2026-11-21T014849071866 | 3 changed (every tool) | quiet |
| 2026-11-21 | `remote/ai.bamf/bamf` | 2026-11-20T172058733721 -> 2026-11-21T014851540777 | 1 changed | quiet |
| 2026-11-21 | `remote/pro.aicut/aicut` | 2026-11-20T155220082933 -> 2026-11-21T014843299452 | 1 changed, 12 removed | quiet |
| 2026-11-21 | `remote/tech.kaiku/kaiku.1` | 2026-11-20T104802095245 -> 2026-11-21T014844881650 | 2 changed, 6 added | quiet |
| 2026-11-21 | `remote/fun.make/makefun` | 2026-11-20T172056263565 -> 2026-11-21T014840832652 | 1 changed | quiet |
| 2026-11-21 | `remote/com.esqcopilot/matching-engine` | 2026-11-20T172056320538 -> 2026-11-21T014839456458 | 1 added | quiet |
| 2026-11-21 | `remote/io.github.dreamworkhq/dreamwork` | 2026-11-19T122731637122 -> 2026-11-21T014838343818 | 16 changed | quiet |
| 2026-11-21 | `remote/nl.knappekeuze/catalogus` | 2026-11-19T231740108273 -> 2026-11-21T014832063351 | 3 changed | quiet |
| 2026-11-21 | `remote/me.besthotels4/reservas` | 2026-11-19T122706442556 -> 2026-11-21T014825791591 | 2 changed, 1 added | quiet |
| 2026-11-21 | `remote/fr.ip73/ip73` | 2026-11-20T172050312628 -> 2026-11-21T014827247757 | 2 changed | quiet |
| 2026-11-21 | `remote/net.hotelrefund/price-tracker` | 2026-11-20T074915988667 -> 2026-11-21T014822204461 | 1 changed | quiet |
| 2026-11-21 | `remote/com.werop/catalog` | 2026-11-20T105611299447 -> 2026-11-21T014816095807 | 8 changed (every tool) | quiet |
| 2026-11-21 | `remote/com.veridionmarkets/disclosures` | 2026-11-20T105609275007 -> 2026-11-21T014815725510 | 1 changed | quiet |
| 2026-11-21 | `remote/no.restplass/travel-search` | 2026-11-20T172223874017 -> 2026-11-21T014815184959 | 1 changed | quiet |
| 2026-11-21 | `remote/io.github.AKzar1el/god-prompt-mcp` | 2026-11-20T154934992337 -> 2026-11-21T014817654221 | 13 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 79095 substantive, 41077 that changed only numbers (a catalogue counter ticking, a date), 1135 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 65550 | 27196 | 38354 | 0 |
| `a2awire.com` | 3571 | 3571 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 480 | 480 | 0 | 0 |
| `modevc.com` | 436 | 436 | 0 | 0 |
| `civai.co` | 399 | 399 | 0 | 0 |
| `revmesh2074.workers.dev` | 346 | 294 | 52 | 0 |
| `sistaminuten.se` | 264 | 6 | 0 | 258 |
| `afbudsrejser.dk` | 263 | 6 | 0 | 257 |
| `akkilahdot.fi` | 263 | 6 | 0 | 257 |
| `restplass.no` | 263 | 6 | 0 | 257 |
| `socialloop.ai` | 254 | 254 | 0 | 0 |
| 10549 other operators | 46877 | 44100 | 2671 | 106 |
