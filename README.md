# MCP server tool changes

Last change observed 2026-11-08T15:39:07+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

83452 changes to a tool definition: 3605 npm releases (3359 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 79847 readings of hosted servers that found their tools changed; 3599 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-08 | `remote/studio.gradients/mcp` | 2026-11-08T135817838030 -> 2026-11-08T153908445167 | 1 changed | quiet |
| 2026-11-08 | `remote/fi.akkilahdot/travel-search` | 2026-11-08T135747611108 -> 2026-11-08T153907891505 | 1 changed | quiet |
| 2026-11-08 | `remote/ru.vedarai/mcp` | 2026-11-08T135659167127 -> 2026-11-08T153907238880 | 6 changed | quiet |
| 2026-11-08 | `remote/no.restplass/travel-search` | 2026-11-08T135723324647 -> 2026-11-08T153905795828 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.openaccountants/openaccountants` | 2026-11-07T151401761155 -> 2026-11-08T153905743109 | 1 changed | quiet |
| 2026-11-08 | `remote/com.theagentsindex/mcp` | 2026-11-06T144724421148 -> 2026-11-08T153904627917 | 1 changed | quiet |
| 2026-11-08 | `remote/xyz.t0ll/toll` | 2026-11-08T135555296308 -> 2026-11-08T153903168916 | 1 changed, 1 added | quiet |
| 2026-11-08 | `remote/dk.afbudsrejser/travel-search` | 2026-11-08T135643318049 -> 2026-11-08T153903356479 | 1 changed | quiet |
| 2026-11-08 | `remote/com.wht-ai/wai` | 2026-11-08T135631478928 -> 2026-11-08T153902889323 | 2 changed | quiet |
| 2026-11-08 | `remote/io.github.ohad6k/viberaven-guides` | 2026-11-07T064007146939 -> 2026-11-08T153902705467 | 4 changed | quiet |
| 2026-11-08 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-08T135518473621 -> 2026-11-08T153901694092 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-08T135455825897 -> 2026-11-08T153901970219 | 1 added | quiet |
| 2026-11-08 | `remote/ai.surfingdog/search` | 2026-11-08T135630631823 -> 2026-11-08T153859839750 | 6 removed | quiet |
| 2026-11-08 | `remote/com.soc2compared/mcp` | 2026-11-06T144620252420 -> 2026-11-08T153859547847 | 1 changed | quiet |
| 2026-11-08 | `remote/se.sistaminuten/travel-search` | 2026-11-08T135905844949 -> 2026-11-08T153858175999 | 1 changed | quiet |
| 2026-11-08 | `remote/app.perfumate/perfumate` | 2026-11-06T144454712560 -> 2026-11-08T153855750985 | 4 changed | quiet |
| 2026-11-08 | `remote/ca.movahedi/privacy` | 2026-11-07T133212834796 -> 2026-11-08T153852172047 | 2 changed | quiet |
| 2026-11-08 | `remote/io.github.jweezy119/Pabandi` | 2026-11-08T135401159956 -> 2026-11-08T153851686639 | 2 changed | quiet |
| 2026-11-08 | `remote/com.sonarconnections/sonar-connections` | 2026-11-07T133153842338 -> 2026-11-08T153850537432 | 3 added | quiet |
| 2026-11-08 | `remote/ai.switchapp/switch` | 2026-11-08T135135701641 -> 2026-11-08T153846816071 | 4 changed | quiet |
| 2026-11-08 | `remote/com.ortexo/mcp` | 2026-11-07T203314738224 -> 2026-11-08T153844962390 | 1 changed | quiet |
| 2026-11-08 | `remote/com.getmattered/getmattered` | 2026-11-08T134944818770 -> 2026-11-08T153845630371 | 39 changed | quiet |
| 2026-11-08 | `remote/org.qrvote/qrvote.1` | 2026-11-08T135155066410 -> 2026-11-08T153842685224 | 2 changed | quiet |
| 2026-11-08 | `remote/io.echelongraph/echelongraph-mcp` | 2026-11-08T134924880587 -> 2026-11-08T153841447709 | 2 changed | quiet |
| 2026-11-08 | `remote/co.deadbrands/arena` | 2026-11-08T134919079759 -> 2026-11-08T153841100781 | 1 changed, 1 added | review |
| 2026-11-08 | `remote/com.jobmojito/jobmojito` | 2026-11-08T135006769385 -> 2026-11-08T153841104387 | 5 changed, 2 added | quiet |
| 2026-11-08 | `remote/com.googleapis.mapstools/mcp` | 2026-11-06T143925001209 -> 2026-11-08T153837593390 | 3 changed | quiet |
| 2026-11-08 | `remote/com.freqblog/music-metadata` | 2026-11-08T135044187882 -> 2026-11-08T153840136634 | 2 changed, 1 added | quiet |
| 2026-11-08 | `remote/io.github.Clipform/mcp-server` | 2026-11-07T132842623578 -> 2026-11-08T153836891062 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.industrial-platform-ai/research-brief` | 2026-11-06T144014261765 -> 2026-11-08T153836318114 | 1 changed | quiet |
| 2026-11-08 | `remote/club.aiprocurement/procurement-agents` | 2026-11-08T134939902464 -> 2026-11-08T153837868959 | 7 added | quiet |
| 2026-11-08 | `remote/io.github.hristovdimitri2-hub/kristo-intelligence` | 2026-11-07T132701752816 -> 2026-11-08T153835497035 | 7 changed (every tool) | quiet |
| 2026-11-08 | `remote/io.github.si-imtiaz/leadquasar` | 2026-11-08T064543448779 -> 2026-11-08T153834684480 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.saagpatel/portfolio-mcp` | 2026-11-08T135241817033 -> 2026-11-08T153834816546 | 1 added | quiet |
| 2026-11-08 | `remote/io.github.34r7h/handoff` | 2026-11-08T134651761486 -> 2026-11-08T153848850567 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.Marsell-Official/marsell` | 2026-11-08T134636169244 -> 2026-11-08T153829687046 | 1 changed | quiet |
| 2026-11-08 | `remote/com.githubcard/mcp` | 2026-11-07T132434490700 -> 2026-11-08T153829541602 | 4 changed | quiet |
| 2026-11-08 | `remote/io.kompare/search` | 2026-11-08T135152590308 -> 2026-11-08T153829932449 | 1 changed | quiet |
| 2026-11-08 | `remote/app.vercel.fork-for-agents/fork` | 2026-11-08T134544968882 -> 2026-11-08T153828053178 | 1 changed | quiet |
| 2026-11-08 | `remote/io.taifoon/coordination-layer` | 2026-11-07T203255223561 -> 2026-11-08T153827913617 | 1 changed | quiet |
| 2026-11-08 | `remote/now.carejobs/healthcare-jobs` | 2026-11-08T134325209728 -> 2026-11-08T153826406187 | 1 changed | quiet |
| 2026-11-08 | `remote/app.chopit/chopit` | 2026-11-08T000057137168 -> 2026-11-08T153825582455 | 7 changed | quiet |
| 2026-11-08 | `remote/markets.borro/borro` | 2026-11-08T134321157288 -> 2026-11-08T153822695901 | 2 changed, 4 added | quiet |
| 2026-11-08 | `remote/io.github.smithdavedesign/botchelor` | 2026-11-08T134323337410 -> 2026-11-08T153822639315 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.Batu1-1an/istanbul-mcp` | 2026-11-08T134859819801 -> 2026-11-08T153820700083 | 3 changed | quiet |
| 2026-11-08 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-11-08T134142990322 -> 2026-11-08T153818971202 | 1 changed | quiet |
| 2026-11-08 | `remote/com.publicwww/publicwww` | 2026-11-08T134136663962 -> 2026-11-08T153820115712 | 2 changed | quiet |
| 2026-11-08 | `remote/io.github.tettertotter/fundinglandscape` | 2026-11-08T134646963448 -> 2026-11-08T153816698570 | 1 changed | quiet |
| 2026-11-08 | `remote/kr.xdata/xdata-mcp` | 2026-11-08T134158183562 -> 2026-11-08T153814731680 | 1 changed, 9 added | quiet |
| 2026-11-08 | `remote/com.citedindex/mcp` | 2026-11-06T143342107807 -> 2026-11-08T153813300802 | 1 changed | quiet |
| 2026-11-08 | `remote/io.onchainagentintel/agent-zero-intel` | 2026-11-06T162036735926 -> 2026-11-08T153809515988 | 1 changed | quiet |
| 2026-11-08 | `remote/domains.audit/appraisal` | 2026-11-07T063923274662 -> 2026-11-08T153808538351 | 6 changed | review |
| 2026-11-08 | `remote/ai.betslipdoctor/mcp` | 2026-11-08T064523327005 -> 2026-11-08T153806450654 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.FinzData/finzdata-mcp` | 2026-11-08T133944113480 -> 2026-11-08T153805123521 | 1 changed | quiet |
| 2026-11-08 | `remote/ai.liquidagent.api/liquid-agent` | 2026-11-08T134041872982 -> 2026-11-08T153802756652 | 1 changed | quiet |
| 2026-11-08 | `remote/net.anyhook/anyhook` | 2026-11-08T133912473695 -> 2026-11-08T153803023331 | 17 changed (every tool) | quiet |
| 2026-11-08 | `remote/com.agentwebmap/agentwebmap` | 2026-11-08T133846560586 -> 2026-11-08T153801540790 | 1 added | quiet |
| 2026-11-08 | `remote/com.agentgid/agentgid` | 2026-11-07T131715254883 -> 2026-11-08T153800908560 | 1 added | quiet |
| 2026-11-08 | `remote/ai.agentsindex/mcp` | 2026-11-06T142624846651 -> 2026-11-08T153759432461 | 1 changed | quiet |
| 2026-11-08 | `remote/com.xn--5kvtwv52d/jizhineng-mcp-gateway` | 2026-11-02T163754140872 -> 2026-11-08T135934783178 | 10 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 51404 substantive, 31145 that changed only numbers (a catalogue counter ticking, a date), 903 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 45119 | 15889 | 29230 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1843 | 1843 | 0 | 0 |
| `caseyjhand.com` | 354 | 354 | 0 | 0 |
| `sistaminuten.se` | 212 | 6 | 0 | 206 |
| `afbudsrejser.dk` | 211 | 6 | 0 | 205 |
| `akkilahdot.fi` | 211 | 6 | 0 | 205 |
| `restplass.no` | 211 | 6 | 0 | 205 |
| `socialloop.ai` | 203 | 203 | 0 | 0 |
| `revmesh2074.workers.dev` | 190 | 167 | 23 | 0 |
| `civai.co` | 188 | 188 | 0 | 0 |
| `modevc.com` | 174 | 174 | 0 | 0 |
| 8043 other operators | 32195 | 30221 | 1892 | 82 |
