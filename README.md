# MCP server tool changes

Last change observed 2026-09-27T07:29:24+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9409 npm servers from the official MCP registry (154 daily, the rest weekly) and 18576 hosted endpoints (daily).

11734 releases that changed a tool definition (11488 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)); 8 where `heldfast wrap --drift graded` would refuse something.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-09-27 | `remote/se.sistaminuten/travel-search` | 2026-09-27T070522715406 -> 2026-09-27T072925971995 | 1 changed | quiet |
| 2026-09-27 | `remote/fi.akkilahdot/travel-search` | 2026-09-27T070036345428 -> 2026-09-27T072849092270 | 1 changed | quiet |
| 2026-09-27 | `remote/ai.susurration/playground` | 2026-09-23T160945381300 -> 2026-09-27T072816119035 | 2 changed | quiet |
| 2026-09-27 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-27T065948694533 -> 2026-09-27T072802286788 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.moralito311-andr/andreax` | 2026-09-27T055048143253 -> 2026-09-27T072714833709 | 1 changed, 1 added | quiet |
| 2026-09-27 | `remote/ru.activatedai/activated-ai` | 2026-09-23T160802595323 -> 2026-09-27T072629517842 | 4 changed (every tool) | quiet |
| 2026-09-27 | `remote/no.restplass/travel-search` | 2026-09-27T070019533370 -> 2026-09-27T072527454659 | 1 changed | quiet |
| 2026-09-27 | `remote/com.hireahelper/mcp` | 2026-09-27T065729485134 -> 2026-09-27T072522159081 | 16 removed | quiet |
| 2026-09-27 | `remote/dk.afbudsrejser/travel-search` | 2026-09-27T070001965439 -> 2026-09-27T072507093949 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.alexar76/aimarket-hub` | 2026-09-26T045245801190 -> 2026-09-27T072427919041 | 1 changed | quiet |
| 2026-09-27 | `remote/com.tkawen/intelligence-gateway` | 2026-09-27T065852137694 -> 2026-09-27T072355599213 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/yelp` | 2026-09-24T202350967733 -> 2026-09-27T072324912937 | 4 changed | quiet |
| 2026-09-27 | `remote/net.isitdns/isitdns` | 2026-09-27T055040793234 -> 2026-09-27T072321809023 | 9 changed (every tool) | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/statfin-fi` | 2026-09-26T044907755683 -> 2026-09-27T072247321369 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/eurostat` | 2026-09-26T044840850820 -> 2026-09-27T072219837275 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/animequotes` | 2026-09-26T044821955720 -> 2026-09-27T072201306488 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/alphafold` | 2026-09-26T044821592891 -> 2026-09-27T072200275326 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.tettertotter/fundinglandscape` | 2026-09-26T231040291493 -> 2026-09-27T072155625546 | 2 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/waqi` | 2026-09-24T211856417699 -> 2026-09-27T072056149425 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/wa-dmv` | 2026-09-24T211856186528 -> 2026-09-27T072056001814 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/w3c` | 2026-09-26T044935310580 -> 2026-09-27T072055964364 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.pipeworx-io/vizier` | 2026-09-26T044935347757 -> 2026-09-27T072055854618 | 4 changed | quiet |
| 2026-09-27 | `remote/io.github.Shuaigle/roomnology-forum` | 2026-09-23T160340162808 -> 2026-09-27T071928456884 | 3 changed | quiet |
| 2026-09-27 | `remote/com.googleapis.compute/mcp` | 2026-09-27T065358315220 -> 2026-09-27T071810536729 | 10 changed | quiet |
| 2026-09-27 | `remote/ltd.branddesign/commerce` | 2026-09-23T162329921136 -> 2026-09-27T071748235311 | 1 changed | quiet |
| 2026-09-27 | `remote/io.tokenbooks/tokenbooks` | 2026-09-26T192530822088 -> 2026-09-27T071706944309 | 1 changed | quiet |
| 2026-09-27 | `remote/com.prereason/mcp` | 2026-09-25T115952944488 -> 2026-09-27T071702103363 | 2 changed | quiet |
| 2026-09-27 | `remote/io.github.eamwhite1/xrpl-referee` | 2026-09-23T161043385389 -> 2026-09-27T070532236835 | 3 changed | quiet |
| 2026-09-27 | `remote/se.sistaminuten/travel-search` | 2026-09-27T055051773635 -> 2026-09-27T070522715406 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-09-23T161028179486 -> 2026-09-27T070512810802 | 2 changed | quiet |
| 2026-09-27 | `remote/com.entangleeq/pay-transparency` | 2026-09-23T161025505613 -> 2026-09-27T070508873658 | 1 changed | quiet |
| 2026-09-27 | `remote/com.viraloutliers/viral-outliers` | 2026-09-23T161008781610 -> 2026-09-27T070444449734 | 3 changed, 5 added | quiet |
| 2026-09-27 | `remote/com.thepantrybutler/pantry` | 2026-09-24T202614190907 -> 2026-09-27T070408763278 | 6 changed (every tool) | quiet |
| 2026-09-27 | `remote/com.submitmap/directory` | 2026-09-23T160944077098 -> 2026-09-27T070357628448 | 4 changed | quiet |
| 2026-09-27 | `remote/com.sssnack/sssnack` | 2026-09-24T120254219101 -> 2026-09-27T070355018966 | 5 changed | quiet |
| 2026-09-27 | `remote/com.narrowhighway/concordance` | 2026-09-23T160839259188 -> 2026-09-27T070220275005 | 1 added | quiet |
| 2026-09-27 | `remote/io.github.HuangGoodmanAgency/edgar-and-edgarette` | 2026-09-23T160848597060 -> 2026-09-27T070149186556 | 2 added | quiet |
| 2026-09-27 | `remote/com.zoningsignal/observatory` | 2026-09-23T163002313329 -> 2026-09-27T070127155902 | 17 changed | quiet |
| 2026-09-27 | `remote/io.github.corsur/swarm-tips` | 2026-09-23T160758183125 -> 2026-09-27T070123321373 | 2 changed | quiet |
| 2026-09-27 | `remote/co.schoolscope/mcp` | 2026-09-23T160751031598 -> 2026-09-27T070108761322 | 5 changed | quiet |
| 2026-09-27 | `remote/io.github.toshihiroshishido/revenuescope-mcp` | 2026-09-23T160748554260 -> 2026-09-27T070104507147 | 3 changed | quiet |
| 2026-09-27 | `remote/ai.intuitek.the-stall/the-stall` | 2026-09-23T160808890814 -> 2026-09-27T070055759725 | 1 changed | quiet |
| 2026-09-27 | `remote/com.tapeperp/tape` | 2026-09-23T160805584162 -> 2026-09-27T070050478995 | 1 changed | quiet |
| 2026-09-27 | `remote/io.szum/charts` | 2026-09-23T160805981602 -> 2026-09-27T070049346392 | 9 changed, 3 added, 2 removed | quiet |
| 2026-09-27 | `remote/services.ottoai/otto` | 2026-09-24T202415306828 -> 2026-09-27T070047043550 | 1 removed | quiet |
| 2026-09-27 | `remote/swiss.openhelvetia/gateway` | 2026-09-23T160737722702 -> 2026-09-27T070046262387 | 3 changed | quiet |
| 2026-09-27 | `remote/fi.akkilahdot/travel-search` | 2026-09-27T055104414145 -> 2026-09-27T070036345428 | 1 changed | quiet |
| 2026-09-27 | `remote/dev.zhiyong/knowledge-graph` | 2026-09-23T163153105904 -> 2026-09-27T070033816806 | 3 changed | quiet |
| 2026-09-27 | `remote/ai.verticalmarketplace/vertical-marketplace` | 2026-09-23T162922827562 -> 2026-09-27T070025686219 | 2 changed | quiet |
| 2026-09-27 | `remote/com.statementtobudget.www/bank-statement-converter` | 2026-09-23T163144006667 -> 2026-09-27T070021242268 | 1 changed | quiet |
| 2026-09-27 | `remote/no.restplass/travel-search` | 2026-09-27T055159898393 -> 2026-09-27T070019533370 | 1 changed | quiet |
| 2026-09-27 | `remote/dk.afbudsrejser/travel-search` | 2026-09-27T055158707169 -> 2026-09-27T070001965439 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.ogasurfproject-jpg/horizon-shield-webmcp` | 2026-09-23T163110453750 -> 2026-09-27T065956129605 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.nsudhanva/sudhanva-public-profile` | 2026-09-23T162901156250 -> 2026-09-27T065955986154 | 3 changed (every tool) | quiet |
| 2026-09-27 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-27T055102628696 -> 2026-09-27T065948694533 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.samuelzcom/chauffeur-booking` | 2026-09-23T202316499859 -> 2026-09-27T065953671423 | 2 changed | quiet |
| 2026-09-27 | `remote/systems.phion/evidence-engine` | 2026-09-23T160716090437 -> 2026-09-27T065947074237 | 1 changed, 9 added | quiet |
| 2026-09-27 | `remote/com.underpricedai/underpriced-ai` | 2026-09-23T163055287588 -> 2026-09-27T065944891426 | 3 changed | quiet |
| 2026-09-27 | `remote/com.tradeassi/mcp` | 2026-09-23T163050285508 -> 2026-09-27T065940439447 | 1 changed | quiet |
| 2026-09-27 | `remote/me.sudhanva/public-profile` | 2026-09-23T163019564669 -> 2026-09-27T065921173237 | 3 changed (every tool) | quiet |
