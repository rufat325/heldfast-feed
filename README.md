# MCP server tool changes

Last change observed 2026-10-19T16:02:17+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

34937 changes to a tool definition: 1387 npm releases (1141 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 33550 readings of hosted servers that found their tools changed; 2178 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-19 | `remote/no.restplass/travel-search` | 2026-10-19T135856026355 -> 2026-10-19T160218950325 | 1 changed | quiet |
| 2026-10-19 | `remote/dev.workers.xbtbot.x402-reader/markdown-reader` | 2026-10-19T135524485149 -> 2026-10-19T160211577064 | 1 added | quiet |
| 2026-10-19 | `remote/se.sistaminuten/travel-search` | 2026-10-19T135513736786 -> 2026-10-19T160200261652 | 1 changed | quiet |
| 2026-10-19 | `remote/dk.afbudsrejser/travel-search` | 2026-10-19T135821898992 -> 2026-10-19T160157835004 | 1 changed | quiet |
| 2026-10-19 | `remote/io.github.robertoyanguas-ops/whale-momentum-mcp` | 2026-10-19T135811887608 -> 2026-10-19T160143684045 | 1 changed | review |
| 2026-10-19 | `remote/com.veritaset/mcp` | 2026-10-19T135756496309 -> 2026-10-19T160132680808 | 6 changed, 1 added (every tool) | quiet |
| 2026-10-19 | `remote/com.vanitynumbers/vanitynumbers` | 2026-10-19T135751401057 -> 2026-10-19T160133780111 | 1 changed | quiet |
| 2026-10-19 | `remote/io.github.voicehook-ai/voicehook` | 2026-10-19T135411795273 -> 2026-10-19T160126924069 | 1 changed | quiet |
| 2026-10-19 | `remote/io.github.tidytools/tidytools-free` | 2026-10-19T135730787510 -> 2026-10-19T160117000525 | 42 added | quiet |
| 2026-10-19 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-19T135644754708 -> 2026-10-19T160049667888 | 10 changed | quiet |
| 2026-10-19 | `remote/io.github.Timothymycompc/solana-pulse-gateway` | 2026-10-17T060308763573 -> 2026-10-19T160047204648 | 15 changed (every tool) | review |
| 2026-10-19 | `remote/dev.agentdiet/shopify-intel` | 2026-10-19T135628109364 -> 2026-10-19T160041076699 | 1 changed | review |
| 2026-10-19 | `remote/dev.agentdiet/shopify-spy` | 2026-10-19T135250138102 -> 2026-10-19T160034218622 | 1 changed | review |
| 2026-10-19 | `remote/io.github.robertoyanguas-ops/sec-intel-mcp` | 2026-10-19T135237250111 -> 2026-10-19T160030491589 | 1 changed | review |
| 2026-10-19 | `remote/com.straelo/relay` | 2026-10-18T113142043672 -> 2026-10-19T160016103668 | 9 changed | quiet |
| 2026-10-19 | `remote/dev.agentdiet/polymarket-odds` | 2026-10-19T135143185817 -> 2026-10-19T155956978341 | 1 changed | review |
| 2026-10-19 | `remote/com.kineticist/mcp-server` | 2026-10-19T135234280947 -> 2026-10-19T155957257173 | 3 changed | quiet |
| 2026-10-19 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-10-19T135230150729 -> 2026-10-19T155956771105 | 1 changed | quiet |
| 2026-10-19 | `remote/com.basischarts/basis` | 2026-10-17T185349262103 -> 2026-10-19T155952291661 | 13 changed, 1 added | quiet |
| 2026-10-19 | `remote/io.github.nukafever-lab/nukafever` | 2026-10-19T135433384641 -> 2026-10-19T155932815456 | 1 changed | quiet |
| 2026-10-19 | `remote/com.movesurge/movesurge` | 2026-10-19T135049262321 -> 2026-10-19T155929446442 | 9 changed, 1 added (every tool) | quiet |
| 2026-10-19 | `remote/design.sleek/sleek` | 2026-10-19T135102547623 -> 2026-10-19T155927308565 | 1 added | quiet |
| 2026-10-19 | `remote/com.momenticmarketing/momentic` | 2026-10-17T055319007741 -> 2026-10-19T155927360470 | 1 changed | quiet |
| 2026-10-19 | `remote/io.github.robertoyanguas-ops/shopify-spy-mcp` | 2026-10-19T135045077203 -> 2026-10-19T155924702708 | 1 changed | review |
| 2026-10-19 | `remote/dev.agentdiet/sec-intel` | 2026-10-19T135030080565 -> 2026-10-19T155923865523 | 1 changed | review |
| 2026-10-19 | `remote/com.voice-school/lesson-booking` | 2026-10-19T135013565518 -> 2026-10-19T155922824473 | 2 changed, 3 added | quiet |
| 2026-10-19 | `remote/io.satelo/satelo` | 2026-10-17T060124088364 -> 2026-10-19T155922652799 | 1 changed | quiet |
| 2026-10-19 | `remote/io.github.GrayWolf8-creator/gw8-signal-api` | 2026-10-19T135405748603 -> 2026-10-19T155920952983 | 3 changed, 1 added | review |
| 2026-10-19 | `remote/com.misslicita/misslicita` | 2026-10-19T135408611612 -> 2026-10-19T155922343843 | 1 changed | quiet |
| 2026-10-19 | `remote/io.roxskin/hyrox` | 2026-10-19T135018129331 -> 2026-10-19T155918826983 | 1 changed | quiet |
| 2026-10-19 | `remote/com.trulyrandomverse/bible-study` | 2026-10-19T134957231051 -> 2026-10-19T155916690830 | 2 changed | quiet |
| 2026-10-19 | `remote/cloud.redu/mcp` | 2026-10-18T113030657818 -> 2026-10-19T155907790305 | 3 changed | quiet |
| 2026-10-19 | `remote/dev.svelte/mcp` | 2026-10-17T060011741827 -> 2026-10-19T155904039741 | 1 changed | quiet |
| 2026-10-19 | `remote/com.sourcey/sourcey` | 2026-10-17T060008796889 -> 2026-10-19T155903262233 | 8 changed (every tool) | quiet |
| 2026-10-19 | `remote/io.github.Payotte-com/payotte-mcp` | 2026-10-17T060028677073 -> 2026-10-19T155900989147 | 1 changed, 12 added | quiet |
| 2026-10-19 | `remote/ai.sendraven/mcp` | 2026-10-19T135320591397 -> 2026-10-19T155902307804 | 1 changed, 1 added | quiet |
| 2026-10-19 | `remote/dev.agentdiet/onchain-risk` | 2026-10-19T134916472213 -> 2026-10-19T155853768614 | 1 changed | review |
| 2026-10-19 | `remote/io.github.robertoyanguas-ops/onchain-risk-mcp` | 2026-10-19T134916067759 -> 2026-10-19T155853107912 | 1 changed | review |
| 2026-10-19 | `remote/org.r3js/r3` | 2026-10-19T135312014714 -> 2026-10-19T155903726006 | 2 changed | quiet |
| 2026-10-19 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-10-18T185925843603 -> 2026-10-19T155850941884 | 1 changed | quiet |
| 2026-10-19 | `remote/ai.letsship/ship` | 2026-10-19T134841511331 -> 2026-10-19T155852833725 | 1 changed | quiet |
| 2026-10-19 | `remote/io.github.ASEM-BATAWY/vicatoo` | 2026-10-19T134804467922 -> 2026-10-19T155836330975 | 1 changed | quiet |
| 2026-10-19 | `remote/com.voice-school/singing-vocal-lesson-booking` | 2026-10-19T134805795873 -> 2026-10-19T155836125400 | 2 changed, 3 added | quiet |
| 2026-10-19 | `remote/com.layerhop/mcp` | 2026-10-19T135236919598 -> 2026-10-19T155835240255 | 6 added | review |
| 2026-10-19 | `remote/io.github.France-Care/france-care` | 2026-10-19T134806962075 -> 2026-10-19T155831042628 | 1 changed | quiet |
| 2026-10-19 | `remote/tech.kaiku/kaiku.1` | 2026-10-19T134639570890 -> 2026-10-19T155818433985 | 4 changed, 2 added | quiet |
| 2026-10-19 | `remote/io.github.costkits/costkits-mcp` | 2026-10-19T135152754738 -> 2026-10-19T155819260168 | 1 added | quiet |
| 2026-10-19 | `remote/com.kenwea.www/notary` | 2026-10-17T055710748628 -> 2026-10-19T155818529901 | 1 changed | quiet |
| 2026-10-19 | `remote/org.georgiacivicdata/georgia-civic-data` | 2026-10-17T055650196456 -> 2026-10-19T155814687964 | 1 changed | quiet |
| 2026-10-19 | `remote/com.convertlyft/convertlyft` | 2026-10-19T134741236339 -> 2026-10-19T155814778394 | 1 changed | quiet |
| 2026-10-19 | `remote/io.github.Desearch-ai/mcp-desearch` | 2026-10-19T134602925582 -> 2026-10-19T155810751815 | 2 changed | quiet |
| 2026-10-19 | `remote/com.avokata/avokata` | 2026-10-19T135137559305 -> 2026-10-19T155811056296 | 1 changed | quiet |
| 2026-10-19 | `remote/com.versyka/versyka` | 2026-10-19T135614623625 -> 2026-10-19T155757073669 | 2 changed | quiet |
| 2026-10-19 | `remote/io.github.imokokok/insight-oracle` | 2026-10-17T055949481960 -> 2026-10-19T155755438387 | 7 changed | quiet |
| 2026-10-19 | `remote/dev.agentdiet/mcp-compiler` | 2026-10-19T134647322999 -> 2026-10-19T155751840902 | 1 changed | review |
| 2026-10-19 | `remote/com.mart402/extract` | 2026-10-19T135102053571 -> 2026-10-19T155752893917 | 35 changed (every tool) | quiet |
| 2026-10-19 | `remote/studio.gradients/mcp` | 2026-10-19T135550217919 -> 2026-10-19T155748657488 | 1 changed | quiet |
| 2026-10-19 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-10-18T190112963442 -> 2026-10-19T155745692868 | 2 changed | quiet |
| 2026-10-19 | `remote/io.github.robertoyanguas-ops/llms-generator-mcp` | 2026-10-19T135047838100 -> 2026-10-19T155743941168 | 1 changed | review |
| 2026-10-19 | `remote/fi.akkilahdot/travel-search` | 2026-10-19T135529418414 -> 2026-10-19T155744551447 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 23276 substantive, 11167 that changed only numbers (a catalogue counter ticking, a date), 494 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 17656 | 7224 | 10432 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 166 | 166 | 0 | 0 |
| `sistaminuten.se` | 119 | 4 | 0 | 115 |
| `afbudsrejser.dk` | 118 | 4 | 0 | 114 |
| `akkilahdot.fi` | 118 | 4 | 0 | 114 |
| `restplass.no` | 118 | 4 | 0 | 114 |
| `socialloop.ai` | 115 | 115 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `remoshift.com` | 89 | 6 | 83 | 0 |
| `fundinglandscape.com` | 88 | 55 | 33 | 0 |
| 4313 other operators | 13259 | 12603 | 619 | 37 |
