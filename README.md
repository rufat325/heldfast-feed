# MCP server tool changes

Last change observed 2026-10-13T12:13:12+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10495 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 23695 hosted endpoints (read daily, and every four hours while they keep changing).

26337 changes to a tool definition: 870 npm releases (624 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 25467 readings of hosted servers that found their tools changed; 401 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-13 | `remote/ru.vedarai/mcp` | 2026-10-12T181508444301 -> 2026-10-13T121314350236 | 7 changed | quiet |
| 2026-10-13 | `remote/fi.akkilahdot/travel-search` | 2026-10-13T021646254550 -> 2026-10-13T121313352219 | 1 changed | quiet |
| 2026-10-13 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-13T021637185290 -> 2026-10-13T121312458640 | 1 changed | quiet |
| 2026-10-13 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-12T181503933679 -> 2026-10-13T121313185137 | 1 changed | quiet |
| 2026-10-13 | `remote/ch.swisslivingindex/swiss-living-index` | 2026-10-13T021637344961 -> 2026-10-13T121312728704 | 1 changed, 2 added | quiet |
| 2026-10-13 | `remote/com.remoshift/jobs` | 2026-10-13T021633102768 -> 2026-10-13T121311764629 | 1 changed | quiet |
| 2026-10-13 | `remote/com.multicinesortega/cartelera` | 2026-10-13T021629182983 -> 2026-10-13T121312042905 | 1 changed | quiet |
| 2026-10-13 | `remote/com.mooncatcherwire/wire` | 2026-10-12T181452347999 -> 2026-10-13T121310623404 | 1 changed | quiet |
| 2026-10-13 | `remote/ai.switchapp/switch` | 2026-10-13T021623507646 -> 2026-10-13T121309764799 | 3 changed, 6 added | quiet |
| 2026-10-13 | `remote/io.github.si-imtiaz/leadquasar` | 2026-10-12T063533566133 -> 2026-10-13T121309042339 | 2 changed | quiet |
| 2026-10-13 | `remote/io.github.whiteknightonhorse/apibase` | 2026-10-13T021604876040 -> 2026-10-13T121307950452 | 9 removed | quiet |
| 2026-10-13 | `remote/no.restplass/travel-search` | 2026-10-13T021618315252 -> 2026-10-13T121304367288 | 1 changed | quiet |
| 2026-10-13 | `remote/io.github.Timothymycompc/solana-pulse-gateway` | 2026-10-12T181454653502 -> 2026-10-13T121302575938 | 15 added, 15 removed | quiet |
| 2026-10-13 | `remote/dk.afbudsrejser/travel-search` | 2026-10-13T021617751165 -> 2026-10-13T121304776042 | 1 changed | quiet |
| 2026-10-13 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-12T181454859184 -> 2026-10-13T121303126159 | 13 changed | quiet |
| 2026-10-13 | `remote/se.sistaminuten/travel-search` | 2026-10-13T021613784087 -> 2026-10-13T121301616662 | 1 changed | quiet |
| 2026-10-13 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-12T000129502039 -> 2026-10-13T121314481727 | 1 added | quiet |
| 2026-10-13 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-13T021620875968 -> 2026-10-13T121300799644 | 4 added | quiet |
| 2026-10-13 | `remote/io.github.Embassy-of-the-Free-Mind/sourcelibrary` | 2026-10-12T181438472065 -> 2026-10-13T121301146243 | 2 changed | quiet |
| 2026-10-13 | `remote/com.youspot/youspot` | 2026-10-12T181439432469 -> 2026-10-13T121301222141 | 1 changed | quiet |
| 2026-10-13 | `remote/com.sourcey/sourcey` | 2026-10-12T181452896182 -> 2026-10-13T121300823293 | 2 changed | quiet |
| 2026-10-13 | `remote/com.sfxmint/sounds` | 2026-10-12T181437511673 -> 2026-10-13T121300238644 | 3 changed | quiet |
| 2026-10-13 | `remote/ch.kulalabs.pazair/pazair` | 2026-10-12T181454220024 -> 2026-10-13T121301736379 | 4 changed | quiet |
| 2026-10-13 | `remote/ai.skuit/catalog` | 2026-10-12T181437200083 -> 2026-10-13T121259884403 | 1 changed | quiet |
| 2026-10-13 | `remote/net.isitdns/isitdns` | 2026-10-13T021610407817 -> 2026-10-13T121259219286 | 3 changed | quiet |
| 2026-10-13 | `remote/io.github.tang-vu/keryx` | 2026-10-12T063528364620 -> 2026-10-13T121301102999 | 1 added | quiet |
| 2026-10-13 | `remote/gl.parse/mcp` | 2026-10-12T181438461371 -> 2026-10-13T121300265539 | 2 changed | quiet |
| 2026-10-13 | `remote/ai.autonomad/travel` | 2026-10-13T021610242243 -> 2026-10-13T121259676075 | 1 changed | quiet |
| 2026-10-13 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-13T021609904696 -> 2026-10-13T121258659293 | 1 changed | quiet |
| 2026-10-13 | `remote/dev.mcphost/mcphost` | 2026-10-12T181436800100 -> 2026-10-13T121259390635 | 1 changed | quiet |
| 2026-10-13 | `remote/com.squirrelscan/squirrelscan` | 2026-10-13T021623474882 -> 2026-10-13T121259848869 | 3 changed | quiet |
| 2026-10-13 | `remote/com.jojapi/product-barcode-api` | 2026-10-13T021619369155 -> 2026-10-13T121258541315 | 1 changed | quiet |
| 2026-10-13 | `remote/co.homemaster/homemaster` | 2026-10-11T150641075094 -> 2026-10-13T121302283113 | 1 changed | quiet |
| 2026-10-13 | `remote/org.aspern/aspern` | 2026-10-12T181446738818 -> 2026-10-13T121303236985 | 3 changed, 1 added | quiet |
| 2026-10-13 | `remote/io.github.sean0007/free-agent-tools` | 2026-10-12T063525237263 -> 2026-10-13T121257847239 | 1 added | quiet |
| 2026-10-13 | `remote/directory.nohumans/registry` | 2026-10-13T021616030852 -> 2026-10-13T121257199843 | 1 changed | quiet |
| 2026-10-13 | `remote/com.enhancedint/enhanced-intelligence` | 2026-10-12T181435217583 -> 2026-10-13T121259183458 | 2 changed | quiet |
| 2026-10-13 | `remote/com.cooperemail/cooper-email` | 2026-10-12T181432723624 -> 2026-10-13T121257047644 | 6 changed | quiet |
| 2026-10-13 | `remote/ch.kulalabs.agents/jobflow` | 2026-10-12T181432399215 -> 2026-10-13T121257031660 | 4 changed | quiet |
| 2026-10-13 | `remote/io.agentsvc/services` | 2026-10-13T021609277548 -> 2026-10-13T121257883373 | 2 added | quiet |
| 2026-10-13 | `remote/com.uplika/uplika` | 2026-10-13T021610108944 -> 2026-10-13T121259692420 | 17 changed | quiet |
| 2026-10-13 | `remote/com.enhancedint/es-luxury` | 2026-10-12T181435422787 -> 2026-10-13T121259021192 | 2 changed | quiet |
| 2026-10-13 | `remote/wedding.aisle/aisle` | 2026-10-13T021611026950 -> 2026-10-13T121257171103 | 7 changed | quiet |
| 2026-10-13 | `remote/com.ashareapi/ashare-data-api` | 2026-10-11T063055702365 -> 2026-10-13T121257865799 | 1 changed, 1 added | quiet |
| 2026-10-13 | `remote/au.com.alpineai/factstamp` | 2026-10-11T150649513156 -> 2026-10-13T121256429005 | 1 changed | quiet |
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

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 17859 substantive, 8062 that changed only numbers (a catalogue counter ticking, a date), 416 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 13231 | 5706 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 538 | 538 | 0 | 0 |
| `sistaminuten.se` | 100 | 3 | 0 | 97 |
| `afbudsrejser.dk` | 99 | 3 | 0 | 96 |
| `akkilahdot.fi` | 99 | 3 | 0 | 96 |
| `restplass.no` | 99 | 3 | 0 | 96 |
| `socialloop.ai` | 97 | 97 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `caseyjhand.com` | 77 | 77 | 0 | 0 |
| `remoshift.com` | 72 | 4 | 68 | 0 |
| `fundinglandscape.com` | 71 | 41 | 30 | 0 |
| 3055 other operators | 9416 | 8946 | 439 | 31 |
