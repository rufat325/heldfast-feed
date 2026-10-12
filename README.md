# MCP server tool changes

Last change observed 2026-10-12T18:15:11+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10495 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 23695 hosted endpoints (read daily, and every four hours while they keep changing).

26244 changes to a tool definition: 870 npm releases (624 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 25374 readings of hosted servers that found their tools changed; 398 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-12 | `remote/com.ikeytz/website` | 2026-10-11T203729665432 -> 2026-10-12T181516066485 | 1 changed | quiet |
| 2026-10-12 | `remote/fi.akkilahdot/travel-search` | 2026-10-12T063538380392 -> 2026-10-12T181514153491 | 1 changed | quiet |
| 2026-10-12 | `remote/com.voyscout/price-history` | 2026-10-11T063114170686 -> 2026-10-12T181511130266 | 3 changed | quiet |
| 2026-10-12 | `remote/ru.vedarai/mcp` | 2026-10-12T063539076375 -> 2026-10-12T181508444301 | 1 added | quiet |
| 2026-10-12 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-12T063537155024 -> 2026-10-12T181503933679 | 1 changed | quiet |
| 2026-10-12 | `remote/com.tickerinside/tickerinside-mcp` | 2026-10-10T202057298579 -> 2026-10-12T181502703889 | 1 added | quiet |
| 2026-10-12 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-12T063536961694 -> 2026-10-12T181458357076 | 1 changed | quiet |
| 2026-10-12 | `remote/com.swarmmemo/bulletin` | 2026-10-12T000130682630 -> 2026-10-12T181502868704 | 1 changed | quiet |
| 2026-10-12 | `remote/ch.swisslivingindex/swiss-living-index` | 2026-10-11T203724187177 -> 2026-10-12T181502367919 | 1 added | quiet |
| 2026-10-12 | `remote/no.restplass/travel-search` | 2026-10-12T063531999392 -> 2026-10-12T181456994484 | 1 changed | quiet |
| 2026-10-12 | `remote/io.github.Timothymycompc/solana-pulse-gateway` | 2026-10-12T063530596429 -> 2026-10-12T181454653502 | 15 changed (every tool) | review |
| 2026-10-12 | `remote/dk.afbudsrejser/travel-search` | 2026-10-12T063531955205 -> 2026-10-12T181457219670 | 1 changed | quiet |
| 2026-10-12 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-11T203659744579 -> 2026-10-12T181454859184 | 13 changed | quiet |
| 2026-10-12 | `remote/ai.trydock/dock` | 2026-10-10T062539390496 -> 2026-10-12T181455704721 | 1 changed | quiet |
| 2026-10-12 | `remote/ai.shorti/shorti` | 2026-10-12T063538203829 -> 2026-10-12T181502763656 | 12 changed | quiet |
| 2026-10-12 | `remote/ua.com.quintadb/mcp` | 2026-10-11T203700967226 -> 2026-10-12T181456277842 | 5 changed | quiet |
| 2026-10-12 | `remote/com.remoshift/jobs` | 2026-10-12T063536444528 -> 2026-10-12T181457761236 | 1 changed | quiet |
| 2026-10-12 | `remote/io.github.richardsolomou/praetorium` | 2026-10-12T063530356801 -> 2026-10-12T181454533248 | 3 changed | quiet |
| 2026-10-12 | `remote/ch.kulalabs.pazair/pazair` | 2026-10-12T063529623507 -> 2026-10-12T181454220024 | 2 changed | quiet |
| 2026-10-12 | `remote/com.sourcey/sourcey` | 2026-10-12T000117697201 -> 2026-10-12T181452896182 | 1 changed | quiet |
| 2026-10-12 | `remote/eu.paymentslaw/legislation` | 2026-10-10T235255631718 -> 2026-10-12T181452920178 | 1 changed | quiet |
| 2026-10-12 | `remote/online.pageaudit/pageaudit` | 2026-10-11T150702262939 -> 2026-10-12T181456014729 | 1 changed | quiet |
| 2026-10-12 | `remote/io.github.HelloSafe/travel-insurance` | 2026-10-10T062527215799 -> 2026-10-12T181450043060 | 1 changed | quiet |
| 2026-10-12 | `remote/io.github.bosmdavid-gif/dropthehassle` | 2026-10-11T150649163296 -> 2026-10-12T181448790987 | 1 changed | quiet |
| 2026-10-12 | `remote/com.vendooly/vendooly` | 2026-10-11T150700831026 -> 2026-10-12T181452339520 | 1 added | quiet |
| 2026-10-12 | `remote/com.mooncatcherwire/wire` | 2026-10-11T203720815225 -> 2026-10-12T181452347999 | 3 changed, 1 added | quiet |
| 2026-10-12 | `remote/org.aspern/aspern` | 2026-10-12T063524180105 -> 2026-10-12T181446738818 | 3 changed, 3 added | quiet |
| 2026-10-12 | `remote/space.studiosphere/pulse` | 2026-10-10T062520999241 -> 2026-10-12T181447028819 | 3 changed | quiet |
| 2026-10-12 | `remote/wedding.aisle/aisle` | 2026-10-12T063522278171 -> 2026-10-12T181443024853 | 9 changed, 2 added | quiet |
| 2026-10-12 | `remote/se.sistaminuten/travel-search` | 2026-10-12T063534485608 -> 2026-10-12T181443473015 | 1 changed | quiet |
| 2026-10-12 | `remote/com.followontours/cricket-travel` | 2026-10-10T144716063915 -> 2026-10-12T181443141969 | 8 changed (every tool) | quiet |
| 2026-10-12 | `remote/ru.quintadb/mcp` | 2026-10-11T203704265018 -> 2026-10-12T181441552808 | 5 changed | quiet |
| 2026-10-12 | `remote/com.youspot/youspot` | 2026-10-10T202048178843 -> 2026-10-12T181439432469 | 1 changed, 1 added | quiet |
| 2026-10-12 | `remote/ai.satohub/onchain-agents` | 2026-10-12T063532252131 -> 2026-10-12T181441053882 | 4 changed | quiet |
| 2026-10-12 | `remote/com.jojapi/swift-ai` | 2026-10-12T063534237019 -> 2026-10-12T181442131972 | 4 changed | quiet |
| 2026-10-12 | `remote/io.github.Embassy-of-the-Free-Mind/sourcelibrary` | 2026-10-12T063524339704 -> 2026-10-12T181438472065 | 2 changed, 2 added | quiet |
| 2026-10-12 | `remote/gl.parse/mcp` | 2026-10-10T144706026786 -> 2026-10-12T181438461371 | 3 changed | quiet |
| 2026-10-12 | `remote/com.sfxmint/sounds` | 2026-10-11T063100229994 -> 2026-10-12T181437511673 | 5 changed | review |
| 2026-10-12 | `remote/com.quintadb/mcp` | 2026-10-11T203657516930 -> 2026-10-12T181437938318 | 5 changed | quiet |
| 2026-10-12 | `remote/ai.skuit/catalog` | 2026-10-12T063529558878 -> 2026-10-12T181437200083 | 1 changed | quiet |
| 2026-10-12 | `remote/io.github.minsooparkk/korea-tax-law-mcp` | 2026-10-10T062518194714 -> 2026-10-12T181437358080 | 3 changed | quiet |
| 2026-10-12 | `remote/dev.mcphost/mcphost` | 2026-10-12T063522442860 -> 2026-10-12T181436800100 | 11 changed, 2 added | quiet |
| 2026-10-12 | `remote/com.knowjudges/knowjudges` | 2026-10-11T203658705491 -> 2026-10-12T181438703943 | 1 changed | quiet |
| 2026-10-12 | `remote/ai.autonomad/travel` | 2026-10-11T150639832190 -> 2026-10-12T181435930652 | 2 changed | quiet |
| 2026-10-12 | `remote/net.isitdns/isitdns` | 2026-10-11T063048844631 -> 2026-10-12T181435809645 | 6 changed (every tool) | quiet |
| 2026-10-12 | `remote/com.squirrelscan/squirrelscan` | 2026-10-12T063522210700 -> 2026-10-12T181438152583 | 1 changed | quiet |
| 2026-10-12 | `remote/com.jojapi/product-barcode-api` | 2026-10-12T063521206267 -> 2026-10-12T181435269787 | 1 changed | quiet |
| 2026-10-12 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-12T000121110722 -> 2026-10-12T181434732262 | 3 changed | quiet |
| 2026-10-12 | `remote/com.enhancedint/enhanced-intelligence` | 2026-10-11T150639480204 -> 2026-10-12T181435217583 | 2 changed | quiet |
| 2026-10-12 | `remote/com.cooperemail/cooper-email` | 2026-10-11T150638123542 -> 2026-10-12T181432723624 | 1 added | quiet |
| 2026-10-12 | `remote/com.algotrada.cubicle/cubicle` | 2026-10-10T202036838681 -> 2026-10-12T181434387434 | 1 added | quiet |
| 2026-10-12 | `remote/io.github.mooshee/govgazette` | 2026-10-10T202041242106 -> 2026-10-12T181432709657 | 4 changed | quiet |
| 2026-10-12 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-10-12T000123583224 -> 2026-10-12T181433054388 | 3 changed | quiet |
| 2026-10-12 | `remote/io.github.34r7h/handoff` | 2026-10-12T063532680506 -> 2026-10-12T181433004429 | 9 changed, 4 added | quiet |
| 2026-10-12 | `remote/directory.nohumans/registry` | 2026-10-12T063518133324 -> 2026-10-12T181432341213 | 1 changed | quiet |
| 2026-10-12 | `remote/com.enhancedint/es-luxury` | 2026-10-11T150635141810 -> 2026-10-12T181435422787 | 2 changed | quiet |
| 2026-10-12 | `remote/io.github.tryflask/flask` | 2026-10-10T062506198086 -> 2026-10-12T181431906081 | 14 changed, 1 added | quiet |
| 2026-10-12 | `remote/io.github.snefhew/factline` | 2026-10-12T063532000266 -> 2026-10-12T181433100234 | 2 changed, 2 added | quiet |
| 2026-10-12 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt` | 2026-10-12T063531699485 -> 2026-10-12T181431392437 | 1 changed | quiet |
| 2026-10-12 | `remote/com.uplika/uplika` | 2026-10-11T150634121729 -> 2026-10-12T181433540765 | 2 changed, 3 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 17786 substantive, 8048 that changed only numbers (a catalogue counter ticking, a date), 410 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 13231 | 5706 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 538 | 538 | 0 | 0 |
| `sistaminuten.se` | 98 | 2 | 0 | 96 |
| `afbudsrejser.dk` | 97 | 2 | 0 | 95 |
| `akkilahdot.fi` | 97 | 2 | 0 | 95 |
| `restplass.no` | 97 | 2 | 0 | 95 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `socialloop.ai` | 95 | 95 | 0 | 0 |
| `caseyjhand.com` | 77 | 77 | 0 | 0 |
| `remoshift.com` | 70 | 4 | 66 | 0 |
| `dayze.com` | 69 | 69 | 0 | 0 |
| 3054 other operators | 9337 | 8851 | 457 | 29 |
