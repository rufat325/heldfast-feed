# MCP server tool changes

Last change observed 2026-10-18T11:35:17+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10495 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 23695 hosted endpoints (read daily, and every four hours while they keep changing).

32462 changes to a tool definition: 1188 npm releases (942 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 31274 readings of hosted servers that found their tools changed; 2089 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-18 | `remote/dev.zambo/zambo` | 2026-10-18T051353382124 -> 2026-10-18T113517731801 | 35 changed (every tool) | quiet |
| 2026-10-18 | `remote/io.github.zambodotdev/zambo` | 2026-10-18T051353316366 -> 2026-10-18T113517759556 | 35 changed (every tool) | quiet |
| 2026-10-18 | `remote/io.github.kwizzlesurp10-ctrl/x402-mcp` | 2026-10-01T134422827300 -> 2026-10-18T113512273096 | 1 changed | quiet |
| 2026-10-18 | `remote/io.taifoon/coordination-layer.1` | 2026-10-18T051349738204 -> 2026-10-18T113507051892 | 2 changed | review |
| 2026-10-18 | `remote/se.sistaminuten/travel-search` | 2026-10-18T051348177487 -> 2026-10-18T113504797314 | 1 changed | quiet |
| 2026-10-18 | `remote/eu.skavio/paid-micro-apis` | 2026-10-17T070518267367 -> 2026-10-18T113505580564 | 3 changed | quiet |
| 2026-10-18 | `remote/ai.myporta/myporta` | 2026-10-17T055613253831 -> 2026-10-18T113457787732 | 1 changed | quiet |
| 2026-10-18 | `remote/coach.marian/mentoring-inquiry-builder` | 2026-10-09T153647411777 -> 2026-10-18T113457366909 | 4 changed | quiet |
| 2026-10-18 | `remote/no.apier/mcp` | 2026-10-17T055555369890 -> 2026-10-18T113435235185 | 1 changed | quiet |
| 2026-10-18 | `remote/de.wostrom/catalog` | 2026-09-23T202524677799 -> 2026-10-18T113432304620 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.suprraz/webzum` | 2026-10-06T110222315003 -> 2026-10-18T113416811180 | 1 changed | quiet |
| 2026-10-18 | `remote/com.voxodds/voxodds` | 2026-10-01T134401959709 -> 2026-10-18T113415588708 | 6 changed | quiet |
| 2026-10-18 | `remote/no.restplass/travel-search` | 2026-10-18T051542321767 -> 2026-10-18T113414100701 | 1 changed | quiet |
| 2026-10-18 | `remote/ai.pulsegate/provenance` | 2026-10-07T001333588400 -> 2026-10-18T113412731917 | 3 changed (every tool) | quiet |
| 2026-10-18 | `remote/com.meridiandispatch/travel-guides` | 2026-10-07T001331054018 -> 2026-10-18T113407145263 | 9 changed, 4 added (every tool) | quiet |
| 2026-10-18 | `remote/com.vibe-fixer/vibefix` | 2026-10-07T063345656497 -> 2026-10-18T113404921501 | 2 changed, 3 added | quiet |
| 2026-10-18 | `remote/fr.comparr/comparr` | 2026-09-28T142304018099 -> 2026-10-18T113350085556 | 3 changed | quiet |
| 2026-10-18 | `remote/com.cintrasupply/cintra-quote` | 2026-10-08T135515370702 -> 2026-10-18T113348040220 | 3 changed | quiet |
| 2026-10-18 | `remote/io.github.lonniev/tollbooth-shortlinks` | 2026-09-23T160950848524 -> 2026-10-18T113345896873 | 4 changed (every tool) | quiet |
| 2026-10-18 | `remote/io.github.lonniev/tollbooth-oauth2-collector` | 2026-09-23T160812076750 -> 2026-10-18T113345251517 | 4 changed (every tool) | quiet |
| 2026-10-18 | `remote/dk.afbudsrejser/travel-search` | 2026-10-18T051530650154 -> 2026-10-18T113342685871 | 1 changed | quiet |
| 2026-10-18 | `remote/de.wopool/catalog` | 2026-09-23T202534482925 -> 2026-10-18T113340191574 | 1 changed | quiet |
| 2026-10-18 | `remote/ai.wem3/wem-price-compare` | 2026-10-09T153620446261 -> 2026-10-18T113335433443 | 6 changed | quiet |
| 2026-10-18 | `remote/com.tariffmonkee/mcp` | 2026-09-23T160806508115 -> 2026-10-18T113333494666 | 19 changed (every tool) | quiet |
| 2026-10-18 | `remote/com.zinvyl/marketplace` | 2026-10-17T060007115729 -> 2026-10-18T113330249000 | 2 changed, 3 added | quiet |
| 2026-10-18 | `remote/com.vidreno/mcp` | 2026-10-17T060406275017 -> 2026-10-18T113327591155 | 3 changed | quiet |
| 2026-10-18 | `remote/com.viarapidaservices/mcp` | 2026-10-06T110242670266 -> 2026-10-18T113327660292 | 1 changed | quiet |
| 2026-10-18 | `remote/fyi.smartfin/smartfin` | 2026-10-17T055449050317 -> 2026-10-18T113322048669 | 12 changed, 3 added | quiet |
| 2026-10-18 | `remote/video.quiz/api` | 2026-09-23T162951697067 -> 2026-10-18T113319829516 | 1 changed, 1 added | quiet |
| 2026-10-18 | `remote/io.github.cyanheads/unesco-heritage-mcp-server` | 2026-10-06T110235490305 -> 2026-10-18T113318902584 | 9 changed (every tool) | quiet |
| 2026-10-18 | `remote/dev.primitive/email` | 2026-10-10T202105216296 -> 2026-10-18T113318149065 | 14 changed (every tool) | quiet |
| 2026-10-18 | `remote/io.github.cyanheads/uk-police-crime-mcp-server` | 2026-10-06T110234948996 -> 2026-10-18T113317484466 | 6 changed (every tool) | quiet |
| 2026-10-18 | `remote/io.github.taux-io/twse-mcp` | 2026-09-30T152314515081 -> 2026-10-18T113316230547 | 3 changed | quiet |
| 2026-10-18 | `remote/design.overflow/mcp` | 2026-10-06T110422707843 -> 2026-10-18T113318722948 | 2 changed | quiet |
| 2026-10-18 | `remote/com.shipshapedata/shipshape-data-docs` | 2026-10-17T055442819592 -> 2026-10-18T113315235046 | 1 changed | quiet |
| 2026-10-18 | `remote/com.jobcrawls/connector` | 2026-10-17T055942922649 -> 2026-10-18T113312264238 | 4 changed (every tool) | quiet |
| 2026-10-18 | `remote/com.incrediblefi/loan-marketplace` | 2026-09-23T162944896150 -> 2026-10-18T113314304869 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.anburan-tech/shoe-fit-checker` | 2026-10-01T134227285448 -> 2026-10-18T113255494748 | 1 changed | quiet |
| 2026-10-18 | `remote/com.shipshapedata/shipshape-data` | 2026-10-17T070432476060 -> 2026-10-18T113255701666 | 1 changed | quiet |
| 2026-10-18 | `remote/ar.com.consignatarias/cattle-market` | 2026-10-08T135459081873 -> 2026-10-18T113255900442 | 1 changed | quiet |
| 2026-10-18 | `remote/fi.akkilahdot/travel-search` | 2026-10-18T051400473100 -> 2026-10-18T113251061459 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.agentready-market/audit` | 2026-10-06T110346652644 -> 2026-10-18T113250825204 | 1 changed, 1 added | quiet |
| 2026-10-18 | `remote/com.serdaroztetik/call-me` | 2026-10-04T195022757945 -> 2026-10-18T113246691615 | 1 changed, 2 added | quiet |
| 2026-10-18 | `remote/io.github.RegistrumUK/uk-companies-house-mcp` | 2026-10-17T055418708432 -> 2026-10-18T113247055191 | 9 changed, 2 added (every tool) | quiet |
| 2026-10-18 | `remote/com.santismm/knowledge` | 2026-10-17T224433804711 -> 2026-10-18T113237504553 | 3 changed | quiet |
| 2026-10-18 | `remote/us.srv.vehcdj664efetfrsolne5umanq/quoteproof-mcp` | 2026-10-18T051356069633 -> 2026-10-18T113233751786 | 12 changed | quiet |
| 2026-10-18 | `remote/io.github.cyanheads/ris-austria-mcp-server` | 2026-09-25T120358667859 -> 2026-10-18T113230488044 | 7 changed | quiet |
| 2026-10-18 | `remote/io.github.richardjhobbs/rrg-marketplace` | 2026-10-10T202044642389 -> 2026-10-18T113225219531 | 1 changed | quiet |
| 2026-10-18 | `remote/dev.pages.smithtalks/smithtalks` | 2026-10-17T224359939507 -> 2026-10-18T113223800838 | 1 changed | quiet |
| 2026-10-18 | `remote/com.selisesignature/signature` | 2026-10-06T110145531045 -> 2026-10-18T113219471114 | 2 changed | quiet |
| 2026-10-18 | `remote/com.probe402/endpoint-history` | 2026-10-08T135231023370 -> 2026-10-18T113213587366 | 2 changed (every tool) | review |
| 2026-10-18 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-18T051346236704 -> 2026-10-18T113210402075 | 1 changed | quiet |
| 2026-10-18 | `remote/ai.outfitmaker/outfit-assistant.1` | 2026-10-06T105945102648 -> 2026-10-18T113209684704 | 3 changed (every tool) | quiet |
| 2026-10-18 | `remote/app.seatsherpa/rides` | 2026-10-17T070311555539 -> 2026-10-18T113204839709 | 3 changed | quiet |
| 2026-10-18 | `remote/com.onefindme/search` | 2026-10-06T105938695206 -> 2026-10-18T113203121991 | 1 changed | quiet |
| 2026-10-18 | `remote/com.sunsetmixing/site-mcp` | 2026-09-23T162901047007 -> 2026-10-18T113200964975 | 6 changed (every tool) | quiet |
| 2026-10-18 | `remote/io.github.samuelzcom/chauffeur-booking` | 2026-10-09T064743392215 -> 2026-10-18T113205492453 | 5 changed (every tool) | quiet |
| 2026-10-18 | `remote/io.github.cueqzapper/picorn` | 2026-10-17T060036857696 -> 2026-10-18T113157300496 | 2 changed, 2 added | quiet |
| 2026-10-18 | `remote/io.github.everyai-com/sahadeva` | 2026-10-17T155957776787 -> 2026-10-18T113155446309 | 24 changed, 2 added | quiet |
| 2026-10-18 | `remote/app.steadywrk/mcp-dispatch` | 2026-10-17T055817087776 -> 2026-10-18T113155151762 | 3 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 22335 substantive, 9660 that changed only numbers (a catalogue counter ticking, a date), 467 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 16224 | 7212 | 9012 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 142 | 142 | 0 | 0 |
| `sistaminuten.se` | 113 | 4 | 0 | 109 |
| `afbudsrejser.dk` | 112 | 4 | 0 | 108 |
| `akkilahdot.fi` | 112 | 4 | 0 | 108 |
| `restplass.no` | 112 | 4 | 0 | 108 |
| `socialloop.ai` | 109 | 109 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `fundinglandscape.com` | 83 | 50 | 33 | 0 |
| `remoshift.com` | 83 | 6 | 77 | 0 |
| 3959 other operators | 12281 | 11709 | 538 | 34 |
