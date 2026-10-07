# MCP server tool changes

Last change observed 2026-10-07T06:34:27+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10128 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 21701 hosted endpoints (read daily, and every four hours while they keep changing).

22606 changes to a tool definition: 789 npm releases (543 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 21817 readings of hosted servers that found their tools changed; 303 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-07 | `remote/io.github.SoapyRED/freightutils` | 2026-10-07T001235671929 -> 2026-10-07T063429551915 | 3 changed | quiet |
| 2026-10-07 | `remote/fi.akkilahdot/travel-search` | 2026-10-07T001233462791 -> 2026-10-07T063426302823 | 1 changed | quiet |
| 2026-10-07 | `remote/lat.watchtower/watchtower` | 2026-10-06T110333548006 -> 2026-10-07T063423145737 | 4 changed | quiet |
| 2026-10-07 | `remote/com.vermarco/marketplace` | 2026-10-06T110327188189 -> 2026-10-07T063421629627 | 8 added | quiet |
| 2026-10-07 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-06T013128967229 -> 2026-10-07T063415506006 | 1 changed | quiet |
| 2026-10-07 | `remote/com.swarmmemo/bulletin` | 2026-10-07T001226388171 -> 2026-10-07T063414813978 | 71 changed, 4 added (every tool) | quiet |
| 2026-10-07 | `remote/us.spacenexus/spacenexus` | 2026-10-06T110237208718 -> 2026-10-07T063409058838 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-07T001221441284 -> 2026-10-07T063409223418 | 1 changed | quiet |
| 2026-10-07 | `remote/ai.shorti/shorti` | 2026-10-07T001222361566 -> 2026-10-07T063408069611 | 11 changed | quiet |
| 2026-10-07 | `remote/com.remoshift/jobs` | 2026-10-07T001217285928 -> 2026-10-07T063401972522 | 1 changed | quiet |
| 2026-10-07 | `remote/com.multicinesortega/cartelera` | 2026-10-06T110050163638 -> 2026-10-07T063348805823 | 1 changed | quiet |
| 2026-10-07 | `remote/com.vibe-fixer/vibefix` | 2026-10-07T001232271340 -> 2026-10-07T063345656497 | 2 added | quiet |
| 2026-10-07 | `remote/com.veritahire/jobs` | 2026-10-06T110208749165 -> 2026-10-07T063345192755 | 1 changed | quiet |
| 2026-10-07 | `remote/ar.com.muovi/mcp-server` | 2026-10-07T001204023598 -> 2026-10-07T063341301194 | 1 changed | quiet |
| 2026-10-07 | `remote/com.jojapi/swift-ai` | 2026-10-06T013101802579 -> 2026-10-07T063340618665 | 1 changed | quiet |
| 2026-10-07 | `remote/com.eventescapes/event-escapes` | 2026-10-06T105911566276 -> 2026-10-07T063344268273 | 1 changed | quiet |
| 2026-10-07 | `remote/io.careclinic/health-tracker` | 2026-10-06T105848228645 -> 2026-10-07T063334785473 | 4 changed | quiet |
| 2026-10-07 | `remote/vn.algolab/mcp.1` | 2026-10-06T105836210397 -> 2026-10-07T063335136931 | 4 changed | quiet |
| 2026-10-07 | `remote/io.github.industrial-platform-ai/research-brief` | 2026-10-06T105838664171 -> 2026-10-07T063333179443 | 1 changed | quiet |
| 2026-10-07 | `remote/com.thefilmradar/filmlab` | 2026-10-07T001156958186 -> 2026-10-07T063333666683 | 2 added | quiet |
| 2026-10-07 | `remote/trade.loomdesk/loomdesk` | 2026-10-07T001154230584 -> 2026-10-07T063329241892 | 5 changed, 2 added | quiet |
| 2026-10-07 | `remote/io.github.89rat/code402` | 2026-10-06T133806969728 -> 2026-10-07T063328647831 | 7 changed, 1 added | quiet |
| 2026-10-07 | `remote/com.qevrulan/lockzone` | 2026-10-06T110006576745 -> 2026-10-07T063327155660 | 1 changed | quiet |
| 2026-10-07 | `remote/no.restplass/travel-search` | 2026-10-07T001333425646 -> 2026-10-07T063325572685 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.samuelzcom/chauffeur-booking` | 2026-10-05T172644134384 -> 2026-10-07T063330678477 | 5 changed (every tool) | quiet |
| 2026-10-07 | `remote/app.pixly/pixly` | 2026-10-06T184008618013 -> 2026-10-07T063324616929 | 3 changed | quiet |
| 2026-10-07 | `remote/dk.afbudsrejser/travel-search` | 2026-10-07T001327770266 -> 2026-10-07T063320948257 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.VoiceScapee/voicescape` | 2026-10-07T001325250827 -> 2026-10-07T063318904986 | 1 changed, 1 added | quiet |
| 2026-10-07 | `remote/io.github.nimbusbci/nimbus-mcp` | 2026-10-06T105925702957 -> 2026-10-07T063318114909 | 1 changed | quiet |
| 2026-10-07 | `remote/se.sistaminuten/travel-search` | 2026-10-07T001242514419 -> 2026-10-07T063315638638 | 1 changed | quiet |
| 2026-10-07 | `remote/com.tickerz/tickerz` | 2026-10-06T110217660295 -> 2026-10-07T063314961636 | 2 added | quiet |
| 2026-10-07 | `remote/com.menloinsurance/mcp` | 2026-10-06T110200983057 -> 2026-10-07T063321555292 | 3 changed | quiet |
| 2026-10-07 | `remote/com.theoddsgap/answers` | 2026-10-06T110215931879 -> 2026-10-07T063314442624 | 1 changed | quiet |
| 2026-10-07 | `remote/com.tiamatcrypto.sweetai/agent-intel` | 2026-10-06T110202984500 -> 2026-10-07T063314404309 | 1 added | quiet |
| 2026-10-07 | `remote/io.scopeweb/scopeweb` | 2026-10-06T105818872321 -> 2026-10-07T063309443546 | 6 changed | quiet |
| 2026-10-07 | `remote/cloud.dchub/mcp-server.2` | 2026-10-06T105458166409 -> 2026-10-07T063305444136 | 3 changed | quiet |
| 2026-10-07 | `remote/io.github.bourhaouta/tailwindshades` | 2026-10-06T110057343030 -> 2026-10-07T063304971125 | 1 changed | quiet |
| 2026-10-07 | `remote/com.jojapi/product-barcode-api` | 2026-10-06T183944641737 -> 2026-10-07T063305278280 | 2 changed | quiet |
| 2026-10-07 | `remote/im.peoplesearch/email-finder` | 2026-10-06T110027578052 -> 2026-10-07T063302627818 | 2 changed | quiet |
| 2026-10-07 | `remote/io.github.cloakmaster/pact0` | 2026-10-07T001253257387 -> 2026-10-07T063301681976 | 1 changed | quiet |
| 2026-10-07 | `remote/co.civai.nova/research-agent` | 2026-10-06T110012083333 -> 2026-10-07T063300521768 | 2 added | quiet |
| 2026-10-07 | `remote/co.civai.nova/google-sheets-agent` | 2026-10-06T110010956205 -> 2026-10-07T063300422639 | 2 added | quiet |
| 2026-10-07 | `remote/ai.satohub/onchain-agents` | 2026-10-06T110029078738 -> 2026-10-07T063259798301 | 6 changed | quiet |
| 2026-10-07 | `remote/io.github.snayyar00/webability` | 2026-10-06T105941743270 -> 2026-10-07T063257157794 | 6 changed, 4 added | quiet |
| 2026-10-07 | `remote/win.price/pricewin` | 2026-10-06T113346225978 -> 2026-10-07T063253685203 | 1 changed | quiet |
| 2026-10-07 | `remote/com.dimhour/catalog` | 2026-10-05T172634251694 -> 2026-10-07T063245646248 | 1 changed | quiet |
| 2026-10-07 | `remote/ai.skuit/catalog` | 2026-10-06T105824282291 -> 2026-10-07T063244546874 | 1 changed | quiet |
| 2026-10-07 | `remote/gl.parse/mcp` | 2026-10-07T001200005644 -> 2026-10-07T063243798994 | 6 changed | quiet |
| 2026-10-07 | `remote/io.github.89rat/openfang-rail` | 2026-10-06T133244372258 -> 2026-10-07T063243205845 | 7 changed, 1 added | quiet |
| 2026-10-07 | `remote/io.github.Book0fEli/paycheck` | 2026-10-07T001229799470 -> 2026-10-07T063258616826 | 1 changed | quiet |
| 2026-10-07 | `remote/com.hproxy/mcp` | 2026-10-06T105743924204 -> 2026-10-07T063239826998 | 1 changed | quiet |
| 2026-10-07 | `remote/io.github.cherami-mail/cherami-mcp` | 2026-10-06T105421168876 -> 2026-10-07T063245205036 | 19 changed | quiet |
| 2026-10-07 | `remote/io.github.genesis-plan/lingshu-solver` | 2026-10-06T105651051157 -> 2026-10-07T063235506538 | 3 changed, 1 added | quiet |
| 2026-10-07 | `remote/io.github.xpex-systems-ai/gxeon-agent-marketplace` | 2026-10-06T105637975346 -> 2026-10-07T063232520511 | 1 added | quiet |
| 2026-10-07 | `remote/io.github.sustany/casemagic` | 2026-10-06T105416423434 -> 2026-10-07T063236198704 | 6 changed | quiet |
| 2026-10-07 | `remote/com.blockvectra/docs` | 2026-10-06T113312768325 -> 2026-10-07T063228488699 | 1 changed | quiet |
| 2026-10-07 | `remote/net.gradetv/grade` | 2026-10-05T172630614429 -> 2026-10-07T063226002811 | 2 changed | quiet |
| 2026-10-07 | `remote/com.chateaupedia/chateaux` | 2026-10-06T105358704402 -> 2026-10-07T063217712390 | 1 changed | quiet |
| 2026-10-07 | `remote/cloud.dchub/mcp-server` | 2026-10-06T105411663265 -> 2026-10-07T063217227844 | 92 changed (every tool) | quiet |
| 2026-10-07 | `remote/dev.workers.ekelund-apps.custody-calendar/custody-calendar-maker` | 2026-10-06T105402695806 -> 2026-10-07T063214431394 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 15830 substantive, 6447 that changed only numbers (a catalogue counter ticking, a date), 329 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 11736 | 5690 | 6046 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `sistaminuten.se` | 80 | 2 | 0 | 78 |
| `afbudsrejser.dk` | 79 | 2 | 0 | 77 |
| `akkilahdot.fi` | 79 | 2 | 0 | 77 |
| `restplass.no` | 79 | 2 | 0 | 77 |
| `socialloop.ai` | 77 | 77 | 0 | 0 |
| `caseyjhand.com` | 74 | 74 | 0 | 0 |
| `dayze.com` | 65 | 65 | 0 | 0 |
| `remoshift.com` | 55 | 2 | 53 | 0 |
| 2774 other operators | 7420 | 7052 | 348 | 20 |
