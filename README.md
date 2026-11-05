# MCP server tool changes

Last change observed 2026-11-05T01:07:41+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

77324 changes to a tool definition: 3200 npm releases (2954 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 74124 readings of hosted servers that found their tools changed; 3362 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-05 | `remote/se.sistaminuten/travel-search` | 2026-11-04T200757545050 -> 2026-11-05T010741886993 | 1 changed | quiet |
| 2026-11-05 | `remote/com.menloinsurance/mcp` | 2026-11-04T150738561901 -> 2026-11-05T010740618615 | 3 changed | quiet |
| 2026-11-05 | `remote/com.coveragecat/insurance` | 2026-11-04T200749505695 -> 2026-11-05T010737155360 | 12 changed, 7 removed | quiet |
| 2026-11-05 | `remote/com.anchorterminal/anchor-terminal` | 2026-11-03T195659630979 -> 2026-11-05T010736416095 | 1 changed, 2 added | quiet |
| 2026-11-05 | `remote/io.github.SKalinin909/tradingcalc` | 2026-11-04T200739914370 -> 2026-11-05T010730085242 | 1 added | quiet |
| 2026-11-05 | `remote/com.thefomite/fomite` | 2026-11-04T005914205697 -> 2026-11-05T010728881040 | 1 changed | quiet |
| 2026-11-05 | `remote/dev.tanod/tanod` | 2026-11-03T144751169317 -> 2026-11-05T010726977283 | 3 changed | quiet |
| 2026-11-05 | `remote/dev.tanod/agents` | 2026-11-03T144749848889 -> 2026-11-05T010726536194 | 3 changed | quiet |
| 2026-11-05 | `remote/io.github.cryptoconspiracy/vurto-swap` | 2026-11-04T200731063286 -> 2026-11-05T010724392317 | 1 changed, 2 added | review |
| 2026-11-05 | `remote/com.idosgames/platform` | 2026-11-04T005907966987 -> 2026-11-05T010721915955 | 27 changed | quiet |
| 2026-11-05 | `remote/pl.finwire/data` | 2026-11-04T200721723165 -> 2026-11-05T010718291633 | 3 changed, 7 added | quiet |
| 2026-11-05 | `remote/es.proceres/proceres` | 2026-11-04T200729046641 -> 2026-11-05T010717213419 | 6 changed | quiet |
| 2026-11-05 | `remote/com.crm-connector/crm-connector` | 2026-11-04T200717249574 -> 2026-11-05T010715757196 | 2 changed | quiet |
| 2026-11-05 | `remote/io.github.imokokok/insight-oracle` | 2026-11-04T123823384665 -> 2026-11-05T010701487278 | 3 changed | quiet |
| 2026-11-05 | `remote/studio.gradients/mcp` | 2026-11-04T200818111804 -> 2026-11-05T010659916036 | 1 changed | quiet |
| 2026-11-05 | `remote/io.kompare/search` | 2026-11-03T122615621180 -> 2026-11-05T010701914613 | 2 changed | quiet |
| 2026-11-05 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-04T005901139962 -> 2026-11-05T010657183434 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-04T150511338424 -> 2026-11-05T010657997506 | 8 added | quiet |
| 2026-11-05 | `remote/fi.akkilahdot/travel-search` | 2026-11-04T200815013020 -> 2026-11-05T010657948288 | 1 changed | quiet |
| 2026-11-05 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-04T200815521798 -> 2026-11-05T010657399743 | 9 changed (every tool) | quiet |
| 2026-11-05 | `remote/land.fabrica/mcp` | 2026-11-04T123729895612 -> 2026-11-05T010656724674 | 2 added | quiet |
| 2026-11-05 | `remote/io.github.seasonsagents-art/webaz` | 2026-11-04T200812224709 -> 2026-11-05T010656426119 | 1 added | quiet |
| 2026-11-05 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-04T200809148659 -> 2026-11-05T010656669208 | 2 changed | quiet |
| 2026-11-05 | `remote/io.github.ronrey/comos-federation` | 2026-11-04T145647638774 -> 2026-11-05T010655370318 | 2 changed | quiet |
| 2026-11-05 | `remote/io.github.grzesir/botspot-trading` | 2026-11-03T122608311606 -> 2026-11-05T010655731374 | 3 changed | quiet |
| 2026-11-05 | `remote/si.thinkhard/prompt-tools` | 2026-11-04T200800865019 -> 2026-11-05T010654140958 | 1 changed | quiet |
| 2026-11-05 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-04T200800206147 -> 2026-11-05T010654416789 | 2 changed | quiet |
| 2026-11-05 | `remote/net.letsbot/mcp` | 2026-11-04T200634576565 -> 2026-11-05T010652711020 | 1 changed | quiet |
| 2026-11-05 | `remote/law.lexray/lexray` | 2026-11-03T144013467362 -> 2026-11-05T010653454417 | 3 changed | quiet |
| 2026-11-05 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-04T123804851642 -> 2026-11-05T010653700115 | 1 changed | quiet |
| 2026-11-05 | `remote/com.strongsaga/gear-lookup` | 2026-11-03T024253452048 -> 2026-11-05T010651788174 | 2 changed | review |
| 2026-11-05 | `remote/net.stabledomains/registrar` | 2026-11-04T150253198901 -> 2026-11-05T010650521832 | 9 changed | quiet |
| 2026-11-05 | `remote/io.github.liad142/yedapo` | 2026-11-04T200812971713 -> 2026-11-05T010649840266 | 2 changed (every tool) | quiet |
| 2026-11-05 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-04T200752427939 -> 2026-11-05T010649879932 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-04T200815544998 -> 2026-11-05T010649654641 | 2 changed | quiet |
| 2026-11-05 | `remote/ai.oriiion/oriiion` | 2026-11-04T150750784738 -> 2026-11-05T010649231896 | 1 changed | quiet |
| 2026-11-05 | `remote/no.restplass/travel-search` | 2026-11-04T200810318346 -> 2026-11-05T010649043462 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.QDThead/signal-lab` | 2026-11-03T195753390147 -> 2026-11-05T010650288280 | 4 changed | quiet |
| 2026-11-05 | `remote/io.github.tettertotter/fundinglandscape` | 2026-11-04T200617727713 -> 2026-11-05T010647507666 | 2 changed | quiet |
| 2026-11-05 | `remote/com.triremes/triremes` | 2026-11-03T195503869339 -> 2026-11-05T010647163174 | 2 changed | quiet |
| 2026-11-05 | `remote/be.lexgo/jobs` | 2026-11-04T150844580686 -> 2026-11-05T010647367253 | 5 changed | quiet |
| 2026-11-05 | `remote/com.remoshift/jobs` | 2026-11-04T200744136782 -> 2026-11-05T010645539094 | 1 changed | quiet |
| 2026-11-05 | `remote/com.reliasim/public` | 2026-11-04T150138869119 -> 2026-11-05T010645345865 | 3 changed | quiet |
| 2026-11-05 | `remote/dk.afbudsrejser/travel-search` | 2026-11-04T200800582444 -> 2026-11-05T010644812555 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.fivebar-xyz/fivebar` | 2026-11-04T200615202839 -> 2026-11-05T010646294900 | 3 changed | quiet |
| 2026-11-05 | `remote/com.neblla/neblla` | 2026-11-04T005832335643 -> 2026-11-05T010642203893 | 9 changed | quiet |
| 2026-11-05 | `remote/com.multicinesortega/cartelera` | 2026-11-04T200728268664 -> 2026-11-05T010643635549 | 1 changed | quiet |
| 2026-11-05 | `remote/info.stride/stride` | 2026-11-03T144818952370 -> 2026-11-05T010640318809 | 3 changed | quiet |
| 2026-11-05 | `remote/com.googleapis.sqladmin/mcp` | 2026-11-04T200742214145 -> 2026-11-05T010638441870 | 3 changed | quiet |
| 2026-11-05 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-11-04T005842370362 -> 2026-11-05T010640374388 | 1 changed | quiet |
| 2026-11-05 | `remote/cloud.nttzen.secdb/zen-secdb` | 2026-11-04T200742575412 -> 2026-11-05T010638829826 | 1 changed | quiet |
| 2026-11-05 | `remote/app.openkrill/buyersignals` | 2026-11-04T123801340850 -> 2026-11-05T010638199814 | 1 changed | quiet |
| 2026-11-05 | `remote/re.rundata/temps-reel` | 2026-11-04T150238292336 -> 2026-11-05T010638862326 | 31 changed (every tool) | quiet |
| 2026-11-05 | `remote/com.rushordertees/rushordertees` | 2026-11-04T200714244634 -> 2026-11-05T010637681675 | 11 changed | quiet |
| 2026-11-05 | `remote/com.kernelcad/kernelcad` | 2026-11-04T123728962680 -> 2026-11-05T010636608884 | 2 changed | quiet |
| 2026-11-05 | `remote/com.getfairquery/agent-trust-mcp` | 2026-11-04T200705333708 -> 2026-11-05T010634083317 | 5 changed | quiet |
| 2026-11-05 | `remote/trade.coil/stock-market-scanner.1` | 2026-11-03T195708892847 -> 2026-11-05T010632707669 | 2 changed | quiet |
| 2026-11-05 | `remote/org.worldgdp/nowcasts` | 2026-11-04T200711587062 -> 2026-11-05T010631423187 | 1 added | quiet |
| 2026-11-05 | `remote/fi.northpoint/marketing-compliance` | 2026-11-03T144520206129 -> 2026-11-05T010632325771 | 3 changed | quiet |
| 2026-11-05 | `remote/com.cev-os/data` | 2026-11-04T145557884914 -> 2026-11-05T010632205254 | 3 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 47410 substantive, 29082 that changed only numbers (a catalogue counter ticking, a date), 832 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 43261 | 15875 | 27386 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1366 | 1366 | 0 | 0 |
| `caseyjhand.com` | 352 | 352 | 0 | 0 |
| `sistaminuten.se` | 196 | 6 | 0 | 190 |
| `afbudsrejser.dk` | 195 | 6 | 0 | 189 |
| `akkilahdot.fi` | 195 | 6 | 0 | 189 |
| `restplass.no` | 195 | 6 | 0 | 189 |
| `socialloop.ai` | 188 | 188 | 0 | 0 |
| `remoshift.com` | 165 | 14 | 151 | 0 |
| `openkrill.app` | 153 | 153 | 0 | 0 |
| `fundinglandscape.com` | 150 | 91 | 59 | 0 |
| 7517 other operators | 28567 | 27006 | 1486 | 75 |
