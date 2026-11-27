# MCP server tool changes

Last change observed 2026-11-27T14:56:30+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 18238 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 43073 hosted endpoints (read daily, and every four hours while they keep changing).

145282 changes to a tool definition: 5617 npm releases (5371 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 139665 readings of hosted servers that found their tools changed; 5231 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-27 | `remote/com.xaminat/xaminat` | 2026-11-23T185611276546 -> 2026-11-27T145631270907 | 1 changed | quiet |
| 2026-11-27 | `remote/design.overflow/mcp` | 2026-11-26T135530438754 -> 2026-11-27T145541867441 | 1 changed | quiet |
| 2026-11-27 | `remote/ai.modulos/demo-booking` | 2026-11-27T091025815143 -> 2026-11-27T145534142684 | 3 changed, 1 added | quiet |
| 2026-11-27 | `remote/studio.gradients/mcp` | 2026-11-27T091024205114 -> 2026-11-27T145512067881 | 1 changed | quiet |
| 2026-11-27 | `remote/com.evalgate/evalgate` | 2026-11-18T135922537116 -> 2026-11-27T145457986634 | 5 changed | quiet |
| 2026-11-27 | `remote/com.enerviapower/bess` | 2026-10-17T055931754183 -> 2026-11-27T145456112034 | 6 changed, 2 added (every tool) | quiet |
| 2026-11-27 | `remote/com.direct-hotels/directory` | 2026-11-23T185503440983 -> 2026-11-27T145451912861 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.yourimageshare/yourimageshare` | 2026-10-19T135320576979 -> 2026-11-27T145451342027 | 1 changed | quiet |
| 2026-11-27 | `remote/com.halffee/coinrebate` | 2026-10-08T135500220710 -> 2026-11-27T145448090041 | 4 changed | quiet |
| 2026-11-27 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-22T221047009948 -> 2026-11-27T145446405399 | 1 changed | quiet |
| 2026-11-27 | `remote/io.alertio/alertio` | 2026-10-19T135530574058 -> 2026-11-27T145426720599 | 1 changed | quiet |
| 2026-11-27 | `remote/fi.akkilahdot/travel-search` | 2026-11-27T091024659598 -> 2026-11-27T145426530374 | 1 changed | quiet |
| 2026-11-27 | `remote/app.wuai/wuai` | 2026-11-17T164903200925 -> 2026-11-27T145422412969 | 1 changed | quiet |
| 2026-11-27 | `remote/dev.themes/ui` | 2026-11-23T185347471225 -> 2026-11-27T145421298253 | 2 changed | quiet |
| 2026-11-27 | `remote/com.supersetapp/public` | 2026-11-11T150046736969 -> 2026-11-27T145417257594 | 1 changed | quiet |
| 2026-11-27 | `remote/com.wezzet/aicomms` | 2026-11-14T140130114349 -> 2026-11-27T145405489741 | 2 added | quiet |
| 2026-11-27 | `remote/com.notacompany/newsletter` | 2026-11-26T004631753606 -> 2026-11-27T145354770979 | 1 changed | quiet |
| 2026-11-27 | `remote/ai.oriiion/oriiion` | 2026-11-23T185328588041 -> 2026-11-27T145355764343 | 5 changed, 2 added | quiet |
| 2026-11-27 | `remote/com.easykmarket.vote/votebox-law` | 2026-11-26T135417234828 -> 2026-11-27T145353833793 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.borsty2103/viventii-mcp` | 2026-11-23T185354356429 -> 2026-11-27T145351190144 | 1 changed | quiet |
| 2026-11-27 | `remote/com.mikefluff/mikefluff` | 2026-11-22T150932814932 -> 2026-11-27T145350241528 | 5 changed | quiet |
| 2026-11-27 | `remote/com.visdenda/public` | 2026-11-27T091022779984 -> 2026-11-27T145350533863 | 5 changed, 1 added | quiet |
| 2026-11-27 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-27T091022037911 -> 2026-11-27T145346147208 | 3 changed | quiet |
| 2026-11-27 | `remote/dev.workers.veritas-silicea.veritas-silicea-shop/art` | 2026-11-26T172949172526 -> 2026-11-27T145340240403 | 1 changed | quiet |
| 2026-11-27 | `remote/com.ascent-partners/vision-driven-design` | 2026-11-25T110030958764 -> 2026-11-27T145333370660 | 1 changed, 2 added, 13 removed | quiet |
| 2026-11-27 | `remote/io.github.kushkillerjsixx66/vara-mcp-server` | 2026-10-23T120604742937 -> 2026-11-27T145330980090 | 6 changed (every tool) | quiet |
| 2026-11-27 | `remote/com.gotfreefax/mcp` | 2026-11-08T204942609631 -> 2026-11-27T145323197682 | 7 changed (every tool) | quiet |
| 2026-11-27 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-27T091039511152 -> 2026-11-27T145321939782 | 1 changed | quiet |
| 2026-11-27 | `remote/com.upheron/upheron` | 2026-11-22T150412648315 -> 2026-11-27T145322981953 | 2 changed | quiet |
| 2026-11-27 | `remote/app.travelhealthpass/healthpass` | 2026-11-16T163020666741 -> 2026-11-27T145303640354 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.TGS-checker/tracecheck` | 2026-11-26T135330478579 -> 2026-11-27T145258181748 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.ssitdeveloper/zorqelio` | 2026-11-16T163418270938 -> 2026-11-27T145254558857 | 29 changed (every tool) | quiet |
| 2026-11-27 | `remote/com.appstoretracker/mcp` | 2026-11-23T185236908100 -> 2026-11-27T145251552404 | 3 changed, 1 added | quiet |
| 2026-11-27 | `remote/xyz.quantumatlas/x402-payment-hub` | 2026-11-24T165833619189 -> 2026-11-27T145247789171 | 1 changed | review |
| 2026-11-27 | `remote/io.github.sudzikcoin/suverse-agent-assistant` | 2026-11-27T091012601195 -> 2026-11-27T145235358899 | 3 changed | quiet |
| 2026-11-27 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-26T172845408023 -> 2026-11-27T145233783312 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.ceedot-rock/slid-phi-labs` | 2026-11-14T140206471353 -> 2026-11-27T145227232713 | 25 added | quiet |
| 2026-11-27 | `remote/io.github.RafaCoelho33/web3-systemic-agent` | 2026-11-17T031605927120 -> 2026-11-27T145226755886 | 1 changed, 2 added | review |
| 2026-11-27 | `remote/no.restplass/travel-search` | 2026-11-27T091010339582 -> 2026-11-27T145223434510 | 1 changed | quiet |
| 2026-11-27 | `remote/com.waketrades/mcp` | 2026-11-02T163810123716 -> 2026-11-27T145222953763 | 5 changed, 4 added | quiet |
| 2026-11-27 | `remote/pl.podziemieanalityczne/dane` | 2026-11-27T091010893189 -> 2026-11-27T145218852287 | 1 changed | quiet |
| 2026-11-27 | `remote/com.tablejourney/food-travel` | 2026-10-28T132942344964 -> 2026-11-27T145214792817 | 1 changed | quiet |
| 2026-11-27 | `remote/io.suverse.versum/catalog` | 2026-11-27T091037187074 -> 2026-11-27T145212190426 | 3 changed | quiet |
| 2026-11-27 | `remote/io.github.sf0116/myschoolhub` | 2026-11-21T151109531106 -> 2026-11-27T145210345887 | 1 changed | quiet |
| 2026-11-27 | `remote/com.zainsaeed/hire-zain` | 2026-11-02T163509487623 -> 2026-11-27T145206114051 | 1 changed | quiet |
| 2026-11-27 | `remote/com.variotrip/esim-catalog` | 2026-11-23T185151635925 -> 2026-11-27T145203970741 | 1 changed | quiet |
| 2026-11-27 | `remote/tr.com.kariwood.www/catalog` | 2026-10-17T060444384722 -> 2026-11-27T145203947153 | 6 changed | quiet |
| 2026-11-27 | `remote/xn--3ds443g.xn--s7y/duan-online` | 2026-11-25T035029537072 -> 2026-11-27T145201575066 | 17 changed (every tool) | quiet |
| 2026-11-27 | `remote/io.github.Hyatus-Living/hyatus-stays` | 2026-11-16T163254670751 -> 2026-11-27T145156385092 | 5 changed (every tool) | quiet |
| 2026-11-27 | `remote/io.github.cryptoduke01/gloam` | 2026-11-23T185429567203 -> 2026-11-27T145153468072 | 1 changed | quiet |
| 2026-11-27 | `remote/com.achivx/stablescan` | 2026-11-26T135224989884 -> 2026-11-27T145148476932 | 1 changed | quiet |
| 2026-11-27 | `remote/xyz.tereno/tereno` | 2026-11-24T050520205609 -> 2026-11-27T145144121802 | 1 changed | quiet |
| 2026-11-27 | `remote/io.taifoon/coordination-layer.1` | 2026-11-25T035026810568 -> 2026-11-27T145143126998 | 1 changed | quiet |
| 2026-11-27 | `remote/io.deeplead/deeplead` | 2026-11-25T174715607546 -> 2026-11-27T145142602386 | 18 changed | quiet |
| 2026-11-27 | `remote/io.suverse.www/catalog` | 2026-11-27T091115773750 -> 2026-11-27T145142683964 | 3 changed | quiet |
| 2026-11-27 | `remote/finance.souvenir/coins` | 2026-11-22T150229601564 -> 2026-11-27T145140490505 | 1 changed | quiet |
| 2026-11-27 | `remote/se.sistaminuten/travel-search` | 2026-11-27T091115173544 -> 2026-11-27T145136246789 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-27T091010599093 -> 2026-11-27T145135419102 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.benzatkulak-collab/socialperks` | 2026-09-23T162853217896 -> 2026-11-27T145135673291 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.cyanheads/smithsonian-mcp-server` | 2026-11-16T122829864962 -> 2026-11-27T145131805943 | 3 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 96872 substantive, 47163 that changed only numbers (a catalogue counter ticking, a date), 1247 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 80486 | 36546 | 43940 | 0 |
| `a2awire.com` | 4105 | 4105 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 549 | 549 | 0 | 0 |
| `modevc.com` | 524 | 524 | 0 | 0 |
| `civai.co` | 403 | 403 | 0 | 0 |
| `revmesh2074.workers.dev` | 373 | 315 | 58 | 0 |
| `sistaminuten.se` | 290 | 7 | 0 | 283 |
| `afbudsrejser.dk` | 289 | 7 | 0 | 282 |
| `akkilahdot.fi` | 289 | 7 | 0 | 282 |
| `restplass.no` | 289 | 7 | 0 | 282 |
| `socialloop.ai` | 280 | 280 | 0 | 0 |
| 11807 other operators | 55064 | 51781 | 3165 | 118 |
