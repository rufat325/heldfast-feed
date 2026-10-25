# MCP server tool changes

Last change observed 2026-10-25T19:19:09+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

49983 changes to a tool definition: 2189 npm releases (1943 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 47794 readings of hosted servers that found their tools changed; 2603 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-25 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-10-25T132420442558 -> 2026-10-25T191910765650 | 2 changed | quiet |
| 2026-10-25 | `remote/no.restplass/travel-search` | 2026-10-25T132419885562 -> 2026-10-25T191908932059 | 1 changed | quiet |
| 2026-10-25 | `remote/dk.afbudsrejser/travel-search` | 2026-10-25T132418638778 -> 2026-10-25T191907563568 | 1 changed | quiet |
| 2026-10-25 | `remote/com.findbroadbanddeals/broadband-deals` | 2026-10-25T102534971465 -> 2026-10-25T191908056349 | 1 changed | quiet |
| 2026-10-25 | `remote/studio.gradients/mcp` | 2026-10-25T132425245148 -> 2026-10-25T191905616013 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.imokokok/insight-oracle` | 2026-10-25T115827594171 -> 2026-10-25T191906389661 | 1 changed, 6 added | review |
| 2026-10-25 | `remote/fi.akkilahdot/travel-search` | 2026-10-25T132424541734 -> 2026-10-25T191903916903 | 1 changed | quiet |
| 2026-10-25 | `remote/org.thealibrary/thea` | 2026-10-24T190414497710 -> 2026-10-25T191902829841 | 3 changed | quiet |
| 2026-10-25 | `remote/gg.unicum/wot-stats` | 2026-10-25T052300350674 -> 2026-10-25T191900525932 | 2 changed, 1 added | quiet |
| 2026-10-25 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-25T052258693861 -> 2026-10-25T191859493020 | 1 changed | quiet |
| 2026-10-25 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-25T052253080115 -> 2026-10-25T191858773679 | 10 changed | quiet |
| 2026-10-25 | `remote/com.swarmmemo/bulletin.1` | 2026-10-25T115658790777 -> 2026-10-25T191859541496 | 1 changed | quiet |
| 2026-10-25 | `remote/com.socialnetworkforaiagents/agent-socials` | 2026-10-23T120441790417 -> 2026-10-25T191857860808 | 2 changed, 1 added | quiet |
| 2026-10-25 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-25T132418219591 -> 2026-10-25T191857205645 | 1 changed | quiet |
| 2026-10-25 | `remote/ai.shorti/shorti` | 2026-10-24T112839805721 -> 2026-10-25T191856864354 | 4 changed | quiet |
| 2026-10-25 | `remote/dev.workers.quietworklabs.qw-swap/quietwork-swap` | 2026-10-25T102241651740 -> 2026-10-25T191853828054 | 14 changed, 2 added (every tool) | quiet |
| 2026-10-25 | `remote/io.github.richardsolomou/praetorium` | 2026-10-24T190407387833 -> 2026-10-25T191853439578 | 2 changed | quiet |
| 2026-10-25 | `remote/dev.precleared/contact-check` | 2026-10-23T120339856169 -> 2026-10-25T191854823140 | 1 changed | quiet |
| 2026-10-25 | `remote/com.remoshift/jobs` | 2026-10-25T132415677679 -> 2026-10-25T191853120444 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-10-25T132413527198 -> 2026-10-25T191850809130 | 2 changed | quiet |
| 2026-10-25 | `remote/io.github.fredxhansson-cmyk/noniner` | 2026-10-23T233427450996 -> 2026-10-25T191849912820 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.eamwhite1/xrpl-referee` | 2026-10-25T132413167381 -> 2026-10-25T191850293994 | 3 changed | quiet |
| 2026-10-25 | `remote/com.pondchat/pondchat` | 2026-10-25T115528135075 -> 2026-10-25T191850418138 | 2 changed | quiet |
| 2026-10-25 | `remote/co.civai.nova/google-sheets-agent` | 2026-10-25T115513015516 -> 2026-10-25T191850208651 | 2 added | quiet |
| 2026-10-25 | `remote/io.taifoon/coordination-layer.1` | 2026-10-25T132412473355 -> 2026-10-25T191849110781 | 1 changed | review |
| 2026-10-25 | `remote/ai.usedby/usedby` | 2026-10-25T120056066945 -> 2026-10-25T191849450703 | 6 changed (every tool) | quiet |
| 2026-10-25 | `remote/se.sistaminuten/travel-search` | 2026-10-25T132412107601 -> 2026-10-25T191849072785 | 1 changed | quiet |
| 2026-10-25 | `remote/win.price/pricewin` | 2026-10-25T102043235135 -> 2026-10-25T191847397791 | 2 changed | quiet |
| 2026-10-25 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-25T102447871213 -> 2026-10-25T191847014500 | 3 added | quiet |
| 2026-10-25 | `remote/com.moltlinestudio/skillmd-lint` | 2026-10-25T102024698087 -> 2026-10-25T191843854614 | 3 changed | quiet |
| 2026-10-25 | `remote/com.moltlinestudio/outbound` | 2026-10-25T102024597187 -> 2026-10-25T191843700873 | 1 changed | quiet |
| 2026-10-25 | `remote/com.moltlinestudio/merchant` | 2026-10-25T102024552023 -> 2026-10-25T191843521621 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.mirabello-consultancy/mcp-server` | 2026-10-25T102023978616 -> 2026-10-25T191845705605 | 1 changed | quiet |
| 2026-10-25 | `remote/com.moltlinestudio/humanizer` | 2026-10-25T102024395323 -> 2026-10-25T191843390424 | 3 changed | quiet |
| 2026-10-25 | `remote/com.moltlinestudio/govern` | 2026-10-25T102024271247 -> 2026-10-25T191843369541 | 4 changed | quiet |
| 2026-10-25 | `remote/com.moltlinestudio/educator` | 2026-10-25T102024318686 -> 2026-10-25T191843202991 | 1 changed | quiet |
| 2026-10-25 | `remote/ai.switchapp/switch` | 2026-10-25T102226161238 -> 2026-10-25T191843170561 | 2 changed | quiet |
| 2026-10-25 | `remote/io.github.eamwhite1/agent-trust` | 2026-10-25T132438974724 -> 2026-10-25T191842498429 | 3 changed | quiet |
| 2026-10-25 | `remote/com.tektolo/rental-property` | 2026-10-25T052254726681 -> 2026-10-25T191841518405 | 2 changed | quiet |
| 2026-10-25 | `remote/com.pagelemon/pagelemon` | 2026-10-24T190411045906 -> 2026-10-25T191840833582 | 3 changed, 15 added, 15 removed | quiet |
| 2026-10-25 | `remote/com.opedd/opedd-mcp` | 2026-10-25T102150864564 -> 2026-10-25T191840669702 | 1 changed | quiet |
| 2026-10-25 | `remote/com.moltlinestudio/dropship` | 2026-10-25T102138205106 -> 2026-10-25T191839866528 | 6 changed (every tool) | quiet |
| 2026-10-25 | `remote/com.moltlinestudio/data` | 2026-10-25T102138027107 -> 2026-10-25T191839807667 | 2 changed | quiet |
| 2026-10-25 | `remote/dev.upfork/upfork` | 2026-10-25T102858733576 -> 2026-10-25T191839790687 | 1 changed, 3 added | quiet |
| 2026-10-25 | `remote/com.moltlinestudio/codereview` | 2026-10-25T102137831893 -> 2026-10-25T191839248385 | 3 changed | quiet |
| 2026-10-25 | `remote/io.github.exquad/thecablecode` | 2026-10-23T200817592963 -> 2026-10-25T191837945775 | 1 added | quiet |
| 2026-10-25 | `remote/com.tektolo/capabilities` | 2026-10-25T052254183621 -> 2026-10-25T191836841442 | 2 changed | quiet |
| 2026-10-25 | `remote/com.kernelcad/kernelcad` | 2026-10-25T132401796655 -> 2026-10-25T191839254691 | 2 changed | quiet |
| 2026-10-25 | `remote/cc.thecolony/mcp-server` | 2026-10-25T132517412136 -> 2026-10-25T191838226880 | 7 changed | quiet |
| 2026-10-25 | `remote/online.sellular/sellular` | 2026-10-25T102321504903 -> 2026-10-25T191836737264 | 22 changed (every tool) | quiet |
| 2026-10-25 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-24T112702745683 -> 2026-10-25T191835381643 | 4 added | quiet |
| 2026-10-25 | `remote/io.github.peter120525-cmd/lawmadi-os` | 2026-10-25T132349563267 -> 2026-10-25T191835064924 | 1 changed | quiet |
| 2026-10-25 | `remote/com.thefilmradar/filmlab` | 2026-10-25T115155933991 -> 2026-10-25T191835212825 | 3 changed | quiet |
| 2026-10-25 | `remote/io.github.drexthealpha/knos` | 2026-10-23T200753515639 -> 2026-10-25T191831645316 | 1 changed | quiet |
| 2026-10-25 | `remote/com.owlchart/owlchart` | 2026-10-25T102227572488 -> 2026-10-25T191834012283 | 2 added | quiet |
| 2026-10-25 | `remote/app.pagecritic/pagecritic` | 2026-10-25T102227994294 -> 2026-10-25T191832932497 | 1 changed | quiet |
| 2026-10-25 | `remote/dev.specpilot/specpilot` | 2026-10-24T125756606646 -> 2026-10-25T191831689671 | 2 changed (every tool) | quiet |
| 2026-10-25 | `remote/com.normapi/mcp` | 2026-10-23T120508493314 -> 2026-10-25T191831108560 | 4 changed (every tool) | quiet |
| 2026-10-25 | `remote/nl.nltaxcalculator/dutch-tax` | 2026-10-25T102205427810 -> 2026-10-25T191831430520 | 15 added | quiet |
| 2026-10-25 | `remote/io.github.Perufitlife/postwire-mcp` | 2026-10-23T052608931433 -> 2026-10-25T191830586406 | 1 changed, 4 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 31891 substantive, 17450 that changed only numbers (a catalogue counter ticking, a date), 642 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 26731 | 10363 | 16368 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 775 | 775 | 0 | 0 |
| `caseyjhand.com` | 220 | 220 | 0 | 0 |
| `sistaminuten.se` | 152 | 4 | 0 | 148 |
| `afbudsrejser.dk` | 151 | 4 | 0 | 147 |
| `akkilahdot.fi` | 151 | 4 | 0 | 147 |
| `restplass.no` | 151 | 4 | 0 | 147 |
| `socialloop.ai` | 146 | 146 | 0 | 0 |
| `remoshift.com` | 121 | 8 | 113 | 0 |
| `fundinglandscape.com` | 116 | 75 | 41 | 0 |
| `openkrill.app` | 111 | 111 | 0 | 0 |
| 5609 other operators | 18817 | 17836 | 928 | 53 |
