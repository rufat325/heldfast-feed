# MCP server tool changes

Last change observed 2026-11-01T13:58:59+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

68082 changes to a tool definition: 2873 npm releases (2627 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 65209 readings of hosted servers that found their tools changed; 3144 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-01 | `remote/xn--3ds443g.xn--s7y/duan-online` | 2026-10-28T133519297232 -> 2026-11-01T135901633096 | 1 changed, 2 added | quiet |
| 2026-11-01 | `remote/insure.travelprotection/travel-insurance` | 2026-10-19T135519299710 -> 2026-11-01T135839779497 | 2 changed | review |
| 2026-11-01 | `remote/io.github.fathyshalaby/specky` | 2026-10-08T135536915927 -> 2026-11-01T135822002431 | 1 changed | quiet |
| 2026-11-01 | `remote/se.sistaminuten/travel-search` | 2026-11-01T065456679986 -> 2026-11-01T135819542034 | 1 changed | quiet |
| 2026-11-01 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-10-28T212418007109 -> 2026-11-01T135744042242 | 152 changed (every tool) | review |
| 2026-11-01 | `remote/uk.co.gigstamp/gigstamp` | 2026-11-01T065455526241 -> 2026-11-01T135741455315 | 3 changed | quiet |
| 2026-11-01 | `remote/com.cadprops/cadprops` | 2026-10-24T112909603757 -> 2026-11-01T135721816163 | 3 changed | quiet |
| 2026-11-01 | `remote/com.autoridaddigital.www/geo` | 2026-10-19T135440788112 -> 2026-11-01T135719375893 | 1 changed | quiet |
| 2026-11-01 | `remote/com.alexandria-archive/archive` | 2026-10-19T135439097722 -> 2026-11-01T135715918414 | 1 changed | quiet |
| 2026-11-01 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-30T210620323256 -> 2026-11-01T135706077268 | 2 added | quiet |
| 2026-11-01 | `remote/com.viraloutliers/viral-outliers` | 2026-10-17T055534121365 -> 2026-11-01T135642607252 | 1 added | quiet |
| 2026-11-01 | `remote/com.scriptmasterlabs/verdict` | 2026-10-26T133801093249 -> 2026-11-01T135635070513 | 2 changed | review |
| 2026-11-01 | `remote/io.github.eric-tijerina/trollbridge-mcp` | 2026-10-06T110113420505 -> 2026-11-01T135608294242 | 15 changed | review |
| 2026-11-01 | `remote/io.github.SKalinin909/tradingcalc` | 2026-10-31T234849844348 -> 2026-11-01T135605004505 | 1 added | quiet |
| 2026-11-01 | `remote/com.skaidigital/shopify-speed-check` | 2026-10-26T133733167888 -> 2026-11-01T135600598894 | 1 added | quiet |
| 2026-11-01 | `remote/com.skaidigital/norwegian-companies` | 2026-10-26T133733703580 -> 2026-11-01T135600893745 | 1 added | quiet |
| 2026-11-01 | `remote/com.timeofmeeting/time-of-meeting` | 2026-10-24T112807951542 -> 2026-11-01T135552105492 | 1 changed | quiet |
| 2026-11-01 | `remote/io.github.f-tiger/dollscout-collecting` | 2026-10-06T110100806729 -> 2026-11-01T135547686606 | 1 changed, 3 added | quiet |
| 2026-11-01 | `remote/com.tektolo/rental-property` | 2026-10-25T191841518405 -> 2026-11-01T135538203995 | 5 changed (every tool) | quiet |
| 2026-11-01 | `remote/io.github.eamwhite1/agent-trust` | 2026-10-28T153342107819 -> 2026-11-01T135515735678 | 2 changed | quiet |
| 2026-11-01 | `remote/com.scriptmasterlabs/robinhood-rwa` | 2026-10-26T133645524013 -> 2026-11-01T135504293551 | 8 changed (every tool) | review |
| 2026-11-01 | `remote/com.satellitequotes/satellitequotes` | 2026-10-17T224515218506 -> 2026-11-01T135458185213 | 2 changed | quiet |
| 2026-11-01 | `remote/com.idosgames/platform` | 2026-10-28T062204052698 -> 2026-11-01T135459524503 | 1 changed | quiet |
| 2026-11-01 | `remote/com.rightshold/rightshold` | 2026-10-26T133712193081 -> 2026-11-01T135456842923 | 8 changed | quiet |
| 2026-11-01 | `remote/io.github.CustomBlinds/cb-shop` | 2026-10-29T212855129581 -> 2026-11-01T135451386185 | 6 changed | quiet |
| 2026-11-01 | `remote/com.shipshapedata/shipshape-data-docs` | 2026-10-31T130034832713 -> 2026-11-01T135451005625 | 1 changed | quiet |
| 2026-11-01 | `remote/io.github.ryan-tish/sendpaper` | 2026-10-10T144713101776 -> 2026-11-01T135442257902 | 2 changed | quiet |
| 2026-11-01 | `remote/watch.sbox/sbox-watch` | 2026-10-17T055431845811 -> 2026-11-01T135431509760 | 3 changed | quiet |
| 2026-11-01 | `remote/com.synthexforge.x402/paid-agent-services` | 2026-10-26T133616723795 -> 2026-11-01T135429261721 | 2 changed, 188 added, 121 removed (every tool) | review |
| 2026-11-01 | `remote/ng.com.xpressflowsystems.www/esim-domains` | 2026-10-31T130439794770 -> 2026-11-01T135426917009 | 1 changed | quiet |
| 2026-11-01 | `remote/ai.reg-bot/compliance-oracle` | 2026-10-19T135605610770 -> 2026-11-01T135414258916 | 1 changed | quiet |
| 2026-11-01 | `remote/work.remoty/remote-jobs` | 2026-10-26T133600898095 -> 2026-11-01T135404707223 | 1 added | quiet |
| 2026-11-01 | `remote/studio.gradients/mcp` | 2026-11-01T065445331687 -> 2026-11-01T135401416392 | 1 changed | quiet |
| 2026-11-01 | `remote/io.github.EasyGerber/easygerber` | 2026-10-24T113023221834 -> 2026-11-01T135352706376 | 5 changed | quiet |
| 2026-11-01 | `remote/com.xither/record` | 2026-10-06T110336185414 -> 2026-11-01T135348522275 | 1 changed | quiet |
| 2026-11-01 | `remote/ru.quintadb/mcp` | 2026-10-26T211457153620 -> 2026-11-01T135345851638 | 1 changed | quiet |
| 2026-11-01 | `remote/dev.upfork/upfork` | 2026-10-30T132850274133 -> 2026-11-01T135343603359 | 2 changed | quiet |
| 2026-11-01 | `remote/org.steadysteel/steady-steel` | 2026-10-17T060457309536 -> 2026-11-01T135341326701 | 1 changed | quiet |
| 2026-11-01 | `remote/ro.soundcreation/catalog` | 2026-10-31T130307852628 -> 2026-11-01T135342569211 | 2 changed | quiet |
| 2026-11-01 | `remote/io.github.ucunhome/ucun-select` | 2026-10-28T212406973242 -> 2026-11-01T135341266716 | 5 changed | quiet |
| 2026-11-01 | `remote/no.restplass/travel-search` | 2026-11-01T065449525350 -> 2026-11-01T135336381020 | 1 changed | quiet |
| 2026-11-01 | `remote/fi.akkilahdot/travel-search` | 2026-11-01T065443515433 -> 2026-11-01T135335300405 | 1 changed | quiet |
| 2026-11-01 | `remote/dev.workers.regnotes.workday-calendar/workday-calendar` | 2026-10-26T133458678125 -> 2026-11-01T135328551701 | 4 changed (every tool) | quiet |
| 2026-11-01 | `remote/com.meridiandispatch/travel-guides` | 2026-10-31T202136666006 -> 2026-11-01T135327971760 | 1 changed | quiet |
| 2026-11-01 | `remote/com.proflightsearch/airport-delays` | 2026-10-28T133120309382 -> 2026-11-01T135328068237 | 2 changed | quiet |
| 2026-11-01 | `remote/fr.lingoris/traduction-assermentee` | 2026-09-23T163137662866 -> 2026-11-01T135325876254 | 1 changed | quiet |
| 2026-11-01 | `remote/com.whichtrim/vehicle-records` | 2026-10-19T135519444989 -> 2026-11-01T135322937911 | 1 changed | quiet |
| 2026-11-01 | `remote/com.thenewengineer/hvac` | 2026-10-30T210617154440 -> 2026-11-01T135320684698 | 2 changed | quiet |
| 2026-11-01 | `remote/app.openkrill/post-stats` | 2026-10-23T200823568727 -> 2026-11-01T135319348818 | 2 changed | quiet |
| 2026-11-01 | `remote/xyz.pokeka/card-prices` | 2026-10-31T062128144946 -> 2026-11-01T135316674233 | 3 changed | quiet |
| 2026-11-01 | `remote/cc.thecolony/mcp-server` | 2026-10-31T234849348543 -> 2026-11-01T135317982771 | 3 changed, 2 added | quiet |
| 2026-11-01 | `remote/io.github.Fizzl13/plaintext-wallet-checker` | 2026-10-01T134225210905 -> 2026-11-01T135312254657 | 3 changed (every tool) | quiet |
| 2026-11-01 | `remote/com.tektolo/capabilities` | 2026-10-25T191836841442 -> 2026-11-01T135310685289 | 5 changed (every tool) | quiet |
| 2026-11-01 | `remote/tech.ydb-qdrant.pets/codex-pets-ydb-qdrant` | 2026-10-22T121652866755 -> 2026-11-01T135307220970 | 1 changed | quiet |
| 2026-11-01 | `remote/io.github.suanrongbaicai/vibecodepicks` | 2026-10-23T052642914696 -> 2026-11-01T135303182136 | 13 changed (every tool) | quiet |
| 2026-11-01 | `remote/dk.afbudsrejser/travel-search` | 2026-11-01T065444369398 -> 2026-11-01T135301547543 | 1 changed | quiet |
| 2026-11-01 | `remote/ai.surfingdog/search` | 2026-10-28T133603512742 -> 2026-11-01T135300586199 | 16 changed, 6 added (every tool) | quiet |
| 2026-11-01 | `remote/ru.vedarai/mcp` | 2026-10-30T132945295596 -> 2026-11-01T135300529481 | 1 changed, 1 added | quiet |
| 2026-11-01 | `remote/io.github.witanmarkets/witan` | 2026-10-28T133409234096 -> 2026-11-01T135256004358 | 8 changed (every tool) | quiet |
| 2026-11-01 | `remote/com.webhook-studio/webhooks` | 2026-09-23T163111076137 -> 2026-11-01T135249492757 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 43919 substantive, 23394 that changed only numbers (a catalogue counter ticking, a date), 769 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 37734 | 15838 | 21896 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1245 | 1245 | 0 | 0 |
| `caseyjhand.com` | 309 | 309 | 0 | 0 |
| `sistaminuten.se` | 182 | 6 | 0 | 176 |
| `afbudsrejser.dk` | 181 | 6 | 0 | 175 |
| `akkilahdot.fi` | 181 | 6 | 0 | 175 |
| `restplass.no` | 181 | 6 | 0 | 175 |
| `socialloop.ai` | 175 | 175 | 0 | 0 |
| `remoshift.com` | 151 | 10 | 141 | 0 |
| `revmesh2074.workers.dev` | 146 | 128 | 18 | 0 |
| `fundinglandscape.com` | 139 | 87 | 52 | 0 |
| 6834 other operators | 25117 | 23762 | 1287 | 68 |
