# MCP server tool changes

Last change observed 2026-09-29T13:18:01+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

13223 changes to a tool definition: 384 npm releases (138 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 12839 readings of hosted servers that found their tools changed; 77 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-09-29 | `remote/no.restplass/travel-search` | 2026-09-29T113446824575 -> 2026-09-29T131803368376 | 1 changed | quiet |
| 2026-09-29 | `remote/com.youspot/youspot` | 2026-09-29T061642095763 -> 2026-09-29T131739702093 | 1 changed | quiet |
| 2026-09-29 | `remote/dk.afbudsrejser/travel-search` | 2026-09-29T113428746182 -> 2026-09-29T131739584243 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.Fizzl13/x402-doctor` | 2026-09-28T170424616410 -> 2026-09-29T131734183659 | 2 added | review |
| 2026-09-29 | `remote/com.zernote/zernote` | 2026-09-23T161046153713 -> 2026-09-29T131732134286 | 3 added | quiet |
| 2026-09-29 | `remote/com.zaimhub/catalog` | 2026-09-23T161045544767 -> 2026-09-29T131732362389 | 1 changed | quiet |
| 2026-09-29 | `remote/se.sistaminuten/travel-search` | 2026-09-29T113551744770 -> 2026-09-29T131719853984 | 1 changed | quiet |
| 2026-09-29 | `remote/dog.swoleeswoge/swogeagentic` | 2026-09-29T061658505250 -> 2026-09-29T131640395061 | 1 changed | quiet |
| 2026-09-29 | `remote/ru.zavod-stanki/cnc-catalog` | 2026-09-24T202805671044 -> 2026-09-29T131633404521 | 1 changed | quiet |
| 2026-09-29 | `remote/ru.zavod-stanki/cnc-catalog.1` | 2026-09-24T202530104515 -> 2026-09-29T131625624730 | 1 changed | quiet |
| 2026-09-29 | `remote/cc.thecolony/mcp-server` | 2026-09-27T195348518701 -> 2026-09-29T131612193027 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.Lorenzino69/easypdf` | 2026-09-23T162939147170 -> 2026-09-29T131608407530 | 1 added | quiet |
| 2026-09-29 | `remote/fi.akkilahdot/travel-search` | 2026-09-29T113456639943 -> 2026-09-29T131600819332 | 1 changed | quiet |
| 2026-09-29 | `remote/com.ai2fin/ai2fin-tax-mcp` | 2026-09-24T120257782325 -> 2026-09-29T131558950969 | 4 changed | quiet |
| 2026-09-29 | `remote/ru.vedarai/mcp` | 2026-09-26T114322471057 -> 2026-09-29T131547806736 | 1 changed | quiet |
| 2026-09-29 | `remote/com.straelo/relay` | 2026-09-29T061647472946 -> 2026-09-29T131544713038 | 2 added | quiet |
| 2026-09-29 | `remote/com.swarmmemo/bulletin` | 2026-09-29T073748253870 -> 2026-09-29T131523635064 | 2 changed, 4 added | review |
| 2026-09-29 | `remote/com.ribqa/sentinel-aleph` | 2026-09-29T075705509421 -> 2026-09-29T131511619142 | 1 changed, 2 added | quiet |
| 2026-09-29 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-29T113414037706 -> 2026-09-29T131509507177 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.cloakmaster/pact0` | 2026-09-26T114303769435 -> 2026-09-29T131504939948 | 7 changed, 1 added | quiet |
| 2026-09-29 | `remote/com.seqbench/workbench` | 2026-09-27T055102147697 -> 2026-09-29T131458791967 | 2 changed | quiet |
| 2026-09-29 | `remote/ai.agentlookups/counterscript` | 2026-09-29T101812105351 -> 2026-09-29T131448464537 | 1 changed | quiet |
| 2026-09-29 | `remote/com.remoshift/jobs` | 2026-09-29T113332718299 -> 2026-09-29T131439668408 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.Payotte-com/payotte-mcp` | 2026-09-29T073011308747 -> 2026-09-29T131433114437 | 2 changed | quiet |
| 2026-09-29 | `remote/ai.agentlookups/overassessed` | 2026-09-28T104150749622 -> 2026-09-29T131405459899 | 1 changed | quiet |
| 2026-09-29 | `remote/md.mostlyright/datasets` | 2026-09-23T160647184648 -> 2026-09-29T131359553459 | 1 changed | quiet |
| 2026-09-29 | `remote/com.rekvira/rekvira` | 2026-09-27T153025862877 -> 2026-09-29T131302412020 | 1 changed | quiet |
| 2026-09-29 | `remote/com.productclank/productclank` | 2026-09-23T160744142835 -> 2026-09-29T131256862762 | 4 changed, 2 added | quiet |
| 2026-09-29 | `remote/ai.normhyra/normhyra` | 2026-09-23T160601506727 -> 2026-09-29T131249173478 | 4 changed | quiet |
| 2026-09-29 | `remote/com.lightbringer/connector` | 2026-09-23T162702748075 -> 2026-09-29T131233650861 | 2 changed, 3 added | quiet |
| 2026-09-29 | `remote/com.jobmojito/jobmojito` | 2026-09-28T103956110264 -> 2026-09-29T131225180911 | 2 changed | quiet |
| 2026-09-29 | `remote/com.avokata/avokata` | 2026-09-28T141824941506 -> 2026-09-29T131225747898 | 1 changed, 6 added | quiet |
| 2026-09-29 | `remote/io.github.digitalmentes7-maker/gobuy-product-trust` | 2026-09-29T101504403041 -> 2026-09-29T131211615198 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.CoinRithm/mcp-trading` | 2026-09-29T072751138400 -> 2026-09-29T131157402106 | 2 changed, 1 added | quiet |
| 2026-09-29 | `remote/com.dexpaprika/dexpaprika` | 2026-09-28T141814849349 -> 2026-09-29T131207540205 | 1 added | quiet |
| 2026-09-29 | `remote/com.lucyesl/jobs` | 2026-09-23T162624845701 -> 2026-09-29T131137161446 | 7 changed (every tool) | quiet |
| 2026-09-29 | `remote/gr.bestprice/mcp` | 2026-09-26T045024148763 -> 2026-09-29T131133115952 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.kylehawke-stack/locationlists` | 2026-09-29T113049878992 -> 2026-09-29T131118097731 | 3 changed | review |
| 2026-09-29 | `remote/net.isitdns/isitdns` | 2026-09-29T003546191721 -> 2026-09-29T131028187375 | 7 changed, 5 removed (every tool) | quiet |
| 2026-09-29 | `remote/io.github.tettertotter/fundinglandscape` | 2026-09-29T112822000464 -> 2026-09-29T130912588951 | 2 changed | quiet |
| 2026-09-29 | `remote/dev.workers.bhazarstudio.datoqa/historical-exchange-rates` | 2026-09-29T003550843200 -> 2026-09-29T130859500756 | 1 added | quiet |
| 2026-09-29 | `remote/com.cymetica/event-trader-research` | 2026-09-28T170308177478 -> 2026-09-29T130854900369 | 8 added | quiet |
| 2026-09-29 | `remote/ai.agentlookups/groundtruth` | 2026-09-23T162412396795 -> 2026-09-29T130853671615 | 3 changed (every tool) | quiet |
| 2026-09-29 | `remote/ai.councilof/gspc` | 2026-09-29T072508882876 -> 2026-09-29T130834345005 | 1 changed | quiet |
| 2026-09-29 | `remote/dev.workers.bhazarstudio.datoqa/datoqa` | 2026-09-29T003536520825 -> 2026-09-29T130832292806 | 2 added | quiet |
| 2026-09-29 | `remote/com.cymetica/event-trader-mcp` | 2026-09-28T170307802290 -> 2026-09-29T130825970882 | 10 added | quiet |
| 2026-09-29 | `remote/io.github.CSOAI-ORG/gspc` | 2026-09-29T072740277484 -> 2026-09-29T130820430378 | 1 changed | quiet |
| 2026-09-29 | `remote/com.compensationprofessional/discovery` | 2026-09-29T072731107414 -> 2026-09-29T130814330612 | 2 changed | quiet |
| 2026-09-29 | `remote/com.campiamo/campsites` | 2026-09-28T170314634041 -> 2026-09-29T130811228156 | 1 changed | quiet |
| 2026-09-29 | `remote/com.birkinbagstock/mcp` | 2026-09-23T160315096428 -> 2026-09-29T130800705848 | 4 added | quiet |
| 2026-09-29 | `remote/ltd.branddesign/commerce` | 2026-09-27T071748235311 -> 2026-09-29T130746847722 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.kiddhu/seekapi` | 2026-09-26T192530851020 -> 2026-09-29T130726257010 | 1 changed, 4 added | review |
| 2026-09-29 | `remote/com.difficat/difficat` | 2026-09-29T075208868767 -> 2026-09-29T130722754937 | 3 changed | quiet |
| 2026-09-29 | `remote/io.github.iabdullahm/rafid-agent-api` | 2026-09-29T072604541699 -> 2026-09-29T130658495850 | 69 changed | review |
| 2026-09-29 | `remote/com.labelixa/zpl` | 2026-09-23T162235412568 -> 2026-09-29T130442794148 | 1 changed | quiet |
| 2026-09-29 | `remote/com.marketintelligenceapi.api/market-intelligence` | 2026-09-29T081943738402 -> 2026-09-29T130430052733 | 1 changed | quiet |
| 2026-09-29 | `remote/io.github.mosaro0224/averis-protocol` | 2026-09-28T103326426975 -> 2026-09-29T130401907031 | 3 added | quiet |
| 2026-09-29 | `remote/art.aiwashere/wall` | 2026-09-28T140912559692 -> 2026-09-29T130401458090 | 11 changed | quiet |
| 2026-09-29 | `remote/io.github.TWolf01/agentsgather` | 2026-09-29T112425200257 -> 2026-09-29T130338484008 | 4 changed, 1 added | quiet |
| 2026-09-29 | `remote/io.github.faisal-maverick/aayat-ai` | 2026-09-29T100208903118 -> 2026-09-29T130236758591 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 9890 substantive, 3160 that changed only numbers (a catalogue counter ticking, a date), 173 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 7023 | 4048 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `caseyjhand.com` | 56 | 56 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| `sistaminuten.se` | 44 | 2 | 0 | 42 |
| `afbudsrejser.dk` | 43 | 2 | 0 | 41 |
| `akkilahdot.fi` | 43 | 2 | 0 | 41 |
| `restplass.no` | 43 | 2 | 0 | 41 |
| `socialloop.ai` | 43 | 43 | 0 | 0 |
| `fastmcp.app` | 29 | 29 | 0 | 0 |
| `dayze.com` | 28 | 28 | 0 | 0 |
| 1286 other operators | 3055 | 2862 | 185 | 8 |
