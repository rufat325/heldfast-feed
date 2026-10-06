# MCP server tool changes

Last change observed 2026-10-06T01:31:28+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10128 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 21701 hosted endpoints (read daily, and every four hours while they keep changing).

19756 changes to a tool definition: 696 npm releases (450 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 19060 readings of hosted servers that found their tools changed; 240 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-06 | `remote/fi.akkilahdot/travel-search` | 2026-10-05T172742499649 -> 2026-10-06T013128827820 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-04T195025592459 -> 2026-10-06T013128967229 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-05T172723189589 -> 2026-10-06T013127452505 | 91 changed | quiet |
| 2026-10-06 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-05T061630386108 -> 2026-10-06T013124976335 | 1 changed | quiet |
| 2026-10-06 | `remote/com.innergcomplete/shearquery` | 2026-10-05T061628227787 -> 2026-10-06T013129081934 | 2 added | quiet |
| 2026-10-06 | `remote/com.tkawen/intelligence-gateway` | 2026-10-05T172638426341 -> 2026-10-06T013121246421 | 1 changed | quiet |
| 2026-10-06 | `remote/com.remoshift/jobs` | 2026-10-05T172716084744 -> 2026-10-06T013121236946 | 1 changed | quiet |
| 2026-10-06 | `remote/com.recipebooq/recipebooq` | 2026-10-04T054915682015 -> 2026-10-06T013120659511 | 2 changed | quiet |
| 2026-10-06 | `remote/net.clickwise/product-catalog` | 2026-10-04T124035467556 -> 2026-10-06T013120361248 | 1 changed | quiet |
| 2026-10-06 | `remote/com.jojapi/product-barcode-api` | 2026-10-05T172633045688 -> 2026-10-06T013117877910 | 2 changed | quiet |
| 2026-10-06 | `remote/com.hergertsynthora/synthora-x402` | 2026-10-05T172631849015 -> 2026-10-06T013117190024 | 28 removed | quiet |
| 2026-10-06 | `remote/io.github.Poiuyhje/eqvps` | 2026-10-05T172631298576 -> 2026-10-06T013116928714 | 1 changed | quiet |
| 2026-10-06 | `remote/io.companygraph/mental-model` | 2026-10-04T195003853672 -> 2026-10-06T013116511977 | 14 changed (every tool) | quiet |
| 2026-10-06 | `remote/com.gluecron/gluecron` | 2026-10-04T054508765593 -> 2026-10-06T013112961482 | 1 added | quiet |
| 2026-10-06 | `remote/com.opointo/opointo` | 2026-10-04T054843346292 -> 2026-10-06T013116033520 | 2 changed | quiet |
| 2026-10-06 | `remote/com.obriym-crm/mcp` | 2026-10-04T195016898318 -> 2026-10-06T013114966690 | 8 added | quiet |
| 2026-10-06 | `remote/org.biobricks/site` | 2026-10-04T054245226290 -> 2026-10-06T013108343851 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.naief9961-tech/naif-fixgraph` | 2026-10-05T172702832354 -> 2026-10-06T013110746339 | 1 changed, 1 added | review |
| 2026-10-06 | `remote/com.revdoku/revdoku` | 2026-10-05T172619445966 -> 2026-10-06T013107571812 | 14 changed | quiet |
| 2026-10-06 | `remote/info.3dcms/mcp` | 2026-10-04T142417912519 -> 2026-10-06T013105953561 | 2 changed | quiet |
| 2026-10-06 | `remote/directory.nohumans/registry` | 2026-10-04T233730534669 -> 2026-10-06T013105744548 | 1 changed | quiet |
| 2026-10-06 | `remote/com.hashn/hashn` | 2026-10-04T054002249937 -> 2026-10-06T013105671754 | 3 changed | quiet |
| 2026-10-06 | `remote/ai.switchapp/switch` | 2026-10-04T054756154021 -> 2026-10-06T013106724609 | 5 changed, 1 added | quiet |
| 2026-10-06 | `remote/com.kernelcad/kernelcad` | 2026-10-05T172653681838 -> 2026-10-06T013110248581 | 3 changed | quiet |
| 2026-10-06 | `remote/com.jojapi/swift-ai` | 2026-10-05T061620525937 -> 2026-10-06T013101802579 | 1 changed | quiet |
| 2026-10-06 | `remote/com.hireahelper/mcp` | 2026-10-05T172649010179 -> 2026-10-06T013056046256 | 16 removed | quiet |
| 2026-10-06 | `remote/io.guestgraph/mental-model` | 2026-10-04T195013222537 -> 2026-10-06T013057297959 | 14 changed (every tool) | quiet |
| 2026-10-06 | `remote/io.github.Clipform/mcp-server` | 2026-10-05T172640257507 -> 2026-10-06T013051744693 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.davisvillelabs/localproof` | 2026-10-04T142438049046 -> 2026-10-06T013046523393 | 10 changed | quiet |
| 2026-10-06 | `remote/com.thefilmradar/filmlab` | 2026-10-05T172639121774 -> 2026-10-06T013050834452 | 4 added | review |
| 2026-10-06 | `remote/net.hotelrefund/price-tracker` | 2026-10-05T061612875798 -> 2026-10-06T013041866720 | 1 changed | quiet |
| 2026-10-06 | `remote/no.restplass/travel-search` | 2026-10-05T172649755891 -> 2026-10-06T013036898441 | 1 changed | quiet |
| 2026-10-06 | `remote/dk.afbudsrejser/travel-search` | 2026-10-05T172648416866 -> 2026-10-06T013036328717 | 1 changed | quiet |
| 2026-10-06 | `remote/se.sistaminuten/travel-search` | 2026-10-05T172659369194 -> 2026-10-06T013035081882 | 1 changed | quiet |
| 2026-10-06 | `remote/com.thefomite/fomite` | 2026-10-05T061620804947 -> 2026-10-06T013034071476 | 1 changed | quiet |
| 2026-10-06 | `remote/com.spacexploration/listings` | 2026-10-05T172644993280 -> 2026-10-06T013034489502 | 1 changed | quiet |
| 2026-10-06 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-04T233800273687 -> 2026-10-06T013033944843 | 2 changed | quiet |
| 2026-10-06 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt` | 2026-10-05T172612443114 -> 2026-10-06T013033103525 | 1 changed | quiet |
| 2026-10-06 | `remote/com.shipshapedata/shipshape-data-docs` | 2026-10-04T124142477949 -> 2026-10-06T013033628574 | 1 changed | quiet |
| 2026-10-06 | `remote/com.predictionmarketspicks/quant` | 2026-10-04T142444032798 -> 2026-10-06T013033374767 | 4 changed, 1 added, 4 removed | quiet |
| 2026-10-06 | `remote/ua.com.mfoxa/catalog` | 2026-10-04T124016323260 -> 2026-10-06T013031992511 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.whiteknightonhorse/apibase` | 2026-10-05T172612124258 -> 2026-10-06T013032231580 | 2 changed, 11 added | review |
| 2026-10-06 | `remote/io.github.troothllc/trooth-network` | 2026-10-05T061607797646 -> 2026-10-06T013031091587 | 6 changed, 2 added (every tool) | quiet |
| 2026-10-06 | `remote/io.github.nanoparse-dev/nanoparse-mcp` | 2026-10-04T054924136224 -> 2026-10-06T013031430937 | 1 changed | quiet |
| 2026-10-06 | `remote/com.meettempi/tempi` | 2026-10-04T124012403515 -> 2026-10-06T013031355909 | 1 changed | quiet |
| 2026-10-06 | `remote/com.prereason/mcp` | 2026-10-05T061607946059 -> 2026-10-06T013030677288 | 3 changed | quiet |
| 2026-10-06 | `remote/io.orbitwan/orbitwan` | 2026-10-04T195009944452 -> 2026-10-06T013030601808 | 6 changed | quiet |
| 2026-10-06 | `remote/so.darwin/darwin` | 2026-10-05T172633873725 -> 2026-10-06T013029845586 | 1 changed | quiet |
| 2026-10-06 | `remote/io.insourcia/insourcia` | 2026-10-05T172638006247 -> 2026-10-06T013028981079 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.TotesMagotes/mcp-server-auth` | 2026-10-05T172633799499 -> 2026-10-06T013028068397 | 6 changed | quiet |
| 2026-10-06 | `remote/ch.blust/mental-model` | 2026-10-04T194956515722 -> 2026-10-06T013028114388 | 14 changed (every tool) | quiet |
| 2026-10-06 | `remote/io.github.Dahliyaal/justicelibre` | 2026-10-05T172630470928 -> 2026-10-06T013027343373 | 11 changed | quiet |
| 2026-10-06 | `remote/dev.hatchloop/sanctions-screening` | 2026-10-04T054513687125 -> 2026-10-06T013027694026 | 4 changed | quiet |
| 2026-10-06 | `remote/dev.hatchloop/company-verification` | 2026-10-04T054513713220 -> 2026-10-06T013027569322 | 2 changed | quiet |
| 2026-10-06 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-05T172629339033 -> 2026-10-06T013024805969 | 3 changed | quiet |
| 2026-10-06 | `remote/dev.hatchloop/appointment-booking` | 2026-10-04T054513185551 -> 2026-10-06T013027352106 | 1 changed | quiet |
| 2026-10-06 | `remote/com.damagerestorehq/site` | 2026-10-04T054315024816 -> 2026-10-06T013026277903 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.hermoso-ai/hermoso` | 2026-10-05T172624109587 -> 2026-10-06T013024138116 | 6 changed | quiet |
| 2026-10-06 | `remote/com.buckybuild/bucky` | 2026-10-04T194955683947 -> 2026-10-06T013024048607 | 1 changed | quiet |
| 2026-10-06 | `remote/cloud.dchub/mcp-server` | 2026-10-05T061608113299 -> 2026-10-06T013025074600 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 14559 substantive, 4894 that changed only numbers (a catalogue counter ticking, a date), 303 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 10219 | 5684 | 4535 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `sistaminuten.se` | 74 | 2 | 0 | 72 |
| `afbudsrejser.dk` | 73 | 2 | 0 | 71 |
| `akkilahdot.fi` | 73 | 2 | 0 | 71 |
| `restplass.no` | 73 | 2 | 0 | 71 |
| `caseyjhand.com` | 72 | 72 | 0 | 0 |
| `socialloop.ai` | 71 | 71 | 0 | 0 |
| `dayze.com` | 63 | 63 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| 2103 other operators | 6125 | 5748 | 359 | 18 |
