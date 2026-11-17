# MCP server tool changes

Last change observed 2026-11-17T16:50:18+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

110997 changes to a tool definition: 4505 npm releases (4259 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 106492 readings of hosted servers that found their tools changed; 4298 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-17 | `remote/io.github.zodiacs-org/zodiacs` | 2026-11-14T183421363821 -> 2026-11-17T165019623250 | 10 changed | quiet |
| 2026-11-17 | `remote/app.zolvaagent/zolva` | 2026-11-16T163305729774 -> 2026-11-17T165020324478 | 1 changed | quiet |
| 2026-11-17 | `remote/ai.zairalabs/guide` | 2026-11-13T120655719384 -> 2026-11-17T165016946030 | 1 changed | quiet |
| 2026-11-17 | `remote/io.github.makloai/yoya-booking` | 2026-09-23T163000074707 -> 2026-11-17T165015350749 | 7 changed (every tool) | quiet |
| 2026-11-17 | `remote/cz.bydleno/prodeje` | 2026-11-02T163646763203 -> 2026-11-17T165014483682 | 1 changed | quiet |
| 2026-11-17 | `remote/app.vercel.ora-x402-gateway/sensations-mergulho` | 2026-10-28T133522507927 -> 2026-11-17T165005427585 | 1 changed | quiet |
| 2026-11-17 | `remote/com.yangopen/mcp` | 2026-11-13T150716441936 -> 2026-11-17T165000310170 | 1 added | quiet |
| 2026-11-17 | `remote/com.vehiclehistorybyvin/vehicle-history-by-vin` | 2026-11-02T163633223400 -> 2026-11-17T165000265109 | 3 changed (every tool) | quiet |
| 2026-11-17 | `remote/com.theaiintegrationhub/use-cases` | 2026-10-31T130432080038 -> 2026-11-17T165000137948 | 1 changed | quiet |
| 2026-11-17 | `remote/io.github.sudzikcoin/suverse-agent-assistant` | 2026-11-17T135656698438 -> 2026-11-17T164954946001 | 3 changed | quiet |
| 2026-11-17 | `remote/com.patchmcp/patch` | 2026-11-12T155326270466 -> 2026-11-17T164945496865 | 1 changed, 1 added | quiet |
| 2026-11-17 | `remote/com.watheeqahr/attendance-analyzer` | 2026-11-02T163451079414 -> 2026-11-17T164944268817 | 1 changed | quiet |
| 2026-11-17 | `remote/at.schitterhof.www/camping` | 2026-11-02T163621687166 -> 2026-11-17T164946131986 | 6 changed (every tool) | quiet |
| 2026-11-17 | `remote/no.restplass/travel-search` | 2026-11-17T135654184602 -> 2026-11-17T164943001839 | 1 changed | quiet |
| 2026-11-17 | `remote/com.mintlify/searchmcp` | 2026-11-14T010706544369 -> 2026-11-17T164941825177 | 1 changed | quiet |
| 2026-11-17 | `remote/ai.modulos/demo-booking` | 2026-11-13T200755153637 -> 2026-11-17T164941973665 | 2 changed, 1 added | quiet |
| 2026-11-17 | `remote/com.kaicalls/kaicalls.1` | 2026-11-12T170947269043 -> 2026-11-17T164935431019 | 2 changed | quiet |
| 2026-11-17 | `remote/ai.usedby/usedby` | 2026-11-17T135644579616 -> 2026-11-17T164933687291 | 1 changed | quiet |
| 2026-11-17 | `remote/tr.com.isinn.www/isinn` | 2026-11-09T170316069830 -> 2026-11-17T164933803514 | 2 changed | quiet |
| 2026-11-17 | `remote/app.nailme/nailme` | 2026-11-09T170404485364 -> 2026-11-17T164933247008 | 2 changed | quiet |
| 2026-11-17 | `remote/studio.gradients/mcp` | 2026-11-17T135642479988 -> 2026-11-17T164929995773 | 1 changed | quiet |
| 2026-11-17 | `remote/io.github.Wei-LienWU/pit-fundamentals` | 2026-11-10T030050517238 -> 2026-11-17T164928136426 | 3 added | quiet |
| 2026-11-17 | `remote/com.kulicadvisory/aictionbot-werkbank` | 2026-11-17T135651628345 -> 2026-11-17T164925488169 | 3 changed, 1 added | quiet |
| 2026-11-17 | `remote/de.firma/rechner` | 2026-11-17T135642059930 -> 2026-11-17T164924923786 | 3 added | quiet |
| 2026-11-17 | `remote/io.github.AG-ITAcademy/home-fitness-exercise-library` | 2026-11-02T163601322474 -> 2026-11-17T164923445214 | 1 changed | quiet |
| 2026-11-17 | `remote/com.theagentcolosseum/agent-colosseum` | 2026-11-16T163256517208 -> 2026-11-17T164925033446 | 6 changed (every tool) | quiet |
| 2026-11-17 | `remote/com.expressnumber/mcp` | 2026-11-09T170259779672 -> 2026-11-17T164922578447 | 2 changed | quiet |
| 2026-11-17 | `remote/work.funfriday/funfriday` | 2026-11-12T155030452539 -> 2026-11-17T164917276305 | 1 changed | quiet |
| 2026-11-17 | `remote/com.swiftprobate/probate` | 2026-11-15T212138893734 -> 2026-11-17T164911967711 | 1 changed | quiet |
| 2026-11-17 | `remote/io.suverse.www/catalog` | 2026-11-17T135644464239 -> 2026-11-17T164911182784 | 3 changed | quiet |
| 2026-11-17 | `remote/fi.akkilahdot/travel-search` | 2026-11-17T135639304341 -> 2026-11-17T164906997927 | 1 changed | quiet |
| 2026-11-17 | `remote/io.github.eamwhite1/agent-trust` | 2026-11-15T115839768464 -> 2026-11-17T164904737405 | 1 changed | quiet |
| 2026-11-17 | `remote/de.wospeicher/catalog` | 2026-10-28T212423521907 -> 2026-11-17T164903389093 | 3 changed (every tool) | quiet |
| 2026-11-17 | `remote/app.wuai/wuai` | 2026-11-16T163132192788 -> 2026-11-17T164903200925 | 1 added, 1 removed | quiet |
| 2026-11-17 | `remote/se.sistaminuten/travel-search` | 2026-11-17T135642838196 -> 2026-11-17T164902439962 | 1 changed | quiet |
| 2026-11-17 | `remote/io.christiantechjobs/jobs` | 2026-11-09T170335892590 -> 2026-11-17T164902214694 | 3 changed (every tool) | quiet |
| 2026-11-17 | `remote/com.christianjobslist/jobs` | 2026-11-09T170334428812 -> 2026-11-17T164900680281 | 3 changed (every tool) | quiet |
| 2026-11-17 | `remote/io.github.Fizzl13/x402-doctor` | 2026-11-13T120029284112 -> 2026-11-17T164859750815 | 1 added | quiet |
| 2026-11-17 | `remote/de.wolaptop/catalog` | 2026-10-28T212422085281 -> 2026-11-17T164859976965 | 3 changed (every tool) | quiet |
| 2026-11-17 | `remote/de.wokonsole/catalog` | 2026-10-28T212421448694 -> 2026-11-17T164900221831 | 3 changed (every tool) | quiet |
| 2026-11-17 | `remote/io.github.whisper-sec/whisper` | 2026-11-07T133633935476 -> 2026-11-17T164855124048 | 1 added | quiet |
| 2026-11-17 | `remote/com.aiseocrew.www/ai-seo-crew` | 2026-11-12T154958106460 -> 2026-11-17T164852155727 | 1 changed | quiet |
| 2026-11-17 | `remote/dk.afbudsrejser/travel-search` | 2026-11-17T135645992566 -> 2026-11-17T164850583855 | 1 changed | quiet |
| 2026-11-17 | `remote/de.wouhr/catalog` | 2026-10-28T212519302346 -> 2026-11-17T164847233612 | 3 changed (every tool) | quiet |
| 2026-11-17 | `remote/de.wosneaker/catalog` | 2026-10-28T212517817148 -> 2026-11-17T164847053392 | 3 changed (every tool) | quiet |
| 2026-11-17 | `remote/io.github.Atenkai/smasher-studio` | 2026-10-30T133016947916 -> 2026-11-17T164844580911 | 2 changed | review |
| 2026-11-17 | `remote/de.wopool/catalog` | 2026-10-28T212517829648 -> 2026-11-17T164845406235 | 3 changed (every tool) | quiet |
| 2026-11-17 | `remote/io.github.witanmarkets/witan` | 2026-11-04T150730140040 -> 2026-11-17T164843236118 | 1 changed | quiet |
| 2026-11-17 | `remote/com.waystationagents/commons` | 2026-10-17T055910625883 -> 2026-11-17T164843917167 | 8 changed, 1 added (every tool) | quiet |
| 2026-11-17 | `remote/com.onlyworlds/mcp` | 2026-11-14T010657631032 -> 2026-11-17T164839429341 | 1 changed | quiet |
| 2026-11-17 | `remote/org.omenz.www/agent-tools` | 2026-11-17T031623261196 -> 2026-11-17T164838708105 | 2 changed | review |
| 2026-11-17 | `remote/sk.nakus/unit-price` | 2026-11-10T130414273501 -> 2026-11-17T164835552583 | 1 changed | quiet |
| 2026-11-17 | `remote/fr.partner-construction/assurance-decennale` | 2026-11-02T163915948887 -> 2026-11-17T164834086944 | 1 changed | quiet |
| 2026-11-17 | `remote/com.visionlibra/catalog` | 2026-11-09T170204530793 -> 2026-11-17T164831986287 | 1 changed | quiet |
| 2026-11-17 | `remote/de.objelio/immobiliensuche` | 2026-11-08T204946056364 -> 2026-11-17T164833016902 | 4 changed | quiet |
| 2026-11-17 | `remote/io.github.suanrongbaicai/vibecodepicks` | 2026-11-13T120507050391 -> 2026-11-17T164828060047 | 2 changed | quiet |
| 2026-11-17 | `remote/io.github.edbror/watr-software-oracle` | 2026-11-09T170303654429 -> 2026-11-17T164827963685 | 5 changed (every tool) | quiet |
| 2026-11-17 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-17T135636132524 -> 2026-11-17T164827671816 | 3 changed | quiet |
| 2026-11-17 | `remote/com.kaicalls/kaicalls` | 2026-11-17T031621513477 -> 2026-11-17T164820886351 | 2 changed, 2 added | quiet |
| 2026-11-17 | `remote/com.kineticist/mcp-server` | 2026-10-30T132956797755 -> 2026-11-17T164820313873 | 10 changed (every tool) | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 69097 substantive, 40833 that changed only numbers (a catalogue counter ticking, a date), 1067 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 59946 | 21593 | 38353 | 0 |
| `a2awire.com` | 3107 | 3107 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 461 | 461 | 0 | 0 |
| `civai.co` | 368 | 368 | 0 | 0 |
| `modevc.com` | 349 | 349 | 0 | 0 |
| `revmesh2074.workers.dev` | 295 | 256 | 39 | 0 |
| `sistaminuten.se` | 249 | 6 | 0 | 243 |
| `afbudsrejser.dk` | 248 | 6 | 0 | 242 |
| `akkilahdot.fi` | 248 | 6 | 0 | 242 |
| `restplass.no` | 248 | 6 | 0 | 242 |
| `socialloop.ai` | 240 | 240 | 0 | 0 |
| 9957 other operators | 42897 | 40358 | 2441 | 98 |
