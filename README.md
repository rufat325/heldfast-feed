# MCP server tool changes

Last change observed 2026-11-04T15:10:22+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

76994 changes to a tool definition: 3200 npm releases (2954 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 73794 readings of hosted servers that found their tools changed; 3342 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-04 | `remote/io.github.moelayyan90/xguard` | 2026-09-26T045459053286 -> 2026-11-04T151023212182 | 5 added, 8 removed | quiet |
| 2026-11-04 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-11-02T163638663685 -> 2026-11-04T151018392204 | 1 changed | quiet |
| 2026-11-04 | `remote/com.tabflows/site` | 2026-10-30T210645264293 -> 2026-11-04T151031259008 | 1 changed | quiet |
| 2026-11-04 | `remote/com.sapiensinteticos/sapiens` | 2026-11-01T065451806643 -> 2026-11-04T150937166264 | 2 changed | quiet |
| 2026-11-04 | `remote/no.restplass/travel-search` | 2026-11-04T123822599020 -> 2026-11-04T150934371466 | 1 changed | quiet |
| 2026-11-04 | `remote/com.primecutsnursery/public-data` | 2026-10-03T232152980441 -> 2026-11-04T150911545117 | 1 changed | quiet |
| 2026-11-04 | `remote/app.postel/postel` | 2026-10-30T133018036411 -> 2026-11-04T150910639702 | 3 changed | quiet |
| 2026-11-04 | `remote/be.lexgo/jobs` | 2026-10-19T135846617828 -> 2026-11-04T150844580686 | 1 changed | quiet |
| 2026-11-04 | `remote/com.iscabox/iscabox` | 2026-10-17T060444033099 -> 2026-11-04T150839518822 | 1 changed, 6 added, 6 removed | quiet |
| 2026-11-04 | `remote/es.zacatrus/zacatrus` | 2026-10-17T055632344632 -> 2026-11-04T150837867592 | 1 changed | quiet |
| 2026-11-04 | `remote/io.huntertech/vendor-insights.3` | 2026-10-30T133006009028 -> 2026-11-04T150834666936 | 3 changed | quiet |
| 2026-11-04 | `remote/xn--3ds443g.xn--s7y/duan-online` | 2026-11-01T135901633096 -> 2026-11-04T150831218846 | 1 added | quiet |
| 2026-11-04 | `remote/io.github.travisseamon-a11y/xemstudio` | 2026-10-29T212919867526 -> 2026-11-04T150828652968 | 2 changed | quiet |
| 2026-11-04 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-11-02T163455327675 -> 2026-11-04T150823754916 | 1 changed | quiet |
| 2026-11-04 | `remote/dev.workers.sebastiaan-ba3.x402lint/tools` | 2026-10-19T135311172482 -> 2026-11-04T150821540612 | 2 added | review |
| 2026-11-04 | `remote/com.findbroadbanddeals/broadband-deals` | 2026-10-26T211531499686 -> 2026-11-04T150856247303 | 4 changed (every tool) | quiet |
| 2026-11-04 | `remote/ai.usedby/usedby` | 2026-10-26T133920435468 -> 2026-11-04T150814049836 | 1 changed | quiet |
| 2026-11-04 | `remote/de.drgsystem/medical-catalogs` | 2026-10-30T210638595223 -> 2026-11-04T150809684593 | 2 changed | quiet |
| 2026-11-04 | `remote/com.techfabric/techfabric` | 2026-11-02T065433878799 -> 2026-11-04T150809718960 | 6 changed | quiet |
| 2026-11-04 | `remote/se.sistaminuten/travel-search` | 2026-11-04T123836362637 -> 2026-11-04T150756848697 | 1 changed | quiet |
| 2026-11-04 | `remote/domains.cheapest/cheapest-domains` | 2026-10-08T135515730210 -> 2026-11-04T150755046579 | 12 changed (every tool) | quiet |
| 2026-11-04 | `remote/ai.oriiion/oriiion` | 2026-11-03T144953382778 -> 2026-11-04T150750784738 | 1 changed | quiet |
| 2026-11-04 | `remote/de.objelio/immobiliensuche` | 2026-11-04T123815393471 -> 2026-11-04T150751453589 | 3 changed | quiet |
| 2026-11-04 | `remote/io.github.jonatanvazquez/propfacil` | 2026-10-27T112400608414 -> 2026-11-04T150748903334 | 3 changed | quiet |
| 2026-11-04 | `remote/com.orbitfour/domains` | 2026-10-26T133903936382 -> 2026-11-04T150744484527 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.andzar22/offstereo` | 2026-10-22T110002893720 -> 2026-11-04T150743288119 | 3 added | quiet |
| 2026-11-04 | `remote/com.lazyweb/discovery` | 2026-10-20T135422505401 -> 2026-11-04T150742774483 | 9 changed (every tool) | quiet |
| 2026-11-04 | `remote/io.github.oaleviola/arroway` | 2026-10-21T202557796630 -> 2026-11-04T150740709728 | 18 changed (every tool) | quiet |
| 2026-11-04 | `remote/com.menloinsurance/mcp` | 2026-10-30T132904284728 -> 2026-11-04T150738561901 | 3 changed | quiet |
| 2026-11-04 | `remote/dk.afbudsrejser/travel-search` | 2026-11-04T123816156368 -> 2026-11-04T150736824718 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.witanmarkets/witan` | 2026-11-01T135256004358 -> 2026-11-04T150730140040 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.Tomalarrrr/cyclesite-mcp-server` | 2026-11-04T123830452824 -> 2026-11-04T150717477407 | 34 changed (every tool) | quiet |
| 2026-11-04 | `remote/com.coverage-rights/coverage-rights` | 2026-09-23T161023535907 -> 2026-11-04T150713280320 | 9 changed, 1 added (every tool) | quiet |
| 2026-11-04 | `remote/io.github.ohad6k/viberaven-guides` | 2026-11-03T195554746035 -> 2026-11-04T150705406636 | 2 changed | quiet |
| 2026-11-04 | `remote/ai.usesuperflow/tools` | 2026-10-23T120558988077 -> 2026-11-04T150656541038 | 1 added | quiet |
| 2026-11-04 | `remote/io.github.Billibo6/unlockpulse` | 2026-11-04T123810083689 -> 2026-11-04T150650906868 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.cyanheads/unhcr-refugees-mcp-server` | 2026-10-20T104209993802 -> 2026-11-04T150649979385 | 7 changed | quiet |
| 2026-11-04 | `remote/io.github.cyanheads/unesco-heritage-mcp-server` | 2026-10-18T113318902584 -> 2026-11-04T150649879413 | 2 changed | quiet |
| 2026-11-04 | `remote/io.github.yappmaniac/grocery-price-snapshots` | 2026-10-27T210211612801 -> 2026-11-04T150647979730 | 5 changed (every tool) | quiet |
| 2026-11-04 | `remote/io.github.Z4KARY/upgrowth-mcp` | 2026-10-29T104603913119 -> 2026-11-04T150642775136 | 1 added | quiet |
| 2026-11-04 | `remote/io.github.gmahar82-stack/trust-check` | 2026-10-22T110149491525 -> 2026-11-04T150639681815 | 1 changed | review |
| 2026-11-04 | `remote/dev.workers.rainmaker-wells.well-016-datacleanup/data-cleanup` | 2026-10-26T133820903584 -> 2026-11-04T150634985205 | 1 changed | quiet |
| 2026-11-04 | `remote/dev.workers.rainmaker-wells.well-011-sharescan/sharescan` | 2026-10-26T133820232517 -> 2026-11-04T150633910748 | 1 changed | quiet |
| 2026-11-04 | `remote/dev.workers.rainmaker-wells.well-009-url-change-watch/url-change-check` | 2026-10-26T133819888587 -> 2026-11-04T150633301807 | 1 changed | quiet |
| 2026-11-04 | `remote/io.tooloracle/yieldoracle` | 2026-09-23T163049873593 -> 2026-11-04T150627988550 | 3 changed | quiet |
| 2026-11-04 | `remote/io.tooloracle/macroooracle` | 2026-10-08T135433561551 -> 2026-11-04T150627500706 | 4 changed | quiet |
| 2026-11-04 | `remote/video.quiz/api` | 2026-10-18T113319829516 -> 2026-11-04T150625587926 | 3 changed, 8 added | quiet |
| 2026-11-04 | `remote/io.tooloracle/ampel` | 2026-09-23T163048525605 -> 2026-11-04T150625450118 | 1 changed | quiet |
| 2026-11-04 | `remote/com.premierletters/mcp` | 2026-10-21T202524324666 -> 2026-11-04T150622973840 | 2 changed, 1 added | quiet |
| 2026-11-04 | `remote/com.variotrip/esim-catalog` | 2026-10-29T104347378197 -> 2026-11-04T150605670377 | 4 changed | quiet |
| 2026-11-04 | `remote/studio.gradients/mcp` | 2026-11-04T123817129914 -> 2026-11-04T150600378470 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.SoapyRED/freightutils` | 2026-10-31T062140842699 -> 2026-11-04T150556429669 | 1 changed | quiet |
| 2026-11-04 | `remote/com.findbroadbanddeals/broadband-outages` | 2026-10-27T112232089334 -> 2026-11-04T150555222310 | 3 changed (every tool) | quiet |
| 2026-11-04 | `remote/de.containerdienst-regional/anfrage` | 2026-10-28T133107112407 -> 2026-11-04T150544056717 | 1 changed | quiet |
| 2026-11-04 | `remote/com.udansa/udansa` | 2026-10-23T120820780793 -> 2026-11-04T150538128060 | 2 changed | quiet |
| 2026-11-04 | `remote/ink.trinkwassermonitor/trinkwasser` | 2026-10-19T135143761090 -> 2026-11-04T150534573076 | 3 changed | quiet |
| 2026-11-04 | `remote/app.openkrill/transcript-kit` | 2026-10-31T130141955053 -> 2026-11-04T150531175452 | 1 changed | quiet |
| 2026-11-04 | `remote/fi.akkilahdot/travel-search` | 2026-11-04T123815205762 -> 2026-11-04T150529366834 | 1 changed | quiet |
| 2026-11-04 | `remote/com.ablakunio/nyilaszaro-mcp` | 2026-09-23T162932563550 -> 2026-11-04T150527753894 | 5 changed (every tool) | quiet |
| 2026-11-04 | `remote/io.tooloracle/memeoracle` | 2026-09-23T160814437553 -> 2026-11-04T150522300451 | 3 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 47109 substantive, 29063 that changed only numbers (a catalogue counter ticking, a date), 822 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 43261 | 15875 | 27386 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1366 | 1366 | 0 | 0 |
| `caseyjhand.com` | 352 | 352 | 0 | 0 |
| `sistaminuten.se` | 194 | 6 | 0 | 188 |
| `afbudsrejser.dk` | 193 | 6 | 0 | 187 |
| `akkilahdot.fi` | 193 | 6 | 0 | 187 |
| `restplass.no` | 193 | 6 | 0 | 187 |
| `socialloop.ai` | 186 | 186 | 0 | 0 |
| `remoshift.com` | 163 | 13 | 150 | 0 |
| `openkrill.app` | 152 | 152 | 0 | 0 |
| `fundinglandscape.com` | 148 | 89 | 59 | 0 |
| 7488 other operators | 28252 | 26711 | 1468 | 73 |
