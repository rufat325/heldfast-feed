# MCP server tool changes

Last change observed 2026-10-30T21:06:40+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

64563 changes to a tool definition: 2657 npm releases (2411 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 61906 readings of hosted servers that found their tools changed; 3037 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-30 | `remote/com.tabflows/site` | 2026-10-28T133509141466 -> 2026-10-30T210645264293 | 1 changed | quiet |
| 2026-10-30 | `remote/no.restplass/travel-search` | 2026-10-30T152414966306 -> 2026-10-30T210642837929 | 1 changed | quiet |
| 2026-10-30 | `remote/ai.greyridgesignals/tech-risk` | 2026-10-29T063232488560 -> 2026-10-30T210638613814 | 1 added | review |
| 2026-10-30 | `remote/studio.gradients/mcp` | 2026-10-30T152353496319 -> 2026-10-30T210635056410 | 1 changed | quiet |
| 2026-10-30 | `remote/com.immersivecommons/floor10` | 2026-10-28T133120708044 -> 2026-10-30T210636039289 | 1 changed | quiet |
| 2026-10-30 | `remote/fi.akkilahdot/travel-search` | 2026-10-30T152351728139 -> 2026-10-30T210632990996 | 1 changed | quiet |
| 2026-10-30 | `remote/de.drgsystem/medical-catalogs` | 2026-10-30T132951568388 -> 2026-10-30T210638595223 | 16 changed | quiet |
| 2026-10-30 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-10-30T063142530643 -> 2026-10-30T210633489991 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.yayabough/tolca` | 2026-10-30T063138402554 -> 2026-10-30T210629663404 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.Schoasch/backtesting-arena` | 2026-10-29T133706326398 -> 2026-10-30T210629844177 | 1 changed | quiet |
| 2026-10-30 | `remote/ca.tonbot.tolca/tolca` | 2026-10-30T063138116192 -> 2026-10-30T210629438658 | 2 changed | quiet |
| 2026-10-30 | `remote/si.thinkhard/prompt-tools` | 2026-10-30T063138619185 -> 2026-10-30T210629725074 | 5 changed | quiet |
| 2026-10-30 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-30T132908170599 -> 2026-10-30T210629342431 | 1 changed | quiet |
| 2026-10-30 | `remote/dk.afbudsrejser/travel-search` | 2026-10-30T152411447698 -> 2026-10-30T210630727236 | 1 changed | quiet |
| 2026-10-30 | `remote/com.86hc/hongkong-company` | 2026-10-30T132935278645 -> 2026-10-30T210632326770 | 9 changed (every tool) | quiet |
| 2026-10-30 | `remote/com.swarmmemo/bulletin.1` | 2026-10-30T152345034020 -> 2026-10-30T210626829563 | 1 changed | quiet |
| 2026-10-30 | `remote/com.swarmmemo/bulletin` | 2026-10-30T152344591315 -> 2026-10-30T210626594464 | 1 changed | quiet |
| 2026-10-30 | `remote/com.strongsaga/gear-lookup` | 2026-10-30T063139834490 -> 2026-10-30T210625888855 | 9 changed | quiet |
| 2026-10-30 | `remote/io.taifoon/coordination-layer.1` | 2026-10-30T132920831368 -> 2026-10-30T210624469969 | 1 changed | review |
| 2026-10-30 | `remote/io.github.zambodotdev/zambo` | 2026-10-30T133036384858 -> 2026-10-30T210623835196 | 35 changed, 1 added (every tool) | quiet |
| 2026-10-30 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-30T152342574396 -> 2026-10-30T210624477268 | 1 changed | quiet |
| 2026-10-30 | `remote/dev.zambo/zambo` | 2026-10-30T133036408531 -> 2026-10-30T210624083890 | 35 changed, 1 added (every tool) | quiet |
| 2026-10-30 | `remote/com.talentanvil/talentanvil` | 2026-10-29T104526344706 -> 2026-10-30T210624131037 | 1 changed | quiet |
| 2026-10-30 | `remote/com.stayotter/stay-otter` | 2026-10-29T212851609352 -> 2026-10-30T210625972971 | 1 changed | quiet |
| 2026-10-30 | `remote/se.sistaminuten/travel-search` | 2026-10-30T152351682719 -> 2026-10-30T210623866970 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.rezearcher/tech-risk` | 2026-10-29T063236190999 -> 2026-10-30T210623124463 | 1 added | review |
| 2026-10-30 | `remote/io.github.davidgringras/scrutica` | 2026-10-28T062142735118 -> 2026-10-30T210624237944 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.bnth09productions-maker/scrapling-x402-store` | 2026-10-30T132809155581 -> 2026-10-30T210623185407 | 2 added | quiet |
| 2026-10-30 | `remote/com.techfabric/techfabric` | 2026-10-30T063206324627 -> 2026-10-30T210625014910 | 3 changed | quiet |
| 2026-10-30 | `remote/com.klarefi/mcp` | 2026-10-30T132859751653 -> 2026-10-30T210622839790 | 1 changed | quiet |
| 2026-10-30 | `remote/com.quailos/quailos` | 2026-10-29T104501746863 -> 2026-10-30T210622272124 | 1 changed, 4 added | quiet |
| 2026-10-30 | `remote/com.remoshift/jobs` | 2026-10-30T152339045729 -> 2026-10-30T210622480544 | 1 changed | quiet |
| 2026-10-30 | `remote/com.radar-cnpj/radar-cnpj` | 2026-10-30T132736985937 -> 2026-10-30T210622125490 | 4 changed, 14 added | review |
| 2026-10-30 | `remote/com.pourwire/pourwire` | 2026-10-30T152336887431 -> 2026-10-30T210620005279 | 2 changed (every tool) | quiet |
| 2026-10-30 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-30T132832080230 -> 2026-10-30T210620323256 | 2 changed | quiet |
| 2026-10-30 | `remote/com.thenewengineer/hvac` | 2026-10-30T132821945650 -> 2026-10-30T210617154440 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.SKalinin909/tradingcalc` | 2026-10-30T132740273936 -> 2026-10-30T210616189626 | 7 changed, 1 added | quiet |
| 2026-10-30 | `remote/io.github.Nadeus/toolradar` | 2026-10-29T104450052674 -> 2026-10-30T210620148100 | 8 changed, 3 added (every tool) | quiet |
| 2026-10-30 | `remote/estate.new/listings` | 2026-10-30T152334190997 -> 2026-10-30T210617346627 | 1 changed | quiet |
| 2026-10-30 | `remote/com.multicinesortega/cartelera` | 2026-10-30T063130305078 -> 2026-10-30T210617219149 | 1 changed | quiet |
| 2026-10-30 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-10-29T104103351974 -> 2026-10-30T210616469827 | 5 changed | quiet |
| 2026-10-30 | `remote/com.sonarconnections/sonar-connections` | 2026-10-30T132556358785 -> 2026-10-30T210614649774 | 5 changed | quiet |
| 2026-10-30 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-30T132742927416 -> 2026-10-30T210614324406 | 2 changed | quiet |
| 2026-10-30 | `remote/io.github.tinbox-labs/spawnpop` | 2026-10-28T133536285408 -> 2026-10-30T210614494144 | 1 changed | quiet |
| 2026-10-30 | `remote/fr.synergieloc/immobilier` | 2026-10-30T132812430734 -> 2026-10-30T210616510825 | 30 added | quiet |
| 2026-10-30 | `remote/dev.tanod/tanod` | 2026-10-30T063145935599 -> 2026-10-30T210615977851 | 1 changed | quiet |
| 2026-10-30 | `remote/com.solvscore/mcp` | 2026-10-29T104356241409 -> 2026-10-30T210613383899 | 3 added | review |
| 2026-10-30 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-30T063135149082 -> 2026-10-30T210613536012 | 3 changed | quiet |
| 2026-10-30 | `remote/at.space-core/game` | 2026-10-30T063136392746 -> 2026-10-30T210615168654 | 1 changed | quiet |
| 2026-10-30 | `remote/tools.settled/settled` | 2026-10-30T132732483116 -> 2026-10-30T210612383511 | 4 changed | quiet |
| 2026-10-30 | `remote/io.github.cnghockey/sats4ai` | 2026-10-29T063223723110 -> 2026-10-30T210612719848 | 3 changed | quiet |
| 2026-10-30 | `remote/wiki.rust/rust-wiki` | 2026-10-28T062214410270 -> 2026-10-30T210611774581 | 1 added | quiet |
| 2026-10-30 | `remote/io.github.majidkabir/sootcase` | 2026-10-29T212856589661 -> 2026-10-30T210611902071 | 2 changed | quiet |
| 2026-10-30 | `remote/dev.sportsapis/sportsapis` | 2026-10-29T104313159729 -> 2026-10-30T210611114321 | 1 changed | quiet |
| 2026-10-30 | `remote/dev.releasealert/mcp` | 2026-10-30T132642711742 -> 2026-10-30T210609908411 | 2 added | quiet |
| 2026-10-30 | `remote/site.chatgpt.orellise.relay-agent-services/relay` | 2026-10-28T133049380299 -> 2026-10-30T210611929052 | 2 changed | quiet |
| 2026-10-30 | `remote/com.straelo/relay` | 2026-10-30T132649519408 -> 2026-10-30T210609512800 | 2 added | quiet |
| 2026-10-30 | `remote/pl.przetargowyjanusz/tenders` | 2026-10-30T132528703841 -> 2026-10-30T210607990211 | 1 changed | quiet |
| 2026-10-30 | `remote/es.proceres/proceres` | 2026-10-30T132523796922 -> 2026-10-30T210606843797 | 2 changed | quiet |
| 2026-10-30 | `remote/com.pontofato/pontofato` | 2026-10-30T132614595242 -> 2026-10-30T210608394640 | 3 changed, 7 added | review |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 42377 substantive, 21448 that changed only numbers (a catalogue counter ticking, a date), 738 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 35898 | 15833 | 20065 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1126 | 1126 | 0 | 0 |
| `caseyjhand.com` | 282 | 282 | 0 | 0 |
| `sistaminuten.se` | 175 | 6 | 0 | 169 |
| `afbudsrejser.dk` | 174 | 6 | 0 | 168 |
| `akkilahdot.fi` | 174 | 6 | 0 | 168 |
| `restplass.no` | 174 | 6 | 0 | 168 |
| `socialloop.ai` | 168 | 168 | 0 | 0 |
| `remoshift.com` | 144 | 10 | 134 | 0 |
| `fundinglandscape.com` | 134 | 85 | 49 | 0 |
| `revmesh2074.workers.dev` | 129 | 116 | 13 | 0 |
| 6581 other operators | 23644 | 22392 | 1187 | 65 |
