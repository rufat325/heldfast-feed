# MCP server tool changes

Last change observed 2026-10-02T18:30:19+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

18338 changes to a tool definition: 545 npm releases (299 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 17793 readings of hosted servers that found their tools changed; 167 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-10-02 | `remote/io.taifoon/coordination-layer` | 2026-10-02T130832931637 -> 2026-10-02T183021905118 | 2 changed | quiet |
| 2026-10-02 | `remote/com.youspot/youspot` | 2026-10-02T061633542180 -> 2026-10-02T183020584396 | 5 added | quiet |
| 2026-10-02 | `remote/com.rubrkit/rubrkit` | 2026-09-29T073512164452 -> 2026-10-02T183014828308 | 1 changed, 2 added | quiet |
| 2026-10-02 | `remote/no.restplass/travel-search` | 2026-10-02T150318105800 -> 2026-10-02T183013621999 | 1 changed | quiet |
| 2026-10-02 | `remote/dk.afbudsrejser/travel-search` | 2026-10-02T150316799928 -> 2026-10-02T182950517997 | 1 changed | quiet |
| 2026-10-02 | `remote/com.whenisbins/bin-collections` | 2026-10-01T134224499521 -> 2026-10-02T182944757113 | 4 changed (every tool) | quiet |
| 2026-10-02 | `remote/io.github.SidneyBissoli/uis-mcp-server` | 2026-09-28T073136135279 -> 2026-10-02T182925021536 | 2 changed | quiet |
| 2026-10-02 | `remote/ai.trydock/dock` | 2026-09-24T120414991775 -> 2026-10-02T182920824509 | 1 changed, 4 added | quiet |
| 2026-10-02 | `remote/com.tradeassi/mcp` | 2026-09-30T152310697870 -> 2026-10-02T182916775975 | 2 changed | quiet |
| 2026-10-02 | `remote/com.lowerscript/prices` | 2026-09-23T162946816732 -> 2026-10-02T182904343549 | 2 changed | quiet |
| 2026-10-02 | `remote/se.sistaminuten/travel-search` | 2026-10-02T150339990824 -> 2026-10-02T182903370919 | 1 changed | quiet |
| 2026-10-02 | `remote/io.kolmo.www/kolmo-mcp-server` | 2026-10-02T130253849471 -> 2026-10-02T182848727095 | 1 changed | quiet |
| 2026-10-02 | `remote/com.luxurylodgingpm.stay/luxury-lodging` | 2026-10-02T150312248337 -> 2026-10-02T182841001194 | 4 changed | quiet |
| 2026-10-02 | `remote/fi.akkilahdot/travel-search` | 2026-10-02T150330611285 -> 2026-10-02T182839929091 | 1 changed | quiet |
| 2026-10-02 | `remote/com.soxoa/automation-planning` | 2026-09-23T163012932437 -> 2026-10-02T182836098950 | 2 changed (every tool) | quiet |
| 2026-10-02 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-02T130434517841 -> 2026-10-02T182835010683 | 3 added | review |
| 2026-10-02 | `remote/xyz.pflow.sim/whatif` | 2026-10-02T150332612767 -> 2026-10-02T182826320208 | 10 changed | quiet |
| 2026-10-02 | `remote/org.texs/tapercraft` | 2026-09-29T073335260893 -> 2026-10-02T182839160006 | 16 changed (every tool) | quiet |
| 2026-10-02 | `remote/io.github.send21io/mcp` | 2026-09-23T160741721264 -> 2026-10-02T182816227714 | 3 changed | quiet |
| 2026-10-02 | `remote/ai.vaaya/mcp` | 2026-10-01T134354048386 -> 2026-10-02T182812540189 | 1 changed | review |
| 2026-10-02 | `remote/ai.rokha/rokha` | 2026-10-02T061619916342 -> 2026-10-02T182805298963 | 4 added | quiet |
| 2026-10-02 | `remote/com.topologyindex/topology-index` | 2026-09-26T231053759346 -> 2026-10-02T182803532061 | 3 changed | quiet |
| 2026-10-02 | `remote/com.synapticrelay/board.1` | 2026-10-01T063556975690 -> 2026-10-02T182800129906 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.Jaywestphilly/stock-bloc` | 2026-09-23T162858313506 -> 2026-10-02T182752958635 | 7 changed | review |
| 2026-10-02 | `remote/io.github.dtajitdinov-aris/sphere-marketplace` | 2026-10-02T150326136113 -> 2026-10-02T182749986406 | 1 added, 1 removed | quiet |
| 2026-10-02 | `remote/art.thisisstill/still-mcp` | 2026-09-23T160943314745 -> 2026-10-02T182748196373 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.Nikolife2016/pulsefeed-x402` | 2026-09-23T162929128291 -> 2026-10-02T182746960090 | 1 changed | quiet |
| 2026-10-02 | `remote/insure.spot/insurance-research` | 2026-10-02T061630896245 -> 2026-10-02T182748397163 | 3 changed | quiet |
| 2026-10-02 | `remote/xyz.solknife/toolkit` | 2026-09-23T162855605772 -> 2026-10-02T182744092663 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.Perufitlife/postwire-mcp` | 2026-10-01T134139363640 -> 2026-10-02T182742014309 | 5 changed | quiet |
| 2026-10-02 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-02T150324111974 -> 2026-10-02T182741290250 | 1 changed | quiet |
| 2026-10-02 | `remote/com.shipshapedata/shipshape-data-docs` | 2026-09-23T160935784132 -> 2026-10-02T182736714802 | 1 changed | quiet |
| 2026-10-02 | `remote/app.pixly/pixly` | 2026-10-02T061623413570 -> 2026-10-02T182735953015 | 6 added | quiet |
| 2026-10-02 | `remote/dev.benys/the-pit` | 2026-09-29T101005423641 -> 2026-10-02T182735624494 | 2 changed, 9 added | quiet |
| 2026-10-02 | `remote/systems.phion/evidence-engine` | 2026-10-02T071727668840 -> 2026-10-02T182732327490 | 1 changed, 1 added | quiet |
| 2026-10-02 | `remote/io.github.SidneyBissoli/senado-br-mcp-cloudflare` | 2026-09-25T120506423720 -> 2026-10-02T182731142437 | 2 changed | quiet |
| 2026-10-02 | `remote/es.cesaryague/paki-curator` | 2026-10-02T130552793637 -> 2026-10-02T182724554839 | 2 changed | quiet |
| 2026-10-02 | `remote/io.github.mangelmartinezfer-hue/returncheck` | 2026-09-23T162834882170 -> 2026-10-02T182715337519 | 1 changed | quiet |
| 2026-10-02 | `remote/com.remoshift/jobs` | 2026-10-02T150322789774 -> 2026-10-02T182713614267 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.salemalem/npmscan` | 2026-10-02T130541351939 -> 2026-10-02T182710570857 | 2 changed | quiet |
| 2026-10-02 | `remote/com.regsentry/tracking-inspector` | 2026-09-23T160914911686 -> 2026-10-02T182709767026 | 1 changed | quiet |
| 2026-10-02 | `remote/jp.yomitasu/zippa-jp` | 2026-09-28T142002823836 -> 2026-10-02T182641499916 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.lemonaide152/meld` | 2026-10-01T134038356124 -> 2026-10-02T182644580600 | 1 changed | quiet |
| 2026-10-02 | `remote/com.zeamprism/prism-mcp` | 2026-10-02T071642809394 -> 2026-10-02T182633314009 | 1 changed | quiet |
| 2026-10-02 | `remote/jp.yomitasu/yomitasu-jp` | 2026-09-28T142015858116 -> 2026-10-02T182632126566 | 1 changed | quiet |
| 2026-10-02 | `remote/jp.yomitasu/prenica-jp` | 2026-09-28T142015812097 -> 2026-10-02T182632442132 | 1 changed | quiet |
| 2026-10-02 | `remote/jp.yomitasu/earthenware-jp` | 2026-09-28T142015873098 -> 2026-10-02T182632172820 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.linxule/mcp-music-studio` | 2026-10-02T150319724614 -> 2026-10-02T182624713512 | 2 changed | quiet |
| 2026-10-02 | `remote/com.mosaiden/souq` | 2026-10-02T080619464944 -> 2026-10-02T182622606627 | 1 added | quiet |
| 2026-10-02 | `remote/dev.moradas/moradas` | 2026-10-01T134320223063 -> 2026-10-02T182621567915 | 1 changed | quiet |
| 2026-10-02 | `remote/com.tkawen/intelligence-gateway` | 2026-10-02T150315434547 -> 2026-10-02T182616164208 | 1 changed | quiet |
| 2026-10-02 | `remote/com.viberooster/hatch` | 2026-09-27T232545794193 -> 2026-10-02T182614348193 | 2 changed | quiet |
| 2026-10-02 | `remote/io.github.SidneyBissoli/medical-terminologies-mcp` | 2026-09-29T061639157183 -> 2026-10-02T182605442409 | 2 changed | quiet |
| 2026-10-02 | `remote/com.meettempi/tempi` | 2026-10-01T063526008883 -> 2026-10-02T182605263293 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.sailorpepe/undesirables-mcp-server` | 2026-09-24T202602567349 -> 2026-10-02T182559003142 | 4 changed, 2 removed | quiet |
| 2026-10-02 | `remote/com.scanmalware.mcp/scanmalware-mcp` | 2026-09-23T160609420148 -> 2026-10-02T182559866575 | 7 changed | quiet |
| 2026-10-02 | `remote/jp.yomitasu/tsuyoshikashiwazaki-jp` | 2026-09-28T142007476534 -> 2026-10-02T182555767344 | 1 changed | quiet |
| 2026-10-02 | `remote/com.stocklens/stocklens` | 2026-09-28T170328638279 -> 2026-10-02T182554467613 | 1 changed | quiet |
| 2026-10-02 | `remote/com.veterical/veterical` | 2026-10-01T212500291437 -> 2026-10-02T182540551976 | 1 added | quiet |
| 2026-10-02 | `remote/app.manawa/manawa-terminal` | 2026-10-01T133900134125 -> 2026-10-02T182540127148 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 13363 substantive, 4738 that changed only numbers (a catalogue counter ticking, a date), 237 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 10138 | 5671 | 4467 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `caseyjhand.com` | 66 | 66 | 0 | 0 |
| `sistaminuten.se` | 59 | 2 | 0 | 57 |
| `afbudsrejser.dk` | 58 | 2 | 0 | 56 |
| `akkilahdot.fi` | 58 | 2 | 0 | 56 |
| `restplass.no` | 58 | 2 | 0 | 56 |
| `socialloop.ai` | 57 | 57 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| `dayze.com` | 51 | 51 | 0 | 0 |
| 1843 other operators | 4880 | 4597 | 271 | 12 |
