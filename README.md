# MCP server tool changes

Last change observed 2026-10-23T13:52:09+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

45001 changes to a tool definition: 1988 npm releases (1742 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 43013 readings of hosted servers that found their tools changed; 2414 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-23 | `remote/se.sistaminuten/travel-search` | 2026-10-23T120940432806 -> 2026-10-23T135211510867 | 1 changed | quiet |
| 2026-10-23 | `remote/studio.gradients/mcp` | 2026-10-23T120646168528 -> 2026-10-23T135205997816 | 1 changed | quiet |
| 2026-10-23 | `remote/fi.akkilahdot/travel-search` | 2026-10-23T120631530160 -> 2026-10-23T135205208871 | 1 changed | quiet |
| 2026-10-23 | `remote/ar.com.consignatarias/cattle-market` | 2026-10-22T105957540352 -> 2026-10-23T135205688191 | 1 changed | quiet |
| 2026-10-23 | `remote/ru.vedarai/mcp` | 2026-10-23T120608160595 -> 2026-10-23T135205864495 | 2 changed, 1 added | quiet |
| 2026-10-23 | `remote/io.github.marcoret74/semantic-geometry` | 2026-10-22T202057206621 -> 2026-10-23T135205955624 | 1 changed | quiet |
| 2026-10-23 | `remote/no.restplass/travel-search` | 2026-10-23T120701191102 -> 2026-10-23T135203114196 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.intoApex/tradingagentstack` | 2026-10-23T120811325357 -> 2026-10-23T135202695259 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.SKalinin909/tradingcalc` | 2026-10-22T202053602282 -> 2026-10-23T135203150611 | 9 changed | quiet |
| 2026-10-23 | `remote/com.usethisskill/skills` | 2026-10-22T105856836266 -> 2026-10-23T135203732658 | 1 changed | quiet |
| 2026-10-23 | `remote/dk.afbudsrejser/travel-search` | 2026-10-23T120623562469 -> 2026-10-23T135202450285 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-23T052641301915 -> 2026-10-23T135202450442 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-23T120509761076 -> 2026-10-23T135159052824 | 1 changed | quiet |
| 2026-10-23 | `remote/com.shipshapedata/shipshape-data-docs` | 2026-10-22T105718533205 -> 2026-10-23T135200317094 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.slookisen/lokal-mcp` | 2026-10-23T120627978483 -> 2026-10-23T135157962767 | 2 changed | quiet |
| 2026-10-23 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-23T120446639862 -> 2026-10-23T135155671717 | 10 changed | quiet |
| 2026-10-23 | `remote/com.remoshift/jobs` | 2026-10-23T120418518283 -> 2026-10-23T135155640969 | 1 changed | quiet |
| 2026-10-23 | `remote/com.basischarts/basis` | 2026-10-23T120629126982 -> 2026-10-23T135154339780 | 6 changed | quiet |
| 2026-10-23 | `remote/com.screenrove/screenrove` | 2026-10-22T110010902562 -> 2026-10-23T135155450062 | 1 changed, 3 added | quiet |
| 2026-10-23 | `remote/com.ocklu/hypermarket` | 2026-10-23T120308727255 -> 2026-10-23T135153759017 | 1 added | quiet |
| 2026-10-23 | `remote/com.neblla/neblla` | 2026-10-23T120258541277 -> 2026-10-23T135151689989 | 4 changed | quiet |
| 2026-10-23 | `remote/ch.kulalabs.pazair/pazair` | 2026-10-23T052621696120 -> 2026-10-23T135152097392 | 6 added | quiet |
| 2026-10-23 | `remote/dev.uptimepage/uptimepage` | 2026-10-22T105446852641 -> 2026-10-23T135150136809 | 1 changed | quiet |
| 2026-10-23 | `remote/com.sfxmint/sounds` | 2026-10-23T052613505207 -> 2026-10-23T135148760660 | 3 changed, 2 added | quiet |
| 2026-10-23 | `remote/com.pagelemon/pagelemon` | 2026-10-22T140828136588 -> 2026-10-23T135144963240 | 3 changed, 16 added | quiet |
| 2026-10-23 | `remote/org.r3js/r3` | 2026-10-22T105720055142 -> 2026-10-23T135145649685 | 3 changed | quiet |
| 2026-10-23 | `remote/com.plainrouter/mcp` | 2026-10-23T052609279678 -> 2026-10-23T135144055708 | 2 changed | quiet |
| 2026-10-23 | `remote/com.coworkingview/mcp` | 2026-10-22T105346044246 -> 2026-10-23T135141175122 | 1 changed | quiet |
| 2026-10-23 | `remote/com.coinpaprika/coinpaprika` | 2026-10-21T121603988651 -> 2026-10-23T135201207692 | 25 changed | quiet |
| 2026-10-23 | `remote/pro.aicut/aicut` | 2026-10-23T115950822764 -> 2026-10-23T135139090170 | 1 changed | quiet |
| 2026-10-23 | `remote/com.dexpaprika/dexpaprika` | 2026-10-21T121624524741 -> 2026-10-23T135159907403 | 20 changed (every tool) | quiet |
| 2026-10-23 | `remote/de.dm.mcp/dm-drogerie-markt` | 2026-10-23T120059395271 -> 2026-10-23T135139101198 | 1 added | quiet |
| 2026-10-23 | `remote/com.thefilmradar/filmlab` | 2026-10-23T115942611732 -> 2026-10-23T135139734295 | 1 changed | quiet |
| 2026-10-23 | `remote/com.convertlyft/convertlyft` | 2026-10-23T120141235284 -> 2026-10-23T135138454654 | 2 changed | quiet |
| 2026-10-23 | `remote/com.lebaneselegislation/mcp` | 2026-10-21T234125090206 -> 2026-10-23T135137312464 | 1 changed | quiet |
| 2026-10-23 | `remote/io.gajo/url-shortener` | 2026-10-21T121211174381 -> 2026-10-23T135129622138 | 5 changed, 2 added | quiet |
| 2026-10-23 | `remote/com.onrender.draconic21-x402-api/data-tools.1` | 2026-10-22T052531883456 -> 2026-10-23T135128122510 | 2 changed | quiet |
| 2026-10-23 | `remote/com.onrender.draconic21-x402-api/data-tools` | 2026-10-21T052205211796 -> 2026-10-23T135128274331 | 1 changed | quiet |
| 2026-10-23 | `remote/net.cwsi/fares` | 2026-10-23T120010268914 -> 2026-10-23T135128196599 | 1 changed | quiet |
| 2026-10-23 | `remote/dev.omikuji/calories` | 2026-10-22T202004550278 -> 2026-10-23T135124457076 | 1 changed | quiet |
| 2026-10-23 | `remote/xyz.filingdelta/filingdelta` | 2026-10-22T140812720512 -> 2026-10-23T135121971481 | 3 changed | quiet |
| 2026-10-23 | `remote/io.github.edtool79-collab/hirepulse-gateway` | 2026-10-23T115801595257 -> 2026-10-23T135122461975 | 8 changed | quiet |
| 2026-10-23 | `remote/io.github.hermoso-ai/hermoso` | 2026-10-23T052559260858 -> 2026-10-23T135121404308 | 2 changed | quiet |
| 2026-10-23 | `remote/app.apick/all` | 2026-10-23T115442720231 -> 2026-10-23T135121884899 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.WellApp-ai/well-mcp` | 2026-10-23T115435336838 -> 2026-10-23T135119039671 | 6 changed | quiet |
| 2026-10-23 | `remote/com.ultimaps/mcp` | 2026-10-22T233851093235 -> 2026-10-23T135120088754 | 1 changed | quiet |
| 2026-10-23 | `remote/app.apick/business` | 2026-10-23T115439162059 -> 2026-10-23T135120538758 | 1 changed | quiet |
| 2026-10-23 | `remote/com.doseedo/doseedo` | 2026-10-23T052546306871 -> 2026-10-23T135114974926 | 1 changed | quiet |
| 2026-10-23 | `remote/com.ce-net/ce-net` | 2026-10-23T115547184906 -> 2026-10-23T135120744250 | 3 added | quiet |
| 2026-10-23 | `remote/io.github.whiteknightonhorse/apibase` | 2026-10-23T052550473168 -> 2026-10-23T135112197028 | 4 added, 3 removed | quiet |
| 2026-10-23 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-10-22T233841896984 -> 2026-10-23T135112112132 | 2 changed | quiet |
| 2026-10-23 | `remote/com.ashareapi/ashare-data-api` | 2026-10-23T115035188656 -> 2026-10-23T135113791831 | 1 changed | quiet |
| 2026-10-23 | `remote/com.agentservicedirectory/agent-service-directory` | 2026-10-23T115001851950 -> 2026-10-23T135111651165 | 1 changed | quiet |
| 2026-10-23 | `remote/com.agentwebmap/agentwebmap` | 2026-10-23T115009207880 -> 2026-10-23T135108722191 | 2 changed, 1 added | quiet |
| 2026-10-23 | `remote/io.github.johngee518/agenttoolbox` | 2026-10-21T140951389484 -> 2026-10-23T135106560126 | 1 changed | quiet |
| 2026-10-23 | `remote/com.agentserviceatlas/agent-service-atlas` | 2026-10-23T115007137575 -> 2026-10-23T135107680012 | 1 changed | quiet |
| 2026-10-23 | `remote/ch.kulalabs.agents/jobflow` | 2026-10-23T052539539317 -> 2026-10-23T135106989301 | 6 added | quiet |
| 2026-10-23 | `remote/io.sslip.128.221.67.45.agent-exec/agent-exec` | 2026-10-23T114851770399 -> 2026-10-23T135106920028 | 1 changed | quiet |
| 2026-10-23 | `remote/com.agentgid/agentgid` | 2026-10-22T202011542369 -> 2026-10-23T135105868314 | 2 added | quiet |
| 2026-10-23 | `remote/com.agentdrives/directory.1` | 2026-10-23T114941800467 -> 2026-10-23T135106205556 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 28556 substantive, 15856 that changed only numbers (a catalogue counter ticking, a date), 589 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 23651 | 8749 | 14902 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 655 | 655 | 0 | 0 |
| `caseyjhand.com` | 187 | 187 | 0 | 0 |
| `sistaminuten.se` | 140 | 4 | 0 | 136 |
| `afbudsrejser.dk` | 139 | 4 | 0 | 135 |
| `akkilahdot.fi` | 139 | 4 | 0 | 135 |
| `restplass.no` | 139 | 4 | 0 | 135 |
| `socialloop.ai` | 135 | 135 | 0 | 0 |
| `remoshift.com` | 110 | 8 | 102 | 0 |
| `fundinglandscape.com` | 107 | 71 | 36 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| 5336 other operators | 17161 | 16297 | 816 | 48 |
