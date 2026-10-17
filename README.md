# MCP server tool changes

Last change observed 2026-10-17T11:12:40+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10495 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 23695 hosted endpoints (read daily, and every four hours while they keep changing).

30157 changes to a tool definition: 1052 npm releases (806 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 29105 readings of hosted servers that found their tools changed; 2052 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-17 | `remote/com.immersivecommons/floor10` | 2026-10-17T055942283508 -> 2026-10-17T111242113497 | 1 added | quiet |
| 2026-10-17 | `remote/fi.akkilahdot/travel-search` | 2026-10-17T073756919270 -> 2026-10-17T111223508210 | 1 changed | quiet |
| 2026-10-17 | `remote/us.srv.vehcdj664efetfrsolne5umanq/quoteproof-mcp` | 2026-10-17T055900696034 -> 2026-10-17T111205518506 | 2 changed | quiet |
| 2026-10-17 | `remote/tech.varexis/varexis-index` | 2026-10-17T055858903246 -> 2026-10-17T111203065169 | 3 changed | quiet |
| 2026-10-17 | `remote/io.github.sharan01x/usetested` | 2026-10-08T135434290106 -> 2026-10-17T111201777627 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-17T070501096067 -> 2026-10-17T111142660726 | 1 changed | quiet |
| 2026-10-17 | `remote/dev.tanod/web` | 2026-10-17T055831144409 -> 2026-10-17T111139383155 | 2 changed, 1 added | quiet |
| 2026-10-17 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-17T073625757198 -> 2026-10-17T111120466946 | 1 changed | quiet |
| 2026-10-17 | `remote/com.remoshift/jobs` | 2026-10-17T055724591090 -> 2026-10-17T111045869207 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.KilianPA/pryx` | 2026-10-01T134412843726 -> 2026-10-17T111036382255 | 3 changed (every tool) | quiet |
| 2026-10-17 | `remote/io.taifoon/coordination-layer.1` | 2026-10-17T055621073833 -> 2026-10-17T111001609046 | 1 changed | quiet |
| 2026-10-17 | `remote/se.sistaminuten/travel-search` | 2026-10-17T073406621083 -> 2026-10-17T110958870396 | 1 changed | quiet |
| 2026-10-17 | `remote/com.neblla/neblla` | 2026-10-17T055614157185 -> 2026-10-17T110949926368 | 2 changed | quiet |
| 2026-10-17 | `remote/com.multicinesortega/cartelera` | 2026-10-17T055610994225 -> 2026-10-17T110947919257 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.zambodotdev/zambo` | 2026-10-17T060428488218 -> 2026-10-17T110941336243 | 35 changed (every tool) | quiet |
| 2026-10-17 | `remote/dev.zambo/zambo` | 2026-10-17T060428448690 -> 2026-10-17T110941698410 | 35 changed (every tool) | quiet |
| 2026-10-17 | `remote/dev.mearef/reference-data` | 2026-10-17T055558477439 -> 2026-10-17T110940161112 | 15 changed | review |
| 2026-10-17 | `remote/de.vonfrauen/vonfrauen` | 2026-10-17T060419122084 -> 2026-10-17T110935488805 | 2 changed | quiet |
| 2026-10-17 | `remote/app.soclo/soclo-mcp` | 2026-10-17T055524927218 -> 2026-10-17T110906224056 | 22 changed, 3 added | quiet |
| 2026-10-17 | `remote/io.github.octoco-ltd/sheetsdata-mcp` | 2026-10-17T055521052802 -> 2026-10-17T110902377897 | 13 changed | quiet |
| 2026-10-17 | `remote/com.starcovery/mcp` | 2026-10-17T060456118682 -> 2026-10-17T110838885839 | 10 changed | quiet |
| 2026-10-17 | `remote/no.restplass/travel-search` | 2026-10-17T073545660609 -> 2026-10-17T110834953229 | 1 changed | quiet |
| 2026-10-17 | `remote/com.minimindslab.mcp/tools` | 2026-10-03T121216835333 -> 2026-10-17T110832699479 | 1 added | quiet |
| 2026-10-17 | `remote/io.github.openaccountants/openaccountants` | 2026-10-17T060449812765 -> 2026-10-17T110831681288 | 1 changed | quiet |
| 2026-10-17 | `remote/ai.mapmap/mapmap` | 2026-10-17T055439872368 -> 2026-10-17T110827799112 | 3 added | quiet |
| 2026-10-17 | `remote/com.kernelcad/kernelcad` | 2026-10-17T055428271841 -> 2026-10-17T110820133230 | 3 changed | quiet |
| 2026-10-17 | `remote/ch.antevo/trademark` | 2026-09-23T160816425641 -> 2026-10-17T110815914080 | 1 changed | quiet |
| 2026-10-17 | `remote/dev.tanod/tanod` | 2026-10-17T055502356611 -> 2026-10-17T110810849596 | 9 changed, 11 added | quiet |
| 2026-10-17 | `remote/dev.tanod/docs` | 2026-10-17T055501493567 -> 2026-10-17T110808455762 | 3 changed | quiet |
| 2026-10-17 | `remote/dev.tanod/agents` | 2026-10-17T055501559486 -> 2026-10-17T110809526863 | 2 changed, 7 added | quiet |
| 2026-10-17 | `remote/dk.afbudsrejser/travel-search` | 2026-10-17T073511803747 -> 2026-10-17T110803672697 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.witanmarkets/witan` | 2026-10-17T060417729735 -> 2026-10-17T110759179895 | 3 changed | quiet |
| 2026-10-17 | `remote/dev.tanod/util` | 2026-10-17T060225672621 -> 2026-10-17T110758080532 | 3 changed, 3 added | quiet |
| 2026-10-17 | `remote/dev.tanod/images` | 2026-10-17T060224413309 -> 2026-10-17T110757086635 | 2 changed, 1 added | quiet |
| 2026-10-17 | `remote/world.staylist/staylist` | 2026-10-17T060209250502 -> 2026-10-17T110743292913 | 1 added | quiet |
| 2026-10-17 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-17T060201448088 -> 2026-10-17T110736858169 | 2 changed | quiet |
| 2026-10-17 | `remote/dev.usaref/reference-data` | 2026-10-17T060402857259 -> 2026-10-17T110736355122 | 15 changed | review |
| 2026-10-17 | `remote/xyz.trusteed/mcp-gateway` | 2026-10-17T060353694288 -> 2026-10-17T110728472302 | 16 changed | quiet |
| 2026-10-17 | `remote/com.santismm/knowledge` | 2026-09-23T160737785777 -> 2026-10-17T110704357796 | 12 changed, 1 added | quiet |
| 2026-10-17 | `remote/cz.robotio/event-robots` | 2026-10-17T060116314104 -> 2026-10-17T110658918637 | 1 changed | quiet |
| 2026-10-17 | `remote/com.adrianhomelab/leadgen-onrc` | 2026-10-17T055247761112 -> 2026-10-17T110655945653 | 16 changed (every tool) | quiet |
| 2026-10-17 | `remote/io.github.89rat/code402` | 2026-10-17T060104461804 -> 2026-10-17T110645904710 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.alfongj-com/yo` | 2026-09-23T162513207311 -> 2026-10-17T110611816843 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.pipeworx-io/yelp` | 2026-10-01T133941059634 -> 2026-10-17T110605708955 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.pipeworx-io/worms` | 2026-10-01T133940626095 -> 2026-10-17T110603176388 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.pipeworx-io/worldbank-poverty` | 2026-10-01T133940180661 -> 2026-10-17T110602377388 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.pipeworx-io/woocommerce` | 2026-09-27T065544914498 -> 2026-10-17T110602037371 | 9 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.pipeworx-io/wikidata` | 2026-10-01T133939744617 -> 2026-10-17T110600296740 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/com.oceanalt/aml` | 2026-10-17T070307231710 -> 2026-10-17T110559701923 | 3 changed | quiet |
| 2026-10-17 | `remote/io.github.pipeworx-io/wi-dmv` | 2026-10-01T133939417188 -> 2026-10-17T110600166975 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.pipeworx-io/walkscore` | 2026-10-05T061612256997 -> 2026-10-17T110556475227 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.pipeworx-io/visa-requirements` | 2026-10-01T133938713136 -> 2026-10-17T110555201117 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.pipeworx-io/vessel-tracking` | 2026-10-06T105709642819 -> 2026-10-17T110555066461 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.pipeworx-io/vc-finder` | 2026-10-06T105709509780 -> 2026-10-17T110553628385 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.pipeworx-io/vaers` | 2026-10-06T105709481591 -> 2026-10-17T110552936346 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.pipeworx-io/va-museum` | 2026-10-06T105709405418 -> 2026-10-17T110550621050 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.pipeworx-io/usitc-edis` | 2026-10-01T133937615144 -> 2026-10-17T110550540782 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.pipeworx-io/usgs-water` | 2026-10-06T105709134519 -> 2026-10-17T110548411082 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.pipeworx-io/usgs-volcano` | 2026-10-06T105708971910 -> 2026-10-17T110548358490 | 8 changed, 5 added | review |
| 2026-10-17 | `remote/io.github.pipeworx-io/usgs-mrdata` | 2026-10-06T105708674005 -> 2026-10-17T110546926185 | 8 changed, 5 added | review |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 21583 substantive, 8132 that changed only numbers (a catalogue counter ticking, a date), 442 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 14726 | 7201 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 126 | 126 | 0 | 0 |
| `sistaminuten.se` | 107 | 4 | 0 | 103 |
| `afbudsrejser.dk` | 106 | 4 | 0 | 102 |
| `akkilahdot.fi` | 106 | 4 | 0 | 102 |
| `restplass.no` | 106 | 4 | 0 | 102 |
| `socialloop.ai` | 104 | 104 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `fundinglandscape.com` | 77 | 45 | 32 | 0 |
| `remoshift.com` | 77 | 4 | 73 | 0 |
| 3767 other operators | 11531 | 10996 | 502 | 33 |
