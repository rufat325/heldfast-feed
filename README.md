# MCP server tool changes

Last change observed 2026-10-10T23:53:10+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10128 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 21701 hosted endpoints (read daily, and every four hours while they keep changing).

25917 changes to a tool definition: 870 npm releases (624 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 25047 readings of hosted servers that found their tools changed; 386 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-10 | `remote/io.github.withgrokbot/verified-catalog` | 2026-10-10T202046648605 -> 2026-10-10T235311492474 | 1 changed | quiet |
| 2026-10-10 | `remote/io.github.CodeWever/wever-labs-products` | 2026-10-10T062535742921 -> 2026-10-10T235310624823 | 2 changed | quiet |
| 2026-10-10 | `remote/fi.akkilahdot/travel-search` | 2026-10-10T202102791955 -> 2026-10-10T235310732663 | 1 changed | quiet |
| 2026-10-10 | `remote/se.sistaminuten/travel-search` | 2026-10-10T202059172403 -> 2026-10-10T235305649758 | 1 changed | quiet |
| 2026-10-10 | `remote/com.swarmmemo/bulletin` | 2026-10-10T202058179256 -> 2026-10-10T235306204207 | 4 changed, 12 added | quiet |
| 2026-10-10 | `remote/no.restplass/travel-search` | 2026-10-10T202126540815 -> 2026-10-10T235305161091 | 1 changed | quiet |
| 2026-10-10 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-10T202055918323 -> 2026-10-10T235304536934 | 1 changed | quiet |
| 2026-10-10 | `remote/dk.afbudsrejser/travel-search` | 2026-10-10T202125549051 -> 2026-10-10T235303895098 | 1 changed | quiet |
| 2026-10-10 | `remote/io.github.nimbusbci/nimbus-mcp` | 2026-10-10T062517688633 -> 2026-10-10T235310734941 | 2 changed | quiet |
| 2026-10-10 | `remote/com.remoshift/jobs` | 2026-10-10T202053933564 -> 2026-10-10T235302618106 | 1 changed | quiet |
| 2026-10-10 | `remote/com.saferesize/saferesize` | 2026-10-08T213429637723 -> 2026-10-10T235300271072 | 4 changed (every tool) | quiet |
| 2026-10-10 | `remote/com.mooncatcherwire/wire` | 2026-10-10T062522594411 -> 2026-10-10T235259382756 | 1 changed | quiet |
| 2026-10-10 | `remote/io.github.richardsolomou/praetorium` | 2026-10-08T213424756084 -> 2026-10-10T235259125187 | 1 changed | quiet |
| 2026-10-10 | `remote/io.github.Fizzl13/presign-guard` | 2026-10-10T202112693389 -> 2026-10-10T235258946548 | 3 changed | quiet |
| 2026-10-10 | `remote/com.kenwea.www/notary` | 2026-10-08T155433249456 -> 2026-10-10T235258362714 | 1 changed | quiet |
| 2026-10-10 | `remote/com.jojapi/product-barcode-api` | 2026-10-10T202037213655 -> 2026-10-10T235258407687 | 1 changed | quiet |
| 2026-10-10 | `remote/eu.paymentslaw/legislation` | 2026-10-09T153605907896 -> 2026-10-10T235255631718 | 2 changed | quiet |
| 2026-10-10 | `remote/com.galleyrender/galley-render` | 2026-10-08T134958536767 -> 2026-10-10T235255945861 | 1 changed | quiet |
| 2026-10-10 | `remote/com.falazuki/finance-br` | 2026-10-08T134953130403 -> 2026-10-10T235255498285 | 3 changed | review |
| 2026-10-10 | `remote/so.darwin/darwin` | 2026-10-10T062530315889 -> 2026-10-10T235253827697 | 2 changed | quiet |
| 2026-10-10 | `remote/com.metricduck/financial-analysis` | 2026-10-09T153610571246 -> 2026-10-10T235252736335 | 1 changed | quiet |
| 2026-10-10 | `remote/fun.lesgooo/lesgooo` | 2026-10-10T202042780918 -> 2026-10-10T235254537126 | 1 changed | quiet |
| 2026-10-10 | `remote/ar.indicadores/empresas` | 2026-10-10T144718679791 -> 2026-10-10T235252737487 | 1 changed | quiet |
| 2026-10-10 | `remote/io.github.tang-vu/keryx` | 2026-10-09T153559842841 -> 2026-10-10T235253141847 | 1 changed, 5 added | quiet |
| 2026-10-10 | `remote/io.github.snefhew/factline` | 2026-10-10T202040094523 -> 2026-10-10T235250094915 | 35 changed | quiet |
| 2026-10-10 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt` | 2026-10-10T202039438329 -> 2026-10-10T235248698726 | 6 changed, 4 added | quiet |
| 2026-10-10 | `remote/io.github.bosmdavid-gif/dropthehassle` | 2026-10-10T144713063208 -> 2026-10-10T235247996470 | 1 changed, 3 added | quiet |
| 2026-10-10 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-10-10T202031060853 -> 2026-10-10T235249034835 | 1 changed | quiet |
| 2026-10-10 | `remote/directory.nohumans/registry` | 2026-10-10T202030051308 -> 2026-10-10T235248459245 | 1 changed | quiet |
| 2026-10-10 | `remote/com.askmatchbox/matchbox` | 2026-10-10T202035739252 -> 2026-10-10T235244237085 | 2 changed | quiet |
| 2026-10-10 | `remote/io.github.whiteknightonhorse/apibase` | 2026-10-10T144655334357 -> 2026-10-10T235244970063 | 7 removed | quiet |
| 2026-10-10 | `remote/io.github.kiddhu/seekapi` | 2026-10-08T134413044572 -> 2026-10-10T235245128966 | 4 changed | quiet |
| 2026-10-10 | `remote/eu.sirenic/sirenic` | 2026-10-10T062520189537 -> 2026-10-10T235244660858 | 1 changed | quiet |
| 2026-10-10 | `remote/com.uplika/uplika` | 2026-10-10T062509680347 -> 2026-10-10T235244192263 | 1 changed | quiet |
| 2026-10-10 | `remote/wedding.aisle/aisle` | 2026-10-09T153532964869 -> 2026-10-10T235242176417 | 4 changed, 1 added | quiet |
| 2026-10-10 | `remote/app.agentbit/mcp` | 2026-10-10T202033448643 -> 2026-10-10T235242818528 | 1 changed | quiet |
| 2026-10-10 | `remote/no.restplass/travel-search` | 2026-10-10T144735708039 -> 2026-10-10T202126540815 | 1 changed | quiet |
| 2026-10-10 | `remote/dk.afbudsrejser/travel-search` | 2026-10-10T144733946368 -> 2026-10-10T202125549051 | 1 changed | quiet |
| 2026-10-10 | `remote/io.github.VoiceScapee/voicescape` | 2026-10-10T062540697633 -> 2026-10-10T202123807678 | 3 changed | quiet |
| 2026-10-10 | `remote/dev.pages.smithtalks/smithtalks` | 2026-10-10T062538666875 -> 2026-10-10T202118571512 | 1 added | quiet |
| 2026-10-10 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-10T144729831291 -> 2026-10-10T202121618986 | 13 changed | quiet |
| 2026-10-10 | `remote/ai.rokha/rokha` | 2026-10-08T213429084091 -> 2026-10-10T202115184572 | 25 changed, 1 added, 1 removed | review |
| 2026-10-10 | `remote/io.github.Fizzl13/presign-guard` | 2026-10-10T062535423262 -> 2026-10-10T202112693389 | 3 changed | quiet |
| 2026-10-10 | `remote/ch.kulalabs.pazair/pazair` | 2026-10-10T062534811672 -> 2026-10-10T202109433664 | 1 changed | quiet |
| 2026-10-10 | `remote/co.civai.nova/research-agent` | 2026-10-10T144724988836 -> 2026-10-10T202106509388 | 2 added | quiet |
| 2026-10-10 | `remote/co.civai.nova/google-sheets-agent` | 2026-10-10T144724949778 -> 2026-10-10T202105893335 | 2 added | quiet |
| 2026-10-10 | `remote/ai.thebotique.www/sigil` | 2026-10-10T062534611885 -> 2026-10-10T202104573581 | 1 changed | quiet |
| 2026-10-10 | `remote/dev.primitive/email` | 2026-10-09T064816305817 -> 2026-10-10T202105216296 | 4 changed | quiet |
| 2026-10-10 | `remote/fi.akkilahdot/travel-search` | 2026-10-10T144740357584 -> 2026-10-10T202102791955 | 1 changed | quiet |
| 2026-10-10 | `remote/com.vermarco/marketplace` | 2026-10-10T062529380863 -> 2026-10-10T202100270120 | 1 added | quiet |
| 2026-10-10 | `remote/ai.verticalmarketplace/vertical-marketplace` | 2026-10-10T062529626460 -> 2026-10-10T202100138410 | 1 added | quiet |
| 2026-10-10 | `remote/se.sistaminuten/travel-search` | 2026-10-10T144716947031 -> 2026-10-10T202059172403 | 1 changed | quiet |
| 2026-10-10 | `remote/io.github.tjcgraham-rgb/gaip-broker` | 2026-10-10T062533070270 -> 2026-10-10T202101490824 | 2 changed | quiet |
| 2026-10-10 | `remote/com.tickerinside/tickerinside-mcp` | 2026-10-10T062527530641 -> 2026-10-10T202057298579 | 12 changed (every tool) | quiet |
| 2026-10-10 | `remote/com.klarefi/mcp` | 2026-10-08T135524650124 -> 2026-10-10T202059030052 | 1 changed | quiet |
| 2026-10-10 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-10T144734307577 -> 2026-10-10T202055918323 | 1 changed | quiet |
| 2026-10-10 | `remote/com.swarmmemo/bulletin` | 2026-10-10T144736022113 -> 2026-10-10T202058179256 | 1 changed, 2 added | quiet |
| 2026-10-10 | `remote/com.seqbench/workbench` | 2026-10-09T064806538902 -> 2026-10-10T202055191269 | 3 changed | quiet |
| 2026-10-10 | `remote/com.remoshift/jobs` | 2026-10-10T144732063088 -> 2026-10-10T202053933564 | 1 changed | quiet |
| 2026-10-10 | `remote/app.openkrill/shop-duty` | 2026-10-08T213529126001 -> 2026-10-10T202055389272 | 5 changed, 1 removed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 17525 substantive, 8010 that changed only numbers (a catalogue counter ticking, a date), 382 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 13231 | 5706 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 538 | 538 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `sistaminuten.se` | 92 | 2 | 0 | 90 |
| `afbudsrejser.dk` | 91 | 2 | 0 | 89 |
| `akkilahdot.fi` | 91 | 2 | 0 | 89 |
| `restplass.no` | 91 | 2 | 0 | 89 |
| `socialloop.ai` | 89 | 89 | 0 | 0 |
| `caseyjhand.com` | 77 | 77 | 0 | 0 |
| `dayze.com` | 69 | 69 | 0 | 0 |
| `fundinglandscape.com` | 65 | 36 | 29 | 0 |
| 3054 other operators | 9045 | 8564 | 456 | 25 |
