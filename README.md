# MCP server tool changes

Last change observed 2026-09-27T12:32:26+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9409 npm servers from the official MCP registry (154 daily, the rest weekly) and 18576 hosted endpoints (daily).

11871 changes to a tool definition: 342 npm releases (96 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 11529 readings of hosted servers that found their tools changed; 9 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-09-27 | `remote/se.sistaminuten/travel-search` | 2026-09-27T120949381978 -> 2026-09-27T123227188781 | 1 changed | quiet |
| 2026-09-27 | `remote/no.restplass/travel-search` | 2026-09-27T121157865593 -> 2026-09-27T123151936152 | 1 changed | quiet |
| 2026-09-27 | `remote/dk.afbudsrejser/travel-search` | 2026-09-27T121139321284 -> 2026-09-27T123133238824 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-09-27T055156362632 -> 2026-09-27T123047177343 | 15 changed | review |
| 2026-09-27 | `remote/fi.akkilahdot/travel-search` | 2026-09-27T121222018818 -> 2026-09-27T123025860978 | 1 changed | quiet |
| 2026-09-27 | `remote/app.sallim/korea-realty` | 2026-09-27T121011898111 -> 2026-09-27T123008016036 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-27T121126621324 -> 2026-09-27T122921057598 | 1 changed | quiet |
| 2026-09-27 | `remote/com.hireahelper/mcp` | 2026-09-27T072522159081 -> 2026-09-27T122641790473 | 16 added | quiet |
| 2026-09-27 | `remote/cloud.theprotocol/registry` | 2026-09-24T115815768089 -> 2026-09-27T122338300072 | 32 changed | quiet |
| 2026-09-27 | `remote/app.agentbit/mcp` | 2026-09-27T110202291568 -> 2026-09-27T122001056872 | 1 changed | quiet |
| 2026-09-27 | `remote/fi.akkilahdot/travel-search` | 2026-09-27T114538656141 -> 2026-09-27T121222018818 | 1 changed | quiet |
| 2026-09-27 | `remote/no.restplass/travel-search` | 2026-09-27T113235843857 -> 2026-09-27T121157865593 | 1 changed | quiet |
| 2026-09-27 | `remote/dk.afbudsrejser/travel-search` | 2026-09-27T113217089744 -> 2026-09-27T121139321284 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-27T114445125418 -> 2026-09-27T121126621324 | 1 changed | quiet |
| 2026-09-27 | `remote/app.sallim/korea-realty` | 2026-09-27T105159627535 -> 2026-09-27T121011898111 | 1 changed | quiet |
| 2026-09-27 | `remote/se.sistaminuten/travel-search` | 2026-09-27T113300535003 -> 2026-09-27T120949381978 | 1 changed | quiet |
| 2026-09-27 | `remote/dev.mcphost/mcphost` | 2026-09-27T055017208893 -> 2026-09-27T120856254978 | 8 added | quiet |
| 2026-09-27 | `remote/com.rekvira/rekvira` | 2026-09-25T120248613186 -> 2026-09-27T120818450649 | 1 changed | quiet |
| 2026-09-27 | `remote/dev.homespun/homespun` | 2026-09-23T162531147405 -> 2026-09-27T120629111412 | 1 changed, 1 added | quiet |
| 2026-09-27 | `remote/io.github.f-tiger/hvac-btu-heat-klimaanlage` | 2026-09-23T162511838013 -> 2026-09-27T120608630035 | 1 removed | quiet |
| 2026-09-27 | `remote/io.github.f-tiger/getecoback-climate-weather` | 2026-09-23T160432235741 -> 2026-09-27T120559019796 | 1 removed | quiet |
| 2026-09-27 | `remote/ai.eykon/intelligence` | 2026-09-27T065413015563 -> 2026-09-27T120512587418 | 2 added | quiet |
| 2026-09-27 | `remote/com.datailo/datailo` | 2026-09-26T045035686109 -> 2026-09-27T120505620402 | 1 changed | quiet |
| 2026-09-27 | `remote/com.googleapis.compute/mcp` | 2026-09-27T112429980414 -> 2026-09-27T120420331937 | 10 changed | quiet |
| 2026-09-27 | `remote/io.github.f-tiger/getecoback-raumklima` | 2026-09-23T160547733209 -> 2026-09-27T120336292428 | 1 removed | quiet |
| 2026-09-27 | `remote/ai.smry.r/smry-product` | 2026-09-23T160245033955 -> 2026-09-27T120320091344 | 1 changed | quiet |
| 2026-09-27 | `remote/jp.sealgate/sealgate` | 2026-09-24T115818003495 -> 2026-09-27T120316563652 | 12 changed, 9 added | quiet |
| 2026-09-27 | `remote/io.github.tettertotter/fundinglandscape` | 2026-09-27T112545743772 -> 2026-09-27T120249892074 | 2 changed | quiet |
| 2026-09-27 | `remote/io.github.gosadu/loophole-tape` | 2026-09-27T103035361772 -> 2026-09-27T115937597136 | 9 changed | quiet |
| 2026-09-27 | `remote/com.allratestoday/mcp` | 2026-09-27T065147897519 -> 2026-09-27T115909403121 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.0xinsider/mcp` | 2026-09-26T192518367335 -> 2026-09-27T115903506735 | 2 changed | quiet |
| 2026-09-27 | `remote/fi.akkilahdot/travel-search` | 2026-09-27T111140568608 -> 2026-09-27T114538656141 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-27T111058411751 -> 2026-09-27T114445125418 | 1 changed | quiet |
| 2026-09-27 | `@togglhq/mcp` | 1.11.65 -> 1.11.66 | 10 changed, 2 added, 1 removed | quiet |
| 2026-09-27 | `remote/se.sistaminuten/travel-search` | 2026-09-27T111228858531 -> 2026-09-27T113300535003 | 1 changed | quiet |
| 2026-09-27 | `remote/no.restplass/travel-search` | 2026-09-27T111233244543 -> 2026-09-27T113235843857 | 1 changed | quiet |
| 2026-09-27 | `remote/dk.afbudsrejser/travel-search` | 2026-09-27T111215250704 -> 2026-09-27T113217089744 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.moralito311-andr/andreax` | 2026-09-27T105310222819 -> 2026-09-27T113051434838 | 2 changed, 1 added | quiet |
| 2026-09-27 | `remote/com.tkawen/intelligence-gateway` | 2026-09-27T110917455481 -> 2026-09-27T112844030598 | 1 changed | quiet |
| 2026-09-27 | `remote/net.praegant/landhaus` | 2026-09-27T103533048082 -> 2026-09-27T112820497695 | 2 changed | quiet |
| 2026-09-27 | `remote/io.github.Kopaev/openvan-travel` | 2026-09-23T160600643129 -> 2026-09-27T112815669662 | 4 added | quiet |
| 2026-09-27 | `remote/io.github.SidneyBissoli/ibge-br-mcp` | 2026-09-23T160603025805 -> 2026-09-27T112658616036 | 23 changed (every tool) | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/ted-eu` | 2026-09-26T113833149740 -> 2026-09-27T112632550515 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/take-the-meeting` | 2026-09-26T044908359112 -> 2026-09-27T112632319862 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.tettertotter/fundinglandscape` | 2026-09-27T103244029495 -> 2026-09-27T112545743772 | 2 changed | quiet |
| 2026-09-27 | `remote/com.llmotions.farm/gpt-5-6-sol-agent` | 2026-09-23T160353231485 -> 2026-09-27T112512155977 | 1 changed | quiet |
| 2026-09-27 | `remote/com.googleapis.compute/mcp` | 2026-09-27T110451807745 -> 2026-09-27T112429980414 | 10 changed | quiet |
| 2026-09-27 | `remote/online.x-402/mcp` | 2026-09-26T044708544922 -> 2026-09-27T112406386959 | 5 added | quiet |
| 2026-09-27 | `remote/io.github.moonspacenow-tech/aicomglobal` | 2026-09-27T102915928698 -> 2026-09-27T112126496078 | 2 changed | quiet |
| 2026-09-27 | `remote/com.agiscorecard/agi-scorecard` | 2026-09-27T065244321759 -> 2026-09-27T112114926338 | 1 changed | quiet |
| 2026-09-27 | `remote/no.restplass/travel-search` | 2026-09-27T105330730752 -> 2026-09-27T111233244543 | 1 changed | quiet |
| 2026-09-27 | `remote/se.sistaminuten/travel-search` | 2026-09-27T105503526461 -> 2026-09-27T111228858531 | 1 changed | quiet |
| 2026-09-27 | `remote/dk.afbudsrejser/travel-search` | 2026-09-27T105315316322 -> 2026-09-27T111215250704 | 1 changed | quiet |
| 2026-09-27 | `remote/fi.akkilahdot/travel-search` | 2026-09-27T105415349612 -> 2026-09-27T111140568608 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-27T105330519591 -> 2026-09-27T111058411751 | 1 changed | quiet |
| 2026-09-27 | `remote/ai.sendraven/mcp` | 2026-09-23T162806721720 -> 2026-09-27T110926583510 | 28 changed | quiet |
| 2026-09-27 | `remote/com.tkawen/intelligence-gateway` | 2026-09-27T072355599213 -> 2026-09-27T110917455481 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.toshihiroshishido/revenuescope-mcp` | 2026-09-27T070104507147 -> 2026-09-27T110858802819 | 4 changed, 1 added | quiet |
| 2026-09-27 | `remote/io.companygraph/mental-model` | 2026-09-27T103433449815 -> 2026-09-27T110746651162 | 1 changed | quiet |
| 2026-09-27 | `remote/ch.blust/mental-model` | 2026-09-27T105035462810 -> 2026-09-27T110740919168 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 8706 substantive, 3088 that changed only numbers (a catalogue counter ticking, a date), 77 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 6996 | 4021 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `caseyjhand.com` | 55 | 55 | 0 | 0 |
| `daedalmap.com` | 47 | 47 | 0 | 0 |
| `sistaminuten.se` | 21 | 2 | 0 | 19 |
| `afbudsrejser.dk` | 20 | 2 | 0 | 18 |
| `akkilahdot.fi` | 20 | 2 | 0 | 18 |
| `restplass.no` | 20 | 2 | 0 | 18 |
| `socialloop.ai` | 20 | 20 | 0 | 0 |
| `assetfare.dev` | 18 | 18 | 0 | 0 |
| `dayze.com` | 18 | 18 | 0 | 0 |
| 924 other operators | 1871 | 1754 | 113 | 4 |
