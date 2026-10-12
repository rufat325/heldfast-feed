# MCP server tool changes

Last change observed 2026-10-12T00:01:30+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10128 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 21701 hosted endpoints (read daily, and every four hours while they keep changing).

26128 changes to a tool definition: 870 npm releases (624 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 25258 readings of hosted servers that found their tools changed; 394 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-12 | `remote/com.thefilmradar/filmlab` | 2026-10-11T203715195460 -> 2026-10-12T000125902995 | 116 changed (every tool) | quiet |
| 2026-10-12 | `remote/com.kenwea.www/notary` | 2026-10-10T235258362714 -> 2026-10-12T000125127141 | 3 added, 3 removed | quiet |
| 2026-10-12 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-11T203656038937 -> 2026-10-12T000121110722 | 2 changed | quiet |
| 2026-10-12 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-10-11T203649693407 -> 2026-10-12T000123583224 | 1 changed | quiet |
| 2026-10-12 | `remote/cloud.dchub/mcp-server` | 2026-10-10T062512765007 -> 2026-10-12T000120940777 | 2 changed | quiet |
| 2026-10-12 | `remote/no.restplass/travel-search` | 2026-10-11T203702658579 -> 2026-10-12T000120545968 | 1 changed | quiet |
| 2026-10-12 | `remote/dk.afbudsrejser/travel-search` | 2026-10-11T203702109084 -> 2026-10-12T000120870749 | 1 changed | quiet |
| 2026-10-12 | `remote/domains.audit/appraisal` | 2026-10-11T150634323024 -> 2026-10-12T000119287247 | 1 added | quiet |
| 2026-10-12 | `remote/io.github.richardsolomou/praetorium` | 2026-10-11T203659944858 -> 2026-10-12T000120397029 | 1 changed | quiet |
| 2026-10-12 | `remote/io.github.Fizzl13/presign-guard` | 2026-10-11T203659091129 -> 2026-10-12T000119246433 | 1 added | quiet |
| 2026-10-12 | `remote/io.github.0xinsider/mcp` | 2026-10-11T203652344320 -> 2026-10-12T000118450655 | 1 changed | quiet |
| 2026-10-12 | `remote/app.flaim/mcp` | 2026-10-11T063045699405 -> 2026-10-12T000118024106 | 8 changed | quiet |
| 2026-10-12 | `remote/com.sourcey/sourcey` | 2026-10-11T150654145043 -> 2026-10-12T000117697201 | 3 changed | quiet |
| 2026-10-12 | `remote/net.hotelrefund/price-tracker` | 2026-10-11T063102812368 -> 2026-10-12T000119152625 | 1 changed | quiet |
| 2026-10-12 | `remote/com.idevice/wearables` | 2026-10-11T203655268080 -> 2026-10-12T000116137687 | 1 changed | quiet |
| 2026-10-12 | `remote/io.github.lonniev/goodearth-mcp` | 2026-10-11T203654627730 -> 2026-10-12T000115128730 | 1 added | quiet |
| 2026-10-12 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt` | 2026-10-11T203700439654 -> 2026-10-12T000114955226 | 1 changed | quiet |
| 2026-10-12 | `remote/com.askmatchbox/matchbox` | 2026-10-11T203655667731 -> 2026-10-12T000113731710 | 2 changed | quiet |
| 2026-10-12 | `remote/io.github.whiteknightonhorse/apibase` | 2026-10-11T203654777954 -> 2026-10-12T000113526707 | 2 added, 7 removed | quiet |
| 2026-10-12 | `remote/wedding.aisle/aisle` | 2026-10-11T203649242020 -> 2026-10-12T000110339916 | 4 changed | quiet |
| 2026-10-11 | `remote/fr.projet-ariane/ariane-orientation` | 2026-10-10T062534539315 -> 2026-10-11T203728363973 | 1 changed | quiet |
| 2026-10-11 | `remote/com.ikeytz/website` | 2026-10-10T062534161949 -> 2026-10-11T203729665432 | 3 changed | quiet |
| 2026-10-11 | `remote/fi.akkilahdot/travel-search` | 2026-10-11T150706262800 -> 2026-10-11T203726527610 | 1 changed | quiet |
| 2026-10-11 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-10-10T062531903064 -> 2026-10-11T203727087466 | 1 changed | quiet |
| 2026-10-11 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-11T150702842757 -> 2026-10-11T203724034411 | 1 changed | quiet |
| 2026-10-11 | `remote/com.swarmmemo/bulletin` | 2026-10-11T150704127310 -> 2026-10-11T203725032491 | 2 changed, 6 added | quiet |
| 2026-10-11 | `remote/ch.swisslivingindex/swiss-living-index` | 2026-10-11T150703110565 -> 2026-10-11T203724187177 | 1 added | quiet |
| 2026-10-11 | `remote/com.remoshift/jobs` | 2026-10-11T150702055705 -> 2026-10-11T203722054677 | 1 changed | quiet |
| 2026-10-11 | `remote/io.github.yschimke/compose-preview` | 2026-10-10T062525157732 -> 2026-10-11T203724198764 | 1 changed, 2 added | quiet |
| 2026-10-11 | `remote/com.multicinesortega/cartelera` | 2026-10-11T063111109062 -> 2026-10-11T203722751446 | 1 changed | quiet |
| 2026-10-11 | `remote/com.mooncatcherwire/wire` | 2026-10-11T063109323530 -> 2026-10-11T203720815225 | 2 changed, 1 added | quiet |
| 2026-10-11 | `remote/com.vinktar/mcp` | 2026-10-10T062522329843 -> 2026-10-11T203721388054 | 7 changed, 4 added, 3 removed | quiet |
| 2026-10-11 | `remote/com.sonarconnections/sonar-connections` | 2026-10-11T150659603573 -> 2026-10-11T203720370399 | 1 added | quiet |
| 2026-10-11 | `remote/com.falazuki/finance-br` | 2026-10-11T063106331848 -> 2026-10-11T203717242851 | 1 changed | quiet |
| 2026-10-11 | `remote/com.thefilmradar/filmlab` | 2026-10-11T150649334223 -> 2026-10-11T203715195460 | 2 changed | quiet |
| 2026-10-11 | `remote/co.getclippy/clippy` | 2026-10-10T144718882067 -> 2026-10-11T203712625940 | 1 changed | quiet |
| 2026-10-11 | `remote/se.sistaminuten/travel-search` | 2026-10-11T150644972304 -> 2026-10-11T203705508281 | 1 changed | quiet |
| 2026-10-11 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-11T150645101888 -> 2026-10-11T203704207349 | 2 changed | quiet |
| 2026-10-11 | `remote/ru.quintadb/mcp` | 2026-10-11T150645800144 -> 2026-10-11T203704265018 | 2 changed | quiet |
| 2026-10-11 | `remote/no.restplass/travel-search` | 2026-10-11T150658790552 -> 2026-10-11T203702658579 | 1 changed | quiet |
| 2026-10-11 | `remote/dk.afbudsrejser/travel-search` | 2026-10-11T150658812800 -> 2026-10-11T203702109084 | 1 changed | quiet |
| 2026-10-11 | `remote/ltd.qianyuan/qy-evolution` | 2026-10-11T150644453915 -> 2026-10-11T203702946513 | 1 changed | quiet |
| 2026-10-11 | `remote/com.oods-foundry/foundry` | 2026-10-09T064735906196 -> 2026-10-11T203702449276 | 4 changed | quiet |
| 2026-10-11 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-11T063106749303 -> 2026-10-11T203659744579 | 13 changed | quiet |
| 2026-10-11 | `remote/pro.particle/particle-pro` | 2026-10-11T150640853812 -> 2026-10-11T203659091568 | 7 changed | quiet |
| 2026-10-11 | `remote/ai.skuit/catalog` | 2026-10-11T063051709378 -> 2026-10-11T203659439369 | 1 changed | quiet |
| 2026-10-11 | `remote/ua.com.quintadb/mcp` | 2026-10-11T150657460135 -> 2026-10-11T203700967226 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 17693 substantive, 8035 that changed only numbers (a catalogue counter ticking, a date), 400 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 13231 | 5706 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 538 | 538 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `sistaminuten.se` | 96 | 2 | 0 | 94 |
| `afbudsrejser.dk` | 95 | 2 | 0 | 93 |
| `akkilahdot.fi` | 95 | 2 | 0 | 93 |
| `restplass.no` | 95 | 2 | 0 | 93 |
| `socialloop.ai` | 93 | 93 | 0 | 0 |
| `caseyjhand.com` | 77 | 77 | 0 | 0 |
| `dayze.com` | 69 | 69 | 0 | 0 |
| `fundinglandscape.com` | 68 | 39 | 29 | 0 |
| 3054 other operators | 9233 | 8725 | 481 | 27 |
