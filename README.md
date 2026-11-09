# MCP server tool changes

Last change observed 2026-11-09T19:15:57+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

84684 changes to a tool definition: 3727 npm releases (3481 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 80957 readings of hosted servers that found their tools changed; 3659 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-09 | `remote/agency.zoll/ausfuhr` | 2026-11-09T170419458349 -> 2026-11-09T191559538338 | 1 added | quiet |
| 2026-11-09 | `remote/dev.primitive/email` | 2026-11-07T133723538416 -> 2026-11-09T191553173403 | 1 changed | quiet |
| 2026-11-09 | `remote/com.patchmcp/patch` | 2026-11-09T071638928946 -> 2026-11-09T191552340614 | 1 changed | quiet |
| 2026-11-09 | `remote/studio.gradients/mcp` | 2026-11-09T170309001559 -> 2026-11-09T191550477724 | 1 changed | quiet |
| 2026-11-09 | `remote/no.restplass/travel-search` | 2026-11-09T170414915259 -> 2026-11-09T191543143895 | 1 changed | quiet |
| 2026-11-09 | `remote/fi.akkilahdot/travel-search` | 2026-11-09T170234372124 -> 2026-11-09T191545482008 | 1 changed | quiet |
| 2026-11-09 | `remote/com.sapiensinteticos/sapiens` | 2026-11-08T064603534011 -> 2026-11-09T191543781528 | 1 changed | quiet |
| 2026-11-09 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-09T071633833394 -> 2026-11-09T191542428534 | 8 added | review |
| 2026-11-09 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-09T170200858596 -> 2026-11-09T191539678508 | 2 changed | quiet |
| 2026-11-09 | `remote/domains.cheapest/cheapest-domains` | 2026-11-08T135651301858 -> 2026-11-09T191538612614 | 6 changed | quiet |
| 2026-11-09 | `remote/gg.unicum/wot-stats` | 2026-11-09T170148812260 -> 2026-11-09T191536890645 | 1 changed | quiet |
| 2026-11-09 | `remote/dk.afbudsrejser/travel-search` | 2026-11-09T170323626467 -> 2026-11-09T191535142866 | 1 changed | quiet |
| 2026-11-09 | `remote/app.wieldr/radar` | 2026-11-09T170312543437 -> 2026-11-09T191533963009 | 1 changed, 1 added | quiet |
| 2026-11-09 | `remote/ai.peerfoundry/typedpull` | 2026-11-09T170138878539 -> 2026-11-09T191532748324 | 2 changed, 1 added | quiet |
| 2026-11-09 | `remote/com.veritaset/mcp` | 2026-11-08T204943698338 -> 2026-11-09T191532781301 | 2 changed | quiet |
| 2026-11-09 | `remote/global.uain/network` | 2026-11-07T133615674913 -> 2026-11-09T191529077177 | 1 changed | quiet |
| 2026-11-09 | `remote/cz.iustoria/pruvodci` | 2026-11-09T170136618600 -> 2026-11-09T191531455719 | 1 added | quiet |
| 2026-11-09 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-08T204938726913 -> 2026-11-09T191530250783 | 2 changed | quiet |
| 2026-11-09 | `remote/com.swellcabin/surf` | 2026-11-09T170043074143 -> 2026-11-09T191526248259 | 2 changed | quiet |
| 2026-11-09 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-09T170014231818 -> 2026-11-09T191522214927 | 1 changed | quiet |
| 2026-11-09 | `remote/com.tangerineindex/tangerine-index` | 2026-11-09T170131544750 -> 2026-11-09T191522671255 | 4 changed (every tool) | quiet |
| 2026-11-09 | `remote/com.statisticsoftheworld/sotw` | 2026-11-09T170109003651 -> 2026-11-09T191520459975 | 1 added | quiet |
| 2026-11-09 | `remote/uk.co.santascalling/santas-calling` | 2026-11-09T165927832741 -> 2026-11-09T191517253081 | 4 changed (every tool) | quiet |
| 2026-11-09 | `remote/se.sistaminuten/travel-search` | 2026-11-09T170300760553 -> 2026-11-09T191512074307 | 1 changed | quiet |
| 2026-11-09 | `remote/io.github.andzar22/offstereo` | 2026-11-09T170248116301 -> 2026-11-09T191509855382 | 2 changed | quiet |
| 2026-11-09 | `remote/com.postthisdeal/deal-evidence` | 2026-11-09T165851769023 -> 2026-11-09T191511219667 | 2 added | quiet |
| 2026-11-09 | `remote/com.mailbypony/mail-by-pony` | 2026-11-07T133905797633 -> 2026-11-09T191509592610 | 1 changed | quiet |
| 2026-11-09 | `remote/dev.sourcepost/directory` | 2026-11-09T165847792935 -> 2026-11-09T191509038899 | 3 changed (every tool) | quiet |
| 2026-11-09 | `remote/org.goodtherapy/directory` | 2026-11-09T170237547960 -> 2026-11-09T191507514458 | 3 added, 1 removed | quiet |
| 2026-11-09 | `remote/fun.pumpdata/pumpdata` | 2026-11-09T071552252972 -> 2026-11-09T191507348324 | 1 changed | quiet |
| 2026-11-09 | `remote/org.parcelsheet/parcelsheet` | 2026-11-09T165806090033 -> 2026-11-09T191504393906 | 1 changed | quiet |
| 2026-11-09 | `remote/io.github.marcoret74/semantic-geometry` | 2026-11-09T170133314974 -> 2026-11-09T191500460017 | 1 changed | quiet |
| 2026-11-09 | `remote/com.partstable/partstable` | 2026-11-08T135244198818 -> 2026-11-09T191500760455 | 1 changed | quiet |
| 2026-11-09 | `remote/io.github.intoApex/tradingagentstack` | 2026-11-08T204921984416 -> 2026-11-09T191453470620 | 1 changed | quiet |
| 2026-11-09 | `remote/com.tkscmlimited.mine/hawaii-data` | 2026-11-09T165729754848 -> 2026-11-09T191449672976 | 1 added | quiet |
| 2026-11-09 | `remote/io.opsinlab/opsin` | 2026-11-09T165553472874 -> 2026-11-09T191446864266 | 2 added | quiet |
| 2026-11-09 | `remote/io.github.farenberglord-star/orb-studio` | 2026-11-09T165558417864 -> 2026-11-09T191448708768 | 1 added | quiet |
| 2026-11-09 | `remote/io.github.Invaro/opentax` | 2026-11-09T165553362819 -> 2026-11-09T191446464889 | 2 changed | quiet |
| 2026-11-09 | `remote/dev.tanod/tanod` | 2026-11-09T170016234672 -> 2026-11-09T191449624068 | 1 changed, 2 added | quiet |
| 2026-11-09 | `remote/dev.tanod/docs` | 2026-11-09T170016087118 -> 2026-11-09T191449884284 | 1 changed | quiet |
| 2026-11-09 | `remote/io.github.negm17111995/maqami-travel` | 2026-11-07T133005236051 -> 2026-11-09T191442114058 | 5 removed | quiet |
| 2026-11-09 | `remote/io.github.magichourhq/magic-hour` | 2026-11-07T063947379184 -> 2026-11-09T191441548697 | 1 changed, 2 added | review |
| 2026-11-09 | `remote/com.idosgames/platform` | 2026-11-09T071558042381 -> 2026-11-09T191442044304 | 2 changed | quiet |
| 2026-11-09 | `remote/com.midasiteurope/civil-nx` | 2026-11-09T165456598857 -> 2026-11-09T191440567818 | 1 changed | quiet |
| 2026-11-09 | `remote/io.github.yzlee/opcmenu` | 2026-11-09T165553776522 -> 2026-11-09T191439234825 | 147 changed, 11 added | quiet |
| 2026-11-09 | `remote/org.walkably/walkably` | 2026-11-08T204923035518 -> 2026-11-09T191436641929 | 1 changed | quiet |
| 2026-11-09 | `remote/io.github.eskygroup/thomascook-holidays` | 2026-11-09T165344855878 -> 2026-11-09T191435597239 | 1 changed | quiet |
| 2026-11-09 | `remote/com.queuesim/public` | 2026-11-09T165828038329 -> 2026-11-09T191434351915 | 3 added | quiet |
| 2026-11-09 | `remote/io.github.fxams/crewpay-mcp` | 2026-11-09T165326238417 -> 2026-11-09T191433162379 | 1 added | review |
| 2026-11-09 | `remote/com.prizepicksapi/server` | 2026-11-09T165815112948 -> 2026-11-09T191432408162 | 1 changed | quiet |
| 2026-11-09 | `remote/com.crm-connector/crm-connector` | 2026-11-09T165754618720 -> 2026-11-09T191428812175 | 1 changed | quiet |
| 2026-11-09 | `remote/io.github.eskygroup/esky-holidays` | 2026-11-09T165432154857 -> 2026-11-09T191427802418 | 1 changed | quiet |
| 2026-11-09 | `remote/co.deadbrands/arena` | 2026-11-09T165418081834 -> 2026-11-09T191426339871 | 5 changed, 1 added | quiet |
| 2026-11-09 | `remote/io.github.si-imtiaz/leadquasar` | 2026-11-09T165147565799 -> 2026-11-09T191424622748 | 1 changed | quiet |
| 2026-11-09 | `remote/io.github.KilvingtonDigital/groundquote` | 2026-11-09T165157038463 -> 2026-11-09T191423023974 | 4 changed | quiet |
| 2026-11-09 | `remote/io.github.lineofflight/frankfurter` | 2026-11-09T071549752074 -> 2026-11-09T191422829768 | 3 changed | quiet |
| 2026-11-09 | `remote/com.kushbitx/agentproof` | 2026-11-09T165141223123 -> 2026-11-09T191422056474 | 2 changed | quiet |
| 2026-11-09 | `remote/nl.nltaxcalculator/dutch-tax` | 2026-11-08T135413824819 -> 2026-11-09T191420799280 | 1 added | quiet |
| 2026-11-09 | `remote/com.netactuate/net-actuate` | 2026-11-09T165654440047 -> 2026-11-09T191419267347 | 1 changed | quiet |
| 2026-11-09 | `remote/app.luala/luala` | 2026-11-09T165236209434 -> 2026-11-09T191418524366 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 52567 substantive, 31197 that changed only numbers (a catalogue counter ticking, a date), 920 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 45128 | 15898 | 29230 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1843 | 1843 | 0 | 0 |
| `caseyjhand.com` | 359 | 359 | 0 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `civai.co` | 234 | 234 | 0 | 0 |
| `sistaminuten.se` | 216 | 6 | 0 | 210 |
| `afbudsrejser.dk` | 215 | 6 | 0 | 209 |
| `akkilahdot.fi` | 215 | 6 | 0 | 209 |
| `restplass.no` | 215 | 6 | 0 | 209 |
| `socialloop.ai` | 207 | 207 | 0 | 0 |
| `revmesh2074.workers.dev` | 197 | 174 | 23 | 0 |
| 8259 other operators | 33256 | 31229 | 1944 | 83 |
