# MCP server tool changes

Last change observed 2026-10-11T15:07:04+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10128 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 21701 hosted endpoints (read daily, and every four hours while they keep changing).

26041 changes to a tool definition: 870 npm releases (624 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 25171 readings of hosted servers that found their tools changed; 394 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-11 | `remote/fi.akkilahdot/travel-search` | 2026-10-11T063115105057 -> 2026-10-11T150706262800 | 1 changed | quiet |
| 2026-10-11 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-11T063114226823 -> 2026-10-11T150705326773 | 1 changed | quiet |
| 2026-10-11 | `remote/com.swarmmemo/bulletin` | 2026-10-10T235306204207 -> 2026-10-11T150704127310 | 4 changed, 2 added | quiet |
| 2026-10-11 | `remote/ch.swisslivingindex/swiss-living-index` | 2026-10-10T144735253823 -> 2026-10-11T150703110565 | 3 added | quiet |
| 2026-10-11 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-11T063112621236 -> 2026-10-11T150702842757 | 1 changed | quiet |
| 2026-10-11 | `remote/online.pageaudit/pageaudit` | 2026-10-10T144730434015 -> 2026-10-11T150702262939 | 1 changed | quiet |
| 2026-10-11 | `remote/io.github.deviljin17/remode` | 2026-10-10T062525313789 -> 2026-10-11T150701504146 | 1 changed | quiet |
| 2026-10-11 | `remote/com.remoshift/jobs` | 2026-10-11T063111992865 -> 2026-10-11T150702055705 | 1 changed | quiet |
| 2026-10-11 | `remote/no.restplass/travel-search` | 2026-10-11T063109199696 -> 2026-10-11T150658790552 | 1 changed | quiet |
| 2026-10-11 | `remote/dk.afbudsrejser/travel-search` | 2026-10-11T063108613031 -> 2026-10-11T150658812800 | 1 changed | quiet |
| 2026-10-11 | `remote/com.sonarconnections/sonar-connections` | 2026-10-11T063108794852 -> 2026-10-11T150659603573 | 22 changed | quiet |
| 2026-10-11 | `remote/io.github.Timothymycompc/solana-pulse-gateway` | 2026-10-11T063106540774 -> 2026-10-11T150657017462 | 6 changed, 9 added, 14 removed (every tool) | review |
| 2026-10-11 | `remote/com.vendooly/vendooly` | 2026-10-09T153607033082 -> 2026-10-11T150700831026 | 2 changed | quiet |
| 2026-10-11 | `remote/ai.rokha/rokha` | 2026-10-10T202115184572 -> 2026-10-11T150655910578 | 4 changed, 2 added, 1 removed | quiet |
| 2026-10-11 | `remote/ua.com.quintadb/mcp` | 2026-10-10T062537403071 -> 2026-10-11T150657460135 | 2 changed | quiet |
| 2026-10-11 | `remote/io.github.Fizzl13/presign-guard` | 2026-10-11T063105144358 -> 2026-10-11T150655647232 | 2 changed | quiet |
| 2026-10-11 | `remote/com.qumge/skills` | 2026-10-10T062535289902 -> 2026-10-11T150655126958 | 5 changed, 1 added | quiet |
| 2026-10-11 | `remote/io.github.richardsolomou/praetorium` | 2026-10-11T063105998455 -> 2026-10-11T150655596244 | 1 changed | quiet |
| 2026-10-11 | `remote/com.sourcey/sourcey` | 2026-10-09T153607381190 -> 2026-10-11T150654145043 | 3 changed | quiet |
| 2026-10-11 | `remote/ch.kulalabs.pazair/pazair` | 2026-10-10T202109433664 -> 2026-10-11T150655698846 | 71 changed, 1 added (every tool) | quiet |
| 2026-10-11 | `remote/ai.switchapp/switch` | 2026-10-11T063108744886 -> 2026-10-11T150659361110 | 6 changed | quiet |
| 2026-10-11 | `remote/so.darwin/darwin` | 2026-10-11T063102977655 -> 2026-10-11T150653710218 | 1 changed | quiet |
| 2026-10-11 | `remote/io.github.mirabello-consultancy/mcp-server` | 2026-10-09T153606025019 -> 2026-10-11T150653285440 | 1 changed | quiet |
| 2026-10-11 | `remote/com.idevice/wearables` | 2026-10-11T063100224343 -> 2026-10-11T150651711525 | 1 changed | quiet |
| 2026-10-11 | `remote/au.com.alpineai/factstamp` | 2026-10-09T064750219810 -> 2026-10-11T150649513156 | 1 changed | quiet |
| 2026-10-11 | `remote/io.github.bosmdavid-gif/dropthehassle` | 2026-10-11T063058715174 -> 2026-10-11T150649163296 | 1 changed, 4 added | quiet |
| 2026-10-11 | `remote/org.aspern/aspern` | 2026-10-10T202043425421 -> 2026-10-11T150648200631 | 6 changed | quiet |
| 2026-10-11 | `remote/et.bina/binasmart` | 2026-10-09T153547506351 -> 2026-10-11T150649897645 | 1 changed | quiet |
| 2026-10-11 | `remote/io.github.kiddhu/seekapi` | 2026-10-11T063056897120 -> 2026-10-11T150647810976 | 5 changed | review |
| 2026-10-11 | `remote/eu.sirenic/sirenic` | 2026-10-11T063058741674 -> 2026-10-11T150649758548 | 1 changed | review |
| 2026-10-11 | `remote/wedding.aisle/aisle` | 2026-10-11T063055336880 -> 2026-10-11T150646218173 | 5 changed | quiet |
| 2026-10-11 | `remote/se.sistaminuten/travel-search` | 2026-10-11T063055158472 -> 2026-10-11T150644972304 | 1 changed | quiet |
| 2026-10-11 | `remote/com.restaurantdoctorai/profit-check` | 2026-10-11T063059887509 -> 2026-10-11T150644407442 | 10 changed, 1 added | review |
| 2026-10-11 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-09T064743511734 -> 2026-10-11T150645101888 | 1 changed | quiet |
| 2026-10-11 | `remote/ru.quintadb/mcp` | 2026-10-10T062528130871 -> 2026-10-11T150645800144 | 2 changed | quiet |
| 2026-10-11 | `remote/ltd.qianyuan/qy-evolution` | 2026-10-10T144712869960 -> 2026-10-11T150644453915 | 1 changed | quiet |
| 2026-10-11 | `remote/com.thefilmradar/filmlab` | 2026-10-10T202044919743 -> 2026-10-11T150649334223 | 7 changed, 2 added | quiet |
| 2026-10-11 | `remote/com.quintadb/mcp` | 2026-10-10T062521880572 -> 2026-10-11T150644973658 | 2 changed | quiet |
| 2026-10-11 | `remote/trade.loomdesk/loomdesk` | 2026-10-11T063105292614 -> 2026-10-11T150645828625 | 1 changed | quiet |
| 2026-10-11 | `remote/io.github.equinoxaifinance-rgb/proof-fetch` | 2026-10-10T144710810616 -> 2026-10-11T150642698148 | 3 changed (every tool) | quiet |
| 2026-10-11 | `remote/dev.mcphost/mcphost` | 2026-10-09T064733322532 -> 2026-10-11T150642896737 | 1 changed | quiet |
| 2026-10-11 | `remote/com.plainrouter/mcp` | 2026-10-10T144715601157 -> 2026-10-11T150644188443 | 5 changed | quiet |
| 2026-10-11 | `remote/pro.particle/particle-pro` | 2026-10-11T063050514599 -> 2026-10-11T150640853812 | 9 changed | quiet |
| 2026-10-11 | `remote/com.squirrelscan/squirrelscan` | 2026-10-11T063100833429 -> 2026-10-11T150644458825 | 2 changed | quiet |
| 2026-10-11 | `remote/com.knowjudges/knowjudges` | 2026-10-10T144704504882 -> 2026-10-11T150641025542 | 2 changed | quiet |
| 2026-10-11 | `remote/co.ainumbers/tools` | 2026-10-11T063057218187 -> 2026-10-11T150640831166 | 2 changed | quiet |
| 2026-10-11 | `remote/com.ikeytz/maps` | 2026-10-10T144706640850 -> 2026-10-11T150641100355 | 1 changed | quiet |
| 2026-10-11 | `remote/com.howtomakemoneyonsnapchat/creator-monetization` | 2026-10-10T062512200497 -> 2026-10-11T150640970664 | 2 added | quiet |
| 2026-10-11 | `remote/ai.autonomad/travel` | 2026-10-10T062515735719 -> 2026-10-11T150639832190 | 9 changed, 1 added (every tool) | quiet |
| 2026-10-11 | `remote/io.github.equinoxaifinance-rgb/fluxproof` | 2026-10-10T062511042812 -> 2026-10-11T150638923863 | 6 changed (every tool) | quiet |
| 2026-10-11 | `remote/com.cooperemail/cooper-email` | 2026-10-11T063054270263 -> 2026-10-11T150638123542 | 1 changed, 2 added | quiet |
| 2026-10-11 | `remote/com.enhancedint/enhanced-intelligence` | 2026-10-10T144701277493 -> 2026-10-11T150639480204 | 2 changed | quiet |
| 2026-10-11 | `remote/co.homemaster/homemaster` | 2026-10-09T064727740500 -> 2026-10-11T150641075094 | 1 changed | quiet |
| 2026-10-11 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-10-10T235249034835 -> 2026-10-11T150637181692 | 2 changed | quiet |
| 2026-10-11 | `remote/directory.nohumans/registry` | 2026-10-11T063053321890 -> 2026-10-11T150636779414 | 1 changed | quiet |
| 2026-10-11 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-10T202038165828 -> 2026-10-11T150636606439 | 2 changed | quiet |
| 2026-10-11 | `remote/io.github.snefhew/factline` | 2026-10-11T063103951734 -> 2026-10-11T150638673820 | 1 added | review |
| 2026-10-11 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt` | 2026-10-11T063102192204 -> 2026-10-11T150636006992 | 7 changed, 5 added | quiet |
| 2026-10-11 | `remote/ch.kulalabs.agents/jobflow` | 2026-10-10T202028390022 -> 2026-10-11T150636770276 | 71 changed, 1 added | quiet |
| 2026-10-11 | `remote/domains.audit/appraisal` | 2026-10-09T064721186093 -> 2026-10-11T150634323024 | 4 changed, 2 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 17623 substantive, 8026 that changed only numbers (a catalogue counter ticking, a date), 392 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 13231 | 5706 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 538 | 538 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `sistaminuten.se` | 94 | 2 | 0 | 92 |
| `afbudsrejser.dk` | 93 | 2 | 0 | 91 |
| `akkilahdot.fi` | 93 | 2 | 0 | 91 |
| `restplass.no` | 93 | 2 | 0 | 91 |
| `socialloop.ai` | 91 | 91 | 0 | 0 |
| `caseyjhand.com` | 77 | 77 | 0 | 0 |
| `dayze.com` | 69 | 69 | 0 | 0 |
| `fundinglandscape.com` | 66 | 37 | 29 | 0 |
| 3054 other operators | 9158 | 8659 | 472 | 27 |
