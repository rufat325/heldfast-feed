# MCP server tool changes

Last change observed 2026-11-15T07:16:24+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

99490 changes to a tool definition: 4181 npm releases (3935 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 95309 readings of hosted servers that found their tools changed; 4129 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-15 | `remote/xyz.tereno/tereno` | 2026-11-14T183359042342 -> 2026-11-15T071625856915 | 1 changed | review |
| 2026-11-15 | `remote/se.sistaminuten/travel-search` | 2026-11-15T002331227209 -> 2026-11-15T071625331328 | 1 changed | quiet |
| 2026-11-15 | `remote/io.taifoon/coordination-layer.1` | 2026-11-14T114954627278 -> 2026-11-15T071625619316 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-15T002324599216 -> 2026-11-15T071624124802 | 3 changed | quiet |
| 2026-11-15 | `remote/com.kaicalls/kaicalls` | 2026-11-13T115956612515 -> 2026-11-15T071623768215 | 2 added | quiet |
| 2026-11-15 | `remote/com.ferntool/ip` | 2026-11-13T115947885719 -> 2026-11-15T071622866657 | 1 added | quiet |
| 2026-11-15 | `remote/io.suverse.versum/catalog` | 2026-11-15T002323540408 -> 2026-11-15T071622832850 | 3 changed | quiet |
| 2026-11-15 | `remote/co.truerent/rental-review` | 2026-11-13T115831000888 -> 2026-11-15T071620493591 | 2 changed | quiet |
| 2026-11-15 | `remote/com.lvl2player/sandbox` | 2026-11-13T115637084377 -> 2026-11-15T071616980758 | 2 changed | quiet |
| 2026-11-15 | `remote/com.sfxmint/sounds` | 2026-11-13T115651672053 -> 2026-11-15T071614563816 | 3 changed, 2 added | review |
| 2026-11-15 | `remote/studio.gradients/mcp` | 2026-11-15T002329769762 -> 2026-11-15T071614198809 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-14T010704283051 -> 2026-11-15T071612094856 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-15T002330899275 -> 2026-11-15T071616148510 | 16 added | quiet |
| 2026-11-15 | `remote/gg.plazmi/plazmi` | 2026-11-15T002317733795 -> 2026-11-15T071612742551 | 5 changed, 2 added | quiet |
| 2026-11-15 | `remote/fi.akkilahdot/travel-search` | 2026-11-15T002328386981 -> 2026-11-15T071612681601 | 1 changed | quiet |
| 2026-11-15 | `remote/co.seatac/rides` | 2026-11-13T115639948825 -> 2026-11-15T071611917316 | 4 changed | quiet |
| 2026-11-15 | `remote/cn.com.bioinformatics/weishengxin` | 2026-11-14T140150307378 -> 2026-11-15T071615791289 | 1 changed | quiet |
| 2026-11-15 | `remote/wiki.rust/rust-wiki` | 2026-11-14T135806402031 -> 2026-11-15T071612014009 | 3 changed, 9 added | quiet |
| 2026-11-15 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-15T002327067995 -> 2026-11-15T071611282445 | 3 changed | quiet |
| 2026-11-15 | `remote/app.lovable.release-ripple-roadmap/logpulse` | 2026-11-15T002317517309 -> 2026-11-15T071611183328 | 1 changed | quiet |
| 2026-11-15 | `remote/ru.vedarai/mcp` | 2026-11-15T002327683352 -> 2026-11-15T071612039015 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.Triodian/obligations-atlas` | 2026-11-14T114932492124 -> 2026-11-15T071611659795 | 3 changed | quiet |
| 2026-11-15 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-14T010659185965 -> 2026-11-15T071608953320 | 1 changed | quiet |
| 2026-11-15 | `remote/nl.nltaxcalculator/dutch-tax` | 2026-11-14T135627326006 -> 2026-11-15T071609293138 | 13 changed | quiet |
| 2026-11-15 | `remote/dev.pdfops/pdfops-mcp` | 2026-11-14T135649777105 -> 2026-11-15T071613859295 | 1 changed, 3 added | quiet |
| 2026-11-15 | `remote/io.github.jdhart81/taxcredit-engine` | 2026-11-14T114923829341 -> 2026-11-15T071606392537 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.jdhart81/regulatory-radar` | 2026-11-14T114923633792 -> 2026-11-15T071606103727 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.jdhart81/quantity-takeoff` | 2026-11-14T114923561182 -> 2026-11-15T071605867093 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-15T002321462313 -> 2026-11-15T071605574203 | 1 changed | quiet |
| 2026-11-15 | `remote/io.realuptime/mcp.1` | 2026-11-14T010618570022 -> 2026-11-15T071604135023 | 3 removed | quiet |
| 2026-11-15 | `remote/gl.parse/mcp` | 2026-11-15T002312791936 -> 2026-11-15T071606187055 | 1 changed | quiet |
| 2026-11-15 | `remote/com.seqbench/workbench` | 2026-11-14T010653678166 -> 2026-11-15T071602844838 | 6 changed | quiet |
| 2026-11-15 | `remote/com.tkawen/intelligence-gateway` | 2026-11-15T002307270536 -> 2026-11-15T071603618241 | 1 changed | quiet |
| 2026-11-15 | `remote/com.remoshift/jobs` | 2026-11-15T002318244196 -> 2026-11-15T071600353309 | 1 changed | quiet |
| 2026-11-15 | `remote/com.jojapi/sms-verify` | 2026-11-14T114919095718 -> 2026-11-15T071601288854 | 1 changed | quiet |
| 2026-11-15 | `remote/com.parkypass/parky` | 2026-11-13T145842072797 -> 2026-11-15T071558999105 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.grzesir/botspot-trading` | 2026-11-15T002306128623 -> 2026-11-15T071556921994 | 6 changed | quiet |
| 2026-11-15 | `remote/io.github.Damien829/aipaygen` | 2026-11-15T002305147339 -> 2026-11-15T071556446458 | 22 added | review |
| 2026-11-15 | `remote/com.neblla/neblla` | 2026-11-15T002313341188 -> 2026-11-15T071554399388 | 2 changed | quiet |
| 2026-11-15 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-15T002312952677 -> 2026-11-15T071554318545 | 3 changed, 2 removed | quiet |
| 2026-11-15 | `remote/net.fundz/fundz` | 2026-11-14T010613249623 -> 2026-11-15T071553885959 | 1 changed, 1 added | quiet |
| 2026-11-15 | `remote/com.multicinesortega/cartelera` | 2026-11-15T002313839464 -> 2026-11-15T071555069019 | 1 changed | quiet |
| 2026-11-15 | `remote/co.ainumbers/tools` | 2026-11-15T002258258610 -> 2026-11-15T071553748475 | 1 changed | quiet |
| 2026-11-15 | `remote/com.waypointrecruit.jobs/healthcare-jobs` | 2026-11-14T114909946394 -> 2026-11-15T071552639913 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.jdhart81/ghg-ledger` | 2026-11-14T114954697228 -> 2026-11-15T071551222597 | 1 changed | quiet |
| 2026-11-15 | `remote/domains.unique/mcp-server` | 2026-11-14T114954090292 -> 2026-11-15T071550516344 | 14 changed | quiet |
| 2026-11-15 | `remote/io.github.financeratecalc/frc-mcp` | 2026-11-13T114751460366 -> 2026-11-15T071546864049 | 1 added | quiet |
| 2026-11-15 | `remote/io.github.Vortx-AI/emem` | 2026-11-13T114718315993 -> 2026-11-15T071545932159 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.lubobali/lubot` | 2026-11-14T010634346653 -> 2026-11-15T071544853694 | 8 changed | review |
| 2026-11-15 | `remote/io.github.liad142/yedapo` | 2026-11-14T010704760199 -> 2026-11-15T071545448492 | 2 changed (every tool) | quiet |
| 2026-11-15 | `remote/com.tabflows/site` | 2026-11-15T002355673357 -> 2026-11-15T071544867268 | 2 changed | quiet |
| 2026-11-15 | `remote/no.restplass/travel-search` | 2026-11-15T002354839166 -> 2026-11-15T071544593455 | 1 changed | quiet |
| 2026-11-15 | `remote/com.kulicadvisory/aictionbot-werkbank` | 2026-11-14T183357283108 -> 2026-11-15T071543882563 | 1 added | quiet |
| 2026-11-15 | `remote/com.draftkingsapi/server` | 2026-11-14T010559171243 -> 2026-11-15T071544404932 | 2 added | quiet |
| 2026-11-15 | `remote/dk.afbudsrejser/travel-search` | 2026-11-15T002353700007 -> 2026-11-15T071543643226 | 1 changed | quiet |
| 2026-11-15 | `remote/com.dcblueprint/data-centres` | 2026-11-15T002248799506 -> 2026-11-15T071544794906 | 2 changed | quiet |
| 2026-11-15 | `remote/com.algotrada.cubicle/cubicle` | 2026-11-15T002254019410 -> 2026-11-15T071544329603 | 8 added | quiet |
| 2026-11-15 | `remote/io.github.daniel3303/equibles` | 2026-11-15T002305678323 -> 2026-11-15T071542946827 | 6 changed | quiet |
| 2026-11-15 | `remote/dev.taifoon.coord/text-digest-1170141` | 2026-11-14T114857535941 -> 2026-11-15T071550912925 | 1 changed | quiet |
| 2026-11-15 | `remote/com.trackerhacker/mcp` | 2026-11-14T183350311556 -> 2026-11-15T071541327962 | 8 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 61402 substantive, 37066 that changed only numbers (a catalogue counter ticking, a date), 1022 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 52535 | 17771 | 34764 | 0 |
| `a2awire.com` | 2508 | 2508 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 420 | 420 | 0 | 0 |
| `civai.co` | 318 | 318 | 0 | 0 |
| `revmesh2074.workers.dev` | 262 | 229 | 33 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `sistaminuten.se` | 238 | 6 | 0 | 232 |
| `afbudsrejser.dk` | 237 | 6 | 0 | 231 |
| `akkilahdot.fi` | 237 | 6 | 0 | 231 |
| `restplass.no` | 237 | 6 | 0 | 231 |
| `socialloop.ai` | 229 | 229 | 0 | 0 |
| 9380 other operators | 39670 | 37304 | 2269 | 97 |
