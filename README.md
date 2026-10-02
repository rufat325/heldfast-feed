# MCP server tool changes

Last change observed 2026-10-02T21:01:56+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

18390 changes to a tool definition: 545 npm releases (299 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 17845 readings of hosted servers that found their tools changed; 167 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-10-02 | `remote/com.youspot/youspot` | 2026-10-02T183020584396 -> 2026-10-02T210158057865 | 3 changed | quiet |
| 2026-10-02 | `remote/com.makometrics/mako-metrics` | 2026-10-02T071859516632 -> 2026-10-02T210154103198 | 14 changed | quiet |
| 2026-10-02 | `remote/com.toolfound/toolfound` | 2026-10-02T071850177159 -> 2026-10-02T210153056408 | 4 added | quiet |
| 2026-10-02 | `remote/com.thenewengineer/hvac` | 2026-10-01T063533557407 -> 2026-10-02T210153062801 | 1 added | quiet |
| 2026-10-02 | `remote/xyz.pflow.sim/whatif` | 2026-10-02T182826320208 -> 2026-10-02T210150190656 | 5 changed | quiet |
| 2026-10-02 | `remote/se.sistaminuten/travel-search` | 2026-10-02T182903370919 -> 2026-10-02T210148407547 | 1 changed | quiet |
| 2026-10-02 | `remote/pro.socialhive/platform` | 2026-09-30T152229231730 -> 2026-10-02T210146939128 | 1 changed, 2 removed | quiet |
| 2026-10-02 | `remote/app.pixly/pixly` | 2026-10-02T182735953015 -> 2026-10-02T210145041111 | 2 changed | quiet |
| 2026-10-02 | `remote/com.topologyindex/topology-index` | 2026-10-02T182803532061 -> 2026-10-02T210140340559 | 3 changed | quiet |
| 2026-10-02 | `remote/fi.akkilahdot/travel-search` | 2026-10-02T182839929091 -> 2026-10-02T210139594821 | 1 changed | quiet |
| 2026-10-02 | `remote/tech.viewprinter/viewprinter` | 2026-09-30T060132952326 -> 2026-10-02T210137916770 | 7 changed | quiet |
| 2026-10-02 | `remote/io.github.Schoasch/backtesting-arena` | 2026-10-02T130057040509 -> 2026-10-02T210136544968 | 2 changed | quiet |
| 2026-10-02 | `remote/store.scvd/general-store` | 2026-10-01T212509138980 -> 2026-10-02T210136524074 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.IO31-WEB/synapse-lounge` | 2026-10-02T150327438634 -> 2026-10-02T210136922267 | 1 changed | quiet |
| 2026-10-02 | `remote/app.repopilot/repopilot` | 2026-10-02T130100713183 -> 2026-10-02T210135321764 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.warpfreight/warp-agent-mcp` | 2026-10-01T134020829786 -> 2026-10-02T210134628654 | 1 added | quiet |
| 2026-10-02 | `remote/no.restplass/travel-search` | 2026-10-02T183013621999 -> 2026-10-02T210133748473 | 1 changed | quiet |
| 2026-10-02 | `remote/insure.spot/insurance-research` | 2026-10-02T182748397163 -> 2026-10-02T210137168547 | 4 changed | quiet |
| 2026-10-02 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-02T182741290250 -> 2026-10-02T210132562801 | 1 changed | quiet |
| 2026-10-02 | `remote/dk.afbudsrejser/travel-search` | 2026-10-02T182950517997 -> 2026-10-02T210132369860 | 1 changed | quiet |
| 2026-10-02 | `remote/com.seqbench/workbench` | 2026-10-02T150322678319 -> 2026-10-02T210131795346 | 4 changed | quiet |
| 2026-10-02 | `remote/dev.turva/turva-mcp` | 2026-10-02T150314793747 -> 2026-10-02T210131842303 | 1 changed | quiet |
| 2026-10-02 | `remote/com.remoshift/jobs` | 2026-10-02T182713614267 -> 2026-10-02T210130667614 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.linxule/mcp-music-studio` | 2026-10-02T182624713512 -> 2026-10-02T210129404228 | 1 changed | quiet |
| 2026-10-02 | `remote/dev.moradas/moradas` | 2026-10-02T182621567915 -> 2026-10-02T210127357191 | 1 changed | quiet |
| 2026-10-02 | `remote/com.multicinesortega/cartelera` | 2026-10-02T061623229363 -> 2026-10-02T210128513534 | 1 changed | quiet |
| 2026-10-02 | `remote/com.luxurylodgingpm.stay/luxury-lodging` | 2026-10-02T182841001194 -> 2026-10-02T210127498077 | 4 changed, 1 added | quiet |
| 2026-10-02 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-02T150311203148 -> 2026-10-02T210127161409 | 2 changed | quiet |
| 2026-10-02 | `remote/io.github.sailorpepe/undesirables-mcp-server` | 2026-10-02T182559003142 -> 2026-10-02T210126253041 | 1 changed | quiet |
| 2026-10-02 | `remote/com.squawkflow.mcp/market-structure` | 2026-10-01T134055423496 -> 2026-10-02T210126340621 | 14 changed, 1 added | quiet |
| 2026-10-02 | `remote/io.github.tcador/787daily` | 2026-10-02T182419318159 -> 2026-10-02T210120973621 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.Clipform/mcp-server` | 2026-10-01T134126691898 -> 2026-10-02T210122499010 | 1 changed | quiet |
| 2026-10-02 | `remote/com.donebear/donebear` | 2026-09-30T152217761738 -> 2026-10-02T210121304144 | 3 changed | quiet |
| 2026-10-02 | `remote/io.github.yzlee/opcmenu` | 2026-10-01T212513667095 -> 2026-10-02T210122212951 | 2 changed | quiet |
| 2026-10-02 | `remote/io.github.apollographql/graphos-mcp-server` | 2026-10-01T133915213821 -> 2026-10-02T210116061233 | 29 changed | quiet |
| 2026-10-02 | `remote/team.jogo/mcp` | 2026-10-02T071644858716 -> 2026-10-02T210115064616 | 1 changed | quiet |
| 2026-10-02 | `remote/com.davisvillelabs/facilityproof` | 2026-10-02T182153382195 -> 2026-10-02T210115899676 | 2 changed (every tool) | quiet |
| 2026-10-02 | `remote/so.darwin/darwin` | 2026-10-02T182509536722 -> 2026-10-02T210114887721 | 1 changed | quiet |
| 2026-10-02 | `remote/com.jithox/jithox` | 2026-10-02T125545098562 -> 2026-10-02T210113979605 | 8 changed (every tool) | quiet |
| 2026-10-02 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-02T182134517509 -> 2026-10-02T210111487185 | 1 changed | quiet |
| 2026-10-02 | `remote/cloud.dchub/mcp-server` | 2026-10-02T080033662626 -> 2026-10-02T210108373747 | 3 changed | quiet |
| 2026-10-02 | `remote/com.beleeg/beleeg-public` | 2026-09-30T060046784512 -> 2026-10-02T210104764977 | 2 removed | quiet |
| 2026-10-02 | `remote/page.anew/anew` | 2026-10-02T071055531661 -> 2026-10-02T210104115452 | 1 changed | quiet |
| 2026-10-02 | `remote/com.uplika/uplika` | 2026-10-02T181950872903 -> 2026-10-02T210103057082 | 1 changed | quiet |
| 2026-10-02 | `remote/com.askmatchbox/matchbox` | 2026-10-02T061558119185 -> 2026-10-02T210103897334 | 2 changed | quiet |
| 2026-10-02 | `remote/io.github.hermoso-ai/hermoso` | 2026-10-01T154218438412 -> 2026-10-02T210101322690 | 4 changed | quiet |
| 2026-10-02 | `remote/com.prereason/mcp` | 2026-10-02T125208479938 -> 2026-10-02T210101222329 | 2 changed | quiet |
| 2026-10-02 | `remote/io.github.0xinsider/mcp` | 2026-10-01T212435026139 -> 2026-10-02T210059359599 | 1 changed | quiet |
| 2026-10-02 | `remote/com.aisenseapi/free-public-tools` | 2026-10-01T133025116565 -> 2026-10-02T210059869355 | 2 changed | quiet |
| 2026-10-02 | `remote/app.agentbit/mcp` | 2026-10-02T181718234960 -> 2026-10-02T210058364678 | 1 changed | quiet |
| 2026-10-02 | `remote/io.openwaters/ais` | 2026-10-01T212445313142 -> 2026-10-02T210055124145 | 4 changed | quiet |
| 2026-10-02 | `remote/com.agorean/agorean` | 2026-10-02T061601479039 -> 2026-10-02T210054297023 | 1 changed | quiet |
| 2026-10-02 | `remote/io.taifoon/coordination-layer` | 2026-10-02T130832931637 -> 2026-10-02T183021905118 | 2 changed | quiet |
| 2026-10-02 | `remote/com.youspot/youspot` | 2026-10-02T061633542180 -> 2026-10-02T183020584396 | 5 added | quiet |
| 2026-10-02 | `remote/com.rubrkit/rubrkit` | 2026-09-29T073512164452 -> 2026-10-02T183014828308 | 1 changed, 2 added | quiet |
| 2026-10-02 | `remote/no.restplass/travel-search` | 2026-10-02T150318105800 -> 2026-10-02T183013621999 | 1 changed | quiet |
| 2026-10-02 | `remote/dk.afbudsrejser/travel-search` | 2026-10-02T150316799928 -> 2026-10-02T182950517997 | 1 changed | quiet |
| 2026-10-02 | `remote/com.whenisbins/bin-collections` | 2026-10-01T134224499521 -> 2026-10-02T182944757113 | 4 changed (every tool) | quiet |
| 2026-10-02 | `remote/io.github.SidneyBissoli/uis-mcp-server` | 2026-09-28T073136135279 -> 2026-10-02T182925021536 | 2 changed | quiet |
| 2026-10-02 | `remote/ai.trydock/dock` | 2026-09-24T120414991775 -> 2026-10-02T182920824509 | 1 changed, 4 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 13408 substantive, 4741 that changed only numbers (a catalogue counter ticking, a date), 241 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 10138 | 5671 | 4467 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `caseyjhand.com` | 66 | 66 | 0 | 0 |
| `sistaminuten.se` | 60 | 2 | 0 | 58 |
| `afbudsrejser.dk` | 59 | 2 | 0 | 57 |
| `akkilahdot.fi` | 59 | 2 | 0 | 57 |
| `restplass.no` | 59 | 2 | 0 | 57 |
| `socialloop.ai` | 58 | 58 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| `dayze.com` | 51 | 51 | 0 | 0 |
| 1843 other operators | 4927 | 4641 | 274 | 12 |
