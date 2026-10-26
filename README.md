# MCP server tool changes

Last change observed 2026-10-26T15:32:43+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

52646 changes to a tool definition: 2293 npm releases (2047 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 50353 readings of hosted servers that found their tools changed; 2744 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-26 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-10-26T052306408170 -> 2026-10-26T153244109291 | 2 changed | review |
| 2026-10-26 | `remote/no.restplass/travel-search` | 2026-10-26T133803916694 -> 2026-10-26T153243347445 | 1 changed | quiet |
| 2026-10-26 | `remote/dk.afbudsrejser/travel-search` | 2026-10-26T133725826284 -> 2026-10-26T153238270084 | 1 changed | quiet |
| 2026-10-26 | `remote/io.github.a1476/verateca` | 2026-10-26T133657809665 -> 2026-10-26T153234026426 | 1 changed | quiet |
| 2026-10-26 | `remote/fun.trnch/trnch` | 2026-10-26T133636010402 -> 2026-10-26T153231109281 | 1 changed | quiet |
| 2026-10-26 | `remote/com.trustbaselab/rcb-data` | 2026-10-26T133638014334 -> 2026-10-26T153232233748 | 1 added | quiet |
| 2026-10-26 | `remote/com.naxytra/xytara-mcp-executor` | 2026-10-26T133745987950 -> 2026-10-26T153219349777 | 14 changed | review |
| 2026-10-26 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-10-26T052258184226 -> 2026-10-26T153218714246 | 2 changed | review |
| 2026-10-26 | `remote/se.sistaminuten/travel-search` | 2026-10-26T133911843790 -> 2026-10-26T153215955564 | 1 changed | quiet |
| 2026-10-26 | `remote/re.rundata/temps-reel` | 2026-10-26T133438905801 -> 2026-10-26T153214308231 | 5 changed | quiet |
| 2026-10-26 | `remote/shop.grokzilla/micro-pay.1` | 2026-10-24T190435819670 -> 2026-10-26T153210443754 | 4 added | quiet |
| 2026-10-26 | `remote/com.warminboxes/deliverability-tools` | 2026-10-26T133814617316 -> 2026-10-26T153208497841 | 1 added | quiet |
| 2026-10-26 | `remote/studio.gradients/mcp` | 2026-10-26T133533268991 -> 2026-10-26T153206162661 | 1 changed | quiet |
| 2026-10-26 | `remote/dev.workers.restockalarm.token-safety-mcp/token-safety` | 2026-10-26T133528427087 -> 2026-10-26T153206802661 | 1 changed, 1 removed | review |
| 2026-10-26 | `remote/com.codestringers/mcp` | 2026-10-26T133510983023 -> 2026-10-26T153204083365 | 6 changed | quiet |
| 2026-10-26 | `remote/fi.akkilahdot/travel-search` | 2026-10-26T133502154297 -> 2026-10-26T153202713583 | 1 changed | quiet |
| 2026-10-26 | `remote/co.civai.nova/google-sheets-agent` | 2026-10-26T133309540729 -> 2026-10-26T153159076806 | 2 added | quiet |
| 2026-10-26 | `remote/com.revampvacations/revamp` | 2026-10-26T133147215873 -> 2026-10-26T153152561787 | 1 changed | quiet |
| 2026-10-26 | `remote/online.sellular/sellular` | 2026-10-25T191836737264 -> 2026-10-26T153149519872 | 2 changed | quiet |
| 2026-10-26 | `remote/dev.rackrates/ledger` | 2026-10-26T133339790009 -> 2026-10-26T153151864621 | 4 changed | quiet |
| 2026-10-26 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-26T133324182890 -> 2026-10-26T153147111694 | 3 changed, 1 added | quiet |
| 2026-10-26 | `remote/io.github.canoydario847-cloud/privi-quantum` | 2026-10-26T133324818230 -> 2026-10-26T153146494488 | 3 added | quiet |
| 2026-10-26 | `remote/io.pitchboom/pitchboom` | 2026-10-26T133311873210 -> 2026-10-26T153144935600 | 2 changed | quiet |
| 2026-10-26 | `remote/io.github.TotesMagotes/mcp-server-auth` | 2026-10-26T133029469399 -> 2026-10-26T153142366362 | 3 changed | quiet |
| 2026-10-26 | `remote/io.github.aatharva16/dalalos` | 2026-10-26T133018002904 -> 2026-10-26T153142002442 | 62 changed (every tool) | quiet |
| 2026-10-26 | `remote/com.remoshift/jobs` | 2026-10-26T133232356669 -> 2026-10-26T153139704446 | 1 changed | quiet |
| 2026-10-26 | `remote/com.peerlace/peerlace` | 2026-10-25T102340715987 -> 2026-10-26T153133958392 | 3 changed | quiet |
| 2026-10-26 | `remote/pl.klyo/games` | 2026-10-26T052328311453 -> 2026-10-26T153134053262 | 1 changed | quiet |
| 2026-10-26 | `remote/co.civai.nova/google-docs-agent` | 2026-10-25T132401464612 -> 2026-10-26T153132497494 | 2 removed | quiet |
| 2026-10-26 | `remote/com.usespur/spur` | 2026-10-26T133127779848 -> 2026-10-26T153132283544 | 1 changed, 9 added | review |
| 2026-10-26 | `remote/com.squirrelscan/squirrelscan` | 2026-10-26T133114906200 -> 2026-10-26T153130418634 | 1 changed | quiet |
| 2026-10-26 | `remote/network.mercatura/mercatura` | 2026-10-26T133406191445 -> 2026-10-26T153127267655 | 6 added | quiet |
| 2026-10-26 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-10-25T052248947590 -> 2026-10-26T153126677240 | 1 added | quiet |
| 2026-10-26 | `remote/net.praegant/landhaus` | 2026-10-26T052252733215 -> 2026-10-26T153125221397 | 10 changed, 1 added (every tool) | quiet |
| 2026-10-26 | `remote/dev.spendctl/spendctl` | 2026-10-26T133313835653 -> 2026-10-26T153123843426 | 6 changed (every tool) | review |
| 2026-10-26 | `remote/com.trivago.mcp/mcp` | 2026-10-26T133022950770 -> 2026-10-26T153121969008 | 3 changed (every tool) | review |
| 2026-10-26 | `remote/za.co.theahg/ahg-archives` | 2026-10-26T133017707171 -> 2026-10-26T153123944533 | 3 changed | quiet |
| 2026-10-26 | `remote/pro.particle/particle-pro` | 2026-10-25T191824302670 -> 2026-10-26T153120214331 | 1 changed, 2 added | quiet |
| 2026-10-26 | `remote/ai.switchapp/switch` | 2026-10-26T052323586312 -> 2026-10-26T153120112277 | 2 added | quiet |
| 2026-10-26 | `remote/ai.neuralverge/neuralverge` | 2026-10-26T133231482965 -> 2026-10-26T153120938780 | 54 changed | quiet |
| 2026-10-26 | `remote/ai.letsship/ship` | 2026-10-24T112406002268 -> 2026-10-26T153119095406 | 1 changed | quiet |
| 2026-10-26 | `remote/ru.layero/layero` | 2026-10-26T132907313445 -> 2026-10-26T153117216566 | 1 changed | quiet |
| 2026-10-26 | `remote/io.github.Clipform/mcp-server` | 2026-10-25T102036300980 -> 2026-10-26T153109933575 | 3 changed | quiet |
| 2026-10-26 | `remote/fun.madeira/hiking-permits` | 2026-10-26T133001439218 -> 2026-10-26T153107258467 | 1 changed | quiet |
| 2026-10-26 | `remote/com.loppee/loppee` | 2026-10-25T102202144235 -> 2026-10-26T153107356213 | 4 changed | quiet |
| 2026-10-26 | `remote/io.github.qxxx5vyd77-byte/directors-lookbook` | 2026-10-26T052240782590 -> 2026-10-26T153106778167 | 1 changed | quiet |
| 2026-10-26 | `remote/dev.laudex/laudex` | 2026-10-26T132805809377 -> 2026-10-26T153103688888 | 1 changed | quiet |
| 2026-10-26 | `remote/com.kongreviews/kongreviews` | 2026-10-26T132758765350 -> 2026-10-26T153102640145 | 29 changed, 5 added (every tool) | quiet |
| 2026-10-26 | `remote/com.duoleads.keywords/keyword-search-volume-google-trends` | 2026-10-26T132755513562 -> 2026-10-26T153102577786 | 3 changed | quiet |
| 2026-10-26 | `remote/io.github.horizon-pulse/horizon-pulse` | 2026-10-24T190347302577 -> 2026-10-26T153057983411 | 1 changed | quiet |
| 2026-10-26 | `remote/shop.grokzilla/micro-pay` | 2026-10-24T190400800736 -> 2026-10-26T153056848389 | 4 added | quiet |
| 2026-10-26 | `remote/com.getpriorivo/website-check` | 2026-10-26T132526504154 -> 2026-10-26T153055395133 | 1 changed | quiet |
| 2026-10-26 | `remote/com.bkkradar/condos` | 2026-10-26T132317177729 -> 2026-10-26T153055807906 | 2 changed | quiet |
| 2026-10-26 | `remote/io.github.giuseppesocci-bot/kalicart-global` | 2026-10-25T132342180062 -> 2026-10-26T153055300253 | 1 changed | quiet |
| 2026-10-26 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-26T132529210672 -> 2026-10-26T153052535395 | 1 changed | quiet |
| 2026-10-26 | `remote/app.vercel.fork-for-agents/fork` | 2026-10-26T132402718347 -> 2026-10-26T153053150662 | 1 changed | quiet |
| 2026-10-26 | `remote/io.github.a0971025732-netizen/finch-agent-catalog` | 2026-10-26T132353670427 -> 2026-10-26T153050537828 | 1 added | quiet |
| 2026-10-26 | `remote/com.getcloseknit/close-knit` | 2026-10-26T132650990740 -> 2026-10-26T153051273134 | 24 changed (every tool) | quiet |
| 2026-10-26 | `remote/io.github.hermoso-ai/hermoso` | 2026-10-26T052225490049 -> 2026-10-26T153047354822 | 3 changed, 3 added | quiet |
| 2026-10-26 | `remote/io.github.HarleyCoops/workspace-alberta` | 2026-10-24T112007128344 -> 2026-10-26T153047411223 | 3 changed, 1 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 34480 substantive, 17506 that changed only numbers (a catalogue counter ticking, a date), 660 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 28526 | 12158 | 16368 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 891 | 891 | 0 | 0 |
| `caseyjhand.com` | 231 | 231 | 0 | 0 |
| `sistaminuten.se` | 156 | 4 | 0 | 152 |
| `afbudsrejser.dk` | 155 | 4 | 0 | 151 |
| `akkilahdot.fi` | 155 | 4 | 0 | 151 |
| `restplass.no` | 155 | 4 | 0 | 151 |
| `socialloop.ai` | 150 | 150 | 0 | 0 |
| `remoshift.com` | 125 | 8 | 117 | 0 |
| `fundinglandscape.com` | 120 | 77 | 43 | 0 |
| `openkrill.app` | 112 | 112 | 0 | 0 |
| 5797 other operators | 19529 | 18496 | 978 | 55 |
