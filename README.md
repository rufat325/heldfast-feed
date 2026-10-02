# MCP server tool changes

Last change observed 2026-10-02T07:22:56+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9712 npm servers from the official MCP registry (154 daily, the rest weekly) and 19746 hosted endpoints (daily).

16462 changes to a tool definition: 532 npm releases (286 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 15930 readings of hosted servers that found their tools changed; 156 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
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
| 2026-10-02 | `remote/dk.afbudsrejser/travel-search` | 2026-10-02T061629511440 -> 2026-10-02T072131645222 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-02T061625513796 -> 2026-10-02T072119123931 | 1 changed | quiet |
| 2026-10-02 | `remote/watch.sbox/sbox-watch` | 2026-10-01T212508879298 -> 2026-10-02T072117989257 | 3 changed | quiet |
| 2026-10-02 | `remote/io.github.CWNApps/trust-gate-mcp` | 2026-09-23T163051347911 -> 2026-10-02T072108952031 | 4 changed, 3 added (every tool) | quiet |
| 2026-10-02 | `remote/com.seqbench/workbench` | 2026-09-29T150800476128 -> 2026-10-02T072107887128 | 1 changed | quiet |
| 2026-10-02 | `remote/com.jbpscapital.tideline/tideline` | 2026-09-28T142221545816 -> 2026-10-02T072058880277 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.leshchenko1979/fast-mcp-telegram` | 2026-09-26T045402581458 -> 2026-10-02T072056526680 | 2 changed | quiet |
| 2026-10-02 | `remote/io.github.jaymiller-cmg/mortgage-hawaii` | 2026-09-29T003609673422 -> 2026-10-02T072053673785 | 1 added | quiet |
| 2026-10-02 | `remote/com.remoshift/jobs` | 2026-10-02T061624074229 -> 2026-10-02T072046911369 | 1 changed | quiet |
| 2026-10-02 | `remote/com.googleapis.sqladmin/mcp` | 2026-09-23T163011781212 -> 2026-10-02T072036868325 | 2 changed | quiet |
| 2026-10-02 | `remote/ch.servicekuhn/service-rechner` | 2026-09-28T142147139226 -> 2026-10-02T072028701989 | 1 changed | quiet |
| 2026-10-02 | `remote/com.pickadive/mcp` | 2026-09-23T162816611460 -> 2026-10-02T072023626426 | 2 changed | quiet |
| 2026-10-02 | `remote/com.scenef/showtimes` | 2026-09-23T162952531262 -> 2026-10-02T072017364242 | 10 changed (every tool) | quiet |
| 2026-10-02 | `remote/io.github.sam1siam/ruagentic-directory` | 2026-09-23T162948291741 -> 2026-10-02T072013289036 | 1 changed | quiet |
| 2026-10-02 | `remote/io.github.marcioyoshida/outage-me` | 2026-09-28T142425266445 -> 2026-10-02T072013127559 | 1 added | quiet |
| 2026-10-02 | `remote/ing.rentseek/evidence` | 2026-09-23T162940585564 -> 2026-10-02T072006422886 | 1 changed | quiet |
| 2026-10-02 | `remote/ai.msza/polish-catholic-sermons` | 2026-09-23T160839497953 -> 2026-10-02T072002035128 | 2 changed | quiet |
| 2026-10-02 | `remote/io.github.Baffles78/viewport-witness` | 2026-09-28T142104598935 -> 2026-10-02T071957462756 | 6 changed (every tool) | quiet |
| 2026-10-02 | `remote/io.github.naief9961-tech/naif-fixgraph` | 2026-09-28T142409284618 -> 2026-10-02T071955548346 | 4 added | quiet |
| 2026-10-02 | `remote/io.github.linxule/mcp-music-studio` | 2026-09-27T065639398311 -> 2026-10-02T071953196326 | 2 changed | quiet |
| 2026-10-02 | `remote/io.github.medley/fda-data` | 2026-09-23T160851169016 -> 2026-10-02T071946183740 | 2 changed, 2 removed | quiet |
| 2026-10-02 | `remote/com.sonarconnections/sonar-connections` | 2026-09-29T003557667705 -> 2026-10-02T071938019819 | 12 changed, 1 added, 1 removed | quiet |
| 2026-10-02 | `remote/io.github.joeyaflores/ourpr-courses` | 2026-09-29T003611314228 -> 2026-10-02T071934851037 | 3 changed | quiet |
| 2026-10-02 | `remote/com.tripways/tours` | 2026-09-29T003557617155 -> 2026-10-02T071926717654 | 6 changed (every tool) | quiet |
| 2026-10-02 | `remote/io.github.isaacaskew/venunite-events` | 2026-09-28T073023023780 -> 2026-10-02T071920818146 | 2 changed (every tool) | quiet |
| 2026-10-02 | `remote/io.github.Travisswop/swop` | 2026-09-23T162731670776 -> 2026-10-02T071919745629 | 7 changed, 16 added | review |
| 2026-10-02 | `remote/online.webring/ring` | 2026-09-23T160828990265 -> 2026-10-02T071915423288 | 2 changed | quiet |
| 2026-10-02 | `remote/ai.muffed/muffed` | 2026-09-23T162843035554 -> 2026-10-02T071911268680 | 1 changed, 1 added | quiet |
| 2026-10-02 | `remote/ai.tensorfeed/mcp-server` | 2026-09-23T160759131184 -> 2026-10-02T071907411227 | 1 changed | quiet |
| 2026-10-02 | `remote/com.supovia/supovia` | 2026-09-28T073009402955 -> 2026-10-02T071904748005 | 1 added | quiet |
| 2026-10-02 | `remote/de.ugc-vz/creator-search` | 2026-09-23T160819618698 -> 2026-10-02T071902137557 | 1 changed | quiet |
| 2026-10-02 | `remote/com.makometrics/mako-metrics` | 2026-09-23T160818446686 -> 2026-10-02T071859516632 | 16 changed (every tool) | quiet |
| 2026-10-02 | `remote/io.github.RidioDevelopment/socialcrawl` | 2026-09-23T160752938233 -> 2026-10-02T071857182936 | 6 changed | quiet |
| 2026-10-02 | `remote/com.trustycap/trustycap` | 2026-10-02T061618110454 -> 2026-10-02T071851370949 | 3 changed | quiet |
| 2026-10-02 | `remote/com.toolfound/toolfound` | 2026-09-23T160812518768 -> 2026-10-02T071850177159 | 2 changed, 10 added | quiet |
| 2026-10-02 | `remote/io.polyblog/polyblog` | 2026-09-28T072943143450 -> 2026-10-02T071840480548 | 4 changed, 1 added | quiet |
| 2026-10-02 | `remote/io.github.smarterweather/weather` | 2026-09-24T205326500544 -> 2026-10-02T071839763866 | 3 changed, 1 added | quiet |
| 2026-10-02 | `remote/io.github.Smartoire/paxaver-mcp` | 2026-09-23T160739919421 -> 2026-10-02T071836783178 | 1 changed, 20 added, 25 removed | quiet |
| 2026-10-02 | `remote/services.ottoai/otto` | 2026-09-28T055519188157 -> 2026-10-02T071835007631 | 9 added | review |
| 2026-10-02 | `remote/immo.rundum/real-estate-appraisal` | 2026-09-23T162803324136 -> 2026-10-02T071833269289 | 2 changed, 3 added (every tool) | quiet |
| 2026-10-02 | `remote/io.github.quotor/home-auto-insurance-quotes` | 2026-09-23T162759246329 -> 2026-10-02T071829348977 | 11 changed, 1 added (every tool) | quiet |
| 2026-10-02 | `remote/com.multilocale/multilocale` | 2026-09-28T072857066791 -> 2026-10-02T071809016356 | 1 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 13014 substantive, 3227 that changed only numbers (a catalogue counter ticking, a date), 221 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 8601 | 5626 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `caseyjhand.com` | 66 | 66 | 0 | 0 |
| `sistaminuten.se` | 55 | 2 | 0 | 53 |
| `afbudsrejser.dk` | 54 | 2 | 0 | 52 |
| `akkilahdot.fi` | 54 | 2 | 0 | 52 |
| `restplass.no` | 54 | 2 | 0 | 52 |
| `socialloop.ai` | 53 | 53 | 0 | 0 |
| `daedalmap.com` | 51 | 51 | 0 | 0 |
| `dayze.com` | 45 | 45 | 0 | 0 |
| 1772 other operators | 4567 | 4303 | 252 | 12 |
