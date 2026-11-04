# MCP server tool changes

Last change observed 2026-11-04T20:08:19+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

77193 changes to a tool definition: 3200 npm releases (2954 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 73993 readings of hosted servers that found their tools changed; 3355 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-04 | `remote/xyz.x402helper/mcp` | 2026-11-03T145023089879 -> 2026-11-04T200821305080 | 1 changed | review |
| 2026-11-04 | `remote/io.github.Fizzl13/x402-doctor` | 2026-11-03T195519853308 -> 2026-11-04T200819633647 | 1 added | quiet |
| 2026-11-04 | `remote/com.vedutum/vedutum` | 2026-11-03T145016185770 -> 2026-11-04T200820456580 | 1 changed | quiet |
| 2026-11-04 | `remote/studio.gradients/mcp` | 2026-11-04T150600378470 -> 2026-11-04T200818111804 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.SoapyRED/freightutils` | 2026-11-04T150556429669 -> 2026-11-04T200818276889 | 25 changed (every tool) | quiet |
| 2026-11-04 | `remote/de.containerdienst-regional/anfrage` | 2026-11-04T150544056717 -> 2026-11-04T200817786557 | 2 changed | quiet |
| 2026-11-04 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-04T123815100060 -> 2026-11-04T200815521798 | 3 changed | quiet |
| 2026-11-04 | `remote/fi.akkilahdot/travel-search` | 2026-11-04T150529366834 -> 2026-11-04T200815013020 | 1 changed | quiet |
| 2026-11-04 | `remote/com.ablakunio/nyilaszaro-mcp` | 2026-11-04T150527753894 -> 2026-11-04T200815275032 | 1 changed | quiet |
| 2026-11-04 | `remote/com.lazyweb/discovery` | 2026-11-04T150742774483 -> 2026-11-04T200814340556 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.seasonsagents-art/webaz` | 2026-11-03T122633378009 -> 2026-11-04T200812224709 | 3 changed | quiet |
| 2026-11-04 | `remote/io.github.liad142/yedapo` | 2026-11-04T005954659252 -> 2026-11-04T200812971713 | 2 changed (every tool) | quiet |
| 2026-11-04 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-04T123812684663 -> 2026-11-04T200815544998 | 2 changed | quiet |
| 2026-11-04 | `remote/no.restplass/travel-search` | 2026-11-04T150934371466 -> 2026-11-04T200810318346 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-04T123811798377 -> 2026-11-04T200809148659 | 2 changed | quiet |
| 2026-11-04 | `remote/io.github.brawlaphant/vealth` | 2026-11-04T005857043678 -> 2026-11-04T200805705293 | 6 added | quiet |
| 2026-11-04 | `remote/dev.upfork/upfork` | 2026-11-04T005856735113 -> 2026-11-04T200805359049 | 3 changed | quiet |
| 2026-11-04 | `remote/si.thinkhard/prompt-tools` | 2026-11-04T150404494126 -> 2026-11-04T200800865019 | 1 changed, 6 added | quiet |
| 2026-11-04 | `remote/net.tichat.tradehub/tradehub.1` | 2026-11-04T005854806164 -> 2026-11-04T200801490213 | 12 changed, 20 added, 20 removed | quiet |
| 2026-11-04 | `remote/dk.afbudsrejser/travel-search` | 2026-11-04T150736824718 -> 2026-11-04T200800582444 | 1 changed | quiet |
| 2026-11-04 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-04T123806205247 -> 2026-11-04T200800206147 | 2 changed | quiet |
| 2026-11-04 | `remote/io.taifoon/coordination-layer.1` | 2026-11-04T123836537441 -> 2026-11-04T200758444812 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.pooriaarab/winecellarbuilders` | 2026-11-02T163524278794 -> 2026-11-04T200800168249 | 2 added | quiet |
| 2026-11-04 | `remote/se.sistaminuten/travel-search` | 2026-11-04T150756848697 -> 2026-11-04T200757545050 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.pooriaarab/voiceagents` | 2026-11-02T163510392799 -> 2026-11-04T200757283071 | 2 added | quiet |
| 2026-11-04 | `remote/ai.startuphub/startuphub` | 2026-11-04T123836607897 -> 2026-11-04T200758660083 | 2 changed | review |
| 2026-11-04 | `remote/xyz.t0ll/toll` | 2026-11-04T150325396038 -> 2026-11-04T200755832937 | 5 changed | quiet |
| 2026-11-04 | `remote/io.github.exquad/thecablecode` | 2026-11-04T123802968225 -> 2026-11-04T200756543927 | 1 added | review |
| 2026-11-04 | `remote/com.vectorstreamsystems/mbestudio` | 2026-11-04T150307013411 -> 2026-11-04T200755116387 | 11 changed | quiet |
| 2026-11-04 | `remote/com.googleapis.stitch/mcp` | 2026-11-03T144802941812 -> 2026-11-04T200754611955 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.JcJamet/ia-qa-security` | 2026-11-03T122704181232 -> 2026-11-04T200753690975 | 2 changed | quiet |
| 2026-11-04 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-11-03T195704121922 -> 2026-11-04T200753744285 | 2 changed | quiet |
| 2026-11-04 | `remote/com.spgdentalimplants/spg-dental-implants` | 2026-11-04T150248591502 -> 2026-11-04T200752890259 | 2 changed | quiet |
| 2026-11-04 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-04T150242507263 -> 2026-11-04T200752427939 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.pooriaarab/soberbars` | 2026-11-02T163404962124 -> 2026-11-04T200751497137 | 2 added | quiet |
| 2026-11-04 | `remote/com.diveratlas/diver-atlas` | 2026-11-04T123830777842 -> 2026-11-04T200751567595 | 3 added | quiet |
| 2026-11-04 | `remote/io.sibidz/sibidz` | 2026-11-02T163352388951 -> 2026-11-04T200751585098 | 1 changed | quiet |
| 2026-11-04 | `remote/com.signupbouncer/checker` | 2026-11-03T144736048322 -> 2026-11-04T200750692215 | 2 changed | quiet |
| 2026-11-04 | `remote/com.coveragecat/insurance` | 2026-11-04T005927500709 -> 2026-11-04T200749505695 | 15 changed | quiet |
| 2026-11-04 | `remote/com.structomat/steel` | 2026-11-04T005847775468 -> 2026-11-04T200749621382 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-11-04T123755346776 -> 2026-11-04T200747319478 | 1 changed | quiet |
| 2026-11-04 | `remote/net.rpscripts/fivem` | 2026-11-02T163259607696 -> 2026-11-04T200745639166 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.pooriaarab/robotaxis` | 2026-11-02T163256676263 -> 2026-11-04T200745114965 | 2 added | quiet |
| 2026-11-04 | `remote/fr.synergieloc/immobilier` | 2026-11-04T150450861792 -> 2026-11-04T200747093396 | 1 added | quiet |
| 2026-11-04 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-04T150428385383 -> 2026-11-04T200746540697 | 2 changed | review |
| 2026-11-04 | `remote/io.github.pooriaarab/sleepstudies` | 2026-11-02T163600801794 -> 2026-11-04T200748107431 | 2 added | quiet |
| 2026-11-04 | `remote/com.remoshift/jobs` | 2026-11-04T150139754072 -> 2026-11-04T200744136782 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.BigRedCloud/red-mcp-server` | 2026-11-04T150136689370 -> 2026-11-04T200744993370 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.spree/ecommerce-docs` | 2026-11-02T163323309270 -> 2026-11-04T200743365032 | 1 changed | quiet |
| 2026-11-04 | `remote/com.googleapis.sqladmin/mcp` | 2026-11-02T065440594957 -> 2026-11-04T200742214145 | 3 changed | quiet |
| 2026-11-04 | `remote/io.github.SKalinin909/tradingcalc` | 2026-11-04T005917032262 -> 2026-11-04T200739914370 | 1 changed, 1 added | quiet |
| 2026-11-04 | `remote/cloud.nttzen.secdb/zen-secdb` | 2026-11-04T150304229563 -> 2026-11-04T200742575412 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.pooriaarab/psilocybincenters` | 2026-11-02T163225886777 -> 2026-11-04T200743671789 | 2 added | quiet |
| 2026-11-04 | `remote/io.github.pooriaarab/privatedock` | 2026-11-02T163224640317 -> 2026-11-04T200748514910 | 2 added | quiet |
| 2026-11-04 | `remote/com.pourwire/pourwire` | 2026-11-04T150103887460 -> 2026-11-04T200738224458 | 2 changed (every tool) | quiet |
| 2026-11-04 | `remote/now.salesjobs/mcp` | 2026-11-03T195524430601 -> 2026-11-04T200737716904 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.pooriaarab/tmsclinics` | 2026-11-02T163233032279 -> 2026-11-04T200741055936 | 2 added | quiet |
| 2026-11-04 | `remote/gg.pixly/mcp` | 2026-11-02T185337015994 -> 2026-11-04T200739947437 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.pooriaarab/privatewellnessrooms` | 2026-11-02T163136818245 -> 2026-11-04T200736022570 | 2 added | quiet |
| 2026-11-04 | `remote/io.github.cryptoconspiracy/vurto-swap` | 2026-11-02T163155416213 -> 2026-11-04T200731063286 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 47294 substantive, 29071 that changed only numbers (a catalogue counter ticking, a date), 828 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 43261 | 15875 | 27386 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1366 | 1366 | 0 | 0 |
| `caseyjhand.com` | 352 | 352 | 0 | 0 |
| `sistaminuten.se` | 195 | 6 | 0 | 189 |
| `afbudsrejser.dk` | 194 | 6 | 0 | 188 |
| `akkilahdot.fi` | 194 | 6 | 0 | 188 |
| `restplass.no` | 194 | 6 | 0 | 188 |
| `socialloop.ai` | 187 | 187 | 0 | 0 |
| `remoshift.com` | 164 | 13 | 151 | 0 |
| `openkrill.app` | 152 | 152 | 0 | 0 |
| `fundinglandscape.com` | 149 | 90 | 59 | 0 |
| 7515 other operators | 28444 | 26894 | 1475 | 75 |
