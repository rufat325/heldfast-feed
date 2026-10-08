# MCP server tool changes

Last change observed 2026-10-08T06:42:49+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10128 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 21701 hosted endpoints (read daily, and every four hours while they keep changing).

22976 changes to a tool definition: 789 npm releases (543 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 22187 readings of hosted servers that found their tools changed; 330 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-08 | `remote/com.zinvyl/marketplace` | 2026-10-07T155001812650 -> 2026-10-08T064251238725 | 8 changed | quiet |
| 2026-10-08 | `remote/ai.thebotique.www/sigil` | 2026-10-07T001237037826 -> 2026-10-08T064248933944 | 2 changed | quiet |
| 2026-10-08 | `remote/se.sistaminuten/travel-search` | 2026-10-07T213833230341 -> 2026-10-08T064248251311 | 1 changed | quiet |
| 2026-10-08 | `remote/io.github.SoapyRED/freightutils` | 2026-10-07T213839355895 -> 2026-10-08T064247231353 | 12 changed | quiet |
| 2026-10-08 | `remote/com.codestringers/mcp` | 2026-10-06T110358709871 -> 2026-10-08T064245529644 | 6 changed | quiet |
| 2026-10-08 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-10-07T001233679253 -> 2026-10-08T064245232896 | 3 changed | quiet |
| 2026-10-08 | `remote/fi.akkilahdot/travel-search` | 2026-10-07T213837986602 -> 2026-10-08T064244429403 | 1 changed | quiet |
| 2026-10-08 | `remote/io.github.kor-jongwon/witan` | 2026-10-06T110343350997 -> 2026-10-08T064244187956 | 6 changed, 1 added | quiet |
| 2026-10-08 | `remote/io.github.CodeWever/wever-labs-products` | 2026-10-07T213835609971 -> 2026-10-08T064243123005 | 1 changed | review |
| 2026-10-08 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-07T213829522323 -> 2026-10-08T064244203005 | 1 changed, 1 added | quiet |
| 2026-10-08 | `remote/lat.watchtower/watchtower` | 2026-10-07T063423145737 -> 2026-10-08T064241994329 | 8 changed (every tool) | quiet |
| 2026-10-08 | `remote/com.youspot/youspot` | 2026-10-07T213855469766 -> 2026-10-08T064242245474 | 4 changed | quiet |
| 2026-10-08 | `remote/direct.vote/vote-direct` | 2026-10-06T110332434979 -> 2026-10-08T064241981486 | 5 changed | quiet |
| 2026-10-08 | `remote/com.vermarco/marketplace` | 2026-10-07T213833850704 -> 2026-10-08T064240998030 | 1 changed | quiet |
| 2026-10-08 | `remote/com.thefomite/fomite` | 2026-10-07T001229942961 -> 2026-10-08T064237860918 | 1 changed | quiet |
| 2026-10-08 | `remote/no.restplass/travel-search` | 2026-10-07T213847783250 -> 2026-10-08T064236112715 | 1 changed | quiet |
| 2026-10-08 | `remote/io.github.withgrokbot/verified-catalog` | 2026-10-07T001231615996 -> 2026-10-08T064234339691 | 1 changed | review |
| 2026-10-08 | `remote/com.swarmmemo/bulletin` | 2026-10-07T213829785939 -> 2026-10-08T064236698926 | 75 changed, 2 added, 5 removed (every tool) | quiet |
| 2026-10-08 | `remote/io.github.dtajitdinov-aris/sphere-marketplace` | 2026-10-07T154941533458 -> 2026-10-08T064235357905 | 1 added, 1 removed | quiet |
| 2026-10-08 | `remote/dk.afbudsrejser/travel-search` | 2026-10-07T213842418169 -> 2026-10-08T064233062435 | 1 changed | quiet |
| 2026-10-08 | `remote/com.toolfound/toolfound` | 2026-10-06T184023292694 -> 2026-10-08T064233424993 | 18 changed | quiet |
| 2026-10-08 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-07T213824433433 -> 2026-10-08T064232607009 | 1 changed | quiet |
| 2026-10-08 | `remote/com.scribiz/mcp` | 2026-10-07T154925349492 -> 2026-10-08T064233298279 | 2 changed | quiet |
| 2026-10-08 | `remote/io.github.VoiceScapee/voicescape` | 2026-10-07T213839575381 -> 2026-10-08T064230746307 | 14 added | quiet |
| 2026-10-08 | `remote/ai.satohub/onchain-agents` | 2026-10-07T063259798301 -> 2026-10-08T064231867347 | 1 changed | quiet |
| 2026-10-08 | `remote/ai.shorti/shorti` | 2026-10-07T213822933688 -> 2026-10-08T064231360240 | 2 changed, 1 removed | quiet |
| 2026-10-08 | `remote/ru.quintadb/mcp` | 2026-10-06T133724179847 -> 2026-10-08T064231636708 | 7 changed | quiet |
| 2026-10-08 | `remote/net.tipmaster/consensus` | 2026-10-06T110223041138 -> 2026-10-08T064228763987 | 2 changed, 1 added | quiet |
| 2026-10-08 | `remote/fun.publish/mcp` | 2026-10-07T154919906453 -> 2026-10-08T064228925609 | 1 added | quiet |
| 2026-10-08 | `remote/com.trustbaselab/rcb-data` | 2026-10-06T110233285703 -> 2026-10-08T064230654245 | 1 changed | quiet |
| 2026-10-08 | `remote/com.remoshift/jobs` | 2026-10-07T213817861725 -> 2026-10-08T064228122973 | 1 changed | quiet |
| 2026-10-08 | `remote/com.predictionmarketspicks/quant` | 2026-10-06T110000742947 -> 2026-10-08T064227996914 | 4 added | quiet |
| 2026-10-08 | `remote/io.github.yschimke/compose-preview` | 2026-10-07T213817088251 -> 2026-10-08T064226448008 | 1 changed, 3 added | quiet |
| 2026-10-08 | `remote/com.pixharvest/tariff-data` | 2026-10-07T213808658932 -> 2026-10-08T064225278480 | 1 changed, 1 added | review |
| 2026-10-08 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-07T001222277418 -> 2026-10-08T064225357719 | 1 changed | quiet |
| 2026-10-08 | `remote/com.predictionmarketspicks/fantasy-draft` | 2026-10-06T110140842083 -> 2026-10-08T064225651636 | 4 changed | quiet |
| 2026-10-08 | `remote/re.parcellai/parcellaire` | 2026-10-07T213809092790 -> 2026-10-08T064224923572 | 1 added | quiet |
| 2026-10-08 | `remote/io.github.KyleClouthier/secondstrike` | 2026-10-06T110130203843 -> 2026-10-08T064222320868 | 1 changed | quiet |
| 2026-10-08 | `remote/com.quintadb/mcp` | 2026-10-06T133806003579 -> 2026-10-08T064223647314 | 7 changed | quiet |
| 2026-10-08 | `remote/com.qevrulan/lockzone` | 2026-10-07T063327155660 -> 2026-10-08T064222122838 | 1 changed | quiet |
| 2026-10-08 | `remote/com.oods-foundry/foundry` | 2026-10-07T154912644449 -> 2026-10-08T064222279356 | 8 changed | quiet |
| 2026-10-08 | `remote/io.github.Perufitlife/postwire-mcp` | 2026-10-07T154932462529 -> 2026-10-08T064220603825 | 2 changed | quiet |
| 2026-10-08 | `remote/ai.rokha/rokha` | 2026-10-07T213825205257 -> 2026-10-08T064220441124 | 1 added | quiet |
| 2026-10-08 | `remote/io.github.samuelzcom/chauffeur-booking` | 2026-10-07T154936671730 -> 2026-10-08T064226468711 | 5 changed (every tool) | quiet |
| 2026-10-08 | `remote/io.github.naief9961-tech/naif-fixgraph` | 2026-10-06T013110746339 -> 2026-10-08T064219981910 | 2 changed | quiet |
| 2026-10-08 | `remote/com.multicinesortega/cartelera` | 2026-10-07T213808563205 -> 2026-10-08T064220377505 | 1 changed | quiet |
| 2026-10-08 | `remote/dev.pdfmd/pdf-to-markdown` | 2026-10-07T001214360238 -> 2026-10-08T064217675708 | 1 changed | quiet |
| 2026-10-08 | `remote/ua.com.quintadb/mcp` | 2026-10-06T133654591166 -> 2026-10-08T064220332486 | 7 changed | quiet |
| 2026-10-08 | `remote/com.pruviq/verdicts` | 2026-10-06T110049892579 -> 2026-10-08T064216888693 | 1 changed | quiet |
| 2026-10-08 | `remote/com.widely-mobile/widely` | 2026-10-07T154907137049 -> 2026-10-08T064217489616 | 1 changed | quiet |
| 2026-10-08 | `remote/im.peoplesearch/email-finder` | 2026-10-07T063302627818 -> 2026-10-08T064215339418 | 2 changed | quiet |
| 2026-10-08 | `remote/co.civai.nova/support-agent-admin` | 2026-10-07T213821167845 -> 2026-10-08T064215368175 | 2 removed | quiet |
| 2026-10-08 | `remote/io.github.nimbusbci/nimbus-mcp` | 2026-10-07T063318114909 -> 2026-10-08T064218747443 | 2 added | quiet |
| 2026-10-08 | `remote/gl.parse/mcp` | 2026-10-07T213758738476 -> 2026-10-08T064214878446 | 4 changed | quiet |
| 2026-10-08 | `remote/com.ontarioprotocol/ontario-protocol` | 2026-10-06T110014805226 -> 2026-10-08T064214063056 | 5 removed | quiet |
| 2026-10-08 | `remote/co.civai.nova/research-agent` | 2026-10-07T213816420172 -> 2026-10-08T064213867257 | 2 removed | quiet |
| 2026-10-08 | `remote/co.civai.nova/google-sheets-agent` | 2026-10-07T213816301977 -> 2026-10-08T064213754599 | 2 removed | quiet |
| 2026-10-08 | `remote/com.jojapi/swift-ai` | 2026-10-07T063340618665 -> 2026-10-08T064212629315 | 1 changed | quiet |
| 2026-10-08 | `remote/io.github.choaticpixels/wicked-mcp` | 2026-10-07T213815216072 -> 2026-10-08T064209915969 | 6 changed, 2 added | quiet |
| 2026-10-08 | `remote/club.goodleads/new-business-owner-contacts` | 2026-10-06T105911957882 -> 2026-10-08T064209963624 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 16161 substantive, 6472 that changed only numbers (a catalogue counter ticking, a date), 343 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 11736 | 5690 | 6046 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `sistaminuten.se` | 83 | 2 | 0 | 81 |
| `afbudsrejser.dk` | 82 | 2 | 0 | 80 |
| `akkilahdot.fi` | 82 | 2 | 0 | 80 |
| `restplass.no` | 82 | 2 | 0 | 80 |
| `socialloop.ai` | 80 | 80 | 0 | 0 |
| `caseyjhand.com` | 74 | 74 | 0 | 0 |
| `dayze.com` | 65 | 65 | 0 | 0 |
| `remoshift.com` | 58 | 2 | 56 | 0 |
| 2846 other operators | 7772 | 7380 | 370 | 22 |
