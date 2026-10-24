# MCP server tool changes

Last change observed 2026-10-24T11:31:28+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

47257 changes to a tool definition: 2087 npm releases (1841 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 45170 readings of hosted servers that found their tools changed; 2455 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-24 | `remote/io.github.TRDEFI/liquidity` | 2026-10-20T104313567482 -> 2026-10-24T113129682085 | 3 added | quiet |
| 2026-10-24 | `remote/no.restplass/travel-search` | 2026-10-24T050519373197 -> 2026-10-24T113109859257 | 1 changed | quiet |
| 2026-10-24 | `remote/com.praxikon/praxikon` | 2026-10-17T060452093488 -> 2026-10-24T113108001401 | 9 changed (every tool) | quiet |
| 2026-10-24 | `remote/com.zinvyl/marketplace` | 2026-10-24T050529428221 -> 2026-10-24T113103919985 | 5 changed | quiet |
| 2026-10-24 | `remote/ro.meseriasi/meseriasi-mcp-server` | 2026-09-23T163138214181 -> 2026-10-24T113100905394 | 1 added | quiet |
| 2026-10-24 | `remote/com.meridiandispatch/travel-guides` | 2026-10-21T234606155205 -> 2026-10-24T113059947268 | 5 added | quiet |
| 2026-10-24 | `remote/io.github.agentsherpa/yieldsentinel` | 2026-09-23T162959355110 -> 2026-10-24T113059027064 | 1 changed | quiet |
| 2026-10-24 | `remote/ca.commercialgaragedoorman/business-card` | 2026-09-23T163127256747 -> 2026-10-24T113036922994 | 1 added | quiet |
| 2026-10-24 | `remote/studio.gradients/mcp` | 2026-10-24T050528486032 -> 2026-10-24T113031104830 | 1 changed | quiet |
| 2026-10-24 | `remote/dk.afbudsrejser/travel-search` | 2026-10-24T050519252592 -> 2026-10-24T113026753581 | 1 changed | quiet |
| 2026-10-24 | `remote/com.elements-live/elements-live` | 2026-10-17T055931632872 -> 2026-10-24T113024367251 | 9 changed (every tool) | quiet |
| 2026-10-24 | `remote/io.github.witanmarkets/witan` | 2026-10-23T120619621397 -> 2026-10-24T113023397754 | 32 removed | quiet |
| 2026-10-24 | `remote/io.github.EasyGerber/easygerber` | 2026-10-20T052509867571 -> 2026-10-24T113023221834 | 8 changed | quiet |
| 2026-10-24 | `remote/io.github.cyanheads/wikipedia-mcp-server` | 2026-09-23T163113650296 -> 2026-10-24T113021062233 | 5 changed | quiet |
| 2026-10-24 | `remote/co.blackcarservice.www/ride-quotes` | 2026-10-17T055925522477 -> 2026-10-24T113019378567 | 1 changed, 2 added | quiet |
| 2026-10-24 | `remote/fi.akkilahdot/travel-search` | 2026-10-24T050527349410 -> 2026-10-24T113015533409 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.privatelawattorneys/wiki-private-law` | 2026-10-20T232816103737 -> 2026-10-24T113010283074 | 3 changed | quiet |
| 2026-10-24 | `remote/io.soundchain/agents` | 2026-10-20T201143508220 -> 2026-10-24T113001784298 | 6 added | quiet |
| 2026-10-24 | `remote/com.vouchernaut/deals` | 2026-10-23T120615537462 -> 2026-10-24T112957408374 | 4 changed | quiet |
| 2026-10-24 | `remote/io.github.paulieb89/uk-legal-mcp` | 2026-09-23T163055378482 -> 2026-10-24T112954697031 | 7 changed, 2 added | quiet |
| 2026-10-24 | `remote/io.github.MohDev212/verifypulse` | 2026-10-17T055900489748 -> 2026-10-24T112951100124 | 1 changed | quiet |
| 2026-10-24 | `remote/ai.trydock/dock` | 2026-10-23T233441604959 -> 2026-10-24T112950829888 | 2 changed | quiet |
| 2026-10-24 | `remote/com.trimtabist/us-tariff-ledger` | 2026-09-23T163051216722 -> 2026-10-24T112949605899 | 4 changed | quiet |
| 2026-10-24 | `remote/io.github.agentsherpa/yieldhunter` | 2026-09-23T161042919630 -> 2026-10-24T112949055071 | 3 changed | quiet |
| 2026-10-24 | `remote/io.github.eamwhite1/xrpl-referee` | 2026-10-20T104402416108 -> 2026-10-24T112948284114 | 5 changed, 2 added | quiet |
| 2026-10-24 | `remote/io.github.sharan01x/usetested` | 2026-10-17T111201777627 -> 2026-10-24T112945968048 | 1 added | review |
| 2026-10-24 | `remote/io.github.philpof102-svg/tokenizedblock` | 2026-10-18T190031018595 -> 2026-10-24T112940947537 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.paulieb89/uk-due-diligence-mcp` | 2026-09-23T162919664456 -> 2026-10-24T112943996800 | 2 changed | quiet |
| 2026-10-24 | `remote/ai.usedby/usedby` | 2026-10-23T233436605105 -> 2026-10-24T112940669381 | 2 changed | quiet |
| 2026-10-24 | `remote/io.taifoon/coordination-layer.1` | 2026-10-23T233436230376 -> 2026-10-24T112937502497 | 1 changed | review |
| 2026-10-24 | `remote/com.test-well/testwell` | 2026-10-17T055620347711 -> 2026-10-24T112937882884 | 2 changed | quiet |
| 2026-10-24 | `remote/se.sistaminuten/travel-search` | 2026-10-24T050517732294 -> 2026-10-24T112934143980 | 1 changed | quiet |
| 2026-10-24 | `remote/com.quantum-expectations/quantum-expectations` | 2026-09-23T161033865408 -> 2026-10-24T112931596285 | 12 changed | quiet |
| 2026-10-24 | `remote/com.metaltakip/digest` | 2026-09-23T161030436280 -> 2026-10-24T112926090428 | 1 changed | quiet |
| 2026-10-24 | `remote/app.openkrill/taste` | 2026-10-17T060330494579 -> 2026-10-24T112924708522 | 6 changed, 1 added | quiet |
| 2026-10-24 | `remote/io.github.nirholas/threews-grok` | 2026-10-17T055835885148 -> 2026-10-24T112922776695 | 9 changed, 1 added | quiet |
| 2026-10-24 | `remote/io.huntertech/vendor-insights` | 2026-09-23T161027322496 -> 2026-10-24T112921355599 | 3 changed, 1 added (every tool) | quiet |
| 2026-10-24 | `remote/com.getcleed/linkedin-buying-signals` | 2026-09-28T142321666105 -> 2026-10-24T112919307050 | 1 changed, 1 added | quiet |
| 2026-10-24 | `remote/io.github.eamwhite1/agent-trust` | 2026-10-20T104418355031 -> 2026-10-24T112918150742 | 5 changed, 2 added | quiet |
| 2026-10-24 | `remote/fr.synergieloc/immobilier` | 2026-10-19T135703094744 -> 2026-10-24T112918427299 | 1 changed, 1 added | quiet |
| 2026-10-24 | `remote/io.github.rezearcher/tech-risk` | 2026-10-23T200822463269 -> 2026-10-24T112914448322 | 2 changed | quiet |
| 2026-10-24 | `remote/com.cyclecalcs/astronomy` | 2026-10-06T110145156844 -> 2026-10-24T112912247111 | 11 changed (every tool) | quiet |
| 2026-10-24 | `remote/com.cadprops/cadprops` | 2026-10-22T140850770972 -> 2026-10-24T112909603757 | 1 changed | quiet |
| 2026-10-24 | `remote/com.blitzreels/blitzreels` | 2026-10-18T224010926553 -> 2026-10-24T112909031104 | 7 changed, 1 added | quiet |
| 2026-10-24 | `remote/com.swarmmemo/bulletin.1` | 2026-10-24T050523105948 -> 2026-10-24T112908346500 | 26 changed | quiet |
| 2026-10-24 | `remote/com.swarmmemo/bulletin` | 2026-10-24T050522218140 -> 2026-10-24T112908038284 | 7 changed | quiet |
| 2026-10-24 | `remote/com.adadiamonds/ada-diamonds` | 2026-10-17T055553200632 -> 2026-10-24T112903346890 | 7 changed | quiet |
| 2026-10-24 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-24T050513110181 -> 2026-10-24T112900309318 | 10 changed | quiet |
| 2026-10-24 | `remote/io.github.Ninjabeam20/sportiq-mcp` | 2026-09-24T202528449028 -> 2026-10-24T112901867176 | 22 changed, 2 added | quiet |
| 2026-10-24 | `remote/ai.whatsupin/events` | 2026-10-23T200838519382 -> 2026-10-24T112855065837 | 5 changed | quiet |
| 2026-10-24 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-24T050521233172 -> 2026-10-24T112848433877 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.sitegpt/sitegpt-docs` | 2026-09-23T163006977455 -> 2026-10-24T112848535694 | 3 changed (every tool) | quiet |
| 2026-10-24 | `remote/app.openkrill/buyersignals` | 2026-10-17T060302914007 -> 2026-10-24T112845271655 | 5 changed, 1 added | quiet |
| 2026-10-24 | `remote/net.signalband/decision-engines` | 2026-10-17T060301867192 -> 2026-10-24T112844443514 | 1 changed | review |
| 2026-10-24 | `remote/io.github.SiliconAnalysts/silicon-analysts` | 2026-10-17T055802111996 -> 2026-10-24T112841300806 | 1 changed | quiet |
| 2026-10-24 | `remote/ai.shorti/shorti` | 2026-10-23T200837223920 -> 2026-10-24T112839805721 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.cyanheads/secedgar-mcp-server` | 2026-10-19T052416148348 -> 2026-10-24T112829723795 | 13 changed | quiet |
| 2026-10-24 | `remote/app.seatsherpa/rides` | 2026-10-23T120424475980 -> 2026-10-24T112829794553 | 3 changed | quiet |
| 2026-10-24 | `remote/com.0xpi.sdsentry/sds-lookup` | 2026-10-17T060251244143 -> 2026-10-24T112827107542 | 3 added | quiet |
| 2026-10-24 | `remote/io.github.chrismore/tuneworks` | 2026-10-19T135348686915 -> 2026-10-24T112825512493 | 100 changed (every tool) | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 29278 substantive, 17373 that changed only numbers (a catalogue counter ticking, a date), 606 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 25144 | 8777 | 16367 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 657 | 657 | 0 | 0 |
| `caseyjhand.com` | 194 | 194 | 0 | 0 |
| `sistaminuten.se` | 144 | 4 | 0 | 140 |
| `afbudsrejser.dk` | 143 | 4 | 0 | 139 |
| `akkilahdot.fi` | 143 | 4 | 0 | 139 |
| `restplass.no` | 143 | 4 | 0 | 139 |
| `socialloop.ai` | 139 | 139 | 0 | 0 |
| `remoshift.com` | 114 | 8 | 106 | 0 |
| `openkrill.app` | 111 | 111 | 0 | 0 |
| `fundinglandscape.com` | 109 | 71 | 38 | 0 |
| 5473 other operators | 17875 | 16964 | 862 | 49 |
