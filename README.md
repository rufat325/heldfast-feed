# MCP server tool changes

Last change observed 2026-11-14T11:50:34+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

98441 changes to a tool definition: 4084 npm releases (3838 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 94357 readings of hosted servers that found their tools changed; 4054 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-14 | `remote/design.overflow/mcp` | 2026-11-13T120622670353 -> 2026-11-14T115037995464 | 1 changed | quiet |
| 2026-11-14 | `remote/studio.gradients/mcp` | 2026-11-14T010705836104 -> 2026-11-14T115034137625 | 1 changed | quiet |
| 2026-11-14 | `remote/fi.akkilahdot/travel-search` | 2026-11-14T010704412708 -> 2026-11-14T115033541184 | 1 changed | quiet |
| 2026-11-14 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-14T010706018221 -> 2026-11-14T115035076074 | 16 added | quiet |
| 2026-11-14 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-14T010704249215 -> 2026-11-14T115030589571 | 3 changed | quiet |
| 2026-11-14 | `remote/io.github.cyanheads/usaspending-mcp-server` | 2026-11-12T155146816685 -> 2026-11-14T115027612067 | 9 changed | quiet |
| 2026-11-14 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-11-13T013144779683 -> 2026-11-14T115025340309 | 3 changed, 1 added | quiet |
| 2026-11-14 | `remote/no.restplass/travel-search` | 2026-11-14T010701489593 -> 2026-11-14T115023265229 | 1 changed | quiet |
| 2026-11-14 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-14T010659362852 -> 2026-11-14T115025491560 | 4 changed | quiet |
| 2026-11-14 | `remote/com.tabflows/site` | 2026-11-13T200813882608 -> 2026-11-14T115023658772 | 1 changed | quiet |
| 2026-11-14 | `remote/io.deeplead/deeplead` | 2026-11-13T150753290874 -> 2026-11-14T115022033898 | 5 changed | quiet |
| 2026-11-14 | `remote/dk.afbudsrejser/travel-search` | 2026-11-14T010659729449 -> 2026-11-14T115021488911 | 1 changed | quiet |
| 2026-11-14 | `remote/com.163yu/hetianyu` | 2026-11-12T154957080118 -> 2026-11-14T115022921642 | 1 changed, 4 added | quiet |
| 2026-11-14 | `remote/is.envelop.unisafe/insight` | 2026-11-13T115844737006 -> 2026-11-14T115019732597 | 6 changed | quiet |
| 2026-11-14 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-14T010654954998 -> 2026-11-14T115018032080 | 3 changed, 5 added | quiet |
| 2026-11-14 | `remote/com.snapwonders/mcp` | 2026-11-12T154959906590 -> 2026-11-14T115018889321 | 1 changed | quiet |
| 2026-11-14 | `remote/com.trackerhacker/mcp` | 2026-11-13T013136335172 -> 2026-11-14T115016391614 | 3 changed | quiet |
| 2026-11-14 | `remote/com.theoutcomelayer/outcome-layer` | 2026-11-13T150607938710 -> 2026-11-14T115015248125 | 2 changed | quiet |
| 2026-11-14 | `remote/com.sendaparcelcompare/site` | 2026-11-12T154912460841 -> 2026-11-14T115014170453 | 2 changed | quiet |
| 2026-11-14 | `remote/com.kyde/score` | 2026-11-13T013212658176 -> 2026-11-14T115013431621 | 2 changed | quiet |
| 2026-11-14 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-13T124156354704 -> 2026-11-14T115011870334 | 2 added | quiet |
| 2026-11-14 | `remote/app.seatsherpa/rides` | 2026-11-13T115646560936 -> 2026-11-14T115007621479 | 5 changed | quiet |
| 2026-11-14 | `remote/io.github.richardsolomou/praetorium` | 2026-11-14T010633100772 -> 2026-11-14T114959587278 | 1 changed | quiet |
| 2026-11-14 | `remote/app.lovable.peppol-invoice-compass/invoiceverify` | 2026-11-14T010632778399 -> 2026-11-14T115001653399 | 2 changed, 1 added | quiet |
| 2026-11-14 | `remote/com.partstable/partstable` | 2026-11-13T115515871010 -> 2026-11-14T114957779709 | 1 changed | quiet |
| 2026-11-14 | `remote/ch.kulalabs.pazair/pazair` | 2026-11-14T010631240330 -> 2026-11-14T114959346318 | 1 changed, 1 added | quiet |
| 2026-11-14 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-13T200713545645 -> 2026-11-14T114957419604 | 4 added | quiet |
| 2026-11-14 | `remote/com.multicinesortega/cartelera` | 2026-11-14T010642136320 -> 2026-11-14T114958608220 | 1 changed | quiet |
| 2026-11-14 | `remote/com.sonarconnections/sonar-connections` | 2026-11-13T115910910754 -> 2026-11-14T114954979328 | 1 changed | quiet |
| 2026-11-14 | `remote/se.sistaminuten/travel-search` | 2026-11-14T010657398664 -> 2026-11-14T114953778067 | 1 changed | quiet |
| 2026-11-14 | `remote/io.taifoon/coordination-layer.1` | 2026-11-13T200812865719 -> 2026-11-14T114954627278 | 1 changed | review |
| 2026-11-14 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-11-13T013223363659 -> 2026-11-14T114955206130 | 3 changed, 1 added | quiet |
| 2026-11-14 | `remote/io.github.jdhart81/ghg-ledger` | 2026-11-12T154549569440 -> 2026-11-14T114954697228 | 1 changed | quiet |
| 2026-11-14 | `remote/domains.unique/mcp-server` | 2026-11-13T115851269830 -> 2026-11-14T114954090292 | 23 changed | quiet |
| 2026-11-14 | `remote/network.tier1protocol/tier1` | 2026-11-13T115841887083 -> 2026-11-14T114953843823 | 2 changed | quiet |
| 2026-11-14 | `remote/io.github.jdhart81/disclosure-compiler` | 2026-11-12T154347550631 -> 2026-11-14T114950518181 | 1 changed | quiet |
| 2026-11-14 | `remote/com.tickerdb/mcp-server` | 2026-11-12T074721828624 -> 2026-11-14T114950168080 | 1 changed | quiet |
| 2026-11-14 | `remote/org.glolaw/glo-law` | 2026-11-14T010633525022 -> 2026-11-14T114947501331 | 1 changed | quiet |
| 2026-11-14 | `remote/io.github.daniel3303/equibles` | 2026-11-14T010633420725 -> 2026-11-14T114947694628 | 3 changed | quiet |
| 2026-11-14 | `remote/app.usesnippet/snippet` | 2026-11-13T013210584460 -> 2026-11-14T114945677100 | 1 changed | quiet |
| 2026-11-14 | `remote/work.finder/jobs` | 2026-11-13T200718773784 -> 2026-11-14T114945469890 | 2 changed | quiet |
| 2026-11-14 | `remote/com.avnester.mcp/property-intelligence` | 2026-11-12T154247661128 -> 2026-11-14T114945981653 | 11 changed (every tool) | quiet |
| 2026-11-14 | `remote/io.github.industrial-platform-ai/web-metadata` | 2026-11-13T115526187518 -> 2026-11-14T114943958000 | 1 changed | quiet |
| 2026-11-14 | `remote/io.github.MsingathiM/swapeazi` | 2026-11-13T200749716225 -> 2026-11-14T114943214253 | 4 changed, 1 added | quiet |
| 2026-11-14 | `remote/pro.aicut/aicut` | 2026-11-13T115508856413 -> 2026-11-14T114943023794 | 1 changed | quiet |
| 2026-11-14 | `remote/co.getclippy/clippy` | 2026-11-14T010629690142 -> 2026-11-14T114942187646 | 3 changed | review |
| 2026-11-14 | `remote/co.deadbrands/arena` | 2026-11-14T010615955494 -> 2026-11-14T114942430591 | 2 changed, 1 added | quiet |
| 2026-11-14 | `remote/io.github.makimmigration/mak-immigration-source-guide` | 2026-11-13T013102183025 -> 2026-11-14T114939377207 | 1 changed | quiet |
| 2026-11-14 | `remote/fun.make/makefun` | 2026-11-13T200651748662 -> 2026-11-14T114941311218 | 9 changed | review |
| 2026-11-14 | `remote/com.shipshapedata/shipshape-data-docs` | 2026-11-13T115656410883 -> 2026-11-14T114939808379 | 1 changed | quiet |
| 2026-11-14 | `remote/com.seraphixsystems/public-records` | 2026-11-13T200744387022 -> 2026-11-14T114939507798 | 1 changed, 1 added | quiet |
| 2026-11-14 | `remote/app.liquidvision/derivatives` | 2026-11-13T115415272802 -> 2026-11-14T114939618430 | 3 changed | quiet |
| 2026-11-14 | `remote/io.github.si-imtiaz/leadquasar` | 2026-11-13T013137518934 -> 2026-11-14T114938535900 | 1 changed | quiet |
| 2026-11-14 | `remote/com.lasermaterialscompare/site` | 2026-11-12T153951560731 -> 2026-11-14T114937535039 | 2 changed | quiet |
| 2026-11-14 | `remote/app.launchfiles/launchfiles` | 2026-11-13T115036203076 -> 2026-11-14T114936916849 | 1 added | quiet |
| 2026-11-14 | `remote/io.github.tiptreesystems/lacuna-research-mcp` | 2026-11-13T115031061057 -> 2026-11-14T114936636668 | 1 changed | quiet |
| 2026-11-14 | `remote/xyz.pokeka/card-prices` | 2026-11-13T115531036636 -> 2026-11-14T114931631278 | 1 changed | quiet |
| 2026-11-14 | `remote/io.github.adriancasas/geo360-concierge` | 2026-11-13T200658987697 -> 2026-11-14T114931739551 | 1 removed | quiet |
| 2026-11-14 | `remote/com.ksaworks/goldseam` | 2026-11-13T200659493600 -> 2026-11-14T114931139549 | 1 added | quiet |
| 2026-11-14 | `remote/io.github.homeaccount7/signaldock` | 2026-11-13T120014655678 -> 2026-11-14T114929711290 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 60418 substantive, 37018 that changed only numbers (a catalogue counter ticking, a date), 1005 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 52526 | 17762 | 34764 | 0 |
| `a2awire.com` | 2375 | 2375 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 407 | 407 | 0 | 0 |
| `civai.co` | 317 | 317 | 0 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `revmesh2074.workers.dev` | 246 | 215 | 31 | 0 |
| `sistaminuten.se` | 234 | 6 | 0 | 228 |
| `afbudsrejser.dk` | 233 | 6 | 0 | 227 |
| `akkilahdot.fi` | 233 | 6 | 0 | 227 |
| `restplass.no` | 233 | 6 | 0 | 227 |
| `socialloop.ai` | 225 | 225 | 0 | 0 |
| 9269 other operators | 38813 | 36494 | 2223 | 96 |
