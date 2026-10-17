# MCP server tool changes

Last change observed 2026-10-17T07:06:54+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10495 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 23695 hosted endpoints (read daily, and every four hours while they keep changing).

29988 changes to a tool definition: 1050 npm releases (804 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 28938 readings of hosted servers that found their tools changed; 1996 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-17 | `remote/com.youspot/youspot` | 2026-10-17T060427162725 -> 2026-10-17T070655350296 | 1 changed | quiet |
| 2026-10-17 | `remote/fi.akkilahdot/travel-search` | 2026-10-17T055920650384 -> 2026-10-17T070552431014 | 1 changed | quiet |
| 2026-10-17 | `remote/se.sistaminuten/travel-search` | 2026-10-17T055617135694 -> 2026-10-17T070518486086 | 1 changed | quiet |
| 2026-10-17 | `remote/eu.skavio/paid-micro-apis` | 2026-10-17T055618001184 -> 2026-10-17T070518267367 | 18 changed (every tool) | quiet |
| 2026-10-17 | `remote/no.restplass/travel-search` | 2026-10-17T060452368842 -> 2026-10-17T070513703016 | 1 changed | quiet |
| 2026-10-17 | `remote/app.swiftprism/swiftprism` | 2026-10-06T110133137302 -> 2026-10-17T070504217425 | 2 changed | quiet |
| 2026-10-17 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-17T055833678907 -> 2026-10-17T070501096067 | 1 changed | quiet |
| 2026-10-17 | `remote/com.digitaltableteur/mcp` | 2026-09-28T142316436555 -> 2026-10-17T070455670647 | 4 changed | quiet |
| 2026-10-17 | `remote/dk.afbudsrejser/travel-search` | 2026-10-17T060420444996 -> 2026-10-17T070445492339 | 1 changed | quiet |
| 2026-10-17 | `remote/com.wizeb/ai-native-index` | 2026-10-02T130803301249 -> 2026-10-17T070441620197 | 4 changed | quiet |
| 2026-10-17 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-17T055808395315 -> 2026-10-17T070432162161 | 1 changed | quiet |
| 2026-10-17 | `remote/com.shipshapedata/shipshape-data` | 2026-10-07T154939717958 -> 2026-10-17T070432476060 | 1 changed | quiet |
| 2026-10-17 | `remote/app.robohub/robohub` | 2026-09-23T162836056859 -> 2026-10-17T070356867315 | 2 changed | quiet |
| 2026-10-17 | `remote/xyz.signomy/civitae` | 2026-10-06T110144251949 -> 2026-10-17T070323310896 | 7 changed, 11 added | quiet |
| 2026-10-17 | `remote/com.organikpi/organikpi` | 2026-09-28T142105014795 -> 2026-10-17T070314176496 | 2 added | quiet |
| 2026-10-17 | `remote/app.seatsherpa/rides` | 2026-10-17T060252446771 -> 2026-10-17T070311555539 | 3 changed | quiet |
| 2026-10-17 | `remote/com.oceanalt/aml` | 2026-10-17T060010056793 -> 2026-10-17T070307231710 | 3 changed | quiet |
| 2026-10-17 | `remote/app.repopilot/repopilot` | 2026-10-02T210135321764 -> 2026-10-17T070301553879 | 1 changed | quiet |
| 2026-10-17 | `remote/ing.rentseek/evidence` | 2026-10-02T072006422886 -> 2026-10-17T070251193847 | 1 changed | quiet |
| 2026-10-17 | `remote/im.peoplesearch/email-finder` | 2026-10-08T064215339418 -> 2026-10-17T070222404886 | 3 changed | quiet |
| 2026-10-17 | `remote/com.hireahelper/mcp` | 2026-10-06T013056046256 -> 2026-10-17T070050387855 | 16 added | quiet |
| 2026-10-17 | `remote/gl.parse/mcp` | 2026-10-17T055207113504 -> 2026-10-17T070023652967 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.industrial-platform-ai/research-brief` | 2026-10-17T055324052389 -> 2026-10-17T065956384993 | 1 changed | quiet |
| 2026-10-17 | `remote/land.fabrica/mcp-testnet` | 2026-10-17T055307597764 -> 2026-10-17T065940206116 | 4 changed | quiet |
| 2026-10-17 | `remote/land.fabrica/mcp` | 2026-10-17T055116809483 -> 2026-10-17T065926767405 | 4 changed, 1 added | quiet |
| 2026-10-17 | `remote/com.convertlyft/convertlyft` | 2026-10-17T055108504111 -> 2026-10-17T065916607090 | 19 changed | quiet |
| 2026-10-17 | `remote/xyz.loadbay/loadbay` | 2026-09-25T120303414549 -> 2026-10-17T065910390957 | 6 changed (every tool) | quiet |
| 2026-10-17 | `remote/xyz.iposignal/iposignal` | 2026-09-23T202138867587 -> 2026-10-17T065847876479 | 2 added | quiet |
| 2026-10-17 | `remote/fr.humanmirror/one` | 2026-09-28T141655826720 -> 2026-10-17T065837954957 | 1 changed | quiet |
| 2026-10-17 | `remote/cloud.hoboworks/agent-market` | 2026-10-06T105539767667 -> 2026-10-17T065825747024 | 8 changed, 5 added, 8 removed | quiet |
| 2026-10-17 | `remote/io.github.pipeworx-io/steam` | 2026-10-08T134730033005 -> 2026-10-17T065814624286 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.pipeworx-io/uk-flood-monitoring` | 2026-10-08T134743656260 -> 2026-10-17T065805544757 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.pipeworx-io/uk-contracts` | 2026-10-08T134743603214 -> 2026-10-17T065805315084 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.pipeworx-io/tx-dmv` | 2026-10-08T134743613596 -> 2026-10-17T065802810485 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.pipeworx-io/trivia` | 2026-10-08T134743557332 -> 2026-10-17T065800431912 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.pipeworx-io/traveltime` | 2026-10-08T134743281423 -> 2026-10-17T065759627158 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.pipeworx-io/transport-nsw` | 2026-10-08T134743179648 -> 2026-10-17T065759076754 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.pipeworx-io/tomtom` | 2026-10-08T134743078851 -> 2026-10-17T065757662263 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.pipeworx-io/tomorrow-io` | 2026-10-08T134743065386 -> 2026-10-17T065757499171 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.pipeworx-io/todoist` | 2026-10-08T134742978879 -> 2026-10-17T065756322253 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/space.galaxymind/galaxy-mind` | 2026-10-17T054607925876 -> 2026-10-17T065714030035 | 2 changed | quiet |
| 2026-10-17 | `remote/io.github.pipeworx-io/buzzword-density` | 2026-10-08T134632886134 -> 2026-10-17T065649285990 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.pipeworx-io/arcgis-marioncountyor` | 2026-10-08T134629411250 -> 2026-10-17T065646722041 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.xOyabunx/everycalc` | 2026-10-17T054538251106 -> 2026-10-17T065643421731 | 69 changed (every tool) | quiet |
| 2026-10-17 | `remote/io.github.pipeworx-io/ai-incident-db` | 2026-10-08T134626250961 -> 2026-10-17T065644288652 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-17T054324512128 -> 2026-10-17T065639962246 | 2 changed | quiet |
| 2026-10-17 | `remote/com.entsoemcp/entsoe-mcp` | 2026-10-17T054306008564 -> 2026-10-17T065619457516 | 1 changed | quiet |
| 2026-10-17 | `remote/org.electionindex/elections` | 2026-10-03T135703149907 -> 2026-10-17T065614460912 | 5 changed | quiet |
| 2026-10-17 | `remote/io.github.fredxhansson-cmyk/fuze` | 2026-10-17T054735325376 -> 2026-10-17T065610356082 | 3 changed | quiet |
| 2026-10-17 | `remote/boats.charter/charter-boats` | 2026-10-17T054357541216 -> 2026-10-17T065558485333 | 1 changed | quiet |
| 2026-10-17 | `remote/uk.co.buildbatch/buildbatch` | 2026-10-13T193420791868 -> 2026-10-17T065545415422 | 1 changed | quiet |
| 2026-10-17 | `remote/org.aspern/aspern` | 2026-10-17T054431465875 -> 2026-10-17T065504084366 | 2 changed | quiet |
| 2026-10-17 | `remote/com.ransomware-tracker.api/dragonseye` | 2026-10-17T054313241502 -> 2026-10-17T065421404213 | 7 added | review |
| 2026-10-17 | `remote/com.orioncmd.api/checks` | 2026-10-17T054307925467 -> 2026-10-17T065417008060 | 3 added | review |
| 2026-10-17 | `remote/directory.nohumans/registry` | 2026-10-17T054307869414 -> 2026-10-17T065415266941 | 1 changed | quiet |
| 2026-10-17 | `remote/com.ashareapi/ashare-data-api` | 2026-10-17T054030656672 -> 2026-10-17T065240515185 | 3 changed | quiet |
| 2026-10-17 | `remote/ai.askmiles/catalog` | 2026-09-29T072508227905 -> 2026-10-17T065239331396 | 1 changed | quiet |
| 2026-10-17 | `remote/com.alkemata/public-knowledge` | 2026-10-17T054009943832 -> 2026-10-17T065226683963 | 17 changed, 4 removed (every tool) | quiet |
| 2026-10-17 | `remote/wedding.aisle/aisle` | 2026-10-13T193417747619 -> 2026-10-17T065223159157 | 2 changed, 1 added | quiet |
| 2026-10-17 | `remote/jobs.aitraining/ai-training-jobs` | 2026-10-17T054156857863 -> 2026-10-17T065219476704 | 3 changed (every tool) | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 21439 substantive, 8115 that changed only numbers (a catalogue counter ticking, a date), 434 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 14681 | 7156 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 126 | 126 | 0 | 0 |
| `sistaminuten.se` | 105 | 4 | 0 | 101 |
| `afbudsrejser.dk` | 104 | 4 | 0 | 100 |
| `akkilahdot.fi` | 104 | 4 | 0 | 100 |
| `restplass.no` | 104 | 4 | 0 | 100 |
| `socialloop.ai` | 102 | 102 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `remoshift.com` | 76 | 4 | 72 | 0 |
| `fundinglandscape.com` | 75 | 44 | 31 | 0 |
| 3741 other operators | 11420 | 10900 | 487 | 33 |
