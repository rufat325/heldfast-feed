# MCP server tool changes

Last change observed 2026-09-29T10:19:48+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

13113 changes to a tool definition: 382 npm releases (136 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 12731 readings of hosted servers that found their tools changed; 70 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
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
| 2026-09-29 | `remote/com.handsforagents/hands` | 2026-09-29T003554078870 -> 2026-09-29T101509366088 | 4 changed | quiet |
| 2026-09-29 | `remote/io.github.digitalmentes7-maker/gobuy-product-trust` | 2026-09-29T003553473908 -> 2026-09-29T101504403041 | 1 added | quiet |
| 2026-09-29 | `remote/no.restplass/travel-search` | 2026-09-29T083035637477 -> 2026-09-29T101335944951 | 1 changed | quiet |
| 2026-09-29 | `remote/dk.afbudsrejser/travel-search` | 2026-09-29T083015874935 -> 2026-09-29T101311693931 | 1 changed | quiet |
| 2026-09-29 | `remote/se.sistaminuten/travel-search` | 2026-09-29T083025377391 -> 2026-09-29T101250350114 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-09-29T073400857436 -> 2026-09-29T101223131313 | 15 changed | review |
| 2026-09-29 | `remote/xyz.signomy/civitae` | 2026-09-29T082920984536 -> 2026-09-29T101212674002 | 1 changed, 2 added | quiet |
| 2026-09-29 | `remote/games.moddable.tools/moddable-games-tools` | 2026-09-29T073314905743 -> 2026-09-29T101147876438 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.steffanricardo/the-dutch-directory` | 2026-09-29T073306620345 -> 2026-09-29T101139866576 | 1 added | quiet |
| 2026-09-29 | `remote/io.github.Project-Gifted1/pg1-threat-intel` | 2026-09-27T124817890221 -> 2026-09-29T101121400254 | 7 changed | quiet |
| 2026-09-29 | `remote/es.cesaryague/paki-curator` | 2026-09-29T082825602947 -> 2026-09-29T101118147251 | 1 changed | quiet |
| 2026-09-29 | `remote/site.chatgpt.lorh89.the-knowledge-commons/evidence` | 2026-09-28T142250130796 -> 2026-09-29T101108748558 | 1 added | quiet |
| 2026-09-29 | `remote/com.talval/research` | 2026-09-29T082958904772 -> 2026-09-29T101103472496 | 2 changed | quiet |
| 2026-09-29 | `remote/app.saber.mcp/saber` | 2026-09-23T162803834025 -> 2026-09-29T101011640007 | 2 changed | quiet |
| 2026-09-29 | `remote/dev.benys/the-pit` | 2026-09-28T142119993154 -> 2026-09-29T101005423641 | 2 changed | quiet |
| 2026-09-29 | `remote/cheap.doc/mcp` | 2026-09-28T141831679171 -> 2026-09-29T100923036525 | 3 added | quiet |
| 2026-09-29 | `remote/io.github.toshihiroshishido/revenuescope-mcp` | 2026-09-28T104014835257 -> 2026-09-29T100911395934 | 1 changed | quiet |
| 2026-09-29 | `remote/co.marketmayhem/mcp` | 2026-09-28T170317566620 -> 2026-09-29T100841016284 | 1 changed | quiet |
| 2026-09-29 | `remote/com.movingplace/mcp` | 2026-09-29T082654798181 -> 2026-09-29T100829159435 | 16 removed | quiet |
| 2026-09-29 | `remote/estate.guthmann/mcp` | 2026-09-23T160714207240 -> 2026-09-29T100829431533 | 1 changed | quiet |
| 2026-09-29 | `remote/co.fastgpu/fastgpu` | 2026-09-28T072553827272 -> 2026-09-29T100827664981 | 1 changed | quiet |
| 2026-09-29 | `remote/app.apiguru/amazon-data` | 2026-09-27T134852961420 -> 2026-09-29T100750759506 | 4 changed | quiet |
| 2026-09-29 | `remote/com.focxle/b2b-agent-negotiation-governance` | 2026-09-28T141551264622 -> 2026-09-29T100652391674 | 1 changed | quiet |
| 2026-09-29 | `remote/xyz.getvia.app/via-network` | 2026-09-29T072622785567 -> 2026-09-29T100623534894 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.whiteknightonhorse/apibase` | 2026-09-29T082245665677 -> 2026-09-29T100609836687 | 4 added | quiet |
| 2026-09-29 | `remote/io.github.tettertotter/fundinglandscape` | 2026-09-29T082342730881 -> 2026-09-29T100608892016 | 2 changed | quiet |
| 2026-09-29 | `remote/com.focxle/afos` | 2026-09-27T065616767145 -> 2026-09-29T100606310295 | 1 changed | quiet |
| 2026-09-29 | `remote/de.nomado24/jobs` | 2026-09-23T162250587934 -> 2026-09-29T100547898691 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.JunHwan-Kwon/deepbom` | 2026-09-29T072636297804 -> 2026-09-29T100539904269 | 3 added | quiet |
| 2026-09-29 | `remote/cloud.dchub/mcp-server` | 2026-09-29T061615077258 -> 2026-09-29T100540237742 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.WellApp-ai/well-mcp` | 2026-09-29T003542328438 -> 2026-09-29T100510313102 | 4 changed | quiet |
| 2026-09-29 | `remote/net.aginx/aginxbrowser` | 2026-09-27T232540884284 -> 2026-09-29T100508795249 | 1 added | quiet |
| 2026-09-29 | `remote/io.github.JSONbored/metagraphed` | 2026-09-29T082209319092 -> 2026-09-29T100452668573 | 3 changed, 1 added, 242 removed (every tool) | quiet |
| 2026-09-29 | `remote/io.github.herve-coulon/tax-retirement` | 2026-09-29T072543704322 -> 2026-09-29T100450577396 | 1 changed | quiet |
| 2026-09-29 | `remote/com.uplika/uplika` | 2026-09-29T003531839396 -> 2026-09-29T100435219639 | 2 changed | quiet |
| 2026-09-29 | `remote/io.github.gosadu/loophole-tape` | 2026-09-29T061609015052 -> 2026-09-29T100427705309 | 4 changed | quiet |
| 2026-09-29 | `remote/io.pxl8/records` | 2026-09-24T201955758572 -> 2026-09-29T100425238960 | 1 changed | quiet |
| 2026-09-29 | `remote/com.googleapis.androidmanagement/mcp` | 2026-09-23T162158816570 -> 2026-09-29T100359173003 | 4 changed | quiet |
| 2026-09-29 | `remote/pw.algo.ai/agent-commons` | 2026-09-29T072420468736 -> 2026-09-29T100350386834 | 4 added | quiet |
| 2026-09-29 | `remote/io.github.odaiin/assetfare-bridge` | 2026-09-29T061604042711 -> 2026-09-29T100349110064 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.shibley/aidataparser` | 2026-09-27T065101775988 -> 2026-09-29T100330561671 | 1 added | quiet |
| 2026-09-29 | `remote/io.github.moonspacenow-tech/aicomglobal` | 2026-09-28T140907618124 -> 2026-09-29T100330356029 | 2 changed | quiet |
| 2026-09-29 | `remote/io.github.odaiin/assetfare` | 2026-09-29T061604416760 -> 2026-09-29T100320196206 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.faisal-maverick/aayat-ai` | 2026-09-29T074843438595 -> 2026-09-29T100208903118 | 6 changed | review |
| 2026-09-29 | `premiere-pro-mcp` | 1.18.5 -> 1.18.6 | 1 changed | quiet |
| 2026-09-29 | `remote/fi.akkilahdot/travel-search` | 2026-09-29T080505381454 -> 2026-09-29T083120282707 | 1 changed | quiet |
| 2026-09-29 | `remote/no.restplass/travel-search` | 2026-09-29T080035144972 -> 2026-09-29T083035637477 | 1 changed | quiet |
| 2026-09-29 | `remote/se.sistaminuten/travel-search` | 2026-09-29T080038352564 -> 2026-09-29T083025377391 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-29T080347917861 -> 2026-09-29T083023012540 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 9796 substantive, 3156 that changed only numbers (a catalogue counter ticking, a date), 161 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 7023 | 4048 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `caseyjhand.com` | 56 | 56 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| `sistaminuten.se` | 41 | 2 | 0 | 39 |
| `afbudsrejser.dk` | 40 | 2 | 0 | 38 |
| `akkilahdot.fi` | 40 | 2 | 0 | 38 |
| `restplass.no` | 40 | 2 | 0 | 38 |
| `socialloop.ai` | 40 | 40 | 0 | 0 |
| `fastmcp.app` | 29 | 29 | 0 | 0 |
| `dayze.com` | 28 | 28 | 0 | 0 |
| 1265 other operators | 2960 | 2771 | 181 | 8 |
