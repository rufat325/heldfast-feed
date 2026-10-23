# MCP server tool changes

Last change observed 2026-10-23T20:08:54+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

45140 changes to a tool definition: 1988 npm releases (1742 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 43152 readings of hosted servers that found their tools changed; 2425 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-23 | `remote/com.zinvyl/marketplace` | 2026-10-23T052646902373 -> 2026-10-23T200857266291 | 12 changed | quiet |
| 2026-10-23 | `remote/studio.gradients/mcp` | 2026-10-23T135205997816 -> 2026-10-23T200853604545 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.worklore/worklore` | 2026-10-21T122151623825 -> 2026-10-23T200851934674 | 1 added | quiet |
| 2026-10-23 | `remote/fi.akkilahdot/travel-search` | 2026-10-23T135205208871 -> 2026-10-23T200852300790 | 1 changed | quiet |
| 2026-10-23 | `remote/tech.viewprinter/viewprinter` | 2026-10-21T122133758669 -> 2026-10-23T200850807967 | 7 added | quiet |
| 2026-10-23 | `remote/ru.vedarai/mcp` | 2026-10-23T135205864495 -> 2026-10-23T200851247773 | 1 changed | quiet |
| 2026-10-23 | `remote/gg.unicum/wot-stats` | 2026-10-22T140852479967 -> 2026-10-23T200850648118 | 2 changed, 1 removed | quiet |
| 2026-10-23 | `remote/com.transitmcp/transit-mcp` | 2026-10-22T233936853367 -> 2026-10-23T200850348463 | 2 changed | quiet |
| 2026-10-23 | `remote/ai.usedby/usedby` | 2026-10-22T233947796808 -> 2026-10-23T200844721883 | 4 changed | quiet |
| 2026-10-23 | `remote/se.sistaminuten/travel-search` | 2026-10-23T135211510867 -> 2026-10-23T200843149372 | 1 changed | quiet |
| 2026-10-23 | `remote/io.taifoon/coordination-layer.1` | 2026-10-22T233944866106 -> 2026-10-23T200844406812 | 1 changed | review |
| 2026-10-23 | `remote/dev.tanod/security` | 2026-10-23T120532659342 -> 2026-10-23T200848046574 | 1 changed | quiet |
| 2026-10-23 | `remote/ai.snowsure/snow` | 2026-10-23T120940608152 -> 2026-10-23T200842811666 | 2 changed | quiet |
| 2026-10-23 | `remote/no.apier/mcp` | 2026-10-23T120915274396 -> 2026-10-23T200840965952 | 1 changed | quiet |
| 2026-10-23 | `remote/ai.whatsupin/events` | 2026-10-23T120857473229 -> 2026-10-23T200838519382 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-23T135159052824 -> 2026-10-23T200838971190 | 1 changed | quiet |
| 2026-10-23 | `remote/app.openkrill/videograb` | 2026-10-22T105904511264 -> 2026-10-23T200837137060 | 3 changed, 1 removed | quiet |
| 2026-10-23 | `remote/ai.shorti/shorti` | 2026-10-21T202455982007 -> 2026-10-23T200837223920 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.SKalinin909/tradingcalc` | 2026-10-23T135203150611 -> 2026-10-23T200833049613 | 6 changed | quiet |
| 2026-10-23 | `remote/dev.tanod/tanod` | 2026-10-23T052623148573 -> 2026-10-23T200831991450 | 1 changed | quiet |
| 2026-10-23 | `remote/dev.sportsapis/sportsapis` | 2026-10-23T120723500940 -> 2026-10-23T200827981648 | 1 changed | quiet |
| 2026-10-23 | `remote/com.remoshift/jobs` | 2026-10-23T135155640969 -> 2026-10-23T200829605168 | 1 changed | quiet |
| 2026-10-23 | `remote/com.asksakina/islamic-knowledge` | 2026-10-23T120639331395 -> 2026-10-23T200824732837 | 1 changed | quiet |
| 2026-10-23 | `remote/app.openkrill/remote-jobs` | 2026-10-22T105647546020 -> 2026-10-23T200825101858 | 1 changed, 1 removed | quiet |
| 2026-10-23 | `remote/com.youspot/youspot` | 2026-10-22T233935621172 -> 2026-10-23T200823571161 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.rezearcher/tech-risk` | 2026-10-21T202508683328 -> 2026-10-23T200822463269 | 2 changed | review |
| 2026-10-23 | `remote/com.programscape/programscape` | 2026-10-23T120603979111 -> 2026-10-23T200822298685 | 8 changed | quiet |
| 2026-10-23 | `remote/com.predictionmarketspicks/quant` | 2026-10-22T140839960333 -> 2026-10-23T200823665333 | 1 changed | quiet |
| 2026-10-23 | `remote/app.openkrill/post-stats` | 2026-10-22T105620198563 -> 2026-10-23T200823568727 | 3 changed | quiet |
| 2026-10-23 | `remote/io.github.withgrokbot/verified-catalog.1` | 2026-10-22T202105820707 -> 2026-10-23T200819026513 | 1 changed | quiet |
| 2026-10-23 | `remote/sh.openpath/openpath` | 2026-10-23T120523781725 -> 2026-10-23T200818102599 | 2 changed (every tool) | quiet |
| 2026-10-23 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-10-21T202457785755 -> 2026-10-23T200818624791 | 2 changed, 1 removed | quiet |
| 2026-10-23 | `remote/io.github.exquad/thecablecode` | 2026-10-23T052616027318 -> 2026-10-23T200817592963 | 3 changed, 1 added | quiet |
| 2026-10-23 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-23T120504877921 -> 2026-10-23T200814906387 | 2 added | quiet |
| 2026-10-23 | `remote/io.github.jennipro-engineering/ghost-market-web` | 2026-10-23T052613861352 -> 2026-10-23T200814350669 | 1 changed | quiet |
| 2026-10-23 | `remote/com.multicinesortega/cartelera` | 2026-10-23T052632464162 -> 2026-10-23T200816747482 | 1 changed | quiet |
| 2026-10-23 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-10-23T052629241024 -> 2026-10-23T200812777582 | 43 added | quiet |
| 2026-10-23 | `remote/no.restplass/travel-search` | 2026-10-23T135203114196 -> 2026-10-23T200809566669 | 1 changed | quiet |
| 2026-10-23 | `remote/dk.afbudsrejser/travel-search` | 2026-10-23T135202450285 -> 2026-10-23T200808292864 | 1 changed | quiet |
| 2026-10-23 | `remote/com.vendooly/vendooly` | 2026-10-22T105552915472 -> 2026-10-23T200809506578 | 1 changed | quiet |
| 2026-10-23 | `remote/ai.prepublish/script-audit` | 2026-10-21T121731644506 -> 2026-10-23T200809493830 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-10-23T052603975427 -> 2026-10-23T200807044653 | 1 changed | review |
| 2026-10-23 | `remote/io.github.meltingpixelsai/zero-core-verify` | 2026-10-23T120602520324 -> 2026-10-23T200806944067 | 3 changed | quiet |
| 2026-10-23 | `remote/ai.switchapp/switch` | 2026-10-23T120213186161 -> 2026-10-23T200807203671 | 2 added | quiet |
| 2026-10-23 | `remote/io.github.Kindora-PBC/foundation-discovery` | 2026-10-21T121651896782 -> 2026-10-23T200805826172 | 1 changed | quiet |
| 2026-10-23 | `remote/com.jojapi/sms-verify` | 2026-10-23T120234737746 -> 2026-10-23T200806712851 | 1 changed | quiet |
| 2026-10-23 | `remote/net.clickwise/mcp` | 2026-10-21T202439860930 -> 2026-10-23T200804982211 | 1 changed, 8 added | quiet |
| 2026-10-23 | `remote/com.pakistancaselaw/caselaw` | 2026-10-22T105616664688 -> 2026-10-23T200804864300 | 1 changed | quiet |
| 2026-10-23 | `remote/com.virtualhangar.owners/beacon` | 2026-10-22T105613617187 -> 2026-10-23T200803775282 | 1 changed | quiet |
| 2026-10-23 | `remote/com.lightbringer/connector` | 2026-10-22T052625304757 -> 2026-10-23T200803692326 | 4 changed, 1 added | quiet |
| 2026-10-23 | `remote/io.github.hail-hq/hail-mcp` | 2026-10-23T120054378319 -> 2026-10-23T200802861615 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.privatebydefault/default-privacy` | 2026-10-22T202037300037 -> 2026-10-23T200800839290 | 19 changed (every tool) | quiet |
| 2026-10-23 | `remote/com.mrrledger/mrrledger` | 2026-10-23T120253540510 -> 2026-10-23T200802940305 | 14 changed, 3 removed (every tool) | quiet |
| 2026-10-23 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-23T135155671717 -> 2026-10-23T200801071682 | 10 changed | quiet |
| 2026-10-23 | `remote/com.convertlyft/convertlyft` | 2026-10-23T135138454654 -> 2026-10-23T200801570175 | 12 changed | quiet |
| 2026-10-23 | `remote/ai.spelunking/hub` | 2026-10-23T120446403398 -> 2026-10-23T200803191007 | 3 changed, 5 added, 4 removed (every tool) | quiet |
| 2026-10-23 | `remote/ai.dreamlit/mcp` | 2026-10-22T202037899220 -> 2026-10-23T200800655979 | 13 changed (every tool) | quiet |
| 2026-10-23 | `remote/com.bota-chat/bota` | 2026-10-22T202036251285 -> 2026-10-23T200759964189 | 1 changed | quiet |
| 2026-10-23 | `remote/app.openkrill/send-out` | 2026-10-22T110017077721 -> 2026-10-23T200759740378 | 7 changed, 1 removed | quiet |
| 2026-10-23 | `remote/io.github.ZacharyVorsteg/provenplaza-agent-mcp` | 2026-10-21T121851423699 -> 2026-10-23T200757279608 | 7 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 28679 substantive, 15868 that changed only numbers (a catalogue counter ticking, a date), 593 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 23651 | 8749 | 14902 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 656 | 656 | 0 | 0 |
| `caseyjhand.com` | 187 | 187 | 0 | 0 |
| `sistaminuten.se` | 141 | 4 | 0 | 137 |
| `afbudsrejser.dk` | 140 | 4 | 0 | 136 |
| `akkilahdot.fi` | 140 | 4 | 0 | 136 |
| `restplass.no` | 140 | 4 | 0 | 136 |
| `socialloop.ai` | 136 | 136 | 0 | 0 |
| `remoshift.com` | 111 | 8 | 103 | 0 |
| `fundinglandscape.com` | 108 | 71 | 37 | 0 |
| `openkrill.app` | 97 | 97 | 0 | 0 |
| 5337 other operators | 17292 | 16418 | 826 | 48 |
