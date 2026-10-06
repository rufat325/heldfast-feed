# MCP server tool changes

Last change observed 2026-10-06T11:04:39+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10128 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 21701 hosted endpoints (read daily, and every four hours while they keep changing).

22106 changes to a tool definition: 779 npm releases (533 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 21327 readings of hosted servers that found their tools changed; 280 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-06 | `remote/com.electionsmcp/electionsmcp` | 2026-09-28T142306739874 -> 2026-10-06T110313198280 | 1 changed | quiet |
| 2026-10-06 | `remote/com.detextit.www/detextit` | 2026-10-02T130812032952 -> 2026-10-06T110309514676 | 1 changed | quiet |
| 2026-10-06 | `remote/uk.co.tm44quote/site` | 2026-09-23T162911179016 -> 2026-10-06T110305544663 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.SiliconRoshiBill/heropedia` | 2026-09-23T160842733604 -> 2026-10-06T110259673782 | 4 changed (every tool) | quiet |
| 2026-10-06 | `remote/com.texassolarcostcalculator/site` | 2026-09-23T162907725389 -> 2026-10-06T110257430401 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.IDNSIDNS/tenderapi-mcp` | 2026-09-23T162906257442 -> 2026-10-06T110256572518 | 1 changed | quiet |
| 2026-10-06 | `remote/dk.afbudsrejser/travel-search` | 2026-10-06T013036328717 -> 2026-10-06T110256308807 | 1 changed | quiet |
| 2026-10-06 | `remote/io.engineeringleaders/elc-trade` | 2026-09-23T160840946015 -> 2026-10-06T110253500765 | 1 changed | quiet |
| 2026-10-06 | `remote/io.engineeringleaders/elc-toolkit` | 2026-09-23T160840733134 -> 2026-10-06T110253485596 | 1 changed | quiet |
| 2026-10-06 | `remote/uk.co.tachocalibration/site` | 2026-09-23T162904671429 -> 2026-10-06T110252039723 | 1 changed | quiet |
| 2026-10-06 | `remote/org.windowsticker/window-sticker` | 2026-09-30T210256222563 -> 2026-10-06T110251468309 | 1 changed | quiet |
| 2026-10-06 | `remote/uk.co.whichevcharger/site` | 2026-09-23T163114221626 -> 2026-10-06T110250109905 | 1 changed | quiet |
| 2026-10-06 | `remote/ch.swisslivingindex/swiss-living-index` | 2026-10-05T172729060848 -> 2026-10-06T110250219013 | 5 added | quiet |
| 2026-10-06 | `remote/io.github.LE-VAI/designesy-org` | 2026-10-01T063534645930 -> 2026-10-06T110250016339 | 1 changed | quiet |
| 2026-10-06 | `remote/com.swarmmemo/bulletin` | 2026-10-03T054746577688 -> 2026-10-06T110251140041 | 42 changed, 29 added (every tool) | review |
| 2026-10-06 | `remote/uk.co.wastecarriercheck/site` | 2026-09-23T163110101146 -> 2026-10-06T110246708696 | 1 changed | quiet |
| 2026-10-06 | `remote/uk.co.structuralreportcost/site` | 2026-09-23T162900630156 -> 2026-10-06T110247068071 | 1 changed | quiet |
| 2026-10-06 | `remote/com.strrulescheck/site` | 2026-09-23T162900127988 -> 2026-10-06T110246456995 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.rzere/linkedin-mcp` | 2026-09-23T160834899559 -> 2026-10-06T110244382204 | 1 changed | quiet |
| 2026-10-06 | `remote/com.googleapis.stitch/mcp` | 2026-09-23T162857999290 -> 2026-10-06T110244353324 | 1 changed | quiet |
| 2026-10-06 | `remote/com.virus-alert/agent-observatory` | 2026-09-23T163105979615 -> 2026-10-06T110244339726 | 6 changed (every tool) | quiet |
| 2026-10-06 | `remote/app.steadywrk/mcp-dispatch` | 2026-09-23T162857326457 -> 2026-10-06T110243385612 | 2 changed | quiet |
| 2026-10-06 | `remote/uk.co.venuecapacitycheck/site` | 2026-09-23T163101838110 -> 2026-10-06T110242031651 | 1 changed | quiet |
| 2026-10-06 | `remote/com.sredfinder/site` | 2026-09-23T162857498217 -> 2026-10-06T110241814726 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-06T013127452505 -> 2026-10-06T110235321613 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.SidneyBissoli/uis-mcp-server` | 2026-10-02T182925021536 -> 2026-10-06T110234812981 | 5 changed (every tool) | quiet |
| 2026-10-06 | `remote/uk.co.workplacerecyclingrules/site` | 2026-09-23T160832752345 -> 2026-10-06T110234782065 | 1 changed | quiet |
| 2026-10-06 | `remote/uk.co.smokecontrolchecker/site` | 2026-09-23T162854093886 -> 2026-10-06T110234464146 | 1 changed | quiet |
| 2026-10-06 | `remote/xyz.trusteed/mcp-gateway` | 2026-10-03T054741253391 -> 2026-10-06T110232244466 | 8 changed | quiet |
| 2026-10-06 | `remote/com.trustbaselab/rcb-data` | 2026-09-23T163052848353 -> 2026-10-06T110233285703 | 2 changed | quiet |
| 2026-10-06 | `remote/ai.trydock/dock` | 2026-10-02T182920824509 -> 2026-10-06T110231129630 | 2 changed, 3 added | quiet |
| 2026-10-06 | `remote/uk.co.treesurveycost/site` | 2026-09-23T163053062311 -> 2026-10-06T110232782073 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 15410 substantive, 6388 that changed only numbers (a catalogue counter ticking, a date), 308 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 11701 | 5689 | 6012 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `sistaminuten.se` | 75 | 2 | 0 | 73 |
| `afbudsrejser.dk` | 74 | 2 | 0 | 72 |
| `akkilahdot.fi` | 74 | 2 | 0 | 72 |
| `caseyjhand.com` | 74 | 74 | 0 | 0 |
| `restplass.no` | 74 | 2 | 0 | 72 |
| `socialloop.ai` | 72 | 72 | 0 | 0 |
| `dayze.com` | 65 | 65 | 0 | 0 |
| `daedalmap.com` | 53 | 53 | 0 | 0 |
| 2647 other operators | 6982 | 6587 | 376 | 19 |
