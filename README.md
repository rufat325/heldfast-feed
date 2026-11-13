# MCP server tool changes

Last change observed 2026-11-13T01:32:36+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

95187 changes to a tool definition: 4016 npm releases (3770 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 91171 readings of hosted servers that found their tools changed; 3859 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-13 | `remote/com.yazilimkocu/erp` | 2026-11-11T230952741415 -> 2026-11-13T013240452040 | 2 changed, 1 added | quiet |
| 2026-11-13 | `remote/com.yazilimkocu/crm` | 2026-11-11T230952608345 -> 2026-11-13T013240606248 | 2 changed, 1 added | quiet |
| 2026-11-13 | `remote/com.mintlify/searchmcp` | 2026-11-11T150127780779 -> 2026-11-13T013231699066 | 1 changed | quiet |
| 2026-11-13 | `remote/studio.gradients/mcp` | 2026-11-12T171005136795 -> 2026-11-13T013230115281 | 1 changed | quiet |
| 2026-11-13 | `remote/fi.akkilahdot/travel-search` | 2026-11-12T170941051795 -> 2026-11-13T013228902691 | 1 changed | quiet |
| 2026-11-13 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-11T230927535975 -> 2026-11-13T013229015356 | 3 changed | quiet |
| 2026-11-13 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-12T074758969120 -> 2026-11-13T013228927879 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-12T170941610019 -> 2026-11-13T013229406026 | 16 added | quiet |
| 2026-11-13 | `remote/ru.vedarai/mcp` | 2026-11-12T170938054321 -> 2026-11-13T013227585137 | 5 changed | quiet |
| 2026-11-13 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-12T074758179811 -> 2026-11-13T013227891955 | 4 changed | quiet |
| 2026-11-13 | `remote/io.github.ysgjay/token-command-center` | 2026-11-12T155118372190 -> 2026-11-13T013223101975 | 3 changed | quiet |
| 2026-11-13 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-11-12T074744955859 -> 2026-11-13T013223363659 | 31 changed | quiet |
| 2026-11-13 | `remote/io.github.Fizzl13/x402-doctor` | 2026-11-12T155010201901 -> 2026-11-13T013223124259 | 1 changed | quiet |
| 2026-11-13 | `remote/dev.workers.moneytools.x402-pay-precheck/pay-precheck` | 2026-11-12T155010561044 -> 2026-11-13T013223470963 | 1 changed | review |
| 2026-11-13 | `remote/com.yazilimkocu/yapayzeka` | 2026-11-11T230900927292 -> 2026-11-13T013224377118 | 2 changed, 1 added | quiet |
| 2026-11-13 | `remote/com.yazilimkocu/belediye` | 2026-11-11T230900862808 -> 2026-11-13T013224738165 | 2 changed, 1 added | quiet |
| 2026-11-13 | `remote/io.taifoon/coordination-layer.1` | 2026-11-12T074743660134 -> 2026-11-13T013227941011 | 1 changed | review |
| 2026-11-13 | `remote/io.github.homeaccount7/signaldock` | 2026-11-11T071430433247 -> 2026-11-13T013223488634 | 8 added | quiet |
| 2026-11-13 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-12T074755144631 -> 2026-11-13T013223105318 | 1 changed | quiet |
| 2026-11-13 | `remote/com.yazilimkocu/pazaryeri` | 2026-11-11T230916064339 -> 2026-11-13T013223617148 | 2 changed, 1 added | quiet |
| 2026-11-13 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-12T155108651999 -> 2026-11-13T013223601551 | 2 changed | quiet |
| 2026-11-13 | `remote/com.socialfaktory/mcp` | 2026-11-11T150018971930 -> 2026-11-13T013222270673 | 1 changed | quiet |
| 2026-11-13 | `remote/se.sistaminuten/travel-search` | 2026-11-12T170939736423 -> 2026-11-13T013221516391 | 1 changed | quiet |
| 2026-11-13 | `remote/network.lucie/sync` | 2026-11-11T145912629729 -> 2026-11-13T013221279845 | 2 changed | quiet |
| 2026-11-13 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-12T154924890136 -> 2026-11-13T013221783525 | 3 changed | quiet |
| 2026-11-13 | `remote/com.onlyworlds/mcp` | 2026-11-11T071423384122 -> 2026-11-13T013221129705 | 1 changed | quiet |
| 2026-11-13 | `remote/com.kaicalls/kaicalls` | 2026-11-12T170937569584 -> 2026-11-13T013221017416 | 1 changed, 2 added | quiet |
| 2026-11-13 | `remote/uk.swiftedge/orderflow` | 2026-11-12T155045751528 -> 2026-11-13T013221023342 | 10 changed | quiet |
| 2026-11-13 | `remote/io.escrova/escrova` | 2026-11-11T230853266995 -> 2026-11-13T013220194288 | 1 changed | quiet |
| 2026-11-13 | `remote/io.suverse.versum/catalog` | 2026-11-12T074734343213 -> 2026-11-13T013226617670 | 4 changed | quiet |
| 2026-11-13 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-12T170921205501 -> 2026-11-13T013217711373 | 1 changed | quiet |
| 2026-11-13 | `remote/com.blitzreels/blitzreels` | 2026-11-11T230852594783 -> 2026-11-13T013218756721 | 3 changed | quiet |
| 2026-11-13 | `remote/com.seoulstart/seoulstart` | 2026-11-12T154915763012 -> 2026-11-13T013214850430 | 1 changed | quiet |
| 2026-11-13 | `remote/app.vercel.watchesinstock-mcp/watches-in-stock` | 2026-11-12T154925417087 -> 2026-11-13T013213090729 | 4 changed | quiet |
| 2026-11-13 | `remote/io.github.exquad/thecablecode` | 2026-11-11T230852777365 -> 2026-11-13T013213216454 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.bnth09productions-maker/scrapling-x402-store` | 2026-11-11T071338619495 -> 2026-11-13T013212385000 | 5 added | quiet |
| 2026-11-13 | `remote/com.kyde/score` | 2026-11-12T154856336355 -> 2026-11-13T013212658176 | 1 changed | quiet |
| 2026-11-13 | `remote/com.googleapis.run/mcp` | 2026-11-12T170912923216 -> 2026-11-13T013210799738 | 1 changed | quiet |
| 2026-11-13 | `remote/app.usesnippet/snippet` | 2026-11-12T074735989212 -> 2026-11-13T013210584460 | 3 added | quiet |
| 2026-11-13 | `remote/dev.moneytools/tools` | 2026-11-12T154825333453 -> 2026-11-13T013208180271 | 1 changed | review |
| 2026-11-13 | `remote/com.thefomite/fomite` | 2026-11-12T074733097900 -> 2026-11-13T013207551090 | 1 changed | quiet |
| 2026-11-13 | `remote/no.pristavla/pristavla` | 2026-11-11T230850964621 -> 2026-11-13T013206276247 | 1 changed | quiet |
| 2026-11-13 | `remote/io.github.scraping-api-plans/web-data-plan-finder` | 2026-11-12T170906937895 -> 2026-11-13T013207144708 | 9 changed | quiet |
| 2026-11-13 | `remote/io.github.cryptoconspiracy/vurto-swap` | 2026-11-12T154749140204 -> 2026-11-13T013205310570 | 1 changed | review |
| 2026-11-13 | `remote/io.github.MsingathiM/swapeazi` | 2026-11-12T154757806941 -> 2026-11-13T013206292219 | 1 changed | quiet |
| 2026-11-13 | `remote/now.salesjobs/mcp` | 2026-11-12T154541703891 -> 2026-11-13T013204264602 | 1 changed | quiet |
| 2026-11-13 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-11-12T074722668464 -> 2026-11-13T013204595040 | 1 changed | quiet |
| 2026-11-13 | `remote/com.signalaf/sigrank` | 2026-11-11T145645922718 -> 2026-11-13T013202662113 | 16 changed (every tool) | quiet |
| 2026-11-13 | `remote/io.github.pbchrist/iconic-intelligence-reserve` | 2026-11-11T230845253295 -> 2026-11-13T013202691418 | 4 changed, 10 added | quiet |
| 2026-11-13 | `remote/dev.releasealert/mcp` | 2026-11-11T145554294260 -> 2026-11-13T013200785242 | 8 changed, 4 added (every tool) | quiet |
| 2026-11-13 | `remote/io.github.rnwy/mcp` | 2026-11-12T074727054830 -> 2026-11-13T013156622688 | 1 changed, 1 added | quiet |
| 2026-11-13 | `remote/com.obriym-crm/mcp` | 2026-11-11T145605441887 -> 2026-11-13T013157640604 | 4 changed, 9 added | quiet |
| 2026-11-13 | `remote/app.pitbi/pitbi` | 2026-11-12T074718553696 -> 2026-11-13T013157654128 | 3 changed | quiet |
| 2026-11-13 | `remote/app.permtracker/perm-tracker` | 2026-11-11T145454106266 -> 2026-11-13T013156623082 | 1 changed | quiet |
| 2026-11-13 | `remote/com.multicinesortega/cartelera` | 2026-11-12T074732463811 -> 2026-11-13T013156712955 | 1 changed | quiet |
| 2026-11-13 | `remote/ca.movahedi/privacy` | 2026-11-12T154627109770 -> 2026-11-13T013154842295 | 1 added | quiet |
| 2026-11-13 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-12T170855165333 -> 2026-11-13T013155470721 | 3 changed | review |
| 2026-11-13 | `remote/io.github.jweezy119/Pabandi` | 2026-11-12T074716515359 -> 2026-11-13T013154690441 | 1 changed, 1 added | quiet |
| 2026-11-13 | `remote/io.github.OptimNow/ai-pricing-hub` | 2026-11-12T154358803196 -> 2026-11-13T013155056030 | 2 changed | quiet |
| 2026-11-13 | `remote/pl.finwire/data` | 2026-11-11T230821438624 -> 2026-11-13T013154049408 | 1 changed, 3 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 59125 substantive, 35084 that changed only numbers (a catalogue counter ticking, a date), 978 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 50678 | 17757 | 32921 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 2242 | 2242 | 0 | 0 |
| `caseyjhand.com` | 402 | 402 | 0 | 0 |
| `civai.co` | 317 | 317 | 0 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `revmesh2074.workers.dev` | 239 | 209 | 30 | 0 |
| `sistaminuten.se` | 228 | 6 | 0 | 222 |
| `afbudsrejser.dk` | 227 | 6 | 0 | 221 |
| `akkilahdot.fi` | 227 | 6 | 0 | 221 |
| `restplass.no` | 227 | 6 | 0 | 221 |
| `socialloop.ai` | 219 | 219 | 0 | 0 |
| 9138 other operators | 37582 | 35356 | 2133 | 93 |
