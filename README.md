# MCP server tool changes

Last change observed 2026-10-06T13:39:47+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10128 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 21701 hosted endpoints (read daily, and every four hours while they keep changing).

22275 changes to a tool definition: 789 npm releases (543 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 21486 readings of hosted servers that found their tools changed; 282 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-06 | `remote/com.riddle/creator` | 2026-10-02T130148294032 -> 2026-10-06T133951082124 | 37 changed, 3 added | quiet |
| 2026-10-06 | `remote/com.n9t2/xrpl-agent-gateway` | 2026-10-06T113433124958 -> 2026-10-06T133950392013 | 19 changed (every tool) | quiet |
| 2026-10-06 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-10-06T110214097038 -> 2026-10-06T133947309395 | 1 changed | quiet |
| 2026-10-06 | `remote/se.sistaminuten/travel-search` | 2026-10-06T113431122201 -> 2026-10-06T133940955306 | 1 changed | quiet |
| 2026-10-06 | `remote/de.overfit/overfit` | 2026-10-06T110203221042 -> 2026-10-06T133937796275 | 24 changed (every tool) | quiet |
| 2026-10-06 | `remote/cc.thecolony/mcp-server` | 2026-10-06T110143536763 -> 2026-10-06T133929937688 | 3 changed, 5 added | quiet |
| 2026-10-06 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-10-06T110358180846 -> 2026-10-06T133922313019 | 2 changed | quiet |
| 2026-10-06 | `remote/fi.akkilahdot/travel-search` | 2026-10-06T113409217155 -> 2026-10-06T133917289215 | 1 changed | quiet |
| 2026-10-06 | `remote/no.restplass/travel-search` | 2026-10-06T113424168876 -> 2026-10-06T133912633321 | 1 changed | quiet |
| 2026-10-06 | `remote/com.withdoorman/doorman` | 2026-10-06T110136987512 -> 2026-10-06T133907276993 | 1 changed, 5 added | quiet |
| 2026-10-06 | `remote/dk.afbudsrejser/travel-search` | 2026-10-06T113417298854 -> 2026-10-06T133848601956 | 1 changed | quiet |
| 2026-10-06 | `remote/co.truerent/rental-review` | 2026-09-23T160958499864 -> 2026-10-06T133837246974 | 2 changed, 1 added, 1 removed (every tool) | quiet |
| 2026-10-06 | `remote/io.github.dtajitdinov-aris/sphere-marketplace` | 2026-10-03T121441191946 -> 2026-10-06T133820111206 | 11 changed | quiet |
| 2026-10-06 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-06T113358142012 -> 2026-10-06T133810953755 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.spokenmd/spoken` | 2026-10-06T110053527939 -> 2026-10-06T133810461556 | 8 changed (every tool) | quiet |
| 2026-10-06 | `remote/store.slopapp/slopstore` | 2026-10-06T110232536694 -> 2026-10-06T133808193361 | 17 changed (every tool) | quiet |
| 2026-10-06 | `remote/io.github.89rat/code402` | 2026-10-06T110011813211 -> 2026-10-06T133806969728 | 1 changed | quiet |
| 2026-10-06 | `remote/com.quintadb/mcp` | 2026-10-05T172640265541 -> 2026-10-06T133806003579 | 10 changed, 12 added | quiet |
| 2026-10-06 | `remote/io.github.SidneyBissoli/sih-br-mcp` | 2026-09-30T060124548937 -> 2026-10-06T133803664669 | 12 changed (every tool) | quiet |
| 2026-10-06 | `remote/io.github.Flikah/scout-mcp` | 2026-09-23T160930452882 -> 2026-10-06T133750089775 | 1 changed | quiet |
| 2026-10-06 | `remote/dev.workers.fhi-llc-1118.polished-truth-c514/fhi-x402-security-tools` | 2026-10-06T105955243151 -> 2026-10-06T133748602015 | 1 added | quiet |
| 2026-10-06 | `remote/com.plainrouter/mcp` | 2026-10-04T233801520503 -> 2026-10-06T133745789371 | 14 changed, 1 added, 1 removed (every tool) | quiet |
| 2026-10-06 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-06T113405470363 -> 2026-10-06T133741857134 | 2 changed | quiet |
| 2026-10-06 | `remote/net.clickwise/mcp` | 2026-10-06T105943041182 -> 2026-10-06T133734134241 | 1 changed | quiet |
| 2026-10-06 | `remote/com.remoshift/jobs` | 2026-10-06T113353405524 -> 2026-10-06T133730201246 | 1 changed | quiet |
| 2026-10-06 | `remote/ru.quintadb/mcp` | 2026-10-05T172655386069 -> 2026-10-06T133724179847 | 10 changed, 12 added | quiet |
| 2026-10-06 | `remote/ai.namewhisper/ens-tools` | 2026-09-23T160650228394 -> 2026-10-06T133705391244 | 12 changed | quiet |
| 2026-10-06 | `remote/io.github.vdmeu/registrum-mcp` | 2026-09-23T162938094305 -> 2026-10-06T133657902387 | 3 changed | quiet |
| 2026-10-06 | `remote/net.clickwise/product-catalog` | 2026-10-06T013120361248 -> 2026-10-06T133654240625 | 1 changed | quiet |
| 2026-10-06 | `remote/re.parcellai/parcellaire` | 2026-10-06T105948431810 -> 2026-10-06T133654594348 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.moralito311-andr/andreax` | 2026-09-30T152226080786 -> 2026-10-06T133657651282 | 3 changed | review |
| 2026-10-06 | `remote/ua.com.quintadb/mcp` | 2026-10-05T172643856370 -> 2026-10-06T133654591166 | 10 changed, 12 added | quiet |
| 2026-10-06 | `remote/mu.micro/mu` | 2026-09-27T141931451656 -> 2026-10-06T133652049630 | 5 added | quiet |
| 2026-10-06 | `remote/com.zeamprism/prism-mcp` | 2026-10-06T105854995101 -> 2026-10-06T133639964034 | 10 changed | quiet |
| 2026-10-06 | `remote/dev.nichedb/nichedb` | 2026-09-26T045354003100 -> 2026-10-06T133631635036 | 2 changed, 1 added | quiet |
| 2026-10-06 | `remote/com.tkawen/intelligence-gateway` | 2026-10-06T013121246421 -> 2026-10-06T133624100046 | 1 changed, 4 removed | quiet |
| 2026-10-06 | `remote/io.github.minsooparkk/korea-tax-law-mcp` | 2026-09-23T160620661214 -> 2026-10-06T133617788275 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.salemalem/npmscan` | 2026-10-06T110011714022 -> 2026-10-06T133614283741 | 11 changed | quiet |
| 2026-10-06 | `remote/com.vendooly/vendooly` | 2026-10-06T110025867302 -> 2026-10-06T133601310514 | 1 changed | quiet |
| 2026-10-06 | `remote/dev.mentio/mcp` | 2026-10-06T105748301767 -> 2026-10-06T133527418488 | 2 changed | quiet |
| 2026-10-06 | `remote/com.mailvakt/mailvakt` | 2026-10-06T105746721962 -> 2026-10-06T133525776434 | 8 changed (every tool) | quiet |
| 2026-10-06 | `remote/com.peppolstatus/api` | 2026-10-06T105953467358 -> 2026-10-06T133524981157 | 1 changed | quiet |
| 2026-10-06 | `remote/com.sinhvu/mcp` | 2026-10-06T105919072452 -> 2026-10-06T133522525071 | 1 changed | quiet |
| 2026-10-06 | `remote/com.jojapi/product-barcode-api` | 2026-10-06T105735265445 -> 2026-10-06T133514300835 | 1 changed | quiet |
| 2026-10-06 | `remote/immo.rundum/real-estate-appraisal` | 2026-10-02T071833269289 -> 2026-10-06T133514049376 | 3 changed | quiet |
| 2026-10-06 | `remote/ai.gondola/gondola` | 2026-10-03T120914761073 -> 2026-10-06T133502650019 | 3 added | quiet |
| 2026-10-06 | `remote/io.github.keelage/mcp` | 2026-10-06T105924407909 -> 2026-10-06T133453913434 | 5 changed, 1 added | quiet |
| 2026-10-06 | `remote/io.github.NeoDemosHQ/neodemos` | 2026-09-23T160732613794 -> 2026-10-06T133450142563 | 1 changed | quiet |
| 2026-10-06 | `remote/com.hotelscasa/hotelscasa-mcp` | 2026-10-01T134150525589 -> 2026-10-06T133444574861 | 3 changed | quiet |
| 2026-10-06 | `remote/org.living-bread.mcp/living-bread` | 2026-10-06T105837786996 -> 2026-10-06T133435152200 | 6 changed, 5 added | quiet |
| 2026-10-06 | `remote/io.echelongraph/echelongraph-mcp` | 2026-10-06T105816345710 -> 2026-10-06T133411794207 | 8 changed | quiet |
| 2026-10-06 | `remote/io.fless/mcp` | 2026-10-01T133943493072 -> 2026-10-06T133411194371 | 1 changed | quiet |
| 2026-10-06 | `remote/co.cookie-compliance/cookie-consent` | 2026-10-06T105810066225 -> 2026-10-06T133405044047 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.Airtreks/airtreks-mcp` | 2026-10-02T125632747130 -> 2026-10-06T133350529895 | 10 changed | quiet |
| 2026-10-06 | `remote/co.getclippy/clippy` | 2026-10-06T105818764340 -> 2026-10-06T133336354832 | 3 changed | quiet |
| 2026-10-06 | `remote/dev.ludoteca/ludoteca` | 2026-10-06T105813314293 -> 2026-10-06T133329726208 | 1 changed | quiet |
| 2026-10-06 | `remote/trade.loomdesk/loomdesk` | 2026-10-06T105812410683 -> 2026-10-06T133328088289 | 11 changed, 1 added (every tool) | quiet |
| 2026-10-06 | `remote/io.github.89rat/openfang-rail` | 2026-10-06T105532268758 -> 2026-10-06T133244372258 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.pipeworx-io/symmap` | 2026-10-02T182259857369 -> 2026-10-06T133224984611 | 4 changed | quiet |
| 2026-10-06 | `remote/io.github.agenttrust-ai/agenttrust.1` | 2026-10-06T105715497421 -> 2026-10-06T133222573843 | 4 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 15534 substantive, 6425 that changed only numbers (a catalogue counter ticking, a date), 316 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 11736 | 5690 | 6046 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `sistaminuten.se` | 77 | 2 | 0 | 75 |
| `afbudsrejser.dk` | 76 | 2 | 0 | 74 |
| `akkilahdot.fi` | 76 | 2 | 0 | 74 |
| `restplass.no` | 76 | 2 | 0 | 74 |
| `caseyjhand.com` | 74 | 74 | 0 | 0 |
| `socialloop.ai` | 74 | 74 | 0 | 0 |
| `dayze.com` | 65 | 65 | 0 | 0 |
| `daedalmap.com` | 54 | 54 | 0 | 0 |
| 2700 other operators | 7105 | 6707 | 379 | 19 |
