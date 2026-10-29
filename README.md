# MCP server tool changes

Last change observed 2026-10-29T10:46:28+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

61389 changes to a tool definition: 2567 npm releases (2321 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 58822 readings of hosted servers that found their tools changed; 2958 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-29 | `remote/ai.yentaknows/directory` | 2026-10-26T133826127248 -> 2026-10-29T104631019630 | 2 changed | quiet |
| 2026-10-29 | `remote/io.github.Trusgent/trusgent-mcp` | 2026-10-17T060502421577 -> 2026-10-29T104620985139 | 2 changed, 1 added | quiet |
| 2026-10-29 | `remote/hr.svijet-beba/products` | 2026-10-17T060501090892 -> 2026-10-29T104619619856 | 1 changed | quiet |
| 2026-10-29 | `remote/no.restplass/travel-search` | 2026-10-29T063248080987 -> 2026-10-29T104612890901 | 1 changed | quiet |
| 2026-10-29 | `remote/com.faceabot/youtube` | 2026-10-26T133620275487 -> 2026-10-29T104609714727 | 1 changed, 1 added | quiet |
| 2026-10-29 | `remote/cn.com.xiaozhaobao/xiaozhaobao` | 2026-10-19T135619381160 -> 2026-10-29T104609306141 | 1 added | quiet |
| 2026-10-29 | `remote/io.github.Z4KARY/upgrowth-mcp` | 2026-10-27T054128296763 -> 2026-10-29T104603913119 | 1 changed | quiet |
| 2026-10-29 | `remote/com.tryspook/spook` | 2026-09-23T162956067878 -> 2026-10-29T104559511710 | 4 added | quiet |
| 2026-10-29 | `remote/com.juzpost/mcp` | 2026-10-22T052611203579 -> 2026-10-29T104601009586 | 1 changed | quiet |
| 2026-10-29 | `remote/com.orlandu/arcade` | 2026-10-24T050528614260 -> 2026-10-29T104546945271 | 1 added | quiet |
| 2026-10-29 | `remote/io.github.Licium-ai/licium` | 2026-10-23T233430174555 -> 2026-10-29T104540649545 | 105 changed, 14 added (every tool) | quiet |
| 2026-10-29 | `remote/fyi.barcelona-rent/mcp` | 2026-09-24T202612328167 -> 2026-10-29T104540253198 | 1 added | quiet |
| 2026-10-29 | `remote/studio.gradients/mcp` | 2026-10-29T063230249476 -> 2026-10-29T104536181313 | 1 changed | quiet |
| 2026-10-29 | `remote/dk.afbudsrejser/travel-search` | 2026-10-29T063241168584 -> 2026-10-29T104537170063 | 1 changed | quiet |
| 2026-10-29 | `remote/io.github.HillTan/tiktikluck` | 2026-10-23T120945001414 -> 2026-10-29T104528625322 | 3 changed, 4 added | quiet |
| 2026-10-29 | `remote/com.talentanvil/talentanvil` | 2026-10-17T055620312220 -> 2026-10-29T104526344706 | 8 changed (every tool) | quiet |
| 2026-10-29 | `remote/uk.co.wastecarriercheck/site` | 2026-10-06T110246708696 -> 2026-10-29T104524864306 | 1 changed | quiet |
| 2026-10-29 | `remote/io.github.zambodotdev/zambo` | 2026-10-25T225056559373 -> 2026-10-29T104524133360 | 4 changed | quiet |
| 2026-10-29 | `remote/dev.zambo/zambo` | 2026-10-25T225056675617 -> 2026-10-29T104524118900 | 4 changed | quiet |
| 2026-10-29 | `remote/se.sistaminuten/travel-search` | 2026-10-29T063229226386 -> 2026-10-29T104522254419 | 1 changed | quiet |
| 2026-10-29 | `remote/io.github.Fizzl13/x402-doctor` | 2026-10-25T225056704548 -> 2026-10-29T104517948739 | 13 changed (every tool) | quiet |
| 2026-10-29 | `remote/com.vidreno/mcp` | 2026-10-28T133347569306 -> 2026-10-29T104517509719 | 1 changed | quiet |
| 2026-10-29 | `remote/io.github.danbuildss/musecourt` | 2026-10-28T153325379403 -> 2026-10-29T104512487207 | 2 changed, 5 added | quiet |
| 2026-10-29 | `remote/com.menloinsurance/mcp` | 2026-10-24T050516728422 -> 2026-10-29T104510777526 | 3 changed | quiet |
| 2026-10-29 | `remote/cn.tandiu/data` | 2026-10-19T135258429171 -> 2026-10-29T104512472991 | 1 changed, 2 added | quiet |
| 2026-10-29 | `remote/sh.stipple/openwarrant` | 2026-10-08T135505006621 -> 2026-10-29T104509195326 | 11 removed | quiet |
| 2026-10-29 | `remote/fi.akkilahdot/travel-search` | 2026-10-29T063228030297 -> 2026-10-29T104505848745 | 1 changed | quiet |
| 2026-10-29 | `remote/com.quailos/quailos` | 2026-10-29T063235053570 -> 2026-10-29T104501746863 | 1 added | quiet |
| 2026-10-29 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-10-19T135523884028 -> 2026-10-29T104500933117 | 1 changed | quiet |
| 2026-10-29 | `remote/com.eatmundo/dishes` | 2026-10-07T001239224720 -> 2026-10-29T104458931747 | 1 changed | quiet |
| 2026-10-29 | `remote/com.digitaltableteur/mcp` | 2026-10-17T070455670647 -> 2026-10-29T104457722013 | 2 changed | quiet |
| 2026-10-29 | `remote/com.coveragecat/insurance` | 2026-10-21T052324024334 -> 2026-10-29T104456974534 | 1 changed | quiet |
| 2026-10-29 | `remote/ai.trydock/dock` | 2026-10-28T062214054907 -> 2026-10-29T104456221100 | 2 changed | quiet |
| 2026-10-29 | `remote/com.myhuiban.www/conference-partner` | 2026-09-28T073215750472 -> 2026-10-29T104455574134 | 3 changed | quiet |
| 2026-10-29 | `remote/io.soundchain/agents` | 2026-10-24T113001784298 -> 2026-10-29T104451309770 | 1 added | quiet |
| 2026-10-29 | `remote/com.artbooksociety/public-catalog` | 2026-10-23T120915352871 -> 2026-10-29T104451529625 | 5 changed (every tool) | quiet |
| 2026-10-29 | `remote/io.github.tidytools/tidytools-free` | 2026-10-27T112412897844 -> 2026-10-29T104449222239 | 31 changed | quiet |
| 2026-10-29 | `remote/io.github.Nadeus/toolradar` | 2026-10-26T133626946336 -> 2026-10-29T104450052674 | 1 changed | quiet |
| 2026-10-29 | `remote/com.ex2/catalogue` | 2026-10-17T070615521897 -> 2026-10-29T104443408160 | 1 added | quiet |
| 2026-10-29 | `remote/net.tipmaster/consensus` | 2026-10-25T102428028592 -> 2026-10-29T104443022802 | 1 added | quiet |
| 2026-10-29 | `remote/ai.whatsupin/events` | 2026-10-24T112855065837 -> 2026-10-29T104438892005 | 5 changed | quiet |
| 2026-10-29 | `remote/io.github.MohDev212/verifypulse` | 2026-10-24T190430740890 -> 2026-10-29T104435576653 | 1 changed, 1 added | review |
| 2026-10-29 | `remote/io.theagentforge/forge` | 2026-10-26T211516552452 -> 2026-10-29T104435337209 | 6 changed (every tool) | quiet |
| 2026-10-29 | `remote/ru.vedarai/mcp` | 2026-10-23T200851247773 -> 2026-10-29T104434466766 | 6 changed | quiet |
| 2026-10-29 | `remote/io.github.vlad-public-code/valem` | 2026-10-28T212416908578 -> 2026-10-29T104430765632 | 2 added | quiet |
| 2026-10-29 | `remote/com.voyagehacks/travel` | 2026-10-25T102434189287 -> 2026-10-29T104427406895 | 1 changed | quiet |
| 2026-10-29 | `remote/io.viseon/semantic-intelligence` | 2026-10-17T055534327059 -> 2026-10-29T104426376158 | 1 changed | quiet |
| 2026-10-29 | `remote/dev.workers.shopttyass-85f.upgrade-brief/upgrade-brief` | 2026-10-26T133427401620 -> 2026-10-29T104426798170 | 4 added | quiet |
| 2026-10-29 | `remote/io.github.paulieb89/uk-due-diligence-mcp` | 2026-10-25T225057815179 -> 2026-10-29T104423602822 | 1 changed | quiet |
| 2026-10-29 | `remote/io.github.donniertf-hub/uk-ch-mcp` | 2026-10-17T055854101927 -> 2026-10-29T104424319677 | 2 added | quiet |
| 2026-10-29 | `remote/io.github.cyanheads/worms-marine-taxa-mcp-server` | 2026-10-26T133625498731 -> 2026-10-29T104423528469 | 2 changed | quiet |
| 2026-10-29 | `remote/dev.tanod/html-to-markdown` | 2026-10-19T135706294781 -> 2026-10-29T104423750975 | 1 changed | quiet |
| 2026-10-29 | `remote/com.varioroam/esim-catalog` | 2026-10-21T122252578717 -> 2026-10-29T104419576145 | 1 changed | quiet |
| 2026-10-29 | `remote/fr.synergieloc/immobilier` | 2026-10-29T063223991470 -> 2026-10-29T104419465667 | 2 added | quiet |
| 2026-10-29 | `remote/io.github.Schoasch/backtesting-arena` | 2026-10-28T133011211658 -> 2026-10-29T104414682504 | 5 changed | quiet |
| 2026-10-29 | `remote/xyz.urbangametheory/urban-game-theory` | 2026-10-28T062221130144 -> 2026-10-29T104415749922 | 20 changed | quiet |
| 2026-10-29 | `remote/io.github.boriskendev/stormap` | 2026-10-18T051510643620 -> 2026-10-29T104407381222 | 1 changed | quiet |
| 2026-10-29 | `remote/si.thinkhard/prompt-tools` | 2026-10-26T133403663019 -> 2026-10-29T104402600253 | 1 changed | quiet |
| 2026-10-29 | `remote/com.theopenapps/openapps` | 2026-10-28T212414905173 -> 2026-10-29T104400656071 | 9 changed | quiet |
| 2026-10-29 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-25T225139857717 -> 2026-10-29T104401066330 | 3 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 41140 substantive, 19540 that changed only numbers (a catalogue counter ticking, a date), 709 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 34063 | 15829 | 18234 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1126 | 1126 | 0 | 0 |
| `caseyjhand.com` | 267 | 267 | 0 | 0 |
| `sistaminuten.se` | 168 | 6 | 0 | 162 |
| `afbudsrejser.dk` | 167 | 6 | 0 | 161 |
| `akkilahdot.fi` | 167 | 6 | 0 | 161 |
| `restplass.no` | 167 | 6 | 0 | 161 |
| `socialloop.ai` | 161 | 161 | 0 | 0 |
| `remoshift.com` | 137 | 9 | 128 | 0 |
| `fundinglandscape.com` | 129 | 81 | 48 | 0 |
| `revmesh2074.workers.dev` | 129 | 116 | 13 | 0 |
| 6440 other operators | 22367 | 21186 | 1117 | 64 |
