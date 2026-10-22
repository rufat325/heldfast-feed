# MCP server tool changes

Last change observed 2026-10-22T20:22:02+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

42710 changes to a tool definition: 1838 npm releases (1592 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 40872 readings of hosted servers that found their tools changed; 2384 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-22 | `remote/no.restplass/travel-search` | 2026-10-22T140859408489 -> 2026-10-22T202203764181 | 1 changed | quiet |
| 2026-10-22 | `remote/dk.afbudsrejser/travel-search` | 2026-10-22T140858394294 -> 2026-10-22T202201979438 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.VoiceScapee/voicescape` | 2026-10-21T141140979267 -> 2026-10-22T202200773265 | 1 changed | quiet |
| 2026-10-22 | `remote/com.underpricedai/underpriced-ai` | 2026-10-21T122052566676 -> 2026-10-22T202159493625 | 1 changed | quiet |
| 2026-10-22 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-22T121815546752 -> 2026-10-22T202154443014 | 10 changed | quiet |
| 2026-10-22 | `remote/com.aibitious.silent/repository-safety-preflight` | 2026-10-20T104114379038 -> 2026-10-22T202155965051 | 1 changed | quiet |
| 2026-10-22 | `remote/site.chatgpt.orellise.relay-agent-services/relay` | 2026-10-22T121722178627 -> 2026-10-22T202151838848 | 2 changed | quiet |
| 2026-10-22 | `remote/app.sallim/korea-realty` | 2026-10-21T234542512932 -> 2026-10-22T202151592462 | 2 changed | quiet |
| 2026-10-22 | `remote/fun.pumpdata/pumpdata` | 2026-10-21T234537627678 -> 2026-10-22T202149497502 | 1 changed | quiet |
| 2026-10-22 | `remote/com.moonshotlab1/inventory` | 2026-10-22T140840813886 -> 2026-10-22T202145691822 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.smarterweather/weather` | 2026-10-21T234501096654 -> 2026-10-22T202142400649 | 14 changed (every tool) | quiet |
| 2026-10-22 | `remote/nyc.motley/mcp` | 2026-10-20T232728259306 -> 2026-10-22T202139559021 | 2 changed, 1 added | quiet |
| 2026-10-22 | `remote/app.manawa/manawa-terminal` | 2026-10-22T140831498080 -> 2026-10-22T202137886220 | 2 changed | quiet |
| 2026-10-22 | `remote/org.living-bread.mcp/living-bread` | 2026-10-20T201118755584 -> 2026-10-22T202139389796 | 1 changed | quiet |
| 2026-10-22 | `remote/com.cielstay/cielstay` | 2026-10-22T105556120735 -> 2026-10-22T202135672224 | 4 changed | quiet |
| 2026-10-22 | `remote/com.advisorfinder/mcp` | 2026-10-22T105521665679 -> 2026-10-22T202133785632 | 1 changed | quiet |
| 2026-10-22 | `remote/com.keywordise/keywordise` | 2026-10-20T103631492613 -> 2026-10-22T202132664041 | 1 changed | quiet |
| 2026-10-22 | `remote/com.idevice/wearables` | 2026-10-20T115748757841 -> 2026-10-22T202131314336 | 2 changed | quiet |
| 2026-10-22 | `remote/dev.workers.h1r3.h1r3/h1r3` | 2026-10-21T202430794392 -> 2026-10-22T202130373274 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.tonic20/extensions-dashboard` | 2026-10-21T141027658789 -> 2026-10-22T202124153459 | 4 changed | quiet |
| 2026-10-22 | `remote/app.everloot/knowledge` | 2026-10-22T052543792358 -> 2026-10-22T202129001510 | 2 changed | quiet |
| 2026-10-22 | `remote/com.deepmapai/earth-grounding` | 2026-10-20T103408147342 -> 2026-10-22T202110340635 | 3 changed | quiet |
| 2026-10-22 | `remote/io.github.withgrokbot/verified-catalog.1` | 2026-10-21T202500354831 -> 2026-10-22T202105820707 | 1 added | quiet |
| 2026-10-22 | `remote/io.github.sorindecu/vibeshipped` | 2026-10-21T234221951778 -> 2026-10-22T202106293168 | 5 changed | quiet |
| 2026-10-22 | `remote/io.github.brawlaphant/vealth` | 2026-10-22T105829479427 -> 2026-10-22T202106469018 | 1 changed | quiet |
| 2026-10-22 | `remote/studio.gradients/mcp` | 2026-10-22T122123121285 -> 2026-10-22T202103341448 | 1 changed | quiet |
| 2026-10-22 | `remote/pro.germanexam/germanexam` | 2026-10-21T141139089081 -> 2026-10-22T202106264343 | 5 added, 3 removed | quiet |
| 2026-10-22 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-21T122021136988 -> 2026-10-22T202102001535 | 4 changed | quiet |
| 2026-10-22 | `remote/io.github.CodeWever/wever-labs-products` | 2026-10-22T105940444972 -> 2026-10-22T202102313309 | 6 changed | review |
| 2026-10-22 | `remote/fi.akkilahdot/travel-search` | 2026-10-22T140853596188 -> 2026-10-22T202102519202 | 1 changed | quiet |
| 2026-10-22 | `remote/ai.usedby/usedby` | 2026-10-22T122021870373 -> 2026-10-22T202102118861 | 1 added | quiet |
| 2026-10-22 | `remote/io.taifoon/coordination-layer.1` | 2026-10-22T122015932300 -> 2026-10-22T202101408000 | 1 changed | review |
| 2026-10-22 | `remote/io.taifoon/coordination-layer` | 2026-10-22T120931356198 -> 2026-10-22T202109692400 | 1 changed | review |
| 2026-10-22 | `remote/io.github.jennipro-engineering/ghost-market-web` | 2026-10-22T121902147188 -> 2026-10-22T202101564832 | 5 changed, 3 added (every tool) | quiet |
| 2026-10-22 | `remote/com.pythonanywhere.conclavex402/conclave-agent-rails` | 2026-10-21T202409142188 -> 2026-10-22T202103509862 | 1 changed, 1 added | quiet |
| 2026-10-22 | `remote/build.naru/contract-compass` | 2026-10-22T120928253659 -> 2026-10-22T202109710200 | 1 changed | quiet |
| 2026-10-22 | `remote/se.sistaminuten/travel-search` | 2026-10-22T140852780752 -> 2026-10-22T202101577997 | 1 changed | quiet |
| 2026-10-22 | `remote/com.transitmcp/transit-mcp` | 2026-10-22T052642890773 -> 2026-10-22T202100037937 | 2 changed | quiet |
| 2026-10-22 | `remote/com.ticketsea/ticketsea` | 2026-10-22T122008230040 -> 2026-10-22T202058724394 | 7 changed (every tool) | quiet |
| 2026-10-22 | `remote/eu.nulegal/recht` | 2026-10-22T105655111626 -> 2026-10-22T202058668065 | 1 changed | quiet |
| 2026-10-22 | `remote/com.tablejourney/food-travel` | 2026-10-21T122047097368 -> 2026-10-22T202058093972 | 1 changed | quiet |
| 2026-10-22 | `remote/com.ready4bots/ready4bots` | 2026-10-22T105655008348 -> 2026-10-22T202059366205 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.voicehook-ai/voicehook` | 2026-10-21T202555809362 -> 2026-10-22T202058197892 | 2 changed | quiet |
| 2026-10-22 | `remote/com.swarmmemo/bulletin` | 2026-10-22T121952256107 -> 2026-10-22T202057416627 | 1 changed | quiet |
| 2026-10-22 | `remote/com.qevrulan/lockzone` | 2026-10-22T105646491530 -> 2026-10-22T202057464353 | 3 changed | quiet |
| 2026-10-22 | `remote/io.github.marcoret74/semantic-geometry` | 2026-10-22T052601181198 -> 2026-10-22T202057206621 | 1 added | quiet |
| 2026-10-22 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-22T140844990797 -> 2026-10-22T202055308091 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.Perufitlife/postwire-mcp` | 2026-10-22T105635629776 -> 2026-10-22T202054973671 | 3 changed | quiet |
| 2026-10-22 | `remote/io.github.davidgringras/scrutica` | 2026-10-22T105801952006 -> 2026-10-22T202054422156 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.leewenjie/oxaide` | 2026-10-21T052239081549 -> 2026-10-22T202101418043 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.SKalinin909/tradingcalc` | 2026-10-21T122229564855 -> 2026-10-22T202053602282 | 9 changed | quiet |
| 2026-10-22 | `remote/com.risetive/mcp` | 2026-10-22T105744985171 -> 2026-10-22T202053264352 | 4 changed | quiet |
| 2026-10-22 | `remote/com.remoshift/jobs` | 2026-10-22T140843228746 -> 2026-10-22T202052483537 | 1 changed | quiet |
| 2026-10-22 | `remote/dev.tanod/tanod` | 2026-10-22T105807830786 -> 2026-10-22T202053986457 | 1 changed, 1 added | quiet |
| 2026-10-22 | `remote/dev.tanod/docs` | 2026-10-22T105807082713 -> 2026-10-22T202053397011 | 1 changed | quiet |
| 2026-10-22 | `remote/co.civai.nova/support-agent-admin` | 2026-10-21T202437719280 -> 2026-10-22T202053059660 | 1 changed | quiet |
| 2026-10-22 | `remote/md.mostlyright/datasets` | 2026-10-21T141107970146 -> 2026-10-22T202049491848 | 1 added | quiet |
| 2026-10-22 | `remote/io.github.muaviamohammed/mizan` | 2026-10-22T105759727512 -> 2026-10-22T202052512617 | 1 changed | quiet |
| 2026-10-22 | `remote/com.multicinesortega/cartelera` | 2026-10-22T052633939475 -> 2026-10-22T202049230368 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.CustomBlinds/cb-shop` | 2026-10-20T104143999890 -> 2026-10-22T202048199442 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 27812 substantive, 14325 that changed only numbers (a catalogue counter ticking, a date), 573 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 22156 | 8734 | 13422 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 654 | 654 | 0 | 0 |
| `caseyjhand.com` | 174 | 174 | 0 | 0 |
| `sistaminuten.se` | 136 | 4 | 0 | 132 |
| `afbudsrejser.dk` | 135 | 4 | 0 | 131 |
| `akkilahdot.fi` | 135 | 4 | 0 | 131 |
| `restplass.no` | 135 | 4 | 0 | 131 |
| `socialloop.ai` | 131 | 131 | 0 | 0 |
| `remoshift.com` | 106 | 8 | 98 | 0 |
| `fundinglandscape.com` | 104 | 69 | 35 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| 5127 other operators | 16406 | 15588 | 770 | 48 |
