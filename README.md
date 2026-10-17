# MCP server tool changes

Last change observed 2026-10-17T12:29:04+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10495 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 23695 hosted endpoints (read daily, and every four hours while they keep changing).

30209 changes to a tool definition: 1052 npm releases (806 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 29157 readings of hosted servers that found their tools changed; 2055 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-17 | `remote/io.taifoon/coordination-layer.1` | 2026-10-17T111001609046 -> 2026-10-17T122905896408 | 1 changed | review |
| 2026-10-17 | `remote/se.sistaminuten/travel-search` | 2026-10-17T110958870396 -> 2026-10-17T122904368635 | 1 changed | quiet |
| 2026-10-17 | `remote/fi.akkilahdot/travel-search` | 2026-10-17T111223508210 -> 2026-10-17T122901805768 | 1 changed | quiet |
| 2026-10-17 | `remote/us.srv.vehcdj664efetfrsolne5umanq/quoteproof-mcp` | 2026-10-17T111205518506 -> 2026-10-17T122856954857 | 10 changed | quiet |
| 2026-10-17 | `remote/io.github.veredamonte-glitch/verithic` | 2026-10-17T055903925489 -> 2026-10-17T122857766510 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.dtajitdinov-aris/sphere-marketplace` | 2026-10-17T055818430410 -> 2026-10-17T122845600781 | 5 changed, 1 added, 1 removed | review |
| 2026-10-17 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-17T111120466946 -> 2026-10-17T122842362350 | 1 changed | quiet |
| 2026-10-17 | `remote/com.remoshift/jobs` | 2026-10-17T111045869207 -> 2026-10-17T122837028580 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.yschimke/compose-preview` | 2026-10-17T055708546308 -> 2026-10-17T122834236735 | 1 changed | quiet |
| 2026-10-17 | `remote/no.restplass/travel-search` | 2026-10-17T110834953229 -> 2026-10-17T122830729274 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.openaccountants/openaccountants` | 2026-10-17T110831681288 -> 2026-10-17T122830576701 | 3 changed | quiet |
| 2026-10-17 | `remote/online.pageaudit/pageaudit` | 2026-10-17T055643838215 -> 2026-10-17T122828026708 | 3 added | quiet |
| 2026-10-17 | `remote/dk.afbudsrejser/travel-search` | 2026-10-17T110803672697 -> 2026-10-17T122824784538 | 1 changed | quiet |
| 2026-10-17 | `remote/com.neblla/neblla` | 2026-10-17T110949926368 -> 2026-10-17T122824649995 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.zambodotdev/zambo` | 2026-10-17T110941336243 -> 2026-10-17T122821517638 | 2 changed | quiet |
| 2026-10-17 | `remote/dev.zambo/zambo` | 2026-10-17T110941698410 -> 2026-10-17T122821637650 | 2 changed | quiet |
| 2026-10-17 | `remote/dev.usaref/reference-data` | 2026-10-17T110736355122 -> 2026-10-17T122822022628 | 3 added | quiet |
| 2026-10-17 | `remote/dev.mearef/reference-data` | 2026-10-17T110940161112 -> 2026-10-17T122822350211 | 3 added | quiet |
| 2026-10-17 | `remote/io.github.everyai-com/sahadeva` | 2026-10-17T060238106002 -> 2026-10-17T122808183268 | 1 added | quiet |
| 2026-10-17 | `remote/com.scrapefield/scrapefield` | 2026-10-17T060250463670 -> 2026-10-17T122809082533 | 5 changed | quiet |
| 2026-10-17 | `remote/ai.mapmap/mapmap` | 2026-10-17T110827799112 -> 2026-10-17T122810348878 | 4 changed | quiet |
| 2026-10-17 | `remote/com.hireahelper/mcp` | 2026-10-17T073147881787 -> 2026-10-17T122804920970 | 16 added | quiet |
| 2026-10-17 | `remote/club.goodleads/new-business-owner-contacts` | 2026-10-17T055409679191 -> 2026-10-17T122804231259 | 1 changed | quiet |
| 2026-10-17 | `remote/ch.kulalabs.pazair/pazair` | 2026-10-17T110526986404 -> 2026-10-17T122800976184 | 1 added | quiet |
| 2026-10-17 | `remote/how.mise/mise` | 2026-10-17T060052993990 -> 2026-10-17T122756085852 | 2 changed | quiet |
| 2026-10-17 | `remote/com.thefilmradar/filmlab` | 2026-10-17T055305118051 -> 2026-10-17T122754176967 | 2 added | quiet |
| 2026-10-17 | `remote/com.helpyself/tools` | 2026-10-17T055211519097 -> 2026-10-17T122743515213 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.qxxx5vyd77-byte/directors-lookbook` | 2026-10-17T055029011048 -> 2026-10-17T122740601660 | 1 changed | quiet |
| 2026-10-17 | `remote/io.dropyour/dropyour` | 2026-10-17T055904711805 -> 2026-10-17T122740925782 | 5 changed | quiet |
| 2026-10-17 | `remote/io.github.fxmacrodata/fxmacrodata` | 2026-10-17T054541578538 -> 2026-10-17T122737138187 | 1 changed | quiet |
| 2026-10-17 | `remote/com.tkawen/intelligence-gateway` | 2026-10-17T110446561818 -> 2026-10-17T122737697562 | 1 changed | quiet |
| 2026-10-17 | `remote/dev.latamref/reference-data` | 2026-10-17T110202326627 -> 2026-10-17T122730306698 | 3 added | quiet |
| 2026-10-17 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-17T110021861921 -> 2026-10-17T122727105678 | 2 changed | quiet |
| 2026-10-17 | `remote/uk.co.buildbatch/buildbatch` | 2026-10-17T065545415422 -> 2026-10-17T122716806803 | 1 changed | quiet |
| 2026-10-17 | `remote/dev.euroref/reference-data` | 2026-10-17T105945259751 -> 2026-10-17T122714756990 | 3 added | quiet |
| 2026-10-17 | `remote/co.bitcoinyield/yields` | 2026-10-17T054331032452 -> 2026-10-17T122713414527 | 2 changed (every tool) | quiet |
| 2026-10-17 | `remote/dev.workers.kikoribera03.flat-rate-llm/x402-tools` | 2026-10-17T054553623653 -> 2026-10-17T122709166188 | 1 changed, 1 added | quiet |
| 2026-10-17 | `remote/dev.ausref/reference-data` | 2026-10-17T105819509080 -> 2026-10-17T122712791159 | 3 added | quiet |
| 2026-10-17 | `remote/com.dechonet/mcp` | 2026-10-17T105919982864 -> 2026-10-17T122710318269 | 1 added | quiet |
| 2026-10-17 | `remote/dev.asiaref/reference-data` | 2026-10-17T105816575119 -> 2026-10-17T122712106123 | 3 added | quiet |
| 2026-10-17 | `remote/com.buyingmesh/procurement` | 2026-10-17T054200892791 -> 2026-10-17T122706316703 | 1 changed, 1 added | quiet |
| 2026-10-17 | `remote/io.taifoon/coordination-layer` | 2026-10-17T054723747435 -> 2026-10-17T122707945073 | 2 changed | review |
| 2026-10-17 | `remote/com.chateaupedia/chateaux` | 2026-10-17T105845148404 -> 2026-10-17T122703011105 | 1 changed | quiet |
| 2026-10-17 | `remote/com.cooperemail/cooper-email` | 2026-10-17T054450868864 -> 2026-10-17T122701806873 | 3 changed | quiet |
| 2026-10-17 | `remote/com.applystead/jobs` | 2026-10-17T054138184251 -> 2026-10-17T122702464748 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.alessandropeng/arc-flash-platform` | 2026-10-17T054416121279 -> 2026-10-17T122655974331 | 1 changed | quiet |
| 2026-10-17 | `remote/exchange.ravn/ravn` | 2026-10-17T054353534541 -> 2026-10-17T122655301054 | 2 changed | quiet |
| 2026-10-17 | `remote/ai.betslipdoctor/mcp` | 2026-10-17T054011042786 -> 2026-10-17T122654072175 | 1 changed | quiet |
| 2026-10-17 | `remote/io.agentsvc/services` | 2026-10-17T105517996770 -> 2026-10-17T122650080203 | 124 changed | quiet |
| 2026-10-17 | `remote/app.agentbit/mcp` | 2026-10-17T105508536831 -> 2026-10-17T122648731144 | 1 changed | quiet |
| 2026-10-17 | `remote/ch.kulalabs.agents/jobflow` | 2026-10-17T105522440533 -> 2026-10-17T122641720289 | 1 added | quiet |
| 2026-10-17 | `remote/dev.afriref/reference-data` | 2026-10-17T105411008020 -> 2026-10-17T122641993824 | 3 added | quiet |
| 2026-10-17 | `remote/com.immersivecommons/floor10` | 2026-10-17T055942283508 -> 2026-10-17T111242113497 | 1 added | quiet |
| 2026-10-17 | `remote/fi.akkilahdot/travel-search` | 2026-10-17T073756919270 -> 2026-10-17T111223508210 | 1 changed | quiet |
| 2026-10-17 | `remote/us.srv.vehcdj664efetfrsolne5umanq/quoteproof-mcp` | 2026-10-17T055900696034 -> 2026-10-17T111205518506 | 2 changed | quiet |
| 2026-10-17 | `remote/tech.varexis/varexis-index` | 2026-10-17T055858903246 -> 2026-10-17T111203065169 | 3 changed | quiet |
| 2026-10-17 | `remote/io.github.sharan01x/usetested` | 2026-10-08T135434290106 -> 2026-10-17T111201777627 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-17T070501096067 -> 2026-10-17T111142660726 | 1 changed | quiet |
| 2026-10-17 | `remote/dev.tanod/web` | 2026-10-17T055831144409 -> 2026-10-17T111139383155 | 2 changed, 1 added | quiet |
| 2026-10-17 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-17T073625757198 -> 2026-10-17T111120466946 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 21628 substantive, 8135 that changed only numbers (a catalogue counter ticking, a date), 446 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 14726 | 7201 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 126 | 126 | 0 | 0 |
| `sistaminuten.se` | 108 | 4 | 0 | 104 |
| `afbudsrejser.dk` | 107 | 4 | 0 | 103 |
| `akkilahdot.fi` | 107 | 4 | 0 | 103 |
| `restplass.no` | 107 | 4 | 0 | 103 |
| `socialloop.ai` | 105 | 105 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `fundinglandscape.com` | 78 | 46 | 32 | 0 |
| `remoshift.com` | 78 | 5 | 73 | 0 |
| 3772 other operators | 11576 | 11038 | 505 | 33 |
