# MCP server tool changes

Last change observed 2026-10-02T08:08:53+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

16504 changes to a tool definition: 533 npm releases (287 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 15971 readings of hosted servers that found their tools changed; 157 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-10-02 | `remote/no.restplass/travel-search` | 2026-10-02T072151301257 -> 2026-10-02T080855420550 | 1 changed | quiet |
| 2026-10-02 | `remote/fi.akkilahdot/travel-search` | 2026-10-02T072213218147 -> 2026-10-02T080849825360 | 1 changed | quiet |
| 2026-10-02 | `remote/dk.afbudsrejser/travel-search` | 2026-10-02T072131645222 -> 2026-10-02T080835418417 | 1 changed | quiet |
| 2026-10-02 | `remote/se.sistaminuten/travel-search` | 2026-10-02T072252726202 -> 2026-10-02T080813120995 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-02T072119123931 -> 2026-10-02T080752553804 | 1 changed | quiet |
| 2026-10-02 | `remote/no.apier/mcp` | 2026-09-23T161024065434 -> 2026-10-02T080748321659 | 1 changed | quiet |
| 2026-10-02 | `remote/com.penguindriver/shop` | 2026-09-28T142518503463 -> 2026-10-02T080746086519 | 2 changed | quiet |
| 2026-10-02 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-10-02T061622185338 -> 2026-10-02T080740713367 | 15 changed | review |
| 2026-10-02 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-02T072036868325 -> 2026-10-02T080735008116 | 2 changed | quiet |
| 2026-10-02 | `remote/com.hortosapp/us` | 2026-09-28T142307850048 -> 2026-10-02T080720061941 | 1 changed | quiet |
| 2026-10-02 | `remote/com.remoshift/jobs` | 2026-10-02T072046911369 -> 2026-10-02T080718712707 | 1 changed | quiet |
| 2026-10-02 | `remote/dev.workers.panda198271.shop-compare/shop-compare` | 2026-09-28T142201515839 -> 2026-10-02T080648913308 | 2 changed | quiet |
| 2026-10-02 | `remote/xyz.pflow.sim/whatif` | 2026-10-02T061626593753 -> 2026-10-02T080627596829 | 4 changed, 2 added | quiet |
| 2026-10-02 | `remote/com.mosaiden/souq` | 2026-09-28T142404690560 -> 2026-10-02T080619464944 | 2 added | quiet |
| 2026-10-02 | `remote/science.pith/pith` | 2026-09-28T142108983875 -> 2026-10-02T080604894811 | 4 added | quiet |
| 2026-10-02 | `remote/com.vendooly/vendooly` | 2026-10-02T071931922453 -> 2026-10-02T080603234311 | 2 added | quiet |
| 2026-10-02 | `remote/io.github.JacobiusMakes/parlayapi` | 2026-09-23T160710575320 -> 2026-10-02T080534195540 | 2 changed | quiet |
| 2026-10-02 | `remote/com.shotpulled/shotpulled` | 2026-09-29T150738628104 -> 2026-10-02T080519666514 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.tareq7/muslim-prayer-mcp` | 2026-10-01T154236848434 -> 2026-10-02T080505759542 | 5 changed (every tool) | quiet |
| 2026-10-02 | `remote/app.meistron/meistron` | 2026-10-01T134032622307 -> 2026-10-02T080455917988 | 3 changed | quiet |
| 2026-10-02 | `remote/com.tkawen/intelligence-gateway` | 2026-10-02T071626542544 -> 2026-10-02T080437662318 | 1 changed | quiet |
| 2026-10-02 | `remote/com.movingplace/mcp` | 2026-09-29T100829159435 -> 2026-10-02T080403215274 | 16 added | quiet |
| 2026-10-02 | `remote/com.hergertsynthora/synthora-x402` | 2026-10-02T071538074842 -> 2026-10-02T080345659612 | 6 added, 6 removed | quiet |
| 2026-10-02 | `remote/com.aiapplyd/aiapplyd` | 2026-10-01T133810937892 -> 2026-10-02T080343280833 | 2 changed | quiet |
| 2026-10-02 | `remote/com.firmtape/spx-options-gamma` | 2026-10-01T133942072598 -> 2026-10-02T080321434655 | 2 changed | quiet |
| 2026-10-02 | `remote/com.penguindriver/hub` | 2026-09-28T170328775352 -> 2026-10-02T080215115071 | 2 changed | quiet |
| 2026-10-02 | `remote/io.github.pipeworx-io/senate-lobbying` | 2026-09-27T065722517917 -> 2026-10-02T080136824173 | 5 changed | quiet |
| 2026-10-02 | `remote/io.github.bosmdavid-gif/dropthehassle` | 2026-10-01T133445561339 -> 2026-10-02T080121109983 | 10 added | quiet |
| 2026-10-02 | `remote/com.dayze/life-context.1` | 2026-10-01T212442344311 -> 2026-10-02T080033213702 | 5 changed | quiet |
| 2026-10-02 | `remote/com.dayze/life-context` | 2026-10-01T212441448378 -> 2026-10-02T080033066013 | 5 changed | quiet |
| 2026-10-02 | `remote/cloud.dchub/mcp-server` | 2026-09-29T112749193134 -> 2026-10-02T080033662626 | 3 changed | quiet |
| 2026-10-02 | `remote/com.xonark/dental-gateway` | 2026-09-28T072451336505 -> 2026-10-02T080028616863 | 2 changed, 1 added | quiet |
| 2026-10-02 | `remote/co.bitcoinyield/yields` | 2026-09-28T141352021330 -> 2026-10-02T080024081533 | 1 changed, 1 added | quiet |
| 2026-10-02 | `remote/app.apick/convert` | 2026-10-02T061608969104 -> 2026-10-02T075954996200 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.WellApp-ai/well-mcp` | 2026-10-01T154214126537 -> 2026-10-02T075949454858 | 6 changed, 1 added | quiet |
| 2026-10-02 | `remote/io.github.santiment/santiment-mcp` | 2026-09-23T162315511997 -> 2026-10-02T075940672612 | 2 changed | quiet |
| 2026-10-02 | `remote/com.zfinia.api/intelligence` | 2026-09-30T060113887109 -> 2026-10-02T075944589945 | 17 added | quiet |
| 2026-10-02 | `remote/app.apick/all` | 2026-10-02T061604045831 -> 2026-10-02T075930947814 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.ra1labsworkx-wq/snapback` | 2026-09-23T160342756526 -> 2026-10-02T075920047655 | 23 changed (every tool) | quiet |
| 2026-10-02 | `remote/io.github.agtrepo/agtrepo-memory` | 2026-09-23T162156399907 -> 2026-10-02T075741032633 | 1 changed | quiet |
| 2026-10-02 | `remote/dev.workers.panda198271.agent-hub-tw/agent-hub` | 2026-09-28T170248094467 -> 2026-10-02T075637640646 | 2 changed | quiet |
| 2026-10-02 | `cituna-mcp` | 1.7.0 -> 1.8.0 | 6 changed | quiet |
| 2026-10-02 | `remote/io.github.chico10117/x402-preflight` | 2026-09-23T161040017811 -> 2026-10-02T072257096948 | 3 changed (every tool) | quiet |
| 2026-10-02 | `remote/se.sistaminuten/travel-search` | 2026-10-02T061636515684 -> 2026-10-02T072252726202 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.rt1966/showmestepbystep` | 2026-09-23T161035380357 -> 2026-10-02T072250943671 | 1 changed | quiet |
| 2026-10-02 | `remote/ai.snowsure/snow` | 2026-09-24T202704400360 -> 2026-10-02T072251806076 | 1 added | quiet |
| 2026-10-02 | `remote/coach.marian/mentoring-inquiry-builder` | 2026-09-23T161031050750 -> 2026-10-02T072246016410 | 5 changed | quiet |
| 2026-10-02 | `remote/ai.robowrite/mcp` | 2026-09-23T162953191924 -> 2026-10-02T072235554913 | 2 changed | quiet |
| 2026-10-02 | `remote/io.engineeringleaders/elc-partnership-builder` | 2026-09-24T202655923639 -> 2026-10-02T072234082445 | 1 changed | quiet |
| 2026-10-02 | `remote/com.contrie/contrie` | 2026-09-30T152244732004 -> 2026-10-02T072230665802 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.Licium-ai/licium` | 2026-09-23T162946342030 -> 2026-10-02T072229433259 | 26 changed, 60 added (every tool) | review |
| 2026-10-02 | `remote/tennis.courts/nyc-tennis-courts` | 2026-09-23T162937708904 -> 2026-10-02T072219137385 | 3 changed, 1 added (every tool) | quiet |
| 2026-10-02 | `remote/fi.akkilahdot/travel-search` | 2026-10-02T061630947282 -> 2026-10-02T072213218147 | 1 changed | quiet |
| 2026-10-02 | `remote/com.thetempleofdoom.vega-mcp/vega` | 2026-09-28T142249342400 -> 2026-10-02T072208075108 | 1 added | quiet |
| 2026-10-02 | `remote/io.github.TRDEFI/liquidity` | 2026-09-29T210512724738 -> 2026-10-02T072204798265 | 6 changed (every tool) | quiet |
| 2026-10-02 | `remote/world.agentindex/x402` | 2026-10-01T134300034905 -> 2026-10-02T072221943997 | 27 added | quiet |
| 2026-10-02 | `remote/net.totallytarot/calculators` | 2026-09-23T160956096351 -> 2026-10-02T072153895302 | 1 changed | quiet |
| 2026-10-02 | `remote/no.restplass/travel-search` | 2026-10-02T061630369874 -> 2026-10-02T072151301257 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.coltongriffith/explorationmaps` | 2026-09-23T163131280321 -> 2026-10-02T072138210031 | 1 changed | quiet |
| 2026-10-02 | `remote/io.deeplead/deeplead` | 2026-09-28T142304084137 -> 2026-10-02T072136078915 | 9 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 13050 substantive, 3229 that changed only numbers (a catalogue counter ticking, a date), 225 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 8602 | 5627 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `caseyjhand.com` | 66 | 66 | 0 | 0 |
| `sistaminuten.se` | 56 | 2 | 0 | 54 |
| `afbudsrejser.dk` | 55 | 2 | 0 | 53 |
| `akkilahdot.fi` | 55 | 2 | 0 | 53 |
| `restplass.no` | 55 | 2 | 0 | 53 |
| `socialloop.ai` | 54 | 54 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| `dayze.com` | 47 | 47 | 0 | 0 |
| 1782 other operators | 4601 | 4335 | 254 | 12 |
