# MCP server tool changes

Last change observed 2026-09-27T11:45:37+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9409 npm servers from the official MCP registry (154 daily, the rest weekly) and 18576 hosted endpoints (daily).

11839 changes to a tool definition: 341 npm releases (95 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 11498 readings of hosted servers that found their tools changed; 8 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-09-27 | `remote/fi.akkilahdot/travel-search` | 2026-09-27T111140568608 -> 2026-09-27T114538656141 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-27T111058411751 -> 2026-09-27T114445125418 | 1 changed | quiet |
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
| 2026-09-27 | `remote/io.github.si-imtiaz/leadquasar` | 2026-09-27T104954171157 -> 2026-09-27T110715646848 | 2 changed | quiet |
| 2026-09-27 | `remote/com.thisisdelightful/games-research-starter-pack` | 2026-09-25T120159846589 -> 2026-09-27T110608783713 | 1 changed | quiet |
| 2026-09-27 | `remote/io.datascoop/datascoop` | 2026-09-23T162358919503 -> 2026-09-27T110507118478 | 1 changed | quiet |
| 2026-09-27 | `remote/com.googleapis.compute/mcp` | 2026-09-27T071810536729 -> 2026-09-27T110451807745 | 10 changed | quiet |
| 2026-09-27 | `remote/io.github.closelookventure/closelook-intelligence` | 2026-09-23T160325816552 -> 2026-09-27T110450557433 | 26 changed (every tool) | quiet |
| 2026-09-27 | `remote/io.github.odaiin/assetfare-bridge` | 2026-09-27T102931328860 -> 2026-09-27T110246925232 | 2 changed | quiet |
| 2026-09-27 | `remote/build.exascale/osint` | 2026-09-23T162208031579 -> 2026-09-27T110225260588 | 1 changed, 2 added | quiet |
| 2026-09-27 | `remote/io.github.odaiin/assetfare` | 2026-09-27T102929299656 -> 2026-09-27T110219700960 | 2 changed | quiet |
| 2026-09-27 | `remote/app.agentbit/mcp` | 2026-09-27T103005104995 -> 2026-09-27T110202291568 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.onetapstudiogames/1f3d9` | 2026-09-26T113236768415 -> 2026-09-27T110038637995 | 1 changed | quiet |
| 2026-09-27 | `remote/se.sistaminuten/travel-search` | 2026-09-27T072925971995 -> 2026-09-27T105503526461 | 1 changed | quiet |
| 2026-09-27 | `remote/com.blitzreels/blitzreels` | 2026-09-26T045429420413 -> 2026-09-27T105449152814 | 4 changed | quiet |
| 2026-09-27 | `remote/com.zinvyl/marketplace` | 2026-09-24T120516307990 -> 2026-09-27T105441795272 | 3 changed | quiet |
| 2026-09-27 | `remote/fi.akkilahdot/travel-search` | 2026-09-27T072849092270 -> 2026-09-27T105415349612 | 1 changed | quiet |
| 2026-09-27 | `remote/com.goedvps.app.wodan-posture/wodan-posture` | 2026-09-26T114330154990 -> 2026-09-27T105412091435 | 2 added | quiet |
| 2026-09-27 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-09-26T192600259381 -> 2026-09-27T105345940463 | 1 changed | quiet |
| 2026-09-27 | `remote/no.restplass/travel-search` | 2026-09-27T072527454659 -> 2026-09-27T105330730752 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-27T072802286788 -> 2026-09-27T105330519591 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.bartosz-kuc/skanfirmy` | 2026-09-26T192557516840 -> 2026-09-27T105328061676 | 6 changed | quiet |
| 2026-09-27 | `remote/ltd.qianyuan/qy-stream` | 2026-09-27T055051300024 -> 2026-09-27T105329994710 | 2 added | quiet |
| 2026-09-27 | `remote/ltd.qianyuan/qy-evolution` | 2026-09-27T055049152130 -> 2026-09-27T105328051207 | 2 added | quiet |
| 2026-09-27 | `remote/xyz.pokeka/card-prices` | 2026-09-23T160900970270 -> 2026-09-27T105318667512 | 1 changed | quiet |
| 2026-09-27 | `remote/dk.afbudsrejser/travel-search` | 2026-09-27T072507093949 -> 2026-09-27T105315316322 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.moralito311-andr/andreax` | 2026-09-27T072714833709 -> 2026-09-27T105310222819 | 4 added | quiet |
| 2026-09-27 | `remote/io.github.taux-io/twse-mcp` | 2026-09-26T192552266118 -> 2026-09-27T105258285288 | 9 added, 9 removed | quiet |
| 2026-09-27 | `remote/xyz.trusteed/mcp-gateway` | 2026-09-26T192552233143 -> 2026-09-27T105257719831 | 5 changed | quiet |
| 2026-09-27 | `remote/com.luxurylodgingpm.stay/luxury-lodging` | 2026-09-26T192549290732 -> 2026-09-27T105232328739 | 1 changed | quiet |
| 2026-09-27 | `remote/com.odilelabs/odile` | 2026-09-26T132452683544 -> 2026-09-27T105231289516 | 3 changed | quiet |
| 2026-09-27 | `remote/io.github.wygogogo19/robotbase-mcp` | 2026-09-27T065854028951 -> 2026-09-27T105208768457 | 4 changed, 3 added | quiet |
| 2026-09-27 | `remote/app.sallim/korea-realty` | 2026-09-27T055157481925 -> 2026-09-27T105159627535 | 1 added | quiet |
| 2026-09-27 | `remote/io.ppc/postclick-landing-page-cro` | 2026-09-23T162719909813 -> 2026-09-27T105139512025 | 1 changed, 1 added | quiet |
| 2026-09-27 | `remote/kr.gronox/finbridge` | 2026-09-25T120258350349 -> 2026-09-27T105108180746 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 8684 substantive, 3086 that changed only numbers (a catalogue counter ticking, a date), 69 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 6996 | 4021 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `caseyjhand.com` | 55 | 55 | 0 | 0 |
| `daedalmap.com` | 47 | 47 | 0 | 0 |
| `sistaminuten.se` | 19 | 2 | 0 | 17 |
| `afbudsrejser.dk` | 18 | 2 | 0 | 16 |
| `akkilahdot.fi` | 18 | 2 | 0 | 16 |
| `assetfare.dev` | 18 | 18 | 0 | 0 |
| `dayze.com` | 18 | 18 | 0 | 0 |
| `restplass.no` | 18 | 2 | 0 | 16 |
| `socialloop.ai` | 18 | 18 | 0 | 0 |
| 921 other operators | 1849 | 1734 | 111 | 4 |
