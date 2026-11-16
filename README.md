# MCP server tool changes

Last change observed 2026-11-16T16:34:06+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

107434 changes to a tool definition: 4382 npm releases (4136 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 103052 readings of hosted servers that found their tools changed; 4214 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-16 | `remote/dev.workers.moneytools.x402-pay-precheck/pay-precheck` | 2026-11-13T120030198224 -> 2026-11-16T163407663149 | 2 changed, 1 added | review |
| 2026-11-16 | `remote/com.stratalize/intelligence` | 2026-09-23T160853815210 -> 2026-11-16T163351080139 | 201 changed (every tool) | quiet |
| 2026-11-16 | `remote/com.stratalize/governance` | 2026-09-23T160853788559 -> 2026-11-16T163351109957 | 201 changed (every tool) | quiet |
| 2026-11-16 | `remote/com.stratalize/crypto` | 2026-09-23T160853711843 -> 2026-11-16T163350683705 | 201 changed (every tool) | quiet |
| 2026-11-16 | `remote/com.uicapsule/components` | 2026-10-23T120711625523 -> 2026-11-16T163345133801 | 1 changed | quiet |
| 2026-11-16 | `remote/com.rightshold/rightshold` | 2026-11-16T122943015126 -> 2026-11-16T163342743082 | 2 changed | quiet |
| 2026-11-16 | `remote/com.theaimeters/theaimeters` | 2026-11-13T120019505331 -> 2026-11-16T163340775403 | 2 changed | quiet |
| 2026-11-16 | `remote/com.stratalize/healthcare` | 2026-09-23T163145650766 -> 2026-11-16T163336110047 | 201 changed (every tool) | quiet |
| 2026-11-16 | `remote/no.restplass/travel-search` | 2026-11-16T122935189167 -> 2026-11-16T163325576596 | 1 changed | quiet |
| 2026-11-16 | `remote/io.github.LouisLin0723/fatestar-ziwei` | 2026-11-15T115742605253 -> 2026-11-16T163306541256 | 1 changed | review |
| 2026-11-16 | `remote/com.whiteautoandmedia/catalog` | 2026-10-25T102534166496 -> 2026-11-16T163306494209 | 3 changed (every tool) | quiet |
| 2026-11-16 | `remote/com.kulicadvisory/aictionbot-werkbank` | 2026-11-16T122920067516 -> 2026-11-16T163303501920 | 4 added | quiet |
| 2026-11-16 | `remote/com.veridionmarkets/disclosures` | 2026-11-15T002331933451 -> 2026-11-16T163302527977 | 6 changed | quiet |
| 2026-11-16 | `remote/ai.usedby/usedby` | 2026-11-15T115647550145 -> 2026-11-16T163300980744 | 1 changed | quiet |
| 2026-11-16 | `remote/com.stratalize/oracle` | 2026-09-23T161036172359 -> 2026-11-16T163249447841 | 201 changed (every tool) | quiet |
| 2026-11-16 | `remote/com.stratalize/finance` | 2026-09-23T161036101325 -> 2026-11-16T163249339882 | 201 changed (every tool) | quiet |
| 2026-11-16 | `remote/se.sistaminuten/travel-search` | 2026-11-16T123049966759 -> 2026-11-16T163252426131 | 1 changed | quiet |
| 2026-11-16 | `remote/com.stratalize/realestate` | 2026-09-23T162954700401 -> 2026-11-16T163239313544 | 201 changed (every tool) | quiet |
| 2026-11-16 | `remote/fr.capepartners/cape-exchange` | 2026-11-09T170332795725 -> 2026-11-16T163230853220 | 1 changed | quiet |
| 2026-11-16 | `remote/io.github.webweaver-nexus/webweaver-mcp-server` | 2026-10-22T105842607229 -> 2026-11-16T163222069671 | 4 changed (every tool) | quiet |
| 2026-11-16 | `remote/dk.afbudsrejser/travel-search` | 2026-11-16T122852344641 -> 2026-11-16T163222814525 | 1 changed | quiet |
| 2026-11-16 | `remote/io.github.imokokok/insight-oracle` | 2026-11-09T170335279263 -> 2026-11-16T163222839722 | 16 removed | quiet |
| 2026-11-16 | `remote/design.overflow/mcp` | 2026-11-14T115037995464 -> 2026-11-16T163223283038 | 1 changed | quiet |
| 2026-11-16 | `remote/com.kaicalls/kaicalls` | 2026-11-15T071623768215 -> 2026-11-16T163220349920 | 1 changed | quiet |
| 2026-11-16 | `remote/app.wieldr/radar` | 2026-11-15T142518083699 -> 2026-11-16T163211740870 | 1 changed | quiet |
| 2026-11-16 | `remote/studio.gradients/mcp` | 2026-11-16T123105867967 -> 2026-11-16T163204666925 | 1 changed | quiet |
| 2026-11-16 | `remote/de.firma/rechner` | 2026-11-10T030040137500 -> 2026-11-16T163158552689 | 1 added | quiet |
| 2026-11-16 | `remote/com.blitzreels/blitzreels` | 2026-11-15T212139685523 -> 2026-11-16T163158014096 | 2 changed | quiet |
| 2026-11-16 | `remote/ai.arcreport/ask` | 2026-11-16T122954894284 -> 2026-11-16T163154380753 | 1 added | quiet |
| 2026-11-16 | `remote/io.github.Voopa-Corp/render-check` | 2026-11-16T122829129979 -> 2026-11-16T163152207686 | 1 changed, 1 added | quiet |
| 2026-11-16 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-16T072238450875 -> 2026-11-16T163146438632 | 1 changed | quiet |
| 2026-11-16 | `remote/fi.akkilahdot/travel-search` | 2026-11-16T123045019130 -> 2026-11-16T163136000031 | 1 changed | quiet |
| 2026-11-16 | `remote/io.github.mooshee/untax` | 2026-11-09T170240506598 -> 2026-11-16T163133817803 | 2 changed, 8 added | quiet |
| 2026-11-16 | `remote/global.uain/network` | 2026-11-16T122804296301 -> 2026-11-16T163125790482 | 1 changed, 5 added | quiet |
| 2026-11-16 | `remote/com.weverlabs/agentic-rails` | 2026-09-23T162928099124 -> 2026-11-16T163120550339 | 538 added, 5 removed | review |
| 2026-11-16 | `remote/app.openkrill/travel` | 2026-10-22T110145971280 -> 2026-11-16T163109930681 | 5 changed (every tool) | quiet |
| 2026-11-16 | `remote/cc.thecolony/mcp-server` | 2026-11-15T212258939370 -> 2026-11-16T163102070805 | 1 changed, 2 added | quiet |
| 2026-11-16 | `remote/com.viraloutliers/viral-outliers` | 2026-11-14T140148610122 -> 2026-11-16T163101262344 | 2 changed | quiet |
| 2026-11-16 | `remote/org.texs/tapercraft` | 2026-10-17T055532590816 -> 2026-11-16T163058372885 | 4 changed | quiet |
| 2026-11-16 | `remote/dev.vetagent/vetagent` | 2026-11-15T212151296909 -> 2026-11-16T163056199629 | 1 changed | quiet |
| 2026-11-16 | `remote/dev.tanod/util` | 2026-11-16T122658024910 -> 2026-11-16T163045548314 | 3 changed | quiet |
| 2026-11-16 | `remote/dev.tanod/images` | 2026-11-16T122656306102 -> 2026-11-16T163045051779 | 3 changed | quiet |
| 2026-11-16 | `remote/org.thewileyrule/public` | 2026-11-16T122737754284 -> 2026-11-16T163043887030 | 1 changed, 1 added | quiet |
| 2026-11-16 | `remote/io.github.PascalSun/talk2geo` | 2026-11-16T072303665846 -> 2026-11-16T163043744260 | 1 changed | quiet |
| 2026-11-16 | `remote/io.github.t0ll-xyz/toll` | 2026-11-16T072301797717 -> 2026-11-16T163039971214 | 1 changed | quiet |
| 2026-11-16 | `remote/io.untax/untax` | 2026-11-09T170146703402 -> 2026-11-16T163039339980 | 2 changed, 8 added | quiet |
| 2026-11-16 | `remote/ai.surfingdog/search` | 2026-11-13T124140164310 -> 2026-11-16T163031029209 | 3 changed | quiet |
| 2026-11-16 | `remote/app.openkrill/trending` | 2026-11-11T145951482748 -> 2026-11-16T163022281258 | 6 changed (every tool) | quiet |
| 2026-11-16 | `remote/dev.tanod/finance` | 2026-11-16T122716707937 -> 2026-11-16T163013187467 | 4 changed | quiet |
| 2026-11-16 | `remote/dev.tanod/chain` | 2026-11-16T122716491933 -> 2026-11-16T163013807575 | 2 changed | quiet |
| 2026-11-16 | `remote/dev.moneytools/tools` | 2026-11-13T115821660280 -> 2026-11-16T163007248632 | 1 changed, 1 added | review |
| 2026-11-16 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-11-16T072257903238 -> 2026-11-16T163004714402 | 2 added, 100 removed | quiet |
| 2026-11-16 | `remote/help.socket/socket-help` | 2026-11-15T212256554448 -> 2026-11-16T162956751871 | 4 changed | quiet |
| 2026-11-16 | `remote/app.askqa/structforge` | 2026-09-23T163018050205 -> 2026-11-16T162948727961 | 3 changed | quiet |
| 2026-11-16 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-16T122658069658 -> 2026-11-16T162945450681 | 1 added | quiet |
| 2026-11-16 | `remote/app.openkrill/tariffs` | 2026-11-15T142459766784 -> 2026-11-16T162943968587 | 4 changed (every tool) | quiet |
| 2026-11-16 | `remote/dev.tanod/web` | 2026-11-16T122910559500 -> 2026-11-16T162943239492 | 4 changed | quiet |
| 2026-11-16 | `remote/dev.tanod/security` | 2026-11-16T122909792183 -> 2026-11-16T162942853293 | 3 changed | quiet |
| 2026-11-16 | `remote/dev.tanod/bank-statement` | 2026-11-16T122909499982 -> 2026-11-16T162942142758 | 1 changed | quiet |
| 2026-11-16 | `remote/io.github.spree/ecommerce-docs` | 2026-11-14T010646164901 -> 2026-11-16T162934798115 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 65633 substantive, 40751 that changed only numbers (a catalogue counter ticking, a date), 1050 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 58079 | 19726 | 38353 | 0 |
| `a2awire.com` | 2974 | 2974 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 460 | 460 | 0 | 0 |
| `civai.co` | 365 | 365 | 0 | 0 |
| `modevc.com` | 305 | 305 | 0 | 0 |
| `revmesh2074.workers.dev` | 275 | 242 | 33 | 0 |
| `sistaminuten.se` | 245 | 6 | 0 | 239 |
| `afbudsrejser.dk` | 244 | 6 | 0 | 238 |
| `akkilahdot.fi` | 244 | 6 | 0 | 238 |
| `restplass.no` | 244 | 6 | 0 | 238 |
| `socialloop.ai` | 236 | 236 | 0 | 0 |
| 9622 other operators | 41422 | 38960 | 2365 | 97 |
