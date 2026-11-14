# MCP server tool changes

Last change observed 2026-11-14T18:34:16+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

99251 changes to a tool definition: 4181 npm releases (3935 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 95070 readings of hosted servers that found their tools changed; 4112 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-14 | `remote/io.github.zodiacs-org/zodiacs` | 2026-11-14T140256936626 -> 2026-11-14T183421363821 | 7 changed | quiet |
| 2026-11-14 | `remote/studio.gradients/mcp` | 2026-11-14T140212258038 -> 2026-11-14T183403651712 | 1 changed | quiet |
| 2026-11-14 | `remote/fi.akkilahdot/travel-search` | 2026-11-14T140145572560 -> 2026-11-14T183400699710 | 1 changed | quiet |
| 2026-11-14 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-14T115035076074 -> 2026-11-14T183403028524 | 8 added | quiet |
| 2026-11-14 | `remote/xyz.tereno/tereno` | 2026-11-13T120022877965 -> 2026-11-14T183359042342 | 3 changed | review |
| 2026-11-14 | `remote/no.restplass/travel-search` | 2026-11-14T140204394872 -> 2026-11-14T183359457976 | 1 changed | quiet |
| 2026-11-14 | `remote/com.starcovery/mcp` | 2026-11-14T010701796171 -> 2026-11-14T183359964199 | 2 changed | quiet |
| 2026-11-14 | `remote/se.sistaminuten/travel-search` | 2026-11-14T140356009127 -> 2026-11-14T183358567642 | 1 changed | quiet |
| 2026-11-14 | `remote/com.oxfordledge/oxford-ledge` | 2026-11-14T140338046084 -> 2026-11-14T183357869199 | 12 changed | quiet |
| 2026-11-14 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-14T140111691198 -> 2026-11-14T183358461089 | 3 changed | quiet |
| 2026-11-14 | `remote/com.kulicadvisory/aictionbot-werkbank` | 2026-11-14T140148354859 -> 2026-11-14T183357283108 | 17 changed, 22 added | quiet |
| 2026-11-14 | `remote/gg.unicum/wot-stats` | 2026-11-12T155143053672 -> 2026-11-14T183356959016 | 1 changed | quiet |
| 2026-11-14 | `remote/app.fluxgraph/linkedin` | 2026-11-14T140139541542 -> 2026-11-14T183356537738 | 69 changed, 2 added (every tool) | review |
| 2026-11-14 | `remote/dk.afbudsrejser/travel-search` | 2026-11-14T140120563840 -> 2026-11-14T183355552170 | 1 changed | quiet |
| 2026-11-14 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-14T140025012636 -> 2026-11-14T183352468762 | 4 changed | quiet |
| 2026-11-14 | `remote/io.github.utilify-io/utilify-mcp` | 2026-11-14T010649680335 -> 2026-11-14T183349755496 | 1 changed | quiet |
| 2026-11-14 | `remote/com.trackerhacker/mcp` | 2026-11-14T140012027617 -> 2026-11-14T183350311556 | 1 changed | quiet |
| 2026-11-14 | `remote/com.stayotter/stay-otter` | 2026-11-13T120322171045 -> 2026-11-14T183347394112 | 1 changed | quiet |
| 2026-11-14 | `remote/com.workers-rights/employment-law` | 2026-11-14T140217651356 -> 2026-11-14T183345978292 | 2 changed | quiet |
| 2026-11-14 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-14T135936758177 -> 2026-11-14T183345645420 | 1 changed | quiet |
| 2026-11-14 | `remote/com.seraphixsystems/public-records` | 2026-11-14T114939507798 -> 2026-11-14T183343402855 | 1 changed | review |
| 2026-11-14 | `remote/io.suverse.versum/catalog` | 2026-11-14T140035733751 -> 2026-11-14T183342116640 | 3 changed | quiet |
| 2026-11-14 | `remote/com.serviche/sergio` | 2026-11-13T200739267290 -> 2026-11-14T183345515065 | 1 changed | quiet |
| 2026-11-14 | `remote/at.space-core/game` | 2026-11-14T010646781783 -> 2026-11-14T183343810503 | 1 changed, 1 added | quiet |
| 2026-11-14 | `remote/io.github.rnwy/mcp` | 2026-11-13T013156622688 -> 2026-11-14T183338415485 | 1 changed | quiet |
| 2026-11-14 | `remote/com.remoshift/jobs` | 2026-11-13T145930891465 -> 2026-11-14T183336233454 | 1 changed | quiet |
| 2026-11-14 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-14T114923798329 -> 2026-11-14T183336604040 | 4 added | quiet |
| 2026-11-14 | `remote/cc.thecolony/mcp-server` | 2026-11-13T115804194927 -> 2026-11-14T183334744450 | 1 changed, 1 added | quiet |
| 2026-11-14 | `remote/gg.pixly/mcp` | 2026-11-12T154744907616 -> 2026-11-14T183333623384 | 1 changed | quiet |
| 2026-11-14 | `remote/com.crm-connector/crm-connector` | 2026-11-13T115524953552 -> 2026-11-14T183332609377 | 63 changed (every tool) | quiet |
| 2026-11-14 | `remote/ai.nexez/commerce` | 2026-11-14T135653788733 -> 2026-11-14T183327851187 | 1 changed | quiet |
| 2026-11-14 | `remote/network.skv/skv` | 2026-11-14T135848612608 -> 2026-11-14T183328060688 | 38 changed (every tool) | quiet |
| 2026-11-14 | `remote/io.github.lx1112/agent-data-api` | 2026-11-14T135637990227 -> 2026-11-14T183327398372 | 1 added | quiet |
| 2026-11-14 | `remote/ca.movahedi/privacy` | 2026-11-13T145748879281 -> 2026-11-14T183325248339 | 1 changed | quiet |
| 2026-11-14 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-14T114957419604 -> 2026-11-14T183325346755 | 3 changed, 1 added | quiet |
| 2026-11-14 | `remote/com.googleapis.memorystore/mcp` | 2026-11-14T135626154130 -> 2026-11-14T183324295589 | 7 changed | quiet |
| 2026-11-14 | `remote/network.tier1protocol/tier1` | 2026-11-14T135555591150 -> 2026-11-14T183322193106 | 2 changed | quiet |
| 2026-11-14 | `remote/com.zobrx/zobrx` | 2026-11-14T135548616346 -> 2026-11-14T183323070254 | 7 changed | quiet |
| 2026-11-14 | `remote/io.github.untitledfinancial/dpx` | 2026-11-14T135530378494 -> 2026-11-14T183320431774 | 5 changed | review |
| 2026-11-14 | `remote/com.stocklens/stocklens` | 2026-11-14T010637092531 -> 2026-11-14T183320361034 | 11 changed (every tool) | quiet |
| 2026-11-14 | `remote/market.populardemand/popular-demand` | 2026-11-14T135518491154 -> 2026-11-14T183319504842 | 14 changed (every tool) | quiet |
| 2026-11-14 | `remote/dev.releasealert/mcp` | 2026-11-13T013200785242 -> 2026-11-14T183319521339 | 1 changed, 1 added, 1 removed | quiet |
| 2026-11-14 | `remote/com.ortexo/mcp` | 2026-11-13T200704366961 -> 2026-11-14T183318780001 | 1 changed | quiet |
| 2026-11-14 | `remote/app.lovable.release-ripple-roadmap/logpulse` | 2026-11-14T135753481259 -> 2026-11-14T183322857956 | 1 added | quiet |
| 2026-11-14 | `remote/eu.paymentslaw/legislation` | 2026-11-13T150020845313 -> 2026-11-14T183318252098 | 15 changed (every tool) | quiet |
| 2026-11-14 | `remote/io.github.ironflowsh/hyperliquid` | 2026-11-13T200701243790 -> 2026-11-14T183316608565 | 2 changed | review |
| 2026-11-14 | `remote/com.plainrouter/mcp` | 2026-11-14T135702871745 -> 2026-11-14T183316212048 | 1 changed | quiet |
| 2026-11-14 | `remote/com.hedwigai/hedwigai` | 2026-11-13T115230725113 -> 2026-11-14T183315083594 | 4 changed, 2 added, 1 removed | quiet |
| 2026-11-14 | `remote/org.glolaw/glo-law` | 2026-11-14T114947501331 -> 2026-11-14T183315467697 | 1 changed | quiet |
| 2026-11-14 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-11-14T010617457621 -> 2026-11-14T183314762458 | 1 changed | review |
| 2026-11-14 | `remote/io.github.MelanieABC/misim-tax-research` | 2026-11-13T115212647804 -> 2026-11-14T183313724414 | 2 changed, 2 added | quiet |
| 2026-11-14 | `remote/io.github.daniel3303/equibles` | 2026-11-14T114947694628 -> 2026-11-14T183314410425 | 2 changed, 1 added | quiet |
| 2026-11-14 | `remote/com.jobshifu/jobshifu.1` | 2026-11-14T135400461218 -> 2026-11-14T183312123582 | 1 changed | quiet |
| 2026-11-14 | `remote/com.cev-os/data` | 2026-11-13T115547229887 -> 2026-11-14T183311677789 | 3 removed | quiet |
| 2026-11-14 | `remote/com.dimhour/catalog` | 2026-11-14T135319794068 -> 2026-11-14T183311292904 | 1 changed | quiet |
| 2026-11-14 | `remote/co.deadbrands/arena` | 2026-11-14T114942430591 -> 2026-11-14T183311170005 | 3 changed | quiet |
| 2026-11-14 | `remote/io.github.grzesir/botspot-trading` | 2026-11-13T013126232278 -> 2026-11-14T183308168566 | 115 changed (every tool) | review |
| 2026-11-14 | `remote/com.midasiteurope/civil-nx` | 2026-11-14T114905680572 -> 2026-11-14T183306726752 | 1 changed | quiet |
| 2026-11-14 | `remote/io.github.lilcityholdings-bit/keptvow` | 2026-11-13T115339761268 -> 2026-11-14T183304332417 | 1 added | quiet |
| 2026-11-14 | `remote/com.streaming-lens.mcp/streaming-radar` | 2026-11-12T154210390450 -> 2026-11-14T183303295517 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 61192 substantive, 37045 that changed only numbers (a catalogue counter ticking, a date), 1014 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 52535 | 17771 | 34764 | 0 |
| `a2awire.com` | 2508 | 2508 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 420 | 420 | 0 | 0 |
| `civai.co` | 318 | 318 | 0 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `revmesh2074.workers.dev` | 255 | 223 | 32 | 0 |
| `sistaminuten.se` | 236 | 6 | 0 | 230 |
| `afbudsrejser.dk` | 235 | 6 | 0 | 229 |
| `akkilahdot.fi` | 235 | 6 | 0 | 229 |
| `restplass.no` | 235 | 6 | 0 | 229 |
| `socialloop.ai` | 227 | 227 | 0 | 0 |
| 9380 other operators | 39448 | 37102 | 2249 | 97 |
