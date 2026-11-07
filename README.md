# MCP server tool changes

Last change observed 2026-11-07T13:40:05+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

82410 changes to a tool definition: 3503 npm releases (3257 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 78907 readings of hosted servers that found their tools changed; 3538 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-07 | `remote/io.github.TRDEFI/liquidity` | 2026-10-31T130331146475 -> 2026-11-07T134006993933 | 1 changed | quiet |
| 2026-11-07 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-11-04T151018392204 -> 2026-11-07T133955945065 | 44 changed (every tool) | quiet |
| 2026-11-07 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-11-04T150823754916 -> 2026-11-07T133940474166 | 44 changed (every tool) | quiet |
| 2026-11-07 | `remote/io.github.matt-moon/sonatina` | 2026-11-02T163439326968 -> 2026-11-07T133925921472 | 1 changed | quiet |
| 2026-11-07 | `remote/se.sistaminuten/travel-search` | 2026-11-07T064005711096 -> 2026-11-07T133923666911 | 1 changed | quiet |
| 2026-11-07 | `remote/com.starcovery/mcp` | 2026-10-28T133505083144 -> 2026-11-07T133924375910 | 2 changed, 36 added | review |
| 2026-11-07 | `remote/io.github.bryantrudy24/saax-protocol` | 2026-10-17T060454177423 -> 2026-11-07T133912887551 | 3 changed, 2 added | quiet |
| 2026-11-07 | `remote/ai.myporta/myporta` | 2026-10-18T113457787732 -> 2026-11-07T133910935446 | 3 changed | quiet |
| 2026-11-07 | `remote/no.restplass/travel-search` | 2026-11-07T064009924037 -> 2026-11-07T133909417311 | 1 changed | quiet |
| 2026-11-07 | `remote/com.reportgem/global-research` | 2026-10-26T133804478733 -> 2026-11-07T133909278367 | 5 changed (every tool) | quiet |
| 2026-11-07 | `remote/com.mailbypony/mail-by-pony` | 2026-11-03T024313696422 -> 2026-11-07T133905797633 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.openaccountants/openaccountants` | 2026-11-06T214842732975 -> 2026-11-07T133858897591 | 1 changed, 1 added | review |
| 2026-11-07 | `remote/ai.neuralpartners/sasha` | 2026-10-26T133758963278 -> 2026-11-07T133855080579 | 3 changed (every tool) | quiet |
| 2026-11-07 | `remote/com.digitaltableteur/mcp` | 2026-10-29T104457722013 -> 2026-11-07T133850520944 | 5 changed | quiet |
| 2026-11-07 | `remote/com.meridiandispatch/travel-guides` | 2026-11-01T135327971760 -> 2026-11-07T133847862961 | 4 changed | quiet |
| 2026-11-07 | `remote/com.kiddinglab/kiddinglab` | 2026-11-02T163603033068 -> 2026-11-07T133840938895 | 3 changed | quiet |
| 2026-11-07 | `remote/io.github.cryptoduke01/gloam` | 2026-11-03T195607584125 -> 2026-11-07T133828568449 | 1 changed | quiet |
| 2026-11-07 | `remote/com.droneclearthailand/droneclear-thailand` | 2026-10-26T133738412414 -> 2026-11-07T133810489463 | 2 changed (every tool) | quiet |
| 2026-11-07 | `remote/io.deeplead/deeplead` | 2026-11-03T145015056879 -> 2026-11-07T133807856096 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.ge3m0r/cola-insight` | 2026-10-19T135830070060 -> 2026-11-07T133802825697 | 1 added | quiet |
| 2026-11-07 | `remote/com.zacharyr0th/public` | 2026-09-23T163000675450 -> 2026-11-07T133749371996 | 1 added | quiet |
| 2026-11-07 | `remote/ai.zairalabs/guide` | 2026-10-17T060004063378 -> 2026-11-07T133749588955 | 4 changed | quiet |
| 2026-11-07 | `remote/com.usepiku/piku` | 2026-11-06T144703852032 -> 2026-11-07T133753199876 | 4 changed, 1 added | quiet |
| 2026-11-07 | `remote/xyz.urbangametheory/urban-game-theory` | 2026-11-03T122653957679 -> 2026-11-07T133747572225 | 5 changed | quiet |
| 2026-11-07 | `remote/com.synthexforge.x402/paid-agent-services` | 2026-11-07T064028758602 -> 2026-11-07T133743428366 | 5 added | quiet |
| 2026-11-07 | `remote/dk.afbudsrejser/travel-search` | 2026-11-07T064007919610 -> 2026-11-07T133742429735 | 1 changed | quiet |
| 2026-11-07 | `remote/com.versyka/versyka` | 2026-10-19T155757073669 -> 2026-11-07T133737965082 | 2 changed | quiet |
| 2026-11-07 | `remote/io.github.AnxForever/stylekit-mcp` | 2026-10-26T133605213345 -> 2026-11-07T133736721559 | 5 changed, 5 removed (every tool) | quiet |
| 2026-11-07 | `remote/ar.com.sofiaferro/portfolio` | 2026-09-23T162953922791 -> 2026-11-07T133730431491 | 1 changed | quiet |
| 2026-11-07 | `remote/ai.robowrite/mcp` | 2026-10-27T054122865401 -> 2026-11-07T133727016803 | 1 changed | quiet |
| 2026-11-07 | `remote/dev.primitive/email` | 2026-11-03T145034137863 -> 2026-11-07T133723538416 | 3 changed | quiet |
| 2026-11-07 | `remote/co.truerent/rental-review` | 2026-10-17T055518527962 -> 2026-11-07T133719242596 | 1 changed, 2 added | quiet |
| 2026-11-07 | `remote/com.torqueindex/truck-reference` | 2026-11-02T163242927337 -> 2026-11-07T133712568874 | 6 added | quiet |
| 2026-11-07 | `remote/studio.gradients/mcp` | 2026-11-07T064020532078 -> 2026-11-07T133707036689 | 1 changed | quiet |
| 2026-11-07 | `remote/net.tnapplianceexchange/repair` | 2026-10-19T135333574540 -> 2026-11-07T133700500565 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.cooyun/etuki-finops-mcp` | 2026-11-06T144902549589 -> 2026-11-07T133701095451 | 4 changed, 3 removed (every tool) | quiet |
| 2026-11-07 | `remote/dev.tlly/tlly` | 2026-11-02T163230979737 -> 2026-11-07T133700800565 | 5 changed | quiet |
| 2026-11-07 | `remote/fi.akkilahdot/travel-search` | 2026-11-07T064018482494 -> 2026-11-07T133644603055 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.privatelawattorneys/wiki-private-law` | 2026-11-07T064019020643 -> 2026-11-07T133635099731 | 3 changed | quiet |
| 2026-11-07 | `remote/io.github.whisper-sec/whisper` | 2026-11-05T115505604251 -> 2026-11-07T133633935476 | 2 changed | quiet |
| 2026-11-07 | `remote/io.whatic/datasheets` | 2026-09-23T162928693794 -> 2026-11-07T133630910060 | 2 changed | quiet |
| 2026-11-07 | `remote/com.warmthengine/observatory` | 2026-10-19T135510074033 -> 2026-11-07T133622922168 | 3 changed | quiet |
| 2026-11-07 | `remote/global.uain/network` | 2026-11-06T144713074893 -> 2026-11-07T133615674913 | 1 added | quiet |
| 2026-11-07 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-07T064019246482 -> 2026-11-07T133614030242 | 3 changed | quiet |
| 2026-11-07 | `remote/ru.vedarai/mcp` | 2026-11-01T135300529481 -> 2026-11-07T133610054157 | 6 changed | quiet |
| 2026-11-07 | `remote/io.github.toolweather/upstream` | 2026-10-19T135449220127 -> 2026-11-07T133602693571 | 3 changed | quiet |
| 2026-11-07 | `remote/com.trip1/mcp` | 2026-10-17T055850827256 -> 2026-11-07T133554091981 | 1 changed | quiet |
| 2026-11-07 | `remote/app.openkrill/settlements` | 2026-10-26T133633815453 -> 2026-11-07T133552084008 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.yayabough/tolca` | 2026-10-30T210629663404 -> 2026-11-07T133543000534 | 1 changed, 1 added | quiet |
| 2026-11-07 | `remote/ca.tonbot.tolca/tolca` | 2026-11-06T162146262102 -> 2026-11-07T133542844380 | 7 changed | quiet |
| 2026-11-07 | `remote/com.tickerinside/tickerinside-mcp` | 2026-10-17T055836198707 -> 2026-11-07T133535816234 | 1 changed | quiet |
| 2026-11-07 | `remote/com.lvl2player/sandbox` | 2026-11-05T222202362922 -> 2026-11-07T133534245877 | 4 changed | quiet |
| 2026-11-07 | `remote/ai.satohub/onchain-agents` | 2026-11-03T195637420738 -> 2026-11-07T133533818157 | 1 changed | quiet |
| 2026-11-07 | `remote/com.textforagents/delivery-capacity-landing-governor` | 2026-10-26T133356343139 -> 2026-11-07T133527465115 | 1 changed | quiet |
| 2026-11-07 | `remote/io.theagentforge/forge` | 2026-11-05T115520374501 -> 2026-11-07T133509167515 | 2 changed | quiet |
| 2026-11-07 | `remote/com.readqurantoday/quran` | 2026-10-26T133554134886 -> 2026-11-07T133504993973 | 1 changed, 1 added | quiet |
| 2026-11-07 | `remote/com.vedutum/vedutum` | 2026-11-05T115512650460 -> 2026-11-07T133504629703 | 19 changed (every tool) | quiet |
| 2026-11-07 | `remote/com.usmortgagecalc/mortgage` | 2026-09-23T160855455882 -> 2026-11-07T133501230091 | 11 changed (every tool) | quiet |
| 2026-11-07 | `remote/cn.tandiu/data` | 2026-11-05T115506254268 -> 2026-11-07T133459487503 | 1 changed | quiet |
| 2026-11-07 | `remote/com.supersetapp/public` | 2026-11-02T163930311949 -> 2026-11-07T133456379640 | 3 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 50454 substantive, 31079 that changed only numbers (a catalogue counter ticking, a date), 877 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 45119 | 15889 | 29230 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1723 | 1723 | 0 | 0 |
| `caseyjhand.com` | 354 | 354 | 0 | 0 |
| `sistaminuten.se` | 206 | 6 | 0 | 200 |
| `afbudsrejser.dk` | 205 | 6 | 0 | 199 |
| `akkilahdot.fi` | 205 | 6 | 0 | 199 |
| `restplass.no` | 205 | 6 | 0 | 199 |
| `socialloop.ai` | 197 | 197 | 0 | 0 |
| `revmesh2074.workers.dev` | 188 | 165 | 23 | 0 |
| `modevc.com` | 174 | 174 | 0 | 0 |
| `civai.co` | 165 | 165 | 0 | 0 |
| 7916 other operators | 31328 | 29422 | 1826 | 80 |
