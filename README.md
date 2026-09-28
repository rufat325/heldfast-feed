# MCP server tool changes

Last change observed 2026-09-28T10:44:17+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9409 npm servers from the official MCP registry (154 daily, the rest weekly) and 18576 hosted endpoints (daily).

12464 changes to a tool definition: 360 npm releases (114 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 12104 readings of hosted servers that found their tools changed; 41 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-09-28 | `remote/io.github.seekdaseek/agentfeed` | 2026-09-28T073232191598 -> 2026-09-28T104419583470 | 2 changed | quiet |
| 2026-09-28 | `remote/se.sistaminuten/travel-search` | 2026-09-28T073343377982 -> 2026-09-28T104352121709 | 1 changed | quiet |
| 2026-09-28 | `remote/fi.akkilahdot/travel-search` | 2026-09-28T073206069408 -> 2026-09-28T104349552972 | 1 changed | quiet |
| 2026-09-28 | `remote/uk.co.gigstamp/gigstamp` | 2026-09-23T161026901375 -> 2026-09-28T104340798402 | 1 changed | quiet |
| 2026-09-28 | `remote/com.autoridaddigital.www/geo` | 2026-09-23T161021452405 -> 2026-09-28T104333448101 | 5 changed (every tool) | quiet |
| 2026-09-28 | `remote/com.trip1/mcp` | 2026-09-26T045534723474 -> 2026-09-28T104325846758 | 1 removed | quiet |
| 2026-09-28 | `remote/world.agentindex/x402` | 2026-09-28T073217920760 -> 2026-09-28T104302021100 | 3 changed | quiet |
| 2026-09-28 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-28T073115999453 -> 2026-09-28T104255115525 | 1 changed | quiet |
| 2026-09-28 | `remote/no.restplass/travel-search` | 2026-09-28T073206633291 -> 2026-09-28T104249419868 | 1 changed | quiet |
| 2026-09-28 | `remote/io.github.CodePhantom-1/ddmarketer-mcp` | 2026-09-28T073155859252 -> 2026-09-28T104236003034 | 1 changed | quiet |
| 2026-09-28 | `remote/ai.agentlookups/counterscript` | 2026-09-28T073056103291 -> 2026-09-28T104234422542 | 1 changed | quiet |
| 2026-09-28 | `remote/dk.afbudsrejser/travel-search` | 2026-09-28T073151138315 -> 2026-09-28T104231553151 | 1 changed | quiet |
| 2026-09-28 | `remote/com.remoshift/jobs` | 2026-09-28T055531873509 -> 2026-09-28T104227368670 | 1 changed | quiet |
| 2026-09-28 | `remote/ai.regulations/regulations-ai` | 2026-09-23T162832662694 -> 2026-09-28T104225161513 | 8 changed (every tool) | quiet |
| 2026-09-28 | `remote/xyz.trusteed/mcp-gateway` | 2026-09-27T105257719831 -> 2026-09-28T104214995179 | 7 changed | quiet |
| 2026-09-28 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-09-28T073109473434 -> 2026-09-28T104151126776 | 15 changed | review |
| 2026-09-28 | `remote/ai.agentlookups/overassessed` | 2026-09-28T073022384242 -> 2026-09-28T104150749622 | 1 changed | quiet |
| 2026-09-28 | `remote/ai.agentlookups/greenlight` | 2026-09-23T163009376076 -> 2026-09-28T104145427730 | 2 changed (every tool) | quiet |
| 2026-09-28 | `remote/io.github.moralito311-andr/andreax` | 2026-09-28T073125363146 -> 2026-09-28T104141766865 | 3 added | quiet |
| 2026-09-28 | `remote/co.civai.nova/terminal-command-agent` | 2026-09-23T162800456409 -> 2026-09-28T104138932773 | 4 added, 4 removed | quiet |
| 2026-09-28 | `remote/co.civai.nova/interviewer-agent` | 2026-09-23T162800295614 -> 2026-09-28T104138530735 | 3 added, 3 removed | quiet |
| 2026-09-28 | `remote/co.civai.nova/gmail-agent` | 2026-09-23T162800186205 -> 2026-09-28T104138511609 | 4 added, 4 removed | quiet |
| 2026-09-28 | `remote/co.civai.nova/blogger-agent` | 2026-09-23T162800094445 -> 2026-09-28T104138267846 | 6 added, 6 removed | quiet |
| 2026-09-28 | `remote/co.civai.nova/whatsapp-web-agent` | 2026-09-23T160844146902 -> 2026-09-28T104129441454 | 11 added, 11 removed | quiet |
| 2026-09-28 | `remote/co.civai.nova/twitter-agent` | 2026-09-23T160844051945 -> 2026-09-28T104129281973 | 4 added, 4 removed | quiet |
| 2026-09-28 | `remote/co.civai.nova/pdf-agent` | 2026-09-23T160843939369 -> 2026-09-28T104129167273 | 6 added, 6 removed | quiet |
| 2026-09-28 | `remote/co.civai.nova/music-agent` | 2026-09-23T160843838710 -> 2026-09-28T104129014545 | 2 added, 2 removed | quiet |
| 2026-09-28 | `remote/co.civai.nova/leads-discovery-agent` | 2026-09-25T120425309044 -> 2026-09-28T104128908034 | 16 added, 16 removed | quiet |
| 2026-09-28 | `remote/co.civai.nova/google-docs-agent` | 2026-09-23T160843579109 -> 2026-09-28T104128651967 | 8 added, 8 removed | quiet |
| 2026-09-28 | `remote/it.piqod/experiences-oracle` | 2026-09-23T160717878028 -> 2026-09-28T104058235599 | 3 changed (every tool) | quiet |
| 2026-09-28 | `remote/ai.tachyo/tachyo` | 2026-09-23T162732911078 -> 2026-09-28T104053755387 | 3 changed | quiet |
| 2026-09-28 | `remote/io.github.mason0501/pairgora` | 2026-09-28T073006305126 -> 2026-09-28T104046341728 | 5 changed | quiet |
| 2026-09-28 | `remote/com.sednasystem/genesis` | 2026-09-24T202552048185 -> 2026-09-28T104042922791 | 3 changed | quiet |
| 2026-09-28 | `remote/co.civai.nova/telegram-agent` | 2026-09-25T120457381646 -> 2026-09-28T104040489785 | 16 added, 16 removed | quiet |
| 2026-09-28 | `remote/co.civai.nova/research-agent` | 2026-09-23T162857497492 -> 2026-09-28T104040312301 | 4 added, 4 removed | quiet |
| 2026-09-28 | `remote/co.civai.nova/openclaw-agent` | 2026-09-23T162857463741 -> 2026-09-28T104040313810 | 4 added, 4 removed | quiet |
| 2026-09-28 | `remote/com.typestate/typestate` | 2026-09-23T160804576905 -> 2026-09-28T104041323577 | 3 added | quiet |
| 2026-09-28 | `remote/co.civai.nova/nova-inbox-agent` | 2026-09-23T162857221506 -> 2026-09-28T104040047513 | 7 added, 7 removed | quiet |
| 2026-09-28 | `remote/co.civai.nova/google-sheets-agent` | 2026-09-23T162856915591 -> 2026-09-28T104040073035 | 9 added, 9 removed | quiet |
| 2026-09-28 | `remote/co.civai.nova/support-agent-admin` | 2026-09-25T120331160019 -> 2026-09-28T104032896202 | 84 added, 84 removed | quiet |
| 2026-09-28 | `remote/co.civai.nova/slidegen-agent` | 2026-09-23T160658277072 -> 2026-09-28T104032426311 | 4 added, 4 removed | quiet |
| 2026-09-28 | `remote/co.civai.nova/content-calendar-agent` | 2026-09-23T160658135736 -> 2026-09-28T104032743789 | 9 added, 9 removed | quiet |
| 2026-09-28 | `remote/co.civai.nova/code-interpreter-agent` | 2026-09-23T160658008082 -> 2026-09-28T104032032759 | 8 added, 8 removed | quiet |
| 2026-09-28 | `remote/co.civai.nova/calendar-agent` | 2026-09-23T160657868338 -> 2026-09-28T104031688399 | 7 added, 7 removed | quiet |
| 2026-09-28 | `remote/co.civai.nova/browsergpt-agent` | 2026-09-23T160657721611 -> 2026-09-28T104031554390 | 4 added, 4 removed | quiet |
| 2026-09-28 | `remote/io.github.toshihiroshishido/revenuescope-mcp` | 2026-09-28T055519589501 -> 2026-09-28T104014835257 | 9 changed | quiet |
| 2026-09-28 | `remote/com.shotpulled/shotpulled` | 2026-09-27T134941206292 -> 2026-09-28T104000325503 | 13 changed | quiet |
| 2026-09-28 | `remote/com.jobmojito/jobmojito` | 2026-09-27T232554141659 -> 2026-09-28T103956110264 | 1 changed | quiet |
| 2026-09-28 | `remote/com.publora/mcp-server` | 2026-09-24T202343467319 -> 2026-09-28T103949774671 | 3 changed, 1 added | quiet |
| 2026-09-28 | `remote/com.thecrowdspace/crowdspace` | 2026-09-28T072910875133 -> 2026-09-28T103945478145 | 2 changed | quiet |
| 2026-09-28 | `remote/com.handsforagents/hands` | 2026-09-27T141918782650 -> 2026-09-28T103946512522 | 4 changed | quiet |
| 2026-09-28 | `remote/com.spaghettiandsummits/outdoors` | 2026-09-23T160615743136 -> 2026-09-28T103938230416 | 2 added | quiet |
| 2026-09-28 | `remote/dev.domainee/domainee` | 2026-09-23T162630140488 -> 2026-09-28T103923710116 | 18 changed (every tool) | quiet |
| 2026-09-28 | `remote/com.dexpaprika/dexpaprika` | 2026-09-23T160717434185 -> 2026-09-28T103925653301 | 1 changed | quiet |
| 2026-09-28 | `remote/com.dataart/case-studies` | 2026-09-24T202334325607 -> 2026-09-28T103902147108 | 3 changed (every tool) | quiet |
| 2026-09-28 | `remote/io.github.AETumiApp/aetumi` | 2026-09-23T162635765789 -> 2026-09-28T103828585353 | 10 changed, 2 added (every tool) | quiet |
| 2026-09-28 | `remote/io.github.si-imtiaz/leadquasar` | 2026-09-28T055523618599 -> 2026-09-28T103828816072 | 2 changed | quiet |
| 2026-09-28 | `remote/io.github.leanrads/leanriq` | 2026-09-23T162538583541 -> 2026-09-28T103812863519 | 2 changed, 2 added | quiet |
| 2026-09-28 | `remote/page.aft/mcp` | 2026-09-23T160512559284 -> 2026-09-28T103803683021 | 5 changed (every tool) | quiet |
| 2026-09-28 | `remote/io.github.RightOnPar-LLC/meshmarket` | 2026-09-26T113854994090 -> 2026-09-28T103755150974 | 4 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 9215 substantive, 3121 that changed only numbers (a catalogue counter ticking, a date), 128 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 7017 | 4042 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `caseyjhand.com` | 56 | 56 | 0 | 0 |
| `daedalmap.com` | 47 | 47 | 0 | 0 |
| `sistaminuten.se` | 33 | 2 | 0 | 31 |
| `afbudsrejser.dk` | 32 | 2 | 0 | 30 |
| `akkilahdot.fi` | 32 | 2 | 0 | 30 |
| `restplass.no` | 32 | 2 | 0 | 30 |
| `socialloop.ai` | 32 | 32 | 0 | 0 |
| `civai.co` | 24 | 24 | 0 | 0 |
| `dayze.com` | 24 | 24 | 0 | 0 |
| 1060 other operators | 2370 | 2217 | 146 | 7 |
