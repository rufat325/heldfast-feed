# MCP server tool changes

Last change observed 2026-10-31T13:04:45+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

65282 changes to a tool definition: 2775 npm releases (2529 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 62507 readings of hosted servers that found their tools changed; 3088 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-31 | `remote/com.zadely/games` | 2026-10-19T135621536912 -> 2026-10-31T130446117950 | 1 added | quiet |
| 2026-10-31 | `remote/com.sakuraweb.yamagishi/physics-papers` | 2026-10-26T133619467518 -> 2026-10-31T130444386928 | 1 changed | quiet |
| 2026-10-31 | `remote/ai.greyridgesignals/tech-risk` | 2026-10-31T062142926054 -> 2026-10-31T130439828269 | 1 added | quiet |
| 2026-10-31 | `remote/ng.com.xpressflowsystems.www/esim-domains` | 2026-10-26T133613943487 -> 2026-10-31T130439794770 | 4 changed | quiet |
| 2026-10-31 | `remote/com.theaiintegrationhub/use-cases` | 2026-10-28T133138296164 -> 2026-10-31T130432080038 | 2 changed | quiet |
| 2026-10-31 | `remote/com.serverscan/mcp` | 2026-10-26T133557417103 -> 2026-10-31T130426372251 | 2 added | quiet |
| 2026-10-31 | `remote/io.github.imokokok/insight-oracle` | 2026-10-26T133549392050 -> 2026-10-31T130420420527 | 2 changed | quiet |
| 2026-10-31 | `remote/com.hoteldiscount24/hotels` | 2026-10-26T133535430246 -> 2026-10-31T130411531156 | 1 changed | quiet |
| 2026-10-31 | `remote/studio.gradients/mcp` | 2026-10-31T062141031010 -> 2026-10-31T130409944307 | 1 changed | quiet |
| 2026-10-31 | `remote/ar.com.consignatarias/cattle-market` | 2026-10-23T135205688191 -> 2026-10-31T130355268882 | 1 changed | quiet |
| 2026-10-31 | `remote/fi.akkilahdot/travel-search` | 2026-10-31T062140117646 -> 2026-10-31T130345218290 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.a21ai/worth` | 2026-10-26T133501224413 -> 2026-10-31T130342971294 | 2 changed | quiet |
| 2026-10-31 | `remote/io.github.TRDEFI/liquidity` | 2026-10-24T190422480951 -> 2026-10-31T130331146475 | 1 added | quiet |
| 2026-10-31 | `remote/ai.yentaknows/directory` | 2026-10-29T104631019630 -> 2026-10-31T130332603842 | 2 changed | quiet |
| 2026-10-31 | `remote/io.github.WattCoin-Org/wattcoin-mcp-server` | 2026-09-23T162927046682 -> 2026-10-31T130326820841 | 16 changed, 6 added, 3 removed (every tool) | quiet |
| 2026-10-31 | `remote/io.github.Fizzl13/x402-doctor` | 2026-10-31T062129519735 -> 2026-10-31T130319888934 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.wyroapi/wyro` | 2026-10-26T133734650193 -> 2026-10-31T130319565259 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.rezearcher/tech-risk` | 2026-10-31T062128557406 -> 2026-10-31T130319223654 | 1 added | quiet |
| 2026-10-31 | `remote/io.taifoon/coordination-layer.1` | 2026-10-31T062139419373 -> 2026-10-31T130314854814 | 1 changed | review |
| 2026-10-31 | `remote/se.sistaminuten/travel-search` | 2026-10-31T062140178054 -> 2026-10-31T130312550036 | 1 changed | quiet |
| 2026-10-31 | `remote/io.soldcomps/sold-comps` | 2026-10-26T133717159908 -> 2026-10-31T130309260761 | 1 changed | quiet |
| 2026-10-31 | `remote/life.underway/underway` | 2026-10-26T133425794985 -> 2026-10-31T130307813213 | 1 changed | quiet |
| 2026-10-31 | `remote/ro.soundcreation/catalog` | 2026-09-26T132456277937 -> 2026-10-31T130307852628 | 2 changed | quiet |
| 2026-10-31 | `remote/io.github.ceedot-rock/slid-phi-labs` | 2026-10-23T120703796898 -> 2026-10-31T130301034590 | 5 changed, 2 added | review |
| 2026-10-31 | `remote/eu.mmatinca/travel-trends-mcp` | 2026-10-26T133418700145 -> 2026-10-31T130259512341 | 1 changed | quiet |
| 2026-10-31 | `remote/com.travelcharika/travelcharika` | 2026-10-17T055849022414 -> 2026-10-31T130258794148 | 3 changed, 1 added | quiet |
| 2026-10-31 | `remote/ai.oriiion/oriiion` | 2026-10-29T153733120900 -> 2026-10-31T130257957666 | 1 changed | quiet |
| 2026-10-31 | `remote/com.market0x/marketplace` | 2026-09-23T160847645672 -> 2026-10-31T130255086890 | 2 changed | quiet |
| 2026-10-31 | `remote/no.restplass/travel-search` | 2026-10-31T062157734689 -> 2026-10-31T130252406320 | 1 changed | quiet |
| 2026-10-31 | `remote/uk.co.gigstamp/gigstamp` | 2026-10-29T063227216539 -> 2026-10-31T130250970045 | 3 changed | quiet |
| 2026-10-31 | `remote/com.coveragecat/insurance` | 2026-10-29T104456974534 -> 2026-10-31T130241563120 | 14 changed, 3 added | review |
| 2026-10-31 | `remote/com.theagentsindex/mcp` | 2026-10-26T211500148548 -> 2026-10-31T130239218649 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-31T062136505877 -> 2026-10-31T130239226716 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.Bikram2112/claimhit` | 2026-10-18T190012963281 -> 2026-10-31T130236698411 | 1 changed | quiet |
| 2026-10-31 | `remote/no.apier/mcp` | 2026-10-24T125805115796 -> 2026-10-31T130235994889 | 1 changed | quiet |
| 2026-10-31 | `remote/xyz.t0ll/toll` | 2026-10-29T212852833116 -> 2026-10-31T130226334160 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.codex-curator/studiomcphub` | 2026-09-23T162900672386 -> 2026-10-31T130220142488 | 1 changed | quiet |
| 2026-10-31 | `remote/tech.dc5.whois/dc5-whois` | 2026-10-26T133619297467 -> 2026-10-31T130219031061 | 1 changed, 4 added | quiet |
| 2026-10-31 | `remote/com.warminboxes/deliverability-tools` | 2026-10-27T054058451294 -> 2026-10-31T130213336264 | 3 changed | quiet |
| 2026-10-31 | `remote/io.github.dtajitdinov-aris/sphere-marketplace` | 2026-10-28T132932574350 -> 2026-10-31T130216083925 | 20 changed, 2 added | quiet |
| 2026-10-31 | `remote/dk.afbudsrejser/travel-search` | 2026-10-31T062150609207 -> 2026-10-31T130208131631 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-31T062134299336 -> 2026-10-31T130204146903 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.cyanheads/socrata-mcp-server` | 2026-10-25T102507603032 -> 2026-10-31T130204068308 | 6 changed (every tool) | quiet |
| 2026-10-31 | `remote/com.i2dev/snap` | 2026-10-26T133322170914 -> 2026-10-31T130202501358 | 1 changed | quiet |
| 2026-10-31 | `remote/app.openkrill/slotscout` | 2026-10-19T135338968158 -> 2026-10-31T130200936260 | 4 changed, 1 added (every tool) | quiet |
| 2026-10-31 | `remote/xyz.urbangametheory/urban-game-theory` | 2026-10-30T132753937422 -> 2026-10-31T130155470755 | 5 changed | quiet |
| 2026-10-31 | `remote/com.usedforktruck/forklift-tools` | 2026-10-19T135148860388 -> 2026-10-31T130151358639 | 7 changed (every tool) | quiet |
| 2026-10-31 | `remote/com.vidreno/mcp` | 2026-10-29T104517509719 -> 2026-10-31T130149793028 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.ohad6k/viberaven-guides` | 2026-10-31T062144608827 -> 2026-10-31T130149361544 | 3 changed | quiet |
| 2026-10-31 | `remote/dev.sarnai/agent-output-verifier` | 2026-10-25T102455757355 -> 2026-10-31T130147832548 | 1 changed | quiet |
| 2026-10-31 | `remote/eu.madeinro/rotv-mcp` | 2026-10-01T212513867620 -> 2026-10-31T130147131332 | 7 changed | quiet |
| 2026-10-31 | `remote/app.openkrill/transcript-kit` | 2026-10-19T135142811582 -> 2026-10-31T130141955053 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.SKalinin909/tradingcalc` | 2026-10-31T062134179529 -> 2026-10-31T130138859479 | 1 added | quiet |
| 2026-10-31 | `remote/com.intoperson.tools/fair-random` | 2026-10-19T135140677380 -> 2026-10-31T130138992321 | 5 changed | quiet |
| 2026-10-31 | `remote/com.toolfound/toolfound` | 2026-10-17T060240529339 -> 2026-10-31T130134755729 | 1 changed | quiet |
| 2026-10-31 | `remote/com.intoperson.tools/lottery-numbers` | 2026-10-27T112218099234 -> 2026-10-31T130134759901 | 4 changed | quiet |
| 2026-10-31 | `remote/health.voa/tiss` | 2026-10-26T133526439486 -> 2026-10-31T130131818384 | 1 changed | quiet |
| 2026-10-31 | `remote/com.truevaluerankings/tvr-mcp` | 2026-09-23T163051521408 -> 2026-10-31T130129546210 | 10 changed (every tool) | quiet |
| 2026-10-31 | `remote/com.sapiensolutions/site` | 2026-10-25T102434376730 -> 2026-10-31T130127740931 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.exquad/thecablecode` | 2026-10-31T062124701521 -> 2026-10-31T130127964516 | 4 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 43027 substantive, 21509 that changed only numbers (a catalogue counter ticking, a date), 746 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 35899 | 15834 | 20065 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1127 | 1127 | 0 | 0 |
| `caseyjhand.com` | 287 | 287 | 0 | 0 |
| `sistaminuten.se` | 177 | 6 | 0 | 171 |
| `afbudsrejser.dk` | 176 | 6 | 0 | 170 |
| `akkilahdot.fi` | 176 | 6 | 0 | 170 |
| `restplass.no` | 176 | 6 | 0 | 170 |
| `socialloop.ai` | 170 | 170 | 0 | 0 |
| `remoshift.com` | 146 | 10 | 136 | 0 |
| `revmesh2074.workers.dev` | 137 | 124 | 13 | 0 |
| `fundinglandscape.com` | 135 | 85 | 50 | 0 |
| 6725 other operators | 24335 | 23025 | 1245 | 65 |
