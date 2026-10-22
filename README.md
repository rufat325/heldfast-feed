# MCP server tool changes

Last change observed 2026-10-22T11:03:27+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

42415 changes to a tool definition: 1835 npm releases (1589 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 40580 readings of hosted servers that found their tools changed; 2368 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-22 | `remote/ai.yentaknows/directory` | 2026-10-08T135555224261 -> 2026-10-22T110329479888 | 5 changed, 1 added | quiet |
| 2026-10-22 | `remote/eu.voxs/voxhouses-pt` | 2026-09-23T163149615015 -> 2026-10-22T110322459741 | 2 changed | quiet |
| 2026-10-22 | `remote/com.starcovery/mcp` | 2026-10-20T104302629157 -> 2026-10-22T110314239427 | 1 changed | quiet |
| 2026-10-22 | `remote/no.restplass/travel-search` | 2026-10-22T052611944512 -> 2026-10-22T110310338916 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.cryptoduke01/gloam` | 2026-10-17T060441228212 -> 2026-10-22T110254033011 | 5 changed | quiet |
| 2026-10-22 | `remote/dk.afbudsrejser/travel-search` | 2026-10-22T052610775589 -> 2026-10-22T110231136266 | 1 changed | quiet |
| 2026-10-22 | `remote/com.veritaset/mcp` | 2026-10-21T202553147535 -> 2026-10-22T110206284820 | 1 changed, 1 added | quiet |
| 2026-10-22 | `remote/is.envelop.unisafe/insight` | 2026-10-21T122054747197 -> 2026-10-22T110157781325 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.gmahar82-stack/trust-check` | 2026-10-17T060352446664 -> 2026-10-22T110149491525 | 1 added | review |
| 2026-10-22 | `remote/app.openkrill/travel` | 2026-10-17T060351364528 -> 2026-10-22T110145971280 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.tradingale/mcp` | 2026-09-23T163050389802 -> 2026-10-22T110144587333 | 4 changed | quiet |
| 2026-10-22 | `remote/io.github.portneymk/stochastic-parrot` | 2026-10-04T055018426249 -> 2026-10-22T110130038424 | 1 added, 4 removed | quiet |
| 2026-10-22 | `remote/com.supercatch/supercatch` | 2026-10-06T110159696053 -> 2026-10-22T110103292570 | 1 changed, 2 added | quiet |
| 2026-10-22 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-21T141130461901 -> 2026-10-22T110047811084 | 10 changed | quiet |
| 2026-10-22 | `remote/com.cliniatlas/evidence` | 2026-10-06T110218942782 -> 2026-10-22T110048385003 | 2 changed | quiet |
| 2026-10-22 | `remote/ai.usedby/usedby` | 2026-10-17T055623158916 -> 2026-10-22T110046247145 | 2 changed | quiet |
| 2026-10-22 | `remote/design.overflow/mcp` | 2026-10-18T113318722948 -> 2026-10-22T110020192737 | 1 changed | quiet |
| 2026-10-22 | `remote/se.sistaminuten/travel-search` | 2026-10-22T052603386360 -> 2026-10-22T110015935699 | 1 changed | quiet |
| 2026-10-22 | `remote/app.openkrill/send-out` | 2026-10-17T060254291525 -> 2026-10-22T110017077721 | 1 added | quiet |
| 2026-10-22 | `remote/com.immersivecommons/floor10` | 2026-10-20T201150303345 -> 2026-10-22T110012937517 | 11 changed, 7 added | quiet |
| 2026-10-22 | `remote/app.seatsherpa/rides` | 2026-10-21T121928640629 -> 2026-10-22T110012593100 | 3 changed | quiet |
| 2026-10-22 | `remote/studio.gradients/mcp` | 2026-10-22T052645443837 -> 2026-10-22T110011337909 | 1 changed | quiet |
| 2026-10-22 | `remote/com.screenrove/screenrove` | 2026-10-06T110128277391 -> 2026-10-22T110010902562 | 9 changed, 3 added | quiet |
| 2026-10-22 | `remote/app.openkrill/school-digest` | 2026-10-19T135611027967 -> 2026-10-22T110006619628 | 1 added | quiet |
| 2026-10-22 | `remote/io.github.andzar22/offstereo` | 2026-09-23T161031611023 -> 2026-10-22T110002893720 | 1 changed, 1 added | quiet |
| 2026-10-22 | `remote/de.overfit/overfit` | 2026-10-06T184112576639 -> 2026-10-22T110010559344 | 24 added, 24 removed | quiet |
| 2026-10-22 | `remote/com.menloinsurance/mcp` | 2026-10-19T212034159775 -> 2026-10-22T105957837439 | 3 changed | quiet |
| 2026-10-22 | `remote/ar.com.consignatarias/cattle-market` | 2026-10-18T113255900442 -> 2026-10-22T105957540352 | 10 changed, 1 added | quiet |
| 2026-10-22 | `remote/io.github.wygogogo19/robotbase-mcp` | 2026-10-20T104046110850 -> 2026-10-22T105954815171 | 2 added | quiet |
| 2026-10-22 | `remote/fi.akkilahdot/travel-search` | 2026-10-22T052644979284 -> 2026-10-22T105951256422 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.CodeWever/wever-labs-products` | 2026-10-18T051358639106 -> 2026-10-22T105940444972 | 29 changed | quiet |
| 2026-10-22 | `remote/com.cadprops/cadprops` | 2026-10-19T135443296655 -> 2026-10-22T105934664426 | 1 changed | quiet |
| 2026-10-22 | `remote/ru.vedarai/mcp` | 2026-10-18T051354633048 -> 2026-10-22T105925012438 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.alexchouck-hash/veabird` | 2026-10-06T110325660998 -> 2026-10-22T105922843519 | 3 added | quiet |
| 2026-10-22 | `remote/tech.skybridge.productivity/Productivity` | 2026-09-23T162923297603 -> 2026-10-22T105922847828 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.cyanheads/uniprot-mcp-server` | 2026-10-17T055854864015 -> 2026-10-22T105917580649 | 4 changed | quiet |
| 2026-10-22 | `remote/gg.unicum/wot-stats` | 2026-10-21T202510868638 -> 2026-10-22T105918123708 | 1 added, 1 removed | quiet |
| 2026-10-22 | `remote/com.zeltser/website-search` | 2026-09-23T161015047304 -> 2026-10-22T105915641983 | 1 changed | quiet |
| 2026-10-22 | `remote/app.openkrill/trending` | 2026-10-19T135441501545 -> 2026-10-22T105912773354 | 1 changed, 1 added | quiet |
| 2026-10-22 | `remote/com.playshowandtell/show-and-tell` | 2026-10-17T060139280697 -> 2026-10-22T105912654309 | 5 changed | quiet |
| 2026-10-22 | `remote/io.github.Schoasch/backtesting-arena` | 2026-10-20T201135758961 -> 2026-10-22T105909212007 | 1 changed | quiet |
| 2026-10-22 | `remote/com.petnecto/pets` | 2026-10-18T190006539502 -> 2026-10-22T105906250875 | 5 changed | quiet |
| 2026-10-22 | `remote/org.virtualflybrain/vfb3-mcp` | 2026-09-23T161008004666 -> 2026-10-22T105904537820 | 1 changed | quiet |
| 2026-10-22 | `remote/app.openkrill/videograb` | 2026-10-19T052414818257 -> 2026-10-22T105904511264 | 1 added | quiet |
| 2026-10-22 | `remote/io.github.LE-VAI/designesy-org` | 2026-10-17T060339790333 -> 2026-10-22T105902963138 | 1 changed | quiet |
| 2026-10-22 | `remote/ch.kulalabs.pazair/pazair` | 2026-10-21T121829567083 -> 2026-10-22T105902624158 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.theyond/jobs` | 2026-10-17T055837698235 -> 2026-10-22T105858023461 | 3 changed (every tool) | quiet |
| 2026-10-22 | `remote/com.usethisskill/skills` | 2026-10-19T135358668102 -> 2026-10-22T105856836266 | 5 changed, 1 added (every tool) | quiet |
| 2026-10-22 | `remote/com.usanaru/schools` | 2026-10-17T055525000024 -> 2026-10-22T105855100449 | 1 changed | quiet |
| 2026-10-22 | `remote/dev.tanod/web` | 2026-10-17T111139383155 -> 2026-10-22T105849786994 | 1 changed | quiet |
| 2026-10-22 | `remote/dev.tanod/text` | 2026-10-17T055830342686 -> 2026-10-22T105849564177 | 1 added | quiet |
| 2026-10-22 | `remote/com.websterberrymarketing.synaptic/data-agents` | 2026-10-19T135410183583 -> 2026-10-22T105845901966 | 6 changed | review |
| 2026-10-22 | `remote/io.github.webweaver-nexus/webweaver-mcp-server` | 2026-10-07T154949442367 -> 2026-10-22T105842607229 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.cyanheads/nonprofit-explorer-mcp-server` | 2026-09-23T162854908350 -> 2026-10-22T105836297024 | 2 changed, 1 added, 1 removed (every tool) | quiet |
| 2026-10-22 | `remote/com.vibe-fixer/vibefix` | 2026-10-20T135414310116 -> 2026-10-22T105832569472 | 2 changed | quiet |
| 2026-10-22 | `remote/io.github.brawlaphant/vealth` | 2026-10-17T185342980994 -> 2026-10-22T105829479427 | 2 changed | quiet |
| 2026-10-22 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-22T052638272814 -> 2026-10-22T105826638409 | 1 changed | quiet |
| 2026-10-22 | `remote/com.frapea/motion` | 2026-10-17T060054425055 -> 2026-10-22T105822782597 | 19 changed, 1 added (every tool) | quiet |
| 2026-10-22 | `remote/tech.skybridge.times-up/Time-s-Up` | 2026-09-23T160953480594 -> 2026-10-22T105819440855 | 2 changed (every tool) | quiet |
| 2026-10-22 | `remote/io.github.Toinedotcom/toolforte` | 2026-09-23T160814011735 -> 2026-10-22T105815355565 | 12 changed | review |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 27548 substantive, 14308 that changed only numbers (a catalogue counter ticking, a date), 559 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 22152 | 8730 | 13422 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 654 | 654 | 0 | 0 |
| `caseyjhand.com` | 174 | 174 | 0 | 0 |
| `sistaminuten.se` | 133 | 4 | 0 | 129 |
| `afbudsrejser.dk` | 132 | 4 | 0 | 128 |
| `akkilahdot.fi` | 132 | 4 | 0 | 128 |
| `restplass.no` | 132 | 4 | 0 | 128 |
| `socialloop.ai` | 128 | 128 | 0 | 0 |
| `remoshift.com` | 103 | 6 | 97 | 0 |
| `fundinglandscape.com` | 101 | 66 | 35 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| 5114 other operators | 16136 | 15336 | 754 | 46 |
