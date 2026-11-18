# MCP server tool changes

Last change observed 2026-11-18T17:41:34+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

114378 changes to a tool definition: 4625 npm releases (4379 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 109753 readings of hosted servers that found their tools changed; 4380 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-18 | `remote/se.sistaminuten/travel-search` | 2026-11-18T161739879370 -> 2026-11-18T174135518559 | 1 changed | quiet |
| 2026-11-18 | `remote/no.restplass/travel-search` | 2026-11-18T161846538908 -> 2026-11-18T174125494879 | 1 changed | quiet |
| 2026-11-18 | `remote/com.iscabox/iscabox` | 2026-11-18T135802444623 -> 2026-11-18T174125101160 | 4 changed | quiet |
| 2026-11-18 | `remote/io.github.rodriguem75/datarespublica` | 2026-11-16T163236877419 -> 2026-11-18T174118241960 | 11 changed (every tool) | quiet |
| 2026-11-18 | `remote/dk.afbudsrejser/travel-search` | 2026-11-18T161731882003 -> 2026-11-18T174115543642 | 1 changed | quiet |
| 2026-11-18 | `remote/io.github.ohad6k/viberaven-guides` | 2026-11-17T164817253190 -> 2026-11-18T174112342928 | 1 changed | quiet |
| 2026-11-18 | `remote/studio.gradients/mcp` | 2026-11-18T161942464492 -> 2026-11-18T174111579905 | 1 changed | quiet |
| 2026-11-18 | `remote/fi.akkilahdot/travel-search` | 2026-11-18T161908158357 -> 2026-11-18T174108600953 | 1 changed | quiet |
| 2026-11-18 | `remote/net.tnapplianceexchange/repair` | 2026-11-18T161444743419 -> 2026-11-18T174107106961 | 5 changed (every tool) | review |
| 2026-11-18 | `remote/fyi.toothache/dentists` | 2026-11-18T161554581687 -> 2026-11-18T174107741373 | 1 changed | quiet |
| 2026-11-18 | `remote/at.space-core/game` | 2026-11-18T135442492883 -> 2026-11-18T174057375086 | 1 changed | quiet |
| 2026-11-18 | `remote/io.github.Friezaaaa/smartfetch` | 2026-11-18T135429634167 -> 2026-11-18T174055494614 | 4 added | quiet |
| 2026-11-18 | `remote/io.github.mastercobeos/tlacuilo` | 2026-11-17T135627995054 -> 2026-11-18T174048654082 | 2 added | quiet |
| 2026-11-18 | `remote/com.registryverify/florida-sunbiz-business-kyb` | 2026-11-17T234314455526 -> 2026-11-18T174048886355 | 1 changed, 3 removed | quiet |
| 2026-11-18 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-18T135718279364 -> 2026-11-18T174050534229 | 1 changed | quiet |
| 2026-11-18 | `remote/io.github.dtajitdinov-aris/sphere-marketplace` | 2026-11-17T164637901165 -> 2026-11-18T174044236449 | 1 changed | quiet |
| 2026-11-18 | `remote/com.scribiz/mcp` | 2026-11-18T135355521672 -> 2026-11-18T174045378025 | 2 changed, 1 removed | quiet |
| 2026-11-18 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-18T135642605990 -> 2026-11-18T174040097622 | 1 changed | quiet |
| 2026-11-18 | `remote/io.github.codytodd-ui/pitchspark` | 2026-11-17T234306503629 -> 2026-11-18T174039795717 | 1 changed, 11 added | quiet |
| 2026-11-18 | `remote/finance.sifter/sifter` | 2026-11-17T164558243665 -> 2026-11-18T174036726642 | 1 changed | quiet |
| 2026-11-18 | `remote/dev.magmite/pay` | 2026-11-18T080145313781 -> 2026-11-18T174038172619 | 1 added | quiet |
| 2026-11-18 | `remote/no.pristavla/pristavla` | 2026-11-18T135419265335 -> 2026-11-18T174022742987 | 1 changed | quiet |
| 2026-11-18 | `remote/biz.valuein/mcp` | 2026-11-18T080132376855 -> 2026-11-18T174020838267 | 55 changed (every tool) | quiet |
| 2026-11-18 | `remote/io.github.rodriguem75/creditlabs` | 2026-11-16T163258504287 -> 2026-11-18T174018211706 | 5 changed | quiet |
| 2026-11-18 | `remote/io.github.dwiel/buyusbcables` | 2026-11-16T163251909166 -> 2026-11-18T174017488409 | 3 changed | quiet |
| 2026-11-18 | `remote/com.nabarfinder/nabarfinder` | 2026-11-17T164104610352 -> 2026-11-18T174012460758 | 1 changed | quiet |
| 2026-11-18 | `remote/org.myaiceo/myaiceo` | 2026-11-18T160926522347 -> 2026-11-18T174007880749 | 5 added | quiet |
| 2026-11-18 | `remote/io.github.faxforagents/faxforagents-mcp` | 2026-11-18T160549017120 -> 2026-11-18T174003387669 | 1 changed | quiet |
| 2026-11-18 | `remote/com.dimhour/catalog` | 2026-11-17T234239157617 -> 2026-11-18T174000489172 | 1 changed | quiet |
| 2026-11-18 | `remote/co.deadbrands/arena` | 2026-11-18T160531010127 -> 2026-11-18T173959880188 | 2 changed | quiet |
| 2026-11-18 | `remote/com.siemens.mcp/siemens` | 2026-11-18T080141197663 -> 2026-11-18T173959204092 | 1 changed | quiet |
| 2026-11-18 | `remote/io.github.RozoAI/checkout` | 2026-11-18T160656000070 -> 2026-11-18T173957779964 | 2 changed | review |
| 2026-11-18 | `remote/io.github.Vordium/vordium-mcp` | 2026-11-16T162454547789 -> 2026-11-18T173957738754 | 1 added | quiet |
| 2026-11-18 | `remote/com.toiseai/toise` | 2026-11-18T160737225119 -> 2026-11-18T173954387426 | 1 changed | quiet |
| 2026-11-18 | `remote/com.marketinque/launch-plan` | 2026-11-18T160416069670 -> 2026-11-18T173953646161 | 1 changed | quiet |
| 2026-11-18 | `remote/com.redstonemarkets/redstone` | 2026-11-18T135323727124 -> 2026-11-18T173944512053 | 5 changed | quiet |
| 2026-11-18 | `remote/com.gearhost/mcp` | 2026-11-18T080129291051 -> 2026-11-18T173948549228 | 3 added | quiet |
| 2026-11-18 | `remote/org.glolaw/glo-law` | 2026-11-18T160507796989 -> 2026-11-18T173939447264 | 1 changed | quiet |
| 2026-11-18 | `remote/app.apiguru/amazon-data` | 2026-11-16T185948293567 -> 2026-11-18T173938105165 | 11 changed | quiet |
| 2026-11-18 | `remote/io.github.daniel3303/equibles` | 2026-11-18T160447477554 -> 2026-11-18T173934992881 | 1 changed | quiet |
| 2026-11-18 | `remote/com.makehybrid/mcp` | 2026-11-18T134614009855 -> 2026-11-18T173934127468 | 1 changed | quiet |
| 2026-11-18 | `remote/com.othermindset/campus` | 2026-11-18T135138509632 -> 2026-11-18T173934142665 | 2 changed | quiet |
| 2026-11-18 | `remote/ai.bamf/bamf` | 2026-11-18T134805470208 -> 2026-11-18T173928997530 | 2 changed | quiet |
| 2026-11-18 | `remote/md.mostlyright/datasets` | 2026-11-16T162601690559 -> 2026-11-18T173926412711 | 3 changed | quiet |
| 2026-11-18 | `remote/io.github.industrial-platform-ai/research-brief` | 2026-11-18T160356316206 -> 2026-11-18T173926460739 | 1 changed | quiet |
| 2026-11-18 | `remote/com.360dialog/mcp` | 2026-11-18T160326811410 -> 2026-11-18T173925467324 | 80 removed | quiet |
| 2026-11-18 | `remote/com.danerolne/dane-rolne` | 2026-11-18T155827436264 -> 2026-11-18T173926460463 | 2 changed | quiet |
| 2026-11-18 | `remote/com.censusev/census` | 2026-11-17T234158379067 -> 2026-11-18T173913639815 | 2 changed, 1 added | quiet |
| 2026-11-18 | `remote/fr.ip73/ip73` | 2026-11-18T160150259623 -> 2026-11-18T173913861527 | 2 changed | quiet |
| 2026-11-18 | `remote/com.bookatu/docs` | 2026-11-16T161344100145 -> 2026-11-18T173910091010 | 1 changed | quiet |
| 2026-11-18 | `remote/io.github.MISHHF93/atlas-explain` | 2026-11-18T133809870016 -> 2026-11-18T173905924233 | 3 changed, 2 added | quiet |
| 2026-11-18 | `remote/io.iresolve.app/mcp-server` | 2026-11-17T162530798054 -> 2026-11-18T173901724601 | 3 changed (every tool) | review |
| 2026-11-18 | `remote/za.co.getlawed/sa-law` | 2026-11-17T163259301111 -> 2026-11-18T173902091045 | 1 changed | quiet |
| 2026-11-18 | `remote/io.github.MKagesawa/masadeals` | 2026-11-17T234229546428 -> 2026-11-18T173857588091 | 1 changed | quiet |
| 2026-11-18 | `remote/app.vercel.fork-for-agents/fork` | 2026-11-18T155935997042 -> 2026-11-18T173856582496 | 1 changed | quiet |
| 2026-11-18 | `remote/io.github.tettertotter/fundinglandscape` | 2026-11-18T134130534583 -> 2026-11-18T173856375084 | 15 changed | quiet |
| 2026-11-18 | `remote/ai.llpro/campus` | 2026-11-18T134540427599 -> 2026-11-18T173855291140 | 2 changed | quiet |
| 2026-11-18 | `remote/io.github.cammac-creator/ibanforge` | 2026-11-18T155105101042 -> 2026-11-18T173852958027 | 3 changed | quiet |
| 2026-11-18 | `remote/dev.goldprice/mcp` | 2026-11-18T133358093378 -> 2026-11-18T173854467079 | 1 changed | quiet |
| 2026-11-18 | `remote/io.github.bck-stack/sitecheck-agent-intel-dev` | 2026-11-18T133350707096 -> 2026-11-18T173851585077 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 72368 substantive, 40920 that changed only numbers (a catalogue counter ticking, a date), 1090 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 61815 | 23462 | 38353 | 0 |
| `a2awire.com` | 3240 | 3240 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 471 | 471 | 0 | 0 |
| `civai.co` | 368 | 368 | 0 | 0 |
| `modevc.com` | 349 | 349 | 0 | 0 |
| `revmesh2074.workers.dev` | 309 | 268 | 41 | 0 |
| `sistaminuten.se` | 254 | 6 | 0 | 248 |
| `afbudsrejser.dk` | 253 | 6 | 0 | 247 |
| `akkilahdot.fi` | 253 | 6 | 0 | 247 |
| `restplass.no` | 253 | 6 | 0 | 247 |
| `socialloop.ai` | 244 | 244 | 0 | 0 |
| 10187 other operators | 44228 | 41601 | 2526 | 101 |
