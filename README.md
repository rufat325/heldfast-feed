# MCP server tool changes

Last change observed 2026-10-18T19:01:22+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10495 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 23695 hosted endpoints (read daily, and every four hours while they keep changing).

32646 changes to a tool definition: 1188 npm releases (942 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 31458 readings of hosted servers that found their tools changed; 2104 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-18 | `remote/io.github.seekdaseek/agentfeed` | 2026-10-17T060000372608 -> 2026-10-18T190124898432 | 1 changed | quiet |
| 2026-10-18 | `remote/fi.akkilahdot/travel-search` | 2026-10-18T125101539126 -> 2026-10-18T190112384591 | 1 changed | quiet |
| 2026-10-18 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-10-17T224356365162 -> 2026-10-18T190112963442 | 4 changed | quiet |
| 2026-10-18 | `remote/us.srv.vehcdj664efetfrsolne5umanq/quoteproof-mcp` | 2026-10-18T113233751786 -> 2026-10-18T190108008209 | 5 changed | quiet |
| 2026-10-18 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-18T113210402075 -> 2026-10-18T190058333861 | 1 changed | quiet |
| 2026-10-18 | `remote/com.swarmmemo/bulletin.1` | 2026-10-17T224344343743 -> 2026-10-18T190054686864 | 5 changed | quiet |
| 2026-10-18 | `remote/com.swarmmemo/bulletin` | 2026-10-17T224344057623 -> 2026-10-18T190054706951 | 5 changed | quiet |
| 2026-10-18 | `remote/app.steadywrk/mcp-dispatch` | 2026-10-18T125044882228 -> 2026-10-18T190051659145 | 2 added | quiet |
| 2026-10-18 | `remote/com.starcovery/mcp` | 2026-10-18T051544025771 -> 2026-10-18T190051293112 | 2 changed | quiet |
| 2026-10-18 | `remote/no.restplass/travel-search` | 2026-10-18T125110772277 -> 2026-10-18T190050013401 | 1 changed | quiet |
| 2026-10-18 | `remote/ch.spickme/swiss-public-transport` | 2026-10-17T055813943812 -> 2026-10-18T190050438738 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-18T125043495277 -> 2026-10-18T190048249229 | 1 changed | quiet |
| 2026-10-18 | `remote/com.roamflat/esim-catalog` | 2026-10-17T155946492308 -> 2026-10-18T190043354572 | 1 changed | quiet |
| 2026-10-18 | `remote/dk.afbudsrejser/travel-search` | 2026-10-18T125059459527 -> 2026-10-18T190040877224 | 1 changed | quiet |
| 2026-10-18 | `remote/com.remoshift/jobs` | 2026-10-18T125039456652 -> 2026-10-18T190040874186 | 1 changed | quiet |
| 2026-10-18 | `remote/com.trustbaselab/rcb-data` | 2026-10-17T060354406695 -> 2026-10-18T190034460908 | 1 changed | quiet |
| 2026-10-18 | `remote/ai.trydock/dock` | 2026-10-18T051525721087 -> 2026-10-18T190033204556 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.philpof102-svg/tokenizedblock` | 2026-10-17T060344073237 -> 2026-10-18T190031018595 | 5 added | review |
| 2026-10-18 | `remote/app.openkrill/postkit` | 2026-10-17T055702540596 -> 2026-10-18T190032248176 | 1 added | quiet |
| 2026-10-18 | `remote/io.github.ashadow07/karmadue.1` | 2026-10-17T055632831528 -> 2026-10-18T190024854807 | 2 changed | quiet |
| 2026-10-18 | `remote/com.obriym-crm/mcp` | 2026-10-18T113023765047 -> 2026-10-18T190045023069 | 4 changed | quiet |
| 2026-10-18 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-10-17T055626208046 -> 2026-10-18T190023013297 | 23 added | review |
| 2026-10-18 | `remote/com.neblla/neblla` | 2026-10-17T224322667667 -> 2026-10-18T190022110957 | 13 changed, 2 added | review |
| 2026-10-18 | `remote/io.taifoon/coordination-layer.1` | 2026-10-18T113507051892 -> 2026-10-18T190021054412 | 2 changed, 7 added | review |
| 2026-10-18 | `remote/pro.sebbi/governance` | 2026-10-17T060252291235 -> 2026-10-18T190019319808 | 23 changed, 3 added, 584 removed (every tool) | quiet |
| 2026-10-18 | `remote/io.github.KyleClouthier/secondstrike` | 2026-10-17T060251996967 -> 2026-10-18T190018825896 | 1 changed | quiet |
| 2026-10-18 | `remote/se.sistaminuten/travel-search` | 2026-10-18T125102100855 -> 2026-10-18T190018736939 | 1 changed | quiet |
| 2026-10-18 | `remote/com.youspot/youspot` | 2026-10-18T051353894094 -> 2026-10-18T190018070678 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.kwizzlesurp10-ctrl/x402-mcp` | 2026-10-18T113512273096 -> 2026-10-18T190017509313 | 2 changed | quiet |
| 2026-10-18 | `remote/com.messeatlas/atlas` | 2026-10-17T055605338657 -> 2026-10-18T190021723217 | 1 added | quiet |
| 2026-10-18 | `remote/io.github.everyai-com/sahadeva` | 2026-10-18T113155446309 -> 2026-10-18T190016581978 | 2 changed | quiet |
| 2026-10-18 | `remote/com.rightshold/rightshold` | 2026-10-18T051350323441 -> 2026-10-18T190014869840 | 7 changed | quiet |
| 2026-10-18 | `remote/io.github.wygogogo19/robotbase-mcp` | 2026-10-18T125038402384 -> 2026-10-18T190015616339 | 2 changed, 13 added, 8 removed | quiet |
| 2026-10-18 | `remote/com.blitzreels/blitzreels` | 2026-10-17T055556361909 -> 2026-10-18T190014690273 | 27 changed, 8 added | quiet |
| 2026-10-18 | `remote/io.github.Bikram2112/claimhit` | 2026-10-17T060337420547 -> 2026-10-18T190012963281 | 1 changed | quiet |
| 2026-10-18 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-17T055546752437 -> 2026-10-18T190013737800 | 2 removed | quiet |
| 2026-10-18 | `remote/ai.weio/site-check` | 2026-10-17T224502591122 -> 2026-10-18T190011686832 | 2 added, 3 removed | quiet |
| 2026-10-18 | `remote/com.voyagehacks/travel` | 2026-10-17T055534637926 -> 2026-10-18T190008976315 | 13 changed (every tool) | quiet |
| 2026-10-18 | `remote/com.petnecto/pets` | 2026-10-17T224347017439 -> 2026-10-18T190006539502 | 1 changed | quiet |
| 2026-10-18 | `remote/app.openkrill/transcript-kit` | 2026-10-17T060248961568 -> 2026-10-18T190006715060 | 1 changed | quiet |
| 2026-10-18 | `remote/ch.kulalabs.pazair/pazair` | 2026-10-18T113113198841 -> 2026-10-18T190008375620 | 1 changed, 1 added | quiet |
| 2026-10-18 | `remote/io.github.cloakmaster/pact0` | 2026-10-17T185329679627 -> 2026-10-18T190003985199 | 2 changed | quiet |
| 2026-10-18 | `remote/io.github.ashadow07/karmadue.2` | 2026-10-17T060112591335 -> 2026-10-18T190004869445 | 2 changed | quiet |
| 2026-10-18 | `remote/com.ontarioprotocol/ontario-protocol` | 2026-10-17T060114384471 -> 2026-10-18T190001456106 | 1 added | review |
| 2026-10-18 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-17T110736858169 -> 2026-10-18T185958790166 | 2 changed | quiet |
| 2026-10-18 | `remote/how.mise/mise` | 2026-10-18T051436062007 -> 2026-10-18T185959825778 | 17 changed, 3 added, 8 removed (every tool) | quiet |
| 2026-10-18 | `remote/com.sfxmint/sounds` | 2026-10-17T060139128130 -> 2026-10-18T185957604781 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.SidneyBissoli/senado-br-mcp-cloudflare` | 2026-10-18T051326321322 -> 2026-10-18T185956688883 | 1 changed | quiet |
| 2026-10-18 | `remote/ai.flyvolo/knowledge` | 2026-10-17T055404287325 -> 2026-10-18T185956626861 | 2 changed | quiet |
| 2026-10-18 | `remote/io.github.daniel3303/equibles` | 2026-10-18T125009621368 -> 2026-10-18T185955005486 | 2 changed, 2 added | quiet |
| 2026-10-18 | `remote/online.putit/put-it-online` | 2026-10-17T055411554631 -> 2026-10-18T185953386451 | 8 changed | quiet |
| 2026-10-18 | `remote/io.github.89rat/code402` | 2026-10-17T110645904710 -> 2026-10-18T185952261530 | 2 changed | quiet |
| 2026-10-18 | `remote/io.github.fxams/crewpay-mcp` | 2026-10-17T055342417076 -> 2026-10-18T185950787418 | 16 changed (every tool) | quiet |
| 2026-10-18 | `remote/tech.ydb-qdrant.pets/codex-pets-ydb-qdrant` | 2026-10-17T055353458702 -> 2026-10-18T185948279985 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.adpadinc/brinkeradvisor-rates` | 2026-10-17T055334217423 -> 2026-10-18T185948751074 | 2 changed | quiet |
| 2026-10-18 | `remote/io.github.cueqzapper/picorn` | 2026-10-18T113157300496 -> 2026-10-18T185947286755 | 3 changed | quiet |
| 2026-10-18 | `remote/pro.aicut/aicut` | 2026-10-17T055315316075 -> 2026-10-18T185946344540 | 1 changed | quiet |
| 2026-10-18 | `remote/com.owlchart/owlchart` | 2026-10-17T185324361098 -> 2026-10-18T185946827559 | 1 changed, 4 added | quiet |
| 2026-10-18 | `remote/nyc.motley/mcp` | 2026-10-17T055935419380 -> 2026-10-18T185944050248 | 2 changed | quiet |
| 2026-10-18 | `remote/io.github.si-imtiaz/leadquasar` | 2026-10-18T051255478299 -> 2026-10-18T185942081517 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 22499 substantive, 9672 that changed only numbers (a catalogue counter ticking, a date), 475 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 16224 | 7212 | 9012 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 143 | 143 | 0 | 0 |
| `sistaminuten.se` | 115 | 4 | 0 | 111 |
| `afbudsrejser.dk` | 114 | 4 | 0 | 110 |
| `akkilahdot.fi` | 114 | 4 | 0 | 110 |
| `restplass.no` | 114 | 4 | 0 | 110 |
| `socialloop.ai` | 111 | 111 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `remoshift.com` | 85 | 6 | 79 | 0 |
| `fundinglandscape.com` | 84 | 51 | 33 | 0 |
| 3981 other operators | 12451 | 11869 | 548 | 34 |
