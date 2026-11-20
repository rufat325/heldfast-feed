# MCP server tool changes

Last change observed 2026-11-20T17:22:24+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

121102 changes to a tool definition: 4852 npm releases (4606 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 116250 readings of hosted servers that found their tools changed; 4560 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-20 | `remote/se.sistaminuten/travel-search` | 2026-11-20T160028596127 -> 2026-11-20T172225624043 | 1 changed | quiet |
| 2026-11-20 | `remote/org.omenz.www/agent-tools` | 2026-11-19T123858900179 -> 2026-11-20T172224119539 | 2 added | quiet |
| 2026-11-20 | `remote/no.restplass/travel-search` | 2026-11-20T160327051480 -> 2026-11-20T172223874017 | 1 changed | quiet |
| 2026-11-20 | `remote/top.web3project/mcp-audit` | 2026-11-20T105439692868 -> 2026-11-20T172219187368 | 3 added | quiet |
| 2026-11-20 | `remote/dk.afbudsrejser/travel-search` | 2026-11-20T160231188164 -> 2026-11-20T172218980186 | 1 changed | quiet |
| 2026-11-20 | `remote/com.vidreno/mcp` | 2026-11-19T162338259398 -> 2026-11-20T172217317123 | 19 changed, 11 added, 5 removed | quiet |
| 2026-11-20 | `remote/com.trackerhacker/mcp` | 2026-11-19T123659356481 -> 2026-11-20T172212715965 | 1 changed | quiet |
| 2026-11-20 | `remote/io.github.hardtab/supercheap-shopping` | 2026-11-19T123601664076 -> 2026-11-20T172211830422 | 2 changed | quiet |
| 2026-11-20 | `remote/com.lvl2player/sandbox` | 2026-11-20T105211094183 -> 2026-11-20T172205783641 | 1 changed | quiet |
| 2026-11-20 | `remote/ai.screwtape/screwtape` | 2026-11-20T074926328066 -> 2026-11-20T172205420156 | 2 changed | quiet |
| 2026-11-20 | `remote/io.github.smarterweather/weather` | 2026-11-20T074921795828 -> 2026-11-20T172153535148 | 1 changed | quiet |
| 2026-11-20 | `remote/ai.signal8/mcp` | 2026-11-20T105154280621 -> 2026-11-20T172151281637 | 1 changed | quiet |
| 2026-11-20 | `remote/today.thekorean/news` | 2026-11-20T160531290423 -> 2026-11-20T172149033601 | 3 added | quiet |
| 2026-11-20 | `remote/com.splitscanner/mcp` | 2026-11-20T104855430423 -> 2026-11-20T172150309375 | 1 changed | quiet |
| 2026-11-20 | `remote/eu.paymentslaw/legislation` | 2026-11-18T134846476519 -> 2026-11-20T172149003129 | 1 changed | quiet |
| 2026-11-20 | `remote/ai.ohmyfin/invoice` | 2026-11-19T231807267687 -> 2026-11-20T172148241989 | 2 changed | quiet |
| 2026-11-20 | `remote/ai.ohmyfin/banking-intelligence` | 2026-11-19T231807176219 -> 2026-11-20T172147853139 | 2 changed | quiet |
| 2026-11-20 | `remote/studio.gradients/mcp` | 2026-11-20T160442972324 -> 2026-11-20T172144054678 | 1 changed | quiet |
| 2026-11-20 | `remote/fi.akkilahdot/travel-search` | 2026-11-20T160355648908 -> 2026-11-20T172143211491 | 1 changed | quiet |
| 2026-11-20 | `remote/com.dimhour/catalog` | 2026-11-19T122902078139 -> 2026-11-20T172139742713 | 3 changed | quiet |
| 2026-11-20 | `remote/com.dilutionscan/mcp` | 2026-11-20T104659602178 -> 2026-11-20T172139143563 | 1 changed | quiet |
| 2026-11-20 | `remote/io.github.bitcoinresearchkit/bitview` | 2026-11-20T104636553568 -> 2026-11-20T172136479575 | 1 changed, 7 added | quiet |
| 2026-11-20 | `remote/io.github.sustany/alcbar-match` | 2026-11-20T154917535460 -> 2026-11-20T172133579045 | 1 changed | quiet |
| 2026-11-20 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-20T160201819788 -> 2026-11-20T172134748095 | 1 changed | quiet |
| 2026-11-20 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-20T160105905228 -> 2026-11-20T172131598003 | 1 changed | quiet |
| 2026-11-20 | `remote/io.github.QDThead/signal-lab` | 2026-11-20T160050120925 -> 2026-11-20T172130422262 | 3 changed | quiet |
| 2026-11-20 | `remote/com.triremes/triremes` | 2026-11-18T161603399228 -> 2026-11-20T172129407070 | 2 changed | quiet |
| 2026-11-20 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-19T162317671276 -> 2026-11-20T172128651779 | 1 added | quiet |
| 2026-11-20 | `remote/earth.remap/routes` | 2026-11-19T122538778418 -> 2026-11-20T172127732669 | 2 changed | quiet |
| 2026-11-20 | `remote/io.github.gridhopai/gpu-price-index` | 2026-11-20T154709046131 -> 2026-11-20T172124886017 | 1 changed | quiet |
| 2026-11-20 | `remote/io.github.PascalSun/talk2geo` | 2026-11-20T105416373759 -> 2026-11-20T172126781329 | 20 added | quiet |
| 2026-11-20 | `remote/no.pristavla/pristavla` | 2026-11-19T231817964838 -> 2026-11-20T172124870595 | 1 changed | quiet |
| 2026-11-20 | `remote/za.co.getlawed/sa-law` | 2026-11-18T173902091045 -> 2026-11-20T172127156456 | 4 added | quiet |
| 2026-11-20 | `remote/com.scraperwatch/scraperwatch` | 2026-11-20T155646444437 -> 2026-11-20T172120916220 | 1 changed | quiet |
| 2026-11-20 | `remote/com.imagiolabs.www/imagio-relay` | 2026-11-20T105228404248 -> 2026-11-20T172117940053 | 11 changed | quiet |
| 2026-11-20 | `remote/ai.llpro.countersign/countersign` | 2026-11-20T074857995612 -> 2026-11-20T172115814821 | 1 changed | quiet |
| 2026-11-20 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-20T155719302801 -> 2026-11-20T172116193191 | 2 changed | quiet |
| 2026-11-20 | `remote/ai.contractorsnearme/contractors-near-me` | 2026-11-19T122124173954 -> 2026-11-20T172116769953 | 7 changed, 5 removed | quiet |
| 2026-11-20 | `remote/com.toiseai/toise` | 2026-11-20T155632186753 -> 2026-11-20T172114331933 | 3 changed | quiet |
| 2026-11-20 | `remote/com.bullionpricecheck/bullion-price-check` | 2026-11-20T103958403613 -> 2026-11-20T172111662414 | 8 changed | quiet |
| 2026-11-20 | `remote/io.github.TaltonFiggins/election-atlas` | 2026-11-19T121951166641 -> 2026-11-20T172109814523 | 2 changed | quiet |
| 2026-11-20 | `remote/com.ortexo/mcp` | 2026-11-20T104928573085 -> 2026-11-20T172109448585 | 1 changed | quiet |
| 2026-11-20 | `remote/ai.ohmyfin/sanctions` | 2026-11-19T231758752337 -> 2026-11-20T172108645940 | 2 changed | quiet |
| 2026-11-20 | `remote/sh.while/while` | 2026-11-20T154222190141 -> 2026-11-20T172107185814 | 1 changed | quiet |
| 2026-11-20 | `remote/ru.arckep/mcp` | 2026-11-20T154228036418 -> 2026-11-20T172111102971 | 1 changed, 2 added | quiet |
| 2026-11-20 | `remote/com.applystead/jobs` | 2026-11-20T154222469817 -> 2026-11-20T172106384064 | 4 changed | quiet |
| 2026-11-20 | `remote/com.word-flux/mcp` | 2026-11-20T103843986200 -> 2026-11-20T172103400012 | 3 changed, 5 added, 5 removed | quiet |
| 2026-11-20 | `remote/uk.co.taptax/taptax` | 2026-11-19T121842542254 -> 2026-11-20T172100598295 | 1 changed | quiet |
| 2026-11-20 | `remote/com.spellbook-finance/mcp` | 2026-11-19T231712445333 -> 2026-11-20T172100468593 | 2 changed | quiet |
| 2026-11-20 | `remote/org.polyform/polyform` | 2026-11-20T154101954357 -> 2026-11-20T172058254332 | 8 added | quiet |
| 2026-11-20 | `remote/ai.bamf/bamf` | 2026-11-20T104716553621 -> 2026-11-20T172058733721 | 1 changed, 1 added | quiet |
| 2026-11-20 | `remote/com.mangoinventory/mango-inventory` | 2026-11-20T155057742378 -> 2026-11-20T172056919246 | 60 changed (every tool) | quiet |
| 2026-11-20 | `remote/com.esqcopilot/matching-engine` | 2026-11-20T155202433529 -> 2026-11-20T172056320538 | 1 changed | quiet |
| 2026-11-20 | `remote/fun.make/makefun` | 2026-11-20T155151708210 -> 2026-11-20T172056263565 | 1 changed | quiet |
| 2026-11-20 | `remote/co.madbroad/madbroad` | 2026-11-18T134713993845 -> 2026-11-20T172055043890 | 1 removed | quiet |
| 2026-11-20 | `remote/net.libertycity/mods` | 2026-11-20T155135720673 -> 2026-11-20T172057216640 | 2 changed | quiet |
| 2026-11-20 | `remote/io.github.rajeswaran140/crowvault` | 2026-11-20T153953493274 -> 2026-11-20T172053913694 | 1 changed | quiet |
| 2026-11-20 | `remote/fi.arche/arche` | 2026-11-19T231701107433 -> 2026-11-20T172053959147 | 67 changed (every tool) | quiet |
| 2026-11-20 | `remote/io.github.0xinsider/mcp` | 2026-11-19T231704545005 -> 2026-11-20T172052640683 | 2 changed | quiet |
| 2026-11-20 | `remote/fr.ip73/ip73` | 2026-11-20T155033451426 -> 2026-11-20T172050312628 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 78906 substantive, 41065 that changed only numbers (a catalogue counter ticking, a date), 1131 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 65550 | 27196 | 38354 | 0 |
| `a2awire.com` | 3571 | 3571 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 479 | 479 | 0 | 0 |
| `modevc.com` | 436 | 436 | 0 | 0 |
| `civai.co` | 399 | 399 | 0 | 0 |
| `revmesh2074.workers.dev` | 343 | 293 | 50 | 0 |
| `sistaminuten.se` | 263 | 6 | 0 | 257 |
| `afbudsrejser.dk` | 262 | 6 | 0 | 256 |
| `akkilahdot.fi` | 262 | 6 | 0 | 256 |
| `restplass.no` | 262 | 6 | 0 | 256 |
| `socialloop.ai` | 253 | 253 | 0 | 0 |
| 10548 other operators | 46681 | 43914 | 2661 | 106 |
