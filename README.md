# MCP server tool changes

Last change observed 2026-10-13T02:16:41+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10495 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 23695 hosted endpoints (read daily, and every four hours while they keep changing).

26292 changes to a tool definition: 870 npm releases (624 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 25422 readings of hosted servers that found their tools changed; 401 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-13 | `remote/fi.akkilahdot/travel-search` | 2026-10-12T181514153491 -> 2026-10-13T021646254550 | 1 changed | quiet |
| 2026-10-13 | `remote/com.voyscout/price-history` | 2026-10-12T181511130266 -> 2026-10-13T021642604994 | 1 changed | quiet |
| 2026-10-13 | `remote/com.tickerinside/tickerinside-mcp` | 2026-10-12T181502703889 -> 2026-10-13T021641589815 | 1 changed | quiet |
| 2026-10-13 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-12T181458357076 -> 2026-10-13T021637185290 | 1 changed | quiet |
| 2026-10-13 | `remote/com.swarmmemo/bulletin` | 2026-10-12T181502868704 -> 2026-10-13T021641441693 | 3 changed | quiet |
| 2026-10-13 | `remote/ch.swisslivingindex/swiss-living-index` | 2026-10-12T181502367919 -> 2026-10-13T021637344961 | 3 added | quiet |
| 2026-10-13 | `remote/com.remoshift/jobs` | 2026-10-12T181457761236 -> 2026-10-13T021633102768 | 1 changed | quiet |
| 2026-10-13 | `remote/com.multicinesortega/cartelera` | 2026-10-12T063536529359 -> 2026-10-13T021629182983 | 1 changed | quiet |
| 2026-10-13 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-12T063523824078 -> 2026-10-13T021620875968 | 46 changed | review |
| 2026-10-13 | `remote/ai.switchapp/switch` | 2026-10-11T150659361110 -> 2026-10-13T021623507646 | 1 changed | quiet |
| 2026-10-13 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-12T000128966645 -> 2026-10-13T021621663714 | 1 changed | quiet |
| 2026-10-13 | `remote/com.restaurantdoctorai/profit-check` | 2026-10-12T063522799809 -> 2026-10-13T021619717986 | 1 changed, 1 added | quiet |
| 2026-10-13 | `remote/com.quintadb/mcp` | 2026-10-12T181437938318 -> 2026-10-13T021620514396 | 5 changed | quiet |
| 2026-10-13 | `remote/com.squirrelscan/squirrelscan` | 2026-10-12T181438152583 -> 2026-10-13T021623474882 | 1 changed | review |
| 2026-10-13 | `remote/no.restplass/travel-search` | 2026-10-12T181456994484 -> 2026-10-13T021618315252 | 1 changed | quiet |
| 2026-10-13 | `remote/com.jojapi/product-barcode-api` | 2026-10-12T181435269787 -> 2026-10-13T021619369155 | 1 changed | quiet |
| 2026-10-13 | `remote/io.github.equinoxaifinance-rgb/fluxproof` | 2026-10-11T150638923863 -> 2026-10-13T021616601904 | 6 changed (every tool) | quiet |
| 2026-10-13 | `remote/dk.afbudsrejser/travel-search` | 2026-10-12T181457219670 -> 2026-10-13T021617751165 | 1 changed | quiet |
| 2026-10-13 | `remote/ua.com.quintadb/mcp` | 2026-10-12T181456277842 -> 2026-10-13T021618332173 | 5 changed | quiet |
| 2026-10-13 | `remote/space.studiosphere/pulse` | 2026-10-12T181447028819 -> 2026-10-13T021619321097 | 3 changed | quiet |
| 2026-10-13 | `remote/io.github.tryflask/flask` | 2026-10-12T181431906081 -> 2026-10-13T021616631221 | 5 changed | quiet |
| 2026-10-13 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-10-12T181433054388 -> 2026-10-13T021615822904 | 2 changed | quiet |
| 2026-10-13 | `remote/directory.nohumans/registry` | 2026-10-12T181432341213 -> 2026-10-13T021616030852 | 1 changed | quiet |
| 2026-10-13 | `remote/ai.rokha/rokha` | 2026-10-11T150655910578 -> 2026-10-13T021615380821 | 22 changed, 25 added | review |
| 2026-10-13 | `remote/io.github.richardsolomou/praetorium` | 2026-10-12T181454533248 -> 2026-10-13T021615539979 | 1 changed | quiet |
| 2026-10-13 | `remote/se.sistaminuten/travel-search` | 2026-10-12T181443473015 -> 2026-10-13T021613784087 | 1 changed | quiet |
| 2026-10-13 | `remote/com.thefomite/fomite` | 2026-10-12T000127425755 -> 2026-10-13T021612586777 | 1 changed | quiet |
| 2026-10-13 | `remote/com.jojapi/swift-ai` | 2026-10-12T181442131972 -> 2026-10-13T021619993568 | 1 changed | quiet |
| 2026-10-13 | `remote/com.idevice/wearables` | 2026-10-12T000116137687 -> 2026-10-13T021613547536 | 9 changed | quiet |
| 2026-10-13 | `remote/ru.quintadb/mcp` | 2026-10-12T181441552808 -> 2026-10-13T021613707001 | 5 changed | quiet |
| 2026-10-13 | `remote/io.github.equinoxaifinance-rgb/proof-fetch` | 2026-10-11T150642698148 -> 2026-10-13T021611306115 | 3 changed (every tool) | quiet |
| 2026-10-13 | `remote/net.isitdns/isitdns` | 2026-10-12T181435809645 -> 2026-10-13T021610407817 | 3 changed | quiet |
| 2026-10-13 | `remote/com.knowjudges/knowjudges` | 2026-10-12T181438703943 -> 2026-10-13T021611483735 | 3 changed | quiet |
| 2026-10-13 | `remote/ai.autonomad/travel` | 2026-10-12T181435930652 -> 2026-10-13T021610242243 | 1 changed | quiet |
| 2026-10-13 | `remote/wedding.aisle/aisle` | 2026-10-12T181443024853 -> 2026-10-13T021611026950 | 3 changed, 1 added | quiet |
| 2026-10-13 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-12T181434732262 -> 2026-10-13T021609904696 | 3 changed | quiet |
| 2026-10-13 | `remote/cloud.dchub/mcp-server` | 2026-10-12T063526645094 -> 2026-10-13T021616719238 | 3 changed | quiet |
| 2026-10-13 | `remote/net.hotelrefund/price-tracker` | 2026-10-12T000119152625 -> 2026-10-13T021611186840 | 1 changed | quiet |
| 2026-10-13 | `remote/me.agentworld/agentworld-mcp` | 2026-10-11T150631995666 -> 2026-10-13T021607545618 | 2 added | quiet |
| 2026-10-13 | `remote/io.github.0xinsider/mcp` | 2026-10-12T181430203468 -> 2026-10-13T021607490861 | 5 changed | quiet |
| 2026-10-13 | `remote/io.agentsvc/services` | 2026-10-12T181431676725 -> 2026-10-13T021609277548 | 4 changed | quiet |
| 2026-10-13 | `remote/com.uplika/uplika` | 2026-10-12T181433540765 -> 2026-10-13T021610108944 | 9 changed | quiet |
| 2026-10-13 | `remote/app.flaim/mcp` | 2026-10-12T000118024106 -> 2026-10-13T021608505716 | 8 changed | quiet |
| 2026-10-13 | `remote/io.github.34r7h/handoff` | 2026-10-12T181433004429 -> 2026-10-13T021614826299 | 2 changed | quiet |
| 2026-10-13 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt` | 2026-10-12T181431392437 -> 2026-10-13T021605704841 | 1 changed | quiet |
| 2026-10-13 | `remote/io.github.whiteknightonhorse/apibase` | 2026-10-12T181431054492 -> 2026-10-13T021604876040 | 1 changed, 12 added | quiet |
| 2026-10-13 | `remote/com.hookdetector/hookdetector` | 2026-10-12T181429232900 -> 2026-10-13T021604717676 | 1 changed | quiet |
| 2026-10-13 | `remote/com.askmatchbox/matchbox` | 2026-10-12T000113731710 -> 2026-10-13T021605750029 | 2 changed | quiet |
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

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 17823 substantive, 8054 that changed only numbers (a catalogue counter ticking, a date), 415 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 13231 | 5706 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 538 | 538 | 0 | 0 |
| `sistaminuten.se` | 99 | 2 | 0 | 97 |
| `afbudsrejser.dk` | 98 | 2 | 0 | 96 |
| `akkilahdot.fi` | 98 | 2 | 0 | 96 |
| `restplass.no` | 98 | 2 | 0 | 96 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `socialloop.ai` | 96 | 96 | 0 | 0 |
| `caseyjhand.com` | 77 | 77 | 0 | 0 |
| `remoshift.com` | 71 | 4 | 67 | 0 |
| `fundinglandscape.com` | 70 | 41 | 29 | 0 |
| 3054 other operators | 9378 | 8915 | 433 | 30 |
