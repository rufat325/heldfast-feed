# MCP server tool changes

Last change observed 2026-11-13T20:08:12+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

98120 changes to a tool definition: 4084 npm releases (3838 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 94036 readings of hosted servers that found their tools changed; 4034 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-13 | `remote/no.restplass/travel-search` | 2026-11-13T150825413296 -> 2026-11-13T200812791927 | 1 changed | quiet |
| 2026-11-13 | `remote/com.tabflows/site` | 2026-11-13T013143910251 -> 2026-11-13T200813882608 | 1 changed | quiet |
| 2026-11-13 | `remote/com.starcovery/mcp` | 2026-11-13T013143725968 -> 2026-11-13T200813041362 | 10 added | quiet |
| 2026-11-13 | `remote/com.kulicadvisory/aictionbot-werkbank` | 2026-11-12T155047414844 -> 2026-11-13T200811790097 | 2 changed | quiet |
| 2026-11-13 | `remote/dk.afbudsrejser/travel-search` | 2026-11-13T150738027062 -> 2026-11-13T200809625254 | 1 changed | quiet |
| 2026-11-13 | `remote/io.taifoon/coordination-layer.1` | 2026-11-13T150651741361 -> 2026-11-13T200812865719 | 1 changed | quiet |
| 2026-11-13 | `remote/se.sistaminuten/travel-search` | 2026-11-13T150647827144 -> 2026-11-13T200806735705 | 1 changed | quiet |
| 2026-11-13 | `remote/ai.uetr/uetr.ai` | 2026-11-12T074743577221 -> 2026-11-13T200811684912 | 2 changed, 1 added | quiet |
| 2026-11-13 | `remote/com.conved/mcp` | 2026-11-13T115929865165 -> 2026-11-13T200758487649 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.christianscode1994/volatiai-mcp` | 2026-11-12T170930710766 -> 2026-11-13T200756302220 | 1 changed, 11 removed | quiet |
| 2026-11-13 | `remote/io.suverse.versum/catalog` | 2026-11-13T115848574627 -> 2026-11-13T200755491285 | 1 changed | quiet |
| 2026-11-13 | `remote/ai.modulos/demo-booking` | 2026-11-12T155322587759 -> 2026-11-13T200755153637 | 4 added | review |
| 2026-11-13 | `remote/studio.gradients/mcp` | 2026-11-13T150229436175 -> 2026-11-13T200751660173 | 1 changed | quiet |
| 2026-11-13 | `remote/fi.akkilahdot/travel-search` | 2026-11-13T150212357069 -> 2026-11-13T200750140906 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.MsingathiM/swapeazi` | 2026-11-13T150355348265 -> 2026-11-13T200749716225 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-13T124207643124 -> 2026-11-13T200751091408 | 16 added | quiet |
| 2026-11-13 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-13T120506687732 -> 2026-11-13T200746895185 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.cyanheads/un-comtrade-mcp-server` | 2026-11-12T155141598213 -> 2026-11-13T200744792009 | 7 changed, 1 added | quiet |
| 2026-11-13 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-12T154749789076 -> 2026-11-13T200746433192 | 31 added | quiet |
| 2026-11-13 | `remote/com.seraphixsystems/public-records` | 2026-11-13T115651004969 -> 2026-11-13T200744387022 | 5 added | quiet |
| 2026-11-13 | `remote/agency.thirdhemisphere/ai-authority-index` | 2026-11-12T154743404240 -> 2026-11-13T200744608899 | 6 changed | quiet |
| 2026-11-13 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-13T013223105318 -> 2026-11-13T200741718649 | 1 changed | quiet |
| 2026-11-13 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-13T124200850656 -> 2026-11-13T200742380048 | 2 changed | quiet |
| 2026-11-13 | `remote/com.swarmbar/swarmbar` | 2026-11-12T154708256860 -> 2026-11-13T200740627230 | 2 changed | quiet |
| 2026-11-13 | `remote/app.lovable.privacy-pill-consent-studio/privacypill` | 2026-11-12T154554658277 -> 2026-11-13T200743131677 | 1 added | quiet |
| 2026-11-13 | `remote/io.github.richardsolomou/praetorium` | 2026-11-11T230853884276 -> 2026-11-13T200739756757 | 3 changed | quiet |
| 2026-11-13 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-13T150022015818 -> 2026-11-13T200736070041 | 1 changed | quiet |
| 2026-11-13 | `remote/ch.kulalabs.pazair/pazair` | 2026-11-13T115519695095 -> 2026-11-13T200737639061 | 2 changed | quiet |
| 2026-11-13 | `remote/io.github.QDThead/signal-lab` | 2026-11-13T150010081506 -> 2026-11-13T200734654999 | 2 added | quiet |
| 2026-11-13 | `remote/com.serviche/sergio` | 2026-11-13T120236593453 -> 2026-11-13T200739267290 | 5 changed | quiet |
| 2026-11-13 | `remote/com.seqbench/workbench` | 2026-11-13T145958279604 -> 2026-11-13T200732520195 | 1 changed | quiet |
| 2026-11-13 | `remote/com.nielslangereis/thinking` | 2026-11-11T145339690769 -> 2026-11-13T200732865025 | 1 added | quiet |
| 2026-11-13 | `remote/io.github.jakegallen/poascan` | 2026-11-12T074723965890 -> 2026-11-13T200730789931 | 2 changed | quiet |
| 2026-11-13 | `remote/com.moaibuy/moa` | 2026-11-13T115428565407 -> 2026-11-13T200730787674 | 4 changed | quiet |
| 2026-11-13 | `remote/gg.plazmi/plazmi` | 2026-11-12T074723257799 -> 2026-11-13T200729716641 | 1 changed | quiet |
| 2026-11-13 | `remote/com.runheed/runheed` | 2026-11-13T115624948780 -> 2026-11-13T200728927072 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.smarterweather/weather` | 2026-11-13T115342250510 -> 2026-11-13T200726764065 | 2 changed | quiet |
| 2026-11-13 | `remote/dev.rackrates/ledger` | 2026-11-13T124132244556 -> 2026-11-13T200729432063 | 1 added | review |
| 2026-11-13 | `remote/dev.pcbbrew/pcbbrew` | 2026-11-13T115512159432 -> 2026-11-13T200726685194 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.cyanheads/pubmed-mcp-server` | 2026-11-11T145532022265 -> 2026-11-13T200725184736 | 6 changed | quiet |
| 2026-11-13 | `remote/ai.signal8/mcp` | 2026-11-13T150053148698 -> 2026-11-13T200725953191 | 1 changed | quiet |
| 2026-11-13 | `remote/org.oravan/mcp` | 2026-11-13T115452220589 -> 2026-11-13T200723700350 | 1 changed | quiet |
| 2026-11-13 | `remote/no.pristavla/pristavla` | 2026-11-13T013206276247 -> 2026-11-13T200723494223 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.medprice-ai/mcp-medprice-ai` | 2026-11-12T154231074818 -> 2026-11-13T200721444870 | 3 changed | quiet |
| 2026-11-13 | `remote/com.getmattered/getmattered` | 2026-11-13T145912006265 -> 2026-11-13T200721183042 | 1 changed | quiet |
| 2026-11-13 | `remote/work.finder/jobs` | 2026-11-13T013106974182 -> 2026-11-13T200718773784 | 2 changed | quiet |
| 2026-11-13 | `remote/com.othermindset/campus` | 2026-11-13T150116642904 -> 2026-11-13T200718711186 | 1 changed | quiet |
| 2026-11-13 | `remote/com.dimhour/catalog` | 2026-11-13T013106016273 -> 2026-11-13T200715897106 | 11 changed | quiet |
| 2026-11-13 | `remote/com.budgetpixel/mcp` | 2026-11-13T115144737106 -> 2026-11-13T200714591857 | 3 changed | review |
| 2026-11-13 | `remote/com.blockreq/rpc` | 2026-11-13T115141830010 -> 2026-11-13T200714002718 | 3 changed | quiet |
| 2026-11-13 | `remote/io.github.assinafy/mcp-server` | 2026-11-12T154107467119 -> 2026-11-13T200714083053 | 8 changed | quiet |
| 2026-11-13 | `remote/com.splitscanner/mcp` | 2026-11-12T154314294866 -> 2026-11-13T200715718305 | 1 changed | quiet |
| 2026-11-13 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-13T115928526892 -> 2026-11-13T200713545645 | 13 changed, 3 added | quiet |
| 2026-11-13 | `remote/md.mostlyright/datasets` | 2026-11-13T115417271977 -> 2026-11-13T200712442598 | 6 changed | quiet |
| 2026-11-13 | `remote/io.github.federico2001/openglass-mcp` | 2026-11-13T115229056812 -> 2026-11-13T200710548770 | 2 changed | quiet |
| 2026-11-13 | `remote/gl.parse/mcp` | 2026-11-13T115235612195 -> 2026-11-13T200713217963 | 5 changed | review |
| 2026-11-13 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-11-13T115217588827 -> 2026-11-13T200708926857 | 4 changed | review |
| 2026-11-13 | `remote/io.github.valuein/mcp-sec-edgar` | 2026-11-13T013146447352 -> 2026-11-13T200711135805 | 2 changed, 3 added | quiet |
| 2026-11-13 | `remote/eu.tradedashboard/eu-trade-explorer` | 2026-11-12T170853968032 -> 2026-11-13T200708966030 | 2 added, 34 removed | quiet |
| 2026-11-13 | `remote/tax.terminal/filing` | 2026-11-12T170837685098 -> 2026-11-13T200706850658 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 60142 substantive, 36982 that changed only numbers (a catalogue counter ticking, a date), 996 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 52526 | 17762 | 34764 | 0 |
| `a2awire.com` | 2375 | 2375 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 405 | 405 | 0 | 0 |
| `civai.co` | 317 | 317 | 0 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `revmesh2074.workers.dev` | 239 | 209 | 30 | 0 |
| `sistaminuten.se` | 232 | 6 | 0 | 226 |
| `afbudsrejser.dk` | 231 | 6 | 0 | 225 |
| `akkilahdot.fi` | 231 | 6 | 0 | 225 |
| `restplass.no` | 231 | 6 | 0 | 225 |
| `socialloop.ai` | 223 | 223 | 0 | 0 |
| 9268 other operators | 38511 | 36228 | 2188 | 95 |
