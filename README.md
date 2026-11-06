# MCP server tool changes

Last change observed 2026-11-06T07:28:27+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

78646 changes to a tool definition: 3319 npm releases (3073 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 75327 readings of hosted servers that found their tools changed; 3463 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-06 | `remote/studio.gradients/mcp` | 2026-11-05T222227755362 -> 2026-11-06T072830405225 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.SoapyRED/freightutils` | 2026-11-05T222228098181 -> 2026-11-06T072833318842 | 26 changed (every tool) | quiet |
| 2026-11-06 | `remote/fi.akkilahdot/travel-search` | 2026-11-05T222224219288 -> 2026-11-06T072827567964 | 1 changed | quiet |
| 2026-11-06 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-05T222223252900 -> 2026-11-06T072827377142 | 2 changed | quiet |
| 2026-11-06 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-05T010657183434 -> 2026-11-06T072825318889 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-05T222223661351 -> 2026-11-06T072825763836 | 1 changed, 16 added | review |
| 2026-11-06 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-05T222222603533 -> 2026-11-06T072827045551 | 3 changed | quiet |
| 2026-11-06 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-05T222219226197 -> 2026-11-06T072825474773 | 4 changed, 3 added | quiet |
| 2026-11-06 | `remote/xyz.t0ll/toll` | 2026-11-05T222216206801 -> 2026-11-06T072820862514 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-05T222219348868 -> 2026-11-06T072822075491 | 7 changed, 2 added (every tool) | quiet |
| 2026-11-06 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-05T222213439126 -> 2026-11-06T072819374603 | 3 changed | quiet |
| 2026-11-06 | `remote/com.signupbouncer/checker` | 2026-11-04T200750692215 -> 2026-11-06T072818156656 | 2 changed | quiet |
| 2026-11-06 | `remote/io.sibidz/sibidz` | 2026-11-04T200751585098 -> 2026-11-06T072818586314 | 1 changed | quiet |
| 2026-11-06 | `remote/ai.shorti/shorti` | 2026-11-04T123758708353 -> 2026-11-06T072818287773 | 1 changed | quiet |
| 2026-11-06 | `remote/ai.searchshop/apostleman` | 2026-11-04T150209970936 -> 2026-11-06T072816624979 | 1 changed | quiet |
| 2026-11-06 | `remote/com.rightshold/rightshold` | 2026-11-05T115456109987 -> 2026-11-06T072813830751 | 1 added, 1 removed | quiet |
| 2026-11-06 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-05T124826962793 -> 2026-11-06T072814935765 | 2 changed | quiet |
| 2026-11-06 | `remote/io.github.Veniwol-Li-Lambd/lilambd-data` | 2026-11-05T222302487483 -> 2026-11-06T072816017381 | 1 added | review |
| 2026-11-06 | `remote/io.github.moelayyan90/xguard` | 2026-11-04T151023212182 -> 2026-11-06T072811623045 | 1 added | review |
| 2026-11-06 | `remote/io.github.liad142/yedapo` | 2026-11-05T010649840266 -> 2026-11-06T072811529827 | 2 changed (every tool) | quiet |
| 2026-11-06 | `remote/no.restplass/travel-search` | 2026-11-05T222252489127 -> 2026-11-06T072810698706 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.ceedot-rock/slid-phi-labs` | 2026-11-05T222251532332 -> 2026-11-06T072810550465 | 2 changed | quiet |
| 2026-11-06 | `remote/com.sapiensinteticos/sapiens` | 2026-11-05T222251989789 -> 2026-11-06T072810875652 | 1 changed | quiet |
| 2026-11-06 | `remote/com.multicinesortega/cartelera` | 2026-11-05T222204001170 -> 2026-11-06T072812060438 | 1 changed | quiet |
| 2026-11-06 | `remote/com.googleapis.monitoring/mcp` | 2026-11-05T222201394757 -> 2026-11-06T072809565823 | 5 changed | quiet |
| 2026-11-06 | `remote/io.github.bowenerchen/cipherhub` | 2026-11-05T124827002284 -> 2026-11-06T072813258806 | 1 changed | quiet |
| 2026-11-06 | `remote/se.sistaminuten/travel-search` | 2026-11-05T222221218331 -> 2026-11-06T072808364828 | 1 changed | quiet |
| 2026-11-06 | `remote/io.stockmap/stockmap` | 2026-11-05T222202643965 -> 2026-11-06T072807210461 | 1 added | review |
| 2026-11-06 | `remote/dk.afbudsrejser/travel-search` | 2026-11-05T222245520541 -> 2026-11-06T072807872972 | 1 changed | quiet |
| 2026-11-06 | `remote/com.structomat/steel` | 2026-11-04T200749621382 -> 2026-11-06T072807537028 | 1 added | quiet |
| 2026-11-06 | `remote/com.stocklens/stocklens` | 2026-11-05T114955875632 -> 2026-11-06T072807340434 | 1 changed | quiet |
| 2026-11-06 | `remote/com.socialseal/mcp` | 2026-11-04T123734469088 -> 2026-11-06T072806792098 | 16 changed | quiet |
| 2026-11-06 | `remote/fyi.toothache/dentists` | 2026-11-04T123808011423 -> 2026-11-06T072805118934 | 1 changed | quiet |
| 2026-11-06 | `remote/fun.trnch/trnch` | 2026-11-05T222241946686 -> 2026-11-06T072805543589 | 8 changed | quiet |
| 2026-11-06 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-11-05T010640374388 -> 2026-11-06T072805241000 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.magichourhq/magic-hour` | 2026-11-05T114844556928 -> 2026-11-06T072803902725 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-05T222237363261 -> 2026-11-06T072804505667 | 2 changed, 1 added, 6 removed | quiet |
| 2026-11-06 | `remote/com.supercatch/supercatch` | 2026-11-05T115447567565 -> 2026-11-06T072803666154 | 5 changed, 5 added | quiet |
| 2026-11-06 | `remote/ai.whatsupin/events` | 2026-11-05T115339652531 -> 2026-11-06T072803537223 | 5 changed | quiet |
| 2026-11-06 | `remote/io.github.marcoret74/semantic-geometry` | 2026-11-05T222219542786 -> 2026-11-06T072802841344 | 1 changed | quiet |
| 2026-11-06 | `remote/de.skysolar/sky-solar` | 2026-11-05T115040015686 -> 2026-11-06T072803421785 | 2 changed | quiet |
| 2026-11-06 | `remote/com.tubesaku/creator-insights` | 2026-11-04T123820229475 -> 2026-11-06T072802350460 | 2 changed | quiet |
| 2026-11-06 | `remote/re.rundata/temps-reel` | 2026-11-05T150516372521 -> 2026-11-06T072802521306 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.industrial-platform-ai/research-brief` | 2026-11-05T114657179991 -> 2026-11-06T072800576733 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.farenberglord-star/orb-studio` | 2026-11-05T222153043850 -> 2026-11-06T072801027546 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.SKalinin909/tradingcalc` | 2026-11-05T010730085242 -> 2026-11-06T072800641310 | 4 added | review |
| 2026-11-06 | `remote/ai.bamf/bamf` | 2026-11-05T114705464866 -> 2026-11-06T072800161359 | 2 added | quiet |
| 2026-11-06 | `remote/pro.aicut/aicut` | 2026-11-05T222147854804 -> 2026-11-06T072800021230 | 1 changed | quiet |
| 2026-11-06 | `remote/fun.pumpdata/pumpdata` | 2026-11-05T115259968068 -> 2026-11-06T072758529633 | 1 changed, 5 added | quiet |
| 2026-11-06 | `remote/ai.rokha/rokha` | 2026-11-04T123757001729 -> 2026-11-06T072759827724 | 1 added, 1 removed | quiet |
| 2026-11-06 | `remote/io.github.si-imtiaz/leadquasar` | 2026-11-05T222146155881 -> 2026-11-06T072758888448 | 1 changed | quiet |
| 2026-11-06 | `remote/com.thefomite/fomite` | 2026-11-05T010728881040 -> 2026-11-06T072758843194 | 1 changed | quiet |
| 2026-11-06 | `remote/com.partstable/partstable` | 2026-11-05T115218055336 -> 2026-11-06T072757462557 | 1 changed | quiet |
| 2026-11-06 | `remote/net.hotelrefund/price-tracker` | 2026-11-05T010626309166 -> 2026-11-06T072755953089 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.lx1112/agent-data-api` | 2026-11-05T115201255640 -> 2026-11-06T072756947999 | 6 added | review |
| 2026-11-06 | `remote/app.vercel.indo-news-api/news` | 2026-11-05T222141462458 -> 2026-11-06T072756666297 | 5 changed | quiet |
| 2026-11-06 | `remote/app.inescapable/booking` | 2026-11-05T114504974009 -> 2026-11-06T072756320576 | 1 changed | quiet |
| 2026-11-06 | `remote/tax.terminal/filing` | 2026-11-05T222142562988 -> 2026-11-06T072756422778 | 1 changed | quiet |
| 2026-11-06 | `remote/fi.northpoint/marketing-compliance` | 2026-11-05T010632325771 -> 2026-11-06T072755764753 | 1 added | quiet |
| 2026-11-06 | `remote/me.freehire/freehire` | 2026-11-05T114254293179 -> 2026-11-06T072754266951 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 48628 substantive, 29162 that changed only numbers (a catalogue counter ticking, a date), 856 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 43271 | 15883 | 27388 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1485 | 1485 | 0 | 0 |
| `caseyjhand.com` | 354 | 354 | 0 | 0 |
| `sistaminuten.se` | 201 | 6 | 0 | 195 |
| `afbudsrejser.dk` | 200 | 6 | 0 | 194 |
| `akkilahdot.fi` | 200 | 6 | 0 | 194 |
| `restplass.no` | 200 | 6 | 0 | 194 |
| `socialloop.ai` | 193 | 193 | 0 | 0 |
| `remoshift.com` | 165 | 14 | 151 | 0 |
| `revmesh2074.workers.dev` | 164 | 145 | 19 | 0 |
| `fundinglandscape.com` | 153 | 93 | 60 | 0 |
| 7675 other operators | 29719 | 28096 | 1544 | 79 |
