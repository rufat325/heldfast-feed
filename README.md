# MCP server tool changes

Last change observed 2026-11-23T18:59:03+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 18238 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 43073 hosted endpoints (read daily, and every four hours while they keep changing).

130202 changes to a tool definition: 5227 npm releases (4981 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 124975 readings of hosted servers that found their tools changed; 4754 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-23 | `remote/com.n9t2/xrpl-agent-gateway` | 2026-10-20T104401177785 -> 2026-11-23T185907127328 | 1 changed | quiet |
| 2026-11-23 | `remote/io.github.vstockma/x402-apis` | 2026-11-20T160046946221 -> 2026-11-23T185901638524 | 2 changed | quiet |
| 2026-11-23 | `remote/io.github.vanakenj45/x402-agent-api` | 2026-10-26T133922591157 -> 2026-11-23T185900748895 | 2 added | review |
| 2026-11-23 | `remote/ai.usedby/usedby` | 2026-11-20T105608742098 -> 2026-11-23T185854333293 | 1 changed | quiet |
| 2026-11-23 | `remote/eu.trisonia/concerts` | 2026-11-14T140419021534 -> 2026-11-23T185852469838 | 2 changed | quiet |
| 2026-11-23 | `remote/io.taifoon/coordination-layer.1` | 2026-11-22T150751986469 -> 2026-11-23T185843448187 | 2 changed | review |
| 2026-11-23 | `remote/io.suverse.www/catalog` | 2026-11-22T221052053443 -> 2026-11-23T185843261040 | 3 changed | quiet |
| 2026-11-23 | `remote/se.sistaminuten/travel-search` | 2026-11-23T081925243594 -> 2026-11-23T185837407491 | 1 changed | quiet |
| 2026-11-23 | `remote/com.paxmod/paxmod` | 2026-11-09T170251006769 -> 2026-11-23T185820531974 | 5 added | quiet |
| 2026-11-23 | `remote/de.overfit/overfit` | 2026-11-16T072204774602 -> 2026-11-23T185819968219 | 2 changed | quiet |
| 2026-11-23 | `remote/com.metaltakip/digest` | 2026-11-19T123854694543 -> 2026-11-23T185809291167 | 1 changed, 2 added | quiet |
| 2026-11-23 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-11-23T081915703525 -> 2026-11-23T185758150339 | 2 changed | quiet |
| 2026-11-23 | `remote/io.github.JcJamet/ia-qa-security` | 2026-11-23T081915797069 -> 2026-11-23T185758341986 | 2 changed | quiet |
| 2026-11-23 | `remote/io.github.JcJamet/ia-qa-eval` | 2026-11-23T081915747766 -> 2026-11-23T185758254117 | 2 changed | quiet |
| 2026-11-23 | `remote/com.herbertandphyllis/mcp` | 2026-11-23T081915284498 -> 2026-11-23T185756675215 | 1 changed | quiet |
| 2026-11-23 | `remote/com.feode/feode-mcp` | 2026-10-25T102508463727 -> 2026-11-23T185749595405 | 12 changed, 7 added (every tool) | quiet |
| 2026-11-23 | `remote/me.divest/divestme` | 2026-10-17T055558643050 -> 2026-11-23T185742420244 | 1 changed | review |
| 2026-11-23 | `remote/com.digitaltableteur/mcp` | 2026-11-07T133850520944 -> 2026-11-23T185741429815 | 2 changed | quiet |
| 2026-11-23 | `remote/io.github.TMcodingarc/bull-otc` | 2026-11-23T081912331282 -> 2026-11-23T185732582332 | 1 added | quiet |
| 2026-11-23 | `remote/no.apier/mcp` | 2026-11-22T104628249733 -> 2026-11-23T185721928924 | 2 added | quiet |
| 2026-11-23 | `remote/io.github.LF3551/alekseialeinikov-site` | 2026-11-16T163152163029 -> 2026-11-23T185717906104 | 1 added | quiet |
| 2026-11-23 | `remote/run.wield/wield` | 2026-11-09T170202827796 -> 2026-11-23T185655186653 | 1 changed | quiet |
| 2026-11-23 | `remote/com.warminboxes/fleet-planner` | 2026-11-16T163113185384 -> 2026-11-23T185626271407 | 16 changed (every tool) | quiet |
| 2026-11-23 | `remote/com.warminboxes/deliverability-tools` | 2026-11-16T122917274854 -> 2026-11-23T185625480710 | 52 changed (every tool) | quiet |
| 2026-11-23 | `remote/now.vulnerable/mcp` | 2026-11-16T163106534504 -> 2026-11-23T185619549951 | 4 changed | quiet |
| 2026-11-23 | `remote/com.varioroam/esim-catalog` | 2026-11-12T154908112763 -> 2026-11-23T185600836656 | 8 changed (every tool) | quiet |
| 2026-11-23 | `remote/com.usetested/reviews` | 2026-11-18T135634217442 -> 2026-11-23T185557066902 | 1 changed, 1 added | quiet |
| 2026-11-23 | `remote/io.github.sorzio/sorzio` | 2026-11-09T170352631926 -> 2026-11-23T185552653558 | 20 changed, 1 added | quiet |
| 2026-11-23 | `remote/fr.publicoffre/marches-publics` | 2026-11-12T155330649448 -> 2026-11-23T185544324540 | 1 added | quiet |
| 2026-11-23 | `remote/uk.co.pocketly/offers` | 2026-11-15T115651735500 -> 2026-11-23T185540825544 | 1 changed | quiet |
| 2026-11-23 | `remote/io.github.aanari/loacare-healthcare-pricing` | 2026-11-18T135945268716 -> 2026-11-23T185531557720 | 2 added | review |
| 2026-11-23 | `remote/co.yougame/yougame` | 2026-11-22T104518623445 -> 2026-11-23T185526647782 | 1 changed | quiet |
| 2026-11-23 | `remote/com.jobcrawls/connector` | 2026-11-10T152941335688 -> 2026-11-23T185523586021 | 1 changed, 26 added | quiet |
| 2026-11-23 | `remote/com.incrediblefi/loan-marketplace` | 2026-11-03T145023011235 -> 2026-11-23T185520864027 | 1 changed, 2 removed | quiet |
| 2026-11-23 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/cve-package-domain-security` | 2026-11-18T135941289942 -> 2026-11-23T185521344900 | 1 changed | quiet |
| 2026-11-23 | `remote/co.ibda/ibda` | 2026-11-22T164202035845 -> 2026-11-23T185519476176 | 1 changed | quiet |
| 2026-11-23 | `remote/app.hyperwave.www/wavetable-tools` | 2026-11-23T081957052112 -> 2026-11-23T185519817670 | 1 changed | quiet |
| 2026-11-23 | `remote/studio.gradients/mcp` | 2026-11-23T081957802655 -> 2026-11-23T185517858010 | 1 changed | quiet |
| 2026-11-23 | `remote/com.uicapsule/components` | 2026-11-16T163345133801 -> 2026-11-23T185513378556 | 2 changed (every tool) | quiet |
| 2026-11-23 | `remote/io.github.SoapyRED/freightutils` | 2026-11-22T073232903176 -> 2026-11-23T185511724731 | 3 added, 1 removed | quiet |
| 2026-11-23 | `remote/io.github.sudzikcoin/suverse-agent-assistant` | 2026-11-22T221028357623 -> 2026-11-23T185510825296 | 3 changed | quiet |
| 2026-11-23 | `remote/io.github.heavyblotto/caelus-mcp` | 2026-09-23T162941362411 -> 2026-11-23T185506870934 | 8 added | quiet |
| 2026-11-23 | `remote/loans.sbaexpress.www/sbaexpress-loans` | 2026-11-19T123905439349 -> 2026-11-23T185500505866 | 1 changed | quiet |
| 2026-11-23 | `remote/com.sapiensinteticos/sapiens` | 2026-11-16T122936051830 -> 2026-11-23T185459713267 | 5 changed | quiet |
| 2026-11-23 | `remote/no.restplass/travel-search` | 2026-11-23T081924867280 -> 2026-11-23T185458597904 | 1 changed | quiet |
| 2026-11-23 | `remote/com.riskcovery/mcp` | 2026-11-22T104436353179 -> 2026-11-23T185459400956 | 3 changed | quiet |
| 2026-11-23 | `remote/com.thenetworkery/network-tools` | 2026-11-11T145754132100 -> 2026-11-23T185456767971 | 5 added | quiet |
| 2026-11-23 | `remote/io.github.openaccountants/openaccountants` | 2026-11-21T014815268519 -> 2026-11-23T185451135885 | 2 changed | quiet |
| 2026-11-23 | `remote/io.github.heathermacavelia-cell/ai-agent-index` | 2026-11-02T163221929550 -> 2026-11-23T185451136352 | 2 changed | quiet |
| 2026-11-23 | `remote/com.eliteaiempire/th-api` | 2026-11-17T135624881494 -> 2026-11-23T185451488060 | 1 changed | quiet |
| 2026-11-23 | `remote/in.nebulatech/nebula` | 2026-11-18T135834090887 -> 2026-11-23T185448165056 | 6 added, 4 removed | quiet |
| 2026-11-23 | `remote/fi.akkilahdot/travel-search` | 2026-11-23T081955773431 -> 2026-11-23T185444646680 | 1 changed | quiet |
| 2026-11-23 | `remote/xyz.wunderlust/wunderlust` | 2026-11-17T031604702458 -> 2026-11-23T185440791345 | 1 changed | quiet |
| 2026-11-23 | `remote/tech.tchin/tchin` | 2026-11-04T123815118806 -> 2026-11-23T185438283257 | 6 changed, 4 removed | quiet |
| 2026-11-23 | `remote/com.iscabox/iscabox` | 2026-11-18T174125101160 -> 2026-11-23T185436265835 | 4 changed | quiet |
| 2026-11-23 | `remote/io.github.cryptoduke01/gloam` | 2026-11-19T123840879331 -> 2026-11-23T185429567203 | 6 changed | quiet |
| 2026-11-23 | `remote/app.fluxgraph/linkedin` | 2026-11-19T123836538687 -> 2026-11-23T185425741278 | 1 changed | quiet |
| 2026-11-23 | `remote/io.github.MsingathiM/swapeazi` | 2026-11-22T104357822402 -> 2026-11-23T185424582823 | 4 added | quiet |
| 2026-11-23 | `remote/com.supercyclehq/supercycle` | 2026-11-22T150413290773 -> 2026-11-23T185420907455 | 2 added | quiet |
| 2026-11-23 | `remote/com.subsola/subsola` | 2026-11-20T105303585911 -> 2026-11-23T185418409845 | 2 changed (every tool) | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 85933 substantive, 43090 that changed only numbers (a catalogue counter ticking, a date), 1179 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 71149 | 30943 | 40206 | 0 |
| `a2awire.com` | 3704 | 3704 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 521 | 521 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 401 | 401 | 0 | 0 |
| `revmesh2074.workers.dev` | 367 | 312 | 55 | 0 |
| `sistaminuten.se` | 274 | 6 | 0 | 268 |
| `afbudsrejser.dk` | 273 | 6 | 0 | 267 |
| `akkilahdot.fi` | 273 | 6 | 0 | 267 |
| `restplass.no` | 273 | 6 | 0 | 267 |
| `socialloop.ai` | 264 | 264 | 0 | 0 |
| 10962 other operators | 49882 | 46943 | 2829 | 110 |
