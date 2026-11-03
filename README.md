# MCP server tool changes

Last change observed 2026-11-03T12:27:57+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

71422 changes to a tool definition: 2981 npm releases (2735 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 68441 readings of hosted servers that found their tools changed; 3239 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-03 | `remote/io.github.Veniwol-Li-Lambd/lilambd-data` | 2026-11-02T163642875333 -> 2026-11-03T122805107100 | 20 added | review |
| 2026-11-03 | `remote/no.restplass/travel-search` | 2026-11-03T024229712582 -> 2026-11-03T122754833871 | 1 changed | quiet |
| 2026-11-03 | `remote/dk.afbudsrejser/travel-search` | 2026-11-03T024223725276 -> 2026-11-03T122747958603 | 1 changed | quiet |
| 2026-11-03 | `remote/is.envelop.unisafe/insight` | 2026-11-01T135232440576 -> 2026-11-03T122743668130 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.Billibo6/unlockpulse` | 2026-11-02T163452926035 -> 2026-11-03T122742887332 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.CWNApps/trust-gate-mcp` | 2026-11-02T163438797279 -> 2026-11-03T122742341745 | 10 changed | quiet |
| 2026-11-03 | `remote/fyi.toothache/dentists` | 2026-11-02T163431993750 -> 2026-11-03T122741065889 | 1 changed | quiet |
| 2026-11-03 | `remote/now.spacejobs/spacejobs-now` | 2026-11-02T163318183686 -> 2026-11-03T122736266134 | 1 changed | quiet |
| 2026-11-03 | `remote/com.socialnetworkforaiagents/agent-socials` | 2026-11-01T135123959890 -> 2026-11-03T122735167283 | 3 changed | quiet |
| 2026-11-03 | `remote/app.seatsherpa/rides` | 2026-11-02T163239958575 -> 2026-11-03T122734816597 | 3 changed | quiet |
| 2026-11-03 | `remote/re.rundata/temps-reel` | 2026-11-03T024209720339 -> 2026-11-03T122733156126 | 2 changed | quiet |
| 2026-11-03 | `remote/io.github.opennodes-io/opennodes` | 2026-11-02T185353038467 -> 2026-11-03T122731697082 | 1 changed, 1 added | quiet |
| 2026-11-03 | `remote/dev.pressmark/pressmark` | 2026-11-02T163133690171 -> 2026-11-03T122727572975 | 2 changed | quiet |
| 2026-11-03 | `remote/com.partstable/partstable` | 2026-11-02T065434524163 -> 2026-11-03T122725209586 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.cyanheads/openfoodfacts-mcp-server` | 2026-11-01T205304605763 -> 2026-11-03T122723926699 | 3 changed | quiet |
| 2026-11-03 | `remote/com.myndock/observatory` | 2026-11-03T024158458919 -> 2026-11-03T122719992245 | 3 added | quiet |
| 2026-11-03 | `remote/io.github.OsakaSaul/mentionfox` | 2026-11-02T065432457763 -> 2026-11-03T122721025023 | 10 changed (every tool) | quiet |
| 2026-11-03 | `remote/com.turbonotify/whatsapp` | 2026-11-02T162931631298 -> 2026-11-03T122716721499 | 19 changed | quiet |
| 2026-11-03 | `remote/io.github.smarterweather/weather` | 2026-11-03T024151339471 -> 2026-11-03T122713291707 | 1 changed | quiet |
| 2026-11-03 | `remote/ai.signal8/mcp` | 2026-11-02T185329817304 -> 2026-11-03T122712828913 | 2 changed | quiet |
| 2026-11-03 | `remote/com.liliphant.mcp/mcp` | 2026-11-02T162808268647 -> 2026-11-03T122712202817 | 2 changed | quiet |
| 2026-11-03 | `remote/io.taifoon/coordination-layer.1` | 2026-11-03T024316718049 -> 2026-11-03T122706179933 | 1 changed | review |
| 2026-11-03 | `remote/se.sistaminuten/travel-search` | 2026-11-03T024315532036 -> 2026-11-03T122705596116 | 1 changed | quiet |
| 2026-11-03 | `remote/com.f1ow/f1ow.1` | 2026-11-02T162728518703 -> 2026-11-03T122706236055 | 1 changed | quiet |
| 2026-11-03 | `remote/so.darwin/darwin` | 2026-11-02T162715313833 -> 2026-11-03T122704946713 | 6 changed | quiet |
| 2026-11-03 | `remote/co.deadbrands/arena` | 2026-11-03T024142606870 -> 2026-11-03T122704453973 | 3 changed, 1 added | quiet |
| 2026-11-03 | `remote/io.github.JcJamet/ia-qa-security` | 2026-11-03T024313609110 -> 2026-11-03T122704181232 | 2 changed | quiet |
| 2026-11-03 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-11-03T024313983143 -> 2026-11-03T122703733460 | 2 changed | quiet |
| 2026-11-03 | `remote/io.github.JcJamet/ia-qa-eval` | 2026-11-03T024313677875 -> 2026-11-03T122703635005 | 2 changed | quiet |
| 2026-11-03 | `remote/com.buscatucamping/rutas` | 2026-11-02T163404132370 -> 2026-11-03T122700517066 | 1 changed | quiet |
| 2026-11-03 | `remote/com.agentbrokerindex/agentbroker-index` | 2026-11-02T162624545484 -> 2026-11-03T122659756097 | 2 changed | quiet |
| 2026-11-03 | `remote/com.wondaverse/agent-space` | 2026-11-02T163347212050 -> 2026-11-03T122658043391 | 4 changed | quiet |
| 2026-11-03 | `remote/com.anchorterminal/anchor-terminal` | 2026-11-03T024309018113 -> 2026-11-03T122659446355 | 1 changed | quiet |
| 2026-11-03 | `remote/com.6ix/mcp` | 2026-11-03T024137933338 -> 2026-11-03T122658730498 | 3 changed, 2 added | quiet |
| 2026-11-03 | `remote/com.veyrul/media-hub` | 2026-11-03T024303583097 -> 2026-11-03T122654781138 | 2 changed | quiet |
| 2026-11-03 | `remote/io.github.marcoret74/semantic-geometry` | 2026-11-03T024311373745 -> 2026-11-03T122656042786 | 5 added | quiet |
| 2026-11-03 | `remote/xyz.urbangametheory/urban-game-theory` | 2026-11-02T065453036995 -> 2026-11-03T122653957679 | 2 changed | quiet |
| 2026-11-03 | `remote/io.github.grupoanesthy-spec/agent-transaction-trust` | 2026-11-02T162512877948 -> 2026-11-03T122651475922 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.babo072/ktourinfo` | 2026-11-02T162528046091 -> 2026-11-03T122653169445 | 1 changed | quiet |
| 2026-11-03 | `remote/xyz.x402helper/mcp` | 2026-11-02T163946891094 -> 2026-11-03T122651596175 | 3 changed, 2 added, 1 removed (every tool) | review |
| 2026-11-03 | `remote/uk.co.tpsclear/tpsclear` | 2026-11-02T163244208599 -> 2026-11-03T122650511857 | 2 added | quiet |
| 2026-11-03 | `remote/dev.zambo/zambo` | 2026-11-02T163951596118 -> 2026-11-03T122650437288 | 2 changed | quiet |
| 2026-11-03 | `remote/com.timeofmeeting/time-of-meeting` | 2026-11-02T065446623276 -> 2026-11-03T122647780679 | 15 changed (every tool) | quiet |
| 2026-11-03 | `remote/io.github.sean0007/free-agent-tools` | 2026-11-03T024125327373 -> 2026-11-03T122644237514 | 1 added | quiet |
| 2026-11-03 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-03T024242849859 -> 2026-11-03T122645312258 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.JcJamet/ia-qa-data` | 2026-11-02T163901736706 -> 2026-11-03T122645242614 | 2 changed | quiet |
| 2026-11-03 | `remote/dev.tanod/tanod` | 2026-11-03T024253947752 -> 2026-11-03T122646834996 | 3 changed | quiet |
| 2026-11-03 | `remote/dev.tanod/agents` | 2026-11-02T163201465732 -> 2026-11-03T122645947780 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.theluckystrike/student-loan-repayment-assistance-plan-calculator-mcp` | 2026-11-02T163148707329 -> 2026-11-03T122643629415 | 1 changed | quiet |
| 2026-11-03 | `remote/com.shipshapedata/shipshape-data-docs` | 2026-11-02T163114882888 -> 2026-11-03T122641215703 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.imokokok/insight-oracle` | 2026-11-03T024311766228 -> 2026-11-03T122640788249 | 3 changed | quiet |
| 2026-11-03 | `remote/studio.gradients/mcp` | 2026-11-03T024308669092 -> 2026-11-03T122636936552 | 1 changed | quiet |
| 2026-11-03 | `remote/com.triremes/triremes` | 2026-11-03T024233962692 -> 2026-11-03T122637599546 | 2 changed | quiet |
| 2026-11-03 | `remote/io.github.cyanheads/eurostat-mcp-server` | 2026-11-01T134257386179 -> 2026-11-03T122636846926 | 6 changed | quiet |
| 2026-11-03 | `remote/io.github.EasyGerber/easygerber` | 2026-11-02T065455169815 -> 2026-11-03T122636076720 | 13 changed, 2 removed | quiet |
| 2026-11-03 | `remote/pl.finwire/data` | 2026-11-03T024242954080 -> 2026-11-03T122635974395 | 2 changed, 3 added | quiet |
| 2026-11-03 | `remote/fi.akkilahdot/travel-search` | 2026-11-03T024306840541 -> 2026-11-03T122635239739 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.seasonsagents-art/webaz` | 2026-11-02T163553895336 -> 2026-11-03T122633378009 | 1 changed | quiet |
| 2026-11-03 | `remote/com.mouseedge/mouseedge-skipper.1` | 2026-11-02T185357245721 -> 2026-11-03T122632645097 | 2 changed | quiet |
| 2026-11-03 | `remote/com.crm-connector/crm-connector` | 2026-11-02T162949896310 -> 2026-11-03T122633414898 | 5 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 45326 substantive, 25297 that changed only numbers (a catalogue counter ticking, a date), 799 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 39567 | 15869 | 23698 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1245 | 1245 | 0 | 0 |
| `caseyjhand.com` | 316 | 316 | 0 | 0 |
| `sistaminuten.se` | 189 | 6 | 0 | 183 |
| `afbudsrejser.dk` | 188 | 6 | 0 | 182 |
| `akkilahdot.fi` | 188 | 6 | 0 | 182 |
| `restplass.no` | 188 | 6 | 0 | 182 |
| `socialloop.ai` | 181 | 181 | 0 | 0 |
| `remoshift.com` | 158 | 12 | 146 | 0 |
| `revmesh2074.workers.dev` | 146 | 128 | 18 | 0 |
| `fundinglandscape.com` | 144 | 89 | 55 | 0 |
| 7160 other operators | 26571 | 25121 | 1380 | 70 |
