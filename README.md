# MCP server tool changes

Last change observed 2026-10-20T23:28:31+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

37708 changes to a tool definition: 1522 npm releases (1276 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 36186 readings of hosted servers that found their tools changed; 2268 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-20 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-10-20T120655719381 -> 2026-10-20T232831584143 | 4 changed, 6 removed | quiet |
| 2026-10-20 | `remote/eu.vokko/vokko` | 2026-10-19T135522561625 -> 2026-10-20T232832216473 | 1 added | quiet |
| 2026-10-20 | `remote/se.sistaminuten/travel-search` | 2026-10-20T201134695766 -> 2026-10-20T232829163715 | 1 changed | quiet |
| 2026-10-20 | `remote/com.zinvyl/marketplace` | 2026-10-20T201156963286 -> 2026-10-20T232827179474 | 4 changed | quiet |
| 2026-10-20 | `remote/com.yardstickoutfitters/mcp` | 2026-10-19T212031843420 -> 2026-10-20T232825286825 | 1 changed | quiet |
| 2026-10-20 | `remote/ai.whatsupin/events` | 2026-10-19T212024755284 -> 2026-10-20T232822784332 | 2 changed | quiet |
| 2026-10-20 | `remote/dev.primitive/email` | 2026-10-20T201152163662 -> 2026-10-20T232821946675 | 14 changed (every tool) | quiet |
| 2026-10-20 | `remote/online.waitapp/waitapp` | 2026-10-19T135415227359 -> 2026-10-20T232821757978 | 5 changed, 2 added, 2 removed | quiet |
| 2026-10-20 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-10-20T120653230932 -> 2026-10-20T232819873596 | 4 changed, 6 removed | quiet |
| 2026-10-20 | `remote/studio.gradients/mcp` | 2026-10-20T201148952162 -> 2026-10-20T232818623081 | 1 changed | quiet |
| 2026-10-20 | `remote/no.restplass/travel-search` | 2026-10-20T201212969175 -> 2026-10-20T232819220307 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.SKalinin909/tradingcalc` | 2026-10-19T135343326563 -> 2026-10-20T232816932817 | 27 changed | quiet |
| 2026-10-20 | `remote/fi.akkilahdot/travel-search` | 2026-10-20T201146773214 -> 2026-10-20T232816642641 | 1 changed | quiet |
| 2026-10-20 | `remote/com.tryalpy/alpy` | 2026-10-20T201123485074 -> 2026-10-20T232818597322 | 4 changed | quiet |
| 2026-10-20 | `remote/ai.haggl/haggl` | 2026-10-20T201211024772 -> 2026-10-20T232816535929 | 4 changed | quiet |
| 2026-10-20 | `remote/io.github.privatelawattorneys/wiki-private-law` | 2026-10-19T212014736882 -> 2026-10-20T232816103737 | 1 changed | quiet |
| 2026-10-20 | `remote/dk.afbudsrejser/travel-search` | 2026-10-20T201207978598 -> 2026-10-20T232814188704 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.jukky-source/wealth-agent` | 2026-10-20T135435004044 -> 2026-10-20T232811121733 | 1 added | quiet |
| 2026-10-20 | `remote/tips.suggestionbox/suggestionbox` | 2026-10-18T125046912904 -> 2026-10-20T232811792177 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.Fizzl13/x402-doctor` | 2026-10-19T212022133813 -> 2026-10-20T232810589366 | 5 changed | quiet |
| 2026-10-20 | `remote/io.github.VoiceScapee/voicescape` | 2026-10-20T052346832474 -> 2026-10-20T232809506087 | 3 added | quiet |
| 2026-10-20 | `remote/com.viarapidaservices/mcp` | 2026-10-19T052429574384 -> 2026-10-20T232809748186 | 1 changed | quiet |
| 2026-10-20 | `remote/com.rightshold/rightshold` | 2026-10-20T201151048239 -> 2026-10-20T232808413120 | 5 changed | quiet |
| 2026-10-20 | `remote/com.transitmcp/transit-mcp` | 2026-10-20T135425698910 -> 2026-10-20T232808280012 | 2 changed | quiet |
| 2026-10-20 | `remote/com.tulugar/tulugar` | 2026-10-20T052345308692 -> 2026-10-20T232806916135 | 1 changed | quiet |
| 2026-10-20 | `remote/com.siliconfloor/silicon-floor` | 2026-10-20T201112487207 -> 2026-10-20T232807004152 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.JakubTrousil/agentsjunction` | 2026-10-20T201144460879 -> 2026-10-20T232804750313 | 2 changed, 1 added | quiet |
| 2026-10-20 | `remote/com.swarmmemo/bulletin.1` | 2026-10-20T135420074008 -> 2026-10-20T232803031328 | 2 changed | quiet |
| 2026-10-20 | `remote/com.swarmmemo/bulletin` | 2026-10-20T135420055591 -> 2026-10-20T232802911047 | 2 changed | quiet |
| 2026-10-20 | `remote/ai.weio/site-check` | 2026-10-20T104322945147 -> 2026-10-20T232802501244 | 2 added, 3 removed | quiet |
| 2026-10-20 | `remote/ai.spoe/spoe` | 2026-10-19T135644087216 -> 2026-10-20T232801267882 | 2 changed | quiet |
| 2026-10-20 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-20T201125310864 -> 2026-10-20T232759197472 | 4 changed | quiet |
| 2026-10-20 | `remote/io.github.exquad/thecablecode` | 2026-10-20T201135588121 -> 2026-10-20T232757766974 | 1 changed | quiet |
| 2026-10-20 | `remote/com.owlchart/owlchart` | 2026-10-20T135406174718 -> 2026-10-20T232757472413 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.vicentesurraco/offpeak` | 2026-10-18T051323422887 -> 2026-10-20T232755600082 | 12 changed | quiet |
| 2026-10-20 | `remote/io.github.jennipro-engineering/ghost-market-web` | 2026-10-20T201129938275 -> 2026-10-20T232754664158 | 4 changed | quiet |
| 2026-10-20 | `remote/com.serdaroztetik/call-me` | 2026-10-18T113246691615 -> 2026-10-20T232753930084 | 1 changed | quiet |
| 2026-10-20 | `remote/com.remoshift/jobs` | 2026-10-20T201118387823 -> 2026-10-20T232751082635 | 1 changed | quiet |
| 2026-10-20 | `remote/com.missyera/missyera` | 2026-10-19T135043003326 -> 2026-10-20T232751585732 | 1 added | quiet |
| 2026-10-20 | `remote/io.github.ondraulehla/mcpcost` | 2026-10-19T135033188743 -> 2026-10-20T232750726749 | 1 changed | quiet |
| 2026-10-20 | `remote/com.voice-school/lesson-booking` | 2026-10-20T103917073047 -> 2026-10-20T232749878135 | 1 changed, 3 added | quiet |
| 2026-10-20 | `remote/io.github.helferundprofi/helfer-und-profi` | 2026-10-20T201110656318 -> 2026-10-20T232745728107 | 4 changed | quiet |
| 2026-10-20 | `remote/online.pageaudit/pageaudit` | 2026-10-20T135402737574 -> 2026-10-20T232745723128 | 1 changed, 1 added | quiet |
| 2026-10-20 | `remote/net.clickwise/mcp` | 2026-10-20T052259372008 -> 2026-10-20T232743830908 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.sonpiaz/openaffiliate-mcp` | 2026-10-19T211917664081 -> 2026-10-20T232742590080 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-10-20T201046550599 -> 2026-10-20T232742345453 | 1 changed | review |
| 2026-10-20 | `remote/com.obriym-crm/mcp` | 2026-10-20T201105781874 -> 2026-10-20T232742848502 | 4 changed, 1 added | quiet |
| 2026-10-20 | `remote/io.github.fredxhansson-cmyk/noniner` | 2026-10-19T135428822666 -> 2026-10-20T232742087626 | 5 added | quiet |
| 2026-10-20 | `remote/io.github.jamboree777/nightwatch` | 2026-10-18T113125205502 -> 2026-10-20T232740476657 | 2 changed, 4 added | quiet |
| 2026-10-20 | `remote/com.neblla/neblla` | 2026-10-20T201104324532 -> 2026-10-20T232741192287 | 6 changed | quiet |
| 2026-10-20 | `remote/com.myinsurancecity/mcp` | 2026-10-19T052346570991 -> 2026-10-20T232738975949 | 1 changed | quiet |
| 2026-10-20 | `remote/com.moonshotlab1/inventory` | 2026-10-19T135412878054 -> 2026-10-20T232739581020 | 2 changed, 1 added | review |
| 2026-10-20 | `remote/io.github.GrayWolf8-creator/gw8-signal-api` | 2026-10-19T155920952983 -> 2026-10-20T232736833396 | 2 added | review |
| 2026-10-20 | `remote/app.gigxchange/gigxchange` | 2026-10-19T211851627223 -> 2026-10-20T232739625223 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.ronrey/comos-federation` | 2026-10-20T103728267403 -> 2026-10-20T232734261505 | 1 removed | quiet |
| 2026-10-20 | `remote/com.voice-school/singing-vocal-lesson-booking` | 2026-10-20T103927724028 -> 2026-10-20T232733839956 | 1 changed, 3 added | quiet |
| 2026-10-20 | `remote/io.github.valuein/mcp-sec-edgar` | 2026-10-20T052251100421 -> 2026-10-20T232732848168 | 4 changed, 1 added | quiet |
| 2026-10-20 | `remote/com.tkawen/intelligence-gateway` | 2026-10-18T223915973655 -> 2026-10-20T232733200484 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.qxxx5vyd77-byte/directors-lookbook` | 2026-10-18T185912531136 -> 2026-10-20T232730466657 | 1 changed | quiet |
| 2026-10-20 | `remote/nyc.motley/mcp` | 2026-10-18T185944050248 -> 2026-10-20T232728259306 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 24452 substantive, 12730 that changed only numbers (a catalogue counter ticking, a date), 526 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 19158 | 7228 | 11930 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 170 | 170 | 0 | 0 |
| `sistaminuten.se` | 126 | 4 | 0 | 122 |
| `afbudsrejser.dk` | 125 | 4 | 0 | 121 |
| `akkilahdot.fi` | 125 | 4 | 0 | 121 |
| `restplass.no` | 125 | 4 | 0 | 121 |
| `socialloop.ai` | 122 | 122 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `remoshift.com` | 96 | 6 | 90 | 0 |
| `fundinglandscape.com` | 94 | 60 | 34 | 0 |
| 4665 other operators | 14476 | 13759 | 676 | 41 |
