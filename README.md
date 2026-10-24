# MCP server tool changes

Last change observed 2026-10-24T22:46:51+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

47488 changes to a tool definition: 2087 npm releases (1841 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 45401 readings of hosted servers that found their tools changed; 2470 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-24 | `remote/io.github.eamwhite1/xrpl-referee` | 2026-10-24T112948284114 -> 2026-10-24T224652156832 | 5 changed | quiet |
| 2026-10-24 | `remote/se.sistaminuten/travel-search` | 2026-10-24T190428788488 -> 2026-10-24T224650501068 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.eamwhite1/agent-trust` | 2026-10-24T112918150742 -> 2026-10-24T224638388688 | 5 changed | quiet |
| 2026-10-24 | `remote/io.github.LE-VAI/designesy-org` | 2026-10-24T050520939584 -> 2026-10-24T224637245545 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-10-24T050519183622 -> 2026-10-24T224634685795 | 44 added | quiet |
| 2026-10-24 | `remote/io.github.SKalinin909/tradingcalc` | 2026-10-23T200833049613 -> 2026-10-24T224636434995 | 6 changed | quiet |
| 2026-10-24 | `remote/com.tofubofu/ai-visibility` | 2026-10-24T112809512210 -> 2026-10-24T224635711272 | 1 changed | quiet |
| 2026-10-24 | `remote/no.restplass/travel-search` | 2026-10-24T190419530359 -> 2026-10-24T224632652633 | 1 changed | quiet |
| 2026-10-24 | `remote/com.starcovery/mcp` | 2026-10-22T110314239427 -> 2026-10-24T224632772929 | 2 changed | quiet |
| 2026-10-24 | `remote/studio.gradients/mcp` | 2026-10-24T190434356712 -> 2026-10-24T224631389507 | 1 changed | quiet |
| 2026-10-24 | `remote/dk.afbudsrejser/travel-search` | 2026-10-24T190418334040 -> 2026-10-24T224631672260 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.privatelawattorneys/wiki-private-law` | 2026-10-24T190432766165 -> 2026-10-24T224630762467 | 4 changed | quiet |
| 2026-10-24 | `remote/io.github.jennipro-engineering/ghost-market-web` | 2026-10-23T200814350669 -> 2026-10-24T224631139012 | 1 changed | quiet |
| 2026-10-24 | `remote/fi.akkilahdot/travel-search` | 2026-10-24T190432982551 -> 2026-10-24T224630716122 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.philpof102-svg/tokenizedblock` | 2026-10-24T112940947537 -> 2026-10-24T224628578659 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.cyanheads/ris-austria-mcp-server` | 2026-10-24T112618101232 -> 2026-10-24T224628189624 | 2 changed | quiet |
| 2026-10-24 | `remote/com.tiamatcrypto.sweetai/agent-intel` | 2026-10-22T121830900007 -> 2026-10-24T224629220620 | 32 removed | quiet |
| 2026-10-24 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-24T112900309318 -> 2026-10-24T224625622584 | 10 changed | quiet |
| 2026-10-24 | `remote/tools.settled/settled` | 2026-10-23T120431387051 -> 2026-10-24T224624414256 | 1 changed | review |
| 2026-10-24 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-24T190425215525 -> 2026-10-24T224623929002 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.muaviamohammed/mizan` | 2026-10-24T190413916512 -> 2026-10-24T224628828771 | 1 changed | quiet |
| 2026-10-24 | `remote/dev.tanod/tanod` | 2026-10-24T190415589015 -> 2026-10-24T224630435101 | 1 changed | quiet |
| 2026-10-24 | `remote/com.0xpi.sdsentry/sds-lookup` | 2026-10-24T112827107542 -> 2026-10-24T224623971327 | 1 changed | quiet |
| 2026-10-24 | `remote/com.idosgames/platform` | 2026-10-22T105725527582 -> 2026-10-24T224624143601 | 1 changed, 7 added | quiet |
| 2026-10-24 | `remote/com.remoshift/jobs` | 2026-10-24T190422845538 -> 2026-10-24T224622066043 | 1 changed | quiet |
| 2026-10-24 | `remote/co.civai.nova/support-agent-admin` | 2026-10-24T190410155602 -> 2026-10-24T224621156653 | 2 added | quiet |
| 2026-10-24 | `remote/sh.openpath/openpath` | 2026-10-24T190406143674 -> 2026-10-24T224619849709 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.cyanheads/nws-weather-mcp-server` | 2026-10-23T120514708323 -> 2026-10-24T224619773298 | 2 changed | quiet |
| 2026-10-24 | `remote/io.github.cloakmaster/pact0` | 2026-10-22T052559820167 -> 2026-10-24T224619325236 | 1 changed | quiet |
| 2026-10-24 | `remote/ch.kulalabs.pazair/pazair` | 2026-10-24T190405385571 -> 2026-10-24T224622763207 | 2 added | quiet |
| 2026-10-24 | `remote/org.worldgdp/nowcasts` | 2026-10-24T190407376729 -> 2026-10-24T224618567124 | 2 changed | quiet |
| 2026-10-24 | `remote/io.github.ondraulehla/mcpcost` | 2026-10-24T190404247737 -> 2026-10-24T224618408927 | 1 changed | quiet |
| 2026-10-24 | `remote/com.webinarignition/mcp` | 2026-10-24T190407231970 -> 2026-10-24T224618444190 | 1 changed | quiet |
| 2026-10-24 | `remote/de.viafrei/mcp` | 2026-10-22T202036499038 -> 2026-10-24T224618073557 | 2 changed | quiet |
| 2026-10-24 | `remote/com.mcpcheckup/mcp` | 2026-10-22T233917137375 -> 2026-10-24T224618003934 | 1 changed | quiet |
| 2026-10-24 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-10-24T190416443147 -> 2026-10-24T224616378123 | 10 changed, 1 added | quiet |
| 2026-10-24 | `remote/com.sportstatsapi/sports-data` | 2026-10-24T190404889266 -> 2026-10-24T224616597180 | 1 changed | quiet |
| 2026-10-24 | `remote/com.multicinesortega/cartelera` | 2026-10-24T050515227082 -> 2026-10-24T224616775895 | 1 changed | quiet |
| 2026-10-24 | `remote/app.manawa/manawa-terminal` | 2026-10-23T233417275474 -> 2026-10-24T224613339736 | 1 changed | quiet |
| 2026-10-24 | `remote/com.movingplace/mcp` | 2026-10-23T120101509440 -> 2026-10-24T224612496916 | 16 added | quiet |
| 2026-10-24 | `remote/io.github.jasp402/hypercodemotion-mcp` | 2026-10-24T112304192935 -> 2026-10-24T224611749627 | 1 changed | quiet |
| 2026-10-24 | `remote/com.opedd/opedd-mcp` | 2026-10-24T112518688853 -> 2026-10-24T224610919512 | 1 changed, 3 removed | quiet |
| 2026-10-24 | `remote/com.keyvex/keyvex` | 2026-10-22T202034256912 -> 2026-10-24T224611668927 | 1 changed | quiet |
| 2026-10-24 | `remote/com.keyvex/keyvex.1` | 2026-10-22T202039562128 -> 2026-10-24T224609986501 | 1 changed | quiet |
| 2026-10-24 | `remote/com.convertlyft/convertlyft` | 2026-10-24T190355718237 -> 2026-10-24T224610829049 | 2 changed | quiet |
| 2026-10-24 | `remote/io.agentweather/agent-weather` | 2026-10-24T112210642074 -> 2026-10-24T224609005872 | 2 changed | quiet |
| 2026-10-24 | `remote/io.github.barneywohl/hugging-bay` | 2026-10-22T052535158841 -> 2026-10-24T224608718733 | 2 changed | quiet |
| 2026-10-24 | `remote/io.github.edtool79-collab/hirepulse-gateway` | 2026-10-24T190352560904 -> 2026-10-24T224604912094 | 19 changed | quiet |
| 2026-10-24 | `remote/cc.hlist/hlist-ai-tools` | 2026-10-24T190347680455 -> 2026-10-24T224604272101 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-24T190346388918 -> 2026-10-24T224602268378 | 1 changed | quiet |
| 2026-10-24 | `remote/com.firenum/fire-planner` | 2026-10-24T112028668801 -> 2026-10-24T224602094670 | 1 changed | quiet |
| 2026-10-24 | `remote/app.everloot/knowledge` | 2026-10-22T202129001510 -> 2026-10-24T224615083806 | 1 changed | quiet |
| 2026-10-24 | `remote/site.cryptofeed402/feed` | 2026-10-23T200734182280 -> 2026-10-24T224600671336 | 12 changed | review |
| 2026-10-24 | `remote/com.cooperemail/cooper-email` | 2026-10-24T190346589237 -> 2026-10-24T224600178958 | 2 changed | quiet |
| 2026-10-24 | `remote/club.elron/public-rentals` | 2026-10-24T050500081521 -> 2026-10-24T224601404955 | 2 changed | quiet |
| 2026-10-24 | `remote/io.github.smithdavedesign/botchelor` | 2026-10-24T190345539211 -> 2026-10-24T224558008944 | 2 changed | quiet |
| 2026-10-24 | `remote/ai.capxule/capxule` | 2026-10-24T190340138020 -> 2026-10-24T224556945428 | 1 changed | quiet |
| 2026-10-24 | `remote/net.ts.tailb4ac3a.ari001/arysphere-x402` | 2026-10-24T050450833733 -> 2026-10-24T224559721324 | 6 added, 26 removed | quiet |
| 2026-10-24 | `remote/io.github.majidkabir/carbonara` | 2026-10-23T115544871253 -> 2026-10-24T224558216999 | 2 added | quiet |
| 2026-10-24 | `remote/com.daedalmap/reverse-geocoding` | 2026-10-24T111709857844 -> 2026-10-24T224555929910 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 29475 substantive, 17394 that changed only numbers (a catalogue counter ticking, a date), 619 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 25144 | 8777 | 16367 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 659 | 659 | 0 | 0 |
| `caseyjhand.com` | 200 | 200 | 0 | 0 |
| `sistaminuten.se` | 147 | 4 | 0 | 143 |
| `afbudsrejser.dk` | 146 | 4 | 0 | 142 |
| `akkilahdot.fi` | 146 | 4 | 0 | 142 |
| `restplass.no` | 146 | 4 | 0 | 142 |
| `socialloop.ai` | 142 | 142 | 0 | 0 |
| `remoshift.com` | 116 | 8 | 108 | 0 |
| `fundinglandscape.com` | 111 | 71 | 40 | 0 |
| `openkrill.app` | 111 | 111 | 0 | 0 |
| 5473 other operators | 18079 | 17150 | 879 | 50 |
