# MCP server tool changes

Last change observed 2026-10-23T23:34:44+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

45222 changes to a tool definition: 1988 npm releases (1742 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 43234 readings of hosted servers that found their tools changed; 2430 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-23 | `remote/no.restplass/travel-search` | 2026-10-23T200809566669 -> 2026-10-23T233445579366 | 1 changed | quiet |
| 2026-10-23 | `remote/dk.afbudsrejser/travel-search` | 2026-10-23T200808292864 -> 2026-10-23T233444827807 | 1 changed | quiet |
| 2026-10-23 | `remote/ai.trydock/dock` | 2026-10-21T202549089118 -> 2026-10-23T233441604959 | 1 changed | quiet |
| 2026-10-23 | `remote/io.taifoon/coordination-layer.1` | 2026-10-23T200844406812 -> 2026-10-23T233436230376 | 1 changed | review |
| 2026-10-23 | `remote/ai.usedby/usedby` | 2026-10-23T200844721883 -> 2026-10-23T233436605105 | 1 changed | quiet |
| 2026-10-23 | `remote/se.sistaminuten/travel-search` | 2026-10-23T200843149372 -> 2026-10-23T233435671280 | 1 changed | quiet |
| 2026-10-23 | `remote/dev.primitive/email` | 2026-10-22T052646146452 -> 2026-10-23T233431948574 | 14 changed (every tool) | quiet |
| 2026-10-23 | `remote/studio.gradients/mcp` | 2026-10-23T200853604545 -> 2026-10-23T233429926806 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.zambodotdev/zambo` | 2026-10-23T052619517765 -> 2026-10-23T233429484692 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.Licium-ai/licium` | 2026-10-21T234238622232 -> 2026-10-23T233430174555 | 9 changed, 7 added | review |
| 2026-10-23 | `remote/dev.zambo/zambo` | 2026-10-23T052619550114 -> 2026-10-23T233429565694 | 1 changed | quiet |
| 2026-10-23 | `remote/com.youspot/youspot` | 2026-10-23T200823571161 -> 2026-10-23T233429748902 | 1 changed | quiet |
| 2026-10-23 | `remote/fi.akkilahdot/travel-search` | 2026-10-23T200852300790 -> 2026-10-23T233429044339 | 1 changed | quiet |
| 2026-10-23 | `remote/net.umbhost/umbhost-mcp` | 2026-10-21T122120398627 -> 2026-10-23T233427583968 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.fredxhansson-cmyk/noniner` | 2026-10-21T234531569967 -> 2026-10-23T233427450996 | 5 added | quiet |
| 2026-10-23 | `remote/com.thenewengineer/hvac` | 2026-10-23T120534261647 -> 2026-10-23T233425705178 | 2 changed | quiet |
| 2026-10-23 | `remote/eu.gridgarden/studio` | 2026-10-21T122041386887 -> 2026-10-23T233425162555 | 1 changed | quiet |
| 2026-10-23 | `remote/com.tektolo/rental-property` | 2026-10-23T120746831177 -> 2026-10-23T233423898509 | 1 changed | quiet |
| 2026-10-23 | `remote/com.tektolo/capabilities` | 2026-10-23T120528432262 -> 2026-10-23T233424298041 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-23T200814906387 -> 2026-10-23T233422891992 | 2 changed, 5 added | quiet |
| 2026-10-23 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-23T200838971190 -> 2026-10-23T233423432991 | 1 changed | quiet |
| 2026-10-23 | `remote/dev.sportsapis/sportsapis` | 2026-10-23T200827981648 -> 2026-10-23T233423101545 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.davidgringras/scrutica` | 2026-10-22T202054422156 -> 2026-10-23T233422676663 | 2 changed | quiet |
| 2026-10-23 | `remote/ai.sfomo/events` | 2026-10-21T122119031200 -> 2026-10-23T233421225276 | 5 changed | quiet |
| 2026-10-23 | `remote/com.predictionmarketspicks/quant` | 2026-10-23T200823665333 -> 2026-10-23T233419847384 | 39 changed, 6 removed (every tool) | quiet |
| 2026-10-23 | `remote/com.pinsvit/api` | 2026-10-21T202527814783 -> 2026-10-23T233419147680 | 1 changed | quiet |
| 2026-10-23 | `remote/com.remoshift/jobs` | 2026-10-23T200829605168 -> 2026-10-23T233418867551 | 1 changed | quiet |
| 2026-10-23 | `remote/com.predictionmarketspicks/elections` | 2026-10-23T120356130131 -> 2026-10-23T233417350495 | 5 changed (every tool) | quiet |
| 2026-10-23 | `remote/app.manawa/manawa-terminal` | 2026-10-22T202137886220 -> 2026-10-23T233417275474 | 3 added | quiet |
| 2026-10-23 | `remote/com.plainrouter/mcp` | 2026-10-23T135144055708 -> 2026-10-23T233417154990 | 2 changed, 1 added, 1 removed | quiet |
| 2026-10-23 | `remote/com.holdingsintel/mcp` | 2026-10-23T120118639576 -> 2026-10-23T233416505772 | 8 removed | quiet |
| 2026-10-23 | `remote/com.predictionmarketspicks/crypto` | 2026-10-22T105713774225 -> 2026-10-23T233417598175 | 7 changed (every tool) | quiet |
| 2026-10-23 | `remote/com.predictionmarketspicks/commodities` | 2026-10-22T105713783052 -> 2026-10-23T233416710392 | 10 changed (every tool) | quiet |
| 2026-10-23 | `remote/pl.klyo/games` | 2026-10-21T234159317697 -> 2026-10-23T233414900902 | 1 changed | quiet |
| 2026-10-23 | `remote/md.mostlyright/datasets` | 2026-10-23T120251857370 -> 2026-10-23T233412340299 | 2 changed | quiet |
| 2026-10-23 | `remote/com.advisorfinder/mcp` | 2026-10-22T202133785632 -> 2026-10-23T233411820886 | 2 changed | quiet |
| 2026-10-23 | `remote/dev.mcphost/mcphost` | 2026-10-23T052602288513 -> 2026-10-23T233409993677 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.valuein/mcp-sec-edgar` | 2026-10-23T200758084424 -> 2026-10-23T233409273949 | 1 added | quiet |
| 2026-10-23 | `remote/io.github.lbailey94/whitemagic-mcp` | 2026-10-22T105507129958 -> 2026-10-23T233407591108 | 1 added | quiet |
| 2026-10-23 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-10-23T200812777582 -> 2026-10-23T233405434193 | 19 added | quiet |
| 2026-10-23 | `remote/cc.hlist/hlist-ai-tools` | 2026-10-23T200735817240 -> 2026-10-23T233405182722 | 1 changed | quiet |
| 2026-10-23 | `remote/com.soundza/soundza.1` | 2026-10-21T234146712795 -> 2026-10-23T233404692462 | 6 changed (every tool) | quiet |
| 2026-10-23 | `remote/ai.switchapp/switch` | 2026-10-23T200807203671 -> 2026-10-23T233403860999 | 13 changed | quiet |
| 2026-10-23 | `remote/ai.autonomad/travel` | 2026-10-23T120121830628 -> 2026-10-23T233400910924 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.fredxhansson-cmyk/fuze` | 2026-10-21T234217412657 -> 2026-10-23T233400548396 | 5 added | quiet |
| 2026-10-23 | `remote/com.hireahelper/mcp` | 2026-10-22T202038840798 -> 2026-10-23T233359305841 | 16 added | quiet |
| 2026-10-23 | `remote/tech.kaiku/kaiku.1` | 2026-10-23T200747965835 -> 2026-10-23T233359401463 | 8 added | quiet |
| 2026-10-23 | `remote/io.llmexpert/transcription` | 2026-10-22T202018872596 -> 2026-10-23T233357790566 | 1 added | quiet |
| 2026-10-23 | `remote/io.taifoon/coordination-layer` | 2026-10-23T200731334870 -> 2026-10-23T233401588161 | 1 changed | review |
| 2026-10-23 | `remote/io.github.OV3RK177/kairos-signal` | 2026-10-23T200755863816 -> 2026-10-23T233356937332 | 2 changed | quiet |
| 2026-10-23 | `remote/co.crevio/crevio` | 2026-10-23T120008408945 -> 2026-10-23T233356473579 | 1 changed | quiet |
| 2026-10-23 | `remote/com.kairossignal/kairos-signal` | 2026-10-23T200756744325 -> 2026-10-23T233356640248 | 2 changed | quiet |
| 2026-10-23 | `remote/co.ainumbers/tools` | 2026-10-23T200744968078 -> 2026-10-23T233357915861 | 2 changed | quiet |
| 2026-10-23 | `remote/ru.magnt/mcp-door` | 2026-10-23T115923383395 -> 2026-10-23T233356016427 | 1 changed | quiet |
| 2026-10-23 | `remote/com.thefilmradar/filmlab` | 2026-10-23T200756996087 -> 2026-10-23T233356592715 | 7 changed | quiet |
| 2026-10-23 | `remote/ai.capxule/capxule` | 2026-10-21T121044367091 -> 2026-10-23T233355497753 | 1 changed | quiet |
| 2026-10-23 | `remote/app.vercel.fork-for-agents/fork` | 2026-10-23T200748272409 -> 2026-10-23T233350974208 | 1 changed, 1 added | quiet |
| 2026-10-23 | `remote/io.github.stand-out-of-my-sun/diogenes-gateway` | 2026-10-21T121119009542 -> 2026-10-23T233350219628 | 5 changed | quiet |
| 2026-10-23 | `remote/cloud.dchub/mcp-server` | 2026-10-22T202009728690 -> 2026-10-23T233351157108 | 2 changed | quiet |
| 2026-10-23 | `remote/express.convert/transcribe` | 2026-10-23T115621260161 -> 2026-10-23T233348429173 | 13 changed, 1 added (every tool) | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 28748 substantive, 15877 that changed only numbers (a catalogue counter ticking, a date), 597 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 23651 | 8749 | 14902 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 657 | 657 | 0 | 0 |
| `caseyjhand.com` | 188 | 188 | 0 | 0 |
| `sistaminuten.se` | 142 | 4 | 0 | 138 |
| `afbudsrejser.dk` | 141 | 4 | 0 | 137 |
| `akkilahdot.fi` | 141 | 4 | 0 | 137 |
| `restplass.no` | 141 | 4 | 0 | 137 |
| `socialloop.ai` | 137 | 137 | 0 | 0 |
| `remoshift.com` | 112 | 8 | 104 | 0 |
| `fundinglandscape.com` | 108 | 71 | 37 | 0 |
| `openkrill.app` | 97 | 97 | 0 | 0 |
| 5337 other operators | 17366 | 16484 | 834 | 48 |
