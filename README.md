# MCP server tool changes

Last change observed 2026-10-07T21:38:53+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10128 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 21701 hosted endpoints (read daily, and every four hours while they keep changing).

22863 changes to a tool definition: 789 npm releases (543 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 22074 readings of hosted servers that found their tools changed; 321 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-07 | `remote/com.youspot/youspot` | 2026-10-07T001240013506 -> 2026-10-07T213855469766 | 2 changed | quiet |
| 2026-10-07 | `remote/dev.hackshop/hackshop-mcp` | 2026-10-06T110257545610 -> 2026-10-07T213849980355 | 1 changed, 5 added | quiet |
| 2026-10-07 | `remote/no.restplass/travel-search` | 2026-10-07T154952439370 -> 2026-10-07T213847783250 | 1 changed | quiet |
| 2026-10-07 | `remote/com.veritahire/jobs` | 2026-10-07T063345192755 -> 2026-10-07T213844320459 | 1 changed | quiet |
| 2026-10-07 | `remote/dk.afbudsrejser/travel-search` | 2026-10-07T154947679131 -> 2026-10-07T213842418169 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.ohad6k/viberaven-guides` | 2026-10-06T110242641102 -> 2026-10-07T213838774046 | 2 changed | quiet |
| 2026-10-07 | `remote/io.github.VoiceScapee/voicescape` | 2026-10-07T154945311635 -> 2026-10-07T213839575381 | 3 added | quiet |
| 2026-10-07 | `remote/io.stackcut/stackcut` | 2026-10-07T001227149691 -> 2026-10-07T213838383803 | 22 changed, 1 added (every tool) | quiet |
| 2026-10-07 | `remote/io.github.SoapyRED/freightutils` | 2026-10-07T063429551915 -> 2026-10-07T213839355895 | 2 changed | quiet |
| 2026-10-07 | `remote/fi.akkilahdot/travel-search` | 2026-10-07T154952405085 -> 2026-10-07T213837986602 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.CodeWever/wever-labs-products` | 2026-10-07T154950384107 -> 2026-10-07T213835609971 | 4 changed, 4 added | quiet |
| 2026-10-07 | `remote/com.tickerz/tickerz` | 2026-10-07T154941511595 -> 2026-10-07T213835050733 | 1 changed | quiet |
| 2026-10-07 | `remote/se.sistaminuten/travel-search` | 2026-10-07T154942835387 -> 2026-10-07T213833230341 | 1 changed | quiet |
| 2026-10-07 | `remote/com.vermarco/marketplace` | 2026-10-07T063421629627 -> 2026-10-07T213833850704 | 1 changed | quiet |
| 2026-10-07 | `remote/com.menloinsurance/mcp` | 2026-10-07T063321555292 -> 2026-10-07T213838150807 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.Schoasch/backtesting-arena` | 2026-10-06T184110434021 -> 2026-10-07T213832122882 | 2 changed | quiet |
| 2026-10-07 | `remote/com.restaurantdoctorai/profit-check` | 2026-10-06T110020477807 -> 2026-10-07T213829811401 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-07T154943096493 -> 2026-10-07T213829898889 | 1 changed | quiet |
| 2026-10-07 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-07T154938771433 -> 2026-10-07T213829522323 | 1 changed, 1 added | quiet |
| 2026-10-07 | `remote/com.swarmmemo/bulletin` | 2026-10-07T154942690073 -> 2026-10-07T213829785939 | 11 changed | quiet |
| 2026-10-07 | `remote/ai.rokha/rokha` | 2026-10-07T001301270391 -> 2026-10-07T213825205257 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-07T154937473844 -> 2026-10-07T213824433433 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.enricoaboujaoude-droid/pal-commerce-catalog-intelligence` | 2026-10-07T001213066206 -> 2026-10-07T213824051205 | 8 changed | quiet |
| 2026-10-07 | `remote/com.innergcomplete/shearquery` | 2026-10-06T013129081934 -> 2026-10-07T213821287047 | 1 changed, 5 added | quiet |
| 2026-10-07 | `remote/co.rahuldsarker/growth-tools` | 2026-10-06T110055908760 -> 2026-10-07T213822154421 | 5 added | quiet |
| 2026-10-07 | `remote/co.civai.nova/support-agent-admin` | 2026-10-06T105926577166 -> 2026-10-07T213821167845 | 2 added | quiet |
| 2026-10-07 | `remote/ai.shorti/shorti` | 2026-10-07T154937111305 -> 2026-10-07T213822933688 | 14 changed, 2 removed (every tool) | quiet |
| 2026-10-07 | `remote/com.remoshift/jobs` | 2026-10-07T154931473986 -> 2026-10-07T213817861725 | 1 changed | quiet |
| 2026-10-07 | `remote/ch.kulalabs.pazair/pazair` | 2026-10-06T184041470668 -> 2026-10-07T213818546817 | 13 changed, 8 removed | quiet |
| 2026-10-07 | `remote/co.civai.nova/research-agent` | 2026-10-07T154922844902 -> 2026-10-07T213816420172 | 2 added | quiet |
| 2026-10-07 | `remote/co.civai.nova/google-sheets-agent` | 2026-10-07T154922666798 -> 2026-10-07T213816301977 | 2 added | quiet |
| 2026-10-07 | `remote/io.github.yschimke/compose-preview` | 2026-10-06T110143518786 -> 2026-10-07T213817088251 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.choaticpixels/wicked-mcp` | 2026-10-06T105849632845 -> 2026-10-07T213815216072 | 3 changed, 3 added | quiet |
| 2026-10-07 | `remote/com.nearbypermits/permits` | 2026-10-07T154921881508 -> 2026-10-07T213815484526 | 2 changed, 1 added | quiet |
| 2026-10-07 | `remote/app.railway.up.rent-check-production/irish-rent-check` | 2026-10-07T154921809743 -> 2026-10-07T213813922792 | 2 added | quiet |
| 2026-10-07 | `remote/io.github.minsooparkk/korea-tax-law-mcp` | 2026-10-06T133617788275 -> 2026-10-07T213814670074 | 1 changed | quiet |
| 2026-10-07 | `remote/com.thmenu/thmenu` | 2026-10-07T154917124777 -> 2026-10-07T213810968515 | 4 changed | quiet |
| 2026-10-07 | `remote/io.github.smarterweather/weather` | 2026-10-06T184030384435 -> 2026-10-07T213810364813 | 3 changed | quiet |
| 2026-10-07 | `remote/com.problee/problee` | 2026-10-07T001200997196 -> 2026-10-07T213810795652 | 2 changed | quiet |
| 2026-10-07 | `remote/dev.mentio/mcp` | 2026-10-06T133527418488 -> 2026-10-07T213808655856 | 17 changed, 1 added | review |
| 2026-10-07 | `remote/com.pixharvest/tariff-data` | 2026-10-06T105954868553 -> 2026-10-07T213808658932 | 1 changed, 1 added | quiet |
| 2026-10-07 | `remote/re.parcellai/parcellaire` | 2026-10-07T154916387450 -> 2026-10-07T213809092790 | 4 changed | quiet |
| 2026-10-07 | `remote/com.multicinesortega/cartelera` | 2026-10-07T063348805823 -> 2026-10-07T213808563205 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.yzlee/opcmenu` | 2026-10-05T172645978387 -> 2026-10-07T213810075528 | 1 changed | quiet |
| 2026-10-07 | `remote/com.jojapi/product-barcode-api` | 2026-10-07T154915875974 -> 2026-10-07T213808282804 | 1 changed | quiet |
| 2026-10-07 | `remote/co.civai.nova/google-docs-agent` | 2026-10-06T105934598582 -> 2026-10-07T213804931748 | 2 added | quiet |
| 2026-10-07 | `remote/com.etfiq/etfiq` | 2026-10-07T001235943320 -> 2026-10-07T213803277972 | 3 added | quiet |
| 2026-10-07 | `remote/com.peppolstatus/api` | 2026-10-06T184037971231 -> 2026-10-07T213801678909 | 6 changed | quiet |
| 2026-10-07 | `remote/co.cookie-compliance/cookie-consent` | 2026-10-06T133405044047 -> 2026-10-07T213802423483 | 8 changed (every tool) | quiet |
| 2026-10-07 | `remote/com.avokata/avokata` | 2026-10-06T105759799995 -> 2026-10-07T213801369937 | 8 changed, 2 added | quiet |
| 2026-10-07 | `remote/io.github.worklittle/jobs` | 2026-10-05T172648721941 -> 2026-10-07T213759687185 | 2 added | quiet |
| 2026-10-07 | `remote/ai.memestack/mcp` | 2026-10-06T184034702171 -> 2026-10-07T213759462400 | 3 changed, 1 added, 1 removed | quiet |
| 2026-10-07 | `remote/com.materialhandling/catalog` | 2026-10-06T105632716134 -> 2026-10-07T213758946136 | 1 changed | quiet |
| 2026-10-07 | `remote/ai.skuit/catalog` | 2026-10-07T154903997985 -> 2026-10-07T213758175965 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.priors-agents/priors-read` | 2026-10-07T154904101438 -> 2026-10-07T213758265763 | 1 added | review |
| 2026-10-07 | `remote/gl.parse/mcp` | 2026-10-07T154904062061 -> 2026-10-07T213758738476 | 6 changed | quiet |
| 2026-10-07 | `remote/com.manjangilchi/manjangilchi` | 2026-10-06T105730301448 -> 2026-10-07T213758190277 | 25 added | quiet |
| 2026-10-07 | `remote/com.googleapis.mapstools/mcp` | 2026-10-06T105729970652 -> 2026-10-07T213757204617 | 2 changed | quiet |
| 2026-10-07 | `remote/dev.cloro/cloro` | 2026-10-06T105849871686 -> 2026-10-07T213755195213 | 1 changed | quiet |
| 2026-10-07 | `remote/com.daisycon.mcp/daisycon.2` | 2026-10-07T001159707481 -> 2026-10-07T213756488053 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 16058 substantive, 6466 that changed only numbers (a catalogue counter ticking, a date), 339 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 11736 | 5690 | 6046 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `sistaminuten.se` | 82 | 2 | 0 | 80 |
| `afbudsrejser.dk` | 81 | 2 | 0 | 79 |
| `akkilahdot.fi` | 81 | 2 | 0 | 79 |
| `restplass.no` | 81 | 2 | 0 | 79 |
| `socialloop.ai` | 79 | 79 | 0 | 0 |
| `caseyjhand.com` | 74 | 74 | 0 | 0 |
| `dayze.com` | 65 | 65 | 0 | 0 |
| `remoshift.com` | 57 | 2 | 55 | 0 |
| 2832 other operators | 7665 | 7278 | 365 | 22 |
