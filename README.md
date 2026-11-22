# MCP server tool changes

Last change observed 2026-11-22T10:49:18+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

126677 changes to a tool definition: 5099 npm releases (4853 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 121578 readings of hosted servers that found their tools changed; 4663 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-22 | `remote/io.github.zerocrewai/zerocrew-directory` | 2026-11-18T140023594292 -> 2026-11-22T104920906250 | 3 changed | quiet |
| 2026-11-22 | `remote/io.github.Hoya25/nctr-mcp-server` | 2026-10-27T112425509382 -> 2026-11-22T104915058058 | 1 changed | quiet |
| 2026-11-22 | `remote/com.xmlvalid/xmlvalid` | 2026-11-11T230902411348 -> 2026-11-22T104912442208 | 5 changed (every tool) | quiet |
| 2026-11-22 | `remote/io.github.XGamesFun/solana-kit` | 2026-11-18T140014866634 -> 2026-11-22T104930868058 | 10 changed, 1 added (every tool) | quiet |
| 2026-11-22 | `remote/io.suverse.www/catalog` | 2026-11-18T080251978876 -> 2026-11-22T104839006389 | 3 changed | quiet |
| 2026-11-22 | `remote/se.sistaminuten/travel-search` | 2026-11-22T073207717557 -> 2026-11-22T104833116365 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.andzar22/offstereo` | 2026-11-13T120005112477 -> 2026-11-22T104815188519 | 1 added | quiet |
| 2026-11-22 | `remote/io.github.JcJamet/ia-qa-eval` | 2026-11-18T135822480105 -> 2026-11-22T104731864448 | 8 changed | quiet |
| 2026-11-22 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-11-22T073206085786 -> 2026-11-22T104730806867 | 3 changed | quiet |
| 2026-11-22 | `remote/io.github.eamwhite1/agent-trust` | 2026-11-17T164904737405 -> 2026-11-22T104707392048 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.TMcodingarc/bull-otc` | 2026-11-21T130643748048 -> 2026-11-22T104631793243 | 5 changed, 1 added | review |
| 2026-11-22 | `remote/com.blitzreels/blitzreels` | 2026-11-18T080243094492 -> 2026-11-22T104630613687 | 5 changed | quiet |
| 2026-11-22 | `remote/io.github.rodriguem75/assuranceslabs` | 2026-11-16T163155780423 -> 2026-11-22T104627854689 | 1 added | quiet |
| 2026-11-22 | `remote/io.github.Mapsdata-io/mapsdata` | 2026-11-13T115954274830 -> 2026-11-22T104628428925 | 1 changed | quiet |
| 2026-11-22 | `remote/no.apier/mcp` | 2026-11-21T151035620107 -> 2026-11-22T104628249733 | 10 changed | quiet |
| 2026-11-22 | `remote/io.github.JcJamet/ia-qa-data` | 2026-11-18T135801141834 -> 2026-11-22T104615037992 | 1 changed | quiet |
| 2026-11-22 | `remote/com.wintraits/wintraits` | 2026-11-16T163139443903 -> 2026-11-22T104603033433 | 18 changed (every tool) | quiet |
| 2026-11-22 | `remote/io.github.asarogers/wellpreppedlife-booking` | 2026-10-06T110135267004 -> 2026-11-22T104552281886 | 4 changed, 4 added (every tool) | quiet |
| 2026-11-22 | `remote/com.aiocompatible/ai-readiness` | 2026-11-16T163245457930 -> 2026-11-22T104548660067 | 1 added | quiet |
| 2026-11-22 | `remote/io.github.cyanheads/worms-marine-taxa-mcp-server` | 2026-10-29T104423528469 -> 2026-11-22T104539556279 | 5 changed | quiet |
| 2026-11-22 | `remote/io.github.cyanheads/wikidata-mcp-server` | 2026-11-16T122822874889 -> 2026-11-22T104532350761 | 5 changed | quiet |
| 2026-11-22 | `remote/app.weekendflights/weekendflights` | 2026-11-05T115356180979 -> 2026-11-22T104529335277 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.cryptoplayer/crypto-casinos` | 2026-11-21T151107615589 -> 2026-11-22T104524048582 | 1 changed | quiet |
| 2026-11-22 | `remote/co.yougame/yougame` | 2026-11-22T073149667069 -> 2026-11-22T104518623445 | 2 changed | quiet |
| 2026-11-22 | `remote/io.github.pratikmehkarkar/vin-recall-mcp` | 2026-09-23T160825040325 -> 2026-11-22T104518154673 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.cyanheads/us-drought-monitor-mcp-server` | 2026-10-26T211518304417 -> 2026-11-22T104514375593 | 6 changed | quiet |
| 2026-11-22 | `remote/io.suverse.versum/catalog` | 2026-11-18T080153808751 -> 2026-11-22T104511964914 | 3 changed | quiet |
| 2026-11-22 | `remote/com.uipolish/mcp` | 2026-11-17T234345518242 -> 2026-11-22T104502699978 | 2 added | quiet |
| 2026-11-22 | `remote/com.tryrankwise/rankwise` | 2026-11-21T215730728556 -> 2026-11-22T104457436085 | 3 changed | quiet |
| 2026-11-22 | `remote/io.github.sudzikcoin/suverse-agent-assistant` | 2026-11-18T080230689323 -> 2026-11-22T104456073980 | 3 changed | quiet |
| 2026-11-22 | `remote/uk.co.transitradar/transitradar` | 2026-10-23T120813076796 -> 2026-11-22T104452391130 | 1 changed | quiet |
| 2026-11-22 | `remote/com.starcovery/mcp` | 2026-11-18T135904412282 -> 2026-11-22T104450193513 | 7 changed | quiet |
| 2026-11-22 | `remote/com.trygoppa/goppa` | 2026-11-17T031602736253 -> 2026-11-22T104446885229 | 1 changed, 18 added | quiet |
| 2026-11-22 | `remote/io.github.snenenenenenene/transita-mcp-server` | 2026-11-03T144825033726 -> 2026-11-22T104441581298 | 15 changed (every tool) | quiet |
| 2026-11-22 | `remote/com.riskcovery/mcp` | 2026-11-16T163326107097 -> 2026-11-22T104436353179 | 25 changed, 1 removed | quiet |
| 2026-11-22 | `remote/no.restplass/travel-search` | 2026-11-22T073147906130 -> 2026-11-22T104435338754 | 1 changed | quiet |
| 2026-11-22 | `remote/com.prismposter/creator-tools` | 2026-10-26T133802361879 -> 2026-11-22T104450505354 | 3 changed | quiet |
| 2026-11-22 | `remote/io.github.SverrirValgeirsson/todourweb` | 2026-11-16T163115145036 -> 2026-11-22T104424347177 | 1 added | quiet |
| 2026-11-22 | `remote/com.eduavenues/eduavenues` | 2026-11-18T135557498893 -> 2026-11-22T104423925937 | 5 changed | quiet |
| 2026-11-22 | `remote/io.github.cyanheads/zenodo-mcp-server` | 2026-10-18T051410676940 -> 2026-11-22T104419438201 | 5 changed | quiet |
| 2026-11-22 | `remote/cn.com.xiaozhaobao/xiaozhaobao` | 2026-10-29T104609306141 -> 2026-11-22T104420886748 | 1 changed | quiet |
| 2026-11-22 | `remote/com.thenewengineer/hvac` | 2026-11-15T115556984548 -> 2026-11-22T104415459286 | 1 changed, 1 added | quiet |
| 2026-11-22 | `remote/io.github.allooloo/issuerwire.1` | 2026-11-11T150154744026 -> 2026-11-22T104413477524 | 4 changed | quiet |
| 2026-11-22 | `remote/report.thales/thales` | 2026-11-14T135942715669 -> 2026-11-22T104407692277 | 2 changed | quiet |
| 2026-11-22 | `remote/com.kulicadvisory/aictionbot-werkbank` | 2026-11-20T105904658437 -> 2026-11-22T104405377603 | 1 added | quiet |
| 2026-11-22 | `remote/io.github.mingyan9989/kaucim-public-mcp` | 2026-11-16T163302525594 -> 2026-11-22T104404006232 | 6 added | quiet |
| 2026-11-22 | `remote/com.swishrjobs/swishrjobs` | 2026-11-17T164455315881 -> 2026-11-22T104400194176 | 4 changed, 8 added | quiet |
| 2026-11-22 | `remote/io.github.MsingathiM/swapeazi` | 2026-11-21T014802462663 -> 2026-11-22T104357822402 | 1 added | quiet |
| 2026-11-22 | `remote/ai.svtr/aidb` | 2026-11-04T150430309819 -> 2026-11-22T104356932341 | 2 changed | quiet |
| 2026-11-22 | `remote/com.patchmcp/patch` | 2026-11-17T164945496865 -> 2026-11-22T104353285019 | 10 changed | quiet |
| 2026-11-22 | `remote/sg.tanatasa/tanatasa` | 2026-11-01T065435796087 -> 2026-11-22T104352783223 | 2 changed | quiet |
| 2026-11-22 | `remote/io.github.racharmi/ohgiftplease` | 2026-11-18T162005879765 -> 2026-11-22T104350870653 | 3 changed | quiet |
| 2026-11-22 | `remote/io.github.1145-am/syracuse-mcp-server` | 2026-11-17T164523979874 -> 2026-11-22T104349602760 | 4 changed (every tool) | quiet |
| 2026-11-22 | `remote/studio.gradients/mcp` | 2026-11-22T073232351937 -> 2026-11-22T104338833009 | 1 changed | quiet |
| 2026-11-22 | `remote/com.droneclearthailand/droneclear-thailand` | 2026-11-08T064602269731 -> 2026-11-22T104336877751 | 2 changed (every tool) | quiet |
| 2026-11-22 | `remote/io.github.CodePhantom-1/ddmarketer-mcp` | 2026-11-12T170949219789 -> 2026-11-22T104334751699 | 1 changed | quiet |
| 2026-11-22 | `remote/io.deeplead/deeplead` | 2026-11-20T160246943774 -> 2026-11-22T104335081971 | 1 changed | quiet |
| 2026-11-22 | `remote/com.structomat/steel` | 2026-11-15T115510400581 -> 2026-11-22T104331522577 | 1 changed, 1 added | quiet |
| 2026-11-22 | `remote/com.codestringers/mcp` | 2026-11-18T161918346707 -> 2026-11-22T104326427755 | 3 changed | quiet |
| 2026-11-22 | `remote/sg.spill/deals` | 2026-11-19T123547027048 -> 2026-11-22T104328520720 | 4 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 82516 substantive, 43004 that changed only numbers (a catalogue counter ticking, a date), 1157 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 69283 | 29077 | 40206 | 0 |
| `a2awire.com` | 3571 | 3571 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 514 | 514 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 401 | 401 | 0 | 0 |
| `revmesh2074.workers.dev` | 361 | 307 | 54 | 0 |
| `sistaminuten.se` | 269 | 6 | 0 | 263 |
| `afbudsrejser.dk` | 268 | 6 | 0 | 262 |
| `akkilahdot.fi` | 268 | 6 | 0 | 262 |
| `restplass.no` | 268 | 6 | 0 | 262 |
| `socialloop.ai` | 259 | 259 | 0 | 0 |
| 10808 other operators | 48394 | 45542 | 2744 | 108 |
