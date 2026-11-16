# MCP server tool changes

Last change observed 2026-11-16T12:32:00+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

107037 changes to a tool definition: 4377 npm releases (4131 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 102660 readings of hosted servers that found their tools changed; 4190 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-16 | `remote/io.github.zerotohundred-admin/marketplace` | 2026-11-05T115612848453 -> 2026-11-16T123202758255 | 1 changed | quiet |
| 2026-11-16 | `remote/dev.primitive/email` | 2026-11-09T191553173403 -> 2026-11-16T123127829043 | 2 changed | quiet |
| 2026-11-16 | `remote/com.premierletters/mcp` | 2026-11-09T170339092594 -> 2026-11-16T123127472279 | 3 changed | quiet |
| 2026-11-16 | `remote/insure.travelprotection/travel-insurance` | 2026-11-02T065459903591 -> 2026-11-16T123108230371 | 1 changed | quiet |
| 2026-11-16 | `remote/studio.gradients/mcp` | 2026-11-16T072239188337 -> 2026-11-16T123105867967 | 1 changed | quiet |
| 2026-11-16 | `remote/io.github.EasyGerber/easygerber` | 2026-11-15T212154972242 -> 2026-11-16T123057185307 | 2 changed | quiet |
| 2026-11-16 | `remote/se.sistaminuten/travel-search` | 2026-11-16T072204513726 -> 2026-11-16T123049966759 | 1 changed | quiet |
| 2026-11-16 | `remote/fi.akkilahdot/travel-search` | 2026-11-16T072238438666 -> 2026-11-16T123045019130 | 1 changed | quiet |
| 2026-11-16 | `remote/io.github.evanyuki/codex-reset-monitor` | 2026-11-09T170232872269 -> 2026-11-16T123044454823 | 3 changed (every tool) | quiet |
| 2026-11-16 | `remote/com.youspot/youspot` | 2026-11-11T071432825132 -> 2026-11-16T123040624495 | 1 changed | quiet |
| 2026-11-16 | `remote/com.whichli/photo-polls` | 2026-09-23T162928939222 -> 2026-11-16T123034423448 | 1 changed | quiet |
| 2026-11-16 | `remote/io.github.kwizzlesurp10-ctrl/x402-mcp` | 2026-11-10T153326804657 -> 2026-11-16T123032386024 | 1 changed | quiet |
| 2026-11-16 | `remote/com.menloinsurance/mcp` | 2026-11-12T155029904537 -> 2026-11-16T123028123242 | 3 changed | quiet |
| 2026-11-16 | `remote/com.easykmarket.vote/votebox-law` | 2026-11-10T152850507893 -> 2026-11-16T123021338984 | 2 changed | quiet |
| 2026-11-16 | `remote/online.gofigure/data-figure-studio` | 2026-10-28T062225527279 -> 2026-11-16T123017745315 | 2 changed | review |
| 2026-11-16 | `remote/com.fuelazores/fuel-prices` | 2026-10-06T110148764362 -> 2026-11-16T123013044541 | 3 changed (every tool) | quiet |
| 2026-11-16 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-16T072236844588 -> 2026-11-16T123013215030 | 2 changed | quiet |
| 2026-11-16 | `remote/io.github.simonwbird/roamworthy` | 2026-10-17T055904592242 -> 2026-11-16T123013809914 | 1 changed | quiet |
| 2026-11-16 | `remote/co.yougame/yougame` | 2026-11-16T072220040899 -> 2026-11-16T123000047324 | 5 changed | quiet |
| 2026-11-16 | `remote/io.github.moelayyan90/xguard` | 2026-11-15T142646702529 -> 2026-11-16T122954845610 | 3 added | quiet |
| 2026-11-16 | `remote/ai.arcreport/ask` | 2026-11-07T064003048101 -> 2026-11-16T122954894284 | 6 changed, 19 removed (every tool) | quiet |
| 2026-11-16 | `remote/no.apier/mcp` | 2026-11-12T154959691390 -> 2026-11-16T122955392485 | 7 changed | quiet |
| 2026-11-16 | `remote/world.agentindex/x402` | 2026-11-10T153105014183 -> 2026-11-16T122955185610 | 1 changed | quiet |
| 2026-11-16 | `remote/ai.undetectedgpt/humanizer` | 2026-10-04T055125236202 -> 2026-11-16T122945817671 | 1 changed | quiet |
| 2026-11-16 | `remote/com.themachinerentalscam/rental-quotes` | 2026-11-04T123822641845 -> 2026-11-16T122943837609 | 2 changed | quiet |
| 2026-11-16 | `remote/com.rightshold/rightshold` | 2026-11-10T153304014148 -> 2026-11-16T122943015126 | 2 changed | quiet |
| 2026-11-16 | `remote/cz.storeinvent/mcp` | 2026-09-23T163146438596 -> 2026-11-16T122942033731 | 7 changed (every tool) | quiet |
| 2026-11-16 | `remote/com.sapiensinteticos/sapiens` | 2026-11-09T191543781528 -> 2026-11-16T122936051830 | 2 changed | quiet |
| 2026-11-16 | `remote/no.restplass/travel-search` | 2026-11-16T072218726942 -> 2026-11-16T122935189167 | 1 changed | quiet |
| 2026-11-16 | `remote/ai.whatsupin/events` | 2026-11-11T071416078641 -> 2026-11-16T122930812057 | 5 changed | quiet |
| 2026-11-16 | `remote/com.nomosprotocol/nomos` | 2026-11-12T074745424008 -> 2026-11-16T122929010609 | 1 changed | quiet |
| 2026-11-16 | `remote/ar.mueblito/mueblito` | 2026-11-02T163610401065 -> 2026-11-16T122926736818 | 8 changed | quiet |
| 2026-11-16 | `remote/io.github.Andrii-Tiurin/mono-esim` | 2026-11-11T071456271448 -> 2026-11-16T122926633437 | 1 changed | quiet |
| 2026-11-16 | `remote/com.meridiandispatch/travel-guides` | 2026-11-10T153029773670 -> 2026-11-16T122923869344 | 1 changed | quiet |
| 2026-11-16 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-16T072235485842 -> 2026-11-16T122924389170 | 2 changed | quiet |
| 2026-11-16 | `remote/uk.webdesignbasingstoke/site` | 2026-11-11T145907658380 -> 2026-11-16T122922482881 | 2 changed | quiet |
| 2026-11-16 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-16T072234513560 -> 2026-11-16T122925335588 | 1 changed | quiet |
| 2026-11-16 | `remote/com.kulicadvisory/aictionbot-werkbank` | 2026-11-15T155630555350 -> 2026-11-16T122920067516 | 1 changed, 5 added | quiet |
| 2026-11-16 | `remote/com.juzpost/mcp` | 2026-11-16T072217868356 -> 2026-11-16T122918880970 | 4 changed | quiet |
| 2026-11-16 | `remote/com.warminboxes/deliverability-tools` | 2026-11-10T220220810764 -> 2026-11-16T122917274854 | 1 changed | quiet |
| 2026-11-16 | `remote/ai.haggl/haggl` | 2026-11-15T115329868990 -> 2026-11-16T122914397597 | 2 changed | review |
| 2026-11-16 | `remote/dev.tanod/x402-check` | 2026-11-10T220123383686 -> 2026-11-16T122910232991 | 3 changed (every tool) | quiet |
| 2026-11-16 | `remote/dev.tanod/web` | 2026-11-03T144818859212 -> 2026-11-16T122910559500 | 40 changed (every tool) | quiet |
| 2026-11-16 | `remote/dev.tanod/text` | 2026-11-03T144819032634 -> 2026-11-16T122909609567 | 27 changed (every tool) | quiet |
| 2026-11-16 | `remote/dev.tanod/security` | 2026-11-10T220123236822 -> 2026-11-16T122909792183 | 28 changed (every tool) | quiet |
| 2026-11-16 | `remote/dev.tanod/pdf-tables` | 2026-10-28T132946416634 -> 2026-11-16T122909391083 | 1 changed | quiet |
| 2026-11-16 | `remote/dev.tanod/bank-statement` | 2026-11-10T152741033820 -> 2026-11-16T122909499982 | 1 changed | quiet |
| 2026-11-16 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-16T072312837985 -> 2026-11-16T122907350909 | 1 changed | quiet |
| 2026-11-16 | `remote/fr.dikoo/dikoo` | 2026-10-19T135226283290 -> 2026-11-16T122859401580 | 1 changed | quiet |
| 2026-11-16 | `remote/ai.arcreport/mcp` | 2026-11-07T064007844895 -> 2026-11-16T122854809460 | 4 changed | quiet |
| 2026-11-16 | `remote/ai.vaaya/mcp` | 2026-10-17T055526651536 -> 2026-11-16T122853437890 | 2 changed | quiet |
| 2026-11-16 | `remote/app.usesnippet/snippet` | 2026-11-14T114945677100 -> 2026-11-16T122851776932 | 1 changed | quiet |
| 2026-11-16 | `remote/dk.afbudsrejser/travel-search` | 2026-11-16T072216539048 -> 2026-11-16T122852344641 | 1 changed | quiet |
| 2026-11-16 | `remote/io.github.Swervie/swervie` | 2026-11-02T163305426456 -> 2026-11-16T122848793197 | 2 changed | quiet |
| 2026-11-16 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-16T072231700907 -> 2026-11-16T122833008766 | 1 changed | quiet |
| 2026-11-16 | `remote/io.github.chrismore/tuneworks` | 2026-11-12T154842092591 -> 2026-11-16T122831840637 | 101 changed (every tool) | quiet |
| 2026-11-16 | `remote/io.github.cyanheads/smithsonian-mcp-server` | 2026-11-02T163400957061 -> 2026-11-16T122829864962 | 6 changed (every tool) | quiet |
| 2026-11-16 | `remote/com.vpncomparehq/site` | 2026-11-12T154935547998 -> 2026-11-16T122830768892 | 2 changed | quiet |
| 2026-11-16 | `remote/io.github.Voopa-Corp/render-check` | 2026-11-09T170259744313 -> 2026-11-16T122829129979 | 1 changed | quiet |
| 2026-11-16 | `remote/io.github.cyanheads/treasury-fiscaldata-mcp-server` | 2026-09-23T160957657936 -> 2026-11-16T122826900243 | 7 changed (every tool) | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 65249 substantive, 40742 that changed only numbers (a catalogue counter ticking, a date), 1046 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 58079 | 19726 | 38353 | 0 |
| `a2awire.com` | 2841 | 2841 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 457 | 457 | 0 | 0 |
| `civai.co` | 364 | 364 | 0 | 0 |
| `modevc.com` | 305 | 305 | 0 | 0 |
| `revmesh2074.workers.dev` | 273 | 240 | 33 | 0 |
| `sistaminuten.se` | 244 | 6 | 0 | 238 |
| `afbudsrejser.dk` | 243 | 6 | 0 | 237 |
| `akkilahdot.fi` | 243 | 6 | 0 | 237 |
| `restplass.no` | 243 | 6 | 0 | 237 |
| `socialloop.ai` | 235 | 235 | 0 | 0 |
| 9592 other operators | 41169 | 38716 | 2356 | 97 |
