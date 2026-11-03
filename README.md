# MCP server tool changes

Last change observed 2026-11-03T14:50:49+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

73838 changes to a tool definition: 3094 npm releases (2848 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 70744 readings of hosted servers that found their tools changed; 3269 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-03 | `remote/no.restplass/travel-search` | 2026-11-03T122754833871 -> 2026-11-03T145050349651 | 1 changed | quiet |
| 2026-11-03 | `remote/com.praxikon/praxikon` | 2026-10-28T133500202705 -> 2026-11-03T145047809401 | 9 changed (every tool) | quiet |
| 2026-11-03 | `remote/io.github.openaccountants/openaccountants` | 2026-10-25T115920443970 -> 2026-11-03T145045012880 | 2 changed | quiet |
| 2026-11-03 | `remote/uk.co.speedi/availability` | 2026-10-28T133136166152 -> 2026-11-03T145042229136 | 1 changed | quiet |
| 2026-11-03 | `remote/dev.primitive/email` | 2026-10-23T233431948574 -> 2026-11-03T145034137863 | 14 changed (every tool) | quiet |
| 2026-11-03 | `remote/io.github.imokokok/insight-oracle` | 2026-11-03T122640788249 -> 2026-11-03T145035154988 | 3 changed, 10 added | quiet |
| 2026-11-03 | `remote/com.jobcrawls/connector` | 2026-10-21T122215782123 -> 2026-11-03T145022682841 | 1 changed | quiet |
| 2026-11-03 | `remote/xyz.x402helper/mcp` | 2026-11-03T122651596175 -> 2026-11-03T145023089879 | 2 changed | quiet |
| 2026-11-03 | `remote/com.incrediblefi/loan-marketplace` | 2026-10-18T113314304869 -> 2026-11-03T145023011235 | 2 changed | quiet |
| 2026-11-03 | `remote/com.immersivecommons/floor10` | 2026-10-30T210636039289 -> 2026-11-03T145020720172 | 1 added | quiet |
| 2026-11-03 | `remote/io.github.Fizzl13/x402-doctor` | 2026-10-31T130319888934 -> 2026-11-03T145018985635 | 1 changed | quiet |
| 2026-11-03 | `remote/studio.gradients/mcp` | 2026-11-03T122636936552 -> 2026-11-03T145018357216 | 1 changed | quiet |
| 2026-11-03 | `remote/dev.workers.microtools-x402.x402-dns-auth-checker/dns-auth-checker` | 2026-10-19T135309069086 -> 2026-11-03T145019507817 | 2 added | review |
| 2026-11-03 | `remote/xyz.tereno/tereno` | 2026-09-23T161036808553 -> 2026-11-03T145017367474 | 1 changed, 1 added | quiet |
| 2026-11-03 | `remote/io.github.wyroapi/wyro` | 2026-10-31T130319565259 -> 2026-11-03T145018602640 | 2 changed | quiet |
| 2026-11-03 | `remote/io.deeplead/deeplead` | 2026-10-27T210232038622 -> 2026-11-03T145015056879 | 13 added | quiet |
| 2026-11-03 | `remote/io.taifoon/coordination-layer.1` | 2026-11-03T122706179933 -> 2026-11-03T145013591863 | 1 changed | quiet |
| 2026-11-03 | `remote/com.vedutum/vedutum` | 2026-11-02T163938065318 -> 2026-11-03T145016185770 | 1 changed | quiet |
| 2026-11-03 | `remote/ai.startuphub/startuphub` | 2026-10-31T062139592611 -> 2026-11-03T145009110035 | 5 changed | review |
| 2026-11-03 | `remote/com.conferencefindr/events` | 2026-10-26T133511535600 -> 2026-11-03T145007485565 | 1 changed | quiet |
| 2026-11-03 | `remote/se.sistaminuten/travel-search` | 2026-11-03T122705596116 -> 2026-11-03T145005457655 | 1 changed | quiet |
| 2026-11-03 | `remote/dk.afbudsrejser/travel-search` | 2026-11-03T122747958603 -> 2026-11-03T145002272531 | 1 changed | quiet |
| 2026-11-03 | `remote/fi.akkilahdot/travel-search` | 2026-11-03T122635239739 -> 2026-11-03T144958884251 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.cryptosun/proximens-oracle` | 2026-09-23T161033442359 -> 2026-11-03T144957319383 | 2 changed | quiet |
| 2026-11-03 | `remote/de.overfit/overfit` | 2026-10-27T112400260161 -> 2026-11-03T144954238480 | 2 changed | quiet |
| 2026-11-03 | `remote/ai.oriiion/oriiion` | 2026-10-31T130257957666 -> 2026-11-03T144953382778 | 1 changed | quiet |
| 2026-11-03 | `remote/com.followontours/cricket-travel` | 2026-10-27T112342562636 -> 2026-11-03T144940045347 | 2 changed, 1 added | quiet |
| 2026-11-03 | `remote/io.github.ohad6k/viberaven-guides` | 2026-11-03T024220545027 -> 2026-11-03T144938537473 | 1 added | quiet |
| 2026-11-03 | `remote/com.viarapidaservices/mcp` | 2026-10-20T232809748186 -> 2026-11-03T144938619475 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-03T122645312258 -> 2026-11-03T144938447502 | 2 changed | quiet |
| 2026-11-03 | `remote/com.veritaset/mcp` | 2026-10-22T110206284820 -> 2026-11-03T144938181090 | 2 changed | quiet |
| 2026-11-03 | `remote/io.github.fmind/portfolio` | 2026-11-03T024241600863 -> 2026-11-03T144937495088 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.kkfir13/valuedge` | 2026-10-26T133655590387 -> 2026-11-03T144934398470 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.Tomalarrrr/cyclesite-mcp-server` | 2026-10-31T234853863408 -> 2026-11-03T144934781383 | 20 changed | quiet |
| 2026-11-03 | `remote/br.com.criptonoticias/noticias` | 2026-10-19T135224170881 -> 2026-11-03T144930141969 | 5 changed (every tool) | quiet |
| 2026-11-03 | `remote/no.apier/mcp` | 2026-10-31T234853873283 -> 2026-11-03T144925671603 | 17 changed, 1 added | quiet |
| 2026-11-03 | `remote/io.github.WattCoin-Org/wattcoin-mcp-server` | 2026-10-31T234921873343 -> 2026-11-03T144925655873 | 17 changed, 6 added, 5 removed (every tool) | quiet |
| 2026-11-03 | `remote/com.translayte/translayte` | 2026-11-02T163436735593 -> 2026-11-03T144916555124 | 9 changed (every tool) | quiet |
| 2026-11-03 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-03T122630438103 -> 2026-11-03T144915766951 | 3 changed | quiet |
| 2026-11-03 | `remote/io.github.cyanheads/worldbank-mcp-server` | 2026-10-19T135212310678 -> 2026-11-03T144914426624 | 5 changed | quiet |
| 2026-11-03 | `remote/com.roasexpert.tools/seo-audit` | 2026-10-27T112413458435 -> 2026-11-03T144911542058 | 1 added | review |
| 2026-11-03 | `remote/fyi.whatsnew/changelogs` | 2026-09-25T120548810600 -> 2026-11-03T144909612709 | 2 changed | quiet |
| 2026-11-03 | `remote/io.github.suprraz/webzum` | 2026-10-18T113416811180 -> 2026-11-03T144902244048 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.cyanheads/un-comtrade-mcp-server` | 2026-10-19T135446942996 -> 2026-11-03T144901114782 | 9 changed (every tool) | quiet |
| 2026-11-03 | `remote/link.morningbrief/weather` | 2026-10-26T133611586700 -> 2026-11-03T144857716082 | 3 changed, 1 added (every tool) | quiet |
| 2026-11-03 | `remote/ai.peerfoundry/typedpull` | 2026-11-02T163525861241 -> 2026-11-03T144857199226 | 3 changed | quiet |
| 2026-11-03 | `remote/io.github.marcoret74/semantic-geometry` | 2026-11-03T122656042786 -> 2026-11-03T144849758279 | 1 changed, 11 added | quiet |
| 2026-11-03 | `remote/org.verifiedhandles/verified-handles` | 2026-10-28T212410560427 -> 2026-11-03T144848949743 | 2 changed | quiet |
| 2026-11-03 | `remote/com.textforagents/scheduled-agent-outcome-verification` | 2026-10-26T133608610709 -> 2026-11-03T144847075417 | 8 changed (every tool) | quiet |
| 2026-11-03 | `remote/io.github.tidydata-dev/tidydata` | 2026-10-19T135427666943 -> 2026-11-03T144836111177 | 2 added | quiet |
| 2026-11-03 | `remote/dev.tanod/ml` | 2026-10-29T153807401741 -> 2026-11-03T144836435474 | 1 changed | quiet |
| 2026-11-03 | `remote/dev.tanod/finance` | 2026-10-25T102412017631 -> 2026-11-03T144836223659 | 2 changed, 1 added | quiet |
| 2026-11-03 | `remote/media.thecoop/the-coop` | 2026-10-30T132908870763 -> 2026-11-03T144830834317 | 2 added | quiet |
| 2026-11-03 | `remote/io.github.emilingemarkarlsson/bilkalkylen` | 2026-10-26T133745344481 -> 2026-11-03T144828778334 | 4 changed, 1 added | quiet |
| 2026-11-03 | `remote/io.github.snenenenenenene/transita-mcp-server` | 2026-10-27T112300111736 -> 2026-11-03T144825033726 | 2 changed, 4 added | quiet |
| 2026-11-03 | `remote/com.supercatch/supercatch` | 2026-11-02T163339036529 -> 2026-11-03T144824537334 | 2 added | quiet |
| 2026-11-03 | `remote/info.stride/stride` | 2026-10-17T060321096158 -> 2026-11-03T144818952370 | 2 added | quiet |
| 2026-11-03 | `remote/dev.tanod/web` | 2026-11-02T163443945117 -> 2026-11-03T144818859212 | 3 changed | quiet |
| 2026-11-03 | `remote/dev.tanod/text` | 2026-11-02T163444299978 -> 2026-11-03T144819032634 | 2 changed | quiet |
| 2026-11-03 | `remote/dev.tanod/security` | 2026-10-28T132944829007 -> 2026-11-03T144818779135 | 4 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 45879 substantive, 27155 that changed only numbers (a catalogue counter ticking, a date), 804 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 41415 | 15875 | 25540 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1245 | 1245 | 0 | 0 |
| `caseyjhand.com` | 329 | 329 | 0 | 0 |
| `sistaminuten.se` | 190 | 6 | 0 | 184 |
| `afbudsrejser.dk` | 189 | 6 | 0 | 183 |
| `akkilahdot.fi` | 189 | 6 | 0 | 183 |
| `restplass.no` | 189 | 6 | 0 | 183 |
| `socialloop.ai` | 182 | 182 | 0 | 0 |
| `remoshift.com` | 159 | 12 | 147 | 0 |
| `revmesh2074.workers.dev` | 146 | 128 | 18 | 0 |
| `fundinglandscape.com` | 145 | 89 | 56 | 0 |
| 7274 other operators | 27119 | 25654 | 1394 | 71 |
