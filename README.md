# MCP server tool changes

Last change observed 2026-10-11T06:31:13+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10128 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 21701 hosted endpoints (read daily, and every four hours while they keep changing).

25970 changes to a tool definition: 870 npm releases (624 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 25100 readings of hosted servers that found their tools changed; 389 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-11 | `remote/io.github.kor-jongwon/witan` | 2026-10-10T144740384612 -> 2026-10-11T063115715803 | 31 changed | quiet |
| 2026-10-11 | `remote/fi.akkilahdot/travel-search` | 2026-10-10T235310732663 -> 2026-10-11T063115105057 | 1 changed | quiet |
| 2026-10-11 | `remote/com.voyscout/price-history` | 2026-10-10T144738428157 -> 2026-10-11T063114170686 | 5 changed (every tool) | quiet |
| 2026-10-11 | `remote/ru.vedarai/mcp` | 2026-10-10T144739333785 -> 2026-10-11T063115516628 | 1 changed | quiet |
| 2026-10-11 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-10T144736777173 -> 2026-10-11T063114226823 | 1 changed | quiet |
| 2026-10-11 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-10T235304536934 -> 2026-10-11T063112621236 | 1 changed | quiet |
| 2026-10-11 | `remote/ai.shorti/shorti` | 2026-10-10T144735383862 -> 2026-10-11T063112839075 | 1 changed | quiet |
| 2026-10-11 | `remote/com.remoshift/jobs` | 2026-10-10T235302618106 -> 2026-10-11T063111992865 | 1 changed | quiet |
| 2026-10-11 | `remote/no.restplass/travel-search` | 2026-10-10T235305161091 -> 2026-10-11T063109199696 | 1 changed | quiet |
| 2026-10-11 | `remote/com.sonarconnections/sonar-connections` | 2026-10-10T202050762104 -> 2026-10-11T063108794852 | 21 changed | quiet |
| 2026-10-11 | `remote/com.multicinesortega/cartelera` | 2026-10-10T202053085698 -> 2026-10-11T063111109062 | 1 changed | quiet |
| 2026-10-11 | `remote/com.mooncatcherwire/wire` | 2026-10-10T235259382756 -> 2026-10-11T063109323530 | 1 changed | quiet |
| 2026-10-11 | `remote/dk.afbudsrejser/travel-search` | 2026-10-10T235303895098 -> 2026-10-11T063108613031 | 1 changed | quiet |
| 2026-10-11 | `remote/ai.switchapp/switch` | 2026-10-10T202049141575 -> 2026-10-11T063108744886 | 7 added | quiet |
| 2026-10-11 | `remote/io.github.Timothymycompc/solana-pulse-gateway` | 2026-10-09T064811199857 -> 2026-10-11T063106540774 | 20 changed (every tool) | review |
| 2026-10-11 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-10T202121618986 -> 2026-10-11T063106749303 | 13 changed | quiet |
| 2026-10-11 | `remote/com.jojapi/swift-ai` | 2026-10-10T062519759631 -> 2026-10-11T063108110607 | 1 changed | quiet |
| 2026-10-11 | `remote/com.falazuki/finance-br` | 2026-10-10T235255498285 -> 2026-10-11T063106331848 | 2 changed, 3 added | review |
| 2026-10-11 | `remote/io.github.richardsolomou/praetorium` | 2026-10-10T235259125187 -> 2026-10-11T063105998455 | 1 changed | quiet |
| 2026-10-11 | `remote/io.github.Fizzl13/presign-guard` | 2026-10-10T235258946548 -> 2026-10-11T063105144358 | 3 changed | quiet |
| 2026-10-11 | `remote/trade.loomdesk/loomdesk` | 2026-10-09T153555325544 -> 2026-10-11T063105292614 | 1 changed | quiet |
| 2026-10-11 | `remote/net.hotelrefund/price-tracker` | 2026-10-10T062513553188 -> 2026-10-11T063102812368 | 1 changed | quiet |
| 2026-10-11 | `remote/so.darwin/darwin` | 2026-10-10T235253827697 -> 2026-10-11T063102977655 | 2 changed | quiet |
| 2026-10-11 | `remote/io.github.snefhew/factline` | 2026-10-10T235250094915 -> 2026-10-11T063103951734 | 1 changed, 7 added | review |
| 2026-10-11 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt` | 2026-10-10T235248698726 -> 2026-10-11T063102192204 | 1 changed | quiet |
| 2026-10-11 | `remote/io.github.34r7h/handoff` | 2026-10-09T153550387628 -> 2026-10-11T063103265400 | 1 changed, 5 added | quiet |
| 2026-10-11 | `remote/io.github.withgrokbot/verified-catalog` | 2026-10-10T235311492474 -> 2026-10-11T063101211562 | 2 changed | quiet |
| 2026-10-11 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-10T062523058658 -> 2026-10-11T063103350957 | 1 changed | quiet |
| 2026-10-11 | `remote/io.github.Book0fEli/paycheck` | 2026-10-09T064755347241 -> 2026-10-11T063102842922 | 1 changed | quiet |
| 2026-10-11 | `remote/de.immobilieneichmann/listings` | 2026-10-10T144718081995 -> 2026-10-11T063101447915 | 1 changed | quiet |
| 2026-10-11 | `remote/com.sfxmint/sounds` | 2026-10-09T153602098888 -> 2026-10-11T063100229994 | 5 changed, 4 added | quiet |
| 2026-10-11 | `remote/com.restaurantdoctorai/profit-check` | 2026-10-10T062521342109 -> 2026-10-11T063059887509 | 2 added | quiet |
| 2026-10-11 | `remote/com.relvato/relvato` | 2026-10-09T064718511687 -> 2026-10-11T063101532214 | 3 changed | quiet |
| 2026-10-11 | `remote/com.idevice/wearables` | 2026-10-10T144717620000 -> 2026-10-11T063100224343 | 4 changed | quiet |
| 2026-10-11 | `remote/io.github.whiteknightonhorse/apibase` | 2026-10-10T235244970063 -> 2026-10-11T063100186822 | 5 removed | quiet |
| 2026-10-11 | `remote/io.github.sean0007/free-agent-tools` | 2026-10-09T064751754505 -> 2026-10-11T063058802574 | 1 added | quiet |
| 2026-10-11 | `remote/io.github.bosmdavid-gif/dropthehassle` | 2026-10-10T235247996470 -> 2026-10-11T063058715174 | 5 added | quiet |
| 2026-10-11 | `remote/com.squirrelscan/squirrelscan` | 2026-10-10T062518568730 -> 2026-10-11T063100833429 | 7 changed | quiet |
| 2026-10-11 | `remote/io.github.kiddhu/seekapi` | 2026-10-10T235245128966 -> 2026-10-11T063056897120 | 2 changed | quiet |
| 2026-10-11 | `remote/eu.sirenic/sirenic` | 2026-10-10T235244660858 -> 2026-10-11T063058741674 | 4 changed | quiet |
| 2026-10-11 | `remote/com.nicheangle/niche` | 2026-10-10T144706438869 -> 2026-10-11T063055908263 | 1 changed | quiet |
| 2026-10-11 | `remote/co.ainumbers/tools` | 2026-10-10T144705676642 -> 2026-10-11T063057218187 | 2 changed | quiet |
| 2026-10-11 | `remote/se.sistaminuten/travel-search` | 2026-10-10T235305649758 -> 2026-10-11T063055158472 | 1 changed | quiet |
| 2026-10-11 | `remote/com.ashareapi/ashare-data-api` | 2026-10-10T202030804915 -> 2026-10-11T063055702365 | 1 changed | quiet |
| 2026-10-11 | `remote/wedding.aisle/aisle` | 2026-10-10T235242176417 -> 2026-10-11T063055336880 | 10 changed | quiet |
| 2026-10-11 | `remote/com.thefomite/fomite` | 2026-10-10T062527630266 -> 2026-10-11T063053960025 | 1 changed | quiet |
| 2026-10-11 | `remote/com.cooperemail/cooper-email` | 2026-10-10T202032435459 -> 2026-10-11T063054270263 | 1 added | quiet |
| 2026-10-11 | `remote/directory.nohumans/registry` | 2026-10-10T235248459245 -> 2026-10-11T063053321890 | 1 changed | quiet |
| 2026-10-11 | `remote/info.3dcms/mcp` | 2026-10-10T062504367181 -> 2026-10-11T063052192755 | 1 changed | quiet |
| 2026-10-11 | `remote/ai.skuit/catalog` | 2026-10-10T202047774085 -> 2026-10-11T063051709378 | 1 changed | quiet |
| 2026-10-11 | `remote/pro.particle/particle-pro` | 2026-10-10T062519235818 -> 2026-10-11T063050514599 | 9 changed, 3 added | quiet |
| 2026-10-11 | `remote/net.isitdns/isitdns` | 2026-10-09T064726230082 -> 2026-10-11T063048844631 | 3 changed | quiet |
| 2026-10-11 | `remote/app.flaim/mcp` | 2026-10-10T062507766068 -> 2026-10-11T063045699405 | 8 changed | quiet |
| 2026-10-10 | `remote/io.github.withgrokbot/verified-catalog` | 2026-10-10T202046648605 -> 2026-10-10T235311492474 | 1 changed | quiet |
| 2026-10-10 | `remote/io.github.CodeWever/wever-labs-products` | 2026-10-10T062535742921 -> 2026-10-10T235310624823 | 2 changed | quiet |
| 2026-10-10 | `remote/fi.akkilahdot/travel-search` | 2026-10-10T202102791955 -> 2026-10-10T235310732663 | 1 changed | quiet |
| 2026-10-10 | `remote/se.sistaminuten/travel-search` | 2026-10-10T202059172403 -> 2026-10-10T235305649758 | 1 changed | quiet |
| 2026-10-10 | `remote/com.swarmmemo/bulletin` | 2026-10-10T202058179256 -> 2026-10-10T235306204207 | 4 changed, 12 added | quiet |
| 2026-10-10 | `remote/no.restplass/travel-search` | 2026-10-10T202126540815 -> 2026-10-10T235305161091 | 1 changed | quiet |
| 2026-10-10 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-10T202055918323 -> 2026-10-10T235304536934 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 17566 substantive, 8018 that changed only numbers (a catalogue counter ticking, a date), 386 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 13231 | 5706 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 538 | 538 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `sistaminuten.se` | 93 | 2 | 0 | 91 |
| `afbudsrejser.dk` | 92 | 2 | 0 | 90 |
| `akkilahdot.fi` | 92 | 2 | 0 | 90 |
| `restplass.no` | 92 | 2 | 0 | 90 |
| `socialloop.ai` | 90 | 90 | 0 | 0 |
| `caseyjhand.com` | 77 | 77 | 0 | 0 |
| `dayze.com` | 69 | 69 | 0 | 0 |
| `fundinglandscape.com` | 65 | 36 | 29 | 0 |
| 3054 other operators | 9093 | 8604 | 464 | 25 |
