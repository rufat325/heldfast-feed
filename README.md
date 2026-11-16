# MCP server tool changes

Last change observed 2026-11-16T19:01:45+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

107625 changes to a tool definition: 4382 npm releases (4136 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 103243 readings of hosted servers that found their tools changed; 4223 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-16 | `remote/studio.gradients/mcp` | 2026-11-16T163204666925 -> 2026-11-16T190149058392 | 1 changed | quiet |
| 2026-11-16 | `remote/io.suverse.www/catalog` | 2026-11-16T163252712645 -> 2026-11-16T190148372526 | 1 changed | quiet |
| 2026-11-16 | `remote/se.sistaminuten/travel-search` | 2026-11-16T163252426131 -> 2026-11-16T190145638745 | 1 changed | quiet |
| 2026-11-16 | `remote/com.ortopedialowcost/ortopedia-catalog` | 2026-11-16T163235809922 -> 2026-11-16T190145114279 | 5 changed (every tool) | quiet |
| 2026-11-16 | `remote/fi.akkilahdot/travel-search` | 2026-11-16T163136000031 -> 2026-11-16T190139473791 | 1 changed | quiet |
| 2026-11-16 | `remote/com.weverlabs/agentic-rails` | 2026-11-16T163120550339 -> 2026-11-16T190141496226 | 8 added | quiet |
| 2026-11-16 | `remote/ai.arcreport/ask` | 2026-11-16T163154380753 -> 2026-11-16T190136029530 | 2 changed | quiet |
| 2026-11-16 | `remote/dev.vetagent/vetagent` | 2026-11-16T163056199629 -> 2026-11-16T190133798077 | 2 changed | quiet |
| 2026-11-16 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-16T123013215030 -> 2026-11-16T190133210593 | 1 changed | quiet |
| 2026-11-16 | `remote/io.github.mastercobeos/tlacuilo` | 2026-11-16T163006699252 -> 2026-11-16T190122399826 | 10 added | quiet |
| 2026-11-16 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-16T122924389170 -> 2026-11-16T190122105934 | 2 changed | quiet |
| 2026-11-16 | `remote/io.github.ofir09/tendy` | 2026-11-16T162949640441 -> 2026-11-16T190120682608 | 2 changed | quiet |
| 2026-11-16 | `remote/com.eliteaiempire/th-api` | 2026-11-16T162946723977 -> 2026-11-16T190119546195 | 1 changed | quiet |
| 2026-11-16 | `remote/health.telo/telo` | 2026-11-16T122750737770 -> 2026-11-16T190117958696 | 1 changed | quiet |
| 2026-11-16 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-16T162901894684 -> 2026-11-16T190113545669 | 1 changed | quiet |
| 2026-11-16 | `remote/finance.souvenir/coins` | 2026-11-16T162905997662 -> 2026-11-16T190114377415 | 8 changed, 1 added | quiet |
| 2026-11-16 | `remote/com.simplehouseplanner/floor-plans` | 2026-11-16T162846430360 -> 2026-11-16T190111949899 | 37 changed (every tool) | quiet |
| 2026-11-16 | `remote/io.github.QDThead/signal-lab` | 2026-11-14T010654827746 -> 2026-11-16T190110564075 | 2 added | quiet |
| 2026-11-16 | `remote/io.github.davidgringras/scrutica` | 2026-11-15T115325599463 -> 2026-11-16T190110266149 | 1 changed | quiet |
| 2026-11-16 | `remote/network.luca/luca-public` | 2026-11-16T162805497134 -> 2026-11-16T190105349835 | 4 changed (every tool) | quiet |
| 2026-11-16 | `remote/com.eliteaiempire/soccer` | 2026-11-16T162858861112 -> 2026-11-16T190106407347 | 1 changed | quiet |
| 2026-11-16 | `remote/com.remoshift/jobs` | 2026-11-16T162742817785 -> 2026-11-16T190102828514 | 1 changed | quiet |
| 2026-11-16 | `remote/com.qhooks/mcp` | 2026-11-16T162726779069 -> 2026-11-16T190101369939 | 31 changed (every tool) | quiet |
| 2026-11-16 | `remote/io.suverse.versum/catalog` | 2026-11-16T122805409062 -> 2026-11-16T190100840448 | 1 changed | quiet |
| 2026-11-16 | `remote/com.trygoppa/goppa` | 2026-11-15T115622174995 -> 2026-11-16T190056010568 | 2 changed | quiet |
| 2026-11-16 | `remote/xyz.tripgenius/tripgenius` | 2026-11-16T163135733417 -> 2026-11-16T190056731836 | 4 added | quiet |
| 2026-11-16 | `remote/io.github.Fractal-Neurons/pacta` | 2026-11-16T162629110853 -> 2026-11-16T190052818440 | 7 changed (every tool) | quiet |
| 2026-11-16 | `remote/dev.workers.rugsight.rugsight/rugsight` | 2026-11-16T122626355623 -> 2026-11-16T190053077893 | 1 added | review |
| 2026-11-16 | `remote/com.toolfound/toolfound` | 2026-11-15T155605631048 -> 2026-11-16T190052496155 | 2 changed | review |
| 2026-11-16 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-16T072306712183 -> 2026-11-16T190053437758 | 1 added | quiet |
| 2026-11-16 | `remote/io.github.cronus42/ibc-mcp` | 2026-11-16T162747322517 -> 2026-11-16T190047867898 | 2 changed | quiet |
| 2026-11-16 | `remote/il.co.taseli/taseli.1` | 2026-11-14T135932840858 -> 2026-11-16T190048593848 | 1 changed | quiet |
| 2026-11-16 | `remote/org.myaiceo/myaiceo` | 2026-11-16T162537265932 -> 2026-11-16T190046623323 | 4 added | quiet |
| 2026-11-16 | `remote/io.github.t0ll-xyz/toll` | 2026-11-16T163039971214 -> 2026-11-16T190046268434 | 10 changed | quiet |
| 2026-11-16 | `remote/pl.finwire/data` | 2026-11-16T072155880517 -> 2026-11-16T190045728924 | 1 changed, 1 added | quiet |
| 2026-11-16 | `remote/io.github.hft-studio/pokerdata` | 2026-11-16T122525129524 -> 2026-11-16T190042076011 | 3 changed | quiet |
| 2026-11-16 | `remote/com.crm-connector/crm-connector` | 2026-11-15T155553378281 -> 2026-11-16T190041587302 | 2 changed | quiet |
| 2026-11-16 | `remote/ai.switchapp/switch` | 2026-11-15T141942827703 -> 2026-11-16T190037259389 | 2 changed | quiet |
| 2026-11-16 | `remote/io.outil/outil` | 2026-11-16T162623695252 -> 2026-11-16T190035070745 | 10 changed, 13 added | quiet |
| 2026-11-16 | `remote/io.github.sudzikcoin/suverse-agent-assistant` | 2026-11-16T163343011029 -> 2026-11-16T190037802009 | 1 changed | quiet |
| 2026-11-16 | `remote/no.restplass/travel-search` | 2026-11-16T163325576596 -> 2026-11-16T190035759244 | 1 changed | quiet |
| 2026-11-16 | `remote/io.github.hail-hq/hail-mcp` | 2026-11-16T162230078727 -> 2026-11-16T190029437649 | 1 changed | quiet |
| 2026-11-16 | `remote/com.moacut/moacut` | 2026-11-16T163310153883 -> 2026-11-16T190028047437 | 1 changed | quiet |
| 2026-11-16 | `remote/com.foundationscounselingllc/practice` | 2026-11-14T135347586687 -> 2026-11-16T190027529541 | 4 changed | quiet |
| 2026-11-16 | `remote/dev.flagbearer/flagbearer` | 2026-11-16T162206556893 -> 2026-11-16T190026364594 | 2 added | quiet |
| 2026-11-16 | `remote/co.civai.nova/mcp-firecrawl` | 2026-11-16T162600340581 -> 2026-11-16T190026921993 | 1 changed, 1 removed | quiet |
| 2026-11-16 | `remote/com.kulicadvisory/aictionbot-werkbank` | 2026-11-16T163303501920 -> 2026-11-16T190025347025 | 11 added | quiet |
| 2026-11-16 | `remote/city.close/close-api` | 2026-11-16T122152085409 -> 2026-11-16T190023081501 | 10 changed (every tool) | quiet |
| 2026-11-16 | `remote/dk.afbudsrejser/travel-search` | 2026-11-16T163222814525 -> 2026-11-16T190022313942 | 1 changed | quiet |
| 2026-11-16 | `remote/com.nearfine/books` | 2026-11-16T122425591611 -> 2026-11-16T190021584187 | 1 changed | quiet |
| 2026-11-16 | `remote/app.pitbi/pitbi` | 2026-11-16T072251444388 -> 2026-11-16T190022945187 | 1 changed | quiet |
| 2026-11-16 | `remote/com.markdownlogic/markdown-logic-public` | 2026-11-16T162027889269 -> 2026-11-16T190016525870 | 1 changed | quiet |
| 2026-11-16 | `remote/me.miow/miow` | 2026-11-16T122405382395 -> 2026-11-16T190014934187 | 3 changed | quiet |
| 2026-11-16 | `remote/io.github.m2mfreedom/freedom-m2m-mcp-server` | 2026-11-14T010626687333 -> 2026-11-16T190014137168 | 4 added | review |
| 2026-11-16 | `remote/com.eliteaiempire/th-datasets` | 2026-11-16T163033742802 -> 2026-11-16T190010706355 | 1 changed | quiet |
| 2026-11-16 | `remote/org.summarizethis/summarizethis` | 2026-11-16T162954870459 -> 2026-11-16T190006400985 | 1 changed | quiet |
| 2026-11-16 | `remote/fr.ip73/ip73` | 2026-11-16T161900107335 -> 2026-11-16T190003921699 | 2 changed | quiet |
| 2026-11-16 | `remote/com.muddworldorg/sanctuary` | 2026-11-16T122226044538 -> 2026-11-16T190001217910 | 2 changed, 2 added | quiet |
| 2026-11-16 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-11-16T072143094691 -> 2026-11-16T185959202693 | 1 changed | review |
| 2026-11-16 | `remote/app.moosetracker/moose-tracker` | 2026-11-14T010617264263 -> 2026-11-16T190000132713 | 8 changed (every tool) | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 65806 substantive, 40765 that changed only numbers (a catalogue counter ticking, a date), 1054 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 58079 | 19726 | 38353 | 0 |
| `a2awire.com` | 2974 | 2974 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 460 | 460 | 0 | 0 |
| `civai.co` | 366 | 366 | 0 | 0 |
| `modevc.com` | 305 | 305 | 0 | 0 |
| `revmesh2074.workers.dev` | 285 | 251 | 34 | 0 |
| `sistaminuten.se` | 246 | 6 | 0 | 240 |
| `afbudsrejser.dk` | 245 | 6 | 0 | 239 |
| `akkilahdot.fi` | 245 | 6 | 0 | 239 |
| `restplass.no` | 245 | 6 | 0 | 239 |
| `socialloop.ai` | 237 | 237 | 0 | 0 |
| 9677 other operators | 41597 | 39122 | 2378 | 97 |
