# MCP server tool changes

Last change observed 2026-10-10T14:47:38+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10128 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 21701 hosted endpoints (read daily, and every four hours while they keep changing).

25803 changes to a tool definition: 870 npm releases (624 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 24933 readings of hosted servers that found their tools changed; 382 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-10 | `remote/io.github.kor-jongwon/witan` | 2026-10-08T213437429085 -> 2026-10-10T144740384612 | 3 changed, 1 added | quiet |
| 2026-10-10 | `remote/fi.akkilahdot/travel-search` | 2026-10-10T062531983840 -> 2026-10-10T144740357584 | 1 changed | quiet |
| 2026-10-10 | `remote/com.voyscout/price-history` | 2026-10-08T135442020560 -> 2026-10-10T144738428157 | 2 changed | quiet |
| 2026-10-10 | `remote/ru.vedarai/mcp` | 2026-10-10T062530781192 -> 2026-10-10T144739333785 | 1 changed, 2 added | quiet |
| 2026-10-10 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-10T062528635484 -> 2026-10-10T144736777173 | 1 changed | quiet |
| 2026-10-10 | `remote/com.swarmmemo/bulletin` | 2026-10-10T062528132730 -> 2026-10-10T144736022113 | 3 changed, 1 added | quiet |
| 2026-10-10 | `remote/ch.swisslivingindex/swiss-living-index` | 2026-10-09T153617646123 -> 2026-10-10T144735253823 | 4 changed, 3 added | quiet |
| 2026-10-10 | `remote/no.restplass/travel-search` | 2026-10-10T062543081722 -> 2026-10-10T144735708039 | 1 changed | quiet |
| 2026-10-10 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-10T062526360247 -> 2026-10-10T144734307577 | 1 changed | quiet |
| 2026-10-10 | `remote/dk.afbudsrejser/travel-search` | 2026-10-10T062542333478 -> 2026-10-10T144733946368 | 1 changed | quiet |
| 2026-10-10 | `remote/ai.shorti/shorti` | 2026-10-09T153616338823 -> 2026-10-10T144735383862 | 1 changed | quiet |
| 2026-10-10 | `remote/com.remoshift/jobs` | 2026-10-10T062525450928 -> 2026-10-10T144732063088 | 1 changed | quiet |
| 2026-10-10 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-08T213434496783 -> 2026-10-10T144729831291 | 13 changed | quiet |
| 2026-10-10 | `remote/online.pageaudit/pageaudit` | 2026-10-10T062524069740 -> 2026-10-10T144730434015 | 2 changed | quiet |
| 2026-10-10 | `remote/io.github.wygogogo19/robotbase-mcp` | 2026-10-08T135321558293 -> 2026-10-10T144729298725 | 5 changed, 2 removed | quiet |
| 2026-10-10 | `remote/ai.switchapp/switch` | 2026-10-08T135119890348 -> 2026-10-10T144727102216 | 5 added | quiet |
| 2026-10-10 | `remote/co.civai.nova/research-agent` | 2026-10-10T062532806089 -> 2026-10-10T144724988836 | 2 removed | quiet |
| 2026-10-10 | `remote/co.civai.nova/google-sheets-agent` | 2026-10-10T062532610255 -> 2026-10-10T144724949778 | 2 removed | quiet |
| 2026-10-10 | `remote/io.github.jackskip22/rapier` | 2026-10-10T062521037868 -> 2026-10-10T144724303772 | 24 changed, 23 added, 25 removed (every tool) | quiet |
| 2026-10-10 | `remote/io.github.springrolldev/springroll` | 2026-10-08T135324002303 -> 2026-10-10T144720548485 | 1 changed | quiet |
| 2026-10-10 | `remote/com.aiapplyd/aiapplyd` | 2026-10-08T134919791851 -> 2026-10-10T144720998411 | 3 changed | quiet |
| 2026-10-10 | `remote/com.thefilmradar/filmlab` | 2026-10-10T062516644942 -> 2026-10-10T144720528034 | 2 changed, 1 added | quiet |
| 2026-10-10 | `remote/co.getclippy/clippy` | 2026-10-10T062515456974 -> 2026-10-10T144718882067 | 2 changed | quiet |
| 2026-10-10 | `remote/io.github.Fizzl13/ichimoku-signal` | 2026-10-09T153551140318 -> 2026-10-10T144717378815 | 2 changed | quiet |
| 2026-10-10 | `remote/fun.lesgooo/lesgooo` | 2026-10-10T062515135884 -> 2026-10-10T144717826842 | 14 changed | quiet |
| 2026-10-10 | `remote/de.immobilieneichmann/listings` | 2026-10-08T134822202342 -> 2026-10-10T144718081995 | 4 changed (every tool) | quiet |
| 2026-10-10 | `remote/com.idevice/wearables` | 2026-10-10T062526280101 -> 2026-10-10T144717620000 | 1 changed | quiet |
| 2026-10-10 | `remote/ar.indicadores/empresas` | 2026-10-08T134817935238 -> 2026-10-10T144718679791 | 2 changed, 2 added | quiet |
| 2026-10-10 | `remote/se.sistaminuten/travel-search` | 2026-10-10T062530651966 -> 2026-10-10T144716947031 | 1 changed | quiet |
| 2026-10-10 | `remote/com.followontours/cricket-travel` | 2026-10-08T155658481928 -> 2026-10-10T144716063915 | 2 changed, 1 added | quiet |
| 2026-10-10 | `remote/io.github.ryan-tish/sendpaper` | 2026-10-08T135339096843 -> 2026-10-10T144713101776 | 5 changed | quiet |
| 2026-10-10 | `remote/com.plainrouter/mcp` | 2026-10-08T135220416958 -> 2026-10-10T144715601157 | 3 changed | quiet |
| 2026-10-10 | `remote/io.github.bosmdavid-gif/dropthehassle` | 2026-10-09T153552844442 -> 2026-10-10T144713063208 | 2 changed | quiet |
| 2026-10-10 | `remote/co.civai.nova/support-agent-admin` | 2026-10-10T062519054179 -> 2026-10-10T144711980447 | 3 changed, 6 added, 2 removed | quiet |
| 2026-10-10 | `remote/ltd.qianyuan/qy-evolution` | 2026-10-08T135258775969 -> 2026-10-10T144712869960 | 1 changed | quiet |
| 2026-10-10 | `remote/io.github.equinoxaifinance-rgb/proof-fetch` | 2026-10-08T135252580915 -> 2026-10-10T144710810616 | 3 changed (every tool) | review |
| 2026-10-10 | `remote/io.github.pscale-commons/bsp-mcp` | 2026-10-08T213318181349 -> 2026-10-10T144710648222 | 1 changed | quiet |
| 2026-10-10 | `remote/org.aspern/aspern` | 2026-10-08T155351049803 -> 2026-10-10T144710426343 | 4 changed, 1 added | quiet |
| 2026-10-10 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt` | 2026-10-10T062511686162 -> 2026-10-10T144712792914 | 1 changed | quiet |
| 2026-10-10 | `remote/co.civai.nova/google-docs-agent` | 2026-10-10T062522863038 -> 2026-10-10T144709278571 | 2 removed | quiet |
| 2026-10-10 | `remote/kr.xdata/xdata-mcp` | 2026-10-09T064728116105 -> 2026-10-10T144710377068 | 6 changed | quiet |
| 2026-10-10 | `remote/app.evlek/mcp-server` | 2026-10-10T062512682869 -> 2026-10-10T144712628109 | 2 changed | quiet |
| 2026-10-10 | `remote/com.nicheangle/niche` | 2026-10-10T062515770550 -> 2026-10-10T144706438869 | 7 changed | quiet |
| 2026-10-10 | `remote/com.jojapi/product-barcode-api` | 2026-10-10T062514274214 -> 2026-10-10T144707561467 | 2 changed | quiet |
| 2026-10-10 | `remote/co.ainumbers/tools` | 2026-10-09T064726105075 -> 2026-10-10T144705676642 | 2 changed | quiet |
| 2026-10-10 | `remote/gl.parse/mcp` | 2026-10-08T064214878446 -> 2026-10-10T144706026786 | 15 changed, 1 added | quiet |
| 2026-10-10 | `remote/com.ikeytz/maps` | 2026-10-10T062513822359 -> 2026-10-10T144706640850 | 9 changed | quiet |
| 2026-10-10 | `remote/com.knowjudges/knowjudges` | 2026-10-09T153610680119 -> 2026-10-10T144704504882 | 3 changed | quiet |
| 2026-10-10 | `remote/com.ashareapi/ashare-data-api` | 2026-10-10T062514792845 -> 2026-10-10T144705446394 | 1 changed, 2 added | quiet |
| 2026-10-10 | `remote/dev.fastdrop/fastdrop` | 2026-10-08T134613076420 -> 2026-10-10T144703723097 | 6 changed, 1 added | quiet |
| 2026-10-10 | `remote/com.blockvectra/docs` | 2026-10-10T062510493989 -> 2026-10-10T144702711911 | 5 changed | quiet |
| 2026-10-10 | `remote/com.cooperemail/cooper-email` | 2026-10-10T062509660167 -> 2026-10-10T144702127769 | 14 changed | quiet |
| 2026-10-10 | `remote/com.402post/402post` | 2026-10-08T064118791611 -> 2026-10-10T144701837470 | 2 changed | quiet |
| 2026-10-10 | `remote/com.imperioutils/fisco-it` | 2026-10-08T134742709957 -> 2026-10-10T144700697867 | 1 changed | quiet |
| 2026-10-10 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-10T062513137234 -> 2026-10-10T144659296029 | 1 changed | quiet |
| 2026-10-10 | `remote/com.enhancedint/enhanced-intelligence` | 2026-10-09T153540656803 -> 2026-10-10T144701277493 | 2 changed | quiet |
| 2026-10-10 | `remote/uk.co.buildbatch/buildbatch` | 2026-10-09T153543833101 -> 2026-10-10T144659022860 | 2 changed | quiet |
| 2026-10-10 | `remote/io.github.gatoprd/bounty-engineer` | 2026-10-08T213327216102 -> 2026-10-10T144656761937 | 2 changed | quiet |
| 2026-10-10 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-10-10T062508015298 -> 2026-10-10T144657471087 | 1 changed | quiet |
| 2026-10-10 | `remote/com.booklint/desk` | 2026-10-08T213327471825 -> 2026-10-10T144656538073 | 8 changed (every tool) | review |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 17427 substantive, 8002 that changed only numbers (a catalogue counter ticking, a date), 374 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 13231 | 5706 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 538 | 538 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `sistaminuten.se` | 90 | 2 | 0 | 88 |
| `afbudsrejser.dk` | 89 | 2 | 0 | 87 |
| `akkilahdot.fi` | 89 | 2 | 0 | 87 |
| `restplass.no` | 89 | 2 | 0 | 87 |
| `socialloop.ai` | 87 | 87 | 0 | 0 |
| `caseyjhand.com` | 77 | 77 | 0 | 0 |
| `dayze.com` | 69 | 69 | 0 | 0 |
| `fundinglandscape.com` | 64 | 36 | 28 | 0 |
| 3054 other operators | 8942 | 8468 | 449 | 25 |
