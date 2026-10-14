# MCP server tool changes

Last change observed 2026-10-13T23:57:09+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10495 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 23695 hosted endpoints (read daily, and every four hours while they keep changing).

26401 changes to a tool definition: 870 npm releases (624 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 25531 readings of hosted servers that found their tools changed; 402 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-13 | `remote/se.sistaminuten/travel-search` | 2026-10-13T193419586439 -> 2026-10-13T235710546667 | 1 changed | quiet |
| 2026-10-13 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-13T193416121748 -> 2026-10-13T235707605136 | 3 changed | quiet |
| 2026-10-13 | `remote/no.restplass/travel-search` | 2026-10-13T193423687964 -> 2026-10-13T235705677012 | 1 changed | quiet |
| 2026-10-13 | `remote/io.github.0xinsider/mcp` | 2026-10-13T021607490861 -> 2026-10-13T235705451741 | 1 changed | quiet |
| 2026-10-13 | `remote/dk.afbudsrejser/travel-search` | 2026-10-13T193423241637 -> 2026-10-13T235705542025 | 1 changed | quiet |
| 2026-10-13 | `remote/com.uplika/uplika` | 2026-10-13T121259692420 -> 2026-10-13T235706879433 | 12 changed | quiet |
| 2026-10-13 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-13T121303126159 -> 2026-10-13T235704476951 | 13 changed | quiet |
| 2026-10-13 | `remote/io.github.tang-vu/keryx` | 2026-10-13T121301102999 -> 2026-10-13T235705845065 | 3 changed, 2 added | quiet |
| 2026-10-13 | `remote/eu.paymentslaw/legislation` | 2026-10-12T181452920178 -> 2026-10-13T235704129417 | 1 added | quiet |
| 2026-10-13 | `remote/com.sourcey/sourcey` | 2026-10-13T121300823293 -> 2026-10-13T235703523713 | 1 changed | quiet |
| 2026-10-13 | `remote/ch.kulalabs.pazair/pazair` | 2026-10-13T121301736379 -> 2026-10-13T235704025289 | 1 changed, 2 removed | quiet |
| 2026-10-13 | `remote/com.idevice/wearables` | 2026-10-13T193419234544 -> 2026-10-13T235702471811 | 1 changed | quiet |
| 2026-10-13 | `remote/org.aspern/aspern` | 2026-10-13T193418743210 -> 2026-10-13T235701921533 | 6 changed | quiet |
| 2026-10-13 | `remote/com.youspot/youspot` | 2026-10-13T193425055695 -> 2026-10-13T235700267240 | 3 changed, 2 added | quiet |
| 2026-10-13 | `remote/fi.akkilahdot/travel-search` | 2026-10-13T193428332457 -> 2026-10-13T235659980559 | 1 changed | quiet |
| 2026-10-13 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-10-13T193427752869 -> 2026-10-13T235700279015 | 2 changed | quiet |
| 2026-10-13 | `remote/ru.vedarai/mcp` | 2026-10-13T121314350236 -> 2026-10-13T235700776648 | 1 changed | quiet |
| 2026-10-13 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-13T193426266033 -> 2026-10-13T235657940991 | 1 changed, 5 added | quiet |
| 2026-10-13 | `remote/com.swarmmemo/bulletin` | 2026-10-13T193427853406 -> 2026-10-13T235658595093 | 12 changed, 2 added | quiet |
| 2026-10-13 | `remote/online.pageaudit/pageaudit` | 2026-10-13T193426357170 -> 2026-10-13T235657491834 | 1 changed, 1 added | quiet |
| 2026-10-13 | `remote/com.remoshift/jobs` | 2026-10-13T193426234301 -> 2026-10-13T235656818419 | 1 changed | quiet |
| 2026-10-13 | `remote/com.howtomakemoneyonsnapchat/creator-monetization` | 2026-10-11T150640970664 -> 2026-10-13T235657869741 | 2 changed | quiet |
| 2026-10-13 | `remote/io.github.withgrokbot/verified-catalog` | 2026-10-11T063101211562 -> 2026-10-13T235655006875 | 2 changed | quiet |
| 2026-10-13 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-10-13T193416968125 -> 2026-10-13T235657033404 | 1 changed | quiet |
| 2026-10-13 | `remote/ch.kulalabs.agents/jobflow` | 2026-10-13T121257031660 -> 2026-10-13T235656954586 | 1 changed, 2 removed | quiet |
| 2026-10-13 | `remote/ai.switchapp/switch` | 2026-10-13T193424200409 -> 2026-10-13T235655493118 | 1 changed | quiet |
| 2026-10-13 | `remote/io.github.si-imtiaz/leadquasar` | 2026-10-13T193423974698 -> 2026-10-13T235654998503 | 2 changed | quiet |
| 2026-10-13 | `remote/co.getclippy/clippy` | 2026-10-12T063533397662 -> 2026-10-13T235654677736 | 1 changed | quiet |
| 2026-10-13 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-10-11T203727087466 -> 2026-10-13T193427752869 | 2 changed | quiet |
| 2026-10-13 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-13T121313185137 -> 2026-10-13T193428533447 | 1 changed | quiet |
| 2026-10-13 | `remote/fi.akkilahdot/travel-search` | 2026-10-13T121313352219 -> 2026-10-13T193428332457 | 1 changed | quiet |
| 2026-10-13 | `remote/com.tickerinside/tickerinside-mcp` | 2026-10-13T021641589815 -> 2026-10-13T193427129657 | 1 changed | quiet |
| 2026-10-13 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-13T121312458640 -> 2026-10-13T193426266033 | 1 changed | quiet |
| 2026-10-13 | `remote/com.swarmmemo/bulletin` | 2026-10-13T021641441693 -> 2026-10-13T193427853406 | 3 changed | quiet |
| 2026-10-13 | `remote/ai.shorti/shorti` | 2026-10-12T181502763656 -> 2026-10-13T193426599510 | 1 changed | quiet |
| 2026-10-13 | `remote/online.pageaudit/pageaudit` | 2026-10-12T181456014729 -> 2026-10-13T193426357170 | 1 changed, 9 added | quiet |
| 2026-10-13 | `remote/com.remoshift/jobs` | 2026-10-13T121311764629 -> 2026-10-13T193426234301 | 1 changed | quiet |
| 2026-10-13 | `remote/ai.switchapp/switch` | 2026-10-13T121309764799 -> 2026-10-13T193424200409 | 3 changed | quiet |
| 2026-10-13 | `remote/no.restplass/travel-search` | 2026-10-13T121304367288 -> 2026-10-13T193423687964 | 1 changed | quiet |
| 2026-10-13 | `remote/io.github.jackskip22/rapier` | 2026-10-12T000126559485 -> 2026-10-13T193424144653 | 32 added, 6 removed | quiet |
| 2026-10-13 | `remote/dk.afbudsrejser/travel-search` | 2026-10-13T121304776042 -> 2026-10-13T193423241637 | 1 changed | quiet |
| 2026-10-13 | `remote/com.youspot/youspot` | 2026-10-13T121301222141 -> 2026-10-13T193425055695 | 2 changed, 2 added | quiet |
| 2026-10-13 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-13T121300799644 -> 2026-10-13T193422749773 | 2 changed | review |
| 2026-10-13 | `remote/io.github.si-imtiaz/leadquasar` | 2026-10-13T121309042339 -> 2026-10-13T193423974698 | 1 changed | quiet |
| 2026-10-13 | `remote/io.github.Embassy-of-the-Free-Mind/sourcelibrary` | 2026-10-13T121301146243 -> 2026-10-13T193424549662 | 4 changed | quiet |
| 2026-10-13 | `remote/ua.com.quintadb/mcp` | 2026-10-13T021618332173 -> 2026-10-13T193424431910 | 6 changed | quiet |
| 2026-10-13 | `remote/io.github.richardsolomou/praetorium` | 2026-10-13T021615539979 -> 2026-10-13T193423009106 | 1 changed | quiet |
| 2026-10-13 | `remote/com.quintadb/mcp` | 2026-10-13T021620514396 -> 2026-10-13T193422621347 | 6 changed | quiet |
| 2026-10-13 | `remote/app.evlek/mcp-server` | 2026-10-12T181432317065 -> 2026-10-13T193422351657 | 5 changed | quiet |
| 2026-10-13 | `remote/uk.co.buildbatch/buildbatch` | 2026-10-12T063531179202 -> 2026-10-13T193420791868 | 1 changed | quiet |
| 2026-10-13 | `remote/com.relvato/relvato` | 2026-10-11T063101532214 -> 2026-10-13T193422701572 | 2 changed | quiet |
| 2026-10-13 | `remote/com.prereason/mcp` | 2026-10-12T181429551731 -> 2026-10-13T193420543691 | 1 changed | quiet |
| 2026-10-13 | `remote/com.askmatchbox/matchbox` | 2026-10-13T021605750029 -> 2026-10-13T193421698463 | 2 changed | quiet |
| 2026-10-13 | `remote/se.sistaminuten/travel-search` | 2026-10-13T121301616662 -> 2026-10-13T193419586439 | 1 changed | quiet |
| 2026-10-13 | `remote/com.jojapi/product-barcode-api` | 2026-10-13T121258541315 -> 2026-10-13T193421734334 | 1 changed | quiet |
| 2026-10-13 | `remote/com.idevice/wearables` | 2026-10-13T021613547536 -> 2026-10-13T193419234544 | 3 changed | quiet |
| 2026-10-13 | `remote/ru.quintadb/mcp` | 2026-10-13T021613707001 -> 2026-10-13T193420658869 | 6 changed | quiet |
| 2026-10-13 | `remote/org.aspern/aspern` | 2026-10-13T121303236985 -> 2026-10-13T193418743210 | 1 changed | quiet |
| 2026-10-13 | `remote/wedding.aisle/aisle` | 2026-10-13T121257171103 -> 2026-10-13T193417747619 | 1 changed | quiet |
| 2026-10-13 | `remote/io.github.tryflask/flask` | 2026-10-13T021616631221 -> 2026-10-13T193417436817 | 4 changed, 1 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 17909 substantive, 8068 that changed only numbers (a catalogue counter ticking, a date), 424 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 13231 | 5706 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 538 | 538 | 0 | 0 |
| `sistaminuten.se` | 102 | 3 | 0 | 99 |
| `afbudsrejser.dk` | 101 | 3 | 0 | 98 |
| `akkilahdot.fi` | 101 | 3 | 0 | 98 |
| `restplass.no` | 101 | 3 | 0 | 98 |
| `socialloop.ai` | 99 | 99 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `caseyjhand.com` | 77 | 77 | 0 | 0 |
| `remoshift.com` | 74 | 4 | 70 | 0 |
| `fundinglandscape.com` | 73 | 43 | 30 | 0 |
| 3056 other operators | 9466 | 8992 | 443 | 31 |
