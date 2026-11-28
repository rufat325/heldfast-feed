# MCP server tool changes

Last change observed 2026-11-28T16:06:41+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 18238 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 43073 hosted endpoints (read daily, and every four hours while they keep changing).

148715 changes to a tool definition: 5722 npm releases (5476 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 142993 readings of hosted servers that found their tools changed; 5303 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-28 | `remote/xyz.octio/octio` | 2026-11-27T091026087596 -> 2026-11-28T160642744662 | 1 changed | quiet |
| 2026-11-28 | `remote/studio.gradients/mcp` | 2026-11-28T150219884074 -> 2026-11-28T160623833217 | 1 changed | quiet |
| 2026-11-28 | `remote/no.restplass/travel-search` | 2026-11-28T150211272426 -> 2026-11-28T160612765491 | 1 changed | quiet |
| 2026-11-28 | `remote/fi.akkilahdot/travel-search` | 2026-11-28T150135040201 -> 2026-11-28T160550197227 | 1 changed | quiet |
| 2026-11-28 | `remote/com.visdenda/public` | 2026-11-28T150056092361 -> 2026-11-28T160516688924 | 1 added | quiet |
| 2026-11-28 | `remote/dk.afbudsrejser/travel-search` | 2026-11-28T150110367464 -> 2026-11-28T160513966557 | 1 changed | quiet |
| 2026-11-28 | `remote/com.visdenda/free` | 2026-11-28T083141116612 -> 2026-11-28T160443817174 | 1 added | quiet |
| 2026-11-28 | `remote/pro.telehealthnearme/telehealth-compare` | 2026-11-28T145923456593 -> 2026-11-28T160327948716 | 1 added | quiet |
| 2026-11-28 | `remote/se.sistaminuten/travel-search` | 2026-11-28T150027565023 -> 2026-11-28T160323350852 | 1 changed | quiet |
| 2026-11-28 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-28T083153314024 -> 2026-11-28T160309020818 | 1 changed | quiet |
| 2026-11-28 | `remote/work.agentexchange/us-macro-regime` | 2026-11-28T145854151672 -> 2026-11-28T160301726904 | 1 changed | review |
| 2026-11-28 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-28T083156232504 -> 2026-11-28T160258057100 | 1 changed | quiet |
| 2026-11-28 | `remote/io.github.TMcodingarc/bull-otc` | 2026-11-27T145050495523 -> 2026-11-28T160238230847 | 5 changed | quiet |
| 2026-11-28 | `remote/il.co.taseli/taseli.1` | 2026-11-28T150048199996 -> 2026-11-28T160237491556 | 1 changed | quiet |
| 2026-11-28 | `remote/app.svglab/svglab` | 2026-11-28T150036544542 -> 2026-11-28T160226189071 | 94 changed (every tool) | quiet |
| 2026-11-28 | `remote/com.wpformation/wordpress` | 2026-10-19T135434399161 -> 2026-11-28T160220823743 | 2 changed, 2 added | quiet |
| 2026-11-28 | `remote/co.sailrides/sail` | 2026-11-27T171243507597 -> 2026-11-28T160201063560 | 3 changed | quiet |
| 2026-11-28 | `remote/io.ringler/ringler` | 2026-11-22T104019441060 -> 2026-11-28T160142243153 | 2 added | quiet |
| 2026-11-28 | `remote/no.verako/verako` | 2026-11-28T083239445014 -> 2026-11-28T160139600167 | 4 changed | quiet |
| 2026-11-28 | `remote/io.github.wwwnlab/rest-area` | 2026-11-28T145717012006 -> 2026-11-28T160133138914 | 3 changed | quiet |
| 2026-11-28 | `remote/dev.tradestats/tradestats` | 2026-11-27T214242709529 -> 2026-11-28T160108063385 | 4 added | quiet |
| 2026-11-28 | `remote/xyz.proofofstock/proof-of-stock` | 2026-11-27T144938559614 -> 2026-11-28T160106545833 | 3 changed | quiet |
| 2026-11-28 | `remote/family.polypad/polypad` | 2026-11-28T145623403266 -> 2026-11-28T160035675340 | 5 added | quiet |
| 2026-11-28 | `remote/com.imagiolabs.www/imagio-relay` | 2026-11-28T145836825430 -> 2026-11-28T160019464494 | 42 changed | review |
| 2026-11-28 | `remote/com.osmanthagent/market` | 2026-11-27T214218866253 -> 2026-11-28T160012782583 | 14 changed | quiet |
| 2026-11-28 | `remote/io.github.adamgraymon/agent-finops-budget-spend-guard` | 2026-11-26T215959532126 -> 2026-11-28T155954590171 | 1 changed | quiet |
| 2026-11-28 | `remote/io.github.llm-9-to-5/nightshift-agent-tools` | 2026-11-28T145540477405 -> 2026-11-28T155938431604 | 1 added | quiet |
| 2026-11-28 | `remote/ca.movahedi/privacy` | 2026-11-27T144736907590 -> 2026-11-28T155921188293 | 1 changed | quiet |
| 2026-11-28 | `remote/co.neverapply/neverapply` | 2026-11-20T155555931114 -> 2026-11-28T155915070208 | 1 changed | quiet |
| 2026-11-28 | `remote/io.github.slavosckie/oskkee` | 2026-11-27T144703215704 -> 2026-11-28T155852726322 | 2 changed (every tool) | quiet |
| 2026-11-28 | `remote/pl.finwire/data` | 2026-11-28T083231035574 -> 2026-11-28T155842359802 | 1 changed, 1 added | quiet |
| 2026-11-28 | `remote/app.yomio/yomio-mcp` | 2026-10-17T110441612187 -> 2026-11-28T155825825433 | 15 changed, 13 added (every tool) | quiet |
| 2026-11-28 | `remote/il.co.taseli/taseli` | 2026-11-28T145430778559 -> 2026-11-28T155818023961 | 1 changed | quiet |
| 2026-11-28 | `remote/io.github.supplementscanner/scanner` | 2026-11-28T083139836025 -> 2026-11-28T155813501769 | 4 changed (every tool) | quiet |
| 2026-11-28 | `remote/io.outil/outil` | 2026-11-28T145442020900 -> 2026-11-28T155756940437 | 1 changed | quiet |
| 2026-11-28 | `remote/com.siilostomy/store` | 2026-11-27T144339356928 -> 2026-11-28T155740934235 | 1 changed | quiet |
| 2026-11-28 | `remote/io.github.coret/openarchieven-mcp-server` | 2026-11-28T145330945748 -> 2026-11-28T155720614971 | 6 changed, 1 removed | quiet |
| 2026-11-28 | `remote/io.github.ocean1547-ui/nspros-mcp-gateway` | 2026-11-28T083136001904 -> 2026-11-28T155711135481 | 1 changed | quiet |
| 2026-11-28 | `remote/io.mediawork/mediawork` | 2026-11-25T150247210903 -> 2026-11-28T155655828156 | 2 changed | quiet |
| 2026-11-28 | `remote/nl.supplementenscanner/scanner` | 2026-11-28T083132815907 -> 2026-11-28T155654584854 | 4 changed (every tool) | quiet |
| 2026-11-28 | `remote/be.vibedeploy/vibedeploy` | 2026-11-26T004508495505 -> 2026-11-28T155629760537 | 2 changed | quiet |
| 2026-11-28 | `remote/co.deadbrands/arena` | 2026-11-28T145128674746 -> 2026-11-28T155526585819 | 1 changed | quiet |
| 2026-11-28 | `remote/dk.cvrradar/cvrradar` | 2026-11-28T145128266616 -> 2026-11-28T155525591826 | 1 changed | quiet |
| 2026-11-28 | `remote/com.appraisily/mcp` | 2026-11-26T172000403454 -> 2026-11-28T155449534098 | 2 added | review |
| 2026-11-28 | `remote/com.locktrip/hotels` | 2026-11-09T165234418617 -> 2026-11-28T155349582045 | 1 changed | quiet |
| 2026-11-28 | `remote/io.github.akihidem/kuchiyose` | 2026-11-28T083108260078 -> 2026-11-28T155324456451 | 1 changed | quiet |
| 2026-11-28 | `remote/io.github.akihidem/japan-hands` | 2026-11-28T144839681212 -> 2026-11-28T155253196191 | 1 changed | quiet |
| 2026-11-28 | `remote/markets.iamai/marketplace` | 2026-11-28T144834736302 -> 2026-11-28T155245626709 | 2 changed | quiet |
| 2026-11-28 | `remote/ai.llpro/campus` | 2026-11-28T145007841029 -> 2026-11-28T155225349519 | 2 changed | quiet |
| 2026-11-28 | `remote/io.github.PascalSun/agenticgeomate` | 2026-11-28T144731050423 -> 2026-11-28T155142397227 | 22 added | quiet |
| 2026-11-28 | `remote/app.vercel.fork-for-agents/fork` | 2026-11-28T144556052124 -> 2026-11-28T155049872771 | 1 changed | quiet |
| 2026-11-28 | `remote/co.golfdata/golfdata` | 2026-11-27T143835477024 -> 2026-11-28T155044246531 | 1 changed | quiet |
| 2026-11-28 | `remote/io.github.akihidem/hands-for-agents` | 2026-11-28T144818218483 -> 2026-11-28T155036006690 | 1 changed | quiet |
| 2026-11-28 | `remote/com.datamembership/uk-consumer-data` | 2026-11-24T163900908997 -> 2026-11-28T154928862278 | 1 changed | quiet |
| 2026-11-28 | `remote/ai.llpro.countersign/countersign` | 2026-11-28T144327482766 -> 2026-11-28T154902523864 | 1 changed | quiet |
| 2026-11-28 | `remote/io.github.thiagopatzdorf/fichario` | 2026-11-27T214130589466 -> 2026-11-28T154829607254 | 1 changed, 1 added | review |
| 2026-11-28 | `remote/com.cheapnypublication/ny-llc` | 2026-10-28T131517282090 -> 2026-11-28T154822975748 | 1 changed | quiet |
| 2026-11-28 | `remote/app.countlink/countdown` | 2026-10-27T122943982607 -> 2026-11-28T154747155314 | 1 changed | quiet |
| 2026-11-28 | `remote/io.forthclear/liquidation` | 2026-11-28T144048464842 -> 2026-11-28T154642086986 | 2 changed | quiet |
| 2026-11-28 | `remote/com.senpinai/ask-japan-hub` | 2026-11-28T144156797353 -> 2026-11-28T154636278670 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 100197 substantive, 47249 that changed only numbers (a catalogue counter ticking, a date), 1269 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 82353 | 38412 | 43941 | 0 |
| `a2awire.com` | 4371 | 4371 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 571 | 571 | 0 | 0 |
| `modevc.com` | 568 | 568 | 0 | 0 |
| `civai.co` | 403 | 403 | 0 | 0 |
| `revmesh2074.workers.dev` | 381 | 321 | 60 | 0 |
| `sistaminuten.se` | 295 | 7 | 0 | 288 |
| `afbudsrejser.dk` | 294 | 7 | 0 | 287 |
| `akkilahdot.fi` | 294 | 7 | 0 | 287 |
| `restplass.no` | 294 | 7 | 0 | 287 |
| `socialloop.ai` | 284 | 284 | 0 | 0 |
| 11973 other operators | 56266 | 52898 | 3248 | 120 |
