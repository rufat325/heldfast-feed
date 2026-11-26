# MCP server tool changes

Last change observed 2026-11-26T17:32:01+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 18238 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 43073 hosted endpoints (read daily, and every four hours while they keep changing).

142234 changes to a tool definition: 5525 npm releases (5279 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 136709 readings of hosted servers that found their tools changed; 5185 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-26 | `remote/com.yazilimkocu/ajan` | 2026-11-21T151138477262 -> 2026-11-26T173203384324 | 2 changed | quiet |
| 2026-11-26 | `remote/com.workeey/quote-links` | 2026-11-21T151136849059 -> 2026-11-26T173202215952 | 6 changed (every tool) | quiet |
| 2026-11-26 | `remote/io.github.thrive-fleet/fleet-data` | 2026-11-16T163401277853 -> 2026-11-26T173156336013 | 1 added | quiet |
| 2026-11-26 | `remote/ru.zavod-stanki/cnc-catalog` | 2026-10-26T133623406598 -> 2026-11-26T173151365893 | 3 added | quiet |
| 2026-11-26 | `remote/no.restplass/travel-search` | 2026-11-26T134730362384 -> 2026-11-26T173144222665 | 1 changed | quiet |
| 2026-11-26 | `remote/com.yazilimkocu/erp` | 2026-11-21T151217309382 -> 2026-11-26T173140131532 | 1 changed | quiet |
| 2026-11-26 | `remote/com.yazilimkocu/crm` | 2026-11-21T151217189084 -> 2026-11-26T173139626581 | 1 changed | quiet |
| 2026-11-26 | `remote/net.continental/expiring-domains` | 2026-11-23T185418296680 -> 2026-11-26T173102813427 | 1 added | quiet |
| 2026-11-26 | `remote/app.hyperwave.www/wavetable-tools` | 2026-11-23T185519817670 -> 2026-11-26T173100619689 | 1 changed | quiet |
| 2026-11-26 | `remote/studio.gradients/mcp` | 2026-11-26T135515295764 -> 2026-11-26T173059508613 | 1 changed | quiet |
| 2026-11-26 | `remote/dk.afbudsrejser/travel-search` | 2026-11-26T134639416505 -> 2026-11-26T173045276426 | 1 changed | quiet |
| 2026-11-26 | `remote/fi.akkilahdot/travel-search` | 2026-11-26T135446392153 -> 2026-11-26T173030894181 | 1 changed | quiet |
| 2026-11-26 | `remote/xyz.wunderlust/wunderlust` | 2026-11-23T185440791345 -> 2026-11-26T173027499072 | 11 changed (every tool) | quiet |
| 2026-11-26 | `remote/com.vidreno/mcp` | 2026-11-26T134610220932 -> 2026-11-26T173012998711 | 1 changed | quiet |
| 2026-11-26 | `remote/com.yangopen/mcp` | 2026-11-24T170306945002 -> 2026-11-26T173001430107 | 21 changed | quiet |
| 2026-11-26 | `remote/xyz.x402helper/mcp` | 2026-11-25T175323115648 -> 2026-11-26T172956796978 | 1 changed, 1 added, 1 removed | quiet |
| 2026-11-26 | `remote/com.yazilimkocu/yapayzeka` | 2026-11-21T151219462711 -> 2026-11-26T172955219322 | 1 changed | quiet |
| 2026-11-26 | `remote/com.yazilimkocu/belediye` | 2026-11-21T151217996105 -> 2026-11-26T172954567262 | 1 changed | quiet |
| 2026-11-26 | `remote/com.yazilimkocu/pazaryeri` | 2026-11-21T151234903205 -> 2026-11-26T172952038027 | 1 changed | quiet |
| 2026-11-26 | `remote/dev.workers.veritas-silicea.veritas-silicea-shop/art` | 2026-11-26T135405839318 -> 2026-11-26T172949172526 | 1 changed | quiet |
| 2026-11-26 | `remote/com.theagentcolosseum/agent-colosseum` | 2026-11-26T135608056894 -> 2026-11-26T172946185489 | 6 changed (every tool) | quiet |
| 2026-11-26 | `remote/se.sistaminuten/travel-search` | 2026-11-26T135555952843 -> 2026-11-26T172934075994 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.renderedfits/open-data` | 2026-11-25T150355485178 -> 2026-11-26T172931631079 | 1 changed | quiet |
| 2026-11-26 | `remote/com.trackerhacker/mcp` | 2026-11-24T050344167562 -> 2026-11-26T172929960608 | 1 changed | quiet |
| 2026-11-26 | `remote/com.quantamentry/quantamentry` | 2026-09-23T160850586788 -> 2026-11-26T172931398314 | 1 added | quiet |
| 2026-11-26 | `remote/com.quantum-expectations/quantum-expectations` | 2026-11-10T152957435883 -> 2026-11-26T172927148627 | 6 changed | quiet |
| 2026-11-26 | `remote/io.github.tradinglookup/data` | 2026-11-24T170131067582 -> 2026-11-26T172915349335 | 1 changed, 5 added | quiet |
| 2026-11-26 | `remote/com.herbertandphyllis/mcp` | 2026-11-25T150358464613 -> 2026-11-26T172904075761 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-26T134704083575 -> 2026-11-26T172859197460 | 3 changed, 8 added | quiet |
| 2026-11-26 | `remote/com.entangleeq/pay-transparency` | 2026-11-25T105909426660 -> 2026-11-26T172856456628 | 6 changed (every tool) | quiet |
| 2026-11-26 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-26T135308836050 -> 2026-11-26T172845408023 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.MSNR-Create/symbiosis-agora` | 2026-11-26T134454907542 -> 2026-11-26T172839800325 | 1 added | quiet |
| 2026-11-26 | `remote/mx.techstore/catalog` | 2026-11-26T135258212723 -> 2026-11-26T172834773632 | 5 added | review |
| 2026-11-26 | `remote/ru.zavod-stanki/cnc-catalog.1` | 2026-10-26T133531539696 -> 2026-11-26T172816239869 | 3 added | quiet |
| 2026-11-26 | `remote/com.andque/agent-data` | 2026-11-26T085939225118 -> 2026-11-26T172810871334 | 18 changed (every tool) | quiet |
| 2026-11-26 | `remote/com.southwestpitch/southwest-pitch` | 2026-11-23T185121857285 -> 2026-11-26T172802221740 | 4 added | quiet |
| 2026-11-26 | `remote/ai.stablenews/news` | 2026-11-26T135224583072 -> 2026-11-26T172752726907 | 1 changed | quiet |
| 2026-11-26 | `remote/com.thetempleofdoom.vega-mcp/vega` | 2026-11-25T174900439174 -> 2026-11-26T172736369282 | 26 changed (every tool) | quiet |
| 2026-11-26 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-26T135210898752 -> 2026-11-26T172734242499 | 1 changed | quiet |
| 2026-11-26 | `remote/dev.upfork/upfork` | 2026-11-04T200805359049 -> 2026-11-26T172732418935 | 3 changed | quiet |
| 2026-11-26 | `remote/io.github.eyeinthesky6/unseen-workflow-compiler` | 2026-11-20T074935722662 -> 2026-11-26T172731557684 | 2 changed | review |
| 2026-11-26 | `remote/xyz.urbangametheory/urban-game-theory` | 2026-11-26T085924945022 -> 2026-11-26T172727890819 | 6 changed | quiet |
| 2026-11-26 | `remote/io.sibidz/sibidz` | 2026-11-25T105819385502 -> 2026-11-26T172715863082 | 8 changed, 4 added (every tool) | review |
| 2026-11-26 | `remote/app.seoaeogeo/seo-aeo-geo` | 2026-11-13T145957034118 -> 2026-11-26T172701738827 | 1 changed | quiet |
| 2026-11-26 | `remote/co.roterminal/roterminal` | 2026-11-26T085905178584 -> 2026-11-26T172651814992 | 4 changed, 2 added | quiet |
| 2026-11-26 | `remote/com.tofubofu/ai-visibility` | 2026-11-26T135318843261 -> 2026-11-26T172650521353 | 16 added | quiet |
| 2026-11-26 | `remote/com.tapeperp/tape` | 2026-11-10T153014905057 -> 2026-11-26T172634120689 | 2 changed | review |
| 2026-11-26 | `remote/ai.teasa/teasa` | 2026-10-24T112801647102 -> 2026-11-26T172628744172 | 3 changed | quiet |
| 2026-11-26 | `remote/com.swishrjobs/swishrjobs` | 2026-11-26T135248954237 -> 2026-11-26T172618171468 | 3 changed, 1 added | quiet |
| 2026-11-26 | `remote/com.radarbg/radar-tools` | 2026-11-26T134307592811 -> 2026-11-26T172616994836 | 2 added | quiet |
| 2026-11-26 | `remote/com.thetempleofdoom.styx-mcp/styx` | 2026-09-28T142213960425 -> 2026-11-26T172611130907 | 6 changed (every tool) | review |
| 2026-11-26 | `remote/io.speakbase/speakbase` | 2026-11-26T134419433786 -> 2026-11-26T172555050037 | 5 changed | quiet |
| 2026-11-26 | `remote/com.soundiiz/soundiiz` | 2026-11-25T150328569606 -> 2026-11-26T172552705094 | 1 changed | quiet |
| 2026-11-26 | `remote/app.rarylib/rarylib` | 2026-11-26T135044271250 -> 2026-11-26T172551708948 | 1 added | quiet |
| 2026-11-26 | `remote/com.qhooks/mcp` | 2026-11-26T135035134258 -> 2026-11-26T172543681814 | 1 changed, 3 added | quiet |
| 2026-11-26 | `remote/com.pnwpitch/pnw-pitch` | 2026-11-23T184904763416 -> 2026-11-26T172541440008 | 4 added | quiet |
| 2026-11-26 | `remote/org.pitchnetwork/pitch-network` | 2026-11-23T184857542676 -> 2026-11-26T172534289566 | 7 added | quiet |
| 2026-11-26 | `remote/no.pristavla/pristavla` | 2026-11-26T085908169265 -> 2026-11-26T172528124173 | 1 changed | quiet |
| 2026-11-26 | `remote/dev.chinng-lab-srv/portal` | 2026-11-16T162700501462 -> 2026-11-26T172517852435 | 8 changed (every tool) | quiet |
| 2026-11-26 | `remote/io.github.kfx2026/sanyu-research` | 2026-11-26T135134398929 -> 2026-11-26T172513512632 | 113 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 95784 substantive, 45217 that changed only numbers (a catalogue counter ticking, a date), 1233 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 78619 | 36545 | 42074 | 0 |
| `a2awire.com` | 3972 | 3972 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 546 | 546 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 402 | 402 | 0 | 0 |
| `revmesh2074.workers.dev` | 370 | 315 | 55 | 0 |
| `sistaminuten.se` | 287 | 7 | 0 | 280 |
| `afbudsrejser.dk` | 286 | 7 | 0 | 279 |
| `akkilahdot.fi` | 286 | 7 | 0 | 279 |
| `restplass.no` | 286 | 7 | 0 | 279 |
| `socialloop.ai` | 277 | 277 | 0 | 0 |
| 11677 other operators | 54082 | 50878 | 3088 | 116 |
