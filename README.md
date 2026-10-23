# MCP server tool changes

Last change observed 2026-10-23T05:26:45+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

42893 changes to a tool definition: 1838 npm releases (1592 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 41055 readings of hosted servers that found their tools changed; 2394 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-23 | `remote/com.zinvyl/marketplace` | 2026-10-21T052307547540 -> 2026-10-23T052646902373 | 12 changed | quiet |
| 2026-10-23 | `remote/studio.gradients/mcp` | 2026-10-22T233939994929 -> 2026-10-23T052644638425 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.suanrongbaicai/vibecodepicks` | 2026-10-21T122130548291 -> 2026-10-23T052642914696 | 1 changed | quiet |
| 2026-10-23 | `remote/fi.akkilahdot/travel-search` | 2026-10-22T233938726543 -> 2026-10-23T052644836774 | 1 changed | quiet |
| 2026-10-23 | `remote/ru.vedarai/mcp` | 2026-10-22T105925012438 -> 2026-10-23T052644033552 | 1 added | quiet |
| 2026-10-23 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-22T122003810682 -> 2026-10-23T052641301915 | 1 changed | quiet |
| 2026-10-23 | `remote/com.swarmmemo/bulletin.1` | 2026-10-22T052641590823 -> 2026-10-23T052639903666 | 7 changed, 3 removed | quiet |
| 2026-10-23 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-22T233932018753 -> 2026-10-23T052637565050 | 2 changed | quiet |
| 2026-10-23 | `remote/com.remoshift/jobs` | 2026-10-22T233927214983 -> 2026-10-23T052634244466 | 1 changed | quiet |
| 2026-10-23 | `remote/com.multicinesortega/cartelera` | 2026-10-22T202049230368 -> 2026-10-23T052632464162 | 1 changed | quiet |
| 2026-10-23 | `remote/no.restplass/travel-search` | 2026-10-22T233939757568 -> 2026-10-23T052629572740 | 1 changed | quiet |
| 2026-10-23 | `remote/dk.afbudsrejser/travel-search` | 2026-10-22T233937192863 -> 2026-10-23T052628908106 | 1 changed | quiet |
| 2026-10-23 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-10-22T105611225685 -> 2026-10-23T052629241024 | 2 changed | quiet |
| 2026-10-23 | `remote/se.sistaminuten/travel-search` | 2026-10-22T233944844089 -> 2026-10-23T052628036840 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.pdarche/model-wellness` | 2026-10-21T052228310093 -> 2026-10-23T052628670449 | 15 changed (every tool) | quiet |
| 2026-10-23 | `remote/com.googleapis.memorystore/mcp` | 2026-10-22T233915450647 -> 2026-10-23T052627379896 | 4 changed | quiet |
| 2026-10-23 | `remote/com.ferntool/ip` | 2026-10-22T052602436445 -> 2026-10-23T052626733417 | 2 added | quiet |
| 2026-10-23 | `remote/ai.switchapp/switch` | 2026-10-22T202044530205 -> 2026-10-23T052626947690 | 3 changed | quiet |
| 2026-10-23 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-10-22T233929949328 -> 2026-10-23T052625290673 | 2 added | quiet |
| 2026-10-23 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-22T202154443014 -> 2026-10-23T052623670467 | 10 changed | quiet |
| 2026-10-23 | `remote/site.chatgpt.orellise.relay-agent-services/relay` | 2026-10-22T202151838848 -> 2026-10-23T052623361520 | 1 changed, 1 added | quiet |
| 2026-10-23 | `remote/io.github.wygogogo19/robotbase-mcp` | 2026-10-22T233925797265 -> 2026-10-23T052624299048 | 8 changed, 4 added | quiet |
| 2026-10-23 | `remote/com.thefomite/fomite` | 2026-10-22T052558287021 -> 2026-10-23T052621676919 | 1 changed | quiet |
| 2026-10-23 | `remote/dev.tanod/tanod` | 2026-10-22T202053986457 -> 2026-10-23T052623148573 | 1 added | quiet |
| 2026-10-23 | `remote/io.github.zambodotdev/zambo` | 2026-10-22T233935270363 -> 2026-10-23T052619517765 | 35 changed (every tool) | quiet |
| 2026-10-23 | `remote/dev.zambo/zambo` | 2026-10-22T233935433298 -> 2026-10-23T052619550114 | 35 changed (every tool) | quiet |
| 2026-10-23 | `remote/ch.kulalabs.pazair/pazair` | 2026-10-22T105902624158 -> 2026-10-23T052621696120 | 1 added | quiet |
| 2026-10-23 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-10-22T140858484820 -> 2026-10-23T052619113642 | 2 changed | quiet |
| 2026-10-23 | `remote/io.ainsof/mcp` | 2026-10-21T202415258291 -> 2026-10-23T052618153536 | 4 changed | quiet |
| 2026-10-23 | `remote/ai.tunnelmind/data` | 2026-10-21T121503287199 -> 2026-10-23T052616036877 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.exquad/thecablecode` | 2026-10-22T140852867639 -> 2026-10-23T052616027318 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.jennipro-engineering/ghost-market-web` | 2026-10-22T233925745098 -> 2026-10-23T052613861352 | 4 changed | quiet |
| 2026-10-23 | `remote/com.partstable/partstable` | 2026-10-22T105709247603 -> 2026-10-23T052614401045 | 1 changed | quiet |
| 2026-10-23 | `remote/net.hotelrefund/price-tracker` | 2026-10-22T052611993872 -> 2026-10-23T052612758613 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.yzlee/opcmenu` | 2026-10-21T234455530446 -> 2026-10-23T052618716730 | 2 changed | quiet |
| 2026-10-23 | `remote/io.github.lgs1520/agent-procurement-manager` | 2026-10-22T233858357289 -> 2026-10-23T052613830232 | 2 added | quiet |
| 2026-10-23 | `remote/io.github.Wonderfulian/kbv-server` | 2026-10-22T105235444942 -> 2026-10-23T052614029825 | 1 added | quiet |
| 2026-10-23 | `remote/com.sfxmint/sounds` | 2026-10-22T105726050574 -> 2026-10-23T052613505207 | 1 changed | review |
| 2026-10-23 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-22T052600221731 -> 2026-10-23T052613193039 | 1 changed | quiet |
| 2026-10-23 | `remote/com.gameshopenter/shop` | 2026-10-21T052204145193 -> 2026-10-23T052613591184 | 2 changed | quiet |
| 2026-10-23 | `remote/com.cielstay/cielstay` | 2026-10-22T202135672224 -> 2026-10-23T052611012690 | 2 changed | quiet |
| 2026-10-23 | `remote/com.oneuptime/mcp` | 2026-10-22T105552870275 -> 2026-10-23T052609637509 | 33 changed, 6 added | quiet |
| 2026-10-23 | `remote/io.github.Perufitlife/postwire-mcp` | 2026-10-22T202054973671 -> 2026-10-23T052608931433 | 1 changed | quiet |
| 2026-10-23 | `remote/com.mosaisley/cantina` | 2026-10-22T052552576912 -> 2026-10-23T052609347952 | 1 added | quiet |
| 2026-10-23 | `remote/app.vercel.fork-for-agents/fork` | 2026-10-22T104828045708 -> 2026-10-23T052612252051 | 3 changed, 2 added | quiet |
| 2026-10-23 | `remote/com.plainrouter/mcp` | 2026-10-22T233921716628 -> 2026-10-23T052609279678 | 4 changed, 1 added, 1 removed | quiet |
| 2026-10-23 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt` | 2026-10-22T121050458096 -> 2026-10-23T052610876725 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.provenpin/provenpin` | 2026-10-22T202031566951 -> 2026-10-23T052605336482 | 1 changed | quiet |
| 2026-10-23 | `remote/dev.reqistry/mcp` | 2026-10-21T121738997404 -> 2026-10-23T052606304437 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-10-22T233916573142 -> 2026-10-23T052603975427 | 1 changed | review |
| 2026-10-23 | `remote/com.negativeresistance/cure-protocol` | 2026-10-22T233915465396 -> 2026-10-23T052604527359 | 96 changed (every tool) | quiet |
| 2026-10-23 | `remote/co.civai.nova/support-agent-admin` | 2026-10-22T202053059660 -> 2026-10-23T052608664007 | 2 removed | quiet |
| 2026-10-23 | `remote/build.naru/contract-compass` | 2026-10-22T202109710200 -> 2026-10-23T052605047052 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.choaticpixels/wicked-mcp` | 2026-10-22T233911715297 -> 2026-10-23T052601751369 | 1 changed, 12 added | quiet |
| 2026-10-23 | `remote/io.github.Joonsense/birdfury` | 2026-10-22T202041439252 -> 2026-10-23T052601893792 | 2 changed | quiet |
| 2026-10-23 | `remote/dev.mcphost/mcphost` | 2026-10-22T052550209751 -> 2026-10-23T052602288513 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.hermoso-ai/hermoso` | 2026-10-22T202031658885 -> 2026-10-23T052559260858 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.kansei-link/kansei-mcp-server` | 2026-10-21T121432577523 -> 2026-10-23T052619028788 | 1 changed | quiet |
| 2026-10-23 | `remote/team.yardstick/yardstick` | 2026-10-21T234050210384 -> 2026-10-23T052557221702 | 1 changed, 21 added | quiet |
| 2026-10-23 | `remote/com.problee/problee` | 2026-10-21T121644654275 -> 2026-10-23T052558160573 | 3 changed, 1 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 27968 substantive, 14344 that changed only numbers (a catalogue counter ticking, a date), 581 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 22156 | 8734 | 13422 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 654 | 654 | 0 | 0 |
| `caseyjhand.com` | 174 | 174 | 0 | 0 |
| `sistaminuten.se` | 138 | 4 | 0 | 134 |
| `afbudsrejser.dk` | 137 | 4 | 0 | 133 |
| `akkilahdot.fi` | 137 | 4 | 0 | 133 |
| `restplass.no` | 137 | 4 | 0 | 133 |
| `socialloop.ai` | 133 | 133 | 0 | 0 |
| `remoshift.com` | 108 | 8 | 100 | 0 |
| `fundinglandscape.com` | 106 | 71 | 35 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| 5127 other operators | 16575 | 15740 | 787 | 48 |
