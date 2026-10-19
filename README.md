# MCP server tool changes

Last change observed 2026-10-19T13:58:58+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

34791 changes to a tool definition: 1387 npm releases (1141 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 33404 readings of hosted servers that found their tools changed; 2145 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-19 | `remote/com.starcovery/mcp` | 2026-10-18T190051293112 -> 2026-10-19T135859547205 | 3 changed | quiet |
| 2026-10-19 | `remote/at.schitterhof.www/camping` | 2026-10-17T060514053983 -> 2026-10-19T135857665207 | 2 changed | quiet |
| 2026-10-19 | `remote/no.restplass/travel-search` | 2026-10-19T052440777376 -> 2026-10-19T135856026355 | 1 changed | quiet |
| 2026-10-19 | `remote/be.lexgo/jobs` | 2026-09-23T163136247097 -> 2026-10-19T135846617828 | 1 changed | quiet |
| 2026-10-19 | `remote/com.grokbotwiki.www/grok-bot-wiki` | 2026-10-06T110318655573 -> 2026-10-19T135840722337 | 3 added | quiet |
| 2026-10-19 | `remote/io.github.oaleviola/arroway` | 2026-10-17T060422595894 -> 2026-10-19T135823377411 | 1 removed | quiet |
| 2026-10-19 | `remote/dk.afbudsrejser/travel-search` | 2026-10-19T052433173313 -> 2026-10-19T135821898992 | 1 changed | quiet |
| 2026-10-19 | `remote/com.wizeb/ai-native-index` | 2026-10-17T070441620197 -> 2026-10-19T135816728439 | 2 changed, 3 added | quiet |
| 2026-10-19 | `remote/me.walalook/tools.9` | 2026-10-17T060411614171 -> 2026-10-19T135806817185 | 1 added, 1 removed | quiet |
| 2026-10-19 | `remote/me.walalook/tools.7` | 2026-10-17T060412132663 -> 2026-10-19T135806788583 | 1 added, 1 removed | quiet |
| 2026-10-19 | `remote/me.walalook/tools.11` | 2026-10-17T060412246477 -> 2026-10-19T135807040507 | 1 added, 1 removed | quiet |
| 2026-10-19 | `remote/io.github.VoiceScapee/voicescape` | 2026-10-10T202123807678 -> 2026-10-19T135803006551 | 1 added | review |
| 2026-10-19 | `remote/com.vidreno/mcp` | 2026-10-18T113327591155 -> 2026-10-19T135800054010 | 4 changed | quiet |
| 2026-10-19 | `remote/io.github.taux-io/twse-mcp` | 2026-10-18T113316230547 -> 2026-10-19T135742377493 | 1 changed, 1 added | quiet |
| 2026-10-19 | `remote/com.tulugar/tulugar` | 2026-09-23T163053712763 -> 2026-10-19T135740725590 | 1 changed | quiet |
| 2026-10-19 | `remote/io.github.leshchenko1979/fast-mcp-telegram` | 2026-10-02T072056526680 -> 2026-10-19T135716500319 | 3 changed | quiet |
| 2026-10-19 | `remote/com.szymonpaluch/mcp` | 2026-10-17T060328604812 -> 2026-10-19T135702266639 | 1 changed | quiet |
| 2026-10-19 | `remote/fr.synergieloc/immobilier` | 2026-09-29T061656484421 -> 2026-10-19T135703094744 | 2 changed | quiet |
| 2026-10-19 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-13T235704476951 -> 2026-10-19T135644754708 | 10 changed | quiet |
| 2026-10-19 | `remote/at.space-core/game` | 2026-10-19T052419992262 -> 2026-10-19T135644218670 | 1 changed | quiet |
| 2026-10-19 | `remote/com.servghost/servghost` | 2026-09-23T163003328128 -> 2026-10-19T135628726707 | 1 changed | quiet |
| 2026-10-19 | `remote/io.github.seekdaseek/agentfeed` | 2026-10-18T190124898432 -> 2026-10-19T135617673083 | 4 changed | quiet |
| 2026-10-19 | `remote/app.seatsherpa/rides` | 2026-10-18T113204839709 -> 2026-10-19T135616002861 | 3 changed | quiet |
| 2026-10-19 | `remote/com.premierletters/mcp` | 2026-10-17T055948667777 -> 2026-10-19T135602455984 | 2 changed, 4 added | review |
| 2026-10-19 | `remote/io.github.wygogogo19/robotbase-mcp` | 2026-10-19T052413155261 -> 2026-10-19T135603273876 | 66 changed, 6 added (every tool) | review |
| 2026-10-19 | `remote/com.jobcrawls/connector` | 2026-10-18T113312264238 -> 2026-10-19T135554948012 | 1 changed | quiet |
| 2026-10-19 | `remote/com.immersivecommons/floor10` | 2026-10-18T051404625130 -> 2026-10-19T135553806253 | 3 added | quiet |
| 2026-10-19 | `remote/com.hillsignal/hillsignalapp` | 2026-09-24T120502779678 -> 2026-10-19T135552363017 | 1 changed, 1 added | quiet |
| 2026-10-19 | `remote/co.rahuldsarker/growth-tools` | 2026-10-07T213822154421 -> 2026-10-19T135538648072 | 1 added | quiet |
| 2026-10-19 | `remote/ua.com.quintadb/mcp` | 2026-10-17T224351571680 -> 2026-10-19T135538307579 | 2 changed | quiet |
| 2026-10-19 | `remote/fi.akkilahdot/travel-search` | 2026-10-19T052500241961 -> 2026-10-19T135529418414 | 1 changed | quiet |
| 2026-10-19 | `remote/io.github.vanakenj45/x402-agent-api` | 2026-10-17T055626262103 -> 2026-10-19T135522929643 | 2 added | review |
| 2026-10-19 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-10-18T190023013297 -> 2026-10-19T135524331149 | 27 changed, 18 added (every tool) | review |
| 2026-10-19 | `remote/io.github.Fizzl13/presign-guard` | 2026-10-18T125032594656 -> 2026-10-19T135522968489 | 3 changed | quiet |
| 2026-10-19 | `remote/com.whichtrim/vehicle-records` | 2026-09-28T073159336655 -> 2026-10-19T135519444989 | 1 added | quiet |
| 2026-10-19 | `remote/io.taifoon/coordination-layer.1` | 2026-10-19T052423545284 -> 2026-10-19T135517924359 | 2 changed | review |
| 2026-10-19 | `remote/se.sistaminuten/travel-search` | 2026-10-19T052423432371 -> 2026-10-19T135513736786 | 1 changed | quiet |
| 2026-10-19 | `remote/com.warmthengine/observatory` | 2026-10-09T153621617096 -> 2026-10-19T135510074033 | 6 changed | quiet |
| 2026-10-19 | `remote/me.walalook/tools.5` | 2026-10-17T055909057209 -> 2026-10-19T135508697418 | 1 added | quiet |
| 2026-10-19 | `remote/com.vouchernaut/deals` | 2026-10-17T055906867742 -> 2026-10-19T135506736097 | 4 added | quiet |
| 2026-10-19 | `remote/com.oxfordledge/oxford-ledge` | 2026-10-17T055613858804 -> 2026-10-19T135506696864 | 56 changed, 2 removed | quiet |
| 2026-10-19 | `remote/ai.partsgraph/catalog` | 2026-09-23T162911341497 -> 2026-10-19T135454893835 | 9 changed | quiet |
| 2026-10-19 | `remote/xyz.rubenayla.partle/marketplace` | 2026-09-23T162911839726 -> 2026-10-19T135455850033 | 9 added | quiet |
| 2026-10-19 | `remote/io.github.cloakmaster/pact0` | 2026-10-18T190003985199 -> 2026-10-19T135451528107 | 1 added | quiet |
| 2026-10-19 | `remote/io.github.taskin-ai/trytaskin` | 2026-09-23T162921087406 -> 2026-10-19T135445224797 | 3 changed, 1 added | quiet |
| 2026-10-19 | `remote/io.github.nimitt-IN/india-cyber-regulations` | 2026-09-30T152245919357 -> 2026-10-19T135442108402 | 1 added | quiet |
| 2026-10-19 | `remote/com.autoridaddigital.www/geo` | 2026-10-03T120104705905 -> 2026-10-19T135440788112 | 1 changed | quiet |
| 2026-10-19 | `remote/io.github.Schoasch/backtesting-arena` | 2026-10-17T055847361273 -> 2026-10-19T135437667654 | 2 changed | quiet |
| 2026-10-19 | `remote/io.github.cyanheads/noaa-climate-mcp-server` | 2026-09-23T162854157251 -> 2026-10-19T135427218880 | 8 changed | quiet |
| 2026-10-19 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-19T052419231190 -> 2026-10-19T135428124281 | 1 changed | quiet |
| 2026-10-19 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-18T190058333861 -> 2026-10-19T135420286181 | 1 changed | quiet |
| 2026-10-19 | `remote/me.walalook/tools.8` | 2026-10-17T055538965411 -> 2026-10-19T135417412585 | 1 added, 1 removed | quiet |
| 2026-10-19 | `remote/com.struxurenorcal.walnbot/struxure-knowledge-base` | 2026-09-28T142257123213 -> 2026-10-19T135416741759 | 1 added | quiet |
| 2026-10-19 | `remote/me.walalook/tools.6` | 2026-10-17T055538499481 -> 2026-10-19T135415726919 | 1 removed | quiet |
| 2026-10-19 | `remote/me.walalook/tools.4` | 2026-10-17T055538206739 -> 2026-10-19T135416118443 | 1 added, 1 removed | quiet |
| 2026-10-19 | `remote/me.walalook/tools.12` | 2026-10-17T055538852187 -> 2026-10-19T135415562211 | 1 added, 6 removed | quiet |
| 2026-10-19 | `remote/com.synapticrelay/board.1` | 2026-10-03T192912659794 -> 2026-10-19T135410317052 | 3 changed (every tool) | quiet |
| 2026-10-19 | `remote/org.verifiedhandles/verified-handles` | 2026-10-17T073315656861 -> 2026-10-19T135405957496 | 2 changed | quiet |
| 2026-10-19 | `remote/app.turnale/turnale` | 2026-09-23T162823966012 -> 2026-10-19T135344878166 | 6 changed | quiet |
| 2026-10-19 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-19T052441243839 -> 2026-10-19T135343178880 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 23169 substantive, 11132 that changed only numbers (a catalogue counter ticking, a date), 490 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 17656 | 7224 | 10432 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 166 | 166 | 0 | 0 |
| `sistaminuten.se` | 118 | 4 | 0 | 114 |
| `afbudsrejser.dk` | 117 | 4 | 0 | 113 |
| `akkilahdot.fi` | 117 | 4 | 0 | 113 |
| `restplass.no` | 117 | 4 | 0 | 113 |
| `socialloop.ai` | 114 | 114 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `remoshift.com` | 88 | 6 | 82 | 0 |
| `fundinglandscape.com` | 87 | 54 | 33 | 0 |
| 4252 other operators | 13120 | 12498 | 585 | 37 |
