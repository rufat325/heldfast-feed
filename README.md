# MCP server tool changes

Last change observed 2026-11-20T16:06:04+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

121027 changes to a tool definition: 4852 npm releases (4606 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 116175 readings of hosted servers that found their tools changed; 4560 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-20 | `remote/io.github.zodiacs-org/zodiacs` | 2026-11-17T165019623250 -> 2026-11-20T160605307909 | 5 changed | quiet |
| 2026-11-20 | `remote/io.github.speeedy10/foxify-x402-agent-commerce-payment-preflight` | 2026-11-20T105937487687 -> 2026-11-20T160555022716 | 1 added | quiet |
| 2026-11-20 | `remote/today.thekorean/news` | 2026-11-10T130434549388 -> 2026-11-20T160531290423 | 1 added | quiet |
| 2026-11-20 | `remote/uk.co.speedi/availability` | 2026-11-18T140002558018 -> 2026-11-20T160525133031 | 1 added | quiet |
| 2026-11-20 | `remote/io.github.PettyMiggzy/oversize-escort-hub` | 2026-11-11T230941817241 -> 2026-11-20T160506338665 | 1 changed | quiet |
| 2026-11-20 | `remote/co.ibda/ibda` | 2026-11-16T163206486522 -> 2026-11-20T160445490467 | 1 changed | quiet |
| 2026-11-20 | `remote/studio.gradients/mcp` | 2026-11-20T105820230772 -> 2026-11-20T160442972324 | 1 changed | quiet |
| 2026-11-20 | `remote/fi.akkilahdot/travel-search` | 2026-11-20T105746245043 -> 2026-11-20T160355648908 | 1 changed | quiet |
| 2026-11-20 | `remote/no.restplass/travel-search` | 2026-11-20T105921121135 -> 2026-11-20T160327051480 | 1 changed | quiet |
| 2026-11-20 | `remote/ru.vedarai/mcp` | 2026-11-20T074959293731 -> 2026-11-20T160303334089 | 1 changed | quiet |
| 2026-11-20 | `remote/ru.vargov/vargov-design` | 2026-11-19T231832927046 -> 2026-11-20T160259501183 | 1 changed | quiet |
| 2026-11-20 | `remote/dev.workers.moneytools.x402-pay-precheck/pay-precheck` | 2026-11-16T163407663149 -> 2026-11-20T160248246287 | 8 changed | review |
| 2026-11-20 | `remote/io.deeplead/deeplead` | 2026-11-20T105848577265 -> 2026-11-20T160246943774 | 2 changed | quiet |
| 2026-11-20 | `remote/com.thaiprops/mcp` | 2026-09-28T142409950835 -> 2026-11-20T160236717761 | 5 changed (every tool) | quiet |
| 2026-11-20 | `remote/dk.afbudsrejser/travel-search` | 2026-11-20T105835939902 -> 2026-11-20T160231188164 | 1 changed | quiet |
| 2026-11-20 | `remote/io.github.wygogogo19/robotbase-web3` | 2026-11-20T105818770774 -> 2026-11-20T160213357582 | 1 changed, 18 removed | quiet |
| 2026-11-20 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-20T105552729560 -> 2026-11-20T160204741249 | 5 changed | quiet |
| 2026-11-20 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-20T105549511865 -> 2026-11-20T160201819788 | 1 changed | quiet |
| 2026-11-20 | `remote/com.mikefluff/mikefluff` | 2026-11-19T020435216307 -> 2026-11-20T160156445764 | 5 changed | quiet |
| 2026-11-20 | `remote/com.kineticist/mcp-server` | 2026-11-17T164820313873 -> 2026-11-20T160147892344 | 2 changed | quiet |
| 2026-11-20 | `remote/eu.gridgarden/studio` | 2026-11-13T120331776733 -> 2026-11-20T160134579259 | 2 changed | quiet |
| 2026-11-20 | `remote/com.achivx/stablescan` | 2026-11-20T105504957504 -> 2026-11-20T160119940634 | 1 changed | quiet |
| 2026-11-20 | `remote/net.stabledomains/registrar` | 2026-11-20T105503648266 -> 2026-11-20T160118567801 | 1 changed | quiet |
| 2026-11-20 | `remote/com.trendtemplate/templates` | 2026-11-20T105732156501 -> 2026-11-20T160113529306 | 1 changed | quiet |
| 2026-11-20 | `remote/com.spendcanary/free-tools` | 2026-11-16T162908847090 -> 2026-11-20T160113634552 | 1 added | quiet |
| 2026-11-20 | `remote/io.github.pugarte7/spanish-top-tech-companies` | 2026-11-19T162252540514 -> 2026-11-20T160111548439 | 2 changed | quiet |
| 2026-11-20 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-20T105447421115 -> 2026-11-20T160105905228 | 1 changed | quiet |
| 2026-11-20 | `remote/io.github.QDThead/signal-lab` | 2026-11-20T074949885291 -> 2026-11-20T160050120925 | 4 changed | quiet |
| 2026-11-20 | `remote/io.github.vstockma/x402-apis` | 2026-11-16T163308087500 -> 2026-11-20T160046946221 | 2 changed | quiet |
| 2026-11-20 | `remote/com.theagentcolosseum/agent-colosseum` | 2026-11-19T162310215663 -> 2026-11-20T160036940032 | 6 changed (every tool) | quiet |
| 2026-11-20 | `remote/io.taifoon/coordination-layer.1` | 2026-11-19T123918740175 -> 2026-11-20T160033224874 | 1 changed | quiet |
| 2026-11-20 | `remote/com.seeksat/seeksat` | 2026-11-20T074945962545 -> 2026-11-20T160029899957 | 11 changed, 1 removed (every tool) | quiet |
| 2026-11-20 | `remote/se.sistaminuten/travel-search` | 2026-11-20T105556079210 -> 2026-11-20T160028596127 | 1 changed | quiet |
| 2026-11-20 | `remote/fr.scorelook/capucine` | 2026-11-19T231820612949 -> 2026-11-20T160021635448 | 2 changed | quiet |
| 2026-11-20 | `remote/io.github.girapphe/memostem` | 2026-11-13T120004114379 -> 2026-11-20T160011766158 | 3 changed | quiet |
| 2026-11-20 | `remote/io.github.blink1217/quant-swarm.2` | 2026-11-19T020436054504 -> 2026-11-20T160004499024 | 3 changed, 1 added | quiet |
| 2026-11-20 | `remote/com.herbertandphyllis/mcp` | 2026-11-20T074937150860 -> 2026-11-20T155958819630 | 1 changed | quiet |
| 2026-11-20 | `remote/org.goodtherapy/directory` | 2026-11-09T191507514458 -> 2026-11-20T155957441243 | 3 changed (every tool) | quiet |
| 2026-11-20 | `remote/com.remoshift/jobs` | 2026-11-20T105323781236 -> 2026-11-20T155948361405 | 1 changed | quiet |
| 2026-11-20 | `remote/com.diveratlas/diver-atlas` | 2026-11-04T200751567595 -> 2026-11-20T155947530718 | 2 changed, 2 added | quiet |
| 2026-11-20 | `remote/au.com.bidit/registry` | 2026-10-23T120416468423 -> 2026-11-20T155946039819 | 1 changed | quiet |
| 2026-11-20 | `remote/io.github.TMcodingarc/bull-otc` | 2026-11-20T105509253533 -> 2026-11-20T155941366699 | 1 changed | quiet |
| 2026-11-20 | `remote/com.qhooks/mcp` | 2026-11-19T123519602269 -> 2026-11-20T155929192983 | 1 changed, 4 added | quiet |
| 2026-11-20 | `remote/coffee.pwned/pwned-coffee` | 2026-11-11T164129717391 -> 2026-11-20T155927556524 | 1 changed | quiet |
| 2026-11-20 | `remote/co.productaura/productaura.1` | 2026-11-19T162058778658 -> 2026-11-20T155915662796 | 1 changed | quiet |
| 2026-11-20 | `remote/com.predictionmarketspicks/fantasy-draft` | 2026-11-20T105246947156 -> 2026-11-20T155910386871 | 1 changed | quiet |
| 2026-11-20 | `remote/uk.co.vettedhome/property-guides` | 2026-11-05T115321629345 -> 2026-11-20T155853033878 | 1 changed | quiet |
| 2026-11-20 | `remote/com.teamcalendar/mcp` | 2026-11-18T135533761220 -> 2026-11-20T155846713688 | 2 changed, 1 added | quiet |
| 2026-11-20 | `remote/vc.unicornscreener/unicorn-screener` | 2026-10-03T120042632613 -> 2026-11-20T155836041374 | 5 changed (every tool) | quiet |
| 2026-11-20 | `remote/app.sunsetstrip/gta6` | 2026-11-20T105402671549 -> 2026-11-20T155824171897 | 1 changed | quiet |
| 2026-11-20 | `remote/io.github.wygogogo19/robotbase-mcp` | 2026-11-20T105527572845 -> 2026-11-20T155820763696 | 1 changed, 18 removed | quiet |
| 2026-11-20 | `remote/io.github.namlxuit056/social-forex` | 2026-11-19T020349662931 -> 2026-11-20T155805235353 | 4 added | quiet |
| 2026-11-20 | `remote/com.stampedsidewalks/stamped-sidewalks` | 2026-11-16T163010527050 -> 2026-11-20T155803087451 | 1 removed | quiet |
| 2026-11-20 | `remote/io.github.KevinCapri/nowcast-mcp` | 2026-11-19T123348946042 -> 2026-11-20T155801470133 | 15 changed (every tool) | quiet |
| 2026-11-20 | `remote/co.civai.nova/mcp-slack_android` | 2026-11-20T105135912954 -> 2026-11-20T155758714810 | 19 added, 1 removed | quiet |
| 2026-11-20 | `remote/co.civai.nova/mcp-browsergpt-browser-control` | 2026-11-20T105135697817 -> 2026-11-20T155758180058 | 26 added, 1 removed | quiet |
| 2026-11-20 | `remote/io.github.Embassy-of-the-Free-Mind/sourcelibrary` | 2026-11-18T135452767274 -> 2026-11-20T155748578287 | 4 changed | quiet |
| 2026-11-20 | `remote/org.citizenofnowhere.rankings/global-metro-power-rankings` | 2026-11-18T135255574619 -> 2026-11-20T155747404092 | 3 added | quiet |
| 2026-11-20 | `remote/com.radarbg/radar-tools` | 2026-11-20T105457716531 -> 2026-11-20T155746582402 | 1 changed | quiet |
| 2026-11-20 | `remote/com.neuralcosmology/neuralcosmology` | 2026-10-19T135125134247 -> 2026-11-20T155742567946 | 1 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 78840 substantive, 41060 that changed only numbers (a catalogue counter ticking, a date), 1127 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 65550 | 27196 | 38354 | 0 |
| `a2awire.com` | 3571 | 3571 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 479 | 479 | 0 | 0 |
| `modevc.com` | 436 | 436 | 0 | 0 |
| `civai.co` | 399 | 399 | 0 | 0 |
| `revmesh2074.workers.dev` | 342 | 293 | 49 | 0 |
| `sistaminuten.se` | 262 | 6 | 0 | 256 |
| `afbudsrejser.dk` | 261 | 6 | 0 | 255 |
| `akkilahdot.fi` | 261 | 6 | 0 | 255 |
| `restplass.no` | 261 | 6 | 0 | 255 |
| `socialloop.ai` | 252 | 252 | 0 | 0 |
| 10548 other operators | 46612 | 43849 | 2657 | 106 |
