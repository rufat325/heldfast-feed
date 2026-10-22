# MCP server tool changes

Last change observed 2026-10-22T12:21:22+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

42488 changes to a tool definition: 1838 npm releases (1592 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 40650 readings of hosted servers that found their tools changed; 2373 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-22 | `remote/studio.gradients/mcp` | 2026-10-22T110011337909 -> 2026-10-22T122123121285 | 1 changed | quiet |
| 2026-10-22 | `remote/fi.akkilahdot/travel-search` | 2026-10-22T105951256422 -> 2026-10-22T122102518715 | 1 changed | quiet |
| 2026-10-22 | `remote/no.restplass/travel-search` | 2026-10-22T110310338916 -> 2026-10-22T122026031968 | 1 changed | quiet |
| 2026-10-22 | `remote/ai.usedby/usedby` | 2026-10-22T110046247145 -> 2026-10-22T122021870373 | 2 changed | quiet |
| 2026-10-22 | `remote/io.taifoon/coordination-layer.1` | 2026-10-22T052604185282 -> 2026-10-22T122015932300 | 1 changed | review |
| 2026-10-22 | `remote/se.sistaminuten/travel-search` | 2026-10-22T110015935699 -> 2026-10-22T122012481540 | 1 changed | quiet |
| 2026-10-22 | `remote/com.ticketsea/ticketsea` | 2026-10-17T055837671557 -> 2026-10-22T122008230040 | 1 added | quiet |
| 2026-10-22 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-22T052641606405 -> 2026-10-22T122003810682 | 1 changed | quiet |
| 2026-10-22 | `remote/com.swarmmemo/bulletin` | 2026-10-22T052640876898 -> 2026-10-22T121952256107 | 1 changed | quiet |
| 2026-10-22 | `remote/com.cadprops/cadprops` | 2026-10-22T105934664426 -> 2026-10-22T121951545820 | 1 changed | quiet |
| 2026-10-22 | `remote/dk.afbudsrejser/travel-search` | 2026-10-22T110231136266 -> 2026-10-22T121945291477 | 1 changed | quiet |
| 2026-10-22 | `remote/com.actualgroup/jobs` | 2026-10-19T135821507814 -> 2026-10-22T121946857823 | 2 changed, 1 added | quiet |
| 2026-10-22 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-22T105826638409 -> 2026-10-22T121931995301 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.tintun2602/veldora` | 2026-10-19T135404701471 -> 2026-10-22T121919249932 | 4 added | quiet |
| 2026-10-22 | `remote/io.github.jennipro-engineering/ghost-market-web` | 2026-10-22T105728502485 -> 2026-10-22T121902147188 | 4 changed | quiet |
| 2026-10-22 | `remote/io.github.send21io/mcp` | 2026-10-20T104153003831 -> 2026-10-22T121848849023 | 14 changed (every tool) | quiet |
| 2026-10-22 | `remote/com.remoshift/jobs` | 2026-10-22T105738568724 -> 2026-10-22T121834346596 | 1 changed | quiet |
| 2026-10-22 | `remote/com.tiamatcrypto.sweetai/agent-intel` | 2026-10-19T211954429664 -> 2026-10-22T121830900007 | 34 changed (every tool) | quiet |
| 2026-10-22 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-22T110047811084 -> 2026-10-22T121815546752 | 10 changed | quiet |
| 2026-10-22 | `remote/cc.placetobe/events` | 2026-10-06T105952507276 -> 2026-10-22T121750796075 | 1 changed | quiet |
| 2026-10-22 | `remote/app.railway.up.payments-intel-production/payments-intel` | 2026-10-17T055648340665 -> 2026-10-22T121746513273 | 2 added | quiet |
| 2026-10-22 | `remote/io.github.Payotte-com/payotte-mcp` | 2026-10-19T155900989147 -> 2026-10-22T121740796936 | 1 added | quiet |
| 2026-10-22 | `remote/site.chatgpt.orellise.relay-agent-services/relay` | 2026-10-21T202530893555 -> 2026-10-22T121722178627 | 2 changed | quiet |
| 2026-10-22 | `remote/io.github.Hovsteder/powersun-tron-mcp` | 2026-09-24T202446182072 -> 2026-10-22T121702629832 | 2 changed | quiet |
| 2026-10-22 | `remote/com.googleapis.memorystore/mcp` | 2026-10-22T105606635424 -> 2026-10-22T121653729352 | 4 changed | quiet |
| 2026-10-22 | `remote/tech.ydb-qdrant.pets/codex-pets-ydb-qdrant` | 2026-10-18T185948279985 -> 2026-10-22T121652866755 | 1 changed | quiet |
| 2026-10-22 | `remote/ai.switchapp/switch` | 2026-10-22T105538383406 -> 2026-10-22T121625356544 | 6 changed, 2 added | quiet |
| 2026-10-22 | `remote/me.miow/miow` | 2026-10-22T105520379260 -> 2026-10-22T121604256820 | 4 changed | quiet |
| 2026-10-22 | `remote/travel.ourway/camino-de-santiago` | 2026-10-19T134958173779 -> 2026-10-22T121553921845 | 2 changed | quiet |
| 2026-10-22 | `remote/com.movingplace/mcp` | 2026-10-22T105402556934 -> 2026-10-22T121459827792 | 16 removed | quiet |
| 2026-10-22 | `remote/ai.letsship/ship` | 2026-10-20T201045793935 -> 2026-10-22T121416605900 | 3 changed | quiet |
| 2026-10-22 | `remote/com.jojapi/sms-verify` | 2026-10-22T105337995183 -> 2026-10-22T121409684548 | 1 changed | quiet |
| 2026-10-22 | `remote/io.dropyour/dropyour` | 2026-10-20T135347856053 -> 2026-10-22T121407837252 | 1 changed | quiet |
| 2026-10-22 | `remote/com.thaifishsashimicatalog/fish-market` | 2026-10-22T105329306949 -> 2026-10-22T121359550637 | 1 changed | quiet |
| 2026-10-22 | `remote/co.cookie-compliance/cookie-consent` | 2026-10-19T135152630457 -> 2026-10-22T121357632945 | 1 changed | quiet |
| 2026-10-22 | `remote/co.chinaready/search` | 2026-10-19T135147869209 -> 2026-10-22T121353968918 | 1 added | quiet |
| 2026-10-22 | `remote/com.frontdeskreview/front-desk-review-data` | 2026-10-22T105317594214 -> 2026-10-22T121349667186 | 3 changed | quiet |
| 2026-10-22 | `remote/io.github.obrientt/landfiller` | 2026-10-06T105804229771 -> 2026-10-22T121327774985 | 1 changed | review |
| 2026-10-22 | `remote/com.kitchengradeapp/kitchengrade` | 2026-10-19T134718284999 -> 2026-10-22T121320925242 | 1 changed | quiet |
| 2026-10-22 | `remote/com.gluecron/gluecron` | 2026-10-21T121326662579 -> 2026-10-22T121150992572 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.zachhhhh/rankroot` | 2026-10-20T103541898705 -> 2026-10-22T121149734798 | 6 added | quiet |
| 2026-10-22 | `remote/io.github.pipeworx-io/folketinget-dk` | 2026-10-22T105002603456 -> 2026-10-22T121148266397 | 1 changed | quiet |
| 2026-10-22 | `remote/com.germandex/guides` | 2026-10-17T055641798059 -> 2026-10-22T121146755840 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.pipeworx-io/grants-gov` | 2026-10-22T105200499473 -> 2026-10-22T121114917721 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.pipeworx-io/country-news` | 2026-10-22T104839925424 -> 2026-10-22T121108747756 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.pipeworx-io/archive` | 2026-10-22T104819968758 -> 2026-10-22T121104344897 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt` | 2026-10-22T052559396399 -> 2026-10-22T121050458096 | 1 changed, 1 added | quiet |
| 2026-10-22 | `remote/xyz.filingdelta/filingdelta` | 2026-10-22T052533344533 -> 2026-10-22T121034722764 | 2 changed | quiet |
| 2026-10-22 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-22T104737754436 -> 2026-10-22T121009293954 | 2 changed | quiet |
| 2026-10-22 | `remote/io.github.easywebshop/mcp` | 2026-09-23T162434598371 -> 2026-10-22T121005943668 | 1 changed | quiet |
| 2026-10-22 | `remote/com.cooperemail/cooper-email` | 2026-10-20T201001335649 -> 2026-10-22T120929404834 | 4 added | quiet |
| 2026-10-22 | `remote/io.taifoon/coordination-layer` | 2026-10-22T052543883808 -> 2026-10-22T120931356198 | 1 changed | review |
| 2026-10-22 | `remote/build.naru/contract-compass` | 2026-10-22T104905738015 -> 2026-10-22T120928253659 | 1 changed | quiet |
| 2026-10-22 | `remote/app.sallim/contract-compass` | 2026-10-22T104634078793 -> 2026-10-22T120857950873 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.smithdavedesign/botchelor` | 2026-10-22T104615610757 -> 2026-10-22T120855237020 | 3 changed | quiet |
| 2026-10-22 | `remote/io.github.randommonicle/commonhold` | 2026-10-17T054216665518 -> 2026-10-22T120850430627 | 1 changed | quiet |
| 2026-10-22 | `remote/com.difficat/difficat` | 2026-10-21T120912118716 -> 2026-10-22T120741086767 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.zifengw/eu-business-data-mcp` | 2026-10-21T052146311333 -> 2026-10-22T120733006506 | 3 changed | quiet |
| 2026-10-22 | `remote/io.github.magiccadai/magicon` | 2026-10-18T185847651407 -> 2026-10-22T120729500566 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.wnsod/oneqaz-trading-mcp` | 2026-10-19T155409686053 -> 2026-10-22T120728551411 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 27613 substantive, 14312 that changed only numbers (a catalogue counter ticking, a date), 563 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 22156 | 8734 | 13422 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 654 | 654 | 0 | 0 |
| `caseyjhand.com` | 174 | 174 | 0 | 0 |
| `sistaminuten.se` | 134 | 4 | 0 | 130 |
| `afbudsrejser.dk` | 133 | 4 | 0 | 129 |
| `akkilahdot.fi` | 133 | 4 | 0 | 129 |
| `restplass.no` | 133 | 4 | 0 | 129 |
| `socialloop.ai` | 129 | 129 | 0 | 0 |
| `remoshift.com` | 104 | 7 | 97 | 0 |
| `fundinglandscape.com` | 102 | 67 | 35 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| 5127 other operators | 16198 | 15394 | 758 | 46 |
