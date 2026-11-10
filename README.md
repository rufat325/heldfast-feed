# MCP server tool changes

Last change observed 2026-11-10T13:04:32+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

85215 changes to a tool definition: 3727 npm releases (3481 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 81488 readings of hosted servers that found their tools changed; 3681 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-10 | `remote/today.thekorean/news` | 2026-11-09T170356792630 -> 2026-11-10T130434549388 | 2 added | quiet |
| 2026-11-10 | `remote/design.overflow/mcp` | 2026-11-10T030051073892 -> 2026-11-10T130432443457 | 1 changed | quiet |
| 2026-11-10 | `remote/com.jokestack/jokestack` | 2026-11-09T170318094593 -> 2026-11-10T130428909668 | 1 changed | quiet |
| 2026-11-10 | `remote/studio.gradients/mcp` | 2026-11-10T030040923668 -> 2026-11-10T130428255568 | 1 changed | quiet |
| 2026-11-10 | `remote/com.x402serps/search` | 2026-11-09T170439965856 -> 2026-11-10T130423646194 | 1 changed | quiet |
| 2026-11-10 | `remote/no.restplass/travel-search` | 2026-11-10T030033964889 -> 2026-11-10T130421487590 | 1 changed | quiet |
| 2026-11-10 | `remote/fi.akkilahdot/travel-search` | 2026-11-10T030032420952 -> 2026-11-10T130421219703 | 1 changed | quiet |
| 2026-11-10 | `remote/cn.com.bioinformatics/weishengxin` | 2026-11-10T030036349295 -> 2026-11-10T130425541423 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.privatelawattorneys/wiki-private-law` | 2026-11-09T071633474221 -> 2026-11-10T130421316871 | 4 changed | quiet |
| 2026-11-10 | `remote/io.github.oon4am-eng/hold` | 2026-11-09T170223166715 -> 2026-11-10T130419961606 | 1 changed | quiet |
| 2026-11-10 | `remote/ai.mosaya/practice` | 2026-11-09T170402905159 -> 2026-11-10T130421708732 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-10T030031181576 -> 2026-11-10T130421562168 | 16 added | review |
| 2026-11-10 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-10T030032913075 -> 2026-11-10T130418880142 | 3 changed | quiet |
| 2026-11-10 | `remote/se.sistaminuten/travel-search` | 2026-11-10T030050026046 -> 2026-11-10T130416153981 | 1 changed | quiet |
| 2026-11-10 | `remote/top.qiaiwan.www/douparse` | 2026-11-09T170257325031 -> 2026-11-10T130418892712 | 1 changed | quiet |
| 2026-11-10 | `remote/nl.prijsprofeet/prijsprofeet-de` | 2026-11-09T170255220847 -> 2026-11-10T130416269824 | 2 changed (every tool) | quiet |
| 2026-11-10 | `remote/dk.afbudsrejser/travel-search` | 2026-11-10T030026291133 -> 2026-11-10T130415129365 | 1 changed | quiet |
| 2026-11-10 | `remote/sk.nakus/unit-price` | 2026-11-09T170247455180 -> 2026-11-10T130414273501 | 4 changed, 2 added (every tool) | quiet |
| 2026-11-10 | `remote/io.github.andzar22/offstereo` | 2026-11-10T030047531634 -> 2026-11-10T130414212901 | 1 changed | quiet |
| 2026-11-10 | `remote/com.onlyworlds/mcp` | 2026-11-10T030048614964 -> 2026-11-10T130414819496 | 1 changed | quiet |
| 2026-11-10 | `remote/com.163yu/hetianyu` | 2026-11-09T170323719752 -> 2026-11-10T130416898761 | 9 changed, 2 added (every tool) | quiet |
| 2026-11-10 | `remote/io.github.NBrangerF/kebiao` | 2026-11-09T170240916514 -> 2026-11-10T130412954636 | 2 changed | quiet |
| 2026-11-10 | `remote/ai.peerfoundry/typedpull` | 2026-11-09T191532748324 -> 2026-11-10T130413256203 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.gokaytr/geoniks.1` | 2026-11-09T170236436904 -> 2026-11-10T130411740709 | 1 changed | quiet |
| 2026-11-10 | `remote/com.veritaset/mcp` | 2026-11-09T191532781301 -> 2026-11-10T130411236485 | 1 changed | quiet |
| 2026-11-10 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-09T191530250783 -> 2026-11-10T130411735402 | 2 changed | quiet |
| 2026-11-10 | `remote/com.theagentsindex/mcp` | 2026-11-08T153904627917 -> 2026-11-10T130410668078 | 1 removed | quiet |
| 2026-11-10 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-10T030021889697 -> 2026-11-10T130410028278 | 1 changed | quiet |
| 2026-11-10 | `remote/dev.tanod/x402-check` | 2026-11-09T170050014784 -> 2026-11-10T130413427290 | 1 changed | quiet |
| 2026-11-10 | `remote/global.uain/network` | 2026-11-10T030019857301 -> 2026-11-10T130407567052 | 7 changed | quiet |
| 2026-11-10 | `remote/com.trackerhacker/mcp` | 2026-11-10T030018571065 -> 2026-11-10T130406374614 | 35 changed, 4 added, 9 removed | quiet |
| 2026-11-10 | `remote/com.reevol.source/supplier-search` | 2026-11-08T135522897814 -> 2026-11-10T130405372314 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-10T030012452861 -> 2026-11-10T130405010549 | 1 changed | quiet |
| 2026-11-10 | `remote/com.thekoreantoday/news` | 2026-11-09T170011549235 -> 2026-11-10T130404862564 | 2 added | quiet |
| 2026-11-10 | `remote/com.tbmlib/mcp` | 2026-11-09T170135517011 -> 2026-11-10T130402105233 | 1 changed, 3 added | quiet |
| 2026-11-10 | `remote/com.forevenza.services/tendmark` | 2026-11-10T030016495437 -> 2026-11-10T130402722570 | 1 changed | quiet |
| 2026-11-10 | `remote/com.tangerineindex/tangerine-index` | 2026-11-09T191522671255 -> 2026-11-10T130401297051 | 1 added | quiet |
| 2026-11-10 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-09T170114381857 -> 2026-11-10T130401582529 | 1 removed | quiet |
| 2026-11-10 | `remote/com.kyde/score` | 2026-11-10T030007193281 -> 2026-11-10T130400330459 | 1 changed | quiet |
| 2026-11-10 | `remote/com.forevenza.services/stillleaf` | 2026-11-10T030014758158 -> 2026-11-10T130400404751 | 1 changed | quiet |
| 2026-11-10 | `remote/xyz.x402helper/mcp` | 2026-11-09T170228671875 -> 2026-11-10T130358888157 | 3 changed | quiet |
| 2026-11-10 | `remote/dev.moneytools/tools` | 2026-11-10T030033010006 -> 2026-11-10T130357661790 | 8 changed, 13 removed | quiet |
| 2026-11-10 | `remote/com.robodebut/submissions` | 2026-11-09T165915401033 -> 2026-11-10T130357802845 | 1 changed, 1 added | quiet |
| 2026-11-10 | `remote/ai.rinda.tradegraph/tradegraph` | 2026-11-09T170056033419 -> 2026-11-10T130359631697 | 1 changed | quiet |
| 2026-11-10 | `remote/dev.workers.moneytools.x402-pay-precheck/pay-precheck` | 2026-11-10T030037634010 -> 2026-11-10T130357484165 | 8 changed, 12 removed | quiet |
| 2026-11-10 | `remote/com.tickmarkbooks/mcp` | 2026-11-09T170039537183 -> 2026-11-10T130357486391 | 1 removed | quiet |
| 2026-11-10 | `remote/nl.prijsprofeet/prijsprofeet` | 2026-11-09T170153812386 -> 2026-11-10T130355041604 | 2 changed (every tool) | quiet |
| 2026-11-10 | `remote/nl.prijsprofeet/prijsprofeet-be` | 2026-11-09T170154222364 -> 2026-11-10T130354741517 | 2 changed (every tool) | quiet |
| 2026-11-10 | `remote/dev.tanod/tanod` | 2026-11-10T030029078775 -> 2026-11-10T130354212014 | 10 changed, 1 added | quiet |
| 2026-11-10 | `remote/dev.tanod/docs` | 2026-11-09T191449884284 -> 2026-11-10T130353858582 | 1 changed | quiet |
| 2026-11-10 | `remote/app.seatsherpa/rides` | 2026-11-09T170021410093 -> 2026-11-10T130353213667 | 5 changed | quiet |
| 2026-11-10 | `remote/com.forevenza.services/plumbline` | 2026-11-10T025959273196 -> 2026-11-10T130352098728 | 1 changed | quiet |
| 2026-11-10 | `remote/io.github.cryptoconspiracy/vurto-swap` | 2026-11-08T000113264734 -> 2026-11-10T130351624778 | 3 changed | quiet |
| 2026-11-10 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-10T030031382018 -> 2026-11-10T130351251207 | 2 changed | quiet |
| 2026-11-10 | `remote/fun.pumpdata/pumpdata` | 2026-11-09T191507348324 -> 2026-11-10T130347924117 | 1 added | quiet |
| 2026-11-10 | `remote/com.psychologieetserenite/catalogue` | 2026-11-08T204934700918 -> 2026-11-10T130348935341 | 1 changed | quiet |
| 2026-11-10 | `remote/com.idosgames/platform` | 2026-11-10T030023337505 -> 2026-11-10T130348473134 | 2 changed | quiet |
| 2026-11-10 | `remote/io.github.RafaCoelho33/web3-systemic-agent` | 2026-11-09T170045525053 -> 2026-11-10T130346776244 | 4 changed (every tool) | quiet |
| 2026-11-10 | `remote/com.probativegrowth/legal-marketing-data` | 2026-11-09T165912390885 -> 2026-11-10T130347380790 | 1 changed | quiet |
| 2026-11-10 | `remote/com.eventualclimate/premium-lock` | 2026-11-10T030001959539 -> 2026-11-10T130347675870 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 53039 substantive, 31247 that changed only numbers (a catalogue counter ticking, a date), 929 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 45146 | 15898 | 29248 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1843 | 1843 | 0 | 0 |
| `caseyjhand.com` | 359 | 359 | 0 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `civai.co` | 235 | 235 | 0 | 0 |
| `sistaminuten.se` | 218 | 6 | 0 | 212 |
| `afbudsrejser.dk` | 217 | 6 | 0 | 211 |
| `akkilahdot.fi` | 217 | 6 | 0 | 211 |
| `restplass.no` | 217 | 6 | 0 | 211 |
| `socialloop.ai` | 209 | 209 | 0 | 0 |
| `revmesh2074.workers.dev` | 201 | 178 | 23 | 0 |
| 8383 other operators | 33754 | 31694 | 1976 | 84 |
