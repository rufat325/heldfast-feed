# MCP server tool changes

Last change observed 2026-10-27T12:45:56+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

55467 changes to a tool definition: 2384 npm releases (2138 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 53083 readings of hosted servers that found their tools changed; 2826 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-27 | `remote/io.taifoon/coordination-layer.1` | 2026-10-27T112409240998 -> 2026-10-27T124557689752 | 1 changed | review |
| 2026-10-27 | `remote/se.sistaminuten/travel-search` | 2026-10-27T112404880243 -> 2026-10-27T124543672677 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.voicehook-ai/voicehook` | 2026-10-27T112252598583 -> 2026-10-27T124343597598 | 5 changed | quiet |
| 2026-10-27 | `remote/design.overflow/mcp` | 2026-10-26T133549760075 -> 2026-10-27T124315274726 | 1 changed | quiet |
| 2026-10-27 | `remote/ru.zakazat-zvezdu/stars` | 2026-10-26T133828160645 -> 2026-10-27T124305012697 | 1 changed | quiet |
| 2026-10-27 | `remote/studio.gradients/mcp` | 2026-10-27T112235544457 -> 2026-10-27T124301438327 | 1 changed | quiet |
| 2026-10-27 | `remote/no.restplass/travel-search` | 2026-10-27T112547687999 -> 2026-10-27T124244328265 | 1 changed | quiet |
| 2026-10-27 | `remote/fi.akkilahdot/travel-search` | 2026-10-27T112213617930 -> 2026-10-27T124237977761 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.xzntexe/yruz-x402` | 2026-10-27T112456725369 -> 2026-10-27T124233973362 | 44 changed, 12 added (every tool) | review |
| 2026-10-27 | `remote/io.github.eamwhite1/agent-trust` | 2026-10-25T191842498429 -> 2026-10-27T124229493044 | 2 changed, 1 added | quiet |
| 2026-10-27 | `remote/com.beachvalencia/booking` | 2026-10-06T110258700478 -> 2026-10-27T124211870677 | 4 changed, 1 added (every tool) | quiet |
| 2026-10-27 | `remote/dk.afbudsrejser/travel-search` | 2026-10-27T112506252550 -> 2026-10-27T124207580093 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.Humanleap/magicscreenshots-mcp` | 2026-10-27T112422846414 -> 2026-10-27T124153028523 | 9 changed | review |
| 2026-10-27 | `remote/io.github.Ockram4444/agentcompute` | 2026-10-26T133644121830 -> 2026-10-27T124132489515 | 1 added | quiet |
| 2026-10-27 | `remote/ai.screwtape/screwtape` | 2026-10-27T054042999160 -> 2026-10-27T124123207157 | 1 changed | quiet |
| 2026-10-27 | `remote/com.nythosx.tools/agent-tools` | 2026-10-26T133627469735 -> 2026-10-27T124118751570 | 1 changed, 1 added | quiet |
| 2026-10-27 | `remote/io.github.dtajitdinov-aris/sphere-marketplace` | 2026-10-27T054107353265 -> 2026-10-27T124107917381 | 7 changed | quiet |
| 2026-10-27 | `remote/com.plainfreight/quotes` | 2026-10-08T135237908839 -> 2026-10-27T124021926496 | 1 changed | quiet |
| 2026-10-27 | `remote/com.slidler/carousel` | 2026-10-25T102338123334 -> 2026-10-27T124020812187 | 1 changed | quiet |
| 2026-10-27 | `remote/com.remoshift/jobs` | 2026-10-27T111958492100 -> 2026-10-27T123958233587 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.jkbngb/handelsregister` | 2026-10-17T060207719788 -> 2026-10-27T123926300502 | 2 changed | quiet |
| 2026-10-27 | `remote/io.github.scraping-api-plans/web-data-plan-finder` | 2026-10-25T102350052878 -> 2026-10-27T123921303295 | 2 changed, 1 added | quiet |
| 2026-10-27 | `remote/app.planbeforeyoudie/facts` | 2026-10-26T133153990096 -> 2026-10-27T123918953069 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.cnucho/methodiq-tools` | 2026-10-27T111909505340 -> 2026-10-27T123913629767 | 10 added | quiet |
| 2026-10-27 | `remote/io.github.Civops-Platform/open-signals` | 2026-10-17T055635356459 -> 2026-10-27T123850482050 | 1 changed | quiet |
| 2026-10-27 | `remote/de.viafrei/mcp` | 2026-10-26T133338161097 -> 2026-10-27T123846268792 | 2 changed | quiet |
| 2026-10-27 | `remote/ai.sitectrl/sitectrl` | 2026-10-27T111813400039 -> 2026-10-27T123816263314 | 2 changed, 1 added | quiet |
| 2026-10-27 | `remote/com.plainrouter/mcp` | 2026-10-24T190414382920 -> 2026-10-27T123808304755 | 1 changed | quiet |
| 2026-10-27 | `remote/io.kompare/search` | 2026-10-21T141102874243 -> 2026-10-27T123725189159 | 4 changed (every tool) | quiet |
| 2026-10-27 | `remote/io.github.c-mongan/ireland-mcp.1` | 2026-10-26T133207443278 -> 2026-10-27T123717410461 | 5 changed, 1 added | quiet |
| 2026-10-27 | `remote/com.reminderit/reminderit` | 2026-10-06T110000101204 -> 2026-10-27T123717154376 | 25 changed (every tool) | quiet |
| 2026-10-27 | `remote/ch.opencaselaw/swiss-caselaw` | 2026-10-26T133130870905 -> 2026-10-27T123640399068 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.eamwhite1/xrpl-referee` | 2026-10-25T191850293994 -> 2026-10-27T123635400967 | 2 changed, 1 added | quiet |
| 2026-10-27 | `remote/com.tensorust/mcp` | 2026-10-27T054050279212 -> 2026-10-27T123621024772 | 2 changed | quiet |
| 2026-10-27 | `remote/ai.eshmere/tenda` | 2026-10-26T133118247462 -> 2026-10-27T123620482155 | 39 changed | quiet |
| 2026-10-27 | `remote/io.github.c-mongan/ireland-mcp` | 2026-10-26T132852979947 -> 2026-10-27T123620834172 | 5 changed, 1 added | quiet |
| 2026-10-27 | `remote/com.freightfa.mcp/freightfa` | 2026-10-25T102105350489 -> 2026-10-27T123605602859 | 1 changed | quiet |
| 2026-10-27 | `remote/com.ellomind/therapy-booking` | 2026-10-27T111607184645 -> 2026-10-27T123548387768 | 3 changed, 2 added | quiet |
| 2026-10-27 | `remote/com.pandavideo/mcp` | 2026-10-26T211437244503 -> 2026-10-27T123539691629 | 3 changed, 1 added | quiet |
| 2026-10-27 | `remote/co.deadbrands/arena` | 2026-10-27T111801069044 -> 2026-10-27T123535645779 | 45 changed | quiet |
| 2026-10-27 | `remote/io.github.flogvit/bible` | 2026-10-26T132959561285 -> 2026-10-27T123517511358 | 12 changed, 8 added | quiet |
| 2026-10-27 | `remote/com.lobstermatch/lobstermatch` | 2026-10-27T111510380758 -> 2026-10-27T123515416292 | 3 changed | quiet |
| 2026-10-27 | `remote/com.avokata/avokata` | 2026-10-27T111739137060 -> 2026-10-27T123515929190 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.industrial-platform-ai/research-brief` | 2026-10-21T202414471984 -> 2026-10-27T123514330442 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.jasp402/hypercodemotion-mcp` | 2026-10-25T052242360151 -> 2026-10-27T123503912114 | 2 changed | quiet |
| 2026-10-27 | `remote/io.github.jkbngb/firmenbuch` | 2026-10-22T105312506147 -> 2026-10-27T123500185673 | 2 changed | quiet |
| 2026-10-27 | `remote/si.divux/divux` | 2026-10-27T111620528464 -> 2026-10-27T123433165989 | 2 changed | quiet |
| 2026-10-27 | `remote/io.github.wellknownmcp/ia-asso` | 2026-10-25T191816408562 -> 2026-10-27T123418648153 | 1 changed | quiet |
| 2026-10-27 | `remote/com.ksaworks/goldseam` | 2026-10-25T101749106158 -> 2026-10-27T123311482567 | 2 changed | quiet |
| 2026-10-27 | `remote/io.github.c-mongan/ireland-mcp.2` | 2026-10-26T132409691935 -> 2026-10-27T123220371484 | 5 changed, 1 added | quiet |
| 2026-10-27 | `remote/app.vercel.fork-for-agents/fork` | 2026-10-27T111227463027 -> 2026-10-27T123213822104 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.edtool79-collab/hirepulse-gateway` | 2026-10-27T111345422383 -> 2026-10-27T123213159984 | 17 changed | quiet |
| 2026-10-27 | `remote/com.getcloseknit/close-knit` | 2026-10-26T153051273134 -> 2026-10-27T123212746101 | 2 changed | quiet |
| 2026-10-27 | `remote/io.github.seanmeverett/evergences` | 2026-10-26T132336503242 -> 2026-10-27T123149948493 | 1 changed | quiet |
| 2026-10-27 | `remote/com.faredice/trips` | 2026-10-27T111327361901 -> 2026-10-27T123128433643 | 1 added | quiet |
| 2026-10-27 | `remote/com.dayze/life-context.1` | 2026-10-27T111129356174 -> 2026-10-27T123126152730 | 1 changed | quiet |
| 2026-10-27 | `remote/com.dayze/life-context` | 2026-10-27T111129137592 -> 2026-10-27T123126265459 | 1 changed | quiet |
| 2026-10-27 | `remote/io.taifoon/coordination-layer` | 2026-10-27T111217560798 -> 2026-10-27T123027490868 | 1 changed | review |
| 2026-10-27 | `remote/io.github.chrp-bass/chrp-epi-authority` | 2026-10-25T101521183870 -> 2026-10-27T123018476366 | 1 added | quiet |
| 2026-10-27 | `remote/com.ce-net/ce-net.1` | 2026-10-27T053955022234 -> 2026-10-27T122958289296 | 1 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 35354 substantive, 19434 that changed only numbers (a catalogue counter ticking, a date), 679 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 30394 | 12161 | 18233 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 891 | 891 | 0 | 0 |
| `caseyjhand.com` | 238 | 238 | 0 | 0 |
| `sistaminuten.se` | 160 | 4 | 0 | 156 |
| `afbudsrejser.dk` | 159 | 4 | 0 | 155 |
| `akkilahdot.fi` | 159 | 4 | 0 | 155 |
| `restplass.no` | 159 | 4 | 0 | 155 |
| `socialloop.ai` | 153 | 153 | 0 | 0 |
| `remoshift.com` | 129 | 8 | 121 | 0 |
| `revmesh2074.workers.dev` | 129 | 116 | 13 | 0 |
| `fundinglandscape.com` | 122 | 78 | 44 | 0 |
| 6068 other operators | 20433 | 19352 | 1023 | 58 |
