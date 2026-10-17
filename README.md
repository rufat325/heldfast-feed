# MCP server tool changes

Last change observed 2026-10-17T16:00:27+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10495 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 23695 hosted endpoints (read daily, and every four hours while they keep changing).

30301 changes to a tool definition: 1052 npm releases (806 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 29249 readings of hosted servers that found their tools changed; 2059 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-17 | `remote/com.starcovery/mcp` | 2026-10-17T110838885839 -> 2026-10-17T160028057532 | 7 changed | quiet |
| 2026-10-17 | `remote/no.restplass/travel-search` | 2026-10-17T122830729274 -> 2026-10-17T160027359547 | 1 changed | quiet |
| 2026-10-17 | `remote/dk.afbudsrejser/travel-search` | 2026-10-17T122824784538 -> 2026-10-17T160019170321 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.witanmarkets/witan` | 2026-10-17T110759179895 -> 2026-10-17T160018788676 | 16 changed | quiet |
| 2026-10-17 | `remote/dev.usaref/reference-data` | 2026-10-17T122822022628 -> 2026-10-17T160016635960 | 16 changed | quiet |
| 2026-10-17 | `remote/fi.akkilahdot/travel-search` | 2026-10-17T122901805768 -> 2026-10-17T160009326159 | 1 changed | quiet |
| 2026-10-17 | `remote/us.srv.vehcdj664efetfrsolne5umanq/quoteproof-mcp` | 2026-10-17T122856954857 -> 2026-10-17T160005562315 | 1 changed | quiet |
| 2026-10-17 | `remote/se.sistaminuten/travel-search` | 2026-10-17T122904368635 -> 2026-10-17T155958858014 | 1 changed | quiet |
| 2026-10-17 | `remote/cloud.pandy/tickets` | 2026-10-17T055836945794 -> 2026-10-17T155957719060 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.everyai-com/sahadeva` | 2026-10-17T122808183268 -> 2026-10-17T155957776787 | 5 changed | quiet |
| 2026-10-17 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-17T111142660726 -> 2026-10-17T155957188698 | 1 changed | quiet |
| 2026-10-17 | `remote/ai.rokha/rokha` | 2026-10-17T060224007680 -> 2026-10-17T155955780067 | 2 changed, 2 added | quiet |
| 2026-10-17 | `remote/io.github.wygogogo19/robotbase-mcp` | 2026-10-17T060225544822 -> 2026-10-17T155958029702 | 5 changed | quiet |
| 2026-10-17 | `remote/ch.swisslivingindex/swiss-living-index` | 2026-10-17T055825142307 -> 2026-10-17T155954409217 | 8 added | quiet |
| 2026-10-17 | `remote/ai.shorti/shorti` | 2026-10-17T055800779918 -> 2026-10-17T155949868867 | 2 changed | quiet |
| 2026-10-17 | `remote/ch.kulalabs.pazair/pazair` | 2026-10-17T122800976184 -> 2026-10-17T155948951160 | 1 changed, 1 added | quiet |
| 2026-10-17 | `remote/com.roamflat/esim-catalog` | 2026-10-17T055731424475 -> 2026-10-17T155946492308 | 2 changed, 5 added, 3 removed (every tool) | quiet |
| 2026-10-17 | `remote/com.remoshift/jobs` | 2026-10-17T122837028580 -> 2026-10-17T155944457945 | 1 changed | quiet |
| 2026-10-17 | `remote/com.radar-cnpj/radar-cnpj` | 2026-10-17T055718692571 -> 2026-10-17T155943378369 | 2 changed | quiet |
| 2026-10-17 | `remote/online.pageaudit/pageaudit` | 2026-10-17T122828026708 -> 2026-10-17T155934422328 | 1 added | quiet |
| 2026-10-17 | `remote/win.price/pricewin` | 2026-10-17T055954116177 -> 2026-10-17T155933332837 | 2 changed | quiet |
| 2026-10-17 | `remote/io.github.77777R7/octocrawl` | 2026-10-17T073044514325 -> 2026-10-17T155930867561 | 2 changed (every tool) | quiet |
| 2026-10-17 | `remote/com.owlchart/owlchart` | 2026-10-17T055347273338 -> 2026-10-17T155930223644 | 1 added | quiet |
| 2026-10-17 | `remote/com.neblla/neblla` | 2026-10-17T122824649995 -> 2026-10-17T155929777026 | 2 changed | quiet |
| 2026-10-17 | `remote/dev.mearef/reference-data` | 2026-10-17T122822350211 -> 2026-10-17T155928496664 | 16 changed | quiet |
| 2026-10-17 | `remote/com.sonarconnections/sonar-connections` | 2026-10-17T055552853606 -> 2026-10-17T155925428023 | 9 changed, 4 added | quiet |
| 2026-10-17 | `remote/com.pontofato/pontofato` | 2026-10-17T060045917499 -> 2026-10-17T155925423156 | 1 changed | quiet |
| 2026-10-17 | `remote/cheap.doc/mcp` | 2026-10-17T055901908684 -> 2026-10-17T155925332255 | 3 changed | quiet |
| 2026-10-17 | `remote/com.budgetpixel/mcp` | 2026-10-17T055845567621 -> 2026-10-17T155921339772 | 2 changed, 1 added | review |
| 2026-10-17 | `remote/com.pakistancaselaw/caselaw` | 2026-10-17T060025603729 -> 2026-10-17T155921944729 | 1 changed | quiet |
| 2026-10-17 | `remote/com.bitcoincreditstack/mcp` | 2026-10-17T055843345823 -> 2026-10-17T155921965474 | 2 changed | quiet |
| 2026-10-17 | `remote/com.keyvex/keyvex.1` | 2026-10-17T055427406495 -> 2026-10-17T155914318571 | 1 changed | quiet |
| 2026-10-17 | `remote/com.hireahelper/mcp` | 2026-10-17T122804920970 -> 2026-10-17T155911948598 | 16 removed | quiet |
| 2026-10-17 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-10-17T055151345288 -> 2026-10-17T155910342945 | 1 changed | review |
| 2026-10-17 | `remote/io.github.conquext/neuron` | 2026-10-17T055155146213 -> 2026-10-17T155915750494 | 3 changed, 7 added | quiet |
| 2026-10-17 | `remote/dev.latamref/reference-data` | 2026-10-17T122730306698 -> 2026-10-17T155913977766 | 16 changed | quiet |
| 2026-10-17 | `remote/com.metraipolis/knowledge-commons` | 2026-10-17T055922808351 -> 2026-10-17T155912610888 | 18 changed, 11 added, 1 removed (every tool) | quiet |
| 2026-10-17 | `remote/dev.mcphost/mcphost` | 2026-10-17T110514224414 -> 2026-10-17T155910554509 | 2 changed | quiet |
| 2026-10-17 | `remote/com.metricduck/financial-analysis` | 2026-10-17T055147689304 -> 2026-10-17T155909676933 | 1 changed | quiet |
| 2026-10-17 | `remote/io.draw/mcp` | 2026-10-17T055348314658 -> 2026-10-17T155908369263 | 1 changed | quiet |
| 2026-10-17 | `remote/app.traderspy/traderspy` | 2026-10-17T055825689903 -> 2026-10-17T155906969377 | 17 changed (every tool) | quiet |
| 2026-10-17 | `remote/io.github.industrial-platform-ai/research-brief` | 2026-10-17T065956384993 -> 2026-10-17T155905163101 | 1 changed | quiet |
| 2026-10-17 | `remote/co.getclippy/clippy` | 2026-10-17T055302123419 -> 2026-10-17T155902601730 | 5 changed (every tool) | quiet |
| 2026-10-17 | `remote/ai.autonomad/travel` | 2026-10-17T055055233861 -> 2026-10-17T155902081792 | 3 changed | quiet |
| 2026-10-17 | `remote/com.problee/problee` | 2026-10-17T055756078160 -> 2026-10-17T155901598059 | 1 changed | quiet |
| 2026-10-17 | `remote/com.preshiftiq/shiftiq-mcp` | 2026-10-17T055750474845 -> 2026-10-17T155900907788 | 10 changed, 2 added (every tool) | quiet |
| 2026-10-17 | `remote/ai.makememoneynomistakes/scoreboard` | 2026-10-17T055032683600 -> 2026-10-17T155859605062 | 3 changed | quiet |
| 2026-10-17 | `remote/io.github.tdobrowolski1/flashalpha` | 2026-10-17T072959066995 -> 2026-10-17T155859697287 | 4 changed | quiet |
| 2026-10-17 | `remote/io.github.si-imtiaz/leadquasar` | 2026-10-17T055248029366 -> 2026-10-17T155901133318 | 1 changed | quiet |
| 2026-10-17 | `remote/com.adrianhomelab/leadgen-onrc` | 2026-10-17T110655945653 -> 2026-10-17T155859713703 | 10 changed, 1 added | quiet |
| 2026-10-17 | `remote/com.keyvex/keyvex` | 2026-10-17T055710754485 -> 2026-10-17T155858456808 | 1 changed | quiet |
| 2026-10-17 | `remote/team.jogo/mcp` | 2026-10-17T055234517981 -> 2026-10-17T155854971532 | 4 changed | quiet |
| 2026-10-17 | `remote/dev.euroref/reference-data` | 2026-10-17T122714756990 -> 2026-10-17T155857920406 | 16 changed | quiet |
| 2026-10-17 | `remote/app.lovable.jessica-hill-holm/leadership-coach` | 2026-10-17T055011247649 -> 2026-10-17T155857804833 | 1 added | quiet |
| 2026-10-17 | `remote/com.marketcheck/api` | 2026-10-17T054742216180 -> 2026-10-17T155851662828 | 1 changed | quiet |
| 2026-10-17 | `remote/us.corpuslaw/corpus-legal` | 2026-10-17T054720404146 -> 2026-10-17T155847159895 | 10 changed (every tool) | quiet |
| 2026-10-17 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-17T122727105678 -> 2026-10-17T155846465392 | 3 changed | quiet |
| 2026-10-17 | `remote/io.github.barneywohl/hugging-bay` | 2026-10-17T055452205334 -> 2026-10-17T155842519260 | 3 changed | quiet |
| 2026-10-17 | `remote/com.editalmd/editalmd` | 2026-10-17T054500123306 -> 2026-10-17T155842037687 | 5 changed, 1 added | quiet |
| 2026-10-17 | `remote/space.galaxymind/galaxy-mind` | 2026-10-17T065714030035 -> 2026-10-17T155839368616 | 7 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 21713 substantive, 8138 that changed only numbers (a catalogue counter ticking, a date), 450 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 14726 | 7201 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 126 | 126 | 0 | 0 |
| `sistaminuten.se` | 109 | 4 | 0 | 105 |
| `afbudsrejser.dk` | 108 | 4 | 0 | 104 |
| `akkilahdot.fi` | 108 | 4 | 0 | 104 |
| `restplass.no` | 108 | 4 | 0 | 104 |
| `socialloop.ai` | 105 | 105 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `fundinglandscape.com` | 79 | 47 | 32 | 0 |
| `remoshift.com` | 79 | 6 | 73 | 0 |
| 3784 other operators | 11662 | 11121 | 508 | 33 |
