# MCP server tool changes

Last change observed 2026-09-30T15:23:26+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

13631 changes to a tool definition: 384 npm releases (138 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 13247 readings of hosted servers that found their tools changed; 99 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-09-30 | `remote/world.agentindex/x402` | 2026-09-29T003629317635 -> 2026-09-30T152329465841 | 3 changed, 12 added | quiet |
| 2026-09-30 | `remote/io.taifoon/coordination-layer` | 2026-09-30T060144249530 -> 2026-09-30T152326050483 | 2 changed, 6 added | quiet |
| 2026-09-30 | `remote/no.restplass/travel-search` | 2026-09-30T060143709015 -> 2026-09-30T152325323884 | 1 changed | quiet |
| 2026-09-30 | `remote/io.github.Uuriko/project-room` | 2026-09-29T003625881517 -> 2026-09-30T152325107925 | 2 added | quiet |
| 2026-09-30 | `remote/dk.afbudsrejser/travel-search` | 2026-09-30T060141073013 -> 2026-09-30T152320358308 | 1 changed | quiet |
| 2026-09-30 | `remote/io.github.simonplmak-cloud/vision-driven-design` | 2026-09-28T142243110927 -> 2026-09-30T152315326297 | 15 changed (every tool) | quiet |
| 2026-09-30 | `remote/io.github.taux-io/twse-mcp` | 2026-09-29T210504475680 -> 2026-09-30T152314515081 | 1 changed | quiet |
| 2026-09-30 | `remote/xyz.trusteed/mcp-gateway` | 2026-09-29T003622121499 -> 2026-09-30T152312112662 | 2 changed | quiet |
| 2026-09-30 | `remote/com.tradeassi/mcp` | 2026-09-29T210502239789 -> 2026-09-30T152310697870 | 2 changed | quiet |
| 2026-09-30 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-09-29T210459225485 -> 2026-09-30T152304883094 | 15 changed | review |
| 2026-09-30 | `remote/com.luxurylodgingpm.stay/luxury-lodging` | 2026-09-29T073359154153 -> 2026-09-30T152304163571 | 6 changed (every tool) | quiet |
| 2026-09-30 | `remote/com.qumge/skills` | 2026-09-29T061646811045 -> 2026-09-30T152302197311 | 2 changed | quiet |
| 2026-09-30 | `remote/ua.com.quintadb/mcp` | 2026-09-29T073313237232 -> 2026-09-30T152253641758 | 3 changed | quiet |
| 2026-09-30 | `remote/se.sistaminuten/travel-search` | 2026-09-30T060138520153 -> 2026-09-30T152247624236 | 1 changed | quiet |
| 2026-09-30 | `remote/io.github.kor-jongwon/witan` | 2026-09-29T210518920769 -> 2026-09-30T152248926741 | 4 changed | quiet |
| 2026-09-30 | `remote/fi.akkilahdot/travel-search` | 2026-09-30T060135687287 -> 2026-09-30T152247316597 | 1 changed | quiet |
| 2026-09-30 | `remote/com.goedvps.app.wodan-posture/wodan-posture` | 2026-09-29T101945049245 -> 2026-09-30T152247175576 | 1 added | quiet |
| 2026-09-30 | `remote/it.expatliving/data` | 2026-09-28T142318028122 -> 2026-09-30T152245364876 | 2 added | quiet |
| 2026-09-30 | `remote/io.github.sharan01x/usetested` | 2026-09-28T142600433224 -> 2026-09-30T152245933217 | 1 changed | quiet |
| 2026-09-30 | `remote/com.contrie/contrie` | 2026-09-30T060133816716 -> 2026-09-30T152244732004 | 1 changed | quiet |
| 2026-09-30 | `remote/io.github.untitledfinancial/dpx` | 2026-09-30T060123687415 -> 2026-09-30T152245878753 | 1 removed | quiet |
| 2026-09-30 | `remote/io.github.nimitt-IN/india-cyber-regulations` | 2026-09-29T210512398244 -> 2026-09-30T152245919357 | 1 changed | quiet |
| 2026-09-30 | `remote/io.github.mlolahq/mlola-ui` | 2026-09-30T060149735722 -> 2026-09-30T152244627415 | 1 changed | quiet |
| 2026-09-30 | `remote/io.github.FTHTrading/genesis402-mcp` | 2026-09-30T060147388240 -> 2026-09-30T152243783191 | 3 changed, 7 added | review |
| 2026-09-30 | `remote/com.trustycap/trustycap` | 2026-09-29T073207038485 -> 2026-09-30T152247325932 | 2 changed | quiet |
| 2026-09-30 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-09-29T210512824716 -> 2026-09-30T152243202527 | 1 changed | quiet |
| 2026-09-30 | `remote/io.orbitwan/orbitwan` | 2026-09-29T082711376497 -> 2026-09-30T152241234159 | 1 added | quiet |
| 2026-09-30 | `remote/com.tenmomo/tenmomo` | 2026-09-28T142246801880 -> 2026-09-30T152240132626 | 1 changed | quiet |
| 2026-09-30 | `remote/cc.thecolony/mcp-server` | 2026-09-29T210511615078 -> 2026-09-30T152244033132 | 2 changed | quiet |
| 2026-09-30 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-30T060125794058 -> 2026-09-30T152238575094 | 1 changed | quiet |
| 2026-09-30 | `remote/io.github.SKalinin909/tradingcalc` | 2026-09-29T210510879897 -> 2026-09-30T152242557065 | 9 changed | quiet |
| 2026-09-30 | `remote/io.github.steffanricardo/the-dutch-directory` | 2026-09-30T060128679610 -> 2026-09-30T152237694713 | 15 changed (every tool) | quiet |
| 2026-09-30 | `remote/com.innergcomplete/shearquery` | 2026-09-30T060126559877 -> 2026-09-30T152242146835 | 1 added | quiet |
| 2026-09-30 | `remote/nl.sportpoeder/agent` | 2026-09-28T142234449289 -> 2026-09-30T152245000388 | 1 changed | quiet |
| 2026-09-30 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-09-29T061629105535 -> 2026-09-30T152235299876 | 2 changed, 3 added | quiet |
| 2026-09-30 | `remote/com.saylorinnovations/data` | 2026-09-29T003607717244 -> 2026-09-30T152235985339 | 2 changed, 12 added | review |
| 2026-09-30 | `remote/com.remoshift/jobs` | 2026-09-30T060120556877 -> 2026-09-30T152233203230 | 1 changed | quiet |
| 2026-09-30 | `remote/com.radar-cnpj/radar-cnpj` | 2026-09-30T060120517361 -> 2026-09-30T152232866669 | 3 changed | quiet |
| 2026-09-30 | `remote/com.ribqa/sentinel-aleph` | 2026-09-29T210501906511 -> 2026-09-30T152232187130 | 1 changed | quiet |
| 2026-09-30 | `remote/ru.quintadb/mcp` | 2026-09-29T073222240885 -> 2026-09-30T152232561363 | 3 changed | quiet |
| 2026-09-30 | `remote/com.quintadb/mcp` | 2026-09-29T073033368721 -> 2026-09-30T152231502111 | 3 changed | quiet |
| 2026-09-30 | `remote/com.quietstance/workflow-assessment` | 2026-09-28T142137145087 -> 2026-09-30T152230209454 | 2 added, 8 removed | quiet |
| 2026-09-30 | `remote/com.qevrulan/lockzone` | 2026-09-28T142134212902 -> 2026-09-30T152229225714 | 2 changed, 4 added | quiet |
| 2026-09-30 | `remote/pro.socialhive/platform` | 2026-09-28T142122440667 -> 2026-09-30T152229231730 | 2 changed | quiet |
| 2026-09-30 | `remote/io.github.geekmarine/mcp-defi-router` | 2026-09-28T141739853998 -> 2026-09-30T152228672901 | 3 changed (every tool) | quiet |
| 2026-09-30 | `remote/com.pontofato/pontofato` | 2026-09-29T210459598445 -> 2026-09-30T152229091691 | 1 changed | quiet |
| 2026-09-30 | `remote/io.github.peter120525-cmd/lawmadi-os` | 2026-09-28T141721386099 -> 2026-09-30T152227957406 | 1 changed | quiet |
| 2026-09-30 | `remote/io.github.steffanricardo/the-dutch-directory.1` | 2026-09-30T060113694653 -> 2026-09-30T152225117046 | 15 changed (every tool) | quiet |
| 2026-09-30 | `remote/io.github.moralito311-andr/andreax` | 2026-09-30T060117527532 -> 2026-09-30T152226080786 | 2 changed | review |
| 2026-09-30 | `remote/ai.switchapp/switch` | 2026-09-30T060112494297 -> 2026-09-30T152224032605 | 2 changed | quiet |
| 2026-09-30 | `remote/com.sednasystem/genesis` | 2026-09-29T113206668064 -> 2026-09-30T152223167896 | 1 changed | quiet |
| 2026-09-30 | `remote/org.nsgoods/nsgoods-workbench-mcp` | 2026-09-29T150741750013 -> 2026-09-30T152220833976 | 2 changed | quiet |
| 2026-09-30 | `remote/dev.genhttp/lambda` | 2026-09-29T003555887871 -> 2026-09-30T152223003198 | 8 changed, 6 added | quiet |
| 2026-09-30 | `remote/com.thisisdelightful/games-research-starter-pack` | 2026-09-28T141557262672 -> 2026-09-30T152220756903 | 5 changed | quiet |
| 2026-09-30 | `remote/dev.mcphost/mcphost` | 2026-09-30T060131747669 -> 2026-09-30T152220960390 | 2 changed | quiet |
| 2026-09-30 | `remote/com.lightbringer/connector` | 2026-09-29T131233650861 -> 2026-09-30T152219484739 | 1 changed | quiet |
| 2026-09-30 | `remote/com.kernelcad/kernelcad` | 2026-09-30T060109682088 -> 2026-09-30T152219952881 | 1 added | quiet |
| 2026-09-30 | `remote/io.github.lbailey94/whitemagic-mcp` | 2026-09-30T060129252037 -> 2026-09-30T152218616634 | 2 changed | quiet |
| 2026-09-30 | `remote/com.veterical/veterical` | 2026-09-28T141948868442 -> 2026-09-30T152218798435 | 1 changed | quiet |
| 2026-09-30 | `remote/io.guestgraph/mental-model` | 2026-09-28T142234244018 -> 2026-09-30T152218066930 | 7 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 10260 substantive, 3180 that changed only numbers (a catalogue counter ticking, a date), 191 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 7023 | 4048 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `caseyjhand.com` | 56 | 56 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| `sistaminuten.se` | 48 | 2 | 0 | 46 |
| `afbudsrejser.dk` | 47 | 2 | 0 | 45 |
| `akkilahdot.fi` | 47 | 2 | 0 | 45 |
| `restplass.no` | 47 | 2 | 0 | 45 |
| `socialloop.ai` | 47 | 47 | 0 | 0 |
| `fastmcp.app` | 41 | 41 | 0 | 0 |
| `dayze.com` | 36 | 36 | 0 | 0 |
| 1343 other operators | 3423 | 3208 | 205 | 10 |
