# MCP server tool changes

Last change observed 2026-11-08T20:49:45+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

83557 changes to a tool definition: 3605 npm releases (3359 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 79952 readings of hosted servers that found their tools changed; 3604 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-08 | `remote/no.restplass/travel-search` | 2026-11-08T153905795828 -> 2026-11-08T204945785101 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.openaccountants/openaccountants` | 2026-11-08T153905743109 -> 2026-11-08T204945711361 | 1 changed | quiet |
| 2026-11-08 | `remote/de.objelio/immobiliensuche` | 2026-11-07T063959917274 -> 2026-11-08T204946056364 | 2 changed | quiet |
| 2026-11-08 | `remote/com.kiddinglab/kiddinglab` | 2026-11-07T133840938895 -> 2026-11-08T204945136883 | 5 changed | quiet |
| 2026-11-08 | `remote/dk.afbudsrejser/travel-search` | 2026-11-08T153903356479 -> 2026-11-08T204943064767 | 1 changed | quiet |
| 2026-11-08 | `remote/com.gotfreefax/mcp` | 2026-11-06T144849944398 -> 2026-11-08T204942609631 | 1 changed | review |
| 2026-11-08 | `remote/studio.gradients/mcp` | 2026-11-08T153908445167 -> 2026-11-08T204942692782 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.imokokok/insight-oracle` | 2026-11-08T135838548017 -> 2026-11-08T204945082860 | 3 changed | review |
| 2026-11-08 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-08T064544530918 -> 2026-11-08T204943327853 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.fmind/portfolio` | 2026-11-08T135810020976 -> 2026-11-08T204942383210 | 2 added | quiet |
| 2026-11-08 | `remote/com.veritaset/mcp` | 2026-11-06T144729417752 -> 2026-11-08T204943698338 | 2 changed | quiet |
| 2026-11-08 | `remote/fi.akkilahdot/travel-search` | 2026-11-08T153907891505 -> 2026-11-08T204941353308 | 1 changed | quiet |
| 2026-11-08 | `remote/com.usepickly/pickly` | 2026-11-08T135718247789 -> 2026-11-08T204945897333 | 4 changed | quiet |
| 2026-11-08 | `remote/com.toolsthatdontupload/tools` | 2026-11-06T144657398605 -> 2026-11-08T204941070097 | 3 added | quiet |
| 2026-11-08 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-08T064612406163 -> 2026-11-08T204941001297 | 8 added | quiet |
| 2026-11-08 | `remote/com.walletmcppass/wallet-mcp` | 2026-11-08T135717699238 -> 2026-11-08T204939563910 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-08T135706151396 -> 2026-11-08T204940220959 | 3 changed | quiet |
| 2026-11-08 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-08T135656998655 -> 2026-11-08T204939885424 | 11 added | review |
| 2026-11-08 | `remote/com.supercatch/supercatch` | 2026-11-08T135501807510 -> 2026-11-08T204939901549 | 3 changed | quiet |
| 2026-11-08 | `remote/cc.thecolony/mcp-server` | 2026-11-07T203332181684 -> 2026-11-08T204939231216 | 1 changed | quiet |
| 2026-11-08 | `remote/ca.tonbot.tolca/tolca` | 2026-11-07T203335453367 -> 2026-11-08T204937754233 | 1 changed | quiet |
| 2026-11-08 | `remote/xyz.t0ll/toll` | 2026-11-08T153903168916 -> 2026-11-08T204936645471 | 2 changed, 2 added | quiet |
| 2026-11-08 | `remote/io.stockmap/stockmap` | 2026-11-06T072807210461 -> 2026-11-08T204937190216 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-08T064608924826 -> 2026-11-08T204938415980 | 1 changed | quiet |
| 2026-11-08 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-08T064610242578 -> 2026-11-08T204938726913 | 2 changed | quiet |
| 2026-11-08 | `remote/com.tetheredtrust/tethered-trust` | 2026-11-08T064608306132 -> 2026-11-08T204937131046 | 3 changed | quiet |
| 2026-11-08 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-11-07T203329936366 -> 2026-11-08T204936684907 | 3 changed, 1 added | quiet |
| 2026-11-08 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-08T153901694092 -> 2026-11-08T204935296291 | 2 changed | quiet |
| 2026-11-08 | `remote/com.searchfragments/search-fragments` | 2026-11-06T144619629582 -> 2026-11-08T204934127485 | 1 changed | quiet |
| 2026-11-08 | `remote/com.brianbooms/quiet-menders.1` | 2026-11-08T135323802405 -> 2026-11-08T204934198571 | 27 changed | quiet |
| 2026-11-08 | `remote/wiki.rust/rust-wiki` | 2026-11-08T135525354302 -> 2026-11-08T204933901180 | 1 changed | quiet |
| 2026-11-08 | `remote/com.psychologieetserenite/catalogue` | 2026-11-07T203326446134 -> 2026-11-08T204934700918 | 2 changed | quiet |
| 2026-11-08 | `remote/io.github.lx1112/agent-data-api` | 2026-11-08T135227377533 -> 2026-11-08T204931864205 | 11 added | quiet |
| 2026-11-08 | `remote/io.github.jweezy119/Pabandi` | 2026-11-08T153851686639 -> 2026-11-08T204930654023 | 4 changed | quiet |
| 2026-11-08 | `remote/io.github.farenberglord-star/orb-studio` | 2026-11-07T133031542286 -> 2026-11-08T204930169754 | 2 added | quiet |
| 2026-11-08 | `remote/io.taifoon/coordination-layer.1` | 2026-11-08T135909400727 -> 2026-11-08T204929221899 | 1 changed | quiet |
| 2026-11-08 | `remote/se.sistaminuten/travel-search` | 2026-11-08T153858175999 -> 2026-11-08T204928991652 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.untitledfinancial/dpx` | 2026-11-08T064542313909 -> 2026-11-08T204927000603 | 2 added | quiet |
| 2026-11-08 | `remote/io.github.umairalisadaqat/weinc` | 2026-11-08T000119394466 -> 2026-11-08T204927583766 | 6 changed | quiet |
| 2026-11-08 | `remote/org.r3js/r3` | 2026-11-08T000110641952 -> 2026-11-08T204927287303 | 2 changed | quiet |
| 2026-11-08 | `remote/com.obriym-crm/mcp` | 2026-11-08T135303658260 -> 2026-11-08T204925235816 | 26 changed, 14 added | quiet |
| 2026-11-08 | `remote/ai.signal8/mcp` | 2026-11-08T064541844276 -> 2026-11-08T204926389728 | 1 changed | quiet |
| 2026-11-08 | `remote/com.anchorterminal/anchor-terminal` | 2026-11-08T135827038838 -> 2026-11-08T204924969681 | 2 changed, 2 added | quiet |
| 2026-11-08 | `remote/org.walkably/walkably` | 2026-11-07T132914637377 -> 2026-11-08T204923035518 | 3 changed (every tool) | quiet |
| 2026-11-08 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-08T135224373477 -> 2026-11-08T204922770984 | 10 changed | quiet |
| 2026-11-08 | `remote/io.github.ironflowsh/mcp` | 2026-11-08T134955988732 -> 2026-11-08T204924188419 | 4 changed, 4 added | quiet |
| 2026-11-08 | `remote/io.github.intoApex/tradingagentstack` | 2026-11-08T135720987490 -> 2026-11-08T204921984416 | 1 changed | quiet |
| 2026-11-08 | `remote/com.sonarconnections/sonar-connections` | 2026-11-08T153850537432 -> 2026-11-08T204921927065 | 3 added | quiet |
| 2026-11-08 | `remote/tax.terminal/filing` | 2026-11-07T203313799953 -> 2026-11-08T204921799366 | 1 changed | quiet |
| 2026-11-08 | `remote/io.tooloracle/quantum` | 2026-11-08T135714046570 -> 2026-11-08T204922504808 | 1 changed | quiet |
| 2026-11-08 | `remote/com.f1ow/f1ow.1` | 2026-11-08T134930051289 -> 2026-11-08T204921526810 | 4 changed, 1 added | quiet |
| 2026-11-08 | `remote/ai.securelend/lender` | 2026-11-08T135207645870 -> 2026-11-08T204920376240 | 1 changed, 1 added, 1 removed | quiet |
| 2026-11-08 | `remote/co.deadbrands/arena` | 2026-11-08T153841100781 -> 2026-11-08T204919548993 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.danafitkowski/cpp-cpm-engine` | 2026-11-08T134916339627 -> 2026-11-08T204918361803 | 3 changed, 1 added | quiet |
| 2026-11-08 | `remote/com.stocklens/stocklens` | 2026-11-06T072807340434 -> 2026-11-08T204917731148 | 3 changed, 1 added | quiet |
| 2026-11-08 | `remote/video.refs/refs` | 2026-11-08T135534175663 -> 2026-11-08T204919486018 | 14 changed (every tool) | quiet |
| 2026-11-08 | `remote/com.brianbooms/quiet-menders` | 2026-11-08T134901763497 -> 2026-11-08T204916899593 | 27 changed | quiet |
| 2026-11-08 | `remote/pl.finwire/data` | 2026-11-08T000110736464 -> 2026-11-08T204916956143 | 1 changed, 1 added | quiet |
| 2026-11-08 | `remote/io.github.truefixr/atlascast-truefixr` | 2026-11-08T134854458794 -> 2026-11-08T204916207368 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.lineofflight/frankfurter` | 2026-11-07T132722242813 -> 2026-11-08T204916436497 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 51500 substantive, 31150 that changed only numbers (a catalogue counter ticking, a date), 907 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 45119 | 15889 | 29230 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1843 | 1843 | 0 | 0 |
| `caseyjhand.com` | 354 | 354 | 0 | 0 |
| `sistaminuten.se` | 213 | 6 | 0 | 207 |
| `afbudsrejser.dk` | 212 | 6 | 0 | 206 |
| `akkilahdot.fi` | 212 | 6 | 0 | 206 |
| `restplass.no` | 212 | 6 | 0 | 206 |
| `socialloop.ai` | 204 | 204 | 0 | 0 |
| `revmesh2074.workers.dev` | 190 | 167 | 23 | 0 |
| `civai.co` | 188 | 188 | 0 | 0 |
| `modevc.com` | 174 | 174 | 0 | 0 |
| 8043 other operators | 32295 | 30316 | 1897 | 82 |
