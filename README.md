# MCP server tool changes

Last change observed 2026-11-04T00:59:54+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

74236 changes to a tool definition: 3094 npm releases (2848 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 71142 readings of hosted servers that found their tools changed; 3292 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-04 | `remote/io.github.Veniwol-Li-Lambd/lilambd-data` | 2026-11-03T122805107100 -> 2026-11-04T010006333998 | 1 changed, 1 added | quiet |
| 2026-11-04 | `remote/io.github.liad142/yedapo` | 2026-11-03T195617748647 -> 2026-11-04T005954659252 | 2 changed (every tool) | quiet |
| 2026-11-04 | `remote/no.restplass/travel-search` | 2026-11-03T195614528502 -> 2026-11-04T005952989329 | 1 changed | quiet |
| 2026-11-04 | `remote/dk.afbudsrejser/travel-search` | 2026-11-03T195603488911 -> 2026-11-04T005945322215 | 1 changed | quiet |
| 2026-11-04 | `remote/com.veritaset/mcp` | 2026-11-03T144938181090 -> 2026-11-04T005942617107 | 1 changed | quiet |
| 2026-11-04 | `remote/se.sistaminuten/travel-search` | 2026-11-03T195707214865 -> 2026-11-04T005934227684 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-03T195545028663 -> 2026-11-04T005933984663 | 4 changed, 2 added | review |
| 2026-11-04 | `remote/com.proz/remoto` | 2026-11-02T163431969842 -> 2026-11-04T005933243461 | 3 changed | quiet |
| 2026-11-04 | `remote/com.cyclecalcs/astronomy` | 2026-11-02T163407281203 -> 2026-11-04T005928614385 | 1 changed | quiet |
| 2026-11-04 | `remote/ai.rokha/rokha` | 2026-11-03T024209219076 -> 2026-11-04T005928180041 | 10 changed, 2 added | review |
| 2026-11-04 | `remote/io.github.opennodes-io/opennodes` | 2026-11-03T195534323813 -> 2026-11-04T005927606175 | 1 changed | quiet |
| 2026-11-04 | `remote/com.coveragecat/insurance` | 2026-11-03T195701745402 -> 2026-11-04T005927500709 | 2 changed, 1 added | quiet |
| 2026-11-04 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-11-03T195658538747 -> 2026-11-04T005926232849 | 3 added | quiet |
| 2026-11-04 | `remote/io.github.Fizzl13/presign-guard` | 2026-11-03T195528128148 -> 2026-11-04T005923467178 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.soyeladice-svg/bursia-utils` | 2026-11-03T195653210274 -> 2026-11-04T005919068579 | 2 changed (every tool) | quiet |
| 2026-11-04 | `remote/io.github.SKalinin909/tradingcalc` | 2026-11-03T024300254535 -> 2026-11-04T005917032262 | 2 changed, 1 added | quiet |
| 2026-11-04 | `remote/co.civai.nova/mcp-bgpt-polymarket` | 2026-11-03T195519920775 -> 2026-11-04T005917668910 | 18 added, 1 removed | quiet |
| 2026-11-04 | `remote/co.civai.nova/mcp-bgpt-giglogistics` | 2026-11-03T195519812218 -> 2026-11-04T005917602917 | 1 added, 1 removed | quiet |
| 2026-11-04 | `remote/co.civai.nova/mcp-apple_developer` | 2026-11-03T195519613655 -> 2026-11-04T005917265090 | 55 added, 1 removed | quiet |
| 2026-11-04 | `remote/co.civai.nova/mcp-apple_ads` | 2026-11-03T195519363158 -> 2026-11-04T005917222492 | 25 added, 1 removed | quiet |
| 2026-11-04 | `remote/co.civai.nova/mcp-android_developer` | 2026-11-03T195519068071 -> 2026-11-04T005917047493 | 38 added, 1 removed | quiet |
| 2026-11-04 | `remote/com.thenetworkery/network-tools` | 2026-11-02T163233671934 -> 2026-11-04T005914801190 | 25 changed, 3 added, 5 removed (every tool) | quiet |
| 2026-11-04 | `remote/com.thefomite/fomite` | 2026-11-03T024255474127 -> 2026-11-04T005914205697 | 1 changed | quiet |
| 2026-11-04 | `remote/com.turbonotify/whatsapp` | 2026-11-03T122716721499 -> 2026-11-04T005910968241 | 1 changed | quiet |
| 2026-11-04 | `remote/com.theprotoclinical/commerce` | 2026-11-02T163733438671 -> 2026-11-04T005909537946 | 9 changed | quiet |
| 2026-11-04 | `remote/com.yomachichi/shop` | 2026-11-02T163949456572 -> 2026-11-04T005907982491 | 9 changed | quiet |
| 2026-11-04 | `remote/dev.x402check/mcp` | 2026-11-03T024248407181 -> 2026-11-04T005907235616 | 6 changed (every tool) | quiet |
| 2026-11-04 | `remote/dev.silvertongue/silvertongue` | 2026-11-02T162910645460 -> 2026-11-04T005907751231 | 4 changed (every tool) | quiet |
| 2026-11-04 | `remote/io.github.yzlee/opcmenu` | 2026-11-02T162838427808 -> 2026-11-04T005909008378 | 2 changed | quiet |
| 2026-11-04 | `remote/com.ticketfairy/ticket-fairy-public-events` | 2026-11-02T163932292723 -> 2026-11-04T005905173093 | 1 changed | quiet |
| 2026-11-04 | `remote/com.idosgames/platform` | 2026-11-03T195641138418 -> 2026-11-04T005907966987 | 1 changed, 1 added | quiet |
| 2026-11-04 | `remote/studio.gradients/mcp` | 2026-11-03T195817232434 -> 2026-11-04T005903971358 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.medprice-ai/mcp-medprice-ai` | 2026-11-02T162818757743 -> 2026-11-04T005904121316 | 5 changed, 1 added | quiet |
| 2026-11-04 | `remote/com.roomeinc.www/quotes` | 2026-11-02T163923012152 -> 2026-11-04T005903509876 | 6 changed (every tool) | quiet |
| 2026-11-04 | `remote/fi.akkilahdot/travel-search` | 2026-11-03T195816343060 -> 2026-11-04T005901830436 | 1 changed | quiet |
| 2026-11-04 | `remote/com.lvl2player/sandbox` | 2026-11-02T163055859284 -> 2026-11-04T005909240608 | 2 changed, 1 added | quiet |
| 2026-11-04 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-03T024307204625 -> 2026-11-04T005902144022 | 2 changed | quiet |
| 2026-11-04 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-03T024306356643 -> 2026-11-04T005901139962 | 1 changed | quiet |
| 2026-11-04 | `remote/link.rentgpu/gpu-market` | 2026-11-02T065439129309 -> 2026-11-04T005901729657 | 3 changed | quiet |
| 2026-11-04 | `remote/io.github.TotesMagotes/mcp-server-auth` | 2026-11-03T195453572228 -> 2026-11-04T005859480103 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-03T195814709939 -> 2026-11-04T005859599314 | 3 changed | quiet |
| 2026-11-04 | `remote/es.proceres/proceres` | 2026-11-03T024242065921 -> 2026-11-04T005857687118 | 13 changed, 2 added | quiet |
| 2026-11-04 | `remote/rent.beep/car-rental` | 2026-11-03T024141469654 -> 2026-11-04T005857837906 | 3 changed | quiet |
| 2026-11-04 | `remote/io.github.brawlaphant/vealth` | 2026-11-02T065430799510 -> 2026-11-04T005857043678 | 2 changed | quiet |
| 2026-11-04 | `remote/dev.upfork/upfork` | 2026-11-03T195506618316 -> 2026-11-04T005856735113 | 1 changed | quiet |
| 2026-11-04 | `remote/net.tichat.tradehub/tradehub.1` | 2026-11-03T195504461667 -> 2026-11-04T005854806164 | 34 changed (every tool) | quiet |
| 2026-11-04 | `remote/io.github.i02202/automan` | 2026-11-03T144137799040 -> 2026-11-04T005855108570 | 6 changed | review |
| 2026-11-04 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-03T195803582120 -> 2026-11-04T005853783170 | 2 changed | quiet |
| 2026-11-04 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-03T122625952531 -> 2026-11-04T005853563942 | 1 changed | quiet |
| 2026-11-04 | `remote/com.thejohnsislander/the-johns-islander` | 2026-11-03T144808843495 -> 2026-11-04T005852123442 | 2 added | quiet |
| 2026-11-04 | `remote/com.6ix/mcp` | 2026-11-03T195445084739 -> 2026-11-04T005852399167 | 1 changed | quiet |
| 2026-11-04 | `remote/ai.maxcv/resume` | 2026-11-02T162613196497 -> 2026-11-04T005853346541 | 1 changed | quiet |
| 2026-11-04 | `remote/com.swarmmemo/bulletin.1` | 2026-11-03T144813122635 -> 2026-11-04T005850914740 | 2 changed | quiet |
| 2026-11-04 | `remote/co.civai.nova/mcp-bgpt-tweet-downloader` | 2026-11-03T195624485950 -> 2026-11-04T005850066872 | 1 added, 1 removed | quiet |
| 2026-11-04 | `remote/co.civai.nova/mcp-bgpt-jiji-recon` | 2026-11-03T195624244849 -> 2026-11-04T005849812564 | 23 added, 1 removed | quiet |
| 2026-11-04 | `remote/co.civai.nova/mcp-bgpt-clannit` | 2026-11-03T195624167519 -> 2026-11-04T005849600181 | 11 added, 1 removed | quiet |
| 2026-11-04 | `remote/wiki.swarmindex/boards` | 2026-11-03T195455693508 -> 2026-11-04T005849567746 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.JacobiusMakes/stienhardt-store` | 2026-11-02T163424349112 -> 2026-11-04T005849059469 | 9 changed | quiet |
| 2026-11-04 | `remote/co.civai.nova/mcp-bgpt-chowdeck` | 2026-11-03T195623765436 -> 2026-11-04T005849609653 | 24 added, 1 removed | quiet |
| 2026-11-04 | `remote/co.civai.nova/mcp-bgpt-cardpeer` | 2026-11-03T195623686343 -> 2026-11-04T005849555658 | 6 added, 1 removed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 46246 substantive, 27177 that changed only numbers (a catalogue counter ticking, a date), 813 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 41415 | 15875 | 25540 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1247 | 1247 | 0 | 0 |
| `caseyjhand.com` | 329 | 329 | 0 | 0 |
| `sistaminuten.se` | 192 | 6 | 0 | 186 |
| `afbudsrejser.dk` | 191 | 6 | 0 | 185 |
| `akkilahdot.fi` | 191 | 6 | 0 | 185 |
| `restplass.no` | 191 | 6 | 0 | 185 |
| `socialloop.ai` | 184 | 184 | 0 | 0 |
| `remoshift.com` | 161 | 12 | 149 | 0 |
| `fundinglandscape.com` | 146 | 89 | 57 | 0 |
| `revmesh2074.workers.dev` | 146 | 128 | 18 | 0 |
| 7327 other operators | 27502 | 26017 | 1413 | 72 |
