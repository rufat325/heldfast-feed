# MCP server tool changes

Last change observed 2026-11-17T23:44:13+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

111244 changes to a tool definition: 4505 npm releases (4259 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 106739 readings of hosted servers that found their tools changed; 4314 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-17 | `remote/xn--3ds443g.xn--s7y/duan-online` | 2026-11-17T031630127698 -> 2026-11-17T234415314258 | 2 changed | quiet |
| 2026-11-17 | `remote/com.yangopen/mcp` | 2026-11-17T165000310170 -> 2026-11-17T234414073179 | 1 removed | quiet |
| 2026-11-17 | `remote/io.taifoon/coordination-layer.1` | 2026-11-17T135643889303 -> 2026-11-17T234408987574 | 1 changed | review |
| 2026-11-17 | `remote/se.sistaminuten/travel-search` | 2026-11-17T164902439962 -> 2026-11-17T234411531681 | 1 changed | quiet |
| 2026-11-17 | `remote/com.mintlify/searchmcp` | 2026-11-17T164941825177 -> 2026-11-17T234408002983 | 1 changed | quiet |
| 2026-11-17 | `remote/studio.gradients/mcp` | 2026-11-17T164929995773 -> 2026-11-17T234404950235 | 1 changed | quiet |
| 2026-11-17 | `remote/com.ortopedialowcost/ortopedia-catalog` | 2026-11-16T190145114279 -> 2026-11-17T234406138276 | 3 changed | quiet |
| 2026-11-17 | `remote/com.kaicalls/kaicalls` | 2026-11-17T164820886351 -> 2026-11-17T234401793437 | 4 changed, 2 added | quiet |
| 2026-11-17 | `remote/com.youspot/youspot` | 2026-11-17T135701979327 -> 2026-11-17T234400337032 | 2 added | quiet |
| 2026-11-17 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-17T031607311450 -> 2026-11-17T234400543320 | 2 changed | quiet |
| 2026-11-17 | `remote/fi.akkilahdot/travel-search` | 2026-11-17T164906997927 -> 2026-11-17T234359076544 | 1 changed | quiet |
| 2026-11-17 | `remote/com.vedutum/vedutum` | 2026-11-15T212308653500 -> 2026-11-17T234358337417 | 1 changed | quiet |
| 2026-11-17 | `remote/no.restplass/travel-search` | 2026-11-17T164943001839 -> 2026-11-17T234355504743 | 1 changed | quiet |
| 2026-11-17 | `remote/io.github.whisper-sec/whisper` | 2026-11-17T164855124048 -> 2026-11-17T234356164814 | 24 changed | quiet |
| 2026-11-17 | `remote/com.vet402/vet402` | 2026-11-17T164637967236 -> 2026-11-17T234348245249 | 1 changed, 1 added | quiet |
| 2026-11-17 | `remote/io.github.utilify-io/utilify-mcp` | 2026-11-16T072200934211 -> 2026-11-17T234346473446 | 3 changed | quiet |
| 2026-11-17 | `remote/io.deeplead/deeplead` | 2026-11-15T142539844539 -> 2026-11-17T234346973926 | 2 added | quiet |
| 2026-11-17 | `remote/app.usesnippet/snippet` | 2026-11-16T122851776932 -> 2026-11-17T234345700922 | 1 changed | quiet |
| 2026-11-17 | `remote/io.github.jgmale123/blockchainiq-x402-remote` | 2026-11-17T164749709404 -> 2026-11-17T234345578802 | 1 changed | quiet |
| 2026-11-17 | `remote/com.withpanta/panta` | 2026-11-17T164736325760 -> 2026-11-17T234346121496 | 1 changed | quiet |
| 2026-11-17 | `remote/com.uipolish/mcp` | 2026-11-17T164606934736 -> 2026-11-17T234345518242 | 3 changed, 1 removed (every tool) | quiet |
| 2026-11-17 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-17T135627385332 -> 2026-11-17T234344818868 | 1 changed | quiet |
| 2026-11-17 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-17T135628484489 -> 2026-11-17T234345729927 | 2 changed | quiet |
| 2026-11-17 | `remote/co.codeways/codeways-mcp` | 2026-11-15T115702674961 -> 2026-11-17T234343319970 | 6 changed, 3 added (every tool) | review |
| 2026-11-17 | `remote/dk.afbudsrejser/travel-search` | 2026-11-17T164850583855 -> 2026-11-17T234341825577 | 1 changed | quiet |
| 2026-11-17 | `remote/io.github.tollnodemcp/tollnode` | 2026-11-17T135625856932 -> 2026-11-17T234341639072 | 2 changed, 2 added | review |
| 2026-11-17 | `remote/health.telo/telo` | 2026-11-16T190117958696 -> 2026-11-17T234340325446 | 1 changed | quiet |
| 2026-11-17 | `remote/io.github.brawlaphant/vealth` | 2026-11-17T164644588048 -> 2026-11-17T234339501365 | 5 changed, 6 added | review |
| 2026-11-17 | `remote/io.github.Voopa-Corp/render-check` | 2026-11-17T135643741254 -> 2026-11-17T234337019177 | 2 changed, 2 added | quiet |
| 2026-11-17 | `remote/ec.tributasoft/documentacion` | 2026-11-17T135647876803 -> 2026-11-17T234338839848 | 3 changed | quiet |
| 2026-11-17 | `remote/com.triremes/triremes` | 2026-11-15T115620066869 -> 2026-11-17T234336976156 | 1 changed | quiet |
| 2026-11-17 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-17T164617671271 -> 2026-11-17T234335292612 | 3 changed | quiet |
| 2026-11-17 | `remote/ai.trydock/dock` | 2026-11-16T122757998223 -> 2026-11-17T234332806690 | 2 changed | quiet |
| 2026-11-17 | `remote/cc.thecolony/mcp-server` | 2026-11-17T164549334160 -> 2026-11-17T234333519698 | 1 changed, 2 added | quiet |
| 2026-11-17 | `remote/app.shvl/shvl` | 2026-11-15T115343235799 -> 2026-11-17T234331917313 | 5 changed | quiet |
| 2026-11-17 | `remote/com.trackerhacker/mcp` | 2026-11-17T135639884969 -> 2026-11-17T234331273508 | 4 changed | quiet |
| 2026-11-17 | `remote/com.shortlistsaas/shortlist` | 2026-11-16T162841179606 -> 2026-11-17T234331732059 | 3 changed | quiet |
| 2026-11-17 | `remote/io.github.t0ll-xyz/toll` | 2026-11-17T164523666683 -> 2026-11-17T234330287277 | 4 changed, 1 added | quiet |
| 2026-11-17 | `remote/io.github.PascalSun/talk2geo` | 2026-11-17T135641756110 -> 2026-11-17T234331870027 | 20 added | quiet |
| 2026-11-17 | `remote/io.github.MorrisMoe/soulintime` | 2026-11-17T135617575582 -> 2026-11-17T234331183164 | 1 changed | quiet |
| 2026-11-17 | `remote/com.serviche/sergio` | 2026-11-16T072232424803 -> 2026-11-17T234334385378 | 2 changed | quiet |
| 2026-11-17 | `remote/com.idosgames/platform` | 2026-11-17T164409677563 -> 2026-11-17T234329871058 | 28 changed, 2 added | quiet |
| 2026-11-17 | `remote/dev.ytriple.storetechscan/storetechscan` | 2026-11-16T163017605044 -> 2026-11-17T234328853830 | 1 changed | quiet |
| 2026-11-17 | `remote/com.thedesignprint/designprint` | 2026-11-16T163038555784 -> 2026-11-17T234328177821 | 3 changed | quiet |
| 2026-11-17 | `remote/uk.co.tenderlead/tenderlead` | 2026-11-15T142355371881 -> 2026-11-17T234326730307 | 4 changed | quiet |
| 2026-11-17 | `remote/pro.telehealthnearme/telehealth-compare` | 2026-11-17T135634643939 -> 2026-11-17T234325774516 | 1 added | quiet |
| 2026-11-17 | `remote/help.socket/socket-help` | 2026-11-16T162956751871 -> 2026-11-17T234328555180 | 3 changed | quiet |
| 2026-11-17 | `remote/com.remoshift/jobs` | 2026-11-17T164452044267 -> 2026-11-17T234326374817 | 1 changed | quiet |
| 2026-11-17 | `remote/com.sfxmint/sounds` | 2026-11-15T115425300506 -> 2026-11-17T234323939228 | 1 changed, 2 added | quiet |
| 2026-11-17 | `remote/no.pristavla/pristavla` | 2026-11-17T031530063665 -> 2026-11-17T234323373832 | 1 changed | quiet |
| 2026-11-17 | `remote/now.salesjobs/mcp` | 2026-11-17T164352302140 -> 2026-11-17T234322350252 | 1 changed | quiet |
| 2026-11-17 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-17T135633181746 -> 2026-11-17T234321812760 | 1 added | quiet |
| 2026-11-17 | `remote/io.rmassistanthub/assistant-hub` | 2026-11-16T122451031934 -> 2026-11-17T234320465260 | 1 changed | quiet |
| 2026-11-17 | `remote/io.github.Nicoiakl/rosetta-quantum-pqc` | 2026-11-16T162849765282 -> 2026-11-17T234319824316 | 2 changed | quiet |
| 2026-11-17 | `remote/com.kindoflost.roth-conversion-calculator/roth-conversion-calculator` | 2026-11-16T162851117082 -> 2026-11-17T234320256829 | 1 changed | quiet |
| 2026-11-17 | `remote/io.github.mazeasdamien/rising-shores-singapore` | 2026-11-17T164340671199 -> 2026-11-17T234319223680 | 1 changed | quiet |
| 2026-11-17 | `remote/pl.klyo/games` | 2026-11-15T002315793437 -> 2026-11-17T234319240348 | 2 changed | quiet |
| 2026-11-17 | `remote/gg.plazmi/plazmi` | 2026-11-17T031541445121 -> 2026-11-17T234317511198 | 2 changed | quiet |
| 2026-11-17 | `remote/io.ddx.pg/archive` | 2026-11-16T072152317826 -> 2026-11-17T234316994118 | 130 changed (every tool) | quiet |
| 2026-11-17 | `remote/com.registryverify/florida-sunbiz-business-kyb` | 2026-11-16T162736710858 -> 2026-11-17T234314455526 | 3 changed, 1 added (every tool) | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 69323 substantive, 40849 that changed only numbers (a catalogue counter ticking, a date), 1072 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 59946 | 21593 | 38353 | 0 |
| `a2awire.com` | 3107 | 3107 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 461 | 461 | 0 | 0 |
| `civai.co` | 368 | 368 | 0 | 0 |
| `modevc.com` | 349 | 349 | 0 | 0 |
| `revmesh2074.workers.dev` | 295 | 256 | 39 | 0 |
| `sistaminuten.se` | 250 | 6 | 0 | 244 |
| `afbudsrejser.dk` | 249 | 6 | 0 | 243 |
| `akkilahdot.fi` | 249 | 6 | 0 | 243 |
| `restplass.no` | 249 | 6 | 0 | 243 |
| `socialloop.ai` | 241 | 241 | 0 | 0 |
| 9993 other operators | 43139 | 40583 | 2457 | 99 |
