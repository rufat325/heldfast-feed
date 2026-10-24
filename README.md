# MCP server tool changes

Last change observed 2026-10-24T05:05:28+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

45314 changes to a tool definition: 1988 npm releases (1742 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 43326 readings of hosted servers that found their tools changed; 2434 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-24 | `remote/com.zinvyl/marketplace` | 2026-10-23T200857266291 -> 2026-10-24T050529428221 | 5 changed | quiet |
| 2026-10-24 | `remote/com.orlandu/arcade` | 2026-10-23T120654698285 -> 2026-10-24T050528614260 | 1 changed | quiet |
| 2026-10-24 | `remote/studio.gradients/mcp` | 2026-10-23T233429926806 -> 2026-10-24T050528486032 | 1 changed | quiet |
| 2026-10-24 | `remote/fi.akkilahdot/travel-search` | 2026-10-23T233429044339 -> 2026-10-24T050527349410 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.CodeWever/wever-labs-products` | 2026-10-22T233938067665 -> 2026-10-24T050526925867 | 2 changed | quiet |
| 2026-10-24 | `remote/com.ticketsea/ticketsea` | 2026-10-22T202058724394 -> 2026-10-24T050524193501 | 2 changed | quiet |
| 2026-10-24 | `remote/com.theagentsindex/mcp` | 2026-10-23T120537878803 -> 2026-10-24T050524540379 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-23T135202450442 -> 2026-10-24T050524496511 | 1 changed | quiet |
| 2026-10-24 | `remote/com.swarmmemo/bulletin.1` | 2026-10-23T052639903666 -> 2026-10-24T050523105948 | 27 changed, 1 added | quiet |
| 2026-10-24 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-23T233423432991 -> 2026-10-24T050521233172 | 1 changed | quiet |
| 2026-10-24 | `remote/com.swarmmemo/bulletin` | 2026-10-22T233933553742 -> 2026-10-24T050522218140 | 8 changed | quiet |
| 2026-10-24 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-10-23T120642034333 -> 2026-10-24T050521858096 | 2 changed | quiet |
| 2026-10-24 | `remote/io.github.LE-VAI/designesy-org` | 2026-10-22T105902963138 -> 2026-10-24T050520939584 | 1 changed | quiet |
| 2026-10-24 | `remote/no.restplass/travel-search` | 2026-10-23T233445579366 -> 2026-10-24T050519373197 | 1 changed | quiet |
| 2026-10-24 | `remote/dk.afbudsrejser/travel-search` | 2026-10-23T233444827807 -> 2026-10-24T050519252592 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-10-23T200818624791 -> 2026-10-24T050519183622 | 1 added | quiet |
| 2026-10-24 | `remote/com.remoshift/jobs` | 2026-10-23T233418867551 -> 2026-10-24T050518705196 | 1 changed | quiet |
| 2026-10-24 | `remote/se.sistaminuten/travel-search` | 2026-10-23T233435671280 -> 2026-10-24T050517732294 | 1 changed | quiet |
| 2026-10-24 | `remote/com.menloinsurance/mcp` | 2026-10-22T105957837439 -> 2026-10-24T050516728422 | 4 changed | quiet |
| 2026-10-24 | `remote/com.ferntool/ip` | 2026-10-23T052626733417 -> 2026-10-24T050516076202 | 1 added | quiet |
| 2026-10-24 | `remote/org.thealibrary/thea` | 2026-10-22T052607513458 -> 2026-10-24T050516584417 | 1 changed | quiet |
| 2026-10-24 | `remote/com.sfxmint/sounds` | 2026-10-23T135148760660 -> 2026-10-24T050514303007 | 2 changed | quiet |
| 2026-10-24 | `remote/com.ocklu/hypermarket` | 2026-10-23T135153759017 -> 2026-10-24T050519905818 | 4 changed | quiet |
| 2026-10-24 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-23T052613193039 -> 2026-10-24T050515093392 | 1 changed | quiet |
| 2026-10-24 | `remote/com.multicinesortega/cartelera` | 2026-10-23T200816747482 -> 2026-10-24T050515227082 | 1 changed | quiet |
| 2026-10-24 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-23T200801071682 -> 2026-10-24T050513110181 | 10 changed | quiet |
| 2026-10-24 | `remote/ca.movahedi/privacy` | 2026-10-22T140836095883 -> 2026-10-24T050513837435 | 2 added | quiet |
| 2026-10-24 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-10-23T233405434193 -> 2026-10-24T050514438741 | 3 changed, 1 removed | quiet |
| 2026-10-24 | `remote/com.thefomite/fomite` | 2026-10-23T120751955261 -> 2026-10-24T050511253732 | 1 changed | quiet |
| 2026-10-24 | `remote/com.screenrove/screenrove` | 2026-10-23T135155450062 -> 2026-10-24T050516930482 | 3 added | quiet |
| 2026-10-24 | `remote/fun.pumpdata/pumpdata` | 2026-10-22T233923153424 -> 2026-10-24T050510189218 | 2 changed, 2 added | quiet |
| 2026-10-24 | `remote/com.vendooly/vendooly` | 2026-10-23T200809506578 -> 2026-10-24T050511753771 | 4 added | quiet |
| 2026-10-24 | `remote/com.project-feldspar/scan` | 2026-10-22T105640985332 -> 2026-10-24T050511560037 | 2 changed (every tool) | quiet |
| 2026-10-24 | `remote/ai.switchapp/switch` | 2026-10-23T233403860999 -> 2026-10-24T050510587918 | 39 changed, 3 added, 1 removed | quiet |
| 2026-10-24 | `remote/io.github.richardsolomou/praetorium` | 2026-10-23T200757922787 -> 2026-10-24T050510558717 | 3 changed | quiet |
| 2026-10-24 | `remote/com.playshowandtell/show-and-tell` | 2026-10-22T105912654309 -> 2026-10-24T050509702725 | 1 added | quiet |
| 2026-10-24 | `remote/com.pagelemon/pagelemon` | 2026-10-23T135144963240 -> 2026-10-24T050508849502 | 32 changed, 3 added | quiet |
| 2026-10-24 | `remote/com.negativeresistance/cure-protocol` | 2026-10-23T052604527359 -> 2026-10-24T050507268562 | 74 changed | quiet |
| 2026-10-24 | `remote/dev.mcphost/mcphost` | 2026-10-23T233409993677 -> 2026-10-24T050508199758 | 2 changed | quiet |
| 2026-10-24 | `remote/io.github.choaticpixels/wicked-mcp` | 2026-10-23T200757414224 -> 2026-10-24T050505537402 | 107 changed (every tool) | quiet |
| 2026-10-24 | `remote/app.toolsnap/toolsnap-mcp` | 2026-10-22T105454308225 -> 2026-10-24T050503445890 | 5 changed | quiet |
| 2026-10-24 | `remote/org.living-bread.mcp/living-bread` | 2026-10-23T200747388919 -> 2026-10-24T050504464845 | 1 changed | quiet |
| 2026-10-24 | `remote/com.lebaneselegislation/mcp` | 2026-10-23T135137312464 -> 2026-10-24T050501456759 | 3 changed, 2 added | quiet |
| 2026-10-24 | `remote/net.hotelrefund/price-tracker` | 2026-10-23T052612758613 -> 2026-10-24T050459672743 | 1 changed | quiet |
| 2026-10-24 | `remote/tech.kaiku/kaiku.1` | 2026-10-23T233359401463 -> 2026-10-24T050459841505 | 1 changed, 1 added | quiet |
| 2026-10-24 | `remote/io.github.jasp402/hypercodemotion-mcp` | 2026-10-23T200746784883 -> 2026-10-24T050458944023 | 2 changed | quiet |
| 2026-10-24 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt` | 2026-10-23T052610876725 -> 2026-10-24T050458325647 | 1 changed | quiet |
| 2026-10-24 | `remote/club.elron/public-rentals` | 2026-10-23T115703665132 -> 2026-10-24T050500081521 | 2 changed | quiet |
| 2026-10-24 | `remote/co.ainumbers/tools` | 2026-10-23T233357915861 -> 2026-10-24T050457633155 | 3 changed | quiet |
| 2026-10-24 | `remote/io.github.kirillradchenko96/fresh402` | 2026-10-23T115736316575 -> 2026-10-24T050456463477 | 5 changed (every tool) | quiet |
| 2026-10-24 | `remote/com.clypmint/clypmint` | 2026-10-23T200732398025 -> 2026-10-24T050455772739 | 1 changed | quiet |
| 2026-10-24 | `remote/com.convertlyft/convertlyft` | 2026-10-23T200801570175 -> 2026-10-24T050454065037 | 66 changed (every tool) | quiet |
| 2026-10-24 | `remote/br.app.classificado/meta-agent-tools` | 2026-10-23T115557622836 -> 2026-10-24T050457753850 | 1 changed | quiet |
| 2026-10-24 | `remote/ai.autonomad/travel` | 2026-10-23T233400910924 -> 2026-10-24T050452905936 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.sustany/alcbar-match` | 2026-10-22T202020586973 -> 2026-10-24T050451962001 | 9 changed | quiet |
| 2026-10-24 | `remote/io.github.OneWave-AI/gillby` | 2026-10-22T202024329800 -> 2026-10-24T050452859428 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.qxxx5vyd77-byte/directors-lookbook` | 2026-10-22T202019671740 -> 2026-10-24T050450913822 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.OV3RK177/kairos-signal` | 2026-10-23T233356937332 -> 2026-10-24T050450474768 | 8 changed | review |
| 2026-10-24 | `remote/com.kairossignal/kairos-signal` | 2026-10-23T233356640248 -> 2026-10-24T050450130262 | 8 changed | review |
| 2026-10-24 | `remote/ai.capxule/capxule` | 2026-10-23T233355497753 -> 2026-10-24T050450374811 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 28826 substantive, 15887 that changed only numbers (a catalogue counter ticking, a date), 601 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 23651 | 8749 | 14902 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 657 | 657 | 0 | 0 |
| `caseyjhand.com` | 188 | 188 | 0 | 0 |
| `sistaminuten.se` | 143 | 4 | 0 | 139 |
| `afbudsrejser.dk` | 142 | 4 | 0 | 138 |
| `akkilahdot.fi` | 142 | 4 | 0 | 138 |
| `restplass.no` | 142 | 4 | 0 | 138 |
| `socialloop.ai` | 138 | 138 | 0 | 0 |
| `remoshift.com` | 113 | 8 | 105 | 0 |
| `fundinglandscape.com` | 108 | 71 | 37 | 0 |
| `openkrill.app` | 97 | 97 | 0 | 0 |
| 5337 other operators | 17452 | 16561 | 843 | 48 |
