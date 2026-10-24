# MCP server tool changes

Last change observed 2026-10-24T19:04:34+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

47402 changes to a tool definition: 2087 npm releases (1841 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 45315 readings of hosted servers that found their tools changed; 2468 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-24 | `remote/shop.grokzilla/micro-pay.1` | 2026-10-22T052647123824 -> 2026-10-24T190435819670 | 5 added | review |
| 2026-10-24 | `remote/design.overflow/mcp` | 2026-10-22T110020192737 -> 2026-10-24T190436310713 | 1 changed | quiet |
| 2026-10-24 | `remote/studio.gradients/mcp` | 2026-10-24T125833778569 -> 2026-10-24T190434356712 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.privatelawattorneys/wiki-private-law` | 2026-10-24T113010283074 -> 2026-10-24T190432766165 | 5 changed | quiet |
| 2026-10-24 | `remote/fi.akkilahdot/travel-search` | 2026-10-24T125832088069 -> 2026-10-24T190432982551 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.sharan01x/usetested` | 2026-10-24T112945968048 -> 2026-10-24T190429876990 | 2 changed, 1 added | review |
| 2026-10-24 | `remote/io.github.MohDev212/verifypulse` | 2026-10-24T125829925540 -> 2026-10-24T190430740890 | 1 changed | review |
| 2026-10-24 | `remote/io.github.Fizzl13/x402-doctor` | 2026-10-23T120711750894 -> 2026-10-24T190430796525 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-10-24T050521858096 -> 2026-10-24T190429723603 | 1 changed | quiet |
| 2026-10-24 | `remote/se.sistaminuten/travel-search` | 2026-10-24T125807391212 -> 2026-10-24T190428788488 | 1 changed | quiet |
| 2026-10-24 | `remote/io.taifoon/coordination-layer.1` | 2026-10-24T112937502497 -> 2026-10-24T190428356416 | 1 changed | review |
| 2026-10-24 | `remote/dev.tanod/web` | 2026-10-22T105849786994 -> 2026-10-24T190428792771 | 2 changed | quiet |
| 2026-10-24 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-24T125823432283 -> 2026-10-24T190425215525 | 1 changed | quiet |
| 2026-10-24 | `remote/eu.gridgarden/studio` | 2026-10-23T233425162555 -> 2026-10-24T190427023263 | 1 changed | quiet |
| 2026-10-24 | `remote/cc.thecolony/mcp-server` | 2026-10-22T140852453039 -> 2026-10-24T190423950720 | 1 changed, 8 added | quiet |
| 2026-10-24 | `remote/net.rpscripts/fivem` | 2026-10-24T112813725217 -> 2026-10-24T190423205188 | 1 changed | quiet |
| 2026-10-24 | `remote/com.remoshift/jobs` | 2026-10-24T112802160891 -> 2026-10-24T190422845538 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.TRDEFI/liquidity` | 2026-10-24T113129682085 -> 2026-10-24T190422480951 | 1 changed | quiet |
| 2026-10-24 | `remote/no.restplass/travel-search` | 2026-10-24T125757170980 -> 2026-10-24T190419530359 | 1 changed | quiet |
| 2026-10-24 | `remote/pl.klyo/games` | 2026-10-23T233414900902 -> 2026-10-24T190419732354 | 1 changed | quiet |
| 2026-10-24 | `remote/dk.afbudsrejser/travel-search` | 2026-10-24T125756588393 -> 2026-10-24T190418334040 | 1 changed | quiet |
| 2026-10-24 | `remote/com.meridiandispatch/travel-guides` | 2026-10-24T113059947268 -> 2026-10-24T190418411592 | 4 changed, 2 added | quiet |
| 2026-10-24 | `remote/eu.nulegal/recht` | 2026-10-22T202058668065 -> 2026-10-24T190416325843 | 1 changed | quiet |
| 2026-10-24 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-10-24T050514438741 -> 2026-10-24T190416443147 | 2 changed | quiet |
| 2026-10-24 | `remote/io.github.tradingale/mcp` | 2026-10-22T110144587333 -> 2026-10-24T190414431273 | 1 changed | quiet |
| 2026-10-24 | `remote/org.thealibrary/thea` | 2026-10-24T050516584417 -> 2026-10-24T190414497710 | 1 changed | quiet |
| 2026-10-24 | `remote/com.vendooly/vendooly` | 2026-10-24T050511753771 -> 2026-10-24T190414337711 | 2 changed | quiet |
| 2026-10-24 | `remote/com.plainrouter/mcp` | 2026-10-23T233417154990 -> 2026-10-24T190414382920 | 3 changed | quiet |
| 2026-10-24 | `remote/ai.taasky/taasky` | 2026-10-22T105538990347 -> 2026-10-24T190412879271 | 2 changed | quiet |
| 2026-10-24 | `remote/io.github.muaviamohammed/mizan` | 2026-10-22T233936826270 -> 2026-10-24T190413916512 | 1 changed | quiet |
| 2026-10-24 | `remote/dev.tanod/tanod` | 2026-10-23T200831991450 -> 2026-10-24T190415589015 | 5 changed, 6 added | quiet |
| 2026-10-24 | `remote/dev.tanod/document-to-markdown` | 2026-10-22T105807771193 -> 2026-10-24T190415273833 | 1 changed | quiet |
| 2026-10-24 | `remote/dev.tanod/docs` | 2026-10-22T202053397011 -> 2026-10-24T190414912092 | 3 changed | quiet |
| 2026-10-24 | `remote/com.pagelemon/pagelemon` | 2026-10-24T050508849502 -> 2026-10-24T190411045906 | 2 changed | quiet |
| 2026-10-24 | `remote/co.civai.nova/support-agent-admin` | 2026-10-24T125802081663 -> 2026-10-24T190410155602 | 2 removed | quiet |
| 2026-10-24 | `remote/ai.spelunking/hub` | 2026-10-23T200803191007 -> 2026-10-24T190410867747 | 1 removed | quiet |
| 2026-10-24 | `remote/com.mrrledger/mrrledger` | 2026-10-23T200802940305 -> 2026-10-24T190409940036 | 1 added | review |
| 2026-10-24 | `remote/com.asksakina/islamic-knowledge` | 2026-10-23T200824732837 -> 2026-10-24T190409025606 | 4 changed (every tool) | quiet |
| 2026-10-24 | `remote/dev.mcphost/mcphost` | 2026-10-24T112435578899 -> 2026-10-24T190409105364 | 1 changed | quiet |
| 2026-10-24 | `remote/ai.rokha/rokha` | 2026-10-24T112806850541 -> 2026-10-24T190407944569 | 1 changed | quiet |
| 2026-10-24 | `remote/org.worldgdp/nowcasts` | 2026-10-24T125749408711 -> 2026-10-24T190407376729 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.choaticpixels/wicked-mcp` | 2026-10-24T050505537402 -> 2026-10-24T190408317176 | 1 added | quiet |
| 2026-10-24 | `remote/sh.openpath/openpath` | 2026-10-23T200818102599 -> 2026-10-24T190406143674 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.richardsolomou/praetorium` | 2026-10-24T050510558717 -> 2026-10-24T190407387833 | 3 changed | quiet |
| 2026-10-24 | `remote/com.webinarignition/mcp` | 2026-10-22T233910321287 -> 2026-10-24T190407231970 | 3 changed | quiet |
| 2026-10-24 | `remote/io.github.ondraulehla/mcpcost` | 2026-10-22T202038153881 -> 2026-10-24T190404247737 | 4 changed, 1 added (every tool) | quiet |
| 2026-10-24 | `remote/com.thefilmradar/filmlab` | 2026-10-24T125801320747 -> 2026-10-24T190404944165 | 6 changed | quiet |
| 2026-10-24 | `remote/com.sportstatsapi/sports-data` | 2026-10-24T112403751209 -> 2026-10-24T190404889266 | 2 changed, 1 added | quiet |
| 2026-10-24 | `remote/fun.lesgooo/lesgooo` | 2026-10-23T115923053563 -> 2026-10-24T190404018082 | 21 changed, 1 removed | quiet |
| 2026-10-24 | `remote/ch.kulalabs.pazair/pazair` | 2026-10-24T112707638441 -> 2026-10-24T190405385571 | 3 changed | quiet |
| 2026-10-24 | `remote/shop.grokzilla/micro-pay` | 2026-10-22T052607995666 -> 2026-10-24T190400800736 | 5 added | review |
| 2026-10-24 | `remote/io.github.lgs1520/agent-procurement-manager` | 2026-10-24T112220386264 -> 2026-10-24T190402140740 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.jamie7893/keelen` | 2026-10-22T105235993139 -> 2026-10-24T190401586657 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.smarterweather/weather` | 2026-10-22T202142400649 -> 2026-10-24T190400555631 | 6 changed, 2 added | quiet |
| 2026-10-24 | `remote/com.gameshopenter/shop` | 2026-10-23T052613591184 -> 2026-10-24T190401407056 | 3 changed | quiet |
| 2026-10-24 | `remote/ai.skuit/catalog` | 2026-10-23T120336814336 -> 2026-10-24T190400390745 | 1 changed | quiet |
| 2026-10-24 | `remote/tech.kaiku/kaiku.1` | 2026-10-24T050459841505 -> 2026-10-24T190400862233 | 3 added | quiet |
| 2026-10-24 | `remote/io.github.priors-agents/priors-read` | 2026-10-24T112435987155 -> 2026-10-24T190359480147 | 2 changed, 2 added | quiet |
| 2026-10-24 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-10-23T200807044653 -> 2026-10-24T190358737985 | 1 changed | review |
| 2026-10-24 | `remote/page.deed/deed-page` | 2026-10-22T202025024332 -> 2026-10-24T190357505526 | 1 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 29398 substantive, 17389 that changed only numbers (a catalogue counter ticking, a date), 615 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 25144 | 8777 | 16367 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 659 | 659 | 0 | 0 |
| `caseyjhand.com` | 198 | 198 | 0 | 0 |
| `sistaminuten.se` | 146 | 4 | 0 | 142 |
| `afbudsrejser.dk` | 145 | 4 | 0 | 141 |
| `akkilahdot.fi` | 145 | 4 | 0 | 141 |
| `restplass.no` | 145 | 4 | 0 | 141 |
| `socialloop.ai` | 141 | 141 | 0 | 0 |
| `remoshift.com` | 115 | 8 | 107 | 0 |
| `openkrill.app` | 111 | 111 | 0 | 0 |
| `fundinglandscape.com` | 110 | 71 | 39 | 0 |
| 5473 other operators | 18002 | 17076 | 876 | 50 |
