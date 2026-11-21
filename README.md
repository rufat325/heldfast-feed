# MCP server tool changes

Last change observed 2026-11-21T15:12:42+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

123937 changes to a tool definition: 4965 npm releases (4719 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 118972 readings of hosted servers that found their tools changed; 4616 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-21 | `remote/com.youspot/youspot` | 2026-11-21T130621331446 -> 2026-11-21T151242937146 | 1 changed, 1 added | quiet |
| 2026-11-21 | `remote/com.yazilimkocu/pazaryeri` | 2026-11-13T013223617148 -> 2026-11-21T151234903205 | 5 changed | quiet |
| 2026-11-21 | `remote/ai.zairalabs/guide` | 2026-11-17T165016946030 -> 2026-11-21T151227850286 | 1 changed | quiet |
| 2026-11-21 | `remote/com.synthexforge.x402/paid-agent-services` | 2026-11-08T000131892422 -> 2026-11-21T151220951825 | 2 added | quiet |
| 2026-11-21 | `remote/com.yazilimkocu/yapayzeka` | 2026-11-13T013224377118 -> 2026-11-21T151219462711 | 5 changed | quiet |
| 2026-11-21 | `remote/com.yazilimkocu/erp` | 2026-11-13T013240452040 -> 2026-11-21T151217309382 | 5 changed | quiet |
| 2026-11-21 | `remote/com.yazilimkocu/crm` | 2026-11-13T013240606248 -> 2026-11-21T151217189084 | 5 changed | quiet |
| 2026-11-21 | `remote/com.yazilimkocu/belediye` | 2026-11-13T013224738165 -> 2026-11-21T151217996105 | 5 changed | quiet |
| 2026-11-21 | `remote/de.objelio/immobiliensuche` | 2026-11-17T164833016902 -> 2026-11-21T151211154878 | 1 changed | quiet |
| 2026-11-21 | `remote/com.movablecapital.www/cash-rates` | 2026-11-09T170144325045 -> 2026-11-21T151207494963 | 2 changed, 2 added | quiet |
| 2026-11-21 | `remote/com.market0x/marketplace` | 2026-11-02T163910150831 -> 2026-11-21T151205524505 | 13 changed (every tool) | quiet |
| 2026-11-21 | `remote/co.leviathansystems/public-content` | 2026-10-26T133656219969 -> 2026-11-21T151202728949 | 2 changed | quiet |
| 2026-11-21 | `remote/cz.iustoria/pruvodci` | 2026-11-11T150017340348 -> 2026-11-21T151159651007 | 7 changed | quiet |
| 2026-11-21 | `remote/io.peakcam/snow` | 2026-10-20T201151806509 -> 2026-11-21T151157079909 | 21 changed (every tool) | quiet |
| 2026-11-21 | `remote/com.peptul/peptul` | 2026-11-13T120623470273 -> 2026-11-21T151158144448 | 5 changed (every tool) | quiet |
| 2026-11-21 | `remote/fit.ilook/face-analysis` | 2026-09-26T114337779712 -> 2026-11-21T151155942983 | 1 changed, 1 added | quiet |
| 2026-11-21 | `remote/io.github.bostanyshop-rgb/growtsy` | 2026-11-21T014915167760 -> 2026-11-21T151152611311 | 11 changed | quiet |
| 2026-11-21 | `remote/com.metaintro/job-search` | 2026-11-12T155321241859 -> 2026-11-21T151151303041 | 2 changed | quiet |
| 2026-11-21 | `remote/co.yougame/yougame` | 2026-11-17T135703094387 -> 2026-11-21T151149229345 | 10 changed, 7 added, 4 removed | quiet |
| 2026-11-21 | `remote/se.sistaminuten/travel-search` | 2026-11-21T130648434809 -> 2026-11-21T151144039223 | 1 changed | quiet |
| 2026-11-21 | `remote/com.jokestack/jokestack` | 2026-11-10T130428909668 -> 2026-11-21T151144634004 | 1 changed | quiet |
| 2026-11-21 | `remote/jp.co.issoh/corporate-site` | 2026-09-23T162944807599 -> 2026-11-21T151143154441 | 1 changed | quiet |
| 2026-11-21 | `remote/com.dieanalysten/adressshop` | 2026-11-16T163259269719 -> 2026-11-21T151143654183 | 5 changed, 1 added (every tool) | quiet |
| 2026-11-21 | `remote/io.github.yandyman/agent-harbor-x402` | 2026-10-19T135910952338 -> 2026-11-21T151141783154 | 3 changed | quiet |
| 2026-11-21 | `remote/studio.gradients/mcp` | 2026-11-21T130613968243 -> 2026-11-21T151140004619 | 1 changed | quiet |
| 2026-11-21 | `remote/com.yazilimkocu/ajan` | 2026-11-13T013145503070 -> 2026-11-21T151138477262 | 6 changed, 2 added | quiet |
| 2026-11-21 | `remote/com.workeey/quote-links` | 2026-11-16T163401780009 -> 2026-11-21T151136849059 | 3 changed | quiet |
| 2026-11-21 | `remote/io.github.SoapyRED/freightutils` | 2026-11-15T002329820704 -> 2026-11-21T151135838334 | 26 changed | quiet |
| 2026-11-21 | `remote/com.theservicemarketingguys/audit` | 2026-09-23T163147469940 -> 2026-11-21T151130661862 | 7 changed (every tool) | quiet |
| 2026-11-21 | `remote/ar.com.consignatarias/cattle-market` | 2026-11-13T150219040630 -> 2026-11-21T151126388284 | 21 changed, 1 added | quiet |
| 2026-11-21 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-17T234400543320 -> 2026-11-21T151125361139 | 2 changed | quiet |
| 2026-11-21 | `remote/com.onlyworlds/mcp` | 2026-11-21T014813120711 -> 2026-11-21T151123808011 | 9 changed | quiet |
| 2026-11-21 | `remote/no.restplass/travel-search` | 2026-11-21T130558938965 -> 2026-11-21T151119324752 | 1 changed | quiet |
| 2026-11-21 | `remote/fi.akkilahdot/travel-search` | 2026-11-21T130613063311 -> 2026-11-21T151117493525 | 1 changed | quiet |
| 2026-11-21 | `remote/io.github.Ipayx-stellar/fx-audit` | 2026-11-20T105545290071 -> 2026-11-21T151116248969 | 4 changed (every tool) | quiet |
| 2026-11-21 | `remote/com.agrodiler/catalog` | 2026-11-16T163135901694 -> 2026-11-21T151117450194 | 7 changed (every tool) | quiet |
| 2026-11-21 | `remote/ai.whichagent/car-rental` | 2026-11-16T163226666213 -> 2026-11-21T151114353571 | 5 changed (every tool) | quiet |
| 2026-11-21 | `remote/com.wecookflow/mcp` | 2026-11-16T163223806538 -> 2026-11-21T151112343201 | 3 changed | quiet |
| 2026-11-21 | `remote/io.github.kamilobstawskiagent-ux/webskan` | 2026-11-09T170048637943 -> 2026-11-21T151111319480 | 2 changed | quiet |
| 2026-11-21 | `remote/io.github.sf0116/myschoolhub` | 2026-10-27T054122106693 -> 2026-11-21T151109531106 | 2 changed | quiet |
| 2026-11-21 | `remote/io.github.cryptoplayer/crypto-casinos` | 2026-10-20T104319068803 -> 2026-11-21T151107615589 | 12 changed, 1 added (every tool) | quiet |
| 2026-11-21 | `remote/ai.iolee/hotel-info` | 2026-11-16T163259343820 -> 2026-11-21T151101741663 | 1 changed, 3 added | quiet |
| 2026-11-21 | `remote/com.faithfriendlyjobs/jobs` | 2026-11-17T164808348460 -> 2026-11-21T151053774578 | 3 changed (every tool) | quiet |
| 2026-11-21 | `remote/it.expatliving/data` | 2026-10-30T063158019710 -> 2026-11-21T151053590186 | 1 changed | quiet |
| 2026-11-21 | `remote/io.github.zikriz/wallet-doctor-x402` | 2026-09-23T162925880396 -> 2026-11-21T151052440515 | 5 changed, 11 removed (every tool) | review |
| 2026-11-21 | `remote/com.entangleeq/pay-transparency` | 2026-10-17T055600283947 -> 2026-11-21T151052581908 | 5 changed (every tool) | quiet |
| 2026-11-21 | `remote/com.cm7brasil.www/mcp` | 2026-11-16T163201041836 -> 2026-11-21T151045346811 | 5 changed | quiet |
| 2026-11-21 | `remote/com.capcenter/capcenter` | 2026-11-05T115401259768 -> 2026-11-21T151042188393 | 1 changed | quiet |
| 2026-11-21 | `remote/io.christiantechjobs/jobs` | 2026-11-17T164902214694 -> 2026-11-21T151038484093 | 3 changed (every tool) | quiet |
| 2026-11-21 | `remote/com.christianjobslist/jobs` | 2026-11-17T164900680281 -> 2026-11-21T151038125630 | 3 changed (every tool) | quiet |
| 2026-11-21 | `remote/com.autoridaddigital.www/geo` | 2026-11-12T155000853501 -> 2026-11-21T151038142686 | 1 changed | quiet |
| 2026-11-21 | `remote/fr.capepartners/cape-exchange` | 2026-11-21T130557098113 -> 2026-11-21T151037343532 | 1 changed | quiet |
| 2026-11-21 | `remote/com.turbomaxai/mcp` | 2026-11-16T122742750259 -> 2026-11-21T151037324325 | 1 changed, 1 removed | quiet |
| 2026-11-21 | `remote/no.apier/mcp` | 2026-11-16T122955392485 -> 2026-11-21T151035620107 | 4 changed | quiet |
| 2026-11-21 | `remote/io.github.tighovh88-png/antarum` | 2026-11-18T135723580124 -> 2026-11-21T151029940613 | 1 changed | quiet |
| 2026-11-21 | `remote/dk.afbudsrejser/travel-search` | 2026-11-21T130556476101 -> 2026-11-21T151027687659 | 1 changed | quiet |
| 2026-11-21 | `remote/io.github.paulieb89/uk-due-diligence-mcp` | 2026-11-18T161731008476 -> 2026-11-21T151020411045 | 1 changed | quiet |
| 2026-11-21 | `remote/ai.peerfoundry/typedpull` | 2026-11-10T130413256203 -> 2026-11-21T151017539820 | 3 changed, 2 added | quiet |
| 2026-11-21 | `remote/cc.thecolony/mcp-server` | 2026-11-17T234333519698 -> 2026-11-21T151004499118 | 2 changed | quiet |
| 2026-11-21 | `remote/net.ticketsministry.ai/events` | 2026-10-17T055837788680 -> 2026-11-21T150950284689 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 81680 substantive, 41112 that changed only numbers (a catalogue counter ticking, a date), 1145 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 67416 | 29061 | 38355 | 0 |
| `a2awire.com` | 3571 | 3571 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 486 | 486 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 401 | 401 | 0 | 0 |
| `revmesh2074.workers.dev` | 350 | 298 | 52 | 0 |
| `sistaminuten.se` | 266 | 6 | 0 | 260 |
| `afbudsrejser.dk` | 265 | 6 | 0 | 259 |
| `akkilahdot.fi` | 265 | 6 | 0 | 259 |
| `restplass.no` | 265 | 6 | 0 | 259 |
| `socialloop.ai` | 256 | 256 | 0 | 0 |
| 10679 other operators | 47575 | 44762 | 2705 | 108 |
