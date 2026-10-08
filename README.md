# MCP server tool changes

Last change observed 2026-10-08T21:35:57+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10128 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 21701 hosted endpoints (read daily, and every four hours while they keep changing).

25365 changes to a tool definition: 870 npm releases (624 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 24495 readings of hosted servers that found their tools changed; 363 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-08 | `remote/se.sistaminuten/travel-search` | 2026-10-08T155701836637 -> 2026-10-08T213558717934 | 1 changed | quiet |
| 2026-10-08 | `remote/io.github.tjcgraham-rgb/gaip-broker` | 2026-10-08T135522499659 -> 2026-10-08T213559377841 | 1 changed | quiet |
| 2026-10-08 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-08T135500673636 -> 2026-10-08T213548826516 | 2 changed, 1 added | quiet |
| 2026-10-08 | `remote/app.openkrill/shop-duty` | 2026-10-06T110044005584 -> 2026-10-08T213529126001 | 1 changed | quiet |
| 2026-10-08 | `remote/io.github.SidneyBissoli/senado-br-mcp-cloudflare` | 2026-10-08T155624960373 -> 2026-10-08T213524718354 | 69 changed (every tool) | quiet |
| 2026-10-08 | `remote/ai.satohub/onchain-agents` | 2026-10-08T064231867347 -> 2026-10-08T213523411800 | 3 changed | quiet |
| 2026-10-08 | `remote/ai.plith/plith` | 2026-10-08T135240831745 -> 2026-10-08T213513082980 | 2 changed | quiet |
| 2026-10-08 | `remote/re.parcellai/parcellaire` | 2026-10-08T135224371347 -> 2026-10-08T213507981820 | 2 changed, 1 added | quiet |
| 2026-10-08 | `remote/com.oods-foundry/foundry` | 2026-10-08T064222279356 -> 2026-10-08T213504238791 | 2 changed | quiet |
| 2026-10-08 | `remote/co.civai.nova/google-docs-agent` | 2026-10-08T135206535144 -> 2026-10-08T213502618720 | 2 added | quiet |
| 2026-10-08 | `remote/com.narrowhighway/concordance` | 2026-10-07T001205886233 -> 2026-10-08T213500200128 | 1 changed | quiet |
| 2026-10-08 | `remote/no.restplass/travel-search` | 2026-10-08T155535402373 -> 2026-10-08T213453768873 | 1 changed | quiet |
| 2026-10-08 | `remote/io.github.SidneyBissoli/medical-terminologies-mcp` | 2026-10-06T105913502873 -> 2026-10-08T213454534795 | 33 changed (every tool) | quiet |
| 2026-10-08 | `remote/dk.afbudsrejser/travel-search` | 2026-10-08T155530153893 -> 2026-10-08T213448239731 | 1 changed | quiet |
| 2026-10-08 | `remote/pro.particle/particle-pro` | 2026-10-06T105810832522 -> 2026-10-08T213446890961 | 1 changed | quiet |
| 2026-10-08 | `remote/io.github.SidneyBissoli/uis-mcp-server` | 2026-10-08T155525607938 -> 2026-10-08T213443499289 | 5 changed (every tool) | quiet |
| 2026-10-08 | `remote/com.txtreel/txtreel` | 2026-10-07T001323112657 -> 2026-10-08T213444169794 | 2 changed | quiet |
| 2026-10-08 | `remote/ai.trydock/dock` | 2026-10-06T110231129630 -> 2026-10-08T213442228672 | 1 changed | quiet |
| 2026-10-08 | `remote/fr.projet-ariane/ariane-orientation` | 2026-10-08T155539499873 -> 2026-10-08T213440733116 | 2 changed | quiet |
| 2026-10-08 | `remote/com.knowjudges/knowjudges` | 2026-10-08T134953937307 -> 2026-10-08T213442575126 | 3 changed | quiet |
| 2026-10-08 | `remote/io.metodic/metodic` | 2026-10-06T110419169030 -> 2026-10-08T213440459184 | 1 changed | quiet |
| 2026-10-08 | `remote/io.github.firecrawl/firecrawl-mcp-server` | 2026-10-06T184020405440 -> 2026-10-08T213438723126 | 1 changed | quiet |
| 2026-10-08 | `remote/io.github.Ahmet11159/x402-agent-services` | 2026-10-08T155516583059 -> 2026-10-08T213439122010 | 20 changed (every tool) | quiet |
| 2026-10-08 | `remote/fi.akkilahdot/travel-search` | 2026-10-08T155533847297 -> 2026-10-08T213436617905 | 1 changed | quiet |
| 2026-10-08 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-10-08T135458536813 -> 2026-10-08T213436903042 | 3 changed | quiet |
| 2026-10-08 | `remote/io.github.kor-jongwon/witan` | 2026-10-08T064244187956 -> 2026-10-08T213437429085 | 8 changed, 4 added | quiet |
| 2026-10-08 | `remote/ing.crank/crank` | 2026-10-07T213752942984 -> 2026-10-08T213438322318 | 4 changed, 2 added | quiet |
| 2026-10-08 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-08T155515423310 -> 2026-10-08T213434496783 | 13 changed | quiet |
| 2026-10-08 | `remote/io.simplyprint/simplyprint` | 2026-10-06T110144954539 -> 2026-10-08T213434154596 | 5 changed | quiet |
| 2026-10-08 | `remote/dev.pages.smithtalks/smithtalks` | 2026-10-07T001311035020 -> 2026-10-08T213434585977 | 3 changed, 3 added | quiet |
| 2026-10-08 | `remote/ru.vedarai/mcp` | 2026-10-08T135436798063 -> 2026-10-08T213434173476 | 2 changed | quiet |
| 2026-10-08 | `remote/com.saferesize/saferesize` | 2026-10-06T110121218530 -> 2026-10-08T213429637723 | 1 changed | quiet |
| 2026-10-08 | `remote/ai.rokha/rokha` | 2026-10-08T064220441124 -> 2026-10-08T213429084091 | 25 changed | review |
| 2026-10-08 | `remote/com.renderball/renderball` | 2026-10-08T135310716573 -> 2026-10-08T213427828665 | 11 changed (every tool) | quiet |
| 2026-10-08 | `remote/io.github.Jaywestphilly/stock-bloc` | 2026-10-08T135358596101 -> 2026-10-08T213425999232 | 1 changed | quiet |
| 2026-10-08 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-08T155516783535 -> 2026-10-08T213423759478 | 2 changed, 3 added | quiet |
| 2026-10-08 | `remote/io.github.richardsolomou/praetorium` | 2026-10-08T155504371969 -> 2026-10-08T213424756084 | 1 added | quiet |
| 2026-10-08 | `remote/co.lumman/mail` | 2026-10-08T155500565078 -> 2026-10-08T213425205959 | 30 changed (every tool) | quiet |
| 2026-10-08 | `remote/io.github.SidneyBissoli/sih-br-mcp` | 2026-10-08T135342657426 -> 2026-10-08T213422400550 | 12 changed (every tool) | quiet |
| 2026-10-08 | `remote/io.github.Project-Gifted1/pg1-threat-intel` | 2026-10-07T154925879274 -> 2026-10-08T213422311562 | 1 added | quiet |
| 2026-10-08 | `remote/ai.shorti/shorti` | 2026-10-08T135341524566 -> 2026-10-08T213423448129 | 2 changed | quiet |
| 2026-10-08 | `remote/io.github.LAHutchins91/patent` | 2026-10-06T110025995362 -> 2026-10-08T213421200654 | 1 changed | quiet |
| 2026-10-08 | `remote/ch.kulalabs.pazair/pazair` | 2026-10-07T213818546817 -> 2026-10-08T213423353953 | 2 changed, 5 added, 2 removed | quiet |
| 2026-10-08 | `remote/com.youspot/youspot` | 2026-10-08T064242245474 -> 2026-10-08T213417440212 | 4 changed | quiet |
| 2026-10-08 | `remote/com.pv-solaire-energie/devis-solaire` | 2026-10-08T155508691189 -> 2026-10-08T213417083897 | 1 changed | quiet |
| 2026-10-08 | `remote/io.github.yschimke/compose-preview` | 2026-10-08T064226448008 -> 2026-10-08T213416906263 | 1 changed | quiet |
| 2026-10-08 | `remote/io.github.SidneyBissoli/ibge-br-mcp` | 2026-10-08T134739791337 -> 2026-10-08T213412052897 | 23 changed (every tool) | quiet |
| 2026-10-08 | `remote/ai.roote/mcp` | 2026-10-06T105910773229 -> 2026-10-08T213411437413 | 1 changed | quiet |
| 2026-10-08 | `remote/co.homemaster/homemaster` | 2026-10-08T155442013491 -> 2026-10-08T213414493543 | 6 changed | quiet |
| 2026-10-08 | `remote/com.thenewengineer/hvac` | 2026-10-08T135350998478 -> 2026-10-08T213409009388 | 2 changed | quiet |
| 2026-10-08 | `remote/com.musedin/musedin` | 2026-10-08T155454857518 -> 2026-10-08T213408060335 | 1 added | quiet |
| 2026-10-08 | `remote/com.multicinesortega/cartelera` | 2026-10-08T064220377505 -> 2026-10-08T213408699286 | 1 changed | quiet |
| 2026-10-08 | `remote/cc.thecolony/mcp-server` | 2026-10-07T154946795278 -> 2026-10-08T213408238430 | 1 changed | quiet |
| 2026-10-08 | `remote/com.talktoaleksandra/consultations` | 2026-10-08T135340706447 -> 2026-10-08T213407641387 | 2 changed | quiet |
| 2026-10-08 | `remote/com.sonarconnections/sonar-connections` | 2026-10-08T135145877472 -> 2026-10-08T213406769371 | 1 added | quiet |
| 2026-10-08 | `remote/io.stackcut/stackcut` | 2026-10-07T213838383803 -> 2026-10-08T213404796485 | 1 changed | quiet |
| 2026-10-08 | `remote/com.goodrecmovies/mcp` | 2026-10-06T105551563924 -> 2026-10-08T213406146653 | 2 changed, 2 added, 1 removed (every tool) | quiet |
| 2026-10-08 | `remote/so.darwin/darwin` | 2026-10-08T155442001757 -> 2026-10-08T213402734714 | 1 changed | quiet |
| 2026-10-08 | `remote/com.signatoro/signatoro` | 2026-10-08T135309978951 -> 2026-10-08T213402114368 | 2 changed | quiet |
| 2026-10-08 | `remote/com.courtdelta/court-delta` | 2026-10-08T134950188603 -> 2026-10-08T213401818983 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 17036 substantive, 7973 that changed only numbers (a catalogue counter ticking, a date), 356 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 13231 | 5706 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 538 | 538 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `sistaminuten.se` | 86 | 2 | 0 | 84 |
| `afbudsrejser.dk` | 85 | 2 | 0 | 83 |
| `akkilahdot.fi` | 85 | 2 | 0 | 83 |
| `restplass.no` | 85 | 2 | 0 | 83 |
| `socialloop.ai` | 83 | 83 | 0 | 0 |
| `caseyjhand.com` | 77 | 77 | 0 | 0 |
| `dayze.com` | 69 | 69 | 0 | 0 |
| `fundinglandscape.com` | 60 | 35 | 25 | 0 |
| 3052 other operators | 8528 | 8082 | 423 | 23 |
