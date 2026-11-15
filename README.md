# MCP server tool changes

Last change observed 2026-11-15T11:58:38+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

101941 changes to a tool definition: 4272 npm releases (4026 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 97669 readings of hosted servers that found their tools changed; 4154 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-15 | `remote/io.github.eamwhite1/agent-trust` | 2026-11-10T153333252570 -> 2026-11-15T115839768464 | 1 changed | quiet |
| 2026-11-15 | `remote/io.soldcomps/sold-comps` | 2026-11-02T065432593612 -> 2026-11-15T115819395355 | 4 changed | quiet |
| 2026-11-15 | `remote/com.roomeinc.www/quotes` | 2026-11-04T005903509876 -> 2026-11-15T115819906650 | 2 changed | quiet |
| 2026-11-15 | `remote/io.github.angelnikolov/remote-jobs` | 2026-10-26T133712532083 -> 2026-11-15T115813203200 | 4 changed | quiet |
| 2026-11-15 | `remote/ai.oriiion/oriiion` | 2026-11-14T140152329220 -> 2026-11-15T115805168409 | 1 added | quiet |
| 2026-11-15 | `remote/nl.insiderradar/insiderradar` | 2026-11-07T133432679980 -> 2026-11-15T115751316451 | 2 changed | quiet |
| 2026-11-15 | `remote/io.github.LouisLin0723/fatestar-ziwei` | 2026-09-23T160840875261 -> 2026-11-15T115742605253 | 3 changed, 4 added (every tool) | quiet |
| 2026-11-15 | `remote/io.github.Portuno/corruptopolis` | 2026-11-02T163845520700 -> 2026-11-15T115734865262 | 1 changed | quiet |
| 2026-11-15 | `remote/co.codeways/codeways-mcp` | 2026-11-02T163816699291 -> 2026-11-15T115702674961 | 1 changed | review |
| 2026-11-15 | `remote/ai.thebotique.www/sigil` | 2026-10-10T202104573581 -> 2026-11-15T115701905120 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.switchwize/switchwize-mcp` | 2026-11-02T163731226049 -> 2026-11-15T115701109400 | 1 changed, 6 added | quiet |
| 2026-11-15 | `remote/xn--3ds443g.xn--s7y/duan-online` | 2026-11-11T150041699586 -> 2026-11-15T115659446014 | 1 changed | quiet |
| 2026-11-15 | `remote/ai.reg-bot/compliance-oracle` | 2026-11-06T144924918481 -> 2026-11-15T115655316678 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.vassiliylakhonin/vizier` | 2026-11-11T145915005451 -> 2026-11-15T115653545449 | 1 changed | quiet |
| 2026-11-15 | `remote/uk.co.pocketly/offers` | 2026-11-09T170338334905 -> 2026-11-15T115651735500 | 1 changed | quiet |
| 2026-11-15 | `remote/ai.usedby/usedby` | 2026-11-06T214859019491 -> 2026-11-15T115647550145 | 2 changed | quiet |
| 2026-11-15 | `remote/io.suverse.versum/catalog` | 2026-11-15T071622832850 -> 2026-11-15T115648838790 | 3 changed | quiet |
| 2026-11-15 | `remote/io.metodic/metodic` | 2026-11-05T115543340139 -> 2026-11-15T115646397541 | 1 changed | quiet |
| 2026-11-15 | `remote/com.swiftprobate/probate` | 2026-11-12T170940053374 -> 2026-11-15T115640126353 | 2 changed, 3 added | review |
| 2026-11-15 | `remote/studio.gradients/mcp` | 2026-11-15T071614198809 -> 2026-11-15T115635965177 | 1 changed | quiet |
| 2026-11-15 | `remote/se.sistaminuten/travel-search` | 2026-11-15T071625331328 -> 2026-11-15T115638093404 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.eyeinthesky6/unseen-workflow-compiler` | 2026-11-14T140021704100 -> 2026-11-15T115631442060 | 6 changed | quiet |
| 2026-11-15 | `remote/il.co.deali/mcp` | 2026-09-23T162938251253 -> 2026-11-15T115626090196 | 1 changed, 1 added | quiet |
| 2026-11-15 | `remote/com.trygoppa/goppa` | 2026-11-12T154806209403 -> 2026-11-15T115622174995 | 2 changed | quiet |
| 2026-11-15 | `remote/com.triremes/triremes` | 2026-11-11T071417916555 -> 2026-11-15T115620066869 | 1 changed | quiet |
| 2026-11-15 | `remote/fi.akkilahdot/travel-search` | 2026-11-15T071612681601 -> 2026-11-15T115617093181 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.alwaysarafath/thepaymentsnotes-ledger` | 2026-10-27T112256421995 -> 2026-11-15T115613992719 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.cyanheads/who-gho-mcp-server` | 2026-10-26T133455019532 -> 2026-11-15T115607683200 | 3 changed | quiet |
| 2026-11-15 | `remote/io.github.SusanAcharya/design-lounge` | 2026-11-02T163408269670 -> 2026-11-15T115600128255 | 4 removed | quiet |
| 2026-11-15 | `remote/io.github.Tomalarrrr/cyclesite-mcp-server` | 2026-11-13T150611099870 -> 2026-11-15T115600641266 | 3 changed | quiet |
| 2026-11-15 | `remote/com.thenewengineer/hvac` | 2026-11-03T195502354689 -> 2026-11-15T115556984548 | 1 changed | quiet |
| 2026-11-15 | `remote/dev.vetagent/vetagent` | 2026-10-17T185358353343 -> 2026-11-15T115544112119 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-15T071611282445 -> 2026-11-15T115544374881 | 3 changed | quiet |
| 2026-11-15 | `remote/com.workingcapitalquotes/site` | 2026-11-12T154949294839 -> 2026-11-15T115541837521 | 2 changed | quiet |
| 2026-11-15 | `remote/dev.tanod/util` | 2026-11-03T144757215836 -> 2026-11-15T115535903654 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.cyanheads/usda-mcp-server` | 2026-11-11T150008052999 -> 2026-11-15T115532361793 | 4 changed | quiet |
| 2026-11-15 | `remote/io.github.t0ll-xyz/toll` | 2026-11-14T114920467185 -> 2026-11-15T115529951007 | 1 changed | quiet |
| 2026-11-15 | `remote/party.wakidokoro/chiikawa` | 2026-11-09T170144820717 -> 2026-11-15T115515013258 | 7 changed | quiet |
| 2026-11-15 | `remote/io.github.t1mom777/transfers-car-rentals` | 2026-10-17T055848217392 -> 2026-11-15T115512826029 | 3 changed | quiet |
| 2026-11-15 | `remote/io.github.Schoasch/backtesting-arena` | 2026-11-12T155128302990 -> 2026-11-15T115511445006 | 11 changed | quiet |
| 2026-11-15 | `remote/com.structomat/steel` | 2026-11-12T154654897151 -> 2026-11-15T115510400581 | 1 changed | quiet |
| 2026-11-15 | `remote/com.strengthstandardscalc/site` | 2026-11-12T154653917907 -> 2026-11-15T115510803803 | 2 changed | quiet |
| 2026-11-15 | `remote/com.usetested/reviews` | 2026-11-13T150503712695 -> 2026-11-15T115457743061 | 2 added | quiet |
| 2026-11-15 | `remote/com.themachinerecord/register` | 2026-11-03T144831377353 -> 2026-11-15T115452989890 | 1 changed | quiet |
| 2026-11-15 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-14T183352468762 -> 2026-11-15T115453495779 | 2 changed | quiet |
| 2026-11-15 | `remote/fr.solanometeo/solano` | 2026-11-12T154637849247 -> 2026-11-15T115453429798 | 1 changed | quiet |
| 2026-11-15 | `remote/com.snagcast/snagcast` | 2026-11-02T163602814742 -> 2026-11-15T115444372798 | 7 changed (every tool) | quiet |
| 2026-11-15 | `remote/ai.tutorping/tutorping` | 2026-10-06T110114233320 -> 2026-11-15T115442647603 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.IDNSIDNS/tenderapi-mcp` | 2026-10-17T055832826419 -> 2026-11-15T115442360049 | 3 changed (every tool) | quiet |
| 2026-11-15 | `remote/com.tryalpy/alpy` | 2026-10-21T122236270850 -> 2026-11-15T115440631316 | 1 changed | quiet |
| 2026-11-15 | `remote/com.swarmmemo/bulletin.1` | 2026-11-11T145910211995 -> 2026-11-15T115430355854 | 2 changed | quiet |
| 2026-11-15 | `remote/com.shipshapedata/shipshape-data` | 2026-11-14T114917823442 -> 2026-11-15T115429427137 | 1 changed | quiet |
| 2026-11-15 | `remote/net.supertry/bluetab.1` | 2026-11-09T170043135066 -> 2026-11-15T115431799218 | 3 changed | quiet |
| 2026-11-15 | `remote/gs.sundo/sundogs` | 2026-11-09T170041337338 -> 2026-11-15T115429082603 | 1 changed | quiet |
| 2026-11-15 | `remote/com.sfxmint/sounds` | 2026-11-15T071614563816 -> 2026-11-15T115425300506 | 3 changed | quiet |
| 2026-11-15 | `remote/com.selectbnbs/verify` | 2026-09-28T142205026811 -> 2026-11-15T115415866112 | 2 changed (every tool) | quiet |
| 2026-11-15 | `remote/com.zertidox/zertidox` | 2026-10-19T135916244865 -> 2026-11-15T115411893968 | 2 changed | quiet |
| 2026-11-15 | `remote/io.saascity/saascity` | 2026-11-09T165751965551 -> 2026-11-15T115400037982 | 22 changed | quiet |
| 2026-11-15 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-15T071605574203 -> 2026-11-15T115358538812 | 1 changed | quiet |
| 2026-11-15 | `remote/dev.tanod/tanod` | 2026-11-11T164114608773 -> 2026-11-15T115400946096 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 62087 substantive, 38828 that changed only numbers (a catalogue counter ticking, a date), 1026 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 54383 | 17878 | 36505 | 0 |
| `a2awire.com` | 2642 | 2642 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 431 | 431 | 0 | 0 |
| `civai.co` | 319 | 319 | 0 | 0 |
| `revmesh2074.workers.dev` | 266 | 233 | 33 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `sistaminuten.se` | 239 | 6 | 0 | 233 |
| `afbudsrejser.dk` | 238 | 6 | 0 | 232 |
| `akkilahdot.fi` | 238 | 6 | 0 | 232 |
| `restplass.no` | 238 | 6 | 0 | 232 |
| `socialloop.ai` | 230 | 230 | 0 | 0 |
| 9468 other operators | 40118 | 37731 | 2290 | 97 |
