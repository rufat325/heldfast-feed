# MCP server tool changes

Last change observed 2026-10-08T13:55:55+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10128 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 21701 hosted endpoints (read daily, and every four hours while they keep changing).

25158 changes to a tool definition: 870 npm releases (624 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 24288 readings of hosted servers that found their tools changed; 353 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-08 | `remote/dev.zhiyong/knowledge-graph` | 2026-09-27T070033816806 -> 2026-10-08T135555884727 | 11 changed, 3 added (every tool) | quiet |
| 2026-10-08 | `remote/ai.yentaknows/directory` | 2026-09-23T163153667470 -> 2026-10-08T135555224261 | 11 changed, 5 added, 10 removed (every tool) | quiet |
| 2026-10-08 | `remote/info.yank/yank` | 2026-09-29T210511144122 -> 2026-10-08T135553399426 | 2 added | quiet |
| 2026-10-08 | `remote/io.github.cirralink-stack/kevaremesh` | 2026-09-23T161044138084 -> 2026-10-08T135553207682 | 1 changed | quiet |
| 2026-10-08 | `remote/world.agentindex/x402` | 2026-10-05T061632540754 -> 2026-10-08T135552481414 | 1 changed | quiet |
| 2026-10-08 | `remote/io.github.eamwhite1/xrpl-referee` | 2026-09-27T070532236835 -> 2026-10-08T135551123754 | 35 changed, 1 added | quiet |
| 2026-10-08 | `remote/org.ventureatlas/venture-atlas` | 2026-10-01T134255520226 -> 2026-10-08T135548186011 | 2 changed | quiet |
| 2026-10-08 | `remote/com.veterans-rights/bva-corpus` | 2026-09-23T163149068552 -> 2026-10-08T135548621588 | 2 changed | quiet |
| 2026-10-08 | `remote/sh.stipple/stipple-tenders` | 2026-10-05T172651772290 -> 2026-10-08T135545646474 | 5 changed (every tool) | quiet |
| 2026-10-08 | `remote/no.restplass/travel-search` | 2026-10-08T064236112715 -> 2026-10-08T135539163965 | 1 changed | quiet |
| 2026-10-08 | `remote/io.github.openaccountants/openaccountants` | 2026-10-04T055114706272 -> 2026-10-08T135536472557 | 3 changed | quiet |
| 2026-10-08 | `remote/io.github.fathyshalaby/specky` | 2026-09-23T161037824240 -> 2026-10-08T135536915927 | 1 changed | quiet |
| 2026-10-08 | `remote/se.sistaminuten/travel-search` | 2026-10-08T064248251311 -> 2026-10-08T135536052149 | 1 changed | quiet |
| 2026-10-08 | `remote/com.theprotoclinical/commerce` | 2026-10-01T134642572985 -> 2026-10-08T135528072987 | 3 changed | quiet |
| 2026-10-08 | `remote/com.instilus/gpsr` | 2026-09-24T120439286818 -> 2026-10-08T135528709227 | 7 added | quiet |
| 2026-10-08 | `remote/com.memoryplugin/memory` | 2026-09-23T161029922392 -> 2026-10-08T135527308307 | 5 changed | quiet |
| 2026-10-08 | `remote/com.stackerscan/stackerscan` | 2026-09-23T162956734640 -> 2026-10-08T135528673807 | 1 changed | quiet |
| 2026-10-08 | `remote/coach.marian/mentoring-inquiry-builder` | 2026-10-06T110200722133 -> 2026-10-08T135527776217 | 1 changed | quiet |
| 2026-10-08 | `remote/com.klarefi/mcp` | 2026-09-23T161028280317 -> 2026-10-08T135524650124 | 1 changed, 1 added | quiet |
| 2026-10-08 | `remote/fr.projet-ariane/ariane-orientation` | 2026-09-23T162951036069 -> 2026-10-08T135522732198 | 1 changed | quiet |
| 2026-10-08 | `remote/dev.primitive/email` | 2026-10-01T134634223894 -> 2026-10-08T135522664784 | 1 changed | quiet |
| 2026-10-08 | `remote/de.drgsystem/medical-catalogs` | 2026-09-29T073458569001 -> 2026-10-08T135521703564 | 5 added | quiet |
| 2026-10-08 | `remote/dev.marksiazon/profile` | 2026-09-23T162948081919 -> 2026-10-08T135518219933 | 6 changed (every tool) | quiet |
| 2026-10-08 | `remote/io.github.tjcgraham-rgb/gaip-broker` | 2026-10-04T195017464278 -> 2026-10-08T135522499659 | 1 added | quiet |
| 2026-10-08 | `remote/com.followontours/cricket-travel` | 2026-10-01T134424190713 -> 2026-10-08T135515710975 | 2 changed | quiet |
| 2026-10-08 | `remote/com.cintrasupply/cintra-quote` | 2026-10-01T134231126463 -> 2026-10-08T135515370702 | 3 changed | quiet |
| 2026-10-08 | `remote/domains.cheapest/cheapest-domains` | 2026-10-06T110304145141 -> 2026-10-08T135515730210 | 2 changed, 1 added | quiet |
| 2026-10-08 | `remote/com.immersivecommons/floor10` | 2026-10-05T172751883007 -> 2026-10-08T135514280801 | 1 changed | quiet |
| 2026-10-08 | `remote/com.ikeytz/website` | 2026-10-04T055049664899 -> 2026-10-08T135516013721 | 47 changed (every tool) | quiet |
| 2026-10-08 | `remote/io.github.oaleviola/arroway` | 2026-10-07T154947552234 -> 2026-10-08T135511384818 | 1 changed | quiet |
| 2026-10-08 | `remote/com.hemmabo/hemmabo-mcp-server` | 2026-10-03T192917733985 -> 2026-10-08T135510630575 | 2 changed | quiet |
| 2026-10-08 | `remote/com.contrie/contrie` | 2026-10-02T072230665802 -> 2026-10-08T135509896669 | 1 changed | quiet |
| 2026-10-08 | `remote/dk.afbudsrejser/travel-search` | 2026-10-08T064233062435 -> 2026-10-08T135509970340 | 1 changed | quiet |
| 2026-10-08 | `remote/com.uniaffitti.www/room-finder` | 2026-09-23T160856383638 -> 2026-10-08T135511025166 | 21 changed (every tool) | quiet |
| 2026-10-08 | `remote/com.blitzreels/blitzreels` | 2026-09-30T060139872226 -> 2026-10-08T135511450643 | 2 changed, 5 added | quiet |
| 2026-10-08 | `remote/io.github.SoapyRED/freightutils` | 2026-10-08T064247231353 -> 2026-10-08T135506231592 | 23 changed | quiet |
| 2026-10-08 | `remote/sh.stipple/openwarrant` | 2026-10-05T172648854387 -> 2026-10-08T135505006621 | 5 changed | quiet |
| 2026-10-08 | `remote/com.emorahealth/mental-health-care` | 2026-09-23T162940174562 -> 2026-10-08T135503097027 | 2 changed, 6 added, 8 removed (every tool) | quiet |
| 2026-10-08 | `remote/tennis.courts/nyc-tennis-courts` | 2026-10-05T172744668976 -> 2026-10-08T135459881812 | 3 changed | quiet |
| 2026-10-08 | `remote/io.github.mkibrick/compshop` | 2026-09-23T162936532411 -> 2026-10-08T135458775308 | 7 changed (every tool) | quiet |
| 2026-10-08 | `remote/io.github.falsalama/proper-job` | 2026-10-01T134406686747 -> 2026-10-08T135457963773 | 3 changed, 1 added (every tool) | quiet |
| 2026-10-08 | `remote/com.wikexa/knowledge` | 2026-09-23T161016464912 -> 2026-10-08T135459057919 | 1 changed | quiet |
| 2026-10-08 | `remote/com.halffee/coinrebate` | 2026-09-23T162937186125 -> 2026-10-08T135500220710 | 6 changed, 1 added, 1 removed | quiet |
| 2026-10-08 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-08T064244203005 -> 2026-10-08T135500673636 | 3 changed, 3 added | quiet |
| 2026-10-08 | `remote/ar.com.consignatarias/cattle-market` | 2026-10-04T055037685841 -> 2026-10-08T135459081873 | 28 added, 24 removed | quiet |
| 2026-10-08 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-10-08T064245232896 -> 2026-10-08T135458536813 | 3 changed | quiet |
| 2026-10-08 | `remote/io.github.HuangGoodmanAgency/edgar-and-edgarette` | 2026-10-01T134405900629 -> 2026-10-08T135457031542 | 4 added | review |
| 2026-10-08 | `remote/io.github.VoiceScapee/voicescape` | 2026-10-08T064230746307 -> 2026-10-08T135454873573 | 1 changed, 1 added | quiet |
| 2026-10-08 | `remote/fi.akkilahdot/travel-search` | 2026-10-08T064244429403 -> 2026-10-08T135454454766 | 1 changed | quiet |
| 2026-10-08 | `remote/io.github.worklore/worklore` | 2026-09-30T210256364576 -> 2026-10-08T135451039369 | 2 changed, 1 added | quiet |
| 2026-10-08 | `remote/com.underpricedai/underpriced-ai` | 2026-09-29T150758942825 -> 2026-10-08T135443169463 | 1 changed | quiet |
| 2026-10-08 | `remote/com.warmthengine/observatory` | 2026-09-23T162926464855 -> 2026-10-08T135443219417 | 18 changed (every tool) | quiet |
| 2026-10-08 | `remote/com.voyscout/price-history` | 2026-09-28T073155103971 -> 2026-10-08T135442020560 | 5 changed (every tool) | quiet |
| 2026-10-08 | `remote/tech.viewprinter/viewprinter` | 2026-10-03T054747906608 -> 2026-10-08T135437747503 | 4 changed | quiet |
| 2026-10-08 | `remote/com.viatsy/mcp` | 2026-09-23T162924269909 -> 2026-10-08T135439046346 | 1 changed | quiet |
| 2026-10-08 | `remote/com.trustbaselab/rcb-data` | 2026-10-08T064230654245 -> 2026-10-08T135438644070 | 2 added | quiet |
| 2026-10-08 | `remote/ai.verticalmarketplace/vertical-marketplace` | 2026-10-04T055020489609 -> 2026-10-08T135436639363 | 1 changed, 8 added | quiet |
| 2026-10-08 | `remote/ru.vedarai/mcp` | 2026-10-03T135718511041 -> 2026-10-08T135436798063 | 6 changed, 1 added | quiet |
| 2026-10-08 | `remote/io.github.sharan01x/usetested` | 2026-10-02T130105345889 -> 2026-10-08T135434290106 | 1 changed | quiet |
| 2026-10-08 | `remote/io.tooloracle/macroooracle` | 2026-09-23T163049430820 -> 2026-10-08T135433561551 | 2 removed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 16850 substantive, 7961 that changed only numbers (a catalogue counter ticking, a date), 347 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 13231 | 5706 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 538 | 538 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `sistaminuten.se` | 84 | 2 | 0 | 82 |
| `afbudsrejser.dk` | 83 | 2 | 0 | 81 |
| `akkilahdot.fi` | 83 | 2 | 0 | 81 |
| `restplass.no` | 83 | 2 | 0 | 81 |
| `socialloop.ai` | 81 | 81 | 0 | 0 |
| `caseyjhand.com` | 77 | 77 | 0 | 0 |
| `dayze.com` | 67 | 67 | 0 | 0 |
| `remoshift.com` | 59 | 2 | 57 | 0 |
| 3037 other operators | 8334 | 7933 | 379 | 22 |
