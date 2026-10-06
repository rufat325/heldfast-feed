# MCP server tool changes

Last change observed 2026-10-06T11:34:31+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10128 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 21701 hosted endpoints (read daily, and every four hours while they keep changing).

22138 changes to a tool definition: 779 npm releases (533 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 21359 readings of hosted servers that found their tools changed; 281 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-06 | `remote/com.n9t2/xrpl-agent-gateway` | 2026-10-06T110216461570 -> 2026-10-06T113433124958 | 19 changed (every tool) | quiet |
| 2026-10-06 | `remote/se.sistaminuten/travel-search` | 2026-10-06T110208223845 -> 2026-10-06T113431122201 | 1 changed | quiet |
| 2026-10-06 | `remote/no.restplass/travel-search` | 2026-10-06T110327640618 -> 2026-10-06T113424168876 | 1 changed | quiet |
| 2026-10-06 | `remote/ai.vegvis/vegvisai` | 2026-10-06T110122375391 -> 2026-10-06T113421401921 | 5 changed (every tool) | quiet |
| 2026-10-06 | `remote/dk.afbudsrejser/travel-search` | 2026-10-06T110256308807 -> 2026-10-06T113417298854 | 1 changed | quiet |
| 2026-10-06 | `remote/fi.akkilahdot/travel-search` | 2026-10-06T110347221844 -> 2026-10-06T113409217155 | 1 changed | quiet |
| 2026-10-06 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-06T110151936483 -> 2026-10-06T113405470363 | 2 changed | quiet |
| 2026-10-06 | `remote/io.github.Schoasch/backtesting-arena` | 2026-10-06T110314500789 -> 2026-10-06T113404439888 | 1 changed | quiet |
| 2026-10-06 | `remote/ai.pechincha/deals` | 2026-10-06T105951663484 -> 2026-10-06T113403057858 | 2 changed, 6 added | quiet |
| 2026-10-06 | `remote/com.swarmmemo/bulletin` | 2026-10-06T110251140041 -> 2026-10-06T113401830335 | 8 changed | quiet |
| 2026-10-06 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-06T110235321613 -> 2026-10-06T113358142012 | 1 changed | quiet |
| 2026-10-06 | `remote/cn.savantcat/answers` | 2026-10-04T054932815568 -> 2026-10-06T113403201117 | 5 changed (every tool) | quiet |
| 2026-10-06 | `remote/com.remoshift/jobs` | 2026-10-06T110154723086 -> 2026-10-06T113353405524 | 1 changed | quiet |
| 2026-10-06 | `remote/gl.parse/mcp` | 2026-10-06T105811032051 -> 2026-10-06T113350838822 | 2 changed | quiet |
| 2026-10-06 | `remote/win.price/pricewin` | 2026-10-06T105905114007 -> 2026-10-06T113346225978 | 5 changed | quiet |
| 2026-10-06 | `remote/ai.switchapp/switch` | 2026-10-06T110033653568 -> 2026-10-06T113342194114 | 4 changed | quiet |
| 2026-10-06 | `remote/com.audiala/mcp` | 2026-10-06T105757550032 -> 2026-10-06T113337960340 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.Book0fEli/paycheck` | 2026-10-06T105726706451 -> 2026-10-06T113335579308 | 1 changed | quiet |
| 2026-10-06 | `remote/com.keywordise/keywordise` | 2026-10-06T105708961120 -> 2026-10-06T113332383726 | 2 changed | review |
| 2026-10-06 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-06T105446356065 -> 2026-10-06T113325540465 | 2 changed | quiet |
| 2026-10-06 | `remote/au.humanendpoint/humanendpoint` | 2026-10-06T105545510977 -> 2026-10-06T113326002252 | 4 changed | quiet |
| 2026-10-06 | `remote/ai.councilof/gspc-free` | 2026-10-06T105421225922 -> 2026-10-06T113315530588 | 1 changed | quiet |
| 2026-10-06 | `remote/com.blockvectra/docs` | 2026-10-06T105332023207 -> 2026-10-06T113312768325 | 2 changed | quiet |
| 2026-10-06 | `remote/io.github.CSOAI-ORG/gspc` | 2026-10-06T105439319978 -> 2026-10-06T113313127815 | 2 changed | quiet |
| 2026-10-06 | `remote/com.booklint/desk` | 2026-10-06T105333654297 -> 2026-10-06T113310678532 | 1 changed | quiet |
| 2026-10-06 | `remote/ai.councilof/gspc` | 2026-10-06T105317053049 -> 2026-10-06T113310285776 | 2 changed | quiet |
| 2026-10-06 | `remote/app.apick/all` | 2026-10-06T105306517873 -> 2026-10-06T113306117247 | 10 added | quiet |
| 2026-10-06 | `remote/com.ask-ai-data-connector/ask-ai` | 2026-10-06T105339468980 -> 2026-10-06T113303556517 | 1 changed | quiet |
| 2026-10-06 | `remote/app.apick/web` | 2026-10-06T105318274487 -> 2026-10-06T113302766433 | 10 added | quiet |
| 2026-10-06 | `remote/com.revdoku/revdoku` | 2026-10-06T013107571812 -> 2026-10-06T113259926657 | 1 changed | quiet |
| 2026-10-06 | `remote/com.hlaverify/hla-verify` | 2026-10-06T105104104815 -> 2026-10-06T113259027242 | 3 changed | quiet |
| 2026-10-06 | `remote/ai.maxwellinternational/data` | 2026-10-06T105047289047 -> 2026-10-06T113257058642 | 3 changed | quiet |
| 2026-10-06 | `remote/com.zinvyl/marketplace` | 2026-09-27T105441795272 -> 2026-10-06T110440690031 | 4 added | review |
| 2026-10-06 | `remote/io.github.Dcroyalty/xrplhub` | 2026-09-26T132505041224 -> 2026-10-06T110430365166 | 3 changed | quiet |
| 2026-10-06 | `remote/ai.thebotique.www/sigil` | 2026-09-24T120511200417 -> 2026-10-06T110427588515 | 11 changed (every tool) | quiet |
| 2026-10-06 | `remote/io.github.Licium-ai/licium` | 2026-10-02T072229433259 -> 2026-10-06T110416563816 | 7 changed, 2 added | quiet |
| 2026-10-06 | `remote/com.codestringers/mcp` | 2026-09-23T162935977286 -> 2026-10-06T110358709871 | 4 changed, 1 added | quiet |
| 2026-10-06 | `remote/io.github.Gingiris-1031/analook` | 2026-09-23T162934303540 -> 2026-10-06T110348312729 | 8 changed (every tool) | quiet |
| 2026-10-06 | `remote/fi.akkilahdot/travel-search` | 2026-10-06T013128827820 -> 2026-10-06T110347221844 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.agentready-market/audit` | 2026-09-23T162932605828 -> 2026-10-06T110346652644 | 2 changed | quiet |
| 2026-10-06 | `remote/io.github.maxschnee74-source/alpinelead` | 2026-10-01T134429446877 -> 2026-10-06T110344097452 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.ajithisaac/world-resolver` | 2026-09-23T162931840530 -> 2026-10-06T110343879921 | 6 added | quiet |
| 2026-10-06 | `remote/io.github.oppenheimervonbraun/zerostart-agent` | 2026-09-23T163153121904 -> 2026-10-06T110341405097 | 1 changed | review |
| 2026-10-06 | `remote/io.github.kor-jongwon/witan` | 2026-10-02T061631706560 -> 2026-10-06T110343350997 | 5 changed, 2 added | review |
| 2026-10-06 | `remote/com.whichmadvisor/site` | 2026-09-23T162930113344 -> 2026-10-06T110340430145 | 1 changed | quiet |
| 2026-10-06 | `remote/com.whichfieldsoftware/site` | 2026-09-23T162929811218 -> 2026-10-06T110340472257 | 1 changed | quiet |
| 2026-10-06 | `remote/com.workers-rights/employment-law` | 2026-09-23T160857755332 -> 2026-10-06T110336636186 | 3 changed | quiet |
| 2026-10-06 | `remote/xyz.costrinity/vitna-compliance-preflight` | 2026-09-23T162925001560 -> 2026-10-06T110330646779 | 2 changed | quiet |
| 2026-10-06 | `remote/com.smsvertpro/mcp` | 2026-09-28T142323293815 -> 2026-10-06T110330567216 | 2 changed | quiet |
| 2026-10-06 | `remote/no.restplass/travel-search` | 2026-10-06T013036898441 -> 2026-10-06T110327640618 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.vlad-public-code/valem` | 2026-09-23T162921591959 -> 2026-10-06T110325365134 | 2 added | quiet |
| 2026-10-06 | `remote/ar.mueblito/mueblito` | 2026-09-23T163138155208 -> 2026-10-06T110323874509 | 8 changed | quiet |
| 2026-10-06 | `remote/io.github.aneduaim/untap-mcp` | 2026-10-01T134543197299 -> 2026-10-06T110322930953 | 3 changed, 2 added | quiet |
| 2026-10-06 | `remote/help.servicebuddy/mcp` | 2026-10-01T134411116928 -> 2026-10-06T110323178278 | 1 changed | quiet |
| 2026-10-06 | `remote/com.satellitequotes/satellitequotes` | 2026-09-28T142359624166 -> 2026-10-06T110322709268 | 1 added | review |
| 2026-10-06 | `remote/uk.co.underpinningcosts/site` | 2026-09-23T162920496769 -> 2026-10-06T110323250521 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.OmniAISystems/govomniai-machine-services` | 2026-10-03T121508838073 -> 2026-10-06T110322062606 | 1 changed, 1 added | review |
| 2026-10-06 | `remote/dev.workers.panda198271.tw-life-info/life-info` | 2026-09-28T142556980074 -> 2026-10-06T110320231748 | 4 added | quiet |
| 2026-10-06 | `remote/uk.co.transportstatementcost/site` | 2026-09-23T162916848581 -> 2026-10-06T110318794758 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.Schoasch/backtesting-arena` | 2026-10-02T210136544968 -> 2026-10-06T110314500789 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 15437 substantive, 6389 that changed only numbers (a catalogue counter ticking, a date), 312 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 11701 | 5689 | 6012 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `sistaminuten.se` | 76 | 2 | 0 | 74 |
| `afbudsrejser.dk` | 75 | 2 | 0 | 73 |
| `akkilahdot.fi` | 75 | 2 | 0 | 73 |
| `restplass.no` | 75 | 2 | 0 | 73 |
| `caseyjhand.com` | 74 | 74 | 0 | 0 |
| `socialloop.ai` | 73 | 73 | 0 | 0 |
| `dayze.com` | 65 | 65 | 0 | 0 |
| `daedalmap.com` | 53 | 53 | 0 | 0 |
| 2656 other operators | 7009 | 6613 | 377 | 19 |
