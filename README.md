# MCP server tool changes

Last change observed 2026-10-09T06:48:17+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10128 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 21701 hosted endpoints (read daily, and every four hours while they keep changing).

25480 changes to a tool definition: 870 npm releases (624 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 24610 readings of hosted servers that found their tools changed; 367 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-09 | `remote/no.restplass/travel-search` | 2026-10-08T213453768873 -> 2026-10-09T064818896164 | 1 changed | quiet |
| 2026-10-09 | `remote/com.theprotoclinical/commerce` | 2026-10-08T135528072987 -> 2026-10-09T064817128823 | 1 changed | quiet |
| 2026-10-09 | `remote/dk.afbudsrejser/travel-search` | 2026-10-08T213448239731 -> 2026-10-09T064817083217 | 1 changed | quiet |
| 2026-10-09 | `remote/dev.primitive/email` | 2026-10-08T135522664784 -> 2026-10-09T064816305817 | 13 changed, 1 added, 17 removed (every tool) | quiet |
| 2026-10-09 | `remote/tennis.courts/nyc-tennis-courts` | 2026-10-08T135459881812 -> 2026-10-09T064815316698 | 3 changed | quiet |
| 2026-10-09 | `remote/io.github.ohad6k/viberaven-guides` | 2026-10-07T213838774046 -> 2026-10-09T064815606118 | 2 changed | quiet |
| 2026-10-09 | `remote/io.github.VoiceScapee/voicescape` | 2026-10-08T155527832487 -> 2026-10-09T064814750744 | 7 changed, 1 added | quiet |
| 2026-10-09 | `remote/fi.akkilahdot/travel-search` | 2026-10-08T213436617905 -> 2026-10-09T064814384034 | 1 changed | quiet |
| 2026-10-09 | `remote/com.underpricedai/underpriced-ai` | 2026-10-08T135443169463 -> 2026-10-09T064814944302 | 6 changed (every tool) | quiet |
| 2026-10-09 | `remote/io.github.CodeWever/wever-labs-products` | 2026-10-08T064243123005 -> 2026-10-09T064815403338 | 1 changed | quiet |
| 2026-10-09 | `remote/com.trustbaselab/rcb-data` | 2026-10-08T135438644070 -> 2026-10-09T064815028150 | 1 changed | quiet |
| 2026-10-09 | `remote/ai.trydock/dock` | 2026-10-08T213442228672 -> 2026-10-09T064813619331 | 1 changed, 1 added | quiet |
| 2026-10-09 | `remote/com.tickerz/tickerz` | 2026-10-08T135427478016 -> 2026-10-09T064812402543 | 3 changed | quiet |
| 2026-10-09 | `remote/ru.vedarai/mcp` | 2026-10-08T213434173476 -> 2026-10-09T064812927624 | 3 changed | quiet |
| 2026-10-09 | `remote/io.simplyprint/simplyprint` | 2026-10-08T213434154596 -> 2026-10-09T064812674328 | 1 changed | quiet |
| 2026-10-09 | `remote/io.github.Timothymycompc/solana-pulse-gateway` | 2026-10-08T135352972802 -> 2026-10-09T064811199857 | 5 changed, 10 added | review |
| 2026-10-09 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-08T155522663521 -> 2026-10-09T064810830711 | 1 changed | quiet |
| 2026-10-09 | `remote/com.swarmmemo/bulletin` | 2026-10-08T155522389588 -> 2026-10-09T064810999641 | 80 changed (every tool) | quiet |
| 2026-10-09 | `remote/io.github.JacobiusMakes/stienhardt-store` | 2026-10-08T135357119772 -> 2026-10-09T064808448425 | 1 changed | quiet |
| 2026-10-09 | `remote/com.renderball/renderball` | 2026-10-08T213427828665 -> 2026-10-09T064808808050 | 11 changed (every tool) | quiet |
| 2026-10-09 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-08T213423759478 -> 2026-10-09T064808281080 | 1 changed | quiet |
| 2026-10-09 | `remote/ai.shorti/shorti` | 2026-10-08T213423448129 -> 2026-10-09T064809004787 | 2 changed | quiet |
| 2026-10-09 | `remote/io.github.LAHutchins91/patent` | 2026-10-08T213421200654 -> 2026-10-09T064805818086 | 4 changed (every tool) | quiet |
| 2026-10-09 | `remote/com.seqbench/workbench` | 2026-10-08T135332430877 -> 2026-10-09T064806538902 | 1 changed, 1 added | quiet |
| 2026-10-09 | `remote/com.remoshift/jobs` | 2026-10-08T135308048290 -> 2026-10-09T064805881741 | 1 changed | quiet |
| 2026-10-09 | `remote/ch.kulalabs.pazair/pazair` | 2026-10-08T213423353953 -> 2026-10-09T064806629570 | 1 added | quiet |
| 2026-10-09 | `remote/com.thetempleofdoom.osint-mcp/osint-terminal` | 2026-10-08T155459377753 -> 2026-10-09T064806188158 | 3 added | quiet |
| 2026-10-09 | `remote/io.github.smarterweather/weather` | 2026-10-07T213810364813 -> 2026-10-09T064802832691 | 3 changed | quiet |
| 2026-10-09 | `remote/io.github.scimo2021/moneygrid-gridwatch` | 2026-10-08T135155677235 -> 2026-10-09T064801747558 | 3 changed | review |
| 2026-10-09 | `remote/com.musedin/musedin` | 2026-10-08T213408060335 -> 2026-10-09T064802394988 | 17 changed, 1 added | quiet |
| 2026-10-09 | `remote/com.multicinesortega/cartelera` | 2026-10-08T213408699286 -> 2026-10-09T064803127284 | 1 changed | quiet |
| 2026-10-09 | `remote/com.jojapi/swift-ai` | 2026-10-08T064212629315 -> 2026-10-09T064757774447 | 1 changed | quiet |
| 2026-10-09 | `remote/com.budgetpixel/mcp` | 2026-10-07T001233178840 -> 2026-10-09T064756893786 | 1 changed, 1 added | quiet |
| 2026-10-09 | `remote/ai.forkmate/forkmate` | 2026-10-08T155441374747 -> 2026-10-09T064757064229 | 3 changed | quiet |
| 2026-10-09 | `remote/com.donebear/donebear` | 2026-10-08T134944065905 -> 2026-10-09T064756955467 | 2 changed | quiet |
| 2026-10-09 | `remote/io.github.Book0fEli/paycheck` | 2026-10-07T063258616826 -> 2026-10-09T064755347241 | 2 changed | quiet |
| 2026-10-09 | `remote/com.manjangilchi/manjangilchi` | 2026-10-08T213357364614 -> 2026-10-09T064755938412 | 1 added | quiet |
| 2026-10-09 | `remote/io.github.tang-vu/keryx` | 2026-10-08T213352965954 -> 2026-10-09T064755905726 | 2 changed, 2 added | quiet |
| 2026-10-09 | `remote/io.github.sean0007/free-agent-tools` | 2026-10-07T001215475324 -> 2026-10-09T064751754505 | 1 added | quiet |
| 2026-10-09 | `remote/trade.loomdesk/loomdesk` | 2026-10-08T213348440525 -> 2026-10-09T064753537146 | 4 changed | quiet |
| 2026-10-09 | `remote/au.com.alpineai/factstamp` | 2026-10-07T154846793962 -> 2026-10-09T064750219810 | 1 added | quiet |
| 2026-10-09 | `remote/io.github.getDynamoi/dynamoi` | 2026-10-08T155413041707 -> 2026-10-09T064750759123 | 2 changed | quiet |
| 2026-10-09 | `remote/io.github.si-imtiaz/leadquasar` | 2026-10-08T134842258217 -> 2026-10-09T064749497714 | 1 changed | quiet |
| 2026-10-09 | `remote/io.github.eamwhite1/xrpl-referee` | 2026-10-08T135551123754 -> 2026-10-09T064746704129 | 1 changed | quiet |
| 2026-10-09 | `remote/com.youspot/youspot` | 2026-10-08T213417440212 -> 2026-10-09T064745979939 | 2 changed, 2 added | quiet |
| 2026-10-09 | `remote/se.sistaminuten/travel-search` | 2026-10-08T213558717934 -> 2026-10-09T064744759159 | 1 changed | quiet |
| 2026-10-09 | `remote/com.thenewengineer/hvac` | 2026-10-08T213409009388 -> 2026-10-09T064743725519 | 1 changed | quiet |
| 2026-10-09 | `remote/io.stackcut/stackcut` | 2026-10-08T213404796485 -> 2026-10-09T064741951411 | 4 changed | quiet |
| 2026-10-09 | `remote/com.thefomite/fomite` | 2026-10-08T155635911034 -> 2026-10-09T064742654734 | 1 changed | quiet |
| 2026-10-09 | `remote/com.dechonet/mcp` | 2026-10-07T154841338525 -> 2026-10-09T064748601108 | 2 added | quiet |
| 2026-10-09 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-08T213548826516 -> 2026-10-09T064743511734 | 3 changed | quiet |
| 2026-10-09 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-07T154942319866 -> 2026-10-09T064741467617 | 1 changed | quiet |
| 2026-10-09 | `remote/net.hotelrefund/price-tracker` | 2026-10-08T064154207023 -> 2026-10-09T064743522165 | 1 changed | quiet |
| 2026-10-09 | `remote/com.sfxmint/sounds` | 2026-10-08T135303925111 -> 2026-10-09T064740136616 | 1 changed, 6 added | review |
| 2026-10-09 | `remote/io.github.mooshee/govgazette` | 2026-10-08T213340188666 -> 2026-10-09T064743128546 | 6 added, 1 removed | quiet |
| 2026-10-09 | `remote/com.scribiz/mcp` | 2026-10-08T064233298279 -> 2026-10-09T064740433206 | 5 changed (every tool) | quiet |
| 2026-10-09 | `remote/ai.satohub/onchain-agents` | 2026-10-08T213523411800 -> 2026-10-09T064741313133 | 41 changed (every tool) | quiet |
| 2026-10-09 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-08T064225357719 -> 2026-10-09T064740762206 | 1 changed | quiet |
| 2026-10-09 | `remote/io.github.richardjhobbs/rrg-marketplace` | 2026-10-08T135240036987 -> 2026-10-09T064739222649 | 2 changed | quiet |
| 2026-10-09 | `remote/io.github.89rat/code402` | 2026-10-07T063328647831 -> 2026-10-09T064737176381 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 17139 substantive, 7981 that changed only numbers (a catalogue counter ticking, a date), 360 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 13231 | 5706 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 538 | 538 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `sistaminuten.se` | 87 | 2 | 0 | 85 |
| `afbudsrejser.dk` | 86 | 2 | 0 | 84 |
| `akkilahdot.fi` | 86 | 2 | 0 | 84 |
| `restplass.no` | 86 | 2 | 0 | 84 |
| `socialloop.ai` | 84 | 84 | 0 | 0 |
| `caseyjhand.com` | 77 | 77 | 0 | 0 |
| `dayze.com` | 69 | 69 | 0 | 0 |
| `fundinglandscape.com` | 61 | 36 | 25 | 0 |
| 3052 other operators | 8637 | 8183 | 431 | 23 |
