# MCP server tool changes

Last change observed 2026-10-26T21:15:33+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

52838 changes to a tool definition: 2293 npm releases (2047 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 50545 readings of hosted servers that found their tools changed; 2773 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-26 | `remote/uk.zarvo/padel` | 2026-10-26T133933934483 -> 2026-10-26T211535846943 | 7 changed | quiet |
| 2026-10-26 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-10-26T153244109291 -> 2026-10-26T211534777956 | 5 changed, 2 removed | quiet |
| 2026-10-26 | `remote/no.restplass/travel-search` | 2026-10-26T153243347445 -> 2026-10-26T211533757807 | 1 changed | quiet |
| 2026-10-26 | `remote/io.github.joverman/xrplink` | 2026-10-26T133931544000 -> 2026-10-26T211534712303 | 1 changed | quiet |
| 2026-10-26 | `remote/dev.pressmark/pressmark` | 2026-10-26T133800946090 -> 2026-10-26T211532912207 | 2 changed | quiet |
| 2026-10-26 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-10-26T153218714246 -> 2026-10-26T211533143277 | 5 changed, 2 removed | quiet |
| 2026-10-26 | `remote/com.test-well/testwell` | 2026-10-24T112937882884 -> 2026-10-26T211531997454 | 2 changed | quiet |
| 2026-10-26 | `remote/io.taifoon/coordination-layer.1` | 2026-10-26T133915989900 -> 2026-10-26T211531200710 | 1 changed | review |
| 2026-10-26 | `remote/io.huntertech/vendor-insights.3` | 2026-10-26T133753891088 -> 2026-10-26T211531882709 | 3 changed | quiet |
| 2026-10-26 | `remote/com.findbroadbanddeals/broadband-deals` | 2026-10-26T052300851195 -> 2026-10-26T211531499686 | 3 changed | quiet |
| 2026-10-26 | `remote/se.sistaminuten/travel-search` | 2026-10-26T153215955564 -> 2026-10-26T211531231686 | 1 changed | quiet |
| 2026-10-26 | `remote/dk.afbudsrejser/travel-search` | 2026-10-26T153238270084 -> 2026-10-26T211530140893 | 1 changed | quiet |
| 2026-10-26 | `remote/com.techfabric/techfabric` | 2026-10-26T133725541093 -> 2026-10-26T211527900484 | 6 changed | quiet |
| 2026-10-26 | `remote/io.github.HuangGoodmanAgency/edgar-and-edgarette` | 2026-10-25T102959349585 -> 2026-10-26T211524157194 | 26 changed (every tool) | quiet |
| 2026-10-26 | `remote/com.prenotomenu/menu` | 2026-10-26T133706496672 -> 2026-10-26T211524599545 | 1 changed | quiet |
| 2026-10-26 | `remote/io.github.paulieb89/uk-legal-mcp` | 2026-10-24T112954697031 -> 2026-10-26T211524928553 | 1 changed | quiet |
| 2026-10-26 | `remote/xyz.trusteed/mcp-gateway` | 2026-10-25T115805292683 -> 2026-10-26T211524019145 | 1 changed | quiet |
| 2026-10-26 | `remote/lol.wukong.world/agent-world` | 2026-10-26T133625387070 -> 2026-10-26T211520621032 | 2 added | quiet |
| 2026-10-26 | `remote/com.zinvyl/marketplace` | 2026-10-26T052338411931 -> 2026-10-26T211520170177 | 12 changed | quiet |
| 2026-10-26 | `remote/xyz.urbangametheory/urban-game-theory` | 2026-10-26T133754022429 -> 2026-10-26T211520140772 | 1 changed | quiet |
| 2026-10-26 | `remote/io.github.cyanheads/us-drought-monitor-mcp-server` | 2026-10-26T133753394211 -> 2026-10-26T211518304417 | 7 changed (every tool) | quiet |
| 2026-10-26 | `remote/dev.upfork/upfork` | 2026-10-25T191839790687 -> 2026-10-26T211518078137 | 7 changed | quiet |
| 2026-10-26 | `remote/net.totallytarot/calculators` | 2026-10-26T052253810282 -> 2026-10-26T211515810895 | 18 changed (every tool) | quiet |
| 2026-10-26 | `remote/io.theagentforge/forge` | 2026-10-26T133611204859 -> 2026-10-26T211516552452 | 3 changed | quiet |
| 2026-10-26 | `remote/fr.synergieloc/immobilier` | 2026-10-26T133547872559 -> 2026-10-26T211517470914 | 13 added | quiet |
| 2026-10-26 | `remote/com.thejohnsislander/the-johns-islander` | 2026-10-26T133522862989 -> 2026-10-26T211514099411 | 1 changed | quiet |
| 2026-10-26 | `remote/com.theaiintegrationhub/use-cases` | 2026-10-26T133605849290 -> 2026-10-26T211514274712 | 2 changed, 1 added | quiet |
| 2026-10-26 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-10-26T133534613926 -> 2026-10-26T211514262018 | 4 added | review |
| 2026-10-26 | `remote/studio.gradients/mcp` | 2026-10-26T153206162661 -> 2026-10-26T211511362408 | 1 changed | quiet |
| 2026-10-26 | `remote/io.github.Standard-Trade/trade-evidence` | 2026-10-26T133451522863 -> 2026-10-26T211507619871 | 5 changed (every tool) | quiet |
| 2026-10-26 | `remote/fi.akkilahdot/travel-search` | 2026-10-26T153202713583 -> 2026-10-26T211508290202 | 1 changed | quiet |
| 2026-10-26 | `remote/com.tabzoola/pricing` | 2026-10-26T133708354311 -> 2026-10-26T211509857481 | 3 changed | quiet |
| 2026-10-26 | `remote/pro.sebbi/governance` | 2026-10-26T133453219056 -> 2026-10-26T211505807821 | 12 added | quiet |
| 2026-10-26 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-26T133446225426 -> 2026-10-26T211506397272 | 3 added | quiet |
| 2026-10-26 | `remote/link.snip/snip` | 2026-10-26T133439766205 -> 2026-10-26T211506181557 | 2 changed, 6 added | quiet |
| 2026-10-26 | `remote/com.0xpi.sdsentry/sds-lookup` | 2026-10-25T225137861377 -> 2026-10-26T211505483376 | 3 changed | quiet |
| 2026-10-26 | `remote/com.lordevo/shop` | 2026-10-26T133431144338 -> 2026-10-26T211505369344 | 7 changed, 22 added | review |
| 2026-10-26 | `remote/re.rundata/temps-reel` | 2026-10-26T153214308231 -> 2026-10-26T211503931448 | 29 changed (every tool) | quiet |
| 2026-10-26 | `remote/fyi.smartfin/smartfin` | 2026-10-24T112742276217 -> 2026-10-26T211504197963 | 1 changed | review |
| 2026-10-26 | `remote/com.jennipro.shop/shop-local` | 2026-10-26T133635441872 -> 2026-10-26T211502498495 | 2 changed | quiet |
| 2026-10-26 | `remote/io.github.martinPisacreta/textokit-mcp` | 2026-10-26T133405878466 -> 2026-10-26T211502964341 | 1 changed, 1 added | review |
| 2026-10-26 | `remote/com.theagentsindex/mcp` | 2026-10-25T052258583469 -> 2026-10-26T211500148548 | 1 changed | quiet |
| 2026-10-26 | `remote/ua.com.quintadb/mcp` | 2026-10-26T133412285821 -> 2026-10-26T211500268115 | 102 changed | quiet |
| 2026-10-26 | `remote/com.quintadb/mcp` | 2026-10-26T133337685069 -> 2026-10-26T211500140031 | 102 changed | quiet |
| 2026-10-26 | `remote/link.rentgpu/gpu-market` | 2026-10-26T133603729621 -> 2026-10-26T211458796806 | 1 added | quiet |
| 2026-10-26 | `remote/com.stayotter/stay-otter` | 2026-10-26T133334242540 -> 2026-10-26T211457307593 | 2 changed, 1 added | quiet |
| 2026-10-26 | `remote/io.github.mooshee/pressmark` | 2026-10-26T133323803946 -> 2026-10-26T211456648793 | 2 changed | quiet |
| 2026-10-26 | `remote/io.github.Fizzl13/presign-guard` | 2026-10-26T133356138576 -> 2026-10-26T211456291482 | 3 changed | quiet |
| 2026-10-26 | `remote/io.pocketcaddie/drills` | 2026-10-26T133335249878 -> 2026-10-26T211454963942 | 1 changed, 5 added | quiet |
| 2026-10-26 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-26T153147111694 -> 2026-10-26T211454937878 | 1 changed | quiet |
| 2026-10-26 | `remote/ru.quintadb/mcp` | 2026-10-26T133551401351 -> 2026-10-26T211457153620 | 102 changed | quiet |
| 2026-10-26 | `remote/io.github.richardsolomou/praetorium` | 2026-10-26T133355404149 -> 2026-10-26T211456525904 | 3 changed | quiet |
| 2026-10-26 | `remote/io.github.jakegallen/poascan` | 2026-10-26T133540804732 -> 2026-10-26T211451530999 | 1 changed, 4 added | quiet |
| 2026-10-26 | `remote/io.github.cyanheads/openfda-mcp-server` | 2026-10-25T102202239678 -> 2026-10-26T211451624457 | 11 changed | quiet |
| 2026-10-26 | `remote/dev.workers.nextgenmovers.ngm-agent-api/movers` | 2026-10-26T133303848594 -> 2026-10-26T211448669121 | 4 changed (every tool) | review |
| 2026-10-26 | `remote/com.nadveo/service-booking` | 2026-10-25T191829123980 -> 2026-10-26T211448886280 | 1 changed, 1 added | quiet |
| 2026-10-26 | `remote/com.mrrledger/mrrledger` | 2026-10-24T190409940036 -> 2026-10-26T211448607751 | 5 changed | quiet |
| 2026-10-26 | `remote/com.remoshift/jobs` | 2026-10-26T153139704446 -> 2026-10-26T211448372492 | 1 changed | quiet |
| 2026-10-26 | `remote/io.github.arthursantosmedia-stack/mestrepratico-brazil-prices-mcp` | 2026-10-26T133237476306 -> 2026-10-26T211446398200 | 12 changed (every tool) | quiet |
| 2026-10-26 | `remote/io.github.canoydario847-cloud/privi-call` | 2026-10-26T133207263758 -> 2026-10-26T211445133543 | 1 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 34651 substantive, 17523 that changed only numbers (a catalogue counter ticking, a date), 664 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 28526 | 12158 | 16368 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 891 | 891 | 0 | 0 |
| `caseyjhand.com` | 233 | 233 | 0 | 0 |
| `sistaminuten.se` | 157 | 4 | 0 | 153 |
| `afbudsrejser.dk` | 156 | 4 | 0 | 152 |
| `akkilahdot.fi` | 156 | 4 | 0 | 152 |
| `restplass.no` | 156 | 4 | 0 | 152 |
| `socialloop.ai` | 151 | 151 | 0 | 0 |
| `remoshift.com` | 126 | 8 | 118 | 0 |
| `fundinglandscape.com` | 121 | 77 | 44 | 0 |
| `revmesh2074.workers.dev` | 115 | 106 | 9 | 0 |
| 5855 other operators | 19709 | 18670 | 984 | 55 |
