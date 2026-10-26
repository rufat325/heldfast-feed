# MCP server tool changes

Last change observed 2026-10-26T05:23:36+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

50163 changes to a tool definition: 2189 npm releases (1943 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 47974 readings of hosted servers that found their tools changed; 2612 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-26 | `remote/com.zinvyl/marketplace` | 2026-10-25T132428445900 -> 2026-10-26T052338411931 | 2 changed | quiet |
| 2026-10-26 | `remote/studio.gradients/mcp` | 2026-10-25T225102454182 -> 2026-10-26T052336747288 | 1 changed | quiet |
| 2026-10-26 | `remote/io.github.privatelawattorneys/wiki-private-law` | 2026-10-24T224630762467 -> 2026-10-26T052336733777 | 2 changed | quiet |
| 2026-10-26 | `remote/fi.akkilahdot/travel-search` | 2026-10-25T225101485661 -> 2026-10-26T052336062855 | 1 changed | quiet |
| 2026-10-26 | `remote/gg.unicum/wot-stats` | 2026-10-25T191900525932 -> 2026-10-26T052334538344 | 1 added | quiet |
| 2026-10-26 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-25T225053925394 -> 2026-10-26T052331312388 | 1 changed | quiet |
| 2026-10-26 | `remote/io.github.birdwell/runescape-wiki-mcp` | 2026-10-25T132415411001 -> 2026-10-26T052329848189 | 2 added | quiet |
| 2026-10-26 | `remote/com.remoshift/jobs` | 2026-10-25T225050700733 -> 2026-10-26T052329411978 | 1 changed | quiet |
| 2026-10-26 | `remote/pl.klyo/games` | 2026-10-24T190419732354 -> 2026-10-26T052328311453 | 1 changed | quiet |
| 2026-10-26 | `remote/com.multicinesortega/cartelera` | 2026-10-25T225045716520 -> 2026-10-26T052327274065 | 1 changed | quiet |
| 2026-10-26 | `remote/com.socialseal/mcp` | 2026-10-24T112553309670 -> 2026-10-26T052324003953 | 11 changed | quiet |
| 2026-10-26 | `remote/ai.switchapp/switch` | 2026-10-25T191843170561 -> 2026-10-26T052323586312 | 2 changed, 1 added | quiet |
| 2026-10-26 | `remote/io.github.openvancamp/openvan-travel` | 2026-10-25T102153414585 -> 2026-10-26T052323664752 | 2 changed | quiet |
| 2026-10-26 | `remote/io.github.magichourhq/magic-hour` | 2026-10-25T102132524190 -> 2026-10-26T052320061105 | 25 changed | quiet |
| 2026-10-26 | `remote/com.kernelcad/kernelcad` | 2026-10-25T191839254691 -> 2026-10-26T052320875749 | 2 changed | quiet |
| 2026-10-26 | `remote/land.fabrica/mcp-testnet` | 2026-10-24T112320717401 -> 2026-10-26T052315116781 | 1 changed, 2 added, 2 removed | quiet |
| 2026-10-26 | `remote/com.thefilmradar/filmlab` | 2026-10-25T191835212825 -> 2026-10-26T052316034506 | 1 changed, 7 added | quiet |
| 2026-10-26 | `remote/io.github.drexthealpha/knos` | 2026-10-25T191831645316 -> 2026-10-26T052313918005 | 15 changed | quiet |
| 2026-10-26 | `remote/net.hotelrefund/price-tracker` | 2026-10-25T052239493299 -> 2026-10-26T052309080748 | 1 changed | quiet |
| 2026-10-26 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-10-25T052258508003 -> 2026-10-26T052307684819 | 2 changed | quiet |
| 2026-10-26 | `remote/io.github.LE-VAI/designesy-org` | 2026-10-25T052257784749 -> 2026-10-26T052307061001 | 2 changed | quiet |
| 2026-10-26 | `remote/io.github.AKzar1el/god-prompt-mcp` | 2026-10-25T225030220146 -> 2026-10-26T052308750230 | 2 changed | quiet |
| 2026-10-26 | `remote/io.github.exquad/thecablecode` | 2026-10-25T191837945775 -> 2026-10-26T052304338173 | 1 added | quiet |
| 2026-10-26 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-10-25T191910765650 -> 2026-10-26T052306408170 | 30 changed | quiet |
| 2026-10-26 | `remote/cc.thecolony/mcp-server` | 2026-10-25T191838226880 -> 2026-10-26T052305148613 | 1 added | quiet |
| 2026-10-26 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-25T191835381643 -> 2026-10-26T052301887974 | 1 changed | quiet |
| 2026-10-26 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-25T052253609167 -> 2026-10-26T052301196861 | 1 changed | quiet |
| 2026-10-26 | `remote/no.restplass/travel-search` | 2026-10-25T225154580282 -> 2026-10-26T052302625230 | 1 changed | quiet |
| 2026-10-26 | `remote/io.github.samuelzcom/chauffeur-booking` | 2026-10-25T052250812741 -> 2026-10-26T052259592697 | 1 changed | quiet |
| 2026-10-26 | `remote/com.findbroadbanddeals/broadband-deals` | 2026-10-25T191908056349 -> 2026-10-26T052300851195 | 2 changed | quiet |
| 2026-10-26 | `remote/se.sistaminuten/travel-search` | 2026-10-25T225056232420 -> 2026-10-26T052256753882 | 1 changed | quiet |
| 2026-10-26 | `remote/io.taifoon/coordination-layer.1` | 2026-10-25T191849110781 -> 2026-10-26T052257124574 | 1 changed | review |
| 2026-10-26 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-10-25T191850809130 -> 2026-10-26T052258184226 | 30 changed | quiet |
| 2026-10-26 | `remote/dk.afbudsrejser/travel-search` | 2026-10-25T225151159916 -> 2026-10-26T052259123876 | 1 changed | quiet |
| 2026-10-26 | `remote/io.huntertech/vendor-insights` | 2026-10-24T112921355599 -> 2026-10-26T052256121277 | 4 changed (every tool) | quiet |
| 2026-10-26 | `remote/com.ferntool/ip` | 2026-10-25T052300353320 -> 2026-10-26T052255501633 | 1 added | quiet |
| 2026-10-26 | `remote/app.vercel.fork-for-agents/fork` | 2026-10-25T225028939955 -> 2026-10-26T052259540268 | 1 changed | quiet |
| 2026-10-26 | `remote/com.webinarignition/mcp` | 2026-10-25T225041746294 -> 2026-10-26T052255781258 | 2 changed | quiet |
| 2026-10-26 | `remote/com.tkawen/intelligence-gateway` | 2026-10-25T132421400632 -> 2026-10-26T052255355797 | 7 changed, 3 added | quiet |
| 2026-10-26 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-25T225052985528 -> 2026-10-26T052255774552 | 3 added | quiet |
| 2026-10-26 | `remote/net.totallytarot/calculators` | 2026-10-25T102408494798 -> 2026-10-26T052253810282 | 8 changed | quiet |
| 2026-10-26 | `remote/com.trustbaselab/rcb-data` | 2026-10-25T132414932882 -> 2026-10-26T052255461650 | 1 changed | quiet |
| 2026-10-26 | `remote/com.thefomite/fomite` | 2026-10-25T052255664696 -> 2026-10-26T052253273948 | 1 changed | quiet |
| 2026-10-26 | `remote/com.sportstatsapi/sports-data` | 2026-10-25T225038650484 -> 2026-10-26T052254521429 | 1 changed | quiet |
| 2026-10-26 | `remote/net.praegant/landhaus` | 2026-10-24T112343289296 -> 2026-10-26T052252733215 | 2 changed | quiet |
| 2026-10-26 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt` | 2026-10-25T225027949479 -> 2026-10-26T052255373988 | 2 changed | quiet |
| 2026-10-26 | `remote/fr.synergieloc/immobilier` | 2026-10-25T225144076493 -> 2026-10-26T052252603966 | 1 changed, 11 added | quiet |
| 2026-10-26 | `remote/com.idosgames/platform` | 2026-10-25T225044276897 -> 2026-10-26T052249345394 | 27 changed | quiet |
| 2026-10-26 | `remote/io.github.equinoxaifinance-rgb/proof-fetch` | 2026-10-25T102248665753 -> 2026-10-26T052247249572 | 2 changed | quiet |
| 2026-10-26 | `remote/co.ainumbers/tools` | 2026-10-25T225030630429 -> 2026-10-26T052248531421 | 4 changed | quiet |
| 2026-10-26 | `remote/site.chatgpt.orellise.relay-agent-services/relay` | 2026-10-25T225137986127 -> 2026-10-26T052247688566 | 1 added | quiet |
| 2026-10-26 | `remote/ai.rokha/rokha` | 2026-10-24T190407944569 -> 2026-10-26T052247040175 | 13 changed | quiet |
| 2026-10-26 | `remote/io.github.edtool79-collab/hirepulse-gateway` | 2026-10-25T225025895792 -> 2026-10-26T052245308468 | 8 changed | quiet |
| 2026-10-26 | `remote/io.github.barneywohl/hugging-bay` | 2026-10-25T191813557530 -> 2026-10-26T052245364543 | 28 changed (every tool) | quiet |
| 2026-10-26 | `remote/ca.gpucloud/gpu-cloud` | 2026-10-25T102052199976 -> 2026-10-26T052245184095 | 3 changed, 1 added | quiet |
| 2026-10-26 | `remote/io.github.cloakmaster/pact0` | 2026-10-24T224619325236 -> 2026-10-26T052244309066 | 1 changed | quiet |
| 2026-10-26 | `remote/com.nicevois/rvc-training` | 2026-10-25T102148937780 -> 2026-10-26T052243565073 | 8 changed, 3 added | quiet |
| 2026-10-26 | `remote/cloud.redu/mcp` | 2026-10-25T191826517690 -> 2026-10-26T052244464208 | 3 changed, 1 added | quiet |
| 2026-10-26 | `remote/page.deed/deed-page` | 2026-10-25T052237051295 -> 2026-10-26T052245579184 | 3 changed, 1 added | quiet |
| 2026-10-26 | `remote/land.fabrica/mcp` | 2026-10-24T112331304892 -> 2026-10-26T052242077192 | 1 added, 1 removed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 32044 substantive, 17467 that changed only numbers (a catalogue counter ticking, a date), 652 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 26731 | 10363 | 16368 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 775 | 775 | 0 | 0 |
| `caseyjhand.com` | 220 | 220 | 0 | 0 |
| `sistaminuten.se` | 154 | 4 | 0 | 150 |
| `afbudsrejser.dk` | 153 | 4 | 0 | 149 |
| `akkilahdot.fi` | 153 | 4 | 0 | 149 |
| `restplass.no` | 153 | 4 | 0 | 149 |
| `socialloop.ai` | 148 | 148 | 0 | 0 |
| `remoshift.com` | 123 | 8 | 115 | 0 |
| `fundinglandscape.com` | 118 | 77 | 41 | 0 |
| `openkrill.app` | 111 | 111 | 0 | 0 |
| 5609 other operators | 18983 | 17985 | 943 | 55 |
