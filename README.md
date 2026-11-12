# MCP server tool changes

Last change observed 2026-11-12T07:48:08+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

91704 changes to a tool definition: 3941 npm releases (3695 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 87763 readings of hosted servers that found their tools changed; 3810 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-12 | `remote/com.serverscan/mcp` | 2026-11-11T150138911261 -> 2026-11-12T074810782678 | 6 changed (every tool) | quiet |
| 2026-11-12 | `remote/studio.gradients/mcp` | 2026-11-11T230934744772 -> 2026-11-12T074802514671 | 1 changed | quiet |
| 2026-11-12 | `remote/io.github.EasyGerber/easygerber` | 2026-11-10T152925428351 -> 2026-11-12T074800412045 | 3 changed | quiet |
| 2026-11-12 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-11T071403253430 -> 2026-11-12T074758969120 | 1 changed | quiet |
| 2026-11-12 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-11T230927108218 -> 2026-11-12T074801335254 | 2 changed, 16 added | quiet |
| 2026-11-12 | `remote/fi.akkilahdot/travel-search` | 2026-11-11T230925974969 -> 2026-11-12T074759664468 | 1 changed | quiet |
| 2026-11-12 | `remote/io.github.seasonsagents-art/webaz` | 2026-11-10T220132424170 -> 2026-11-12T074757144853 | 1 added | quiet |
| 2026-11-12 | `remote/ru.vedarai/mcp` | 2026-11-11T150015477575 -> 2026-11-12T074758597597 | 1 changed | quiet |
| 2026-11-12 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-11T230923694954 -> 2026-11-12T074758179811 | 3 changed | quiet |
| 2026-11-12 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-11T071351624216 -> 2026-11-12T074755144631 | 1 changed | quiet |
| 2026-11-12 | `remote/ai.stablenews/news` | 2026-11-11T145852182103 -> 2026-11-12T074751703473 | 1 added | quiet |
| 2026-11-12 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-11T230904453049 -> 2026-11-12T074751664257 | 1 changed | quiet |
| 2026-11-12 | `remote/uk.seocornwall/site` | 2026-11-11T145810869213 -> 2026-11-12T074748282831 | 2 changed | quiet |
| 2026-11-12 | `remote/uk.co.seopersonalinjurylawyers/site` | 2026-11-11T145810837824 -> 2026-11-12T074749030725 | 2 changed | quiet |
| 2026-11-12 | `remote/uk.co.seodealerships/site` | 2026-11-11T145810574274 -> 2026-11-12T074748552064 | 2 changed | quiet |
| 2026-11-12 | `remote/io.github.moelayyan90/xguard` | 2026-11-10T030035149097 -> 2026-11-12T074747425788 | 1 changed | quiet |
| 2026-11-12 | `remote/io.github.liad142/yedapo` | 2026-11-11T071500090089 -> 2026-11-12T074746599572 | 2 changed (every tool) | quiet |
| 2026-11-12 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-11-11T071459461049 -> 2026-11-12T074747286971 | 1 added | quiet |
| 2026-11-12 | `remote/no.restplass/travel-search` | 2026-11-11T230930131373 -> 2026-11-12T074746698340 | 1 changed | quiet |
| 2026-11-12 | `remote/com.googleapis.run/mcp` | 2026-11-11T145745089193 -> 2026-11-12T074746370732 | 1 changed | quiet |
| 2026-11-12 | `remote/com.nomosprotocol/nomos` | 2026-11-11T230929287218 -> 2026-11-12T074745424008 | 1 added | quiet |
| 2026-11-12 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-11-11T071428235226 -> 2026-11-12T074744955859 | 1 added | quiet |
| 2026-11-12 | `remote/io.taifoon/coordination-layer.1` | 2026-11-11T071425918426 -> 2026-11-12T074743660134 | 1 changed | review |
| 2026-11-12 | `remote/dk.afbudsrejser/travel-search` | 2026-11-11T230923782952 -> 2026-11-12T074743467883 | 1 changed | quiet |
| 2026-11-12 | `remote/se.sistaminuten/travel-search` | 2026-11-11T230858656816 -> 2026-11-12T074742951240 | 1 changed | quiet |
| 2026-11-12 | `remote/global.uain/network` | 2026-11-10T130407567052 -> 2026-11-12T074740258369 | 2 changed | quiet |
| 2026-11-12 | `remote/ai.uetr/uetr.ai` | 2026-11-11T145745631827 -> 2026-11-12T074743577221 | 3 changed | quiet |
| 2026-11-12 | `remote/dev.zambo/zambo` | 2026-11-11T230918042228 -> 2026-11-12T074739745426 | 1 changed | quiet |
| 2026-11-12 | `remote/com.coveragecat/insurance` | 2026-11-11T230851673263 -> 2026-11-12T074739728373 | 1 added | quiet |
| 2026-11-12 | `remote/uk.co.whitelabelseomarketing/site` | 2026-11-11T145916541760 -> 2026-11-12T074738413478 | 2 changed | quiet |
| 2026-11-12 | `remote/app.vercel.watchesinstock-mcp/watches-in-stock` | 2026-11-10T030038823632 -> 2026-11-12T074736730139 | 1 changed, 3 removed | quiet |
| 2026-11-12 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-11T164057772275 -> 2026-11-12T074736553395 | 1 added, 1 removed | quiet |
| 2026-11-12 | `remote/app.usesnippet/snippet` | 2026-11-11T145838291289 -> 2026-11-12T074735989212 | 1 added | quiet |
| 2026-11-12 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-11T230908279667 -> 2026-11-12T074736641700 | 3 changed | quiet |
| 2026-11-12 | `remote/uk.co.seob2bcompanies/site` | 2026-11-11T145554152768 -> 2026-11-12T074734538280 | 2 changed | quiet |
| 2026-11-12 | `remote/io.github.RafaCoelho33/web3-systemic-agent` | 2026-11-10T130346776244 -> 2026-11-12T074733743911 | 4 changed (every tool) | review |
| 2026-11-12 | `remote/com.spacexploration/listings` | 2026-11-11T230905751611 -> 2026-11-12T074734660478 | 1 changed | quiet |
| 2026-11-12 | `remote/io.suverse.versum/catalog` | 2026-11-11T230902402065 -> 2026-11-12T074734343213 | 3 changed | quiet |
| 2026-11-12 | `remote/com.thefomite/fomite` | 2026-11-11T071408576833 -> 2026-11-12T074733097900 | 1 changed | quiet |
| 2026-11-12 | `remote/se.aigine/redact` | 2026-11-11T230857585249 -> 2026-11-12T074732043913 | 1 changed | quiet |
| 2026-11-12 | `remote/io.github.MorrisMoe/soulintime` | 2026-11-10T220201216551 -> 2026-11-12T074731317514 | 1 changed | quiet |
| 2026-11-12 | `remote/co.totalcms/docs` | 2026-11-11T071417223685 -> 2026-11-12T074731339408 | 3 changed | quiet |
| 2026-11-12 | `remote/uk.co.toolsppc/site` | 2026-11-11T145833482691 -> 2026-11-12T074730725596 | 2 changed | quiet |
| 2026-11-12 | `remote/tech.rovy/dirfast` | 2026-11-11T145449906603 -> 2026-11-12T074731483888 | 1 changed | quiet |
| 2026-11-12 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-11T230854407801 -> 2026-11-12T074730709733 | 1 added | quiet |
| 2026-11-12 | `remote/com.neblla/neblla` | 2026-11-11T230838932387 -> 2026-11-12T074733416894 | 3 changed | quiet |
| 2026-11-12 | `remote/com.multicinesortega/cartelera` | 2026-11-11T230839227098 -> 2026-11-12T074732463811 | 1 changed | quiet |
| 2026-11-12 | `remote/uk.co.seorecruitmentagencies/site` | 2026-11-11T145634020921 -> 2026-11-12T074729362380 | 2 changed | quiet |
| 2026-11-12 | `remote/uk.co.ppcmarketingcompany/site` | 2026-11-11T145440703282 -> 2026-11-12T074729813417 | 2 changed | quiet |
| 2026-11-12 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-10T025947162771 -> 2026-11-12T074729028349 | 3 changed, 18 added | quiet |
| 2026-11-12 | `remote/uk.co.seoplumbers/site` | 2026-11-11T145633457235 -> 2026-11-12T074729302182 | 2 changed | quiet |
| 2026-11-12 | `remote/uk.co.seocontentmarketing/site` | 2026-11-11T145633691427 -> 2026-11-12T074729073772 | 2 changed | quiet |
| 2026-11-12 | `remote/uk.co.seocompanysmallbusiness/site` | 2026-11-11T145633945222 -> 2026-11-12T074729163285 | 2 changed | quiet |
| 2026-11-12 | `remote/io.github.rnwy/mcp` | 2026-11-11T145607925072 -> 2026-11-12T074727054830 | 5 changed | quiet |
| 2026-11-12 | `remote/com.almostfire/strength-training` | 2026-11-10T130338297261 -> 2026-11-12T074727640542 | 1 changed | quiet |
| 2026-11-12 | `remote/ai.surfingdog/search` | 2026-11-11T164103463971 -> 2026-11-12T074728442278 | 1 changed | quiet |
| 2026-11-12 | `remote/org.evebrief.oracle/risk-check` | 2026-11-10T220133515643 -> 2026-11-12T074727165260 | 1 added | quiet |
| 2026-11-12 | `remote/com.partstable/partstable` | 2026-11-11T071421724340 -> 2026-11-12T074727019715 | 1 changed | quiet |
| 2026-11-12 | `remote/ai.switchapp/switch` | 2026-11-11T145439063781 -> 2026-11-12T074726411397 | 1 changed | quiet |
| 2026-11-12 | `remote/com.socialseal/mcp` | 2026-11-10T152242012980 -> 2026-11-12T074725490914 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 57546 substantive, 33194 that changed only numbers (a catalogue counter ticking, a date), 964 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 48830 | 17746 | 31084 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 2108 | 2108 | 0 | 0 |
| `caseyjhand.com` | 383 | 383 | 0 | 0 |
| `civai.co` | 309 | 309 | 0 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `revmesh2074.workers.dev` | 235 | 207 | 28 | 0 |
| `sistaminuten.se` | 225 | 6 | 0 | 219 |
| `afbudsrejser.dk` | 224 | 6 | 0 | 218 |
| `akkilahdot.fi` | 224 | 6 | 0 | 218 |
| `restplass.no` | 224 | 6 | 0 | 218 |
| `socialloop.ai` | 216 | 216 | 0 | 0 |
| 8820 other operators | 36127 | 33954 | 2082 | 91 |
