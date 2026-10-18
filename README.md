# MCP server tool changes

Last change observed 2026-10-18T05:15:42+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10495 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 23695 hosted endpoints (read daily, and every four hours while they keep changing).

30602 changes to a tool definition: 1052 npm releases (806 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 29550 readings of hosted servers that found their tools changed; 2073 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-18 | `remote/com.starcovery/mcp` | 2026-10-17T185412456801 -> 2026-10-18T051544025771 | 5 changed, 2 added, 2 removed | quiet |
| 2026-10-18 | `remote/no.restplass/travel-search` | 2026-10-17T224423103453 -> 2026-10-18T051542321767 | 1 changed | quiet |
| 2026-10-18 | `remote/ar.mueblito/mueblito` | 2026-10-17T060447494976 -> 2026-10-18T051541341235 | 8 changed | quiet |
| 2026-10-18 | `remote/dk.afbudsrejser/travel-search` | 2026-10-17T224414764687 -> 2026-10-18T051530650154 | 1 changed | quiet |
| 2026-10-18 | `remote/ai.trydock/dock` | 2026-10-17T060353096749 -> 2026-10-18T051525721087 | 3 changed, 1 added | quiet |
| 2026-10-18 | `remote/com.tradeassi/mcp` | 2026-10-17T060350212240 -> 2026-10-18T051516845710 | 1 changed | quiet |
| 2026-10-18 | `remote/com.thegtmdirectory/mcp` | 2026-10-17T060339117886 -> 2026-10-18T051514789852 | 2 changed, 2 added | quiet |
| 2026-10-18 | `remote/io.github.boriskendev/stormap` | 2026-10-17T224401521667 -> 2026-10-18T051510643620 | 1 changed | quiet |
| 2026-10-18 | `remote/at.space-core/game` | 2026-10-17T060311932081 -> 2026-10-18T051507549107 | 1 added | quiet |
| 2026-10-18 | `remote/io.github.Project-Gifted1/pg1-threat-intel` | 2026-10-17T060131682893 -> 2026-10-18T051444301085 | 1 changed | quiet |
| 2026-10-18 | `remote/im.peoplesearch/email-finder` | 2026-10-17T070222404886 -> 2026-10-18T051443725538 | 2 changed | quiet |
| 2026-10-18 | `remote/how.mise/mise` | 2026-10-17T224340218632 -> 2026-10-18T051436062007 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.valuein/mcp-sec-edgar.1` | 2026-10-17T060025069475 -> 2026-10-18T051431329533 | 1 changed | quiet |
| 2026-10-18 | `remote/com.partstable/partstable` | 2026-10-17T055946268386 -> 2026-10-18T051414349329 | 2 changed | quiet |
| 2026-10-18 | `remote/io.github.cyanheads/zenodo-mcp-server` | 2026-10-17T060005012548 -> 2026-10-18T051410676940 | 6 changed (every tool) | quiet |
| 2026-10-18 | `remote/ai.ohmyfin/banking-intelligence` | 2026-10-17T055941882296 -> 2026-10-18T051421134943 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.77777R7/octocrawl` | 2026-10-17T224326848059 -> 2026-10-18T051410051298 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.Licium-ai/licium` | 2026-10-17T055944458455 -> 2026-10-18T051404569767 | 2 changed, 2 added | quiet |
| 2026-10-18 | `remote/com.immersivecommons/floor10` | 2026-10-17T111242113497 -> 2026-10-18T051404625130 | 1 changed, 1 added | quiet |
| 2026-10-18 | `remote/io.github.privatelawattorneys/wiki-private-law` | 2026-10-17T224356339489 -> 2026-10-18T051400430577 | 3 changed | quiet |
| 2026-10-18 | `remote/fi.akkilahdot/travel-search` | 2026-10-17T224355313416 -> 2026-10-18T051400473100 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.CodeWever/wever-labs-products` | 2026-10-17T055912756598 -> 2026-10-18T051358639106 | 2 changed | quiet |
| 2026-10-18 | `remote/direct.vote/vote-direct` | 2026-10-17T055906719827 -> 2026-10-18T051357053995 | 2 changed | quiet |
| 2026-10-18 | `remote/io.github.veredamonte-glitch/verithic` | 2026-10-17T224353331705 -> 2026-10-18T051356245052 | 1 changed | quiet |
| 2026-10-18 | `remote/us.srv.vehcdj664efetfrsolne5umanq/quoteproof-mcp` | 2026-10-17T224352525044 -> 2026-10-18T051356069633 | 11 changed, 1 added | quiet |
| 2026-10-18 | `remote/ru.vedarai/mcp` | 2026-10-17T055901659401 -> 2026-10-18T051354633048 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.zambodotdev/zambo` | 2026-10-17T122821517638 -> 2026-10-18T051353316366 | 35 changed (every tool) | quiet |
| 2026-10-18 | `remote/dev.zambo/zambo` | 2026-10-17T122821637650 -> 2026-10-18T051353382124 | 35 changed (every tool) | quiet |
| 2026-10-18 | `remote/com.youspot/youspot` | 2026-10-17T224521612779 -> 2026-10-18T051353894094 | 9 added | quiet |
| 2026-10-18 | `remote/com.etfiq/etfiq` | 2026-10-17T224320385342 -> 2026-10-18T051353261352 | 5 changed, 2 added | quiet |
| 2026-10-18 | `remote/io.dropyour/dropyour` | 2026-10-17T122740925782 -> 2026-10-18T051401097139 | 1 changed | quiet |
| 2026-10-18 | `remote/com.veridionmarkets/disclosures` | 2026-10-17T185359541486 -> 2026-10-18T051350481933 | 2 changed | quiet |
| 2026-10-18 | `remote/com.rightshold/rightshold` | 2026-10-17T224514579463 -> 2026-10-18T051350323441 | 1 changed | quiet |
| 2026-10-18 | `remote/io.taifoon/coordination-layer.1` | 2026-10-17T122905896408 -> 2026-10-18T051349738204 | 1 changed | review |
| 2026-10-18 | `remote/se.sistaminuten/travel-search` | 2026-10-17T224417955539 -> 2026-10-18T051348177487 | 1 changed | quiet |
| 2026-10-18 | `remote/ca.tonbot.tolca/tolca` | 2026-10-17T055840665906 -> 2026-10-18T051347561378 | 1 added | review |
| 2026-10-18 | `remote/io.kolmo.www/kolmo-mcp-server` | 2026-10-17T224416522440 -> 2026-10-18T051346378685 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-17T224346264935 -> 2026-10-18T051346236704 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.dtajitdinov-aris/sphere-marketplace` | 2026-10-17T224344143898 -> 2026-10-18T051343549710 | 8 changed | quiet |
| 2026-10-18 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-17T224340532266 -> 2026-10-18T051339787292 | 1 changed | quiet |
| 2026-10-18 | `remote/world.staylist/staylist` | 2026-10-17T110743292913 -> 2026-10-18T051337499587 | 1 changed | quiet |
| 2026-10-18 | `remote/com.thefomite/fomite` | 2026-10-17T055506241056 -> 2026-10-18T051335886119 | 1 changed | quiet |
| 2026-10-18 | `remote/com.remoshift/jobs` | 2026-10-17T224335564831 -> 2026-10-18T051335265366 | 1 changed | quiet |
| 2026-10-18 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-17T060120843128 -> 2026-10-18T051331459064 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.scraping-api-plans/web-data-plan-finder` | 2026-10-17T055659020991 -> 2026-10-18T051331128316 | 5 changed | quiet |
| 2026-10-18 | `remote/me.phor/phorme-training` | 2026-10-17T224328722317 -> 2026-10-18T051328257225 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.SidneyBissoli/senado-br-mcp-cloudflare` | 2026-10-17T055436891280 -> 2026-10-18T051326321322 | 2 changed | quiet |
| 2026-10-18 | `remote/ai.satohub/onchain-agents` | 2026-10-17T055429085319 -> 2026-10-18T051324917358 | 4 changed | quiet |
| 2026-10-18 | `remote/com.odilelabs/odile` | 2026-10-17T055629471896 -> 2026-10-18T051325385199 | 1 changed, 1 added | review |
| 2026-10-18 | `remote/com.multicinesortega/cartelera` | 2026-10-17T224323233827 -> 2026-10-18T051324132856 | 1 changed | quiet |
| 2026-10-18 | `remote/com.idevice/wearables` | 2026-10-17T224305346156 -> 2026-10-18T051322540611 | 2 changed | quiet |
| 2026-10-18 | `remote/com.oceanalt/aml` | 2026-10-17T110559701923 -> 2026-10-18T051317128276 | 1 added | quiet |
| 2026-10-18 | `remote/io.github.jamboree777/nightwatch` | 2026-10-17T060000501911 -> 2026-10-18T051315400558 | 3 changed | quiet |
| 2026-10-18 | `remote/app.soclo/soclo-mcp` | 2026-10-17T110906224056 -> 2026-10-18T051316444223 | 30 changed, 3 added | quiet |
| 2026-10-18 | `remote/io.github.vassiliylakhonin/agenda-intelligence-md.1` | 2026-10-17T224343602775 -> 2026-10-18T051312384184 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.kirillradchenko96/fresh402` | 2026-10-17T054824592315 -> 2026-10-18T051311878082 | 5 changed (every tool) | review |
| 2026-10-18 | `remote/io.github.vicentesurraco/offpeak` | 2026-10-17T055340867193 -> 2026-10-18T051323422887 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.sean0007/free-agent-tools` | 2026-10-17T054823141321 -> 2026-10-18T051310675980 | 1 added | quiet |
| 2026-10-18 | `remote/io.github.magichourhq/magic-hour` | 2026-10-17T055437785473 -> 2026-10-18T051308824938 | 1 changed | quiet |
| 2026-10-18 | `remote/dev.mcphost/mcphost` | 2026-10-17T185309292835 -> 2026-10-18T051309767680 | 6 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 21982 substantive, 8158 that changed only numbers (a catalogue counter ticking, a date), 462 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 14726 | 7201 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 129 | 129 | 0 | 0 |
| `sistaminuten.se` | 112 | 4 | 0 | 108 |
| `afbudsrejser.dk` | 111 | 4 | 0 | 107 |
| `akkilahdot.fi` | 111 | 4 | 0 | 107 |
| `restplass.no` | 111 | 4 | 0 | 107 |
| `socialloop.ai` | 108 | 108 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `fundinglandscape.com` | 82 | 50 | 32 | 0 |
| `remoshift.com` | 82 | 6 | 76 | 0 |
| 3813 other operators | 11939 | 11381 | 525 | 33 |
