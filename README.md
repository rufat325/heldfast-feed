# MCP server tool changes

Last change observed 2026-10-27T11:26:04+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

55387 changes to a tool definition: 2382 npm releases (2136 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 53005 readings of hosted servers that found their tools changed; 2822 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-27 | `remote/in.xavio/storefront` | 2026-09-23T202601663750 -> 2026-10-27T112607256810 | 3 changed | quiet |
| 2026-10-27 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-10-27T054123813986 -> 2026-10-27T112605063614 | 1 added | review |
| 2026-10-27 | `remote/io.vascue/public-knowledge-search` | 2026-09-23T163149928851 -> 2026-10-27T112600044966 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.roomza-inc/roomza` | 2026-09-23T163142159504 -> 2026-10-27T112548421524 | 3 changed | quiet |
| 2026-10-27 | `remote/no.restplass/travel-search` | 2026-10-27T054123902346 -> 2026-10-27T112547687999 | 1 changed | quiet |
| 2026-10-27 | `remote/com.meridiandispatch/travel-guides` | 2026-10-25T225152317350 -> 2026-10-27T112539053316 | 1 changed | quiet |
| 2026-10-27 | `remote/cool.footage/mcp-server` | 2026-09-23T163134224112 -> 2026-10-27T112526655064 | 7 added | review |
| 2026-10-27 | `remote/io.deeplead/deeplead` | 2026-10-17T060430762269 -> 2026-10-27T112518891832 | 1 changed, 2 added | review |
| 2026-10-27 | `remote/dk.afbudsrejser/travel-search` | 2026-10-27T054119602293 -> 2026-10-27T112506252550 | 1 changed | quiet |
| 2026-10-27 | `remote/com.accentvoice/site` | 2026-10-17T060419740938 -> 2026-10-27T112504907213 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.xzntexe/yruz-x402` | 2026-10-26T133750063265 -> 2026-10-27T112456725369 | 26 added | review |
| 2026-10-27 | `remote/ai.wem3/wem-price-compare` | 2026-10-18T113335433443 -> 2026-10-27T112456191574 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.michalbaturko-lang/voiceflip` | 2026-09-23T160857077247 -> 2026-10-27T112446720609 | 3 changed, 1 added | quiet |
| 2026-10-27 | `remote/com.techfabric/techfabric` | 2026-10-27T054132097760 -> 2026-10-27T112443457790 | 10 changed | quiet |
| 2026-10-27 | `remote/com.resollo/agent-api` | 2026-10-17T060409162748 -> 2026-10-27T112434337692 | 12 changed | quiet |
| 2026-10-27 | `remote/ru.tutvidnee/portal` | 2026-10-08T135442823085 -> 2026-10-27T112430175588 | 2 changed | quiet |
| 2026-10-27 | `remote/io.github.Hoya25/nctr-mcp-server` | 2026-09-23T161043361225 -> 2026-10-27T112425509382 | 4 changed | quiet |
| 2026-10-27 | `remote/io.github.joverman/xrplink` | 2026-10-26T211534712303 -> 2026-10-27T112424819173 | 3 changed, 1 removed | quiet |
| 2026-10-27 | `remote/io.github.Humanleap/magicscreenshots-mcp` | 2026-09-28T142352735539 -> 2026-10-27T112422846414 | 1 changed | quiet |
| 2026-10-27 | `remote/net.qsig.x402/mcp` | 2026-09-29T073422118461 -> 2026-10-27T112421049806 | 1 changed, 2 added | quiet |
| 2026-10-27 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-10-27T054107231391 -> 2026-10-27T112417817131 | 1 added | review |
| 2026-10-27 | `remote/io.github.tidytools/tidytools-free` | 2026-10-22T052607494071 -> 2026-10-27T112412897844 | 6 changed | quiet |
| 2026-10-27 | `remote/com.roasexpert.tools/seo-audit` | 2026-10-27T054101556740 -> 2026-10-27T112413458435 | 3 changed, 1 added | quiet |
| 2026-10-27 | `remote/io.taifoon/coordination-layer.1` | 2026-10-27T054105699080 -> 2026-10-27T112409240998 | 1 changed | review |
| 2026-10-27 | `remote/com.swiftprobate/probate` | 2026-10-17T055625791762 -> 2026-10-27T112408349619 | 2 changed | quiet |
| 2026-10-27 | `remote/se.sistaminuten/travel-search` | 2026-10-27T054105858936 -> 2026-10-27T112404880243 | 1 changed | quiet |
| 2026-10-27 | `remote/com.tickerz/tickerz` | 2026-10-09T064812402543 -> 2026-10-27T112402079583 | 1 changed | quiet |
| 2026-10-27 | `remote/net.rafsoft/faktura-vat` | 2026-09-23T161034608351 -> 2026-10-27T112402670470 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.jonatanvazquez/propfacil` | 2026-09-23T161033064802 -> 2026-10-27T112400608414 | 1 changed | quiet |
| 2026-10-27 | `remote/de.overfit/overfit` | 2026-10-22T110010559344 -> 2026-10-27T112400260161 | 5 changed | quiet |
| 2026-10-27 | `remote/com.oxfordledge/oxford-ledge` | 2026-10-19T135506696864 -> 2026-10-27T112356665837 | 1 changed | quiet |
| 2026-10-27 | `remote/io.kolmo.www/kolmo-mcp-server` | 2026-10-23T120928227431 -> 2026-10-27T112348621966 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-10-23T120928574658 -> 2026-10-27T112348281796 | 8 changed | quiet |
| 2026-10-27 | `remote/uk.co.gigstamp/gigstamp` | 2026-10-17T055605552395 -> 2026-10-27T112345575514 | 3 changed | quiet |
| 2026-10-27 | `remote/com.followontours/cricket-travel` | 2026-10-26T133851031437 -> 2026-10-27T112342562636 | 2 changed | quiet |
| 2026-10-27 | `remote/it.expatliving/data` | 2026-10-22T052602621891 -> 2026-10-27T112340362804 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.GriffMurder/taskbullet-site` | 2026-10-21T052443716993 -> 2026-10-27T112339840002 | 1 changed | review |
| 2026-10-27 | `remote/com.blitzreels/blitzreels` | 2026-10-24T112909031104 -> 2026-10-27T112333505639 | 6 changed | quiet |
| 2026-10-27 | `remote/fr.synergieloc/immobilier` | 2026-10-27T054057322013 -> 2026-10-27T112333597358 | 8 added | quiet |
| 2026-10-27 | `remote/io.github.vassiliylakhonin/vizier` | 2026-10-17T060308767689 -> 2026-10-27T112328680521 | 1 changed | quiet |
| 2026-10-27 | `remote/com.vibe-manufacturing/manufacturer-finder` | 2026-10-17T060305583126 -> 2026-10-27T112324468980 | 3 added | quiet |
| 2026-10-27 | `remote/io.github.creator35lwb-web/verifimind-genesis` | 2026-09-24T202810493236 -> 2026-10-27T112321833074 | 4 changed | quiet |
| 2026-10-27 | `remote/io.strategyarena/strategyarena` | 2026-10-19T135654396467 -> 2026-10-27T112322741606 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.brawlaphant/vealth` | 2026-10-22T202106469018 -> 2026-10-27T112319325037 | 8 removed | quiet |
| 2026-10-27 | `remote/dev.upfork/upfork` | 2026-10-27T054123575752 -> 2026-10-27T112312714545 | 2 changed, 3 added | quiet |
| 2026-10-27 | `remote/ai.spoe/spoe` | 2026-10-20T232801267882 -> 2026-10-27T112311659191 | 6 added | quiet |
| 2026-10-27 | `remote/com.zinvyl/marketplace` | 2026-10-27T054130238280 -> 2026-10-27T112308756473 | 8 changed | quiet |
| 2026-10-27 | `remote/io.github.Timothymycompc/solana-pulse-gateway` | 2026-10-22T233928155214 -> 2026-10-27T112305169237 | 1 changed, 1 added | quiet |
| 2026-10-27 | `remote/io.github.yappmaniac/grocery-price-snapshots` | 2026-10-26T133618415295 -> 2026-10-27T112301281755 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.snenenenenenene/transita-mcp-server` | 2026-10-17T060249479886 -> 2026-10-27T112300111736 | 6 changed, 5 added (every tool) | quiet |
| 2026-10-27 | `remote/online.waply/public` | 2026-10-19T135417163599 -> 2026-10-27T112256772423 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.alwaysarafath/thepaymentsnotes-ledger` | 2026-10-17T060246680058 -> 2026-10-27T112256421995 | 1 added | quiet |
| 2026-10-27 | `remote/com.selisesignature/signature` | 2026-10-18T113219471114 -> 2026-10-27T112256817966 | 4 changed (every tool) | quiet |
| 2026-10-27 | `remote/com.testerexchange/tester-exchange` | 2026-10-26T133810090709 -> 2026-10-27T112253788019 | 1 added, 6 removed | quiet |
| 2026-10-27 | `remote/io.github.voicehook-ai/voicehook` | 2026-10-23T120839238722 -> 2026-10-27T112252598583 | 2 changed | quiet |
| 2026-10-27 | `remote/org.verifiedhandles/verified-handles` | 2026-10-19T135405957496 -> 2026-10-27T112247411295 | 3 changed | quiet |
| 2026-10-27 | `remote/app.seatsherpa/rides` | 2026-10-26T133453181166 -> 2026-10-27T112242283426 | 3 changed | quiet |
| 2026-10-27 | `remote/com.lowerscript/prices` | 2026-10-17T055945098680 -> 2026-10-27T112240548619 | 1 changed | quiet |
| 2026-10-27 | `remote/br.com.scrypta/scrypta-mcp-server` | 2026-10-19T135614648564 -> 2026-10-27T112240031665 | 1 added | quiet |
| 2026-10-27 | `remote/io.geonode/scraper` | 2026-10-26T133450469017 -> 2026-10-27T112240884602 | 15 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 35288 substantive, 19426 that changed only numbers (a catalogue counter ticking, a date), 673 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 30394 | 12161 | 18233 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 891 | 891 | 0 | 0 |
| `caseyjhand.com` | 238 | 238 | 0 | 0 |
| `sistaminuten.se` | 159 | 4 | 0 | 155 |
| `afbudsrejser.dk` | 158 | 4 | 0 | 154 |
| `akkilahdot.fi` | 158 | 4 | 0 | 154 |
| `restplass.no` | 158 | 4 | 0 | 154 |
| `socialloop.ai` | 153 | 153 | 0 | 0 |
| `revmesh2074.workers.dev` | 129 | 116 | 13 | 0 |
| `remoshift.com` | 128 | 8 | 120 | 0 |
| `fundinglandscape.com` | 122 | 78 | 44 | 0 |
| 6059 other operators | 20358 | 19286 | 1016 | 56 |
