# MCP server tool changes

Last change observed 2026-10-12T06:35:37+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10128 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 21701 hosted endpoints (read daily, and every four hours while they keep changing).

26175 changes to a tool definition: 870 npm releases (624 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 25305 readings of hosted servers that found their tools changed; 396 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-12 | `remote/fi.akkilahdot/travel-search` | 2026-10-12T000131871022 -> 2026-10-12T063538380392 | 1 changed | quiet |
| 2026-10-12 | `remote/ru.vedarai/mcp` | 2026-10-11T063115516628 -> 2026-10-12T063539076375 | 2 added | quiet |
| 2026-10-12 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-12T000129335009 -> 2026-10-12T063536961694 | 1 changed | quiet |
| 2026-10-12 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-12T000130913516 -> 2026-10-12T063537155024 | 1 changed | quiet |
| 2026-10-12 | `remote/com.remoshift/jobs` | 2026-10-12T000128515888 -> 2026-10-12T063536444528 | 1 changed | quiet |
| 2026-10-12 | `remote/ai.shorti/shorti` | 2026-10-12T000130027071 -> 2026-10-12T063538203829 | 1 changed | quiet |
| 2026-10-12 | `remote/com.sonarconnections/sonar-connections` | 2026-10-11T203720370399 -> 2026-10-12T063535282529 | 3 changed, 6 added, 1 removed | quiet |
| 2026-10-12 | `remote/com.multicinesortega/cartelera` | 2026-10-11T203722751446 -> 2026-10-12T063536529359 | 1 changed | quiet |
| 2026-10-12 | `remote/se.sistaminuten/travel-search` | 2026-10-12T000129095810 -> 2026-10-12T063534485608 | 1 changed | quiet |
| 2026-10-12 | `remote/com.jojapi/swift-ai` | 2026-10-11T063108110607 -> 2026-10-12T063534237019 | 1 changed | quiet |
| 2026-10-12 | `remote/io.github.si-imtiaz/leadquasar` | 2026-10-10T202043168115 -> 2026-10-12T063533566133 | 1 changed | quiet |
| 2026-10-12 | `remote/com.thefilmradar/filmlab` | 2026-10-12T000125902995 -> 2026-10-12T063534179146 | 1 changed, 1 added | quiet |
| 2026-10-12 | `remote/co.getclippy/clippy` | 2026-10-11T203712625940 -> 2026-10-12T063533397662 | 5 changed (every tool) | quiet |
| 2026-10-12 | `remote/io.github.snefhew/factline` | 2026-10-11T150638673820 -> 2026-10-12T063532000266 | 1 changed | quiet |
| 2026-10-12 | `remote/io.github.34r7h/handoff` | 2026-10-11T063103265400 -> 2026-10-12T063532680506 | 1 changed | quiet |
| 2026-10-12 | `remote/ai.satohub/onchain-agents` | 2026-10-10T202055780082 -> 2026-10-12T063532252131 | 2 changed | quiet |
| 2026-10-12 | `remote/uk.co.buildbatch/buildbatch` | 2026-10-11T203656315367 -> 2026-10-12T063531179202 | 2 changed | quiet |
| 2026-10-12 | `remote/no.restplass/travel-search` | 2026-10-12T000120545968 -> 2026-10-12T063531999392 | 1 changed | quiet |
| 2026-10-12 | `remote/io.github.Timothymycompc/solana-pulse-gateway` | 2026-10-11T150657017462 -> 2026-10-12T063530596429 | 7 changed | quiet |
| 2026-10-12 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt` | 2026-10-12T000114955226 -> 2026-10-12T063531699485 | 3 changed | quiet |
| 2026-10-12 | `remote/dk.afbudsrejser/travel-search` | 2026-10-12T000120870749 -> 2026-10-12T063531955205 | 1 changed | quiet |
| 2026-10-12 | `remote/cloud.dchub/mcp-server.2` | 2026-10-10T062510989773 -> 2026-10-12T063531883227 | 2 changed | quiet |
| 2026-10-12 | `remote/io.github.Fizzl13/presign-guard` | 2026-10-12T000119246433 -> 2026-10-12T063530188123 | 5 changed | quiet |
| 2026-10-12 | `remote/io.github.whiteknightonhorse/apibase` | 2026-10-12T000113526707 -> 2026-10-12T063530888353 | 4 removed | quiet |
| 2026-10-12 | `remote/io.github.richardsolomou/praetorium` | 2026-10-12T000120397029 -> 2026-10-12T063530356801 | 2 changed | quiet |
| 2026-10-12 | `remote/io.github.assetfare/assetfare` | 2026-10-11T150629853951 -> 2026-10-12T063531610879 | 3 changed | quiet |
| 2026-10-12 | `remote/com.prereason/mcp` | 2026-10-11T150628623274 -> 2026-10-12T063529946145 | 1 changed | quiet |
| 2026-10-12 | `remote/ch.kulalabs.pazair/pazair` | 2026-10-11T150655698846 -> 2026-10-12T063529623507 | 1 changed, 2 added | quiet |
| 2026-10-12 | `remote/ai.skuit/catalog` | 2026-10-11T203659439369 -> 2026-10-12T063529558878 | 1 changed | quiet |
| 2026-10-12 | `remote/so.darwin/darwin` | 2026-10-11T150653710218 -> 2026-10-12T063527611050 | 1 changed | quiet |
| 2026-10-12 | `remote/io.github.tang-vu/keryx` | 2026-10-11T203655868759 -> 2026-10-12T063528364620 | 1 changed, 3 added | quiet |
| 2026-10-12 | `remote/cloud.dchub/mcp-server` | 2026-10-12T000120940777 -> 2026-10-12T063526645094 | 28 changed | quiet |
| 2026-10-12 | `remote/io.github.sean0007/free-agent-tools` | 2026-10-11T063058802574 -> 2026-10-12T063525237263 | 1 added | quiet |
| 2026-10-12 | `remote/io.github.lonniev/goodearth-mcp` | 2026-10-12T000115128730 -> 2026-10-12T063525668508 | 3 changed | quiet |
| 2026-10-12 | `remote/org.aspern/aspern` | 2026-10-11T203652181086 -> 2026-10-12T063524180105 | 1 changed | quiet |
| 2026-10-12 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-10T062523229966 -> 2026-10-12T063523824078 | 3 changed | review |
| 2026-10-12 | `remote/io.github.assetfare/assetfare-bridge` | 2026-10-11T150633621869 -> 2026-10-12T063524808810 | 3 changed | quiet |
| 2026-10-12 | `remote/io.github.Embassy-of-the-Free-Mind/sourcelibrary` | 2026-10-11T203658333289 -> 2026-10-12T063524339704 | 1 changed | quiet |
| 2026-10-12 | `remote/io.github.0xinsider/mcp` | 2026-10-12T000118450655 -> 2026-10-12T063523717513 | 1 changed | quiet |
| 2026-10-12 | `remote/com.restaurantdoctorai/profit-check` | 2026-10-11T150644407442 -> 2026-10-12T063522799809 | 7 changed, 2 added | review |
| 2026-10-12 | `remote/com.plainrouter/mcp` | 2026-10-11T203657183194 -> 2026-10-12T063523437590 | 6 changed | quiet |
| 2026-10-12 | `remote/dev.mcphost/mcphost` | 2026-10-11T203655738557 -> 2026-10-12T063522442860 | 3 changed | quiet |
| 2026-10-12 | `remote/com.squirrelscan/squirrelscan` | 2026-10-12T000126373587 -> 2026-10-12T063522210700 | 7 changed, 2 added | quiet |
| 2026-10-12 | `remote/wedding.aisle/aisle` | 2026-10-12T000110339916 -> 2026-10-12T063522278171 | 5 changed | quiet |
| 2026-10-12 | `remote/com.jojapi/product-barcode-api` | 2026-10-10T235258407687 -> 2026-10-12T063521206267 | 1 changed | quiet |
| 2026-10-12 | `remote/directory.nohumans/registry` | 2026-10-11T150636779414 -> 2026-10-12T063518133324 | 1 changed | quiet |
| 2026-10-12 | `remote/ch.kulalabs.agents/jobflow` | 2026-10-11T150636770276 -> 2026-10-12T063518601382 | 1 changed, 2 added | quiet |
| 2026-10-12 | `remote/fi.akkilahdot/travel-search` | 2026-10-11T203726527610 -> 2026-10-12T000131871022 | 1 changed | quiet |
| 2026-10-12 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-11T150705326773 -> 2026-10-12T000130913516 | 1 changed | quiet |
| 2026-10-12 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-11T203724034411 -> 2026-10-12T000129335009 | 1 changed | quiet |
| 2026-10-12 | `remote/com.swarmmemo/bulletin` | 2026-10-11T203725032491 -> 2026-10-12T000130682630 | 4 changed | quiet |
| 2026-10-12 | `remote/se.sistaminuten/travel-search` | 2026-10-11T203705508281 -> 2026-10-12T000129095810 | 1 changed | quiet |
| 2026-10-12 | `remote/io.github.yschimke/compose-preview` | 2026-10-11T203724198764 -> 2026-10-12T000129015150 | 6 changed | quiet |
| 2026-10-12 | `remote/com.remoshift/jobs` | 2026-10-11T203722054677 -> 2026-10-12T000128515888 | 1 changed | quiet |
| 2026-10-12 | `remote/ai.shorti/shorti` | 2026-10-11T063112839075 -> 2026-10-12T000130027071 | 1 changed | quiet |
| 2026-10-12 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-11T063103350957 -> 2026-10-12T000128966645 | 1 changed | quiet |
| 2026-10-12 | `remote/com.thefomite/fomite` | 2026-10-11T063053960025 -> 2026-10-12T000127425755 | 1 changed | quiet |
| 2026-10-12 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-11T203704207349 -> 2026-10-12T000129502039 | 2 changed, 1 added | quiet |
| 2026-10-12 | `remote/io.github.jackskip22/rapier` | 2026-10-10T202048474870 -> 2026-10-12T000126559485 | 6 added, 47 removed | quiet |
| 2026-10-12 | `remote/com.squirrelscan/squirrelscan` | 2026-10-11T203655537868 -> 2026-10-12T000126373587 | 25 changed (every tool) | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 17729 substantive, 8041 that changed only numbers (a catalogue counter ticking, a date), 405 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 13231 | 5706 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 538 | 538 | 0 | 0 |
| `sistaminuten.se` | 97 | 2 | 0 | 95 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `afbudsrejser.dk` | 96 | 2 | 0 | 94 |
| `akkilahdot.fi` | 96 | 2 | 0 | 94 |
| `restplass.no` | 96 | 2 | 0 | 94 |
| `socialloop.ai` | 94 | 94 | 0 | 0 |
| `caseyjhand.com` | 77 | 77 | 0 | 0 |
| `dayze.com` | 69 | 69 | 0 | 0 |
| `remoshift.com` | 69 | 4 | 65 | 0 |
| 3054 other operators | 9274 | 8795 | 451 | 28 |
