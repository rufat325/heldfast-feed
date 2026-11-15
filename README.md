# MCP server tool changes

Last change observed 2026-11-15T15:56:33+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

104067 changes to a tool definition: 4274 npm releases (4028 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 99793 readings of hosted servers that found their tools changed; 4163 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-15 | `remote/co.yougame/yougame` | 2026-11-15T115409889178 -> 2026-11-15T155639996127 | 2 changed | quiet |
| 2026-11-15 | `remote/studio.gradients/mcp` | 2026-11-15T142717379327 -> 2026-11-15T155633784032 | 1 changed | quiet |
| 2026-11-15 | `remote/fi.akkilahdot/travel-search` | 2026-11-15T142644315959 -> 2026-11-15T155633060315 | 1 changed | quiet |
| 2026-11-15 | `remote/no.restplass/travel-search` | 2026-11-15T142616633166 -> 2026-11-15T155631324838 | 1 changed | quiet |
| 2026-11-15 | `remote/com.kulicadvisory/aictionbot-werkbank` | 2026-11-15T142557543331 -> 2026-11-15T155630555350 | 1 added | quiet |
| 2026-11-15 | `remote/ru.vedarai/mcp` | 2026-11-15T142553384011 -> 2026-11-15T155631847191 | 6 changed | quiet |
| 2026-11-15 | `remote/dk.afbudsrejser/travel-search` | 2026-11-15T142527888831 -> 2026-11-15T155629110042 | 1 changed | quiet |
| 2026-11-15 | `remote/dev.vetagent/vetagent` | 2026-11-15T115544112119 -> 2026-11-15T155630622586 | 2 changed | quiet |
| 2026-11-15 | `remote/com.trackerhacker/mcp` | 2026-11-15T115159768281 -> 2026-11-15T155624094481 | 2 changed, 2 added, 1 removed | quiet |
| 2026-11-15 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-15T142436173655 -> 2026-11-15T155623340940 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-15T115111525939 -> 2026-11-15T155622796993 | 1 added | quiet |
| 2026-11-15 | `remote/com.remoshift/jobs` | 2026-11-15T142254319707 -> 2026-11-15T155617690636 | 1 changed | quiet |
| 2026-11-15 | `remote/eu.surfbooking/surfbooking` | 2026-11-15T142756836456 -> 2026-11-15T155613572228 | 2 changed | quiet |
| 2026-11-15 | `remote/com.prenotomenu/menu` | 2026-11-15T142745735024 -> 2026-11-15T155612756999 | 1 changed | quiet |
| 2026-11-15 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-15T142031188633 -> 2026-11-15T155610886020 | 1 changed | quiet |
| 2026-11-15 | `remote/se.sistaminuten/travel-search` | 2026-11-15T142658512016 -> 2026-11-15T155607394377 | 1 changed | quiet |
| 2026-11-15 | `remote/com.toolfound/toolfound` | 2026-11-13T115815230426 -> 2026-11-15T155605631048 | 24 changed | quiet |
| 2026-11-15 | `remote/io.github.PascalSun/talk2geo` | 2026-11-15T142514421765 -> 2026-11-15T155605583281 | 20 added | quiet |
| 2026-11-15 | `remote/io.github.hail-hq/hail-mcp` | 2026-11-15T141809673293 -> 2026-11-15T155603092230 | 26 changed | quiet |
| 2026-11-15 | `remote/io.github.daniel3303/equibles` | 2026-11-15T141743687948 -> 2026-11-15T155600494677 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.MorrisMoe/soulintime` | 2026-11-15T142401251214 -> 2026-11-15T155558957756 | 2 changed | quiet |
| 2026-11-15 | `remote/io.github.CustomBlinds/cb-shop` | 2026-11-15T142345158411 -> 2026-11-15T155557699250 | 1 changed, 2 added | quiet |
| 2026-11-15 | `remote/io.github.joelp22-maker/referencesource` | 2026-11-15T142259961443 -> 2026-11-15T155555227121 | 1 changed | quiet |
| 2026-11-15 | `remote/co.deadbrands/arena` | 2026-11-15T141739529763 -> 2026-11-15T155555034005 | 4 added | review |
| 2026-11-15 | `remote/com.crm-connector/crm-connector` | 2026-11-14T183332609377 -> 2026-11-15T155553378281 | 5 changed | quiet |
| 2026-11-15 | `remote/dev.pcbbrew/pcbbrew` | 2026-11-13T200726685194 -> 2026-11-15T155551674460 | 2 changed | quiet |
| 2026-11-15 | `remote/com.owlchart/owlchart` | 2026-11-13T115500694126 -> 2026-11-15T155552473721 | 1 added | quiet |
| 2026-11-15 | `remote/com.oneuptime/mcp` | 2026-11-14T135646917411 -> 2026-11-15T155549413409 | 4 changed | quiet |
| 2026-11-15 | `remote/com.nearfine/books` | 2026-11-13T150041865894 -> 2026-11-15T155548189768 | 1 changed | quiet |
| 2026-11-15 | `remote/com.idevice/wearables` | 2026-11-15T114334257709 -> 2026-11-15T155547229168 | 6 changed | quiet |
| 2026-11-15 | `remote/cc.hlist/hlist-ai-tools` | 2026-11-13T114941256742 -> 2026-11-15T155546504642 | 1 changed | quiet |
| 2026-11-15 | `remote/app.vercel.fork-for-agents/fork` | 2026-11-15T141322201427 -> 2026-11-15T155544449820 | 1 changed | quiet |
| 2026-11-15 | `remote/in.marketping/marketping` | 2026-11-14T135413791053 -> 2026-11-15T155542694516 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.ContentWriterco/polish-company-financials` | 2026-11-13T114615336438 -> 2026-11-15T155538212497 | 2 changed | quiet |
| 2026-11-15 | `remote/io.github.ContentWriterco/polish-public-tenders` | 2026-11-13T114854265373 -> 2026-11-15T155537504310 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.ContentWriterco/polish-kyb` | 2026-11-13T114853649798 -> 2026-11-15T155537524881 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.ContentWriterco/compabase` | 2026-11-13T114852556176 -> 2026-11-15T155537125151 | 2 changed | quiet |
| 2026-11-15 | `remote/dev.carimage/catalog` | 2026-11-13T200637031024 -> 2026-11-15T155535876174 | 1 changed | quiet |
| 2026-11-15 | `remote/ai.buildersinfintech/fintech-data` | 2026-11-15T113923022603 -> 2026-11-15T155537140340 | 1 added | quiet |
| 2026-11-15 | `remote/io.github.Damien829/aipaygen` | 2026-11-15T071556446458 -> 2026-11-15T155534750495 | 1 added | quiet |
| 2026-11-15 | `remote/dev.jobspipe/mcp.1` | 2026-11-15T114606407943 -> 2026-11-15T155533281055 | 3 changed (every tool) | review |
| 2026-11-15 | `remote/com.astranl/mcp` | 2026-11-15T140928356366 -> 2026-11-15T155533459883 | 5 changed | quiet |
| 2026-11-15 | `remote/io.github.financeratecalc/frc-mcp` | 2026-11-15T141338728932 -> 2026-11-15T155526197835 | 1 changed | quiet |
| 2026-11-15 | `remote/com.doseedo/film-score` | 2026-11-15T140637995928 -> 2026-11-15T155523267147 | 1 changed | quiet |
| 2026-11-15 | `remote/com.plutus-cloud/plutus-cost-data` | 2026-11-15T141201616583 -> 2026-11-15T155523107222 | 1 added | quiet |
| 2026-11-15 | `remote/com.amazap/amazap` | 2026-11-15T113626327196 -> 2026-11-15T155521334414 | 1 changed | review |
| 2026-11-15 | `remote/si.courio/courio` | 2026-11-15T113610346526 -> 2026-11-15T155520991371 | 5 changed (every tool) | quiet |
| 2026-11-15 | `remote/io.github.Jona1245/agentdatahub` | 2026-11-15T113556187485 -> 2026-11-15T155519945994 | 1 added | quiet |
| 2026-11-15 | `remote/io.github.aliasist/alias-forum` | 2026-11-15T113543163944 -> 2026-11-15T155517782856 | 24 added | quiet |
| 2026-11-15 | `remote/me.crowdspark.agents/agent-tools` | 2026-11-13T113943132000 -> 2026-11-15T155516745586 | 1 changed, 2 added | quiet |
| 2026-11-15 | `remote/io.github.stophydotdev/mcp` | 2026-11-15T002239221192 -> 2026-11-15T155515627960 | 6 changed | review |
| 2026-11-15 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-11-15T140917386540 -> 2026-11-15T155518707989 | 1 changed | quiet |
| 2026-11-15 | `remote/com.hashn/hashn` | 2026-11-15T002236735443 -> 2026-11-15T155513537327 | 2 changed, 1 added | quiet |
| 2026-11-15 | `remote/io.github.Mvp2o-ai/cuttingfloor` | 2026-11-15T140702116342 -> 2026-11-15T155512274173 | 12 changed | quiet |
| 2026-11-15 | `remote/com.doseedo/doseedo` | 2026-11-15T140756619312 -> 2026-11-15T155511263156 | 2 changed | quiet |
| 2026-11-15 | `remote/io.github.0xinsider/mcp` | 2026-11-15T140723832978 -> 2026-11-15T155510196530 | 1 changed | quiet |
| 2026-11-15 | `remote/jp.cloneai.ai/agent-hub` | 2026-11-15T140700025968 -> 2026-11-15T155509855986 | 2 changed | quiet |
| 2026-11-15 | `remote/dev.workers.jbarkules.agent-tools/agent-tools` | 2026-11-13T113918111730 -> 2026-11-15T155508612655 | 1 changed, 2 added | quiet |
| 2026-11-15 | `remote/eu.surfbooking/surfbooking` | 2026-10-27T145904517143 -> 2026-11-15T142756836456 | 3 changed | quiet |
| 2026-11-15 | `remote/com.prenotomenu/menu` | 2026-11-13T150637381460 -> 2026-11-15T142745735024 | 4 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 62342 substantive, 40691 that changed only numbers (a catalogue counter ticking, a date), 1034 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 56231 | 17878 | 38353 | 0 |
| `a2awire.com` | 2707 | 2707 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 431 | 431 | 0 | 0 |
| `civai.co` | 341 | 341 | 0 | 0 |
| `revmesh2074.workers.dev` | 266 | 233 | 33 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `sistaminuten.se` | 241 | 6 | 0 | 235 |
| `afbudsrejser.dk` | 240 | 6 | 0 | 234 |
| `akkilahdot.fi` | 240 | 6 | 0 | 234 |
| `restplass.no` | 240 | 6 | 0 | 234 |
| `socialloop.ai` | 232 | 232 | 0 | 0 |
| 9479 other operators | 40299 | 37897 | 2305 | 97 |
