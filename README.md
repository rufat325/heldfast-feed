# MCP server tool changes

Last change observed 2026-11-14T01:07:05+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

98258 changes to a tool definition: 4084 npm releases (3838 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 94174 readings of hosted servers that found their tools changed; 4042 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-14 | `remote/com.mintlify/searchmcp` | 2026-11-13T013231699066 -> 2026-11-14T010706544369 | 1 changed | quiet |
| 2026-11-14 | `remote/studio.gradients/mcp` | 2026-11-13T200751660173 -> 2026-11-14T010705836104 | 1 changed | quiet |
| 2026-11-14 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-13T013228927879 -> 2026-11-14T010704283051 | 1 changed | quiet |
| 2026-11-14 | `remote/io.github.EasyGerber/easygerber` | 2026-11-12T074800412045 -> 2026-11-14T010704857783 | 4 changed, 1 added | quiet |
| 2026-11-14 | `remote/fi.akkilahdot/travel-search` | 2026-11-13T200750140906 -> 2026-11-14T010704412708 | 1 changed | quiet |
| 2026-11-14 | `remote/io.github.liad142/yedapo` | 2026-11-13T013144447790 -> 2026-11-14T010704760199 | 2 changed (every tool) | quiet |
| 2026-11-14 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-13T200751091408 -> 2026-11-14T010706018221 | 8 added | quiet |
| 2026-11-14 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-13T200746895185 -> 2026-11-14T010704249215 | 3 changed | quiet |
| 2026-11-14 | `remote/no.restplass/travel-search` | 2026-11-13T200812791927 -> 2026-11-14T010701489593 | 1 changed | quiet |
| 2026-11-14 | `remote/com.starcovery/mcp` | 2026-11-13T200813041362 -> 2026-11-14T010701796171 | 2 changed, 5 added | quiet |
| 2026-11-14 | `remote/com.kulicadvisory/aictionbot-werkbank` | 2026-11-13T200811790097 -> 2026-11-14T010700456300 | 2 added | quiet |
| 2026-11-14 | `remote/dk.afbudsrejser/travel-search` | 2026-11-13T200809625254 -> 2026-11-14T010659729449 | 1 changed | quiet |
| 2026-11-14 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-13T200741718649 -> 2026-11-14T010659185965 | 1 changed | quiet |
| 2026-11-14 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-13T200742380048 -> 2026-11-14T010659362852 | 2 changed | quiet |
| 2026-11-14 | `remote/com.tamingdns/mcp` | 2026-11-13T150050045761 -> 2026-11-14T010657830546 | 1 changed | quiet |
| 2026-11-14 | `remote/se.sistaminuten/travel-search` | 2026-11-13T200806735705 -> 2026-11-14T010657398664 | 1 changed | quiet |
| 2026-11-14 | `remote/dev.vantagemcp/vantage` | 2026-11-12T154923134825 -> 2026-11-14T010657559174 | 1 changed, 1 added | quiet |
| 2026-11-14 | `remote/com.onlyworlds/mcp` | 2026-11-13T120005520035 -> 2026-11-14T010657631032 | 8 changed | quiet |
| 2026-11-14 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-13T200736070041 -> 2026-11-14T010654954998 | 1 changed | quiet |
| 2026-11-14 | `remote/io.github.QDThead/signal-lab` | 2026-11-13T200734654999 -> 2026-11-14T010654827746 | 2 changed | quiet |
| 2026-11-14 | `remote/com.seqbench/workbench` | 2026-11-13T200732520195 -> 2026-11-14T010653678166 | 1 changed | quiet |
| 2026-11-14 | `remote/com.tickerz/tickerz` | 2026-11-13T115806374446 -> 2026-11-14T010653702318 | 1 changed | quiet |
| 2026-11-14 | `remote/io.github.christianscode1994/volatiai-mcp` | 2026-11-13T200756302220 -> 2026-11-14T010650630414 | 3 added | quiet |
| 2026-11-14 | `remote/io.github.utilify-io/utilify-mcp` | 2026-11-13T115850735092 -> 2026-11-14T010649680335 | 3 changed | quiet |
| 2026-11-14 | `remote/com.thefomite/fomite` | 2026-11-13T013207551090 -> 2026-11-14T010647427878 | 1 changed | quiet |
| 2026-11-14 | `remote/com.statisticsoftheworld/sotw` | 2026-11-13T115728946285 -> 2026-11-14T010646933161 | 3 changed | quiet |
| 2026-11-14 | `remote/io.github.spree/ecommerce-docs` | 2026-11-13T124154623379 -> 2026-11-14T010646164901 | 1 changed | quiet |
| 2026-11-14 | `remote/co.startupperks/startup-perks` | 2026-11-13T115723982998 -> 2026-11-14T010645417809 | 1 changed | quiet |
| 2026-11-14 | `remote/at.space-core/game` | 2026-11-13T150513842054 -> 2026-11-14T010646781783 | 4 changed, 1 added | quiet |
| 2026-11-14 | `remote/com.idosgames/platform` | 2026-11-13T115705894038 -> 2026-11-14T010643270661 | 2 changed | quiet |
| 2026-11-14 | `remote/com.ocklu/hypermarket` | 2026-11-13T120008788307 -> 2026-11-14T010646298995 | 2 changed | quiet |
| 2026-11-14 | `remote/com.multicinesortega/cartelera` | 2026-11-13T115947383860 -> 2026-11-14T010642136320 | 1 changed | quiet |
| 2026-11-14 | `remote/io.suverse.versum/catalog` | 2026-11-13T200755491285 -> 2026-11-14T010641309814 | 3 changed | quiet |
| 2026-11-14 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-13T200746433192 -> 2026-11-14T010638720993 | 2 changed | quiet |
| 2026-11-14 | `remote/com.stocklens/stocklens` | 2026-11-13T200705597565 -> 2026-11-14T010637092531 | 5 changed | quiet |
| 2026-11-14 | `remote/com.orabrain/prax-data-services` | 2026-11-13T200704463534 -> 2026-11-14T010636446685 | 2 changed, 6 added | quiet |
| 2026-11-14 | `remote/io.github.magichourhq/magic-hour` | 2026-11-13T115716189564 -> 2026-11-14T010634794856 | 6 changed | review |
| 2026-11-14 | `remote/io.github.lubobali/lubot` | 2026-11-13T115714408770 -> 2026-11-14T010634346653 | 1 changed | quiet |
| 2026-11-14 | `remote/pl.finwire/data` | 2026-11-13T013154049408 -> 2026-11-14T010635764068 | 2 changed, 1 added | quiet |
| 2026-11-14 | `remote/com.prizepicksapi/server` | 2026-11-12T154559465500 -> 2026-11-14T010633805278 | 3 changed | quiet |
| 2026-11-14 | `remote/org.glolaw/glo-law` | 2026-11-13T115633827521 -> 2026-11-14T010633525022 | 1 changed | quiet |
| 2026-11-14 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-11-12T154641713134 -> 2026-11-14T010632456750 | 1 added | review |
| 2026-11-14 | `remote/com.eventualclimate/premium-lock` | 2026-11-13T013121831373 -> 2026-11-14T010632873826 | 1 changed | quiet |
| 2026-11-14 | `remote/io.github.dstrausser83/db-collab-hub` | 2026-11-13T115559021831 -> 2026-11-14T010631839056 | 2 added | quiet |
| 2026-11-14 | `remote/io.github.daniel3303/equibles` | 2026-11-13T145449902719 -> 2026-11-14T010633420725 | 1 added | quiet |
| 2026-11-14 | `remote/io.github.richardsolomou/praetorium` | 2026-11-13T200739756757 -> 2026-11-14T010633100772 | 4 changed | quiet |
| 2026-11-14 | `remote/gg.plazmi/plazmi` | 2026-11-13T200729716641 -> 2026-11-14T010631149550 | 5 changed | quiet |
| 2026-11-14 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-11-13T013204595040 -> 2026-11-14T010631540234 | 1 changed | quiet |
| 2026-11-14 | `remote/io.github.industrial-platform-ai/research-brief` | 2026-11-13T115526106206 -> 2026-11-14T010630091293 | 1 changed | quiet |
| 2026-11-14 | `remote/ch.kulalabs.pazair/pazair` | 2026-11-13T200737639061 -> 2026-11-14T010631240330 | 1 changed | quiet |
| 2026-11-14 | `remote/app.lovable.peppol-invoice-compass/invoiceverify` | 2026-11-13T150302346706 -> 2026-11-14T010632778399 | 1 added | quiet |
| 2026-11-14 | `remote/io.github.dannyshmueli/agent-analytics-mcp` | 2026-11-13T013143467479 -> 2026-11-14T010630868115 | 1 changed | quiet |
| 2026-11-14 | `remote/io.ddx.pg/archive` | 2026-11-12T074723165331 -> 2026-11-14T010630328097 | 1 changed | quiet |
| 2026-11-14 | `remote/co.getclippy/clippy` | 2026-11-13T115442554941 -> 2026-11-14T010629690142 | 1 changed, 1 added | quiet |
| 2026-11-14 | `remote/ai.tunnelmind/data` | 2026-11-12T074712191102 -> 2026-11-14T010629113470 | 5 changed | quiet |
| 2026-11-14 | `remote/io.github.samuelzcom/chauffeur-booking` | 2026-11-13T115529564433 -> 2026-11-14T010627882286 | 1 changed | quiet |
| 2026-11-14 | `remote/io.github.m2mfreedom/freedom-m2m-mcp-server` | 2026-11-12T074711692652 -> 2026-11-14T010626687333 | 1 added | quiet |
| 2026-11-14 | `remote/com.othermindset/campus` | 2026-11-13T200718711186 -> 2026-11-14T010625958481 | 2 changed | quiet |
| 2026-11-14 | `remote/com.normapi/mcp` | 2026-11-13T115430052409 -> 2026-11-14T010626124002 | 1 changed | quiet |
| 2026-11-14 | `remote/net.hotelrefund/price-tracker` | 2026-11-13T013131604385 -> 2026-11-14T010620969210 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 60265 substantive, 36992 that changed only numbers (a catalogue counter ticking, a date), 1001 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 52526 | 17762 | 34764 | 0 |
| `a2awire.com` | 2375 | 2375 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 405 | 405 | 0 | 0 |
| `civai.co` | 317 | 317 | 0 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `revmesh2074.workers.dev` | 243 | 212 | 31 | 0 |
| `sistaminuten.se` | 233 | 6 | 0 | 227 |
| `afbudsrejser.dk` | 232 | 6 | 0 | 226 |
| `akkilahdot.fi` | 232 | 6 | 0 | 226 |
| `restplass.no` | 232 | 6 | 0 | 226 |
| `socialloop.ai` | 224 | 224 | 0 | 0 |
| 9269 other operators | 38640 | 36347 | 2197 | 96 |
