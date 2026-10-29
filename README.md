# MCP server tool changes

Last change observed 2026-10-29T15:38:15+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

61615 changes to a tool definition: 2574 npm releases (2328 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 59041 readings of hosted servers that found their tools changed; 2972 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-29 | `remote/no.restplass/travel-search` | 2026-10-29T133228234228 -> 2026-10-29T153816924107 | 1 changed | quiet |
| 2026-10-29 | `remote/dev.pressmark/pressmark` | 2026-10-29T133225313516 -> 2026-10-29T153816947854 | 4 changed | quiet |
| 2026-10-29 | `remote/dk.afbudsrejser/travel-search` | 2026-10-29T133152673237 -> 2026-10-29T153813796807 | 1 changed | quiet |
| 2026-10-29 | `remote/io.github.mooshee/untax` | 2026-10-27T054109218177 -> 2026-10-29T153810874874 | 2 added, 2 removed | quiet |
| 2026-10-29 | `remote/dev.tanod/ml` | 2026-10-28T133233654837 -> 2026-10-29T153807401741 | 1 added | quiet |
| 2026-10-29 | `remote/io.taifoon/coordination-layer.1` | 2026-10-29T133935285686 -> 2026-10-29T153804563745 | 1 added | review |
| 2026-10-29 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-29T133005078088 -> 2026-10-29T153803612581 | 3 changed | quiet |
| 2026-10-29 | `remote/se.sistaminuten/travel-search` | 2026-10-29T133930982183 -> 2026-10-29T153805366003 | 1 changed | quiet |
| 2026-10-29 | `remote/at.space-core/game` | 2026-10-28T153239463777 -> 2026-10-29T153805946634 | 2 changed | quiet |
| 2026-10-29 | `remote/com.straelo/relay` | 2026-10-29T104304833922 -> 2026-10-29T153757577175 | 2 added | quiet |
| 2026-10-29 | `remote/com.voyagehacks/travel` | 2026-10-29T104427406895 -> 2026-10-29T153755893655 | 1 changed | quiet |
| 2026-10-29 | `remote/studio.gradients/mcp` | 2026-10-29T133839633834 -> 2026-10-29T153754417451 | 1 changed | quiet |
| 2026-10-29 | `remote/io.github.domusdeiug/muyiribi` | 2026-10-29T133740851201 -> 2026-10-29T153754233044 | 1 changed | quiet |
| 2026-10-29 | `remote/fi.akkilahdot/travel-search` | 2026-10-29T133807374031 -> 2026-10-29T153752527337 | 1 changed | quiet |
| 2026-10-29 | `remote/com.thefomite/fomite` | 2026-10-29T063218481425 -> 2026-10-29T153752275858 | 1 changed | quiet |
| 2026-10-29 | `remote/ru.vedarai/mcp` | 2026-10-29T104434466766 -> 2026-10-29T153750710280 | 7 changed | quiet |
| 2026-10-29 | `remote/io.github.Tonys-Coding/sysketch` | 2026-10-29T133649963925 -> 2026-10-29T153748032020 | 1 changed | quiet |
| 2026-10-29 | `remote/dev.tanod/tanod` | 2026-10-29T133655686407 -> 2026-10-29T153751936716 | 1 added | quiet |
| 2026-10-29 | `remote/com.simafri/professional-email` | 2026-10-29T133643516965 -> 2026-10-29T153746448891 | 2 added | quiet |
| 2026-10-29 | `remote/ai.signal8/mcp` | 2026-10-29T104054937211 -> 2026-10-29T153746246636 | 3 changed, 1 added | quiet |
| 2026-10-29 | `remote/org.r3js/r3` | 2026-10-27T145828205037 -> 2026-10-29T153746955814 | 1 changed, 3 added | quiet |
| 2026-10-29 | `remote/com.swarmmemo/bulletin.1` | 2026-10-27T210150478759 -> 2026-10-29T153741857851 | 1 changed | quiet |
| 2026-10-29 | `remote/com.swarmmemo/bulletin` | 2026-10-27T210149856913 -> 2026-10-29T153741534485 | 1 changed | quiet |
| 2026-10-29 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-29T133559849876 -> 2026-10-29T153739750530 | 1 changed | quiet |
| 2026-10-29 | `remote/io.slopit/slopit` | 2026-10-29T133554138579 -> 2026-10-29T153740399286 | 4 changed | quiet |
| 2026-10-29 | `remote/io.github.lxxmng/container-loading` | 2026-10-29T132606479157 -> 2026-10-29T153740205056 | 1 changed | quiet |
| 2026-10-29 | `remote/io.github.ghostswap1/mcp` | 2026-10-29T103944982906 -> 2026-10-29T153739789050 | 1 changed, 1 added | quiet |
| 2026-10-29 | `remote/io.dropyour/dropyour` | 2026-10-28T212359640777 -> 2026-10-29T153740028205 | 1 changed | quiet |
| 2026-10-29 | `remote/com.remoshift/jobs` | 2026-10-29T133454351696 -> 2026-10-29T153736503145 | 1 changed | quiet |
| 2026-10-29 | `remote/co.deadbrands/arena` | 2026-10-29T132520212640 -> 2026-10-29T153736309519 | 49 changed | quiet |
| 2026-10-29 | `remote/pl.przetargowyjanusz/tenders` | 2026-10-29T133507521688 -> 2026-10-29T153735593930 | 1 changed | quiet |
| 2026-10-29 | `remote/ai.oriiion/oriiion` | 2026-10-29T133518984227 -> 2026-10-29T153733120900 | 1 changed | quiet |
| 2026-10-29 | `remote/es.proceres/proceres` | 2026-10-29T133500676602 -> 2026-10-29T153732433620 | 9 changed | quiet |
| 2026-10-29 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-10-28T062232554920 -> 2026-10-29T153735614849 | 2 changed | quiet |
| 2026-10-29 | `remote/io.github.jakegallen/poascan` | 2026-10-29T063210163113 -> 2026-10-29T153730383825 | 1 changed | quiet |
| 2026-10-29 | `remote/com.vibe-fixer/vibefix` | 2026-10-29T104351375471 -> 2026-10-29T153729093189 | 2 changed | quiet |
| 2026-10-29 | `remote/io.github.praveenjuge/vadivam` | 2026-10-29T104344985250 -> 2026-10-29T153727316187 | 2 changed | quiet |
| 2026-10-29 | `remote/net.tasklite/mcp` | 2026-10-29T104025950113 -> 2026-10-29T153725271307 | 2 changed | quiet |
| 2026-10-29 | `remote/com.senzing/mcp` | 2026-10-29T063210440551 -> 2026-10-29T153721323519 | 2 changed | quiet |
| 2026-10-29 | `remote/ai.switchapp/switch` | 2026-10-29T063211440100 -> 2026-10-29T153722346664 | 5 changed, 3 added | quiet |
| 2026-10-29 | `remote/io.github.vassiliylakhonin/agenda-intelligence-md.9` | 2026-10-28T131637694781 -> 2026-10-29T153715622798 | 1 changed | quiet |
| 2026-10-29 | `remote/io.github.mooshee/pressmark` | 2026-10-29T133146022031 -> 2026-10-29T153715395742 | 4 changed | quiet |
| 2026-10-29 | `remote/com.jobmojito/jobmojito` | 2026-10-28T132452859474 -> 2026-10-29T153715869992 | 4 changed | quiet |
| 2026-10-29 | `remote/com.hireahelper/mcp` | 2026-10-29T133008089382 -> 2026-10-29T153714554251 | 16 removed | quiet |
| 2026-10-29 | `remote/io.github.tradewr333-lgtm/degenscan-intel` | 2026-10-29T132106191316 -> 2026-10-29T153712991069 | 3 added | quiet |
| 2026-10-29 | `remote/io.github.Payotte-com/payotte-mcp` | 2026-10-29T104047036724 -> 2026-10-29T153712159393 | 54 added | quiet |
| 2026-10-29 | `remote/com.cutconvert/converter` | 2026-10-28T131604412864 -> 2026-10-29T153711084331 | 1 added | quiet |
| 2026-10-29 | `remote/io.taifoon/coordination-layer` | 2026-10-29T132051343219 -> 2026-10-29T153714565580 | 1 added | review |
| 2026-10-29 | `remote/build.naru/contract-compass` | 2026-10-28T131551913183 -> 2026-10-29T153713613959 | 1 changed | quiet |
| 2026-10-29 | `remote/io.github.pscale-commons/bsp-mcp` | 2026-10-29T132001848790 -> 2026-10-29T153704445978 | 2 changed | quiet |
| 2026-10-29 | `remote/io.github.industrial-platform-ai/link-extractor` | 2026-10-29T133000051361 -> 2026-10-29T153704546202 | 1 changed | quiet |
| 2026-10-29 | `remote/com.adrianhomelab/leadgen-onrc` | 2026-10-28T132300610941 -> 2026-10-29T153705396883 | 1 changed | quiet |
| 2026-10-29 | `remote/com.tensorust/mcp` | 2026-10-27T123621024772 -> 2026-10-29T153703768878 | 4 added | review |
| 2026-10-29 | `remote/com.pandavideo/mcp` | 2026-10-28T212321313944 -> 2026-10-29T153658507760 | 5 changed, 11 added | review |
| 2026-10-29 | `remote/dev.pages.freetier-agent-api/freetier-agent-api` | 2026-10-29T132526729966 -> 2026-10-29T153657316060 | 18 added | review |
| 2026-10-29 | `remote/app.vercel.fork-for-agents/fork` | 2026-10-29T132523283102 -> 2026-10-29T153655475819 | 1 changed | quiet |
| 2026-10-29 | `remote/ai.entityenricher/enricher` | 2026-10-28T131607010139 -> 2026-10-29T153658190394 | 3 added | quiet |
| 2026-10-29 | `remote/page.deed/deed-page` | 2026-10-28T062056511130 -> 2026-10-29T153650984670 | 3 changed | quiet |
| 2026-10-29 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-29T103437657572 -> 2026-10-29T153652208113 | 3 changed | quiet |
| 2026-10-29 | `remote/io.github.vassiliylakhonin/agenda-intelligence-md.7` | 2026-10-28T131516768473 -> 2026-10-29T153649464638 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 41345 substantive, 19553 that changed only numbers (a catalogue counter ticking, a date), 717 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 34063 | 15829 | 18234 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1126 | 1126 | 0 | 0 |
| `caseyjhand.com` | 269 | 269 | 0 | 0 |
| `sistaminuten.se` | 170 | 6 | 0 | 164 |
| `afbudsrejser.dk` | 169 | 6 | 0 | 163 |
| `akkilahdot.fi` | 169 | 6 | 0 | 163 |
| `restplass.no` | 169 | 6 | 0 | 163 |
| `socialloop.ai` | 163 | 163 | 0 | 0 |
| `remoshift.com` | 139 | 10 | 129 | 0 |
| `fundinglandscape.com` | 130 | 82 | 48 | 0 |
| `revmesh2074.workers.dev` | 129 | 116 | 13 | 0 |
| 6459 other operators | 22578 | 21385 | 1129 | 64 |
