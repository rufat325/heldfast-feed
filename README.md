# MCP server tool changes

Last change observed 2026-11-12T17:09:51+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

94966 changes to a tool definition: 4016 npm releases (3770 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 90950 readings of hosted servers that found their tools changed; 3845 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-12 | `remote/no.restplass/travel-search` | 2026-11-12T155103302182 -> 2026-11-12T170952752415 | 1 changed | quiet |
| 2026-11-12 | `remote/app.postel/postel` | 2026-11-12T155059448102 -> 2026-11-12T170952061793 | 3 changed | quiet |
| 2026-11-12 | `remote/io.github.CodePhantom-1/ddmarketer-mcp` | 2026-11-12T155017391588 -> 2026-11-12T170949219789 | 1 changed | quiet |
| 2026-11-12 | `remote/dk.afbudsrejser/travel-search` | 2026-11-12T154956208628 -> 2026-11-12T170948622204 | 1 changed | quiet |
| 2026-11-12 | `remote/com.kaicalls/kaicalls.1` | 2026-11-12T155316905942 -> 2026-11-12T170947269043 | 19 changed, 1 added | quiet |
| 2026-11-12 | `remote/studio.gradients/mcp` | 2026-11-12T155305782058 -> 2026-11-12T171005136795 | 1 changed | quiet |
| 2026-11-12 | `remote/fi.akkilahdot/travel-search` | 2026-11-12T155240708470 -> 2026-11-12T170941051795 | 1 changed | quiet |
| 2026-11-12 | `remote/com.swiftprobate/probate` | 2026-11-12T155049305923 -> 2026-11-12T170940053374 | 3 changed | quiet |
| 2026-11-12 | `remote/se.sistaminuten/travel-search` | 2026-11-12T155044439003 -> 2026-11-12T170939736423 | 1 changed | quiet |
| 2026-11-12 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-12T074801335254 -> 2026-11-12T170941610019 | 8 added | quiet |
| 2026-11-12 | `remote/com.kaicalls/kaicalls` | 2026-11-12T155022804215 -> 2026-11-12T170937569584 | 50 changed, 2 added | quiet |
| 2026-11-12 | `remote/ru.vedarai/mcp` | 2026-11-12T155151858189 -> 2026-11-12T170938054321 | 1 changed | quiet |
| 2026-11-12 | `remote/io.github.christianscode1994/volatiai-mcp` | 2026-11-12T154918472237 -> 2026-11-12T170930710766 | 2 added | quiet |
| 2026-11-12 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-12T155018960866 -> 2026-11-12T170921205501 | 1 changed | quiet |
| 2026-11-12 | `remote/com.googleapis.run/mcp` | 2026-11-12T154842892308 -> 2026-11-12T170912923216 | 1 changed | quiet |
| 2026-11-12 | `remote/xyz.pokeka/card-prices` | 2026-11-12T154544576647 -> 2026-11-12T170905327862 | 1 changed | quiet |
| 2026-11-12 | `remote/io.github.scraping-api-plans/web-data-plan-finder` | 2026-11-12T154746122841 -> 2026-11-12T170906937895 | 9 changed | quiet |
| 2026-11-12 | `remote/ai.pipefire/pipefire` | 2026-11-12T154538698500 -> 2026-11-12T170904106024 | 6 changed | quiet |
| 2026-11-12 | `remote/com.owlchart/owlchart` | 2026-11-12T154509896987 -> 2026-11-12T170900855248 | 1 changed, 1 added | quiet |
| 2026-11-12 | `remote/io.outil/outil` | 2026-11-12T154510546139 -> 2026-11-12T170900933850 | 3 added | quiet |
| 2026-11-12 | `remote/io.github.smarterweather/weather` | 2026-11-12T074720821863 -> 2026-11-12T170857489703 | 2 changed | quiet |
| 2026-11-12 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-12T154616603327 -> 2026-11-12T170855165333 | 10 added | quiet |
| 2026-11-12 | `remote/me.miow/miow` | 2026-11-12T154415247740 -> 2026-11-12T170852969989 | 2 changed | quiet |
| 2026-11-12 | `remote/com.mosaisley/cantina` | 2026-11-10T152317860662 -> 2026-11-12T170853953892 | 1 changed | quiet |
| 2026-11-12 | `remote/com.googleapis.memorystore/mcp` | 2026-11-12T154609968615 -> 2026-11-12T170853113497 | 7 changed | quiet |
| 2026-11-12 | `remote/eu.tradedashboard/eu-trade-explorer` | 2026-11-11T164110295910 -> 2026-11-12T170853968032 | 9 changed | quiet |
| 2026-11-12 | `remote/work.finder/jobs` | 2026-11-11T145056789299 -> 2026-11-12T170848529760 | 2 changed | quiet |
| 2026-11-12 | `remote/net.clickwise/mcp` | 2026-11-12T154409023255 -> 2026-11-12T170848027657 | 1 changed | quiet |
| 2026-11-12 | `remote/io.github.faxforagents/faxforagents-mcp` | 2026-11-12T154144017780 -> 2026-11-12T170848568255 | 1 changed | quiet |
| 2026-11-12 | `remote/com.ortexo/mcp` | 2026-11-12T154439522609 -> 2026-11-12T170847913283 | 2 changed | quiet |
| 2026-11-12 | `remote/io.echelongraph/echelongraph-mcp` | 2026-11-11T230817400246 -> 2026-11-12T170846767027 | 2 changed | quiet |
| 2026-11-12 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-11-12T074713857171 -> 2026-11-12T170844791865 | 2 changed | review |
| 2026-11-12 | `remote/com.nodecraft/mcp` | 2026-11-10T152119147180 -> 2026-11-12T170845603032 | 1 changed, 2 added | quiet |
| 2026-11-12 | `remote/com.jointextkit/textkit` | 2026-11-12T074712189878 -> 2026-11-12T170842328274 | 2 changed | quiet |
| 2026-11-12 | `remote/tax.terminal/filing` | 2026-11-11T071343233572 -> 2026-11-12T170837685098 | 1 changed | quiet |
| 2026-11-12 | `remote/pro.aicut/aicut` | 2026-11-12T154222186086 -> 2026-11-12T170836550657 | 1 changed | quiet |
| 2026-11-12 | `remote/com.jabbertoon/cartoon-studio` | 2026-11-12T153922859030 -> 2026-11-12T170835171835 | 1 changed | quiet |
| 2026-11-12 | `remote/fun.make/makefun` | 2026-11-12T154153867391 -> 2026-11-12T170833383189 | 1 changed | quiet |
| 2026-11-12 | `remote/com.heynutcracker/nutcracker` | 2026-11-12T153851672319 -> 2026-11-12T170833129256 | 2 changed | quiet |
| 2026-11-12 | `remote/app.liquidvision/derivatives` | 2026-11-12T154137453726 -> 2026-11-12T170832589809 | 2 changed | quiet |
| 2026-11-12 | `remote/io.github.theharrisontruong-web/storefront-grader` | 2026-11-12T153831999478 -> 2026-11-12T170830442085 | 1 added | quiet |
| 2026-11-12 | `remote/io.github.obrientt/landfiller` | 2026-11-12T154120080341 -> 2026-11-12T170829649219 | 1 changed | quiet |
| 2026-11-12 | `remote/com.gangwaze/cruise` | 2026-11-10T151640890198 -> 2026-11-12T170828620196 | 1 changed | quiet |
| 2026-11-12 | `remote/ai.instabids/instabids` | 2026-11-12T153849606441 -> 2026-11-12T170826451054 | 3 changed | quiet |
| 2026-11-12 | `remote/net.fundz/fundz` | 2026-11-11T144900099043 -> 2026-11-12T170827425492 | 3 changed, 4 added | quiet |
| 2026-11-12 | `remote/com.masteringfinancialmarkets/mfm` | 2026-11-10T152048615403 -> 2026-11-12T170825448722 | 3 changed | quiet |
| 2026-11-12 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt.2` | 2026-11-12T074706283850 -> 2026-11-12T170823517371 | 1 changed | quiet |
| 2026-11-12 | `remote/app.vercel.fork-for-agents/fork` | 2026-11-12T153812155003 -> 2026-11-12T170818899490 | 1 changed | quiet |
| 2026-11-12 | `remote/social.flayr/flayr` | 2026-11-12T153641149426 -> 2026-11-12T170816748659 | 1 changed, 2 added | quiet |
| 2026-11-12 | `remote/com.fanduelapi/server` | 2026-11-11T071258626911 -> 2026-11-12T170814712691 | 5 changed | review |
| 2026-11-12 | `remote/io.taifoon/coordination-layer` | 2026-11-12T074651639164 -> 2026-11-12T170817501694 | 1 removed | quiet |
| 2026-11-12 | `remote/com.googleapis.datastream/mcp` | 2026-11-12T153642083013 -> 2026-11-12T170808630689 | 3 changed | quiet |
| 2026-11-12 | `remote/ai.commercebook/commercebook` | 2026-11-12T153449207825 -> 2026-11-12T170810160931 | 1 changed | quiet |
| 2026-11-12 | `remote/lu.chathome/chathome` | 2026-11-12T153430135614 -> 2026-11-12T170808664792 | 2 changed | quiet |
| 2026-11-12 | `remote/now.carejobs/healthcare-jobs` | 2026-11-12T153420855416 -> 2026-11-12T170807149622 | 1 changed | quiet |
| 2026-11-12 | `remote/io.github.midnight232/crypto-pulse` | 2026-11-12T153509441047 -> 2026-11-12T170806597256 | 2 changed | quiet |
| 2026-11-12 | `remote/com.draftkingsapi/server` | 2026-11-12T074640569652 -> 2026-11-12T170805503872 | 1 changed, 1 added | quiet |
| 2026-11-12 | `remote/so.sightkick/mcp` | 2026-11-12T153311136455 -> 2026-11-12T170758646844 | 1 changed | quiet |
| 2026-11-12 | `remote/dev.arquestra/consulting-radar` | 2026-11-12T153323219953 -> 2026-11-12T170755629681 | 2 changed | quiet |
| 2026-11-12 | `remote/eu.sirenic/sirenic` | 2026-11-12T153233736936 -> 2026-11-12T170755061427 | 1 changed, 1 removed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 58925 substantive, 35068 that changed only numbers (a catalogue counter ticking, a date), 973 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 50678 | 17757 | 32921 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 2242 | 2242 | 0 | 0 |
| `caseyjhand.com` | 402 | 402 | 0 | 0 |
| `civai.co` | 314 | 314 | 0 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `revmesh2074.workers.dev` | 239 | 209 | 30 | 0 |
| `sistaminuten.se` | 227 | 6 | 0 | 221 |
| `afbudsrejser.dk` | 226 | 6 | 0 | 220 |
| `akkilahdot.fi` | 226 | 6 | 0 | 220 |
| `restplass.no` | 226 | 6 | 0 | 220 |
| `socialloop.ai` | 218 | 218 | 0 | 0 |
| 9135 other operators | 37369 | 35160 | 2117 | 92 |
