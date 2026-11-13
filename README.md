# MCP server tool changes

Last change observed 2026-11-13T15:08:24+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

97965 changes to a tool definition: 4084 npm releases (3838 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 93881 readings of hosted servers that found their tools changed; 4023 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-13 | `remote/no.restplass/travel-search` | 2026-11-13T124212585844 -> 2026-11-13T150825413296 | 1 changed | quiet |
| 2026-11-13 | `remote/io.deeplead/deeplead` | 2026-11-11T230926384187 -> 2026-11-13T150753290874 | 12 changed, 1 added | quiet |
| 2026-11-13 | `remote/dk.afbudsrejser/travel-search` | 2026-11-13T124208785382 -> 2026-11-13T150738027062 | 1 changed | quiet |
| 2026-11-13 | `remote/com.yangopen/mcp` | 2026-11-12T155119240663 -> 2026-11-13T150716441936 | 1 changed, 14 added | quiet |
| 2026-11-13 | `remote/io.taifoon/coordination-layer.1` | 2026-11-13T124216301396 -> 2026-11-13T150651741361 | 1 changed | review |
| 2026-11-13 | `remote/se.sistaminuten/travel-search` | 2026-11-13T124210647185 -> 2026-11-13T150647827144 | 1 changed | quiet |
| 2026-11-13 | `remote/com.prenotomenu/menu` | 2026-10-26T211524599545 -> 2026-11-13T150637381460 | 2 added | quiet |
| 2026-11-13 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-13T115940466143 -> 2026-11-13T150615407353 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.Tomalarrrr/cyclesite-mcp-server` | 2026-11-05T222219197532 -> 2026-11-13T150611099870 | 1 changed | quiet |
| 2026-11-13 | `remote/com.theoutcomelayer/outcome-layer` | 2026-10-26T133613587483 -> 2026-11-13T150607938710 | 1 changed, 1 added | quiet |
| 2026-11-13 | `remote/com.cookiefreeanalytics/mcp` | 2026-11-11T145943204686 -> 2026-11-13T150607667685 | 1 changed | quiet |
| 2026-11-13 | `remote/sg.cashew/mcp` | 2026-11-12T155005674627 -> 2026-11-13T150606996409 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.gimarcus/signal` | 2026-11-09T170106074856 -> 2026-11-13T150521120615 | 1 changed | quiet |
| 2026-11-13 | `remote/at.space-core/game` | 2026-11-04T150347957024 -> 2026-11-13T150513842054 | 1 changed, 1 added | quiet |
| 2026-11-13 | `remote/ai.sosumi/sosumi` | 2026-11-09T170055682121 -> 2026-11-13T150510095084 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.tim777z/utopia-megastore` | 2026-11-09T170019211188 -> 2026-11-13T150506727858 | 1 changed, 1 added | quiet |
| 2026-11-13 | `remote/com.usetested/reviews` | 2026-10-30T132755753815 -> 2026-11-13T150503712695 | 1 changed | review |
| 2026-11-13 | `remote/app.openkrill/buyersignals` | 2026-11-05T010638199814 -> 2026-11-13T150453368120 | 1 changed | quiet |
| 2026-11-13 | `remote/app.openkrill/transcript-kit` | 2026-11-04T150531175452 -> 2026-11-13T150451376232 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.cyanheads/secedgar-mcp-server` | 2026-11-09T170021546756 -> 2026-11-13T150433062837 | 10 changed | quiet |
| 2026-11-13 | `remote/com.tallybuy/tallybuy` | 2026-11-07T133259604950 -> 2026-11-13T150413330965 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.MsingathiM/swapeazi` | 2026-11-13T115736837921 -> 2026-11-13T150355348265 | 1 added | quiet |
| 2026-11-13 | `remote/com.printags/shop` | 2026-11-13T115730295448 -> 2026-11-13T150349184478 | 7 changed (every tool) | quiet |
| 2026-11-13 | `remote/app.openkrill/recalls` | 2026-10-17T060203882108 -> 2026-11-13T150347180228 | 3 changed | quiet |
| 2026-11-13 | `remote/app.sallim/korea-realty` | 2026-11-13T115601998144 -> 2026-11-13T150347483878 | 1 changed | quiet |
| 2026-11-13 | `remote/app.openkrill/shop-duty` | 2026-11-04T150330389193 -> 2026-11-13T150317805217 | 2 changed | quiet |
| 2026-11-13 | `remote/com.plainquant/plainquant` | 2026-11-12T154540095671 -> 2026-11-13T150309711276 | 2 changed | quiet |
| 2026-11-13 | `remote/app.lovable.peppol-invoice-compass/invoiceverify` | 2026-11-02T163111170625 -> 2026-11-13T150302346706 | 1 added | quiet |
| 2026-11-13 | `remote/studio.gradients/mcp` | 2026-11-13T120605996984 -> 2026-11-13T150229436175 | 1 changed | quiet |
| 2026-11-13 | `remote/wiki.radix/radix-wiki` | 2026-11-10T152809345527 -> 2026-11-13T150222450217 | 18 changed (every tool) | quiet |
| 2026-11-13 | `remote/ar.com.consignatarias/cattle-market` | 2026-11-05T115522308093 -> 2026-11-13T150219040630 | 1 changed | quiet |
| 2026-11-13 | `remote/com.radveo/radveo` | 2026-09-23T160911068175 -> 2026-11-13T150218102988 | 2 changed (every tool) | quiet |
| 2026-11-13 | `remote/fi.akkilahdot/travel-search` | 2026-11-13T124207518504 -> 2026-11-13T150212357069 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.Perufitlife/postwire-mcp` | 2026-11-05T115023958406 -> 2026-11-13T150157939601 | 9 changed | quiet |
| 2026-11-13 | `remote/io.github.AdrianStauffer/copilot-studio-friction-index` | 2026-09-23T160854122704 -> 2026-11-13T150127537978 | 7 changed (every tool) | quiet |
| 2026-11-13 | `remote/com.othermindset/campus` | 2026-11-01T135042855972 -> 2026-11-13T150116642904 | 1 changed, 1 added | quiet |
| 2026-11-13 | `remote/nl.opahaardhout/opahaardhout` | 2026-11-13T115447344357 -> 2026-11-13T150109730975 | 1 changed | quiet |
| 2026-11-13 | `remote/ca.ohey/research` | 2026-11-09T165547237653 -> 2026-11-13T150108574963 | 1 changed | quiet |
| 2026-11-13 | `remote/com.thrustlab/thrustlab` | 2026-10-06T110302343667 -> 2026-11-13T150107534241 | 3 changed | quiet |
| 2026-11-13 | `remote/com.sigoseguros/auto-quote` | 2026-10-27T111945503524 -> 2026-11-13T150052304462 | 2 changed | quiet |
| 2026-11-13 | `remote/io.github.Kromatic-Innovation/neumann` | 2026-11-12T154334067074 -> 2026-11-13T150051318371 | 11 changed, 6 added (every tool) | review |
| 2026-11-13 | `remote/ai.signal8/mcp` | 2026-11-13T115340444833 -> 2026-11-13T150053148698 | 2 changed | quiet |
| 2026-11-13 | `remote/com.tamingdns/mcp` | 2026-11-13T120345422205 -> 2026-11-13T150050045761 | 19 changed (every tool) | quiet |
| 2026-11-13 | `remote/com.swellcabin/surf` | 2026-11-13T120339131812 -> 2026-11-13T150045442625 | 2 changed | quiet |
| 2026-11-13 | `remote/com.nearfine/books` | 2026-11-09T165653012087 -> 2026-11-13T150041865894 | 1 changed | quiet |
| 2026-11-13 | `remote/me.miow/miow` | 2026-11-13T115402274134 -> 2026-11-13T150024648242 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-13T124154281958 -> 2026-11-13T150022015818 | 1 changed | quiet |
| 2026-11-13 | `remote/net.pendingdelete/mcp` | 2026-11-13T115318073039 -> 2026-11-13T150020627145 | 1 changed | quiet |
| 2026-11-13 | `remote/eu.paymentslaw/legislation` | 2026-11-11T145203389709 -> 2026-11-13T150020845313 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.QDThead/signal-lab` | 2026-11-11T230902180048 -> 2026-11-13T150010081506 | 1 changed | quiet |
| 2026-11-13 | `remote/com.seqbench/workbench` | 2026-11-13T120231250645 -> 2026-11-13T145958279604 | 3 changed | quiet |
| 2026-11-13 | `remote/app.seoaeogeo/seo-aeo-geo` | 2026-11-12T154912605705 -> 2026-11-13T145957034118 | 1 changed | quiet |
| 2026-11-13 | `remote/org.worldgdp/nowcasts` | 2026-11-07T132920219757 -> 2026-11-13T145953840811 | 1 changed | quiet |
| 2026-11-13 | `remote/com.searchfragments/search-fragments` | 2026-11-08T204934127485 -> 2026-11-13T145952199635 | 1 changed, 1 added | quiet |
| 2026-11-13 | `remote/co.lovie/company-formation` | 2026-11-13T124124050626 -> 2026-11-13T145949309316 | 1 changed | quiet |
| 2026-11-13 | `remote/com.remoshift/jobs` | 2026-11-13T124144811794 -> 2026-11-13T145930891465 | 1 changed | quiet |
| 2026-11-13 | `remote/com.stackenhance/signal` | 2026-11-09T165349100673 -> 2026-11-13T145921247296 | 1 changed | quiet |
| 2026-11-13 | `remote/com.spaghettiandsummits/outdoors` | 2026-11-12T154205857712 -> 2026-11-13T145917171742 | 4 changed (every tool) | quiet |
| 2026-11-13 | `remote/com.getmattered/getmattered` | 2026-11-13T115227342856 -> 2026-11-13T145912006265 | 3 changed, 1 added | quiet |
| 2026-11-13 | `remote/app.screenbird/screenbird` | 2026-11-02T163100753996 -> 2026-11-13T145907838042 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 60001 substantive, 36973 that changed only numbers (a catalogue counter ticking, a date), 991 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 52526 | 17762 | 34764 | 0 |
| `a2awire.com` | 2375 | 2375 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 403 | 403 | 0 | 0 |
| `civai.co` | 317 | 317 | 0 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `revmesh2074.workers.dev` | 239 | 209 | 30 | 0 |
| `sistaminuten.se` | 231 | 6 | 0 | 225 |
| `afbudsrejser.dk` | 230 | 6 | 0 | 224 |
| `akkilahdot.fi` | 230 | 6 | 0 | 224 |
| `restplass.no` | 230 | 6 | 0 | 224 |
| `socialloop.ai` | 222 | 222 | 0 | 0 |
| 9265 other operators | 38363 | 36090 | 2179 | 94 |
