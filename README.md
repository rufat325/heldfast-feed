# MCP server tool changes

Last change observed 2026-11-05T15:11:16+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

78286 changes to a tool definition: 3319 npm releases (3073 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 74967 readings of hosted servers that found their tools changed; 3415 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-05 | `remote/se.sistaminuten/travel-search` | 2026-11-05T124844239209 -> 2026-11-05T151117687159 | 1 changed | quiet |
| 2026-11-05 | `remote/uk.co.speedi/availability` | 2026-11-03T145042229136 -> 2026-11-05T151109014164 | 1 added | quiet |
| 2026-11-05 | `remote/dev.workers.sebastiaan-ba3.x402lint/tools` | 2026-11-04T150821540612 -> 2026-11-05T151104032678 | 1 changed | quiet |
| 2026-11-05 | `remote/studio.gradients/mcp` | 2026-11-05T124830628598 -> 2026-11-05T151044512333 | 1 changed | quiet |
| 2026-11-05 | `remote/fi.akkilahdot/travel-search` | 2026-11-05T124828469631 -> 2026-11-05T151024796729 | 1 changed | quiet |
| 2026-11-05 | `remote/ai.whatareyoubuilding/wayb` | 2026-10-17T055542913217 -> 2026-11-05T151017701066 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-05T124827463802 -> 2026-11-05T150955932168 | 3 changed | quiet |
| 2026-11-05 | `remote/no.restplass/travel-search` | 2026-11-05T124900326596 -> 2026-11-05T150922137348 | 1 changed | quiet |
| 2026-11-05 | `remote/si.thinkhard/prompt-tools` | 2026-11-05T010654140958 -> 2026-11-05T150915768210 | 1 changed | quiet |
| 2026-11-05 | `remote/com.usepickly/pickly` | 2026-11-02T163750778411 -> 2026-11-05T150918312102 | 2 changed, 2 added (every tool) | quiet |
| 2026-11-05 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-05T010653700115 -> 2026-11-05T150911458732 | 1 added | quiet |
| 2026-11-05 | `remote/net.stabledomains/registrar` | 2026-11-05T010650521832 -> 2026-11-05T150837241530 | 4 changed | quiet |
| 2026-11-05 | `remote/dk.afbudsrejser/travel-search` | 2026-11-05T124855497166 -> 2026-11-05T150832223457 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-05T124818246143 -> 2026-11-05T150829021688 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.ohad6k/viberaven-guides` | 2026-11-05T124853267679 -> 2026-11-05T150808029469 | 7 changed (every tool) | quiet |
| 2026-11-05 | `remote/io.github.24seagull-beep/sense2-catalogue` | 2026-10-01T134308953218 -> 2026-11-05T150759842997 | 7 changed | quiet |
| 2026-11-05 | `remote/com.kindoflost.staff-scheduling/shift-scheduler` | 2026-10-25T102810730737 -> 2026-11-05T150754501776 | 1 changed | quiet |
| 2026-11-05 | `remote/com.skateboardpersonalizado/skateboard-deck` | 2026-10-29T133258713146 -> 2026-11-05T150728864127 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.roman-rr/trading-signals` | 2026-11-05T124817432163 -> 2026-11-05T150723738766 | 1 changed | quiet |
| 2026-11-05 | `remote/dev.workers.sebastiaan-ba3.signals/tools` | 2026-10-19T135047632007 -> 2026-11-05T150722528903 | 1 changed | quiet |
| 2026-11-05 | `remote/video.refs/refs` | 2026-11-04T200722792218 -> 2026-11-05T150722196480 | 1 changed | quiet |
| 2026-11-05 | `remote/gg.pixly/mcp` | 2026-11-04T200739947437 -> 2026-11-05T150651340776 | 4 changed | quiet |
| 2026-11-05 | `remote/com.postalform/postalform` | 2026-10-17T055359556090 -> 2026-11-05T150649106733 | 6 changed | quiet |
| 2026-11-05 | `remote/now.salesjobs/mcp` | 2026-11-04T200737716904 -> 2026-11-05T150649902317 | 1 changed | quiet |
| 2026-11-05 | `remote/com.supapark/agent-api` | 2026-11-04T150442399960 -> 2026-11-05T150642567133 | 1 changed | quiet |
| 2026-11-05 | `remote/com.kindoflost.routing/fleet-route-optimizer` | 2026-10-25T102723516168 -> 2026-11-05T150640164386 | 1 changed | quiet |
| 2026-11-05 | `remote/dev.workers.sebastiaan-ba3.payverify/tools` | 2026-10-19T135159063904 -> 2026-11-05T150639356302 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-05T124847075111 -> 2026-11-05T150635491236 | 1 changed, 1 removed | quiet |
| 2026-11-05 | `remote/com.representments/chargebacks` | 2026-11-02T163458447563 -> 2026-11-05T150629658502 | 1 changed | quiet |
| 2026-11-05 | `remote/com.pagetovid/pagetovid` | 2026-11-04T150105441763 -> 2026-11-05T150622075024 | 3 changed | quiet |
| 2026-11-05 | `remote/io.github.89rat/code402` | 2026-10-18T185952261530 -> 2026-11-05T150614936180 | 1 changed | quiet |
| 2026-11-05 | `remote/ca.movahedi/privacy` | 2026-11-04T200725604930 -> 2026-11-05T150546792070 | 1 changed | quiet |
| 2026-11-05 | `remote/com.googleapis.monitoring/mcp` | 2026-11-05T124806485925 -> 2026-11-05T150543537294 | 5 changed | quiet |
| 2026-11-05 | `remote/io.github.makar52nn-crypto/x402-money-reactor` | 2026-11-05T115050378310 -> 2026-11-05T150543157927 | 32 changed | review |
| 2026-11-05 | `remote/io.github.makar-aibot/money-reactor-mcp` | 2026-11-05T115050680857 -> 2026-11-05T150543346735 | 32 changed | review |
| 2026-11-05 | `remote/app.merron/ai-act-check` | 2026-11-04T145958036428 -> 2026-11-05T150521361350 | 4 changed (every tool) | quiet |
| 2026-11-05 | `remote/app.mcpharbor/mcp-harbor-search` | 2026-10-19T135035719889 -> 2026-11-05T150517456847 | 2 changed, 4 added (every tool) | quiet |
| 2026-11-05 | `remote/re.rundata/temps-reel` | 2026-11-05T115341395402 -> 2026-11-05T150516372521 | 1 changed | quiet |
| 2026-11-05 | `remote/com.psychologieetserenite/catalogue` | 2026-10-30T132633577566 -> 2026-11-05T150436811296 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.Fizzl13/presign-guard` | 2026-11-04T005923467178 -> 2026-11-05T150429080418 | 6 changed | quiet |
| 2026-11-05 | `remote/net.mostexpensivewatches/mcp` | 2026-10-22T105540897422 -> 2026-11-05T150422316450 | 10 changed (every tool) | quiet |
| 2026-11-05 | `remote/io.github.precis-finance/precis-finance-mcp` | 2026-10-17T055509479590 -> 2026-11-05T150414650922 | 2 changed | quiet |
| 2026-11-05 | `remote/com.merarobotics/mera` | 2026-11-02T163217873979 -> 2026-11-05T150405130330 | 3 changed | quiet |
| 2026-11-05 | `remote/cloud.redu/mcp` | 2026-11-05T114810658074 -> 2026-11-05T150400778701 | 104 changed, 1 added | quiet |
| 2026-11-05 | `remote/gl.parse/mcp` | 2026-11-05T124808952672 -> 2026-11-05T150347778418 | 1 changed | quiet |
| 2026-11-05 | `remote/org.walkably/walkably` | 2026-11-05T114812403542 -> 2026-11-05T150336730776 | 2 changed | quiet |
| 2026-11-05 | `remote/dev.workers.makar52nn2016.money-reactor/x402-money-reactor` | 2026-11-05T115115531040 -> 2026-11-05T150315720891 | 32 changed | review |
| 2026-11-05 | `remote/io.github.nevermined-io/catalog` | 2026-11-04T145755120685 -> 2026-11-05T150312545362 | 8 changed | quiet |
| 2026-11-05 | `remote/io.github.GrayWolf8-creator/gw8-signal-api` | 2026-10-28T132907776168 -> 2026-11-05T150306214536 | 1 changed | quiet |
| 2026-11-05 | `remote/com.jointextkit/textkit` | 2026-11-03T024213818829 -> 2026-11-05T150300591112 | 4 changed | quiet |
| 2026-11-05 | `remote/ai.securelend/lender` | 2026-11-05T114737515067 -> 2026-11-05T150257000295 | 1 changed, 2 added | quiet |
| 2026-11-05 | `remote/com.zobrx/zobrx` | 2026-09-23T162831110803 -> 2026-11-05T150255238280 | 7 added | quiet |
| 2026-11-05 | `remote/com.hustlegotreal/mcp` | 2026-11-03T122613666480 -> 2026-11-05T150254436861 | 7 added | quiet |
| 2026-11-05 | `remote/com.quanttogo/quanttogo-mcp` | 2026-10-26T133051632523 -> 2026-11-05T150242286363 | 4 changed, 4 added | quiet |
| 2026-11-05 | `remote/nl.theseo/theseo-mcp` | 2026-11-05T010632015359 -> 2026-11-05T150234622649 | 2 changed | quiet |
| 2026-11-05 | `remote/com.oneuedu.mcp/oneu-education` | 2026-11-04T123719727093 -> 2026-11-05T150221270736 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.thechancerylaneproject/tclp-mcp` | 2026-10-21T121541060529 -> 2026-11-05T150204638017 | 4 changed | quiet |
| 2026-11-05 | `remote/eu.paymentslaw/legislation` | 2026-11-03T144337129353 -> 2026-11-05T150159457229 | 2 changed | quiet |
| 2026-11-05 | `remote/com.clawhard/studio` | 2026-11-04T145645751323 -> 2026-11-05T150157386338 | 2 added | quiet |
| 2026-11-05 | `remote/com.bikefuchs/bikefuchs` | 2026-10-25T102028924914 -> 2026-11-05T150155794070 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 48304 substantive, 29136 that changed only numbers (a catalogue counter ticking, a date), 846 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 43271 | 15883 | 27388 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1485 | 1485 | 0 | 0 |
| `caseyjhand.com` | 354 | 354 | 0 | 0 |
| `sistaminuten.se` | 199 | 6 | 0 | 193 |
| `afbudsrejser.dk` | 198 | 6 | 0 | 192 |
| `akkilahdot.fi` | 198 | 6 | 0 | 192 |
| `restplass.no` | 198 | 6 | 0 | 192 |
| `socialloop.ai` | 191 | 191 | 0 | 0 |
| `remoshift.com` | 165 | 14 | 151 | 0 |
| `openkrill.app` | 153 | 153 | 0 | 0 |
| `revmesh2074.workers.dev` | 153 | 135 | 18 | 0 |
| 7673 other operators | 29380 | 27724 | 1579 | 77 |
