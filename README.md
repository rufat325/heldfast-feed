# MCP server tool changes

Last change observed 2026-11-27T09:11:14+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 18238 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 43073 hosted endpoints (read daily, and every four hours while they keep changing).

142620 changes to a tool definition: 5525 npm releases (5279 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 137095 readings of hosted servers that found their tools changed; 5203 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-27 | `remote/com.test-well/testwell` | 2026-11-26T135606493878 -> 2026-11-27T091115362314 | 2 changed | quiet |
| 2026-11-27 | `remote/se.sistaminuten/travel-search` | 2026-11-26T220042895706 -> 2026-11-27T091115173544 | 1 changed | quiet |
| 2026-11-27 | `remote/io.suverse.www/catalog` | 2026-11-26T085933410268 -> 2026-11-27T091115773750 | 3 changed | quiet |
| 2026-11-27 | `remote/io.github.jhonnysabino/moedux` | 2026-11-26T135536501930 -> 2026-11-27T091113688408 | 23 changed (every tool) | quiet |
| 2026-11-27 | `remote/xyz.urbangametheory/urban-game-theory` | 2026-11-26T172727890819 -> 2026-11-27T091110113866 | 2 changed | quiet |
| 2026-11-27 | `remote/app.usesnippet/snippet` | 2026-11-26T135358463671 -> 2026-11-27T091108419395 | 1 changed | quiet |
| 2026-11-27 | `remote/com.thefomite/fomite` | 2026-11-26T004538104241 -> 2026-11-27T091107871898 | 1 changed | quiet |
| 2026-11-27 | `remote/com.swishrjobs/swishrjobs` | 2026-11-26T220030577946 -> 2026-11-27T091105573365 | 130 changed, 3 added | review |
| 2026-11-27 | `remote/com.caelaralabs/seo` | 2026-11-26T220025556330 -> 2026-11-27T091101784060 | 6 added | quiet |
| 2026-11-27 | `remote/com.rexceltech/pvault` | 2026-11-25T034948716351 -> 2026-11-27T091059745909 | 8 changed (every tool) | review |
| 2026-11-27 | `remote/io.github.hft-studio/pokerdata` | 2026-11-26T135027130172 -> 2026-11-27T091117312154 | 6 changed | quiet |
| 2026-11-27 | `remote/com.partstable/mcp` | 2026-11-26T135004603217 -> 2026-11-27T091057101804 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.donofdebt/ouncescout` | 2026-11-26T004511705206 -> 2026-11-27T091055896562 | 18 changed (every tool) | quiet |
| 2026-11-27 | `remote/io.motomarks/mcp` | 2026-11-25T105259792550 -> 2026-11-27T091054402584 | 8 changed (every tool) | quiet |
| 2026-11-27 | `remote/io.github.liuqianyu885/mrrbench-pricing` | 2026-11-25T034937171670 -> 2026-11-27T091052088186 | 1 changed | quiet |
| 2026-11-27 | `remote/tech.tresbien/drupal-code-query` | 2026-11-26T172149343208 -> 2026-11-27T091050540438 | 2 changed, 1 added | quiet |
| 2026-11-27 | `remote/com.rivalsweeper/signals` | 2026-11-26T220007650192 -> 2026-11-27T091048810121 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-11-26T220004928615 -> 2026-11-27T091046719215 | 1 changed | review |
| 2026-11-27 | `remote/dev.kitscout/kitscout` | 2026-11-25T105012436718 -> 2026-11-27T091044782848 | 1 changed | quiet |
| 2026-11-27 | `remote/com.jojapi/sms-verify` | 2026-11-26T085859037997 -> 2026-11-27T091045212258 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.jimmybr-PDX/rugradar` | 2026-11-26T220017561451 -> 2026-11-27T091042681235 | 2 changed | review |
| 2026-11-27 | `remote/io.github.echopai/echopai-mcp` | 2026-11-26T220005180434 -> 2026-11-27T091050892897 | 5 changed | quiet |
| 2026-11-27 | `remote/ai.catalystdesk/mcp-server` | 2026-11-26T085910221830 -> 2026-11-27T091043154410 | 6 added | quiet |
| 2026-11-27 | `remote/com.ticketfairy/ticket-fairy-public-events` | 2026-11-26T220016887374 -> 2026-11-27T091041910644 | 4 changed, 1 added | quiet |
| 2026-11-27 | `remote/app.gigxchange/gigxchange` | 2026-11-26T171944793336 -> 2026-11-27T091043848252 | 5 changed | quiet |
| 2026-11-27 | `remote/io.github.HuangGoodmanAgency/edgar-and-edgarette` | 2026-11-26T220014090720 -> 2026-11-27T091039041477 | 1 added | quiet |
| 2026-11-27 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-26T220014235746 -> 2026-11-27T091039511152 | 2 changed | quiet |
| 2026-11-27 | `remote/com.whizbrew/whizbrew` | 2026-11-26T220011560026 -> 2026-11-27T091036882018 | 3 changed | quiet |
| 2026-11-27 | `remote/io.suverse.versum/catalog` | 2026-11-26T085905624487 -> 2026-11-27T091037187074 | 3 changed | quiet |
| 2026-11-27 | `remote/estate.cubi/cubi-properties` | 2026-11-25T104911730601 -> 2026-11-27T091038566994 | 3 changed | quiet |
| 2026-11-27 | `remote/com.dilutionscan/mcp` | 2026-11-25T174006246245 -> 2026-11-27T091039023527 | 1 changed | quiet |
| 2026-11-27 | `remote/io.trueinterview/trueinterview` | 2026-11-26T172721985108 -> 2026-11-27T091034637323 | 40 changed (every tool) | quiet |
| 2026-11-27 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-26T220008978628 -> 2026-11-27T091035437455 | 7 changed | quiet |
| 2026-11-27 | `remote/il.co.taseli/taseli.1` | 2026-11-26T004625769459 -> 2026-11-27T091033728785 | 1 changed | quiet |
| 2026-11-27 | `remote/ai.codegene/codegene` | 2026-11-26T215955818686 -> 2026-11-27T091035526915 | 3 changed, 3 added | quiet |
| 2026-11-27 | `remote/io.github.roman-rr/trading-signals` | 2026-11-26T134403045122 -> 2026-11-27T091031720180 | 1 changed | quiet |
| 2026-11-27 | `remote/com.caelaralabs/social` | 2026-11-26T220004017385 -> 2026-11-27T091030884230 | 6 added | quiet |
| 2026-11-27 | `remote/io.github.grzesir/botspot-trading` | 2026-11-25T150242933341 -> 2026-11-27T091034787266 | 4 changed | quiet |
| 2026-11-27 | `remote/com.scorecompute/scorecompute` | 2026-11-26T172504904970 -> 2026-11-27T091031177320 | 1 added | quiet |
| 2026-11-27 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-11-26T004622700942 -> 2026-11-27T091029080190 | 1 changed | quiet |
| 2026-11-27 | `remote/now.salesjobs/mcp` | 2026-11-26T134327487254 -> 2026-11-27T091030412331 | 1 changed | quiet |
| 2026-11-27 | `remote/com.precellence-service/paris-chauffeur` | 2026-11-25T105835553948 -> 2026-11-27T091028010199 | 1 changed | quiet |
| 2026-11-27 | `remote/xyz.octio/octio` | 2026-11-25T175100593050 -> 2026-11-27T091026087596 | 1 added | quiet |
| 2026-11-27 | `remote/shop.photosweat/remove-background` | 2026-11-26T085854712100 -> 2026-11-27T091024951719 | 1 added | review |
| 2026-11-27 | `remote/ai.modulos/demo-booking` | 2026-11-26T135526773592 -> 2026-11-27T091025815143 | 1 changed, 2 added | quiet |
| 2026-11-27 | `remote/studio.gradients/mcp` | 2026-11-26T220041872257 -> 2026-11-27T091024205114 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-26T004801553913 -> 2026-11-27T091022789963 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.farenberglord-star/orb-studio` | 2026-11-26T215956572083 -> 2026-11-27T091025252628 | 1 changed | quiet |
| 2026-11-27 | `remote/fi.akkilahdot/travel-search` | 2026-11-26T220041594670 -> 2026-11-27T091024659598 | 1 changed | quiet |
| 2026-11-27 | `remote/com.whatsonvegas/whats-on-vegas` | 2026-11-26T135427193563 -> 2026-11-27T091022873037 | 2 changed | quiet |
| 2026-11-27 | `remote/com.weverlabs/agentic-rails` | 2026-11-26T220048392969 -> 2026-11-27T091044830892 | 8 added | quiet |
| 2026-11-27 | `remote/com.visdenda/public` | 2026-11-26T135415494810 -> 2026-11-27T091022779984 | 9 changed | quiet |
| 2026-11-27 | `remote/pl.kiedysport/sport` | 2026-11-26T215952324968 -> 2026-11-27T091023055980 | 3 changed | quiet |
| 2026-11-27 | `remote/md.mostlyright/datasets` | 2026-11-26T172223345670 -> 2026-11-27T091020317178 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-26T090004526196 -> 2026-11-27T091022037911 | 3 changed | quiet |
| 2026-11-27 | `remote/com.midasiteurope/civil-nx` | 2026-11-26T215951974710 -> 2026-11-27T091019799232 | 5 changed | quiet |
| 2026-11-27 | `remote/co.zindies/zindies` | 2026-11-25T150257893866 -> 2026-11-27T091018467867 | 2 changed | quiet |
| 2026-11-27 | `remote/works.jobsweep/jobsweep` | 2026-11-26T215951159520 -> 2026-11-27T091019778312 | 2 changed, 1 added | quiet |
| 2026-11-27 | `remote/com.waypointrecruit.jobs/healthcare-jobs` | 2026-11-26T085849447457 -> 2026-11-27T091019250444 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.liad142/yedapo` | 2026-11-26T085920448239 -> 2026-11-27T091011897889 | 2 changed (every tool) | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 96121 substantive, 45257 that changed only numbers (a catalogue counter ticking, a date), 1242 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 78619 | 36545 | 42074 | 0 |
| `a2awire.com` | 3972 | 3972 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 546 | 546 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 403 | 403 | 0 | 0 |
| `revmesh2074.workers.dev` | 371 | 315 | 56 | 0 |
| `sistaminuten.se` | 289 | 7 | 0 | 282 |
| `afbudsrejser.dk` | 288 | 7 | 0 | 281 |
| `akkilahdot.fi` | 288 | 7 | 0 | 281 |
| `restplass.no` | 288 | 7 | 0 | 281 |
| `socialloop.ai` | 279 | 279 | 0 | 0 |
| 11680 other operators | 54456 | 51212 | 3127 | 117 |
