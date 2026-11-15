# MCP server tool changes

Last change observed 2026-11-15T21:23:06+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

104211 changes to a tool definition: 4274 npm releases (4028 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 99937 readings of hosted servers that found their tools changed; 4167 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-15 | `remote/com.vedutum/vedutum` | 2026-11-13T120026146347 -> 2026-11-15T212308653500 | 1 changed | quiet |
| 2026-11-15 | `remote/ai.oriiion/oriiion` | 2026-11-15T142741411761 -> 2026-11-15T212306226425 | 2 changed | quiet |
| 2026-11-15 | `remote/io.suverse.versum/catalog` | 2026-11-15T115648838790 -> 2026-11-15T212310533607 | 3 changed | quiet |
| 2026-11-15 | `remote/app.floot.via-router/via-gateway` | 2026-11-13T115849095275 -> 2026-11-15T212301247880 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.eyeinthesky6/unseen-workflow-compiler` | 2026-11-15T115631442060 -> 2026-11-15T212300594246 | 1 changed | quiet |
| 2026-11-15 | `remote/cc.thecolony/mcp-server` | 2026-11-15T002321392574 -> 2026-11-15T212258939370 | 2 changed | quiet |
| 2026-11-15 | `remote/io.github.PascalSun/talk2geo` | 2026-11-15T155605583281 -> 2026-11-15T212258137297 | 20 removed | quiet |
| 2026-11-15 | `remote/help.socket/socket-help` | 2026-11-15T002319395265 -> 2026-11-15T212256554448 | 3 changed | quiet |
| 2026-11-15 | `remote/now.salesjobs/mcp` | 2026-11-15T142347364032 -> 2026-11-15T212250393802 | 1 changed | quiet |
| 2026-11-15 | `remote/app.pitbi/pitbi` | 2026-11-15T115251595249 -> 2026-11-15T212247066510 | 3 added | quiet |
| 2026-11-15 | `remote/dev.pdfops/pdfops-mcp` | 2026-11-15T071613859295 -> 2026-11-15T212246072683 | 1 changed, 2 added | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-lagos_life` | 2026-11-15T142153906752 -> 2026-11-15T212244400111 | 32 added, 1 removed | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-juicyway` | 2026-11-15T142153908128 -> 2026-11-15T212243652650 | 23 added, 1 removed | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-hacker_news` | 2026-11-15T142153891948 -> 2026-11-15T212243677848 | 14 added, 1 removed | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-bgpt-yarngpt` | 2026-11-15T142153729316 -> 2026-11-15T212243666232 | 4 added, 1 removed | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-bgpt-pdf-generator` | 2026-11-15T142153444426 -> 2026-11-15T212243643884 | 7 added, 1 removed | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-bgpt-livescore` | 2026-11-15T142153410018 -> 2026-11-15T212243625500 | 12 added, 1 removed | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-bgpt-instagram-android` | 2026-11-15T142153422281 -> 2026-11-15T212243630522 | 16 added, 1 removed | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-bgpt-cacnigeria` | 2026-11-15T142153319905 -> 2026-11-15T212243693604 | 3 added, 1 removed | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-audience-resolver` | 2026-11-15T142153038189 -> 2026-11-15T212243748717 | 45 added, 1 removed | quiet |
| 2026-11-15 | `remote/dev.notavibe/mcp` | 2026-11-15T142150940471 -> 2026-11-15T212242540722 | 3 changed | quiet |
| 2026-11-15 | `remote/io.github.sudomichael/mcpserverlist-mcp` | 2026-11-15T115108280999 -> 2026-11-15T212239171035 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.eins78/meteoswiss-mcp` | 2026-11-15T115118876518 -> 2026-11-15T212242374610 | 2 changed | quiet |
| 2026-11-15 | `remote/com.midasiteurope/civil-nx` | 2026-11-14T183306726752 -> 2026-11-15T212239754131 | 108 changed (every tool) | quiet |
| 2026-11-15 | `remote/org.walkably/walkably` | 2026-11-14T135454503586 -> 2026-11-15T212238030927 | 1 changed | quiet |
| 2026-11-15 | `remote/com.squirrelscan/squirrelscan` | 2026-11-15T142015370686 -> 2026-11-15T212233437376 | 2 changed, 4 added | quiet |
| 2026-11-15 | `remote/com.complyonsite/tools` | 2026-11-13T115112650265 -> 2026-11-15T212208561502 | 1 added | quiet |
| 2026-11-15 | `remote/no.restplass/travel-search` | 2026-11-15T155631324838 -> 2026-11-15T212159179995 | 1 changed | quiet |
| 2026-11-15 | `remote/co.ainumbers/tools` | 2026-11-15T071553748475 -> 2026-11-15T212201741909 | 1 changed | quiet |
| 2026-11-15 | `remote/dk.afbudsrejser/travel-search` | 2026-11-15T155629110042 -> 2026-11-15T212156524459 | 1 changed | quiet |
| 2026-11-15 | `remote/studio.gradients/mcp` | 2026-11-15T155633784032 -> 2026-11-15T212155566377 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.EasyGerber/easygerber` | 2026-11-14T010704857783 -> 2026-11-15T212154972242 | 10 changed | quiet |
| 2026-11-15 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-15T002328732963 -> 2026-11-15T212153998547 | 4 changed | quiet |
| 2026-11-15 | `remote/fi.akkilahdot/travel-search` | 2026-11-15T155633060315 -> 2026-11-15T212153681635 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-15T115544374881 -> 2026-11-15T212151556755 | 1 changed | quiet |
| 2026-11-15 | `remote/dev.vetagent/vetagent` | 2026-11-15T155630622586 -> 2026-11-15T212151296909 | 1 changed | quiet |
| 2026-11-15 | `remote/racing.kerbside/f1` | 2026-11-15T114617347115 -> 2026-11-15T212151070247 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-15T071608953320 -> 2026-11-15T212148175559 | 1 changed | quiet |
| 2026-11-15 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-15T115453495779 -> 2026-11-15T212148746235 | 2 changed | quiet |
| 2026-11-15 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-15T155623340940 -> 2026-11-15T212142468491 | 1 changed | quiet |
| 2026-11-15 | `remote/io.sibidz/sibidz` | 2026-11-14T135925496994 -> 2026-11-15T212142878672 | 3 changed, 5 added, 5 removed (every tool) | quiet |
| 2026-11-15 | `remote/se.sistaminuten/travel-search` | 2026-11-15T155607394377 -> 2026-11-15T212138323849 | 1 changed | quiet |
| 2026-11-15 | `remote/de.overfit/overfit` | 2026-11-13T120006668699 -> 2026-11-15T212138723445 | 2 changed | quiet |
| 2026-11-15 | `remote/com.swiftprobate/probate` | 2026-11-15T115640126353 -> 2026-11-15T212138893734 | 1 changed | quiet |
| 2026-11-15 | `remote/ch.kulalabs.pazair/pazair` | 2026-11-15T142057907412 -> 2026-11-15T212139163219 | 1 added | quiet |
| 2026-11-15 | `remote/com.remoshift/jobs` | 2026-11-15T155617690636 -> 2026-11-15T212136379189 | 1 changed | quiet |
| 2026-11-15 | `remote/com.pondchat/pondchat` | 2026-11-15T115225187504 -> 2026-11-15T212134963933 | 1 changed | quiet |
| 2026-11-15 | `remote/com.blitzreels/blitzreels` | 2026-11-15T002328485438 -> 2026-11-15T212139685523 | 5 changed | quiet |
| 2026-11-15 | `remote/com.anchorterminal/anchor-terminal` | 2026-11-14T140243503740 -> 2026-11-15T212136112197 | 2 added | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-bgpt-polymarket` | 2026-11-15T142030426071 -> 2026-11-15T212135524007 | 20 added, 1 removed | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-bgpt-giglogistics` | 2026-11-15T142030391302 -> 2026-11-15T212135326817 | 3 added, 1 removed | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-apple_developer` | 2026-11-15T142030214307 -> 2026-11-15T212135465119 | 57 added, 1 removed | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-apple_ads` | 2026-11-15T142029772382 -> 2026-11-15T212135184912 | 27 added, 1 removed | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-android_developer` | 2026-11-15T142029608906 -> 2026-11-15T212134967974 | 40 added, 1 removed | quiet |
| 2026-11-15 | `remote/gg.pixly/mcp` | 2026-11-15T142206988654 -> 2026-11-15T212135347985 | 1 added | quiet |
| 2026-11-15 | `remote/com.obriym-crm/mcp` | 2026-11-13T120013491059 -> 2026-11-15T212132229843 | 2 changed | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-slack_android` | 2026-11-15T142111752757 -> 2026-11-15T212131683572 | 19 added, 1 removed | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-saas_studio` | 2026-11-15T142111584751 -> 2026-11-15T212131670540 | 34 added, 1 removed | quiet |
| 2026-11-15 | `remote/io.github.smarterweather/weather` | 2026-11-15T002337810451 -> 2026-11-15T212130959459 | 1 changed | quiet |
| 2026-11-15 | `remote/dev.tanod/tanod` | 2026-11-15T115400946096 -> 2026-11-15T212132926513 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 62474 substantive, 40699 that changed only numbers (a catalogue counter ticking, a date), 1038 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 56231 | 17878 | 38353 | 0 |
| `a2awire.com` | 2707 | 2707 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 431 | 431 | 0 | 0 |
| `civai.co` | 363 | 363 | 0 | 0 |
| `revmesh2074.workers.dev` | 266 | 233 | 33 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `sistaminuten.se` | 242 | 6 | 0 | 236 |
| `afbudsrejser.dk` | 241 | 6 | 0 | 235 |
| `akkilahdot.fi` | 241 | 6 | 0 | 235 |
| `restplass.no` | 241 | 6 | 0 | 235 |
| `socialloop.ai` | 233 | 233 | 0 | 0 |
| 9480 other operators | 40416 | 38006 | 2313 | 97 |
