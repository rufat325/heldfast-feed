# MCP server tool changes

Last change observed 2026-10-29T21:29:19+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

61780 changes to a tool definition: 2574 npm releases (2328 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 59206 readings of hosted servers that found their tools changed; 2982 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-29 | `remote/io.github.travisseamon-a11y/xemstudio` | 2026-10-29T063230197751 -> 2026-10-29T212919867526 | 3 changed | quiet |
| 2026-10-29 | `remote/io.taifoon/coordination-layer.1` | 2026-10-29T153804563745 -> 2026-10-29T212919034822 | 1 changed | review |
| 2026-10-29 | `remote/se.sistaminuten/travel-search` | 2026-10-29T153805366003 -> 2026-10-29T212918128991 | 1 changed | quiet |
| 2026-10-29 | `remote/io.github.danbuildss/musecourt` | 2026-10-29T104512487207 -> 2026-10-29T212915130704 | 26 changed | quiet |
| 2026-10-29 | `remote/no.restplass/travel-search` | 2026-10-29T153816924107 -> 2026-10-29T212909735480 | 1 changed | quiet |
| 2026-10-29 | `remote/dev.pressmark/pressmark` | 2026-10-29T153816947854 -> 2026-10-29T212908496589 | 3 changed | quiet |
| 2026-10-29 | `remote/com.patchmcp/patch` | 2026-10-28T212431404782 -> 2026-10-29T212907570780 | 7 changed, 50 added (every tool) | quiet |
| 2026-10-29 | `remote/io.github.aanari/loacare-healthcare-pricing` | 2026-10-28T212430120263 -> 2026-10-29T212907307698 | 4 changed | quiet |
| 2026-10-29 | `remote/com.meridiandispatch/travel-guides` | 2026-10-29T133220159396 -> 2026-10-29T212906401188 | 2 changed | quiet |
| 2026-10-29 | `remote/studio.gradients/mcp` | 2026-10-29T153754417451 -> 2026-10-29T212905022038 | 1 changed | quiet |
| 2026-10-29 | `remote/io.github.SoapyRED/freightutils` | 2026-10-29T133853771947 -> 2026-10-29T212905614919 | 25 changed (every tool) | quiet |
| 2026-10-29 | `remote/io.github.SKalinin909/tradingcalc` | 2026-10-29T104401051641 -> 2026-10-29T212903655211 | 1 added | quiet |
| 2026-10-29 | `remote/ai.haggl/haggl` | 2026-10-29T133212881494 -> 2026-10-29T212904992923 | 11 changed, 1 removed | quiet |
| 2026-10-29 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-10-29T063229088636 -> 2026-10-29T212903120756 | 4 changed | quiet |
| 2026-10-29 | `remote/fi.akkilahdot/travel-search` | 2026-10-29T153752527337 -> 2026-10-29T212903711720 | 1 changed | quiet |
| 2026-10-29 | `remote/io.github.CodeWever/wever-labs-products` | 2026-10-29T063226226813 -> 2026-10-29T212900937272 | 3 changed, 4 added | review |
| 2026-10-29 | `remote/dk.afbudsrejser/travel-search` | 2026-10-29T153813796807 -> 2026-10-29T212901565037 | 1 changed | quiet |
| 2026-10-29 | `remote/ru.vedarai/mcp` | 2026-10-29T153750710280 -> 2026-10-29T212900548899 | 2 changed, 1 added | quiet |
| 2026-10-29 | `remote/io.github.majidkabir/sootcase` | 2026-10-28T133234180262 -> 2026-10-29T212856589661 | 5 changed | quiet |
| 2026-10-29 | `remote/io.github.CustomBlinds/cb-shop` | 2026-10-28T212354177573 -> 2026-10-29T212855129581 | 1 changed | quiet |
| 2026-10-29 | `remote/com.jennipro.shop/shop-local` | 2026-10-27T054044313120 -> 2026-10-29T212854691100 | 1 changed | quiet |
| 2026-10-29 | `remote/ai.wem3/wem-price-compare` | 2026-10-27T112456191574 -> 2026-10-29T212856845911 | 4 changed | quiet |
| 2026-10-29 | `remote/xyz.t0ll/toll` | 2026-10-28T153158541172 -> 2026-10-29T212852833116 | 1 added | quiet |
| 2026-10-29 | `remote/io.github.LKennedyShare/supplier-payment-verifier` | 2026-10-29T133624706199 -> 2026-10-29T212852122773 | 8 changed (every tool) | review |
| 2026-10-29 | `remote/com.swarmmemo/bulletin.1` | 2026-10-29T153741857851 -> 2026-10-29T212853719392 | 5 changed | quiet |
| 2026-10-29 | `remote/com.swarmmemo/bulletin` | 2026-10-29T153741534485 -> 2026-10-29T212853395871 | 3 changed | quiet |
| 2026-10-29 | `remote/io.slopit/slopit` | 2026-10-29T153740399286 -> 2026-10-29T212852087430 | 2 added | quiet |
| 2026-10-29 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-29T153739750530 -> 2026-10-29T212851571780 | 1 changed | quiet |
| 2026-10-29 | `remote/com.stayotter/stay-otter` | 2026-10-28T212406989463 -> 2026-10-29T212851609352 | 5 changed | quiet |
| 2026-10-29 | `remote/pl.przetargowyjanusz/tenders` | 2026-10-29T153735593930 -> 2026-10-29T212850714628 | 10 changed | quiet |
| 2026-10-29 | `remote/es.proceres/proceres` | 2026-10-29T153732433620 -> 2026-10-29T212849706021 | 8 changed | quiet |
| 2026-10-29 | `remote/io.github.jakegallen/poascan` | 2026-10-29T153730383825 -> 2026-10-29T212848149349 | 5 changed | quiet |
| 2026-10-29 | `remote/com.remoshift/jobs` | 2026-10-29T153736503145 -> 2026-10-29T212847214323 | 1 changed | quiet |
| 2026-10-29 | `remote/fr.synergieloc/immobilier` | 2026-10-29T104419465667 -> 2026-10-29T212848411964 | 40 added | quiet |
| 2026-10-29 | `remote/com.slidler/carousel` | 2026-10-27T124020812187 -> 2026-10-29T212846101766 | 1 changed | quiet |
| 2026-10-29 | `remote/re.rundata/temps-reel` | 2026-10-29T132927250903 -> 2026-10-29T212843453062 | 1 changed | quiet |
| 2026-10-29 | `remote/com.odilelabs/odile` | 2026-10-29T133337945486 -> 2026-10-29T212842958469 | 3 changed | quiet |
| 2026-10-29 | `remote/co.civai.nova/leads-discovery-agent` | 2026-10-29T104122826311 -> 2026-10-29T212842646136 | 3 added | quiet |
| 2026-10-29 | `remote/io.github.cyanheads/nasa-power-mcp-server` | 2026-10-29T104112957548 -> 2026-10-29T212841943548 | 4 changed | quiet |
| 2026-10-29 | `remote/com.myanimetracker/myanimetracker-account` | 2026-10-29T104111392199 -> 2026-10-29T212842426375 | 2 added | quiet |
| 2026-10-29 | `remote/com.multicinesortega/cartelera` | 2026-10-29T063215616574 -> 2026-10-29T212843102014 | 1 changed | quiet |
| 2026-10-29 | `remote/me.miow/miow` | 2026-10-27T210124534085 -> 2026-10-29T212841078213 | 3 changed | quiet |
| 2026-10-29 | `remote/com.straelo/relay` | 2026-10-29T153757577175 -> 2026-10-29T212840297608 | 1 removed | quiet |
| 2026-10-29 | `remote/tickets.xp/xp-tickets` | 2026-10-29T063204731770 -> 2026-10-29T212839490806 | 18 changed | quiet |
| 2026-10-29 | `remote/io.github.worklittle/jobs` | 2026-10-29T104038266500 -> 2026-10-29T212839158778 | 1 changed | quiet |
| 2026-10-29 | `remote/fun.pumpdata/pumpdata` | 2026-10-29T063216199953 -> 2026-10-29T212839318827 | 1 changed | quiet |
| 2026-10-29 | `remote/com.wildernesstimes/checklists` | 2026-10-29T104049531342 -> 2026-10-29T212838892808 | 7 changed (every tool) | quiet |
| 2026-10-29 | `remote/io.github.Fizzl13/x402-doctor` | 2026-10-29T104517948739 -> 2026-10-29T212838348413 | 1 changed | quiet |
| 2026-10-29 | `remote/com.vendooly/vendooly` | 2026-10-29T104043430250 -> 2026-10-29T212838634599 | 1 changed, 1 removed | quiet |
| 2026-10-29 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-10-29T153735614849 -> 2026-10-29T212836115327 | 1 changed | quiet |
| 2026-10-29 | `remote/com.calmido/phone-number-lookup` | 2026-10-29T133456012167 -> 2026-10-29T212835320105 | 2 changed | quiet |
| 2026-10-29 | `remote/ai.switchapp/switch` | 2026-10-29T153722346664 -> 2026-10-29T212835122259 | 1 changed | quiet |
| 2026-10-29 | `remote/ai.skuit/catalog` | 2026-10-28T132854710391 -> 2026-10-29T212835102227 | 1 changed | quiet |
| 2026-10-29 | `remote/co.civai.nova/telegram-agent` | 2026-10-29T104159708084 -> 2026-10-29T212833866053 | 3 added | quiet |
| 2026-10-29 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-10-28T212323039119 -> 2026-10-29T212831933255 | 1 changed | review |
| 2026-10-29 | `remote/io.github.brawlaphant/vealth` | 2026-10-29T063230030399 -> 2026-10-29T212831604701 | 1 changed, 4 added | quiet |
| 2026-10-29 | `remote/io.github.smarterweather/weather` | 2026-10-29T063209274602 -> 2026-10-29T212830903632 | 4 changed, 1 removed | quiet |
| 2026-10-29 | `remote/com.ortexo/mcp` | 2026-10-29T133115481244 -> 2026-10-29T212831853081 | 1 added | quiet |
| 2026-10-29 | `remote/com.optimistfi/optimistfi` | 2026-10-28T212336040571 -> 2026-10-29T212831029767 | 2 changed | quiet |
| 2026-10-29 | `remote/org.r3js/r3` | 2026-10-29T153746955814 -> 2026-10-29T212831249803 | 4 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 41499 substantive, 19560 that changed only numbers (a catalogue counter ticking, a date), 721 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 34063 | 15829 | 18234 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1126 | 1126 | 0 | 0 |
| `caseyjhand.com` | 272 | 272 | 0 | 0 |
| `sistaminuten.se` | 171 | 6 | 0 | 165 |
| `afbudsrejser.dk` | 170 | 6 | 0 | 164 |
| `akkilahdot.fi` | 170 | 6 | 0 | 164 |
| `restplass.no` | 170 | 6 | 0 | 164 |
| `socialloop.ai` | 164 | 164 | 0 | 0 |
| `remoshift.com` | 140 | 10 | 130 | 0 |
| `fundinglandscape.com` | 131 | 83 | 48 | 0 |
| `revmesh2074.workers.dev` | 129 | 116 | 13 | 0 |
| 6459 other operators | 22733 | 21534 | 1135 | 64 |
