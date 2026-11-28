# MCP server tool changes

Last change observed 2026-11-28T15:04:42+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 18238 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 43073 hosted endpoints (read daily, and every four hours while they keep changing).

148640 changes to a tool definition: 5721 npm releases (5475 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 142919 readings of hosted servers that found their tools changed; 5299 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-28 | `remote/io.zsign/zsign.1` | 2026-11-23T185416284422 -> 2026-11-28T150444179469 | 17 changed | quiet |
| 2026-11-28 | `remote/io.github.kwizzlesurp10-ctrl/x402-mcp` | 2026-11-16T123032386024 -> 2026-11-28T150425176261 | 1 changed | quiet |
| 2026-11-28 | `remote/com.yazilimkocu/pazaryeri` | 2026-11-26T172952038027 -> 2026-11-28T150422196243 | 1 changed | quiet |
| 2026-11-28 | `remote/dev.themes/ui` | 2026-11-27T145421298253 -> 2026-11-28T150411509087 | 1 changed | quiet |
| 2026-11-28 | `remote/com.step2gcode/step2gcode` | 2026-11-19T162626801692 -> 2026-11-28T150408106966 | 1 changed | quiet |
| 2026-11-28 | `remote/io.github.homeaccount7/signaldock` | 2026-11-14T140204706663 -> 2026-11-28T150404930044 | 2 changed, 2 removed | quiet |
| 2026-11-28 | `remote/com.photoaistudio/photo-ai-studio` | 2026-09-23T160848748914 -> 2026-11-28T150353637243 | 1 changed | quiet |
| 2026-11-28 | `remote/io.github.Humanleap/magicscreenshots-mcp` | 2026-10-27T124153028523 -> 2026-11-28T150342930578 | 19 changed (every tool) | quiet |
| 2026-11-28 | `remote/com.kineticist/mcp-server` | 2026-11-24T165536991035 -> 2026-11-28T150338478938 | 4 changed, 40 added | quiet |
| 2026-11-28 | `remote/io.github.dell-mic/insider-trades-vanilla.1` | 2026-10-17T060351219144 -> 2026-11-28T150335920642 | 2 changed | quiet |
| 2026-11-28 | `remote/com.heroxairdomes/mcp` | 2026-11-27T171509588958 -> 2026-11-28T150329656961 | 9 changed, 3 added (every tool) | quiet |
| 2026-11-28 | `remote/com.yazilimkocu/erp` | 2026-11-26T173140131532 -> 2026-11-28T150316776204 | 1 changed | quiet |
| 2026-11-28 | `remote/com.yazilimkocu/crm` | 2026-11-26T173139626581 -> 2026-11-28T150316989319 | 1 changed | quiet |
| 2026-11-28 | `remote/com.dunnestates/aspen-penthouse` | 2026-11-09T170119980641 -> 2026-11-28T150315835070 | 1 changed | quiet |
| 2026-11-28 | `remote/com.calmido/phone-number-lookup` | 2026-10-29T212835320105 -> 2026-11-28T150307177749 | 1 changed | quiet |
| 2026-11-28 | `remote/com.serverscan/mcp` | 2026-11-12T074810782678 -> 2026-11-28T150252237798 | 1 changed | quiet |
| 2026-11-28 | `remote/ai.reel-e/reel-e` | 2026-11-10T152957840387 -> 2026-11-28T150250029432 | 2 changed, 1 added | quiet |
| 2026-11-28 | `remote/io.github.ssitdeveloper/zorqelio` | 2026-11-27T145254558857 -> 2026-11-28T150246393036 | 5 changed | quiet |
| 2026-11-28 | `remote/io.github.cyanheads/worldbank-mcp-server` | 2026-11-19T162442229678 -> 2026-11-28T150243260070 | 3 changed | quiet |
| 2026-11-28 | `remote/cz.bydleno/prodeje` | 2026-11-17T165014483682 -> 2026-11-28T150244065071 | 1 changed | quiet |
| 2026-11-28 | `remote/page.wordy/wordy-page.1` | 2026-11-24T165444888986 -> 2026-11-28T150241661355 | 2 changed | quiet |
| 2026-11-28 | `remote/io.github.shaozhengkun123/yarrow` | 2026-09-23T163152183888 -> 2026-11-28T150241007984 | 1 changed | quiet |
| 2026-11-28 | `remote/com.onancap/supplier` | 2026-11-18T080324732758 -> 2026-11-28T150240235220 | 1 changed | quiet |
| 2026-11-28 | `remote/xyz.quantumatlas/x402-payment-hub` | 2026-11-28T083144074493 -> 2026-11-28T150239388756 | 14 changed | quiet |
| 2026-11-28 | `remote/com.yazilimkocu/ajan` | 2026-11-26T173203384324 -> 2026-11-28T150235532207 | 1 changed | quiet |
| 2026-11-28 | `remote/net.jpbiz/japan-business-trip` | 2026-11-23T185524011754 -> 2026-11-28T150228360003 | 3 changed (every tool) | quiet |
| 2026-11-28 | `remote/com.uicapsule/components` | 2026-11-23T185513378556 -> 2026-11-28T150227958689 | 2 changed (every tool) | quiet |
| 2026-11-28 | `remote/studio.gradients/mcp` | 2026-11-28T083206221462 -> 2026-11-28T150219884074 | 1 changed | quiet |
| 2026-11-28 | `remote/com.step2gcode/step2gcode.1` | 2026-11-19T162512421374 -> 2026-11-28T150220053994 | 1 changed | quiet |
| 2026-11-28 | `remote/ai.whatagentswant/wall` | 2026-11-23T185215356109 -> 2026-11-28T150222194935 | 1 changed | quiet |
| 2026-11-28 | `remote/fyi.selah/rates` | 2026-10-17T060454983153 -> 2026-11-28T150214779203 | 2 changed (every tool) | quiet |
| 2026-11-28 | `remote/com.sapiensinteticos/sapiens` | 2026-11-24T165807132578 -> 2026-11-28T150213055289 | 1 changed | quiet |
| 2026-11-28 | `remote/no.restplass/travel-search` | 2026-11-28T083142752960 -> 2026-11-28T150211272426 | 1 changed | quiet |
| 2026-11-28 | `remote/io.github.cooyun/etuki-finops-mcp` | 2026-11-09T170259521288 -> 2026-11-28T150207953932 | 9 changed, 2 added (every tool) | quiet |
| 2026-11-28 | `remote/app.floot.via-router/via-gateway` | 2026-11-24T165414384074 -> 2026-11-28T150208095280 | 1 added | review |
| 2026-11-28 | `remote/com.domhaul/mcp` | 2026-10-26T133521264363 -> 2026-11-28T150203978701 | 1 changed | quiet |
| 2026-11-28 | `remote/com.meridiandispatch/travel-guides` | 2026-11-16T122923869344 -> 2026-11-28T150156269901 | 1 changed | quiet |
| 2026-11-28 | `remote/io.github.rich937/lendmail` | 2026-11-20T105905673274 -> 2026-11-28T150153479481 | 3 changed, 1 added | quiet |
| 2026-11-28 | `remote/io.github.FTHTrading/genesis402-mcp` | 2026-11-24T182232790257 -> 2026-11-28T150142457089 | 1 changed | quiet |
| 2026-11-28 | `remote/io.trueinterview/trueinterview` | 2026-11-28T083155158952 -> 2026-11-28T150137912633 | 32 changed | quiet |
| 2026-11-28 | `remote/com.findleademails/mcp` | 2026-11-15T115324670706 -> 2026-11-28T150136656855 | 6 changed (every tool) | quiet |
| 2026-11-28 | `remote/fi.akkilahdot/travel-search` | 2026-11-28T083204810264 -> 2026-11-28T150135040201 | 1 changed | quiet |
| 2026-11-28 | `remote/ai.dsght/public` | 2026-10-17T060431641669 -> 2026-11-28T150133249973 | 8 changed, 4 removed (every tool) | quiet |
| 2026-11-28 | `remote/io.deeplead/deeplead` | 2026-11-27T145142602386 -> 2026-11-28T150128149590 | 37 changed (every tool) | quiet |
| 2026-11-28 | `remote/com.breadboardhub/circuits` | 2026-11-27T171447342916 -> 2026-11-28T150120562972 | 18 changed (every tool) | quiet |
| 2026-11-28 | `remote/dev.workers.restockalarm.token-safety-mcp/token-safety` | 2026-11-09T165947803000 -> 2026-11-28T150118126302 | 5 changed (every tool) | quiet |
| 2026-11-28 | `remote/io.github.nirholas/threews-3d-studio-free` | 2026-11-22T073253302004 -> 2026-11-28T150112245875 | 1 changed | quiet |
| 2026-11-28 | `remote/com.aiseocrew.www/ai-seo-crew` | 2026-11-17T164852155727 -> 2026-11-28T150112408320 | 8 changed | quiet |
| 2026-11-28 | `remote/dk.afbudsrejser/travel-search` | 2026-11-28T083140696354 -> 2026-11-28T150110367464 | 1 changed | quiet |
| 2026-11-28 | `remote/io.github.cyanheads/wsdot-mcp-server` | 2026-11-12T154954955498 -> 2026-11-28T150109058621 | 7 changed | review |
| 2026-11-28 | `remote/com.thedealsdatabase/deals` | 2026-11-23T185106543526 -> 2026-11-28T150106628911 | 1 changed | quiet |
| 2026-11-28 | `remote/io.github.cyanheads/wikipedia-mcp-server` | 2026-11-12T154946337990 -> 2026-11-28T150103230058 | 4 changed | quiet |
| 2026-11-28 | `remote/com.whatsonmiami/whats-on-miami` | 2026-11-21T014812709380 -> 2026-11-28T150059691088 | 4 changed, 4 added | quiet |
| 2026-11-28 | `remote/com.voyscout/price-history` | 2026-11-08T135715656540 -> 2026-11-28T150059388527 | 4 changed | quiet |
| 2026-11-28 | `remote/ai.wem3/wem-price-compare` | 2026-11-27T145110712628 -> 2026-11-28T150058762651 | 4 changed | quiet |
| 2026-11-28 | `remote/com.yippigo/yippigo` | 2026-11-25T110017253642 -> 2026-11-28T150055758060 | 1 changed | quiet |
| 2026-11-28 | `remote/com.visdenda/public` | 2026-11-28T083201954827 -> 2026-11-28T150056092361 | 1 changed, 1 added | quiet |
| 2026-11-28 | `remote/jp.wariwari/wariwari` | 2026-11-24T165634257979 -> 2026-11-28T150050824430 | 4 changed | quiet |
| 2026-11-28 | `remote/com.xmlvalid/xmlvalid` | 2026-11-24T170305992739 -> 2026-11-28T150050993269 | 1 changed | quiet |
| 2026-11-28 | `remote/dev.workers.veritas-silicea.veritas-silicea-shop/art` | 2026-11-27T145340240403 -> 2026-11-28T150047948267 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 100130 substantive, 47245 that changed only numbers (a catalogue counter ticking, a date), 1265 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 82353 | 38412 | 43941 | 0 |
| `a2awire.com` | 4371 | 4371 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 571 | 571 | 0 | 0 |
| `modevc.com` | 568 | 568 | 0 | 0 |
| `civai.co` | 403 | 403 | 0 | 0 |
| `revmesh2074.workers.dev` | 381 | 321 | 60 | 0 |
| `sistaminuten.se` | 294 | 7 | 0 | 287 |
| `afbudsrejser.dk` | 293 | 7 | 0 | 286 |
| `akkilahdot.fi` | 293 | 7 | 0 | 286 |
| `restplass.no` | 293 | 7 | 0 | 286 |
| `socialloop.ai` | 283 | 283 | 0 | 0 |
| 11969 other operators | 56196 | 52832 | 3244 | 120 |
