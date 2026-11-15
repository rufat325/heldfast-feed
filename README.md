# MCP server tool changes

Last change observed 2026-11-15T00:23:54+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

99388 changes to a tool definition: 4181 npm releases (3935 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 95207 readings of hosted servers that found their tools changed; 4119 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-15 | `remote/no.restplass/travel-search` | 2026-11-14T183359457976 -> 2026-11-15T002354839166 | 1 changed | quiet |
| 2026-11-15 | `remote/com.tabflows/site` | 2026-11-14T115023658772 -> 2026-11-15T002355673357 | 1 changed | quiet |
| 2026-11-15 | `remote/io.deeplead/deeplead` | 2026-11-14T115022033898 -> 2026-11-15T002355908630 | 5 changed | quiet |
| 2026-11-15 | `remote/app.fluxgraph/linkedin` | 2026-11-14T183356537738 -> 2026-11-15T002353886627 | 1 changed | quiet |
| 2026-11-15 | `remote/dk.afbudsrejser/travel-search` | 2026-11-14T183355552170 -> 2026-11-15T002353700007 | 1 changed | quiet |
| 2026-11-15 | `remote/com.wht-ai/wai` | 2026-11-14T140109798063 -> 2026-11-15T002353085531 | 1 changed | quiet |
| 2026-11-15 | `remote/com.photoprintagent/mcp` | 2026-11-14T135702013053 -> 2026-11-15T002342723454 | 7 changed, 1 added | quiet |
| 2026-11-15 | `remote/app.lovable.privacy-pill-consent-studio/privacypill` | 2026-11-13T200743131677 -> 2026-11-15T002344330893 | 1 changed | quiet |
| 2026-11-15 | `remote/app.lovable.peppol-invoice-compass/invoiceverify` | 2026-11-14T115001653399 -> 2026-11-15T002347141555 | 1 added | quiet |
| 2026-11-15 | `remote/io.github.jdhart81/disclosure-compiler` | 2026-11-14T114950518181 -> 2026-11-15T002338525827 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.smarterweather/weather` | 2026-11-13T200726764065 -> 2026-11-15T002337810451 | 1 changed | quiet |
| 2026-11-15 | `remote/com.tickerdb/mcp-server` | 2026-11-14T114950168080 -> 2026-11-15T002338676387 | 1 changed, 2 added | quiet |
| 2026-11-15 | `remote/io.github.faxforagents/faxforagents-mcp` | 2026-11-13T013107193569 -> 2026-11-15T002334719631 | 17 changed (every tool) | quiet |
| 2026-11-15 | `remote/io.github.marian-kamenistak/elc-conference-mcp-tickets` | 2026-11-13T145848709736 -> 2026-11-15T002333786389 | 3 changed | quiet |
| 2026-11-15 | `remote/com.veridionmarkets/disclosures` | 2026-11-14T140422391725 -> 2026-11-15T002331933451 | 3 changed, 3 added | quiet |
| 2026-11-15 | `remote/co.deadbrands/arena` | 2026-11-14T183311170005 -> 2026-11-15T002331800834 | 7 changed, 6 added | quiet |
| 2026-11-15 | `remote/se.sistaminuten/travel-search` | 2026-11-14T183358567642 -> 2026-11-15T002331227209 | 1 changed | quiet |
| 2026-11-15 | `remote/studio.gradients/mcp` | 2026-11-14T183403651712 -> 2026-11-15T002329769762 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.SoapyRED/freightutils` | 2026-11-14T140207738108 -> 2026-11-15T002329820704 | 27 changed (every tool) | quiet |
| 2026-11-15 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-14T140152613689 -> 2026-11-15T002328732963 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-14T183403028524 -> 2026-11-15T002330899275 | 8 added | quiet |
| 2026-11-15 | `remote/fi.akkilahdot/travel-search` | 2026-11-14T183400699710 -> 2026-11-15T002328386981 | 1 changed | quiet |
| 2026-11-15 | `remote/com.blitzreels/blitzreels` | 2026-11-13T013218756721 -> 2026-11-15T002328485438 | 2 changed, 10 added | quiet |
| 2026-11-15 | `remote/xyz.iposignal/iposignal` | 2026-11-14T135116197374 -> 2026-11-15T002327159168 | 1 changed | quiet |
| 2026-11-15 | `remote/direct.vote/vote-direct` | 2026-11-13T120514027935 -> 2026-11-15T002326796466 | 1 changed | quiet |
| 2026-11-15 | `remote/app.vercel.watchesinstock-mcp/watches-in-stock` | 2026-11-13T013213090729 -> 2026-11-15T002327232868 | 7 changed | quiet |
| 2026-11-15 | `remote/ru.vedarai/mcp` | 2026-11-13T124204803212 -> 2026-11-15T002327683352 | 2 changed | quiet |
| 2026-11-15 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-14T183358461089 -> 2026-11-15T002327067995 | 3 changed | quiet |
| 2026-11-15 | `remote/com.heynutcracker/nutcracker` | 2026-11-14T183300840596 -> 2026-11-15T002326927007 | 1 changed | quiet |
| 2026-11-15 | `remote/com.thefomite/fomite` | 2026-11-14T010647427878 -> 2026-11-15T002325661668 | 1 changed | quiet |
| 2026-11-15 | `remote/com.ksaworks/goldseam` | 2026-11-14T114931139549 -> 2026-11-15T002324513586 | 44 changed | quiet |
| 2026-11-15 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-14T114929461624 -> 2026-11-15T002324599216 | 1 changed | quiet |
| 2026-11-15 | `remote/com.getmarsell/marsell` | 2026-11-14T183255893348 -> 2026-11-15T002325042965 | 2 changed, 2 added | quiet |
| 2026-11-15 | `remote/io.suverse.versum/catalog` | 2026-11-14T183342116640 -> 2026-11-15T002323540408 | 3 changed | quiet |
| 2026-11-15 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-14T183345645420 -> 2026-11-15T002321462313 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-14T183336604040 -> 2026-11-15T002321639616 | 1 added | quiet |
| 2026-11-15 | `remote/cc.thecolony/mcp-server` | 2026-11-14T183334744450 -> 2026-11-15T002321392574 | 2 changed | quiet |
| 2026-11-15 | `remote/com.prizepicksapi/server` | 2026-11-14T010633805278 -> 2026-11-15T002319669708 | 2 added | quiet |
| 2026-11-15 | `remote/gg.plazmi/plazmi` | 2026-11-14T010631149550 -> 2026-11-15T002317733795 | 2 changed | quiet |
| 2026-11-15 | `remote/io.ddx.pg/archive` | 2026-11-14T010630328097 -> 2026-11-15T002318018810 | 6 changed | quiet |
| 2026-11-15 | `remote/help.socket/socket-help` | 2026-11-14T135854013373 -> 2026-11-15T002319395265 | 3 changed, 1 added | quiet |
| 2026-11-15 | `remote/com.shopyourcolorseason/mcp` | 2026-11-14T135837897536 -> 2026-11-15T002317391778 | 2 changed, 1 added | quiet |
| 2026-11-15 | `remote/com.remoshift/jobs` | 2026-11-14T183336233454 -> 2026-11-15T002318244196 | 1 changed | quiet |
| 2026-11-15 | `remote/io.outil/outil` | 2026-11-13T013147292040 -> 2026-11-15T002318178659 | 3 changed, 4 added | quiet |
| 2026-11-15 | `remote/com.forevenza.services/requirements-desk` | 2026-11-14T135831926169 -> 2026-11-15T002316518040 | 1 changed | quiet |
| 2026-11-15 | `remote/com.forevenza.services/plumbline` | 2026-11-14T135754515483 -> 2026-11-15T002316147785 | 1 changed | quiet |
| 2026-11-15 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-11-14T010631540234 -> 2026-11-15T002316111488 | 1 changed | quiet |
| 2026-11-15 | `remote/pl.klyo/games` | 2026-11-13T145837227425 -> 2026-11-15T002315793437 | 3 changed | quiet |
| 2026-11-15 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt.2` | 2026-11-14T010600269718 -> 2026-11-15T002318724197 | 1 changed | quiet |
| 2026-11-15 | `remote/codes.onv/onv-mcp` | 2026-11-13T120024787909 -> 2026-11-15T002316649751 | 1 changed | quiet |
| 2026-11-15 | `remote/com.neblla/neblla` | 2026-11-14T135648366099 -> 2026-11-15T002313341188 | 4 changed | quiet |
| 2026-11-15 | `remote/com.multicinesortega/cartelera` | 2026-11-14T114958608220 -> 2026-11-15T002313839464 | 1 changed | quiet |
| 2026-11-15 | `remote/app.lovable.release-ripple-roadmap/logpulse` | 2026-11-14T183322857956 -> 2026-11-15T002317517309 | 1 added | quiet |
| 2026-11-15 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-14T183325346755 -> 2026-11-15T002312952677 | 2 changed | quiet |
| 2026-11-15 | `remote/gl.parse/mcp` | 2026-11-14T114922269002 -> 2026-11-15T002312791936 | 6 changed, 1 removed (every tool) | quiet |
| 2026-11-15 | `remote/io.github.jweezy119/Pabandi` | 2026-11-13T013154690441 -> 2026-11-15T002311112076 | 3 changed, 10 added, 61 removed (every tool) | quiet |
| 2026-11-15 | `remote/io.github.MelanieABC/misim-tax-research` | 2026-11-14T183313724414 -> 2026-11-15T002309763383 | 1 added | quiet |
| 2026-11-15 | `remote/com.othermindset/campus` | 2026-11-14T135631462671 -> 2026-11-15T002310197723 | 2 changed | quiet |
| 2026-11-15 | `remote/io.github.Kromatic-Innovation/neumann` | 2026-11-13T150051318371 -> 2026-11-15T002309157303 | 2 changed | quiet |
| 2026-11-15 | `remote/dev.notavibe/mcp` | 2026-11-14T135613819356 -> 2026-11-15T002310119522 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 61316 substantive, 37054 that changed only numbers (a catalogue counter ticking, a date), 1018 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 52535 | 17771 | 34764 | 0 |
| `a2awire.com` | 2508 | 2508 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 420 | 420 | 0 | 0 |
| `civai.co` | 318 | 318 | 0 | 0 |
| `revmesh2074.workers.dev` | 259 | 227 | 32 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `sistaminuten.se` | 237 | 6 | 0 | 231 |
| `afbudsrejser.dk` | 236 | 6 | 0 | 230 |
| `akkilahdot.fi` | 236 | 6 | 0 | 230 |
| `restplass.no` | 236 | 6 | 0 | 230 |
| `socialloop.ai` | 228 | 228 | 0 | 0 |
| 9380 other operators | 39576 | 37221 | 2258 | 97 |
