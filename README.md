# MCP server tool changes

Last change observed 2026-10-07T00:13:34+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10128 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 21701 hosted endpoints (read daily, and every four hours while they keep changing).

22525 changes to a tool definition: 789 npm releases (543 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 21736 readings of hosted servers that found their tools changed; 298 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-07 | `remote/io.github.ihen404/x402-scraper-api` | 2026-10-06T133924721504 -> 2026-10-07T001334925807 | 2 added | quiet |
| 2026-10-07 | `remote/no.restplass/travel-search` | 2026-10-06T184120119984 -> 2026-10-07T001333425646 | 1 changed | quiet |
| 2026-10-07 | `remote/ai.pulsegate/provenance` | 2026-10-06T110326709767 -> 2026-10-07T001333588400 | 1 added | quiet |
| 2026-10-07 | `remote/com.meridiandispatch/travel-guides` | 2026-10-06T110322820704 -> 2026-10-07T001331054018 | 5 changed, 4 added, 4 removed (every tool) | quiet |
| 2026-10-07 | `remote/work.funfriday/funfriday` | 2026-10-06T110317505891 -> 2026-10-07T001331723562 | 1 changed, 1 added | quiet |
| 2026-10-07 | `remote/dk.afbudsrejser/travel-search` | 2026-10-06T184111671750 -> 2026-10-07T001327770266 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.VoiceScapee/voicescape` | 2026-10-06T110244309502 -> 2026-10-07T001325250827 | 2 changed, 3 added | quiet |
| 2026-10-07 | `remote/ai.wem3/wem-price-compare` | 2026-10-05T172648149942 -> 2026-10-07T001326051584 | 1 changed | quiet |
| 2026-10-07 | `remote/com.txtreel/txtreel` | 2026-10-06T184105872762 -> 2026-10-07T001323112657 | 2 changed | quiet |
| 2026-10-07 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-06T133741857134 -> 2026-10-07T001315020218 | 2 changed | quiet |
| 2026-10-07 | `remote/dev.pages.smithtalks/smithtalks` | 2026-10-06T184055043336 -> 2026-10-07T001311035020 | 1 added | quiet |
| 2026-10-07 | `remote/io.github.everyai-com/service-schedule` | 2026-10-06T184051934419 -> 2026-10-07T001306784990 | 1 changed | quiet |
| 2026-10-07 | `remote/ai.rokha/rokha` | 2026-10-05T172642781921 -> 2026-10-07T001301270391 | 20 changed, 25 added | review |
| 2026-10-07 | `remote/io.github.everyai-com/party-plan` | 2026-10-06T184039665781 -> 2026-10-07T001253377357 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.cloakmaster/pact0` | 2026-10-06T110022898452 -> 2026-10-07T001253257387 | 5 changed | review |
| 2026-10-07 | `remote/finance.paddock/paddock` | 2026-10-06T110023262368 -> 2026-10-07T001253784138 | 1 added | quiet |
| 2026-10-07 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-10-06T133947309395 -> 2026-10-07T001244475762 | 1 changed | quiet |
| 2026-10-07 | `remote/se.sistaminuten/travel-search` | 2026-10-06T184112694169 -> 2026-10-07T001242514419 | 1 changed | quiet |
| 2026-10-07 | `remote/eu.paymentslaw/legislation` | 2026-10-06T105859733526 -> 2026-10-07T001242372292 | 1 changed | quiet |
| 2026-10-07 | `remote/com.youspot/youspot` | 2026-10-06T184036344855 -> 2026-10-07T001240013506 | 2 changed, 5 added | quiet |
| 2026-10-07 | `remote/org.living-bread.mcp/living-bread` | 2026-10-06T184026027669 -> 2026-10-07T001240669220 | 2 changed, 11 added, 50 removed (every tool) | quiet |
| 2026-10-07 | `remote/io.github.Dcroyalty/xrplhub` | 2026-10-06T184122179392 -> 2026-10-07T001237620057 | 3 changed | quiet |
| 2026-10-07 | `remote/com.eatmundo/dishes` | 2026-10-06T110146059797 -> 2026-10-07T001239224720 | 2 changed | quiet |
| 2026-10-07 | `remote/app.manawa/manawa-terminal` | 2026-10-06T105838631260 -> 2026-10-07T001238606907 | 1 changed | quiet |
| 2026-10-07 | `remote/no.apier/mcp` | 2026-10-06T110143542253 -> 2026-10-07T001239575454 | 1 changed | quiet |
| 2026-10-07 | `remote/ai.thebotique.www/sigil` | 2026-10-06T184121443918 -> 2026-10-07T001237037826 | 11 changed (every tool) | quiet |
| 2026-10-07 | `remote/com.etfiq/etfiq` | 2026-10-06T105817654475 -> 2026-10-07T001235943320 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.SoapyRED/freightutils` | 2026-10-05T172746940369 -> 2026-10-07T001235671929 | 3 changed | quiet |
| 2026-10-07 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-10-06T184117312070 -> 2026-10-07T001233679253 | 3 changed | quiet |
| 2026-10-07 | `remote/fi.akkilahdot/travel-search` | 2026-10-06T184116845410 -> 2026-10-07T001233462791 | 1 changed | quiet |
| 2026-10-07 | `remote/com.budgetpixel/mcp` | 2026-10-06T105803577163 -> 2026-10-07T001233178840 | 1 changed | review |
| 2026-10-07 | `remote/io.github.withgrokbot/verified-catalog` | 2026-10-06T184024569852 -> 2026-10-07T001231615996 | 1 changed | quiet |
| 2026-10-07 | `remote/com.vibe-fixer/vibefix` | 2026-10-06T110209321777 -> 2026-10-07T001232271340 | 2 changed (every tool) | quiet |
| 2026-10-07 | `remote/io.github.aneduaim/untap-mcp` | 2026-10-06T110322930953 -> 2026-10-07T001230141489 | 2 changed | quiet |
| 2026-10-07 | `remote/io.github.Book0fEli/paycheck` | 2026-10-06T184015773997 -> 2026-10-07T001229799470 | 1 changed | quiet |
| 2026-10-07 | `remote/com.travelcharika/travelcharika` | 2026-10-06T110318267020 -> 2026-10-07T001229682744 | 1 removed | quiet |
| 2026-10-07 | `remote/com.thefomite/fomite` | 2026-10-06T013034071476 -> 2026-10-07T001229942961 | 1 changed | quiet |
| 2026-10-07 | `remote/io.tracetail/tracetail` | 2026-10-06T110314450682 -> 2026-10-07T001228986886 | 1 changed | quiet |
| 2026-10-07 | `remote/io.stackcut/stackcut` | 2026-10-06T110118052271 -> 2026-10-07T001227149691 | 3 changed, 2 added | quiet |
| 2026-10-07 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-05T172642547855 -> 2026-10-07T001227569399 | 3 added | review |
| 2026-10-07 | `remote/com.swarmmemo/bulletin` | 2026-10-06T184108102262 -> 2026-10-07T001226388171 | 3 changed | quiet |
| 2026-10-07 | `remote/io.github.SidneyBissoli/senado-br-mcp-cloudflare` | 2026-10-06T110038456177 -> 2026-10-07T001222981472 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-06T184102350045 -> 2026-10-07T001221441284 | 12 changed, 8 added | quiet |
| 2026-10-07 | `remote/io.github.daveabear/rwa-data-mcp` | 2026-10-06T110027102667 -> 2026-10-07T001221076749 | 4 changed | review |
| 2026-10-07 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-06T013124976335 -> 2026-10-07T001222277418 | 1 changed | quiet |
| 2026-10-07 | `remote/ai.shorti/shorti` | 2026-10-06T110228650012 -> 2026-10-07T001222361566 | 1 changed | quiet |
| 2026-10-07 | `remote/com.remoshift/jobs` | 2026-10-06T184055504200 -> 2026-10-07T001217285928 | 1 changed | quiet |
| 2026-10-07 | `remote/ae.brainy/grocery-prices` | 2026-10-06T110000456620 -> 2026-10-07T001219618132 | 5 changed | quiet |
| 2026-10-07 | `remote/com.quietstance/productive-opportunity-development` | 2026-10-06T184054800071 -> 2026-10-07T001216414706 | 1 changed, 1 added | quiet |
| 2026-10-07 | `remote/io.github.sean0007/free-agent-tools` | 2026-10-06T105528256559 -> 2026-10-07T001215475324 | 1 added | quiet |
| 2026-10-07 | `remote/dev.pdfmd/pdf-to-markdown` | 2026-10-06T105945668783 -> 2026-10-07T001214360238 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.enricoaboujaoude-droid/pal-commerce-catalog-intelligence` | 2026-10-06T105941385831 -> 2026-10-07T001213066206 | 1 added | quiet |
| 2026-10-07 | `remote/io.github.Piloxa/piloxa` | 2026-10-06T184042464692 -> 2026-10-07T001212969530 | 2 changed, 5 added | quiet |
| 2026-10-07 | `remote/ai.pechincha/deals` | 2026-10-06T184041764479 -> 2026-10-07T001211882719 | 4 changed | quiet |
| 2026-10-07 | `remote/re.parcellai/parcellaire` | 2026-10-06T184041675633 -> 2026-10-07T001212414759 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.nanoparse-dev/nanoparse-mcp` | 2026-10-06T184035760176 -> 2026-10-07T001206218411 | 1 changed | quiet |
| 2026-10-07 | `remote/com.vendooly/vendooly` | 2026-10-06T133601310514 -> 2026-10-07T001207362290 | 2 changed, 1 added | quiet |
| 2026-10-07 | `remote/com.narrowhighway/concordance` | 2026-10-06T184035731027 -> 2026-10-07T001205886233 | 1 added | quiet |
| 2026-10-07 | `remote/io.github.tradewr333-lgtm/degenscan-intel` | 2026-10-05T061608118184 -> 2026-10-07T001205329028 | 4 added | quiet |
| 2026-10-07 | `remote/ai.switchapp/switch` | 2026-10-06T113342194114 -> 2026-10-07T001205649895 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 15760 substantive, 6441 that changed only numbers (a catalogue counter ticking, a date), 324 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 11736 | 5690 | 6046 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `sistaminuten.se` | 79 | 2 | 0 | 77 |
| `afbudsrejser.dk` | 78 | 2 | 0 | 76 |
| `akkilahdot.fi` | 78 | 2 | 0 | 76 |
| `restplass.no` | 78 | 2 | 0 | 76 |
| `socialloop.ai` | 76 | 76 | 0 | 0 |
| `caseyjhand.com` | 74 | 74 | 0 | 0 |
| `dayze.com` | 65 | 65 | 0 | 0 |
| `daedalmap.com` | 54 | 54 | 0 | 0 |
| 2751 other operators | 7345 | 6931 | 395 | 19 |
