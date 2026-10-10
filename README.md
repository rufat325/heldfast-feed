# MCP server tool changes

Last change observed 2026-10-10T20:21:24+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10128 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 21701 hosted endpoints (read daily, and every four hours while they keep changing).

25881 changes to a tool definition: 870 npm releases (624 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 25011 readings of hosted servers that found their tools changed; 385 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-10 | `remote/ai.satohub/onchain-agents` | 2026-10-10T062526764022 -> 2026-10-10T202055780082 | 3 changed | quiet |
| 2026-10-10 | `remote/com.aiapplyd/aiapplyd` | 2026-10-10T144720998411 -> 2026-10-10T202055678070 | 12 changed | quiet |
| 2026-10-10 | `remote/net.myopl/pickleball-public-knowledge` | 2026-10-10T062523171194 -> 2026-10-10T202051370709 | 5 changed (every tool) | quiet |
| 2026-10-10 | `remote/com.multicinesortega/cartelera` | 2026-10-10T062524150198 -> 2026-10-10T202053085698 | 1 changed | quiet |
| 2026-10-10 | `remote/ai.plith/plith` | 2026-10-09T153637435455 -> 2026-10-10T202053338679 | 2 changed | quiet |
| 2026-10-10 | `remote/co.civai.nova/google-docs-agent` | 2026-10-10T144709278571 -> 2026-10-10T202050200364 | 2 added | quiet |
| 2026-10-10 | `remote/com.widely-mobile/widely` | 2026-10-08T135118908648 -> 2026-10-10T202050066388 | 4 changed, 1 added | quiet |
| 2026-10-10 | `remote/com.sonarconnections/sonar-connections` | 2026-10-10T062521945197 -> 2026-10-10T202050762104 | 1 changed, 4 added | quiet |
| 2026-10-10 | `remote/ai.switchapp/switch` | 2026-10-10T144727102216 -> 2026-10-10T202049141575 | 4 added | quiet |
| 2026-10-10 | `remote/io.github.jackskip22/rapier` | 2026-10-10T144724303772 -> 2026-10-10T202048474870 | 9 changed | quiet |
| 2026-10-10 | `remote/com.youspot/youspot` | 2026-10-10T062525793948 -> 2026-10-10T202048178843 | 1 added | quiet |
| 2026-10-10 | `remote/io.github.withgrokbot/verified-catalog` | 2026-10-10T062524697128 -> 2026-10-10T202046648605 | 2 changed | quiet |
| 2026-10-10 | `remote/ai.skuit/catalog` | 2026-10-09T064733459048 -> 2026-10-10T202047774085 | 1 changed | quiet |
| 2026-10-10 | `remote/io.github.lonniev/goodearth-mcp` | 2026-10-08T134754616275 -> 2026-10-10T202047686763 | 1 changed | quiet |
| 2026-10-10 | `remote/com.thenewengineer/hvac` | 2026-10-09T064743725519 -> 2026-10-10T202046544272 | 3 changed | quiet |
| 2026-10-10 | `remote/ai.forkmate/forkmate` | 2026-10-10T062519057447 -> 2026-10-10T202046097178 | 2 changed | quiet |
| 2026-10-10 | `remote/io.github.Embassy-of-the-Free-Mind/sourcelibrary` | 2026-10-08T135322331715 -> 2026-10-10T202045931458 | 3 added | quiet |
| 2026-10-10 | `remote/io.github.conquext/neuron` | 2026-10-08T135011796752 -> 2026-10-10T202047861837 | 3 changed | quiet |
| 2026-10-10 | `remote/io.github.richardjhobbs/rrg-marketplace` | 2026-10-09T064739222649 -> 2026-10-10T202044642389 | 1 changed | quiet |
| 2026-10-10 | `remote/io.github.Ahmet11159/x402-agent-services` | 2026-10-09T153608378838 -> 2026-10-10T202043032667 | 1 changed, 3 added | quiet |
| 2026-10-10 | `remote/com.thefilmradar/filmlab` | 2026-10-10T144720528034 -> 2026-10-10T202044919743 | 4 changed | quiet |
| 2026-10-10 | `remote/io.github.si-imtiaz/leadquasar` | 2026-10-10T062515186844 -> 2026-10-10T202043168115 | 2 changed | quiet |
| 2026-10-10 | `remote/fun.lesgooo/lesgooo` | 2026-10-10T144717826842 -> 2026-10-10T202042780918 | 13 changed | quiet |
| 2026-10-10 | `remote/io.github.mooshee/govgazette` | 2026-10-09T064743128546 -> 2026-10-10T202041242106 | 1 changed | quiet |
| 2026-10-10 | `remote/co.civai.nova/support-agent-admin` | 2026-10-10T144711980447 -> 2026-10-10T202041362169 | 2 added | quiet |
| 2026-10-10 | `remote/io.github.snefhew/factline` | 2026-10-10T062512586703 -> 2026-10-10T202040094523 | 37 changed (every tool) | quiet |
| 2026-10-10 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt` | 2026-10-10T144712792914 -> 2026-10-10T202039438329 | 1 changed | quiet |
| 2026-10-10 | `remote/com.preshiftiq/shiftiq-mcp` | 2026-10-08T064206074704 -> 2026-10-10T202037819373 | 2 changed | quiet |
| 2026-10-10 | `remote/com.agenticdealernetwork/adn-gateway` | 2026-10-10T062513280212 -> 2026-10-10T202038148141 | 12 changed (every tool) | quiet |
| 2026-10-10 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-10T144659296029 -> 2026-10-10T202038165828 | 1 changed | quiet |
| 2026-10-10 | `remote/com.jojapi/product-barcode-api` | 2026-10-10T144707561467 -> 2026-10-10T202037213655 | 1 changed | quiet |
| 2026-10-10 | `remote/uk.co.buildbatch/buildbatch` | 2026-10-10T144659022860 -> 2026-10-10T202036194927 | 1 changed | quiet |
| 2026-10-10 | `remote/com.algotrada.cubicle/cubicle` | 2026-10-10T144658086955 -> 2026-10-10T202036838681 | 2 added | quiet |
| 2026-10-10 | `remote/com.prereason/mcp` | 2026-10-10T144654736480 -> 2026-10-10T202034409726 | 4 changed | quiet |
| 2026-10-10 | `remote/com.askmatchbox/matchbox` | 2026-10-10T062507385514 -> 2026-10-10T202035739252 | 2 changed | quiet |
| 2026-10-10 | `remote/org.aspern/aspern` | 2026-10-10T144710426343 -> 2026-10-10T202043425421 | 3 changed, 3 added | review |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 17496 substantive, 8007 that changed only numbers (a catalogue counter ticking, a date), 378 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 13231 | 5706 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 538 | 538 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `sistaminuten.se` | 91 | 2 | 0 | 89 |
| `afbudsrejser.dk` | 90 | 2 | 0 | 88 |
| `akkilahdot.fi` | 90 | 2 | 0 | 88 |
| `restplass.no` | 90 | 2 | 0 | 88 |
| `socialloop.ai` | 88 | 88 | 0 | 0 |
| `caseyjhand.com` | 77 | 77 | 0 | 0 |
| `dayze.com` | 69 | 69 | 0 | 0 |
| `fundinglandscape.com` | 65 | 36 | 29 | 0 |
| 3054 other operators | 9014 | 8536 | 453 | 25 |
