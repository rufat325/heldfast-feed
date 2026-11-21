# MCP server tool changes

Last change observed 2026-11-21T13:06:48+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

121544 changes to a tool definition: 4852 npm releases (4606 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 116692 readings of hosted servers that found their tools changed; 4584 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-21 | `remote/com.veridionmarkets/disclosures` | 2026-11-21T014815725510 -> 2026-11-21T130649144079 | 1 changed | quiet |
| 2026-11-21 | `remote/se.sistaminuten/travel-search` | 2026-11-21T014814409577 -> 2026-11-21T130648434809 | 1 changed | quiet |
| 2026-11-21 | `remote/org.omenz.www/agent-tools` | 2026-11-21T014812815527 -> 2026-11-21T130646159334 | 1 added | quiet |
| 2026-11-21 | `remote/nl.prijsprofeet/prijsprofeet-de` | 2026-11-19T123906308994 -> 2026-11-21T130648767032 | 1 added | quiet |
| 2026-11-21 | `remote/com.ferntool/ip` | 2026-11-19T123839867834 -> 2026-11-21T130644046619 | 1 changed | quiet |
| 2026-11-21 | `remote/io.github.TMcodingarc/bull-otc` | 2026-11-20T155941366699 -> 2026-11-21T130643748048 | 9 changed, 2 added | quiet |
| 2026-11-21 | `remote/com.vet402/vet402` | 2026-11-21T014806969748 -> 2026-11-21T130641356669 | 4 changed | quiet |
| 2026-11-21 | `remote/xyz.urbangametheory/urban-game-theory` | 2026-11-20T105409422616 -> 2026-11-21T130641745421 | 5 changed | quiet |
| 2026-11-21 | `remote/xyz.sofinancelab/sofinance` | 2026-11-20T155707797837 -> 2026-11-21T130634605807 | 1 changed | quiet |
| 2026-11-21 | `remote/com.shipshapedata/shipshape-data-docs` | 2026-11-20T105231714070 -> 2026-11-21T130633891325 | 1 changed | quiet |
| 2026-11-21 | `remote/com.lvl2player/sandbox` | 2026-11-21T014800287026 -> 2026-11-21T130632937147 | 13 changed | quiet |
| 2026-11-21 | `remote/ai.screwtape/screwtape` | 2026-11-21T014759570247 -> 2026-11-21T130632250836 | 1 added | review |
| 2026-11-21 | `remote/pl.finwire/data` | 2026-11-21T014758337088 -> 2026-11-21T130630971771 | 11 changed, 5 added | quiet |
| 2026-11-21 | `remote/re.parcellai/parcellaire` | 2026-11-21T014755883577 -> 2026-11-21T130629277382 | 1 changed | quiet |
| 2026-11-21 | `remote/co.civai.nova/mcp-firecrawl` | 2026-11-19T123252785053 -> 2026-11-21T130625948468 | 34 changed | quiet |
| 2026-11-21 | `remote/com.nabarfinder/nabarfinder` | 2026-11-19T231813244892 -> 2026-11-21T130624406072 | 1 changed | quiet |
| 2026-11-21 | `remote/com.modevc/stage-series-a` | 2026-11-20T074917996720 -> 2026-11-21T130623503266 | 4 added | quiet |
| 2026-11-21 | `remote/com.modevc/chart-openai-leaderboard-ranking` | 2026-11-20T074917431488 -> 2026-11-21T130623402910 | 4 added | quiet |
| 2026-11-21 | `remote/com.modevc/chart-open-weights-vs-proprietary-arena-gap` | 2026-11-20T074917494907 -> 2026-11-21T130622295707 | 4 added | quiet |
| 2026-11-21 | `remote/com.modevc/chart-llm-leaderboard-top-10-gap` | 2026-11-20T074917545920 -> 2026-11-21T130622268797 | 4 added | quiet |
| 2026-11-21 | `remote/com.modevc/chart-how-long-number-one-ai-model-stays-on-top` | 2026-11-20T074917068537 -> 2026-11-21T130622254916 | 4 added | quiet |
| 2026-11-21 | `remote/com.modevc/chart-best-ai-model-vs-most-popular-ai-chatbot` | 2026-11-20T074916766628 -> 2026-11-21T130622283020 | 4 added | quiet |
| 2026-11-21 | `remote/dev.zambo/zambo` | 2026-11-21T014921112549 -> 2026-11-21T130621146037 | 2 changed | quiet |
| 2026-11-21 | `remote/com.youspot/youspot` | 2026-11-21T014921196309 -> 2026-11-21T130621331446 | 3 changed | quiet |
| 2026-11-21 | `remote/com.modevc/chart-best-ai-for-creative-writing` | 2026-11-20T074916342660 -> 2026-11-21T130621318557 | 4 added | quiet |
| 2026-11-21 | `remote/com.modevc/chart-anthropic-sdk-vs-openai-sdk-npm-downloads` | 2026-11-20T074916481251 -> 2026-11-21T130621210551 | 4 added | quiet |
| 2026-11-21 | `remote/com.modevc/chart-ai-model-releases-2026` | 2026-11-20T074916760226 -> 2026-11-21T130621205160 | 4 added | quiet |
| 2026-11-21 | `remote/com.modevc/chart-ai-model-launch-strategy` | 2026-11-20T074916331194 -> 2026-11-21T130620575284 | 4 added | quiet |
| 2026-11-21 | `remote/com.modevc/chart-ai-coding-assistant-statistics` | 2026-11-20T074916225010 -> 2026-11-21T130620295359 | 4 added | quiet |
| 2026-11-21 | `remote/com.modevc/chart-ai-adoption-rate-us-businesses` | 2026-11-20T074915618401 -> 2026-11-21T130620225455 | 4 added | quiet |
| 2026-11-21 | `remote/io.github.cnucho/methodiq-tools` | 2026-11-19T123214426217 -> 2026-11-21T130618979069 | 1 changed | quiet |
| 2026-11-21 | `remote/io.github.worklittle/jobs` | 2026-11-21T014748915413 -> 2026-11-21T130618302508 | 4 changed, 2 added, 8 removed | quiet |
| 2026-11-21 | `remote/nl.prijsprofeet/prijsprofeet-be` | 2026-11-19T123739314668 -> 2026-11-21T130617679944 | 1 added | quiet |
| 2026-11-21 | `remote/nl.prijsprofeet/prijsprofeet` | 2026-11-19T123739965112 -> 2026-11-21T130618221794 | 1 added | quiet |
| 2026-11-21 | `remote/com.splitscanner/mcp` | 2026-11-20T172150309375 -> 2026-11-21T130619257798 | 2 changed | quiet |
| 2026-11-21 | `remote/com.xn--5kvtwv52d/jizhineng-mcp-gateway` | 2026-11-19T124126177828 -> 2026-11-21T130618103710 | 1 added | quiet |
| 2026-11-21 | `remote/ad.pantheon/mcp` | 2026-11-21T014746417248 -> 2026-11-21T130616592738 | 2 changed | quiet |
| 2026-11-21 | `remote/uk.co.speedi/availability` | 2026-11-20T160525133031 -> 2026-11-21T130615212851 | 1 changed | quiet |
| 2026-11-21 | `remote/today.thekorean/news` | 2026-11-21T014937251510 -> 2026-11-21T130616359978 | 1 added | quiet |
| 2026-11-21 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-11-21T014744910002 -> 2026-11-21T130614651552 | 1 changed | review |
| 2026-11-21 | `remote/co.ibda/ibda` | 2026-11-20T160445490467 -> 2026-11-21T130613529972 | 1 changed | quiet |
| 2026-11-21 | `remote/studio.gradients/mcp` | 2026-11-21T014934259813 -> 2026-11-21T130613968243 | 1 changed | quiet |
| 2026-11-21 | `remote/io.github.EasyGerber/easygerber` | 2026-11-20T075000999084 -> 2026-11-21T130613153877 | 2 changed | quiet |
| 2026-11-21 | `remote/fi.akkilahdot/travel-search` | 2026-11-21T014934040884 -> 2026-11-21T130613063311 | 1 changed | quiet |
| 2026-11-21 | `remote/com.weverlabs/agentic-rails` | 2026-11-21T014939295922 -> 2026-11-21T130618437817 | 16 added | quiet |
| 2026-11-21 | `remote/ru.vedarai/mcp` | 2026-11-20T160303334089 -> 2026-11-21T130613516340 | 6 changed | quiet |
| 2026-11-21 | `remote/io.github.christianscode1994/volatiai` | 2026-11-20T105711277461 -> 2026-11-21T130611430329 | 5 added | quiet |
| 2026-11-21 | `remote/com.jojapi/sms-verify` | 2026-11-20T074909718392 -> 2026-11-21T130612902636 | 1 changed | quiet |
| 2026-11-21 | `remote/io.github.echopai/echopai-mcp` | 2026-11-21T014748440729 -> 2026-11-21T130616839150 | 76 changed, 1 added, 2 removed (every tool) | quiet |
| 2026-11-21 | `remote/io.github.PascalSun/talk2geo` | 2026-11-20T172126781329 -> 2026-11-21T130612413934 | 69 changed, 23 added, 21 removed (every tool) | quiet |
| 2026-11-21 | `remote/app.sunsetstrip/gta6` | 2026-11-20T155824171897 -> 2026-11-21T130609834230 | 1 changed | quiet |
| 2026-11-21 | `remote/com.dilutionscan/mcp` | 2026-11-20T172139143563 -> 2026-11-21T130611305267 | 7 changed | quiet |
| 2026-11-21 | `remote/com.simplyglobal/visitor-insurance` | 2026-11-21T014905477853 -> 2026-11-21T130608062012 | 2 changed | quiet |
| 2026-11-21 | `remote/io.github.grzesir/botspot-trading` | 2026-11-19T020312957372 -> 2026-11-21T130608373290 | 3 changed | quiet |
| 2026-11-21 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-20T172134748095 -> 2026-11-21T130608232805 | 1 changed | quiet |
| 2026-11-21 | `remote/com.shipshapedata/shipshape-data` | 2026-11-20T105320536575 -> 2026-11-21T130608353145 | 1 changed | quiet |
| 2026-11-21 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-21T014926958840 -> 2026-11-21T130605018086 | 1 changed | quiet |
| 2026-11-21 | `remote/io.github.pugarte7/spanish-top-tech-companies` | 2026-11-20T160111548439 -> 2026-11-21T130605477922 | 1 changed | quiet |
| 2026-11-21 | `remote/com.imagiolabs.www/imagio-relay` | 2026-11-21T014902268774 -> 2026-11-21T130605171108 | 16 changed | review |
| 2026-11-21 | `remote/com.provyan/provyan` | 2026-11-21T014901281467 -> 2026-11-21T130603919743 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 79305 substantive, 41099 that changed only numbers (a catalogue counter ticking, a date), 1140 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 65550 | 27196 | 38354 | 0 |
| `a2awire.com` | 3571 | 3571 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 480 | 480 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 400 | 400 | 0 | 0 |
| `revmesh2074.workers.dev` | 349 | 297 | 52 | 0 |
| `sistaminuten.se` | 265 | 6 | 0 | 259 |
| `afbudsrejser.dk` | 264 | 6 | 0 | 258 |
| `akkilahdot.fi` | 264 | 6 | 0 | 258 |
| `restplass.no` | 264 | 6 | 0 | 258 |
| `socialloop.ai` | 255 | 255 | 0 | 0 |
| 10550 other operators | 47061 | 44261 | 2693 | 107 |
