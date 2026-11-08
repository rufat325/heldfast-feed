# MCP server tool changes

Last change observed 2026-11-08T00:01:30+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

82658 changes to a tool definition: 3503 npm releases (3257 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 79155 readings of hosted servers that found their tools changed; 3559 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-08 | `remote/no.restplass/travel-search` | 2026-11-07T203340906326 -> 2026-11-08T000131943493 | 1 changed | quiet |
| 2026-11-08 | `remote/com.synthexforge.x402/paid-agent-services` | 2026-11-07T203345091207 -> 2026-11-08T000131892422 | 3 changed, 4 added, 205 removed (every tool) | quiet |
| 2026-11-08 | `remote/studio.gradients/mcp` | 2026-11-07T203340545060 -> 2026-11-08T000130786620 | 1 changed | quiet |
| 2026-11-08 | `remote/fi.akkilahdot/travel-search` | 2026-11-07T203338376499 -> 2026-11-08T000129808124 | 1 changed | quiet |
| 2026-11-08 | `remote/dk.afbudsrejser/travel-search` | 2026-11-07T203337740724 -> 2026-11-08T000129376952 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-07T203337532534 -> 2026-11-08T000129441517 | 3 changed | quiet |
| 2026-11-08 | `remote/ai.trydock/dock` | 2026-11-07T203336100139 -> 2026-11-08T000127917588 | 1 changed, 1 added | quiet |
| 2026-11-08 | `remote/fyi.toothache/dentists` | 2026-11-06T072805118934 -> 2026-11-08T000127551134 | 1 changed | quiet |
| 2026-11-08 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-11-07T063949379960 -> 2026-11-08T000126778932 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-07T203332189313 -> 2026-11-08T000124949271 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.siowweekoon/agent-companion` | 2026-11-07T133515198761 -> 2026-11-08T000126604858 | 3 changed | quiet |
| 2026-11-08 | `remote/com.tetheredtrust/tethered-trust` | 2026-11-07T203334019691 -> 2026-11-08T000125816986 | 3 added | review |
| 2026-11-08 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-07T203332044872 -> 2026-11-08T000126047972 | 1 changed, 8 added | review |
| 2026-11-08 | `remote/com.slashtel/slashtel` | 2026-11-07T203330237092 -> 2026-11-08T000123651802 | 1 added | quiet |
| 2026-11-08 | `remote/io.github.leewenjie/oxaide` | 2026-11-07T133038874079 -> 2026-11-08T000127485141 | 4 changed | quiet |
| 2026-11-08 | `remote/se.sistaminuten/travel-search` | 2026-11-07T203404724228 -> 2026-11-08T000119274818 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.umairalisadaqat/weinc` | 2026-11-07T203321099375 -> 2026-11-08T000119394466 | 2 changed | quiet |
| 2026-11-08 | `remote/com.multicinesortega/cartelera` | 2026-11-07T063958539804 -> 2026-11-08T000118786970 | 1 changed | quiet |
| 2026-11-08 | `remote/dev.toolrail/mcp` | 2026-11-07T063958885319 -> 2026-11-08T000114043808 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.cryptoconspiracy/vurto-swap` | 2026-11-07T203352729796 -> 2026-11-08T000113264734 | 6 changed | quiet |
| 2026-11-08 | `remote/com.thefomite/fomite` | 2026-11-07T063958959344 -> 2026-11-08T000114328617 | 1 changed | quiet |
| 2026-11-08 | `remote/com.squirrelscan/squirrelscan` | 2026-11-07T063939339799 -> 2026-11-08T000114891372 | 4 changed | quiet |
| 2026-11-08 | `remote/com.kernelcad/kernelcad` | 2026-11-07T203312123406 -> 2026-11-08T000110793021 | 1 changed | quiet |
| 2026-11-08 | `remote/pl.finwire/data` | 2026-11-07T203345248780 -> 2026-11-08T000110736464 | 8 changed | quiet |
| 2026-11-08 | `remote/org.r3js/r3` | 2026-11-07T203317018375 -> 2026-11-08T000110641952 | 2 changed | quiet |
| 2026-11-08 | `remote/org.qrvote/qrvote.1` | 2026-11-06T144136608627 -> 2026-11-08T000109460180 | 3 changed | quiet |
| 2026-11-08 | `remote/es.proceres/proceres` | 2026-11-07T133447784039 -> 2026-11-08T000110862251 | 11 changed | quiet |
| 2026-11-08 | `remote/com.predictionmarketspicks/quant` | 2026-11-06T144419278313 -> 2026-11-08T000109784406 | 1 changed | quiet |
| 2026-11-08 | `remote/com.jobmojito/jobmojito` | 2026-11-07T203310499291 -> 2026-11-08T000110041046 | 2 changed | quiet |
| 2026-11-08 | `remote/tech.kaiku/kaiku.1` | 2026-11-07T203310138406 -> 2026-11-08T000109555366 | 1 changed | quiet |
| 2026-11-08 | `remote/dev.cloro/cloro` | 2026-11-07T132842521208 -> 2026-11-08T000106675427 | 1 added | quiet |
| 2026-11-08 | `remote/com.thefilmradar/filmlab` | 2026-11-07T203305458206 -> 2026-11-08T000106858911 | 3 changed, 1 added | quiet |
| 2026-11-08 | `remote/ai.dotsy/mcp` | 2026-11-06T144005711407 -> 2026-11-08T000107135832 | 2 changed | quiet |
| 2026-11-08 | `remote/io.github.si-imtiaz/leadquasar` | 2026-11-07T151307969470 -> 2026-11-08T000106522081 | 1 changed | quiet |
| 2026-11-08 | `remote/co.ainumbers/tools` | 2026-11-07T063926237753 -> 2026-11-08T000104697716 | 1 changed | quiet |
| 2026-11-08 | `remote/com.kushbitx/agentproof` | 2026-11-07T203301957979 -> 2026-11-08T000104460432 | 1 changed | quiet |
| 2026-11-08 | `remote/net.hotelrefund/price-tracker` | 2026-11-07T063936568328 -> 2026-11-08T000102954861 | 1 changed | quiet |
| 2026-11-08 | `remote/me.freehire/freehire` | 2026-11-06T072754266951 -> 2026-11-08T000101561396 | 4 changed | quiet |
| 2026-11-08 | `remote/app.vercel.fork-for-agents/fork` | 2026-11-07T203257558960 -> 2026-11-08T000101201893 | 1 changed | quiet |
| 2026-11-08 | `remote/io.alterlab/mcp-server` | 2026-11-06T143949530331 -> 2026-11-08T000059687186 | 5 added | quiet |
| 2026-11-08 | `remote/com.clypmint/clypmint` | 2026-11-07T203253782193 -> 2026-11-08T000057642510 | 1 changed, 3 added | quiet |
| 2026-11-08 | `remote/com.6ix/mcp` | 2026-11-06T072738222585 -> 2026-11-08T000058415811 | 1 changed | quiet |
| 2026-11-08 | `remote/app.chopit/chopit` | 2026-11-07T132113095857 -> 2026-11-08T000057137168 | 4 changed | quiet |
| 2026-11-08 | `remote/io.github.whiteknightonhorse/apibase` | 2026-11-07T063924824417 -> 2026-11-08T000055214363 | 4 removed | quiet |
| 2026-11-08 | `remote/io.github.LuxAlgo/luxalgo-mcp-server` | 2026-11-07T203328132980 -> 2026-11-08T000054536180 | 6 added | quiet |
| 2026-11-08 | `remote/io.github.stophydotdev/mcp` | 2026-11-07T203250403773 -> 2026-11-08T000053911909 | 4 changed | quiet |
| 2026-11-08 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-11-07T203250984504 -> 2026-11-08T000053535754 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt.2` | 2026-11-07T063929805343 -> 2026-11-08T000051353608 | 1 changed | quiet |
| 2026-11-08 | `remote/com.cvember/cvember` | 2026-11-07T132939410335 -> 2026-11-08T000051651698 | 2 changed | quiet |
| 2026-11-08 | `remote/io.github.getDynamoi/dynamoi` | 2026-11-07T063930115365 -> 2026-11-08T000052876378 | 1 changed, 2 added | quiet |
| 2026-11-08 | `remote/com.dockettrail/dockettrail` | 2026-11-07T063928816538 -> 2026-11-08T000050992681 | 5 changed (every tool) | quiet |
| 2026-11-08 | `remote/io.github.jrpool/kilotest` | 2026-11-07T132727144014 -> 2026-11-08T000048503374 | 9 changed, 2 added, 4 removed (every tool) | quiet |
| 2026-11-08 | `remote/com.holidayready/travel-insurance-quotes` | 2026-11-07T063908314193 -> 2026-11-08T000047306824 | 1 changed | quiet |
| 2026-11-08 | `remote/ai.betslipdoctor/mcp` | 2026-11-07T203242616917 -> 2026-11-08T000045903741 | 2 changed | quiet |
| 2026-11-08 | `remote/dev.dexra/dexra` | 2026-11-07T131759861412 -> 2026-11-08T000046815160 | 1 added | quiet |
| 2026-11-08 | `remote/org.feegate/marketplace` | 2026-11-07T203300112225 -> 2026-11-08T000044749009 | 15 added, 14 removed | quiet |
| 2026-11-08 | `remote/io.github.fivebar-xyz/fivebar` | 2026-11-07T063927720327 -> 2026-11-08T000043360879 | 1 changed, 3 added | quiet |
| 2026-11-08 | `remote/com.a2a2p/a2a2p` | 2026-11-07T203239056133 -> 2026-11-08T000043605670 | 2 changed | quiet |
| 2026-11-08 | `remote/ai.analyticslegends/sap-analytics` | 2026-11-06T142703247066 -> 2026-11-08T000043860963 | 13 changed | quiet |
| 2026-11-08 | `remote/io.github.Vortx-AI/emem` | 2026-11-06T143502600199 -> 2026-11-08T000042727665 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 50663 substantive, 31105 that changed only numbers (a catalogue counter ticking, a date), 890 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 45119 | 15889 | 29230 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1723 | 1723 | 0 | 0 |
| `caseyjhand.com` | 354 | 354 | 0 | 0 |
| `sistaminuten.se` | 209 | 6 | 0 | 203 |
| `afbudsrejser.dk` | 208 | 6 | 0 | 202 |
| `akkilahdot.fi` | 208 | 6 | 0 | 202 |
| `restplass.no` | 208 | 6 | 0 | 202 |
| `socialloop.ai` | 200 | 200 | 0 | 0 |
| `revmesh2074.workers.dev` | 190 | 167 | 23 | 0 |
| `civai.co` | 187 | 187 | 0 | 0 |
| `modevc.com` | 174 | 174 | 0 | 0 |
| 7918 other operators | 31537 | 29604 | 1852 | 81 |
