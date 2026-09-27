# MCP server tool changes

Last change observed 2026-09-27T11:12:31+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9409 npm servers from the official MCP registry (154 daily, the rest weekly) and 18576 hosted endpoints (daily).

11821 changes to a tool definition: 341 npm releases (95 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 11480 readings of hosted servers that found their tools changed; 8 where `heldfast wrap --drift graded` would refuse something.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
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
| 2026-09-27 | `remote/org.golfcore/golfcore` | 2026-09-23T160710444414 -> 2026-09-27T105106382893 | 1 changed, 2 added | quiet |
| 2026-09-27 | `remote/io.github.koraykoylu/ibanchecker-mcp` | 2026-09-27T065750569921 -> 2026-09-27T105124217326 | 5 changed (every tool) | quiet |
| 2026-09-27 | `remote/com.handsforagents/hands` | 2026-09-26T114026136754 -> 2026-09-27T105101970572 | 3 changed | quiet |
| 2026-09-27 | `remote/ch.blust/mental-model` | 2026-09-27T065917757966 -> 2026-09-27T105035462810 | 1 changed | quiet |
| 2026-09-27 | `remote/org.billcommons/bill-commons` | 2026-09-23T160644465302 -> 2026-09-27T105031959011 | 1 changed | quiet |
| 2026-09-27 | `remote/dev.workers.mars-economic.mars-economic-agent-gateway/mars-economic` | 2026-09-23T160630066365 -> 2026-09-27T105013835883 | 1 changed | quiet |
| 2026-09-27 | `remote/ai.greenlandai/greenlandai` | 2026-09-24T202320972781 -> 2026-09-27T105003763378 | 2 changed | quiet |
| 2026-09-27 | `remote/io.github.si-imtiaz/leadquasar` | 2026-09-23T202129136331 -> 2026-09-27T104954171157 | 2 changed | quiet |
| 2026-09-27 | `remote/fr.humanmirror/x402` | 2026-09-26T113855385003 -> 2026-09-27T104939185500 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.Its-fortunatefolly/hubvibe` | 2026-09-27T055039945416 -> 2026-09-27T104938926577 | 5 added | quiet |
| 2026-09-27 | `remote/io.github.simonplmak-cloud/hkex-filings` | 2026-09-23T160559230343 -> 2026-09-27T104935711447 | 3 changed, 1 added (every tool) | quiet |
| 2026-09-27 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-09-26T231108363171 -> 2026-09-27T103811255312 | 1 added | quiet |
| 2026-09-27 | `remote/io.github.samuelzcom/chauffeur-booking` | 2026-09-27T065953671423 -> 2026-09-27T103718621082 | 1 changed | quiet |
| 2026-09-27 | `remote/co.radicadouno/mcp` | 2026-09-26T231102111308 -> 2026-09-27T103536548487 | 1 changed | quiet |
| 2026-09-27 | `remote/net.praegant/landhaus` | 2026-09-26T132430904924 -> 2026-09-27T103533048082 | 3 changed | quiet |
| 2026-09-27 | `remote/com.freqblog/music-metadata` | 2026-09-27T065800378189 -> 2026-09-27T103451682759 | 2 changed | quiet |
| 2026-09-27 | `remote/io.companygraph/mental-model` | 2026-09-27T065746042918 -> 2026-09-27T103433449815 | 1 changed | quiet |
| 2026-09-27 | `remote/com.agenttrafficlab/atl` | 2026-09-27T065728075174 -> 2026-09-27T103411373079 | 3 changed (every tool) | quiet |
