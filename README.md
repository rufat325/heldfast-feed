# MCP server tool changes

Last change observed 2026-10-28T21:25:31+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

58781 changes to a tool definition: 2482 npm releases (2236 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 56299 readings of hosted servers that found their tools changed; 2908 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-28 | `remote/com.rycrentals/deals` | 2026-10-28T133502011651 -> 2026-10-28T212532296711 | 2 changed | quiet |
| 2026-10-28 | `remote/no.restplass/travel-search` | 2026-10-28T153308144475 -> 2026-10-28T212531878769 | 1 changed | quiet |
| 2026-10-28 | `remote/dev.pressmark/pressmark` | 2026-10-27T210233463635 -> 2026-10-28T212532047490 | 1 changed | quiet |
| 2026-10-28 | `remote/io.github.junoventures/dojoplus-co` | 2026-10-26T133737292506 -> 2026-10-28T212523534320 | 26 changed (every tool) | quiet |
| 2026-10-28 | `remote/dk.afbudsrejser/travel-search` | 2026-10-28T153302527381 -> 2026-10-28T212519986941 | 1 changed | quiet |
| 2026-10-28 | `remote/de.wouhr/catalog` | 2026-10-28T133412543193 -> 2026-10-28T212519302346 | 3 changed (every tool) | quiet |
| 2026-10-28 | `remote/de.wosneaker/catalog` | 2026-10-28T133412123355 -> 2026-10-28T212517817148 | 3 changed (every tool) | quiet |
| 2026-10-28 | `remote/de.wopool/catalog` | 2026-10-28T133410316640 -> 2026-10-28T212517829648 | 3 changed (every tool) | quiet |
| 2026-10-28 | `remote/io.github.junoventures/vilamariana-sampa-br` | 2026-10-26T133702851137 -> 2026-10-28T212508866470 | 28 changed (every tool) | quiet |
| 2026-10-28 | `remote/io.github.CYAN-ECLIPSE-TECHNOLOGIES-LLC/white-report` | 2026-10-28T062206915161 -> 2026-10-28T212446598545 | 7 added | quiet |
| 2026-10-28 | `remote/fr.synergieloc/immobilier` | 2026-10-28T133221026527 -> 2026-10-28T212447096043 | 36 added | quiet |
| 2026-10-28 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-10-26T211514262018 -> 2026-10-28T212444946131 | 2 added | quiet |
| 2026-10-28 | `remote/ai.greyridgesignals/tech-risk` | 2026-10-28T133144202006 -> 2026-10-28T212437160595 | 4 added | quiet |
| 2026-10-28 | `remote/com.patchmcp/patch` | 2026-10-28T133128051479 -> 2026-10-28T212431404782 | 4 changed | quiet |
| 2026-10-28 | `remote/io.github.aanari/loacare-healthcare-pricing` | 2026-10-28T133123936949 -> 2026-10-28T212430120263 | 12 changed (every tool) | quiet |
| 2026-10-28 | `remote/studio.gradients/mcp` | 2026-10-28T153216314931 -> 2026-10-28T212428826898 | 1 changed | quiet |
| 2026-10-28 | `remote/com.probativegrowth/legal-marketing-data.2` | 2026-10-28T062153825298 -> 2026-10-28T212427646326 | 6 changed (every tool) | quiet |
| 2026-10-28 | `remote/com.probativegrowth/legal-marketing-data` | 2026-10-28T153218880709 -> 2026-10-28T212427865830 | 24 changed (every tool) | quiet |
| 2026-10-28 | `remote/io.github.junoventures/genesis-social` | 2026-10-26T133530351302 -> 2026-10-28T212426842016 | 26 changed (every tool) | quiet |
| 2026-10-28 | `remote/io.github.SoapyRED/freightutils` | 2026-10-28T133115292998 -> 2026-10-28T212427113050 | 1 changed | quiet |
| 2026-10-28 | `remote/io.github.junoventures/bogeyland-golf` | 2026-10-26T133505767506 -> 2026-10-28T212443902977 | 26 changed (every tool) | quiet |
| 2026-10-28 | `remote/io.taifoon/coordination-layer.1` | 2026-10-28T133504832869 -> 2026-10-28T212422299355 | 1 changed | review |
| 2026-10-28 | `remote/fi.akkilahdot/travel-search` | 2026-10-28T153211883998 -> 2026-10-28T212422693092 | 1 changed | quiet |
| 2026-10-28 | `remote/de.wospeicher/catalog` | 2026-10-28T133052126173 -> 2026-10-28T212423521907 | 3 changed (every tool) | quiet |
| 2026-10-28 | `remote/se.sistaminuten/travel-search` | 2026-10-28T153328709244 -> 2026-10-28T212421415818 | 1 changed | quiet |
| 2026-10-28 | `remote/de.wolaptop/catalog` | 2026-10-28T133049926531 -> 2026-10-28T212422085281 | 3 changed (every tool) | quiet |
| 2026-10-28 | `remote/de.wokonsole/catalog` | 2026-10-28T133049480666 -> 2026-10-28T212421448694 | 3 changed (every tool) | quiet |
| 2026-10-28 | `remote/io.github.rezearcher/tech-risk` | 2026-10-28T133930147505 -> 2026-10-28T212418210827 | 4 added | quiet |
| 2026-10-28 | `remote/uk.co.gigstamp/gigstamp` | 2026-10-27T112345575514 -> 2026-10-28T212416657528 | 3 changed | quiet |
| 2026-10-28 | `remote/io.github.vlad-public-code/valem` | 2026-10-28T133023866326 -> 2026-10-28T212416908578 | 1 added | quiet |
| 2026-10-28 | `remote/io.github.junoventures/graciebarrajiujitsu-site` | 2026-10-26T133854580458 -> 2026-10-28T212416505743 | 26 changed (every tool) | quiet |
| 2026-10-28 | `remote/io.github.junoventures/filipe-coffee` | 2026-10-26T133850862362 -> 2026-10-28T212416576902 | 26 changed (every tool) | quiet |
| 2026-10-28 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-10-28T153324942458 -> 2026-10-28T212418007109 | 1 changed | quiet |
| 2026-10-28 | `remote/io.github.Tomalarrrr/cyclesite-mcp-server` | 2026-10-28T133435282389 -> 2026-10-28T212415861260 | 30 changed | quiet |
| 2026-10-28 | `remote/com.moaibuy/moa` | 2026-10-28T062146683606 -> 2026-10-28T212418490284 | 4 changed | quiet |
| 2026-10-28 | `remote/io.github.tokenzero-ai/tokenzero` | 2026-10-27T210154724126 -> 2026-10-28T212414177768 | 3 changed | quiet |
| 2026-10-28 | `remote/de.wovitamine/catalog` | 2026-10-28T133422466131 -> 2026-10-28T212414275575 | 3 changed (every tool) | quiet |
| 2026-10-28 | `remote/de.wostrom/catalog` | 2026-10-28T133422843255 -> 2026-10-28T212414083913 | 3 changed (every tool) | quiet |
| 2026-10-28 | `remote/de.wohandy/catalog` | 2026-10-28T133418629172 -> 2026-10-28T212414212583 | 3 changed (every tool) | quiet |
| 2026-10-28 | `remote/de.wogrill/catalog` | 2026-10-28T133418150429 -> 2026-10-28T212413642366 | 3 changed (every tool) | quiet |
| 2026-10-28 | `remote/de.woebike/catalog` | 2026-10-28T133418806076 -> 2026-10-28T212413760184 | 3 changed (every tool) | quiet |
| 2026-10-28 | `remote/com.theopenapps/openapps` | 2026-10-27T112121036963 -> 2026-10-28T212414905173 | 1 changed | quiet |
| 2026-10-28 | `remote/de.wotablet/catalog` | 2026-10-28T133814822216 -> 2026-10-28T212412405606 | 3 changed (every tool) | quiet |
| 2026-10-28 | `remote/de.wosolar/catalog` | 2026-10-28T133814862547 -> 2026-10-28T212412159722 | 3 changed (every tool) | quiet |
| 2026-10-28 | `remote/de.woroller/catalog` | 2026-10-28T133814232429 -> 2026-10-28T212412377755 | 3 changed (every tool) | quiet |
| 2026-10-28 | `remote/org.verifiedhandles/verified-handles` | 2026-10-27T112247411295 -> 2026-10-28T212410560427 | 4 changed | quiet |
| 2026-10-28 | `remote/io.github.junoventures/vilamadalena-sampa-br` | 2026-10-26T133806635632 -> 2026-10-28T212409814863 | 28 changed (every tool) | quiet |
| 2026-10-28 | `remote/io.github.junoventures/vilabuarque-sampa-br` | 2026-10-26T133806174647 -> 2026-10-28T212409587823 | 28 changed (every tool) | quiet |
| 2026-10-28 | `remote/io.github.ak10082247-max/stealthguard-402` | 2026-10-28T132930720137 -> 2026-10-28T212406285787 | 1 changed | quiet |
| 2026-10-28 | `remote/io.github.SKalinin909/tradingcalc` | 2026-10-28T133324336911 -> 2026-10-28T212406708591 | 10 changed | quiet |
| 2026-10-28 | `remote/com.stayotter/stay-otter` | 2026-10-28T132930408237 -> 2026-10-28T212406989463 | 1 changed | quiet |
| 2026-10-28 | `remote/io.github.ucunhome/ucun-select` | 2026-10-26T133547110091 -> 2026-10-28T212406973242 | 1 added | quiet |
| 2026-10-28 | `remote/io.github.ygfalcon/solana-wallet-intel` | 2026-10-28T153154372833 -> 2026-10-28T212404582351 | 2 changed, 3 added | review |
| 2026-10-28 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-28T153154544589 -> 2026-10-28T212404921731 | 1 changed | quiet |
| 2026-10-28 | `remote/com.etfiq/etfiq` | 2026-10-28T132655991457 -> 2026-10-28T212358880602 | 10 changed, 7 added | quiet |
| 2026-10-28 | `remote/build.swapi/star-wars` | 2026-10-28T062217294999 -> 2026-10-28T212359448514 | 1 changed | quiet |
| 2026-10-28 | `remote/social.spoofy/mcp` | 2026-10-28T062207736646 -> 2026-10-28T212357424260 | 2 changed | quiet |
| 2026-10-28 | `remote/io.dropyour/dropyour` | 2026-10-28T132655124395 -> 2026-10-28T212359640777 | 4 changed | quiet |
| 2026-10-28 | `remote/com.remoshift/jobs` | 2026-10-28T153146657804 -> 2026-10-28T212358378489 | 1 changed | quiet |
| 2026-10-28 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-28T153318943416 -> 2026-10-28T212356429412 | 4 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 38574 substantive, 19506 that changed only numbers (a catalogue counter ticking, a date), 701 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 32228 | 13994 | 18234 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1009 | 1009 | 0 | 0 |
| `caseyjhand.com` | 245 | 245 | 0 | 0 |
| `sistaminuten.se` | 166 | 5 | 0 | 161 |
| `afbudsrejser.dk` | 165 | 5 | 0 | 160 |
| `akkilahdot.fi` | 165 | 5 | 0 | 160 |
| `restplass.no` | 165 | 5 | 0 | 160 |
| `socialloop.ai` | 159 | 159 | 0 | 0 |
| `remoshift.com` | 135 | 8 | 127 | 0 |
| `revmesh2074.workers.dev` | 129 | 116 | 13 | 0 |
| `fundinglandscape.com` | 128 | 81 | 47 | 0 |
| 6330 other operators | 21746 | 20601 | 1085 | 60 |
