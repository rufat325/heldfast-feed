# MCP server tool changes

Last change observed 2026-10-21T12:24:15+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

39968 changes to a tool definition: 1694 npm releases (1448 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 38274 readings of hosted servers that found their tools changed; 2306 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-21 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-10-21T052331369647 -> 2026-10-21T122416545747 | 1 added | quiet |
| 2026-10-21 | `remote/io.github.radsdevv/vibekast` | 2026-10-17T055624243984 -> 2026-10-21T122414404403 | 3 changed, 2 added | quiet |
| 2026-10-21 | `remote/com.thevicinityapp/vicinity-agent-api` | 2026-09-23T161037776730 -> 2026-10-21T122413179821 | 1 changed | quiet |
| 2026-10-21 | `remote/ai.startuphub/startuphub` | 2026-10-20T201135596116 -> 2026-10-21T122407721440 | 3 changed | quiet |
| 2026-10-21 | `remote/se.sistaminuten/travel-search` | 2026-10-21T052327452863 -> 2026-10-21T122405853584 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-09-27T070512810802 -> 2026-10-21T122354043800 | 3 changed | quiet |
| 2026-10-21 | `remote/it.expatliving/data` | 2026-10-17T055600417283 -> 2026-10-21T122348160826 | 3 changed | quiet |
| 2026-10-21 | `remote/io.engineeringleaders/elc-partnership-builder` | 2026-10-06T110147116720 -> 2026-10-21T122349204840 | 7 changed | quiet |
| 2026-10-21 | `remote/ai.whatsupin/events` | 2026-10-20T232822784332 -> 2026-10-21T122323534960 | 3 changed | quiet |
| 2026-10-21 | `remote/io.github.voicehook-ai/voicehook` | 2026-10-20T135428174798 -> 2026-10-21T122301675981 | 5 changed | quiet |
| 2026-10-21 | `remote/info.vetclinic/directory` | 2026-10-17T055531868993 -> 2026-10-21T122257182202 | 1 changed | quiet |
| 2026-10-21 | `remote/cz.veciobecni/veci-obecni` | 2026-10-19T135408027993 -> 2026-10-21T122255033827 | 1 added | quiet |
| 2026-10-21 | `remote/com.varioroam/esim-catalog` | 2026-10-20T135427318161 -> 2026-10-21T122252578717 | 2 changed | quiet |
| 2026-10-21 | `remote/io.github.seekdaseek/agentfeed` | 2026-10-19T135617673083 -> 2026-10-21T122240697109 | 2 changed | quiet |
| 2026-10-21 | `remote/shop.grokzilla/micro-pay.1` | 2026-10-19T135615792768 -> 2026-10-21T122238019343 | 1 removed | quiet |
| 2026-10-21 | `remote/com.tryalpy/alpy` | 2026-10-20T232818597322 -> 2026-10-21T122236270850 | 4 changed | quiet |
| 2026-10-21 | `remote/com.theprotoclinical/commerce` | 2026-10-17T055955205395 -> 2026-10-21T122232046114 | 9 changed | quiet |
| 2026-10-21 | `remote/io.github.intoApex/tradingagentstack` | 2026-10-19T135342618250 -> 2026-10-21T122228985213 | 5 changed (every tool) | quiet |
| 2026-10-21 | `remote/io.github.SKalinin909/tradingcalc` | 2026-10-20T232816932817 -> 2026-10-21T122229564855 | 1 added | quiet |
| 2026-10-21 | `remote/io.github.Fizzl13/x402-doctor` | 2026-10-20T232810589366 -> 2026-10-21T122222497942 | 3 changed | quiet |
| 2026-10-21 | `remote/io.github.Licium-ai/licium` | 2026-10-18T051404569767 -> 2026-10-21T122216588619 | 5 changed, 6 added | review |
| 2026-10-21 | `remote/com.jobcrawls/connector` | 2026-10-19T135554948012 -> 2026-10-21T122215782123 | 4 changed (every tool) | quiet |
| 2026-10-21 | `remote/com.thefomite/fomite` | 2026-10-21T052312210070 -> 2026-10-21T122213355269 | 1 changed | quiet |
| 2026-10-21 | `remote/studio.gradients/mcp` | 2026-10-21T052301494692 -> 2026-10-21T122212124980 | 1 changed | quiet |
| 2026-10-21 | `remote/world.agentindex/x402` | 2026-10-17T060508406944 -> 2026-10-21T122211246556 | 1 changed, 2 added | quiet |
| 2026-10-21 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-10-21T052515549208 -> 2026-10-21T122209231376 | 1 added | quiet |
| 2026-10-21 | `remote/com.quailos/quailos` | 2026-10-17T060404686975 -> 2026-10-21T122207544139 | 8 changed | quiet |
| 2026-10-21 | `remote/io.github.falsalama/proper-job` | 2026-10-17T060403428761 -> 2026-10-21T122205974362 | 1 changed | quiet |
| 2026-10-21 | `remote/com.theflowersdirectory/flowers` | 2026-09-28T142326497562 -> 2026-10-21T122203286961 | 3 changed, 6 added (every tool) | quiet |
| 2026-10-21 | `remote/no.restplass/travel-search` | 2026-10-21T052512759045 -> 2026-10-21T122156581866 | 1 changed | quiet |
| 2026-10-21 | `remote/fi.akkilahdot/travel-search` | 2026-10-21T052259572120 -> 2026-10-21T122155498756 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.worklore/worklore` | 2026-10-17T055917680251 -> 2026-10-21T122151623825 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.muaviamohammed/mizan` | 2026-10-21T052308886582 -> 2026-10-21T122153687249 | 9 changed, 1 added | quiet |
| 2026-10-21 | `remote/io.engineeringleaders/elc-trade` | 2026-10-06T110253500765 -> 2026-10-21T122149868287 | 1 changed | quiet |
| 2026-10-21 | `remote/com.juzpost/mcp` | 2026-10-19T135844329572 -> 2026-10-21T122144161383 | 4 changed | quiet |
| 2026-10-21 | `remote/tech.viewprinter/viewprinter` | 2026-10-17T055903913864 -> 2026-10-21T122133758669 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.suanrongbaicai/vibecodepicks` | 2026-10-19T135504359263 -> 2026-10-21T122130548291 | 13 changed (every tool) | quiet |
| 2026-10-21 | `remote/ai.weio/site-check` | 2026-10-20T232802501244 -> 2026-10-21T122126535285 | 3 added, 2 removed | quiet |
| 2026-10-21 | `remote/com.siliconfloor/silicon-floor` | 2026-10-20T232807004152 -> 2026-10-21T122125317599 | 1 changed | quiet |
| 2026-10-21 | `remote/dk.afbudsrejser/travel-search` | 2026-10-21T052506741328 -> 2026-10-21T122124250759 | 1 changed | quiet |
| 2026-10-21 | `remote/net.umbhost/umbhost-mcp` | 2026-10-17T055855328550 -> 2026-10-21T122120398627 | 3 changed, 5 added | quiet |
| 2026-10-21 | `remote/ai.sfomo/events` | 2026-10-20T104142476383 -> 2026-10-21T122119031200 | 6 changed (every tool) | quiet |
| 2026-10-21 | `remote/ai.vibebooking/vibebook` | 2026-10-17T060305268762 -> 2026-10-21T122115661754 | 1 added | quiet |
| 2026-10-21 | `remote/io.github.withgrokbot/verified-catalog.1` | 2026-10-17T060302494678 -> 2026-10-21T122113646775 | 1 added | quiet |
| 2026-10-21 | `remote/com.veritaset/mcp` | 2026-10-20T201201573114 -> 2026-10-21T122102511133 | 2 changed | quiet |
| 2026-10-21 | `remote/com.asksakina/islamic-knowledge` | 2026-09-29T210500994603 -> 2026-10-21T122059118137 | 4 changed (every tool) | quiet |
| 2026-10-21 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-20T201133308003 -> 2026-10-21T122055874639 | 1 changed | quiet |
| 2026-10-21 | `remote/is.envelop.unisafe/insight` | 2026-10-19T135746073486 -> 2026-10-21T122054747197 | 1 changed | quiet |
| 2026-10-21 | `remote/com.underpricedai/underpriced-ai` | 2026-10-17T060357950206 -> 2026-10-21T122052566676 | 3 changed | quiet |
| 2026-10-21 | `remote/com.thejohnsonbros/plumbing-booking` | 2026-09-24T212230794091 -> 2026-10-21T122056640258 | 8 changed | quiet |
| 2026-10-21 | `remote/cc.thecolony/mcp-server` | 2026-10-17T060232705005 -> 2026-10-21T122049664599 | 3 changed | quiet |
| 2026-10-21 | `remote/xyz.trusteed/mcp-gateway` | 2026-10-17T110728472302 -> 2026-10-21T122047994788 | 4 changed | quiet |
| 2026-10-21 | `remote/com.tablejourney/food-travel` | 2026-10-08T135407492685 -> 2026-10-21T122047097368 | 8 added | quiet |
| 2026-10-21 | `remote/com.swarmmemo/bulletin.1` | 2026-10-20T232803031328 -> 2026-10-21T122044651219 | 1 changed | quiet |
| 2026-10-21 | `remote/com.swarmmemo/bulletin` | 2026-10-20T232802911047 -> 2026-10-21T122044466290 | 2 changed | quiet |
| 2026-10-21 | `remote/io.github.tidytools/tidytools-free` | 2026-10-21T052446923989 -> 2026-10-21T122041582550 | 44 changed | quiet |
| 2026-10-21 | `remote/io.szum/charts` | 2026-10-17T060224182488 -> 2026-10-21T122041956608 | 6 changed | quiet |
| 2026-10-21 | `remote/eu.gridgarden/studio` | 2026-10-17T055822586911 -> 2026-10-21T122041386887 | 1 changed | quiet |
| 2026-10-21 | `remote/com.googleapis.stitch/mcp` | 2026-10-17T055817872745 -> 2026-10-21T122036375265 | 3 changed, 1 added | quiet |
| 2026-10-21 | `remote/io.github.JacobiusMakes/stienhardt-store` | 2026-10-17T055816852546 -> 2026-10-21T122035198771 | 9 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 25183 substantive, 14249 that changed only numbers (a catalogue counter ticking, a date), 536 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 20653 | 7232 | 13421 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 170 | 170 | 0 | 0 |
| `sistaminuten.se` | 128 | 4 | 0 | 124 |
| `afbudsrejser.dk` | 127 | 4 | 0 | 123 |
| `akkilahdot.fi` | 127 | 4 | 0 | 123 |
| `restplass.no` | 127 | 4 | 0 | 123 |
| `socialloop.ai` | 124 | 124 | 0 | 0 |
| `remoshift.com` | 98 | 6 | 92 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `fundinglandscape.com` | 96 | 62 | 34 | 0 |
| 4922 other operators | 15227 | 14482 | 702 | 43 |
