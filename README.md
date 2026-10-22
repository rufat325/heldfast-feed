# MCP server tool changes

Last change observed 2026-10-22T14:08:58+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

42546 changes to a tool definition: 1838 npm releases (1592 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 40708 readings of hosted servers that found their tools changed; 2374 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-22 | `remote/no.restplass/travel-search` | 2026-10-22T122026031968 -> 2026-10-22T140859408489 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.falsalama/proper-job` | 2026-10-21T122205974362 -> 2026-10-22T140858447453 | 1 changed | quiet |
| 2026-10-22 | `remote/dk.afbudsrejser/travel-search` | 2026-10-22T121945291477 -> 2026-10-22T140858394294 | 1 changed | quiet |
| 2026-10-22 | `remote/com.actualgroup/jobs` | 2026-10-22T121946857823 -> 2026-10-22T140858156820 | 6 changed (every tool) | quiet |
| 2026-10-22 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-10-22T052606759841 -> 2026-10-22T140858484820 | 1 changed | quiet |
| 2026-10-22 | `remote/com.vibe-fixer/vibefix` | 2026-10-22T105832569472 -> 2026-10-22T140854603557 | 2 changed | quiet |
| 2026-10-22 | `remote/fi.akkilahdot/travel-search` | 2026-10-22T122102518715 -> 2026-10-22T140853596188 | 1 changed | quiet |
| 2026-10-22 | `remote/se.sistaminuten/travel-search` | 2026-10-22T122012481540 -> 2026-10-22T140852780752 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.exquad/thecablecode` | 2026-10-22T105808117268 -> 2026-10-22T140852867639 | 1 added | quiet |
| 2026-10-22 | `remote/cc.thecolony/mcp-server` | 2026-10-22T105808627961 -> 2026-10-22T140852453039 | 1 changed | quiet |
| 2026-10-22 | `remote/gg.unicum/wot-stats` | 2026-10-22T105918123708 -> 2026-10-22T140852479967 | 1 changed | quiet |
| 2026-10-22 | `remote/com.cadprops/cadprops` | 2026-10-22T121951545820 -> 2026-10-22T140850770972 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-22T121931995301 -> 2026-10-22T140844990797 | 1 changed | quiet |
| 2026-10-22 | `remote/com.remoshift/jobs` | 2026-10-22T121834346596 -> 2026-10-22T140843228746 | 1 changed | quiet |
| 2026-10-22 | `remote/com.moonshotlab1/inventory` | 2026-10-21T234529567655 -> 2026-10-22T140840813886 | 1 changed | quiet |
| 2026-10-22 | `remote/pl.przetargowyjanusz/tenders` | 2026-10-22T105630283336 -> 2026-10-22T140841179489 | 1 added | quiet |
| 2026-10-22 | `remote/com.predictionmarketspicks/quant` | 2026-10-22T105623251110 -> 2026-10-22T140839960333 | 1 added | quiet |
| 2026-10-22 | `remote/ca.movahedi/privacy` | 2026-10-21T141059290438 -> 2026-10-22T140836095883 | 1 changed | quiet |
| 2026-10-22 | `remote/exchange.merx/mcp` | 2026-10-20T103958421814 -> 2026-10-22T140835187039 | 6 changed | quiet |
| 2026-10-22 | `remote/fr.ohmywind/sailing-planner` | 2026-10-22T105703197801 -> 2026-10-22T140834184893 | 2 changed | quiet |
| 2026-10-22 | `remote/com.webinarignition/mcp` | 2026-10-21T121733712653 -> 2026-10-22T140833909160 | 1 changed | quiet |
| 2026-10-22 | `remote/com.voicedispatcher/mcp-near-me` | 2026-10-22T052629601558 -> 2026-10-22T140832873083 | 1 changed | review |
| 2026-10-22 | `remote/be.vibedeploy/vibedeploy` | 2026-10-22T105450238501 -> 2026-10-22T140833109906 | 1 changed | quiet |
| 2026-10-22 | `remote/app.manawa/manawa-terminal` | 2026-10-22T105647788933 -> 2026-10-22T140831498080 | 2 changed | quiet |
| 2026-10-22 | `remote/ai.switchapp/switch` | 2026-10-22T121625356544 -> 2026-10-22T140831385366 | 7 changed, 1 added | quiet |
| 2026-10-22 | `remote/io.dropyour/dropyour` | 2026-10-22T121407837252 -> 2026-10-22T140832940329 | 1 changed | quiet |
| 2026-10-22 | `remote/com.socialseal/mcp` | 2026-10-22T105532315094 -> 2026-10-22T140830581469 | 1 changed | quiet |
| 2026-10-22 | `remote/com.ableandagent/sandbox` | 2026-10-22T105420848351 -> 2026-10-22T140828952908 | 1 changed, 1 added | quiet |
| 2026-10-22 | `remote/com.pagelemon/pagelemon` | 2026-10-21T141047177433 -> 2026-10-22T140828136588 | 44 changed, 1 added | quiet |
| 2026-10-22 | `remote/com.movingplace/mcp` | 2026-10-22T121459827792 -> 2026-10-22T140825996645 | 16 added | quiet |
| 2026-10-22 | `remote/com.hireahelper/mcp` | 2026-10-22T052623807496 -> 2026-10-22T140823439083 | 16 added | quiet |
| 2026-10-22 | `remote/club.goodleads/new-business-owner-contacts` | 2026-10-22T052624294375 -> 2026-10-22T140823219972 | 6 changed | quiet |
| 2026-10-22 | `remote/io.github.eorscope/eorscope-mcp` | 2026-10-21T121555697858 -> 2026-10-22T140822391004 | 14 changed (every tool) | quiet |
| 2026-10-22 | `remote/com.ksaworks/goldseam` | 2026-10-22T105343973483 -> 2026-10-22T140822255585 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.Argo-RPG-Platform/argo-mcp` | 2026-10-22T105240982449 -> 2026-10-22T140819516415 | 2 changed | quiet |
| 2026-10-22 | `remote/com.convertlyft/convertlyft` | 2026-10-22T105257202615 -> 2026-10-22T140820031448 | 1 changed | quiet |
| 2026-10-22 | `remote/io.llmexpert/transcription` | 2026-10-21T202443827833 -> 2026-10-22T140817107768 | 1 changed | quiet |
| 2026-10-22 | `remote/app.vercel.gouda-studios-agent-tools/gouda-studios-agent-tools` | 2026-10-22T105113838383 -> 2026-10-22T140814131621 | 1 changed, 1 added | quiet |
| 2026-10-22 | `remote/io.github.edtool79-collab/hirepulse-gateway` | 2026-10-22T052534050597 -> 2026-10-22T140813681163 | 8 changed | quiet |
| 2026-10-22 | `remote/xyz.filingdelta/filingdelta` | 2026-10-22T121034722764 -> 2026-10-22T140812720512 | 2 changed | quiet |
| 2026-10-22 | `remote/io.github.giuseppesocci-bot/kalicart-global` | 2026-10-22T105053240287 -> 2026-10-22T140813176813 | 1 changed | quiet |
| 2026-10-22 | `remote/com.heritagedeed/title-search` | 2026-10-22T052535466882 -> 2026-10-22T140813492011 | 2 changed | quiet |
| 2026-10-22 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-22T121009293954 -> 2026-10-22T140812284874 | 3 changed | quiet |
| 2026-10-22 | `remote/com.exchangerebel/exchangerebel` | 2026-10-22T052533606276 -> 2026-10-22T140811622436 | 2 added | quiet |
| 2026-10-22 | `remote/io.github.giuseppesocci-bot/kalicart-global.1` | 2026-10-22T104644860289 -> 2026-10-22T140808753486 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.smithdavedesign/botchelor` | 2026-10-22T120855237020 -> 2026-10-22T140806021719 | 10 changed | quiet |
| 2026-10-22 | `remote/dev.omikuji/calories` | 2026-10-22T104606758527 -> 2026-10-22T140805260776 | 1 changed | quiet |
| 2026-10-22 | `remote/com.engagemii/citation-watch` | 2026-10-22T104300036072 -> 2026-10-22T140804063321 | 2 changed | quiet |
| 2026-10-22 | `remote/properties.hercules/property-data` | 2026-10-21T202335044683 -> 2026-10-22T140804172080 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-10-21T202333409560 -> 2026-10-22T140804458940 | 2 changed | quiet |
| 2026-10-22 | `remote/com.assay-systems/register` | 2026-10-20T135259250916 -> 2026-10-22T140802639039 | 9 changed | quiet |
| 2026-10-22 | `remote/directory.nohumans/registry` | 2026-10-22T104458169939 -> 2026-10-22T140802045930 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.Nutshell2000/agent-data-tools` | 2026-10-22T104106436341 -> 2026-10-22T140758193158 | 1 added | quiet |
| 2026-10-22 | `remote/sg.homejourney/listings` | 2026-10-22T120445108330 -> 2026-10-22T140759549160 | 1 added | quiet |
| 2026-10-22 | `remote/com.agentdrives/directory.1` | 2026-10-22T120435414212 -> 2026-10-22T140756406114 | 6 changed | quiet |
| 2026-10-22 | `remote/io.github.0xinsider/mcp` | 2026-10-22T104240714861 -> 2026-10-22T140754235395 | 1 changed | quiet |
| 2026-10-22 | `remote/com.agentdrives/directory` | 2026-10-21T202321343017 -> 2026-10-22T140754449817 | 4 changed | quiet |
| 2026-10-22 | `remote/io.github.Nutshell2000/agent-data-tools-web` | 2026-10-22T104113900292 -> 2026-10-22T140752089580 | 1 added | quiet |
| 2026-10-22 | `remote/studio.gradients/mcp` | 2026-10-22T110011337909 -> 2026-10-22T122123121285 | 1 changed | quiet |
| 2026-10-22 | `remote/fi.akkilahdot/travel-search` | 2026-10-22T105951256422 -> 2026-10-22T122102518715 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 27663 substantive, 14315 that changed only numbers (a catalogue counter ticking, a date), 568 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 22156 | 8734 | 13422 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 654 | 654 | 0 | 0 |
| `caseyjhand.com` | 174 | 174 | 0 | 0 |
| `sistaminuten.se` | 135 | 4 | 0 | 131 |
| `afbudsrejser.dk` | 134 | 4 | 0 | 130 |
| `akkilahdot.fi` | 134 | 4 | 0 | 130 |
| `restplass.no` | 134 | 4 | 0 | 130 |
| `socialloop.ai` | 130 | 130 | 0 | 0 |
| `remoshift.com` | 105 | 8 | 97 | 0 |
| `fundinglandscape.com` | 103 | 68 | 35 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| 5127 other operators | 16249 | 15441 | 761 | 47 |
