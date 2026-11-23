# MCP server tool changes

Last change observed 2026-11-23T20:40:14+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 18238 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 43073 hosted endpoints (read daily, and every four hours while they keep changing).

130303 changes to a tool definition: 5227 npm releases (4981 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 125076 readings of hosted servers that found their tools changed; 4764 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-23 | `remote/xyz.quantumatlas/x402-payment-hub` | 2026-11-23T185522940055 -> 2026-11-23T204015302351 | 1 changed | quiet |
| 2026-11-23 | `remote/no.restplass/travel-search` | 2026-11-23T185458597904 -> 2026-11-23T204012231557 | 1 changed | quiet |
| 2026-11-23 | `remote/com.riskcovery/mcp` | 2026-11-23T185459400956 -> 2026-11-23T204011795966 | 1 changed | quiet |
| 2026-11-23 | `remote/gg.keyfinder/price-lookup` | 2026-11-23T185438010146 -> 2026-11-23T204007406272 | 1 changed | quiet |
| 2026-11-23 | `remote/com.xmlvalid/xmlvalid` | 2026-11-22T104912442208 -> 2026-11-23T204006809426 | 2 changed, 1 added | review |
| 2026-11-23 | `remote/dk.afbudsrejser/travel-search` | 2026-11-23T185401782126 -> 2026-11-23T204003698932 | 1 changed | quiet |
| 2026-11-23 | `remote/ai.usedby/usedby` | 2026-11-23T185854333293 -> 2026-11-23T204003556349 | 2 changed | quiet |
| 2026-11-23 | `remote/studio.gradients/mcp` | 2026-11-23T185517858010 -> 2026-11-23T204004481845 | 1 changed | quiet |
| 2026-11-23 | `remote/se.sistaminuten/travel-search` | 2026-11-23T185837407491 -> 2026-11-23T204002127918 | 1 changed | quiet |
| 2026-11-23 | `remote/fi.akkilahdot/travel-search` | 2026-11-23T185444646680 -> 2026-11-23T203958751267 | 1 changed | quiet |
| 2026-11-23 | `remote/com.weverlabs/agentic-rails` | 2026-11-23T185417561887 -> 2026-11-23T204004828487 | 8 added | quiet |
| 2026-11-23 | `remote/com.trucehq/truce` | 2026-11-23T185250178831 -> 2026-11-23T203956437612 | 7 changed, 5 added (every tool) | quiet |
| 2026-11-23 | `remote/com.thenetworkery/network-tools` | 2026-11-23T185456767971 -> 2026-11-23T203940857198 | 1 changed | quiet |
| 2026-11-23 | `remote/io.github.SeoScoreAPI/seoscoreapi-mcp` | 2026-11-23T185046524168 -> 2026-11-23T203938282348 | 1 changed | quiet |
| 2026-11-23 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-23T185131106798 -> 2026-11-23T203936841990 | 1 changed | quiet |
| 2026-11-23 | `remote/dev.socialtap/mcp` | 2026-11-23T185132334049 -> 2026-11-23T203937401184 | 8 changed | quiet |
| 2026-11-23 | `remote/io.github.savegeeks/savegeeks-mcp` | 2026-11-23T185035076743 -> 2026-11-23T203929648769 | 1 changed | quiet |
| 2026-11-23 | `remote/com.radarbg/radar-tools` | 2026-11-23T081917206857 -> 2026-11-23T203930095307 | 5 added | quiet |
| 2026-11-23 | `remote/com.remoshift/jobs` | 2026-11-23T081943753215 -> 2026-11-23T203925845636 | 1 changed | quiet |
| 2026-11-23 | `remote/io.github.jamessvn/registry-pages` | 2026-11-23T185002957509 -> 2026-11-23T203925673818 | 3 changed | quiet |
| 2026-11-23 | `remote/io.speakbase/speakbase` | 2026-11-23T185012086476 -> 2026-11-23T203924143549 | 3 changed | quiet |
| 2026-11-23 | `remote/io.github.codytodd-ui/pitchspark` | 2026-11-22T164147919164 -> 2026-11-23T203923925551 | 12 changed | quiet |
| 2026-11-23 | `remote/io.github.roman-rr/trading-signals` | 2026-11-23T184953103805 -> 2026-11-23T203920857808 | 1 changed | quiet |
| 2026-11-23 | `remote/com.clicndone.pdf/pdf-tools` | 2026-11-23T184839537654 -> 2026-11-23T203920779818 | 1 changed | quiet |
| 2026-11-23 | `remote/io.github.Arbromagency-Sato/phantom-mcp-server` | 2026-11-23T184835191392 -> 2026-11-23T203919505712 | 1 changed, 6 removed | quiet |
| 2026-11-23 | `remote/com.salonrenter/salonrenter-muse` | 2026-11-23T185250743879 -> 2026-11-23T203919536618 | 8 changed (every tool) | quiet |
| 2026-11-23 | `remote/io.github.lx1112/agent-data-api` | 2026-11-23T184813126544 -> 2026-11-23T203917236254 | 10 added | review |
| 2026-11-23 | `remote/si.nosebleed/guides` | 2026-11-23T184758152607 -> 2026-11-23T203915103684 | 3 changed (every tool) | quiet |
| 2026-11-23 | `remote/com.imagiolabs.www/imagio-relay` | 2026-11-23T184848891693 -> 2026-11-23T203913348128 | 16 changed | review |
| 2026-11-23 | `remote/io.outil/outil` | 2026-11-23T081901926819 -> 2026-11-23T203909988933 | 1 changed | quiet |
| 2026-11-23 | `remote/io.github.farenberglord-star/orb-studio` | 2026-11-23T184721069436 -> 2026-11-23T203904803270 | 2 changed, 3 added | quiet |
| 2026-11-23 | `remote/io.github.Red-Center-Studio/nocode-migrator` | 2026-11-23T184645985282 -> 2026-11-23T203859585995 | 1 changed | quiet |
| 2026-11-23 | `remote/com.rationalbloks/mcp` | 2026-11-23T184529707424 -> 2026-11-23T203900477539 | 1 added | quiet |
| 2026-11-23 | `remote/com.meettempi/tempi` | 2026-11-22T221025839305 -> 2026-11-23T203900728079 | 1 changed | quiet |
| 2026-11-23 | `remote/io.github.roomi-fields/osc-bridge` | 2026-11-23T184557022516 -> 2026-11-23T203854887987 | 1 changed | quiet |
| 2026-11-23 | `remote/io.github.rationalbloks/rationalbloks-mcp` | 2026-11-23T184750053197 -> 2026-11-23T203854765160 | 1 added | quiet |
| 2026-11-23 | `remote/cloud.redu/mcp` | 2026-11-22T145907127229 -> 2026-11-23T203855041378 | 1 added | quiet |
| 2026-11-23 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-11-23T184709376646 -> 2026-11-23T203851094441 | 1 changed | review |
| 2026-11-23 | `remote/fm.fyug/mcp` | 2026-11-23T184351205652 -> 2026-11-23T203851895948 | 2 changed | quiet |
| 2026-11-23 | `remote/ca.fonciq/fonciq` | 2026-11-21T150159402385 -> 2026-11-23T203850829380 | 5 changed | quiet |
| 2026-11-23 | `remote/dev.qrdx/qrdx` | 2026-11-23T184518939499 -> 2026-11-23T203848797502 | 2 changed, 4 added | quiet |
| 2026-11-23 | `remote/ai.jerry/insurance` | 2026-11-23T184627300598 -> 2026-11-23T203847400691 | 2 changed | quiet |
| 2026-11-23 | `remote/co.deadbrands/arena` | 2026-11-23T184313356774 -> 2026-11-23T203843160652 | 13 added | quiet |
| 2026-11-23 | `remote/ai.mapmap/mapmap` | 2026-11-23T184423322914 -> 2026-11-23T203845224992 | 1 changed | quiet |
| 2026-11-23 | `remote/it.lazyanalysis/lazyanalysis` | 2026-11-23T184414209506 -> 2026-11-23T203843383528 | 4 added | quiet |
| 2026-11-23 | `remote/ca.bakhour/profitcollector` | 2026-11-22T145657147183 -> 2026-11-23T203836460345 | 8 changed, 1 added, 7 removed | quiet |
| 2026-11-23 | `remote/io.github.Poiuyhje/eqvps` | 2026-11-23T184250650791 -> 2026-11-23T203836628769 | 1 changed | quiet |
| 2026-11-23 | `remote/io.github.daniel3303/equibles` | 2026-11-23T184259588478 -> 2026-11-23T203834906803 | 1 added | quiet |
| 2026-11-23 | `remote/com.deyaho/phone-calls` | 2026-11-23T184240360219 -> 2026-11-23T203834329262 | 3 changed | quiet |
| 2026-11-23 | `remote/io.github.Craig-Horton/aibvf-mcp` | 2026-11-22T221007146358 -> 2026-11-23T203829033749 | 1 changed | quiet |
| 2026-11-23 | `remote/de.kernelterrasse/terrassenplaner` | 2026-11-23T184242228430 -> 2026-11-23T203827091710 | 2 changed | quiet |
| 2026-11-23 | `remote/nl.jsplinter/jsplinter` | 2026-11-23T184028996357 -> 2026-11-23T203826984235 | 1 changed | quiet |
| 2026-11-23 | `remote/net.isitdns/isitdns` | 2026-11-23T184217244517 -> 2026-11-23T203823899312 | 6 changed (every tool) | quiet |
| 2026-11-23 | `remote/com.ksaworks/goldseam` | 2026-11-23T183919584583 -> 2026-11-23T203817662733 | 2 changed | quiet |
| 2026-11-23 | `remote/fr.ip73/ip73` | 2026-11-23T183955979584 -> 2026-11-23T203816726555 | 2 changed | quiet |
| 2026-11-23 | `remote/com.factanker/factanker` | 2026-11-23T183735979730 -> 2026-11-23T203813830103 | 1 changed | quiet |
| 2026-11-23 | `remote/com.exchangerebel/exchangerebel` | 2026-11-23T081842567981 -> 2026-11-23T203813181550 | 1 changed, 1 added | quiet |
| 2026-11-23 | `remote/ai.guestlogic/guest-logic` | 2026-11-21T130536833409 -> 2026-11-23T203809975660 | 27 changed | quiet |
| 2026-11-23 | `remote/space.galaxymind/galaxy-mind` | 2026-11-23T183706448665 -> 2026-11-23T203807363430 | 1 changed | quiet |
| 2026-11-23 | `remote/au.com.getneatly/neatly` | 2026-11-23T183846408740 -> 2026-11-23T203808504445 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 86020 substantive, 43100 that changed only numbers (a catalogue counter ticking, a date), 1183 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 71149 | 30943 | 40206 | 0 |
| `a2awire.com` | 3704 | 3704 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 521 | 521 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 401 | 401 | 0 | 0 |
| `revmesh2074.workers.dev` | 367 | 312 | 55 | 0 |
| `sistaminuten.se` | 275 | 6 | 0 | 269 |
| `afbudsrejser.dk` | 274 | 6 | 0 | 268 |
| `akkilahdot.fi` | 274 | 6 | 0 | 268 |
| `restplass.no` | 274 | 6 | 0 | 268 |
| `socialloop.ai` | 265 | 265 | 0 | 0 |
| 10989 other operators | 49978 | 47029 | 2839 | 110 |
