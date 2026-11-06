# MCP server tool changes

Last change observed 2026-11-06T14:49:52+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

79521 changes to a tool definition: 3402 npm releases (3156 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 76119 readings of hosted servers that found their tools changed; 3492 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-06 | `remote/run.cityheart/heart-routes` | 2026-09-23T202515677422 -> 2026-11-06T144953160321 | 1 changed | quiet |
| 2026-11-06 | `remote/com.xquik/mcp` | 2026-11-05T115608347455 -> 2026-11-06T144945607537 | 2 changed | quiet |
| 2026-11-06 | `remote/com.synthexforge.x402/paid-agent-services` | 2026-11-02T163748884830 -> 2026-11-06T144942837416 | 1 added | quiet |
| 2026-11-06 | `remote/com.youspot/youspot` | 2026-11-02T185426210875 -> 2026-11-06T144937773864 | 1 added | quiet |
| 2026-11-06 | `remote/uk.co.speedi/availability` | 2026-11-05T151109014164 -> 2026-11-06T144949865503 | 1 changed, 2 added | quiet |
| 2026-11-06 | `remote/com.stackerscan/stackerscan` | 2026-10-08T155540213075 -> 2026-11-06T144930785951 | 4 changed | quiet |
| 2026-11-06 | `remote/io.github.rezearcher/tech-risk` | 2026-10-31T202127594043 -> 2026-11-06T144927719728 | 6 changed | review |
| 2026-11-06 | `remote/ai.reg-bot/compliance-oracle` | 2026-11-01T135414258916 -> 2026-11-06T144924918481 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.imokokok/insight-oracle` | 2026-11-05T010701487278 -> 2026-11-06T144922038341 | 1 changed | quiet |
| 2026-11-06 | `remote/help.servicebuddy/mcp` | 2026-10-06T110323178278 -> 2026-11-06T144912725291 | 1 added | quiet |
| 2026-11-06 | `remote/com.satellitequotes/satellitequotes` | 2026-11-01T135458185213 -> 2026-11-06T144911709970 | 1 changed | quiet |
| 2026-11-06 | `remote/studio.gradients/mcp` | 2026-11-06T072830405225 -> 2026-11-06T144908974179 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.cooyun/etuki-finops-mcp` | 2026-11-02T163642014097 -> 2026-11-06T144902549589 | 4 changed, 3 added (every tool) | quiet |
| 2026-11-06 | `remote/io.github.mattlsmith/navmds` | 2026-09-23T160846847041 -> 2026-11-06T144902035749 | 12 changed (every tool) | quiet |
| 2026-11-06 | `remote/io.github.fomosdeimos-gif/ora-mcp` | 2026-09-23T161043932826 -> 2026-11-06T144853861612 | 9 changed (every tool) | quiet |
| 2026-11-06 | `remote/com.gotfreefax/mcp` | 2026-09-23T160842146342 -> 2026-11-06T144849944398 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-06T072814935765 -> 2026-11-06T144849989880 | 1 changed | quiet |
| 2026-11-06 | `remote/net.somantic/immobiliensuche` | 2026-10-26T133809494507 -> 2026-11-06T144842831743 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.ceedot-rock/slid-phi-labs` | 2026-11-06T072810550465 -> 2026-11-06T144839767747 | 2 changed | quiet |
| 2026-11-06 | `remote/fi.akkilahdot/travel-search` | 2026-11-06T072827567964 -> 2026-11-06T144839106944 | 1 changed | quiet |
| 2026-11-06 | `remote/no.restplass/travel-search` | 2026-11-06T072810698706 -> 2026-11-06T144837630359 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-06T072825318889 -> 2026-11-06T144833550805 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.openaccountants/openaccountants` | 2026-11-03T145045012880 -> 2026-11-06T144832066134 | 4 changed | quiet |
| 2026-11-06 | `remote/xyz.tereno/tereno` | 2026-11-03T145017367474 -> 2026-11-06T144831259794 | 3 changed, 1 added | review |
| 2026-11-06 | `remote/io.ocolo.www/project-requests` | 2026-09-29T073507965985 -> 2026-11-06T144831739600 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.privatelawattorneys/wiki-private-law` | 2026-10-26T052336733777 -> 2026-11-06T144831754441 | 3 changed | quiet |
| 2026-11-06 | `remote/io.taifoon/coordination-layer.1` | 2026-11-05T222222141955 -> 2026-11-06T144828814506 | 1 changed | review |
| 2026-11-06 | `remote/com.swiftprobate/probate` | 2026-11-02T163441266610 -> 2026-11-06T144828279878 | 1 changed | quiet |
| 2026-11-06 | `remote/se.sistaminuten/travel-search` | 2026-11-06T072808364828 -> 2026-11-06T144825472912 | 1 changed | quiet |
| 2026-11-06 | `remote/com.wjorg/legal-mcp` | 2026-10-26T133623003173 -> 2026-11-06T144824107069 | 1 added | quiet |
| 2026-11-06 | `remote/io.github.girapphe/memostem` | 2026-10-19T052423671763 -> 2026-11-06T144813713594 | 1 added | quiet |
| 2026-11-06 | `remote/com.vibresia/music-visualizer` | 2026-11-02T163543343992 -> 2026-11-06T144807712251 | 3 changed | quiet |
| 2026-11-06 | `remote/io.github.suanrongbaicai/vibecodepicks` | 2026-11-01T135303182136 -> 2026-11-06T144805878780 | 13 changed, 3 added (every tool) | quiet |
| 2026-11-06 | `remote/com.distributedrisk/desk` | 2026-11-02T163545986719 -> 2026-11-06T144805549621 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-06T072827045551 -> 2026-11-06T144808246741 | 3 changed | quiet |
| 2026-11-06 | `remote/io.github.jeannicolasdavid1979/verdictl402` | 2026-10-26T133557800800 -> 2026-11-06T144756697380 | 1 added | quiet |
| 2026-11-06 | `remote/ai.arcreport/mcp` | 2026-11-02T163535638234 -> 2026-11-06T144754499106 | 2 changed | quiet |
| 2026-11-06 | `remote/io.untax/untax` | 2026-11-02T163530923746 -> 2026-11-06T144753230825 | 10 changed, 71 added, 10 removed (every tool) | review |
| 2026-11-06 | `remote/gg.unicum/wot-stats` | 2026-10-27T145845094234 -> 2026-11-06T144753221063 | 2 added | quiet |
| 2026-11-06 | `remote/dk.afbudsrejser/travel-search` | 2026-11-06T072807872972 -> 2026-11-06T144753165988 | 1 changed | quiet |
| 2026-11-06 | `remote/sg.cashew/mcp` | 2026-11-04T123831112600 -> 2026-11-06T144750546189 | 3 changed | quiet |
| 2026-11-06 | `remote/com.tulsafoampros/booking` | 2026-10-26T133420674785 -> 2026-11-06T144747553628 | 1 changed | quiet |
| 2026-11-06 | `remote/com.autoridaddigital.www/geo` | 2026-11-05T115358545943 -> 2026-11-06T144746719820 | 1 changed | quiet |
| 2026-11-06 | `remote/ai.arcreport/ask` | 2026-11-03T024308288741 -> 2026-11-06T144745271829 | 18 changed, 6 added (every tool) | quiet |
| 2026-11-06 | `remote/com.alexandria-archive/archive` | 2026-11-01T135715918414 -> 2026-11-06T144743775460 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.wygogogo19/robotbase-web3` | 2026-10-26T133712831881 -> 2026-11-06T144741214736 | 3 changed, 5 added | quiet |
| 2026-11-06 | `remote/kr.pe.trading/community` | 2026-09-26T114301117590 -> 2026-11-06T144737080746 | 3 changed | quiet |
| 2026-11-06 | `remote/io.github.ysgjay/token-command-center` | 2026-10-17T055839805145 -> 2026-11-06T144736506957 | 2 added | quiet |
| 2026-11-06 | `remote/com.veritaset/mcp` | 2026-11-05T115609038484 -> 2026-11-06T144729417752 | 1 changed | quiet |
| 2026-11-06 | `remote/com.theopenapps/openapps` | 2026-10-29T104400656071 -> 2026-11-06T144726669745 | 2 changed, 2 added | quiet |
| 2026-11-06 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-06T072825474773 -> 2026-11-06T144725796384 | 2 changed, 3 removed | quiet |
| 2026-11-06 | `remote/com.theagentsindex/mcp` | 2026-11-02T065452002193 -> 2026-11-06T144724421148 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-06T072822075491 -> 2026-11-06T144724234858 | 1 changed | quiet |
| 2026-11-06 | `remote/com.tetheredtrust/tethered-trust` | 2026-10-19T135418808891 -> 2026-11-06T144718663913 | 4 changed | quiet |
| 2026-11-06 | `remote/io.github.mooshee/untax` | 2026-10-29T153810874874 -> 2026-11-06T144717757291 | 10 changed, 71 added, 10 removed (every tool) | review |
| 2026-11-06 | `remote/io.github.exquad/thecablecode` | 2026-11-05T115302164971 -> 2026-11-06T144715715706 | 1 changed, 1 added | quiet |
| 2026-11-06 | `remote/cc.thecolony/mcp-server` | 2026-11-02T163705346322 -> 2026-11-06T144716101645 | 1 changed | quiet |
| 2026-11-06 | `remote/com.struxurenorcal.walnbot/struxure-knowledge-base` | 2026-10-19T135416741759 -> 2026-11-06T144715049021 | 7 added | quiet |
| 2026-11-06 | `remote/global.uain/network` | 2026-10-26T133643801249 -> 2026-11-06T144713074893 | 1 added | quiet |
| 2026-11-06 | `remote/io.github.voicehook-ai/voicehook` | 2026-11-05T115327115103 -> 2026-11-06T144710938574 | 2 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 49470 substantive, 29191 that changed only numbers (a catalogue counter ticking, a date), 860 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 43271 | 15883 | 27388 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1604 | 1604 | 0 | 0 |
| `caseyjhand.com` | 354 | 354 | 0 | 0 |
| `sistaminuten.se` | 202 | 6 | 0 | 196 |
| `afbudsrejser.dk` | 201 | 6 | 0 | 195 |
| `akkilahdot.fi` | 201 | 6 | 0 | 195 |
| `restplass.no` | 201 | 6 | 0 | 195 |
| `socialloop.ai` | 194 | 194 | 0 | 0 |
| `modevc.com` | 174 | 174 | 0 | 0 |
| `revmesh2074.workers.dev` | 169 | 149 | 20 | 0 |
| `remoshift.com` | 165 | 14 | 151 | 0 |
| 7809 other operators | 30444 | 28733 | 1632 | 79 |
