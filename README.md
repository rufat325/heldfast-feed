# MCP server tool changes

Last change observed 2026-11-05T12:48:58+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

78142 changes to a tool definition: 3309 npm releases (3063 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 74833 readings of hosted servers that found their tools changed; 3412 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-05 | `remote/no.restplass/travel-search` | 2026-11-05T115729628083 -> 2026-11-05T124900326596 | 1 changed | quiet |
| 2026-11-05 | `remote/dk.afbudsrejser/travel-search` | 2026-11-05T115642264721 -> 2026-11-05T124855497166 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.ohad6k/viberaven-guides` | 2026-11-04T150705406636 -> 2026-11-05T124853267679 | 2 changed | quiet |
| 2026-11-05 | `remote/fr.synergieloc/immobilier` | 2026-11-04T200747093396 -> 2026-11-05T124849532181 | 3 changed | quiet |
| 2026-11-05 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-05T115440624726 -> 2026-11-05T124847075111 | 1 added | quiet |
| 2026-11-05 | `remote/se.sistaminuten/travel-search` | 2026-11-05T115431916747 -> 2026-11-05T124844239209 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-11-04T200753744285 -> 2026-11-05T124842711966 | 3 changed | quiet |
| 2026-11-05 | `remote/io.github.JcJamet/ia-qa-security` | 2026-11-04T200753690975 -> 2026-11-05T124842978292 | 3 changed | quiet |
| 2026-11-05 | `remote/io.github.JcJamet/ia-qa-eval` | 2026-11-03T195704225847 -> 2026-11-05T124843078408 | 1 changed | quiet |
| 2026-11-05 | `remote/studio.gradients/mcp` | 2026-11-05T115534125652 -> 2026-11-05T124830628598 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.Fizzl13/x402-doctor` | 2026-11-04T200819633647 -> 2026-11-05T124829107710 | 6 changed | quiet |
| 2026-11-05 | `remote/fi.akkilahdot/travel-search` | 2026-11-05T115515101780 -> 2026-11-05T124828469631 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.seasonsagents-art/webaz` | 2026-11-05T115452124081 -> 2026-11-05T124827584743 | 3 changed | quiet |
| 2026-11-05 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-05T115442364269 -> 2026-11-05T124827463802 | 3 changed | quiet |
| 2026-11-05 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-05T115432598184 -> 2026-11-05T124826962793 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.JcJamet/ia-qa-data` | 2026-11-03T122645242614 -> 2026-11-05T124826875484 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.bowenerchen/cipherhub` | 2026-11-05T115317807947 -> 2026-11-05T124827002284 | 2 changed | quiet |
| 2026-11-05 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-05T115402464837 -> 2026-11-05T124823762843 | 2 changed | quiet |
| 2026-11-05 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-05T115319744081 -> 2026-11-05T124818246143 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.roman-rr/trading-signals` | 2026-11-05T115152991062 -> 2026-11-05T124817432163 | 1 changed | quiet |
| 2026-11-05 | `remote/app.call2me/mcp` | 2026-11-05T114741679438 -> 2026-11-05T124815724253 | 2 changed | quiet |
| 2026-11-05 | `remote/io.github.i02202/automan` | 2026-11-04T005855108570 -> 2026-11-05T124813244495 | 1 changed | review |
| 2026-11-05 | `remote/io.github.dsanchezp18/maplestats-mcp` | 2026-11-05T010619949451 -> 2026-11-05T124810278049 | 1 changed | quiet |
| 2026-11-05 | `remote/cloud.lcas/directory` | 2026-11-05T114618651872 -> 2026-11-05T124809236010 | 1 changed | quiet |
| 2026-11-05 | `remote/gl.parse/mcp` | 2026-11-04T145826144637 -> 2026-11-05T124808952672 | 1 changed | quiet |
| 2026-11-05 | `remote/com.lasvegastonight/las-vegas-nightlife` | 2026-11-05T114613180207 -> 2026-11-05T124808752689 | 1 added, 1 removed | quiet |
| 2026-11-05 | `remote/com.googleapis.monitoring/mcp` | 2026-11-05T115051023719 -> 2026-11-05T124806485925 | 5 changed | quiet |
| 2026-11-05 | `remote/io.github.HelloSafe/travel-insurance` | 2026-11-03T143946836051 -> 2026-11-05T124805874592 | 1 changed | quiet |
| 2026-11-05 | `remote/com.lightbringer/connector` | 2026-11-03T144303819037 -> 2026-11-05T124800223309 | 6 changed, 2 added | quiet |
| 2026-11-05 | `remote/io.github.getDynamoi/dynamoi` | 2026-11-05T114218763465 -> 2026-11-05T124759438370 | 1 changed | quiet |
| 2026-11-05 | `remote/com.mandateoffice/mandate` | 2026-11-03T122601920991 -> 2026-11-05T124759122769 | 1 added | quiet |
| 2026-11-05 | `remote/social.flayr/flayr` | 2026-11-05T114228069143 -> 2026-11-05T124750878113 | 1 changed | quiet |
| 2026-11-05 | `remote/com.brofindai/brofindai` | 2026-11-04T123642670172 -> 2026-11-05T124750388089 | 1 changed | quiet |
| 2026-11-05 | `remote/app.vercel.fork-for-agents/fork` | 2026-11-05T114249618531 -> 2026-11-05T124747649940 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.hermoso-ai/hermoso` | 2026-11-04T200551541239 -> 2026-11-05T124746790337 | 2 changed | quiet |
| 2026-11-05 | `remote/app.apick/convert` | 2026-11-03T195347770191 -> 2026-11-05T124745901372 | 2 changed, 18 added | quiet |
| 2026-11-05 | `remote/io.github.bck-stack/sitecheck` | 2026-11-05T113836918781 -> 2026-11-05T124742008642 | 147 changed | quiet |
| 2026-11-05 | `remote/io.github.Fizzl13/fizzl-buy` | 2026-11-04T144940122357 -> 2026-11-05T124743030421 | 1 changed | quiet |
| 2026-11-05 | `remote/com.cooperemail/cooper-email` | 2026-11-04T123637532880 -> 2026-11-05T124739839725 | 2 changed | quiet |
| 2026-11-05 | `remote/io.github.bck-stack/sitecheck-company-records` | 2026-11-05T113632582249 -> 2026-11-05T124738335953 | 118 changed | quiet |
| 2026-11-05 | `remote/io.github.bck-stack/sitecheck-agent-intel-dev` | 2026-11-05T113641853237 -> 2026-11-05T124738882731 | 133 changed | review |
| 2026-11-05 | `remote/com.currencyguard/guard-pricing` | 2026-11-05T113635978854 -> 2026-11-05T124739099751 | 11 changed (every tool) | quiet |
| 2026-11-05 | `remote/com.calcbright/calcbright` | 2026-11-05T113915022300 -> 2026-11-05T124738085094 | 1 changed | review |
| 2026-11-05 | `remote/com.googleapis.bigtableadmin/mcp` | 2026-11-05T113933171960 -> 2026-11-05T124737575702 | 6 changed | quiet |
| 2026-11-05 | `remote/wine.beyond/beyond-wine` | 2026-11-05T114018518329 -> 2026-11-05T124735658677 | 11 changed (every tool) | quiet |
| 2026-11-05 | `remote/work.autonet/agent-health` | 2026-11-04T144841653050 -> 2026-11-05T124734242236 | 4 added | quiet |
| 2026-11-05 | `remote/app.apick/all` | 2026-11-04T123637315657 -> 2026-11-05T124737105994 | 2 changed, 18 added | quiet |
| 2026-11-05 | `remote/io.github.bck-stack/sitecheck-jobs-property` | 2026-11-05T113621228798 -> 2026-11-05T124732146080 | 111 changed | quiet |
| 2026-11-05 | `remote/io.github.whiteknightonhorse/apibase` | 2026-11-05T113842219855 -> 2026-11-05T124732003246 | 3 removed | quiet |
| 2026-11-05 | `remote/io.github.bck-stack/sitecheck-web-intel` | 2026-11-05T113837724373 -> 2026-11-05T124730443786 | 119 changed | quiet |
| 2026-11-05 | `remote/io.github.bck-stack/sitecheck-crypto-finance` | 2026-11-05T113555938332 -> 2026-11-05T124730584995 | 171 changed | quiet |
| 2026-11-05 | `remote/io.github.bck-stack/sitecheck-trade-energy` | 2026-11-05T113829505316 -> 2026-11-05T124729381846 | 110 changed | review |
| 2026-11-05 | `remote/io.github.bck-stack/sitecheck-shop-social` | 2026-11-05T113817255047 -> 2026-11-05T124728910381 | 107 changed | quiet |
| 2026-11-05 | `remote/io.github.bck-stack/sitecheck-health-travel` | 2026-11-05T113625693693 -> 2026-11-05T124727571039 | 113 changed | quiet |
| 2026-11-05 | `remote/com.exepal/exepal` | 2026-11-04T200538462324 -> 2026-11-05T124727990308 | 2 added | review |
| 2026-11-05 | `remote/com.amazap/amazap` | 2026-11-05T010607165795 -> 2026-11-05T124724787711 | 1 changed | review |
| 2026-11-05 | `remote/io.github.code0xff/1gateway` | 2026-11-04T005706691581 -> 2026-11-05T124722416379 | 1 changed | quiet |
| 2026-11-05 | `remote/ru.zakazat-zvezdu/stars` | 2026-10-27T124305012697 -> 2026-11-05T115759241000 | 1 changed, 1 removed | quiet |
| 2026-11-05 | `remote/io.github.Veniwol-Li-Lambd/lilambd-data` | 2026-11-04T010006333998 -> 2026-11-05T115757964809 | 1 changed, 1 added | quiet |
| 2026-11-05 | `remote/ai.thewholetorah/thewholetorah` | 2026-09-23T163147783910 -> 2026-11-05T115741322588 | 4 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 48171 substantive, 29130 that changed only numbers (a catalogue counter ticking, a date), 841 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 43267 | 15879 | 27388 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1485 | 1485 | 0 | 0 |
| `caseyjhand.com` | 354 | 354 | 0 | 0 |
| `sistaminuten.se` | 198 | 6 | 0 | 192 |
| `afbudsrejser.dk` | 197 | 6 | 0 | 191 |
| `akkilahdot.fi` | 197 | 6 | 0 | 191 |
| `restplass.no` | 197 | 6 | 0 | 191 |
| `socialloop.ai` | 190 | 190 | 0 | 0 |
| `remoshift.com` | 165 | 14 | 151 | 0 |
| `openkrill.app` | 153 | 153 | 0 | 0 |
| `revmesh2074.workers.dev` | 153 | 135 | 18 | 0 |
| 7655 other operators | 29245 | 27596 | 1573 | 76 |
