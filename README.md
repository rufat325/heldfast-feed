# MCP server tool changes

Last change observed 2026-09-29T11:35:50+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

13162 changes to a tool definition: 383 npm releases (137 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 12779 readings of hosted servers that found their tools changed; 72 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-09-29 | `remote/se.sistaminuten/travel-search` | 2026-09-29T104139359764 -> 2026-09-29T113551744770 | 1 changed | quiet |
| 2026-09-29 | `remote/za.co.simcloud/simcloud` | 2026-09-23T160751503559 -> 2026-09-29T113510770718 | 1 changed | quiet |
| 2026-09-29 | `remote/fi.akkilahdot/travel-search` | 2026-09-29T104015178677 -> 2026-09-29T113456639943 | 1 changed | quiet |
| 2026-09-29 | `remote/no.restplass/travel-search` | 2026-09-29T103957856704 -> 2026-09-29T113446824575 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.Schoasch/backtesting-arena` | 2026-09-28T055533461379 -> 2026-09-29T113434075189 | 4 changed | quiet |
| 2026-09-29 | `remote/dk.afbudsrejser/travel-search` | 2026-09-29T103928230868 -> 2026-09-29T113428746182 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-29T103919941929 -> 2026-09-29T113414037706 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-09-29T101223131313 -> 2026-09-29T113337292549 | 15 changed | review |
| 2026-09-29 | `remote/com.remoshift/jobs` | 2026-09-29T101802364283 -> 2026-09-29T113332718299 | 1 changed | quiet |
| 2026-09-29 | `remote/net.clickwise/product-catalog` | 2026-09-28T142428179211 -> 2026-09-29T113303117731 | 5 added | quiet |
| 2026-09-29 | `remote/es.cesaryague/paki-curator` | 2026-09-29T101118147251 -> 2026-09-29T113236137946 | 1 changed | quiet |
| 2026-09-29 | `remote/uk.ucode/sms` | 2026-09-23T160804723491 -> 2026-09-29T113211937845 | 2 changed, 8 added | quiet |
| 2026-09-29 | `remote/com.shipstatic/mcp` | 2026-09-28T142329433120 -> 2026-09-29T113209248163 | 1 changed | quiet |
| 2026-09-29 | `remote/com.sednasystem/genesis` | 2026-09-29T101612415656 -> 2026-09-29T113206668064 | 1 changed | quiet |
| 2026-09-29 | `remote/com.bluepillow/hotels` | 2026-09-23T160519658734 -> 2026-09-29T113119146800 | 1 changed | quiet |
| 2026-09-29 | `remote/io.insourcia/insourcia` | 2026-09-28T072906166501 -> 2026-09-29T113107916818 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.kylehawke-stack/locationlists` | 2026-09-29T072716087030 -> 2026-09-29T113049878992 | 5 changed | quiet |
| 2026-09-29 | `remote/io.cortexplus/cortexplus` | 2026-09-28T072833207520 -> 2026-09-29T113039625057 | 1 changed | quiet |
| 2026-09-29 | `remote/ai.humanproblems/humanproblems` | 2026-09-28T170329059926 -> 2026-09-29T113016604081 | 5 changed, 1 added | quiet |
| 2026-09-29 | `remote/com.greenlitbooks/catalog` | 2026-09-23T160435538148 -> 2026-09-29T113004880866 | 9 changed, 2 added (every tool) | quiet |
| 2026-09-29 | `remote/io.github.Youjg25/maison-de-talents` | 2026-09-23T160625797629 -> 2026-09-29T113003491844 | 3 changed (every tool) | quiet |
| 2026-09-29 | `remote/cz.suorigo.konfigurator/server` | 2026-09-24T202222607360 -> 2026-09-29T112955900903 | 2 changed | quiet |
| 2026-09-29 | `remote/io.github.tettertotter/fundinglandscape` | 2026-09-29T100608892016 -> 2026-09-29T112822000464 | 2 changed | quiet |
| 2026-09-29 | `remote/cloud.dchub/mcp-server` | 2026-09-29T100540237742 -> 2026-09-29T112749193134 | 1 changed | quiet |
| 2026-09-29 | `remote/xyz.getvia.app/via-network` | 2026-09-29T100623534894 -> 2026-09-29T112637678309 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.gosadu/loophole-tape` | 2026-09-29T100427705309 -> 2026-09-29T112453221981 | 32 changed, 1 added (every tool) | review |
| 2026-09-29 | `remote/com.hookdetector/hookdetector` | 2026-09-28T140938766409 -> 2026-09-29T112448428901 | 2 changed | quiet |
| 2026-09-29 | `remote/io.github.TWolf01/agentsgather` | 2026-09-28T140854251631 -> 2026-09-29T112425200257 | 13 added | quiet |
| 2026-09-29 | `remote/app.agentbit/mcp` | 2026-09-29T102850938294 -> 2026-09-29T112421201032 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.belegante-byte/aetherx-mcp` | 2026-09-29T102753043115 -> 2026-09-29T112310726619 | 5 changed, 5 added | quiet |
| 2026-09-29 | `remote/at.aamio/aamio` | 2026-09-26T113246566969 -> 2026-09-29T112301105753 | 1 changed | quiet |
| 2026-09-29 | `remote/se.sistaminuten/travel-search` | 2026-09-29T101250350114 -> 2026-09-29T104139359764 | 1 changed | quiet |
| 2026-09-29 | `@shipstatic/mcp` | 2.3.0 -> 2.3.1 | 1 changed | quiet |
| 2026-09-29 | `remote/fi.akkilahdot/travel-search` | 2026-09-29T101949386626 -> 2026-09-29T104015178677 | 1 changed | quiet |
| 2026-09-29 | `remote/no.restplass/travel-search` | 2026-09-29T101335944951 -> 2026-09-29T103957856704 | 1 changed | quiet |
| 2026-09-29 | `remote/dk.afbudsrejser/travel-search` | 2026-09-29T101311693931 -> 2026-09-29T103928230868 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-29T101842037959 -> 2026-09-29T103919941929 | 1 changed | quiet |
| 2026-09-29 | `remote/com.tttkmbb/calcgrid` | 2026-09-28T170346188271 -> 2026-09-29T103849625519 | 3 changed, 189 added | quiet |
| 2026-09-29 | `remote/xyz.signomy/civitae` | 2026-09-29T101212674002 -> 2026-09-29T103815842930 | 1 changed | quiet |
| 2026-09-29 | `remote/com.nessgate/nessgate` | 2026-09-29T073543007919 -> 2026-09-29T103748654553 | 1 changed | quiet |
| 2026-09-29 | `remote/fi.ophis/mcp` | 2026-09-29T073430268940 -> 2026-09-29T103649335026 | 2 changed | quiet |
| 2026-09-29 | `remote/io.github.wilmendezofficial/postari` | 2026-09-29T073024006848 -> 2026-09-29T103639411587 | 3 changed | quiet |
| 2026-09-29 | `remote/com.kernelcad/kernelcad` | 2026-09-29T073344714878 -> 2026-09-29T103626156916 | 4 changed | quiet |
| 2026-09-29 | `remote/com.vertodigital/mcp` | 2026-09-23T160628745345 -> 2026-09-29T103535528348 | 1 changed | quiet |
| 2026-09-29 | `remote/com.focxle/agent-payments-virtual-cards` | 2026-09-27T065422437524 -> 2026-09-29T103309982016 | 1 changed | quiet |
| 2026-09-29 | `remote/org.aspern/aspern` | 2026-09-29T003545792029 -> 2026-09-29T103148359904 | 14 changed | quiet |
| 2026-09-29 | `remote/io.github.moonspacenow-tech/aicomglobal` | 2026-09-29T100330356029 -> 2026-09-29T102936928935 | 2 changed | quiet |
| 2026-09-29 | `remote/app.agentbit/mcp` | 2026-09-29T072412964552 -> 2026-09-29T102850938294 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.belegante-byte/aetherx-mcp` | 2026-09-29T072255852595 -> 2026-09-29T102753043115 | 7 changed | quiet |
| 2026-09-29 | `remote/fi.akkilahdot/travel-search` | 2026-09-29T083120282707 -> 2026-09-29T101949386626 | 1 changed | quiet |
| 2026-09-29 | `remote/com.goedvps.app.wodan-posture/wodan-posture` | 2026-09-28T170359825177 -> 2026-09-29T101945049245 | 1 added | quiet |
| 2026-09-29 | `remote/com.tickerinside/tickerinside-mcp` | 2026-09-29T061651208004 -> 2026-09-29T101907831545 | 5 changed | quiet |
| 2026-09-29 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-29T083023012540 -> 2026-09-29T101842037959 | 1 changed | quiet |
| 2026-09-29 | `remote/com.secondappraisal/total-loss-intake` | 2026-09-28T142511213002 -> 2026-09-29T101825206001 | 1 changed | review |
| 2026-09-29 | `remote/ai.agentlookups/counterscript` | 2026-09-28T104234422542 -> 2026-09-29T101812105351 | 1 changed | quiet |
| 2026-09-29 | `remote/com.remoshift/jobs` | 2026-09-29T080301513408 -> 2026-09-29T101802364283 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.steffanricardo/the-dutch-directory.1` | 2026-09-29T080121637005 -> 2026-09-29T101625980794 | 1 added | quiet |
| 2026-09-29 | `remote/ai.switchapp/switch` | 2026-09-29T061633442025 -> 2026-09-29T101620640090 | 1 changed, 1 added | quiet |
| 2026-09-29 | `remote/com.sednasystem/genesis` | 2026-09-29T073448599010 -> 2026-09-29T101612415656 | 1 changed | quiet |
| 2026-09-29 | `remote/travel.ourway/camino-de-santiago` | 2026-09-23T162717210598 -> 2026-09-29T101554567317 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 9834 substantive, 3159 that changed only numbers (a catalogue counter ticking, a date), 169 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 7023 | 4048 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `caseyjhand.com` | 56 | 56 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| `sistaminuten.se` | 43 | 2 | 0 | 41 |
| `afbudsrejser.dk` | 42 | 2 | 0 | 40 |
| `akkilahdot.fi` | 42 | 2 | 0 | 40 |
| `restplass.no` | 42 | 2 | 0 | 40 |
| `socialloop.ai` | 42 | 42 | 0 | 0 |
| `fastmcp.app` | 29 | 29 | 0 | 0 |
| `dayze.com` | 28 | 28 | 0 | 0 |
| 1274 other operators | 2999 | 2807 | 184 | 8 |
