# MCP server tool changes

Last change observed 2026-11-22T22:10:50+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

127129 changes to a tool definition: 5105 npm releases (4859 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 122024 readings of hosted servers that found their tools changed; 4688 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Licence: this project's own data (measurements, dates, grades, counts, digests, checkpoints) is [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The tool definitions recorded here are the servers' own text and remain their authors'; to ask for something to be removed, open an issue.

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps and signed with Sigstore: [checkpoints/](checkpoints). To check a day, rebuild the manifest of the commit it names, compare it with `manifest_sha256`, then verify the proof (the full steps, and what each one trusts, are in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints)):

```bash
day=2026-09-28
commit=$(python3 -c "import json; print(json.load(open('checkpoints/$day.json'))['feed_commit'])")
mkdir ../at && git -c core.autocrlf=false archive "$commit" | tar -x -C ../at
(cd ../at && find . -type f ! -path './checkpoints/*' -printf '%P\0' \
  | LC_ALL=C sort -z | xargs -0 sha256sum | sha256sum)   # = manifest_sha256
pip install opentimestamps-client && ots verify checkpoints/$day.json.ots
```

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-11-22 | `remote/io.suverse.www/catalog` | 2026-11-22T164203441615 -> 2026-11-22T221052053443 | 3 changed | quiet |
| 2026-11-22 | `remote/se.sistaminuten/travel-search` | 2026-11-22T164202469899 -> 2026-11-22T221050649641 | 1 changed | quiet |
| 2026-11-22 | `remote/org.omenz.www/agent-tools` | 2026-11-22T164201624480 -> 2026-11-22T221050338696 | 2 changed, 7 added | quiet |
| 2026-11-22 | `remote/com.herbertandphyllis/mcp` | 2026-11-22T073205411564 -> 2026-11-22T221048409448 | 1 changed | quiet |
| 2026-11-22 | `remote/com.entangleeq/pay-transparency` | 2026-11-21T151052581908 -> 2026-11-22T221048220950 | 5 changed (every tool) | quiet |
| 2026-11-22 | `remote/studio.gradients/mcp` | 2026-11-22T164202478506 -> 2026-11-22T221047910811 | 1 changed | quiet |
| 2026-11-22 | `remote/io.atilab/mcp` | 2026-11-22T150504873015 -> 2026-11-22T221046416025 | 7 changed | quiet |
| 2026-11-22 | `remote/fi.akkilahdot/travel-search` | 2026-11-22T164200917183 -> 2026-11-22T221046666683 | 1 changed | quiet |
| 2026-11-22 | `remote/com.blitzreels/blitzreels` | 2026-11-22T104630613687 -> 2026-11-22T221047249755 | 1 changed | quiet |
| 2026-11-22 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-22T073231520588 -> 2026-11-22T221047009948 | 10 changed (every tool) | quiet |
| 2026-11-22 | `remote/io.github.christianscode1994/volatiai` | 2026-11-22T150431662375 -> 2026-11-22T221044568093 | 1 added | quiet |
| 2026-11-22 | `remote/io.github.bostanyshop-rgb/growtsy` | 2026-11-22T073257039135 -> 2026-11-22T221044766143 | 5 changed, 10 removed | quiet |
| 2026-11-22 | `remote/com.weverlabs/agentic-rails` | 2026-11-22T073237515636 -> 2026-11-22T221052257976 | 16 added | quiet |
| 2026-11-22 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-22T164159444715 -> 2026-11-22T221045321180 | 3 changed | quiet |
| 2026-11-22 | `remote/com.wecookflow/mcp` | 2026-11-21T151112343201 -> 2026-11-22T221044516771 | 2 added | quiet |
| 2026-11-22 | `remote/io.suverse.versum/catalog` | 2026-11-22T164158164785 -> 2026-11-22T221043920249 | 3 changed | quiet |
| 2026-11-22 | `remote/io.github.1145-am/syracuse-mcp-server` | 2026-11-22T150633301401 -> 2026-11-22T221040355626 | 3 changed, 3 added, 1 removed (every tool) | quiet |
| 2026-11-22 | `remote/io.github.pugarte7/spanish-top-tech-companies` | 2026-11-22T150235263645 -> 2026-11-22T221038840084 | 2 changed | quiet |
| 2026-11-22 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-22T164150461007 -> 2026-11-22T221037686100 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.Embassy-of-the-Free-Mind/sourcelibrary` | 2026-11-21T014906700928 -> 2026-11-22T221038042233 | 1 changed | quiet |
| 2026-11-22 | `remote/io.shiptrail/shiptrail` | 2026-11-22T073222752465 -> 2026-11-22T221036643114 | 1 changed | quiet |
| 2026-11-22 | `remote/com.serviche/sergio` | 2026-11-22T073228190977 -> 2026-11-22T221037882151 | 2 changed | quiet |
| 2026-11-22 | `remote/com.innergcomplete/shearquery` | 2026-11-22T104056855251 -> 2026-11-22T221036049327 | 39 changed | quiet |
| 2026-11-22 | `remote/si.scriptura/scriptura` | 2026-11-21T150723775351 -> 2026-11-22T221034741635 | 4 changed, 1 added | quiet |
| 2026-11-22 | `remote/com.kyde/score` | 2026-11-21T150757232704 -> 2026-11-22T221036246687 | 1 changed, 1 added | quiet |
| 2026-11-22 | `remote/com.remoshift/jobs` | 2026-11-22T073220030044 -> 2026-11-22T221033022371 | 1 changed | quiet |
| 2026-11-22 | `remote/gg.plazmi/plazmi` | 2026-11-20T074922050698 -> 2026-11-22T221031545778 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.farenberglord-star/orb-studio` | 2026-11-22T164142831835 -> 2026-11-22T221029209833 | 2 changed, 12 added | quiet |
| 2026-11-22 | `remote/io.github.OptimNow/ai-pricing-hub` | 2026-11-22T150232195057 -> 2026-11-22T221029117589 | 3 changed | quiet |
| 2026-11-22 | `remote/gg.pixly/mcp` | 2026-11-21T150648819341 -> 2026-11-22T221033077788 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.sudzikcoin/suverse-agent-assistant` | 2026-11-22T164200438871 -> 2026-11-22T221028357623 | 3 changed | quiet |
| 2026-11-22 | `remote/com.theservicemarketingguys/audit` | 2026-11-21T151130661862 -> 2026-11-22T221027198358 | 7 changed (every tool) | quiet |
| 2026-11-22 | `remote/com.starcovery/mcp` | 2026-11-22T104450193513 -> 2026-11-22T221026895397 | 17 changed, 4 removed | quiet |
| 2026-11-22 | `remote/com.moon-oh/moonoh-marketplace` | 2026-11-21T215711501010 -> 2026-11-22T221027202209 | 2 added | quiet |
| 2026-11-22 | `remote/no.restplass/travel-search` | 2026-11-22T164159779653 -> 2026-11-22T221027242502 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.Red-Center-Studio/nocode-migrator` | 2026-11-22T073243715472 -> 2026-11-22T221026249015 | 5 changed | quiet |
| 2026-11-22 | `remote/com.mylatinlife/data` | 2026-11-22T150151953418 -> 2026-11-22T221027064252 | 4 changed, 4 added | quiet |
| 2026-11-22 | `remote/com.kulicadvisory/aictionbot-werkbank` | 2026-11-22T164158580326 -> 2026-11-22T221025873204 | 1 changed | quiet |
| 2026-11-22 | `remote/today.nyangi/oneul-nyangi` | 2026-11-22T145941068323 -> 2026-11-22T221026441800 | 1 changed | quiet |
| 2026-11-22 | `remote/com.meettempi/tempi` | 2026-11-22T164137848334 -> 2026-11-22T221025839305 | 2 changed | quiet |
| 2026-11-22 | `remote/dk.afbudsrejser/travel-search` | 2026-11-22T164157668417 -> 2026-11-22T221024592329 | 1 changed | quiet |
| 2026-11-22 | `remote/com.merarobotics/mera` | 2026-11-21T215643561946 -> 2026-11-22T221025025697 | 7 changed | quiet |
| 2026-11-22 | `remote/io.github.ohad6k/viberaven-guides` | 2026-11-21T130555413298 -> 2026-11-22T221023659702 | 3 changed, 3 added | quiet |
| 2026-11-22 | `remote/com.multicinesortega/cartelera` | 2026-11-22T073212974866 -> 2026-11-22T221024730518 | 1 changed | quiet |
| 2026-11-22 | `remote/org.worldgdp/nowcasts` | 2026-11-20T155234157452 -> 2026-11-22T221022023424 | 1 changed, 1 added | quiet |
| 2026-11-22 | `remote/org.walkably/walkably` | 2026-11-22T150047813974 -> 2026-11-22T221021955631 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-11-22T073144817397 -> 2026-11-22T221021369380 | 1 changed | review |
| 2026-11-22 | `remote/io.github.ivaavimusic/singularity` | 2026-11-22T164135288105 -> 2026-11-22T221022319513 | 1 changed | quiet |
| 2026-11-22 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-22T164136326261 -> 2026-11-22T221022855022 | 15 changed | quiet |
| 2026-11-22 | `remote/com.metricduck/financial-analysis` | 2026-11-21T014743914589 -> 2026-11-22T221020771664 | 3 changed | quiet |
| 2026-11-22 | `remote/com.sonarconnections/sonar-connections` | 2026-11-22T103756746892 -> 2026-11-22T221021044509 | 3 changed | quiet |
| 2026-11-22 | `remote/io.insourcia/insourcia` | 2026-11-20T104743956025 -> 2026-11-22T221019440593 | 2 changed | quiet |
| 2026-11-22 | `remote/com.toiseai/toise` | 2026-11-22T164133752710 -> 2026-11-22T221019707666 | 45 changed, 1 added | quiet |
| 2026-11-22 | `remote/io.github.streamloop/mcp` | 2026-11-20T155619297109 -> 2026-11-22T221018111481 | 1 changed | quiet |
| 2026-11-22 | `remote/dev.qrdx/qrdx` | 2026-11-22T103656908908 -> 2026-11-22T221017321243 | 5 changed, 1 added | quiet |
| 2026-11-22 | `remote/com.straelo/relay` | 2026-11-22T073141272577 -> 2026-11-22T221015609759 | 5 changed | quiet |
| 2026-11-22 | `remote/com.radarbg/radar-tools` | 2026-11-22T103953411551 -> 2026-11-22T221016063424 | 5 added | quiet |
| 2026-11-22 | `remote/com.ortexo/mcp` | 2026-11-22T164129972718 -> 2026-11-22T221016256199 | 2 changed | quiet |
| 2026-11-22 | `remote/tech.kaiku/kaiku.1` | 2026-11-22T164130447420 -> 2026-11-22T221017108558 | 3 changed | quiet |
| 2026-11-22 | `remote/io.github.Playpowerpolitics/powerplayers` | 2026-11-22T073139528477 -> 2026-11-22T221013331140 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 82929 substantive, 43031 that changed only numbers (a catalogue counter ticking, a date), 1169 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 69283 | 29077 | 40206 | 0 |
| `a2awire.com` | 3571 | 3571 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 516 | 516 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 401 | 401 | 0 | 0 |
| `revmesh2074.workers.dev` | 361 | 307 | 54 | 0 |
| `sistaminuten.se` | 272 | 6 | 0 | 266 |
| `afbudsrejser.dk` | 271 | 6 | 0 | 265 |
| `akkilahdot.fi` | 271 | 6 | 0 | 265 |
| `restplass.no` | 271 | 6 | 0 | 265 |
| `socialloop.ai` | 262 | 262 | 0 | 0 |
| 10827 other operators | 48829 | 45950 | 2771 | 108 |
