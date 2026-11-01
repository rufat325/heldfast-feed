# MCP server tool changes

Last change observed 2026-11-01T15:31:00+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

68124 changes to a tool definition: 2873 npm releases (2627 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 65251 readings of hosted servers that found their tools changed; 3146 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-01 | `remote/no.restplass/travel-search` | 2026-11-01T135336381020 -> 2026-11-01T153100825004 | 1 changed | quiet |
| 2026-11-01 | `remote/dk.afbudsrejser/travel-search` | 2026-11-01T135301547543 -> 2026-11-01T153059437000 | 1 changed | quiet |
| 2026-11-01 | `remote/studio.gradients/mcp` | 2026-11-01T135401416392 -> 2026-11-01T153055678476 | 1 changed | quiet |
| 2026-11-01 | `remote/io.taifoon/coordination-layer.1` | 2026-11-01T065456449029 -> 2026-11-01T153054366027 | 1 changed | review |
| 2026-11-01 | `remote/se.sistaminuten/travel-search` | 2026-11-01T135819542034 -> 2026-11-01T153053784431 | 1 changed | quiet |
| 2026-11-01 | `remote/fi.akkilahdot/travel-search` | 2026-11-01T135335300405 -> 2026-11-01T153054210168 | 1 changed | quiet |
| 2026-11-01 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-01T065443737524 -> 2026-11-01T153053819524 | 2 changed | quiet |
| 2026-11-01 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-01T135226609318 -> 2026-11-01T153053004824 | 1 changed | quiet |
| 2026-11-01 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-01T135150089457 -> 2026-11-01T153046558407 | 1 changed | quiet |
| 2026-11-01 | `remote/com.timeofmeeting/time-of-meeting` | 2026-11-01T135552105492 -> 2026-11-01T153046600502 | 15 changed (every tool) | quiet |
| 2026-11-01 | `remote/io.github.cloakmaster/pact0` | 2026-10-31T125816858347 -> 2026-11-01T153044782511 | 5 changed | quiet |
| 2026-11-01 | `remote/com.remoshift/jobs` | 2026-11-01T135101308510 -> 2026-11-01T153045421028 | 1 changed | quiet |
| 2026-11-01 | `remote/io.github.brawlaphant/vealth` | 2026-10-31T234851806416 -> 2026-11-01T153042815558 | 112 changed (every tool) | quiet |
| 2026-11-01 | `remote/ca.movahedi/privacy` | 2026-10-31T125929403340 -> 2026-11-01T153039199729 | 1 changed | quiet |
| 2026-11-01 | `remote/com.tickerdb/mcp-server` | 2026-11-01T134840317825 -> 2026-11-01T153038569657 | 2 added | quiet |
| 2026-11-01 | `remote/io.github.tell-and-go/mcp` | 2026-10-31T125833056504 -> 2026-11-01T153036938390 | 3 changed | quiet |
| 2026-11-01 | `remote/es.proceres/proceres` | 2026-10-31T234841711185 -> 2026-11-01T153036313544 | 23 changed | quiet |
| 2026-11-01 | `remote/io.github.77777R7/octocrawl` | 2026-10-31T125625177709 -> 2026-11-01T153035887652 | 2 changed (every tool) | quiet |
| 2026-11-01 | `remote/com.boxerbook/boxing` | 2026-11-01T065423496132 -> 2026-11-01T153032039579 | 1 changed | quiet |
| 2026-11-01 | `remote/io.github.mason0501/pairgora` | 2026-11-01T135047292919 -> 2026-11-01T153030983149 | 2 changed | quiet |
| 2026-11-01 | `remote/si.mttr/mttr` | 2026-11-01T065441112104 -> 2026-11-01T153030775967 | 15 changed, 2 added, 47 removed (every tool) | quiet |
| 2026-11-01 | `remote/com.thefilmradar/filmlab` | 2026-11-01T065420512336 -> 2026-11-01T153031898795 | 1 changed | quiet |
| 2026-11-01 | `remote/com.tkawen/intelligence-gateway` | 2026-11-01T134915971027 -> 2026-11-01T153025999680 | 1 changed | quiet |
| 2026-11-01 | `remote/com.frankox/trade-intelligence` | 2026-10-31T125216458393 -> 2026-11-01T153021741598 | 2 added | quiet |
| 2026-11-01 | `remote/app.vercel.fork-for-agents/fork` | 2026-11-01T065412660319 -> 2026-11-01T153020574369 | 1 changed | quiet |
| 2026-11-01 | `remote/com.leadmarina/leadmarina` | 2026-11-01T065414792071 -> 2026-11-01T153016688377 | 1 changed | quiet |
| 2026-11-01 | `remote/com.googleapis.compute/mcp` | 2026-11-01T134116432100 -> 2026-11-01T153013003258 | 3 changed | quiet |
| 2026-11-01 | `remote/io.github.horizon-pulse/horizon-pulse` | 2026-11-01T065425895708 -> 2026-11-01T153012374199 | 1 changed | review |
| 2026-11-01 | `remote/com.odilelabs/gate` | 2026-10-31T125205461505 -> 2026-11-01T153009142452 | 1 changed | quiet |
| 2026-11-01 | `remote/io.github.tettertotter/fundinglandscape` | 2026-11-01T134433882704 -> 2026-11-01T153008960659 | 1 changed | quiet |
| 2026-11-01 | `remote/app.web.dealer-direct-mcp/dealer-direct-inventory` | 2026-11-01T065412555764 -> 2026-11-01T153007990194 | 1 changed | quiet |
| 2026-11-01 | `remote/ai.emberverse/emberverse` | 2026-10-31T144828229215 -> 2026-11-01T153012079822 | 1 changed | quiet |
| 2026-11-01 | `remote/ai.duami/intent-exchange` | 2026-11-01T134343666328 -> 2026-11-01T153005745458 | 1 changed | quiet |
| 2026-11-01 | `remote/eu.sirenic/sirenic` | 2026-11-01T134011228543 -> 2026-11-01T153007654072 | 1 changed | quiet |
| 2026-11-01 | `remote/org.defade/defade` | 2026-10-31T062056864903 -> 2026-11-01T153002460715 | 1 changed | quiet |
| 2026-11-01 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-11-01T133931572933 -> 2026-11-01T153001690735 | 1 changed | quiet |
| 2026-11-01 | `remote/io.bodywise/mcp` | 2026-11-01T134150665278 -> 2026-11-01T153006232816 | 14 added | quiet |
| 2026-11-01 | `remote/directory.nohumans/registry` | 2026-11-01T133917795374 -> 2026-11-01T153000546927 | 1 changed | quiet |
| 2026-11-01 | `remote/io.github.Mvp2o-ai/cuttingfloor` | 2026-11-01T133757392806 -> 2026-11-01T152958269701 | 10 changed | quiet |
| 2026-11-01 | `remote/com.autoview/mcp` | 2026-10-31T062049332174 -> 2026-11-01T152957532134 | 5 changed | quiet |
| 2026-11-01 | `remote/sg.homejourney/listings` | 2026-11-01T133704893007 -> 2026-11-01T152955659468 | 4 changed | quiet |
| 2026-11-01 | `remote/dev.workers.jbarkules.agent-tools/agent-tools` | 2026-10-31T234744496715 -> 2026-11-01T152954256325 | 1 added | quiet |
| 2026-11-01 | `remote/xn--3ds443g.xn--s7y/duan-online` | 2026-10-28T133519297232 -> 2026-11-01T135901633096 | 1 changed, 2 added | quiet |
| 2026-11-01 | `remote/insure.travelprotection/travel-insurance` | 2026-10-19T135519299710 -> 2026-11-01T135839779497 | 2 changed | review |
| 2026-11-01 | `remote/io.github.fathyshalaby/specky` | 2026-10-08T135536915927 -> 2026-11-01T135822002431 | 1 changed | quiet |
| 2026-11-01 | `remote/se.sistaminuten/travel-search` | 2026-11-01T065456679986 -> 2026-11-01T135819542034 | 1 changed | quiet |
| 2026-11-01 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-10-28T212418007109 -> 2026-11-01T135744042242 | 152 changed (every tool) | review |
| 2026-11-01 | `remote/uk.co.gigstamp/gigstamp` | 2026-11-01T065455526241 -> 2026-11-01T135741455315 | 3 changed | quiet |
| 2026-11-01 | `remote/com.cadprops/cadprops` | 2026-10-24T112909603757 -> 2026-11-01T135721816163 | 3 changed | quiet |
| 2026-11-01 | `remote/com.autoridaddigital.www/geo` | 2026-10-19T135440788112 -> 2026-11-01T135719375893 | 1 changed | quiet |
| 2026-11-01 | `remote/com.alexandria-archive/archive` | 2026-10-19T135439097722 -> 2026-11-01T135715918414 | 1 changed | quiet |
| 2026-11-01 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-30T210620323256 -> 2026-11-01T135706077268 | 2 added | quiet |
| 2026-11-01 | `remote/com.viraloutliers/viral-outliers` | 2026-10-17T055534121365 -> 2026-11-01T135642607252 | 1 added | quiet |
| 2026-11-01 | `remote/com.scriptmasterlabs/verdict` | 2026-10-26T133801093249 -> 2026-11-01T135635070513 | 2 changed | review |
| 2026-11-01 | `remote/io.github.eric-tijerina/trollbridge-mcp` | 2026-10-06T110113420505 -> 2026-11-01T135608294242 | 15 changed | review |
| 2026-11-01 | `remote/io.github.SKalinin909/tradingcalc` | 2026-10-31T234849844348 -> 2026-11-01T135605004505 | 1 added | quiet |
| 2026-11-01 | `remote/com.skaidigital/shopify-speed-check` | 2026-10-26T133733167888 -> 2026-11-01T135600598894 | 1 added | quiet |
| 2026-11-01 | `remote/com.skaidigital/norwegian-companies` | 2026-10-26T133733703580 -> 2026-11-01T135600893745 | 1 added | quiet |
| 2026-11-01 | `remote/com.timeofmeeting/time-of-meeting` | 2026-10-24T112807951542 -> 2026-11-01T135552105492 | 1 changed | quiet |
| 2026-11-01 | `remote/io.github.f-tiger/dollscout-collecting` | 2026-10-06T110100806729 -> 2026-11-01T135547686606 | 1 changed, 3 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 43951 substantive, 23399 that changed only numbers (a catalogue counter ticking, a date), 774 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 37734 | 15838 | 21896 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1245 | 1245 | 0 | 0 |
| `caseyjhand.com` | 309 | 309 | 0 | 0 |
| `sistaminuten.se` | 183 | 6 | 0 | 177 |
| `afbudsrejser.dk` | 182 | 6 | 0 | 176 |
| `akkilahdot.fi` | 182 | 6 | 0 | 176 |
| `restplass.no` | 182 | 6 | 0 | 176 |
| `socialloop.ai` | 176 | 176 | 0 | 0 |
| `remoshift.com` | 152 | 11 | 141 | 0 |
| `revmesh2074.workers.dev` | 146 | 128 | 18 | 0 |
| `fundinglandscape.com` | 140 | 87 | 53 | 0 |
| 6834 other operators | 25152 | 23792 | 1291 | 69 |
