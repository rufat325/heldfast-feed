# MCP server tool changes

Last change observed 2026-11-18T16:20:58+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

114286 changes to a tool definition: 4625 npm releases (4379 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 109661 readings of hosted servers that found their tools changed; 4376 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-18 | `remote/com.sakuraweb.yamagishi/physics-papers` | 2026-10-31T130444386928 -> 2026-11-18T162101097480 | 1 changed | quiet |
| 2026-11-18 | `remote/io.github.racharmi/ohgiftplease` | 2026-11-15T142729206406 -> 2026-11-18T162005879765 | 1 changed | quiet |
| 2026-11-18 | `remote/studio.gradients/mcp` | 2026-11-18T135930413508 -> 2026-11-18T161942464492 | 1 changed | quiet |
| 2026-11-18 | `remote/com.codestringers/mcp` | 2026-11-15T142659794151 -> 2026-11-18T161918346707 | 1 changed | quiet |
| 2026-11-18 | `remote/fi.akkilahdot/travel-search` | 2026-11-18T135855704807 -> 2026-11-18T161908158357 | 1 changed | quiet |
| 2026-11-18 | `remote/io.github.Kali123411/k402` | 2026-09-23T160858830306 -> 2026-11-18T161850795139 | 2 changed, 8 added | quiet |
| 2026-11-18 | `remote/no.restplass/travel-search` | 2026-11-18T135849372869 -> 2026-11-18T161846538908 | 1 changed | quiet |
| 2026-11-18 | `remote/com.dharmikvibes/wellness` | 2026-10-26T133450004788 -> 2026-11-18T161840686958 | 2 changed, 4 added, 4 removed (every tool) | quiet |
| 2026-11-18 | `remote/io.github.openaccountants/openaccountants` | 2026-11-17T135653583656 -> 2026-11-18T161839592743 | 1 changed | quiet |
| 2026-11-18 | `remote/com.ticketfairy/ticket-fairy-public-events` | 2026-11-05T115506723251 -> 2026-11-18T161839373886 | 2 changed | quiet |
| 2026-11-18 | `remote/pl.obligacyjnyinwestor/obligacje-catalyst` | 2026-11-17T135654502099 -> 2026-11-18T161839973205 | 3 added | quiet |
| 2026-11-18 | `remote/cn.tandiu/data` | 2026-11-18T135915116496 -> 2026-11-18T161837962222 | 1 added | quiet |
| 2026-11-18 | `remote/com.easykmarket.vote/votebox-law` | 2026-11-16T123021338984 -> 2026-11-18T161823448055 | 1 changed | quiet |
| 2026-11-18 | `remote/com.juzpost/mcp` | 2026-11-16T122918880970 -> 2026-11-18T161817922803 | 3 changed | quiet |
| 2026-11-18 | `remote/com.theagentcolosseum/agent-colosseum` | 2026-11-17T164925033446 -> 2026-11-18T161748317963 | 6 changed (every tool) | quiet |
| 2026-11-18 | `remote/se.sistaminuten/travel-search` | 2026-11-18T135921819850 -> 2026-11-18T161739879370 | 1 changed | quiet |
| 2026-11-18 | `remote/io.github.paulieb89/uk-due-diligence-mcp` | 2026-10-29T104423602822 -> 2026-11-18T161731008476 | 3 changed | quiet |
| 2026-11-18 | `remote/dk.afbudsrejser/travel-search` | 2026-11-18T135721174456 -> 2026-11-18T161731882003 | 1 changed | quiet |
| 2026-11-18 | `remote/com.aguasto.www/tools` | 2026-11-18T135726784401 -> 2026-11-18T161722295035 | 1 changed | quiet |
| 2026-11-18 | `remote/app.wieldr/radar` | 2026-11-16T163211740870 -> 2026-11-18T161718928253 | 1 changed | quiet |
| 2026-11-18 | `remote/net.fatstack/registry` | 2026-11-18T135808060163 -> 2026-11-18T161658002349 | 1 added | quiet |
| 2026-11-18 | `remote/io.github.Voopa-Corp/render-check` | 2026-11-18T135658973064 -> 2026-11-18T161658548447 | 3 added | quiet |
| 2026-11-18 | `remote/io.github.paulieb89/uk-legal-mcp` | 2026-11-16T122806901283 -> 2026-11-18T161621313620 | 8 changed | quiet |
| 2026-11-18 | `remote/com.trustbaselab/rcb-data` | 2026-11-10T152909549307 -> 2026-11-18T161608343976 | 1 changed | quiet |
| 2026-11-18 | `remote/com.triremes/triremes` | 2026-11-18T135618860457 -> 2026-11-18T161603399228 | 1 changed | quiet |
| 2026-11-18 | `remote/fyi.toothache/dentists` | 2026-11-18T135605809357 -> 2026-11-18T161554581687 | 1 changed | quiet |
| 2026-11-18 | `remote/io.github.blink1217/quant-swarm` | 2026-11-18T135520578119 -> 2026-11-18T161502010290 | 1 removed | quiet |
| 2026-11-18 | `remote/net.tnapplianceexchange/repair` | 2026-11-07T133700500565 -> 2026-11-18T161444743419 | 1 changed | review |
| 2026-11-18 | `remote/io.github.SeoScoreAPI/seoscoreapi-mcp` | 2026-11-16T162831147444 -> 2026-11-18T161337394819 | 1 changed | quiet |
| 2026-11-18 | `remote/sk.rybarstvo/portal` | 2026-11-18T135335687829 -> 2026-11-18T161309492082 | 13 changed (every tool) | quiet |
| 2026-11-18 | `remote/io.github.Aruon-AI/reir` | 2026-11-17T164330074622 -> 2026-11-18T161302799724 | 2 changed | quiet |
| 2026-11-18 | `remote/dev.rackrates/ledger` | 2026-11-13T200729432063 -> 2026-11-18T161249411868 | 2 added | quiet |
| 2026-11-18 | `remote/io.rdapapi/rdap` | 2026-10-19T135206797727 -> 2026-11-18T161210995875 | 1 changed | quiet |
| 2026-11-18 | `remote/rent.quub/hotels` | 2026-11-18T135310493690 -> 2026-11-18T161154774507 | 1 changed | quiet |
| 2026-11-18 | `remote/com.eventualclimate/premium-lock` | 2026-11-17T234311074488 -> 2026-11-18T161149201772 | 3 changed | quiet |
| 2026-11-18 | `remote/fr.pausila/mcp` | 2026-11-17T135626428206 -> 2026-11-18T161139034083 | 2 changed | quiet |
| 2026-11-18 | `remote/io.github.farenberglord-star/orb-studio` | 2026-11-18T080119892352 -> 2026-11-18T161116946918 | 1 added | quiet |
| 2026-11-18 | `remote/com.offladder/offladder` | 2026-11-17T135620714659 -> 2026-11-18T161112177628 | 1 changed | quiet |
| 2026-11-18 | `remote/com.crm-connector/crm-connector` | 2026-11-18T135230901421 -> 2026-11-18T161103520407 | 1 changed | quiet |
| 2026-11-18 | `remote/io.github.Fractal-Neurons/pacta` | 2026-11-18T135335657642 -> 2026-11-18T161047299553 | 1 changed | quiet |
| 2026-11-18 | `remote/br.com.omofi/mofi` | 2026-11-09T165821008638 -> 2026-11-18T161040416847 | 5 changed | quiet |
| 2026-11-18 | `remote/com.openforallofus/agora` | 2026-10-06T105941275682 -> 2026-11-18T160929084546 | 2 changed | quiet |
| 2026-11-18 | `remote/com.offthefloornurse/nurse-jobs` | 2026-11-09T165715036675 -> 2026-11-18T160918253213 | 4 changed (every tool) | quiet |
| 2026-11-18 | `remote/org.myaiceo/myaiceo` | 2026-11-17T135605448797 -> 2026-11-18T160926522347 | 5 removed | quiet |
| 2026-11-18 | `remote/com.whywontai/ai-visibility` | 2026-11-11T230835971382 -> 2026-11-18T160857815273 | 3 added | quiet |
| 2026-11-18 | `remote/ca.movahedi/privacy` | 2026-11-17T164230847567 -> 2026-11-18T160849696570 | 1 changed | quiet |
| 2026-11-18 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-18T135213919215 -> 2026-11-18T160833747238 | 6 changed, 3 added | quiet |
| 2026-11-18 | `remote/dev.verisource/mcp` | 2026-11-17T031523806521 -> 2026-11-18T160740775511 | 1 changed | quiet |
| 2026-11-18 | `remote/com.toiseai/toise` | 2026-11-18T135131290048 -> 2026-11-18T160737225119 | 18 changed | quiet |
| 2026-11-18 | `remote/ai.multiservicios/services` | 2026-10-06T105750487902 -> 2026-11-18T160731207407 | 1 changed | quiet |
| 2026-11-18 | `remote/org.morpho/mcp` | 2026-11-09T165240216100 -> 2026-11-18T160729752125 | 1 changed, 27 removed | quiet |
| 2026-11-18 | `remote/dev.mentio/mcp` | 2026-11-18T134818786790 -> 2026-11-18T160726369040 | 1 changed | quiet |
| 2026-11-18 | `remote/com.manifoldbt/docs` | 2026-11-09T165236318623 -> 2026-11-18T160725051167 | 1 changed | quiet |
| 2026-11-18 | `remote/io.github.mydatapass/mydatapass` | 2026-10-03T121024201831 -> 2026-11-18T160707236960 | 5 changed (every tool) | quiet |
| 2026-11-18 | `remote/com.kiprarent/kipra-rent-a-car` | 2026-11-09T165218500957 -> 2026-11-18T160705098556 | 2 changed | quiet |
| 2026-11-18 | `remote/ai.justdomain/just-domain` | 2026-10-31T234823877552 -> 2026-11-18T160701419693 | 2 changed | quiet |
| 2026-11-18 | `remote/io.github.RozoAI/checkout` | 2026-11-17T163921748002 -> 2026-11-18T160656000070 | 2 changed | review |
| 2026-11-18 | `remote/com.rivalsweeper/signals` | 2026-11-17T163920705156 -> 2026-11-18T160656496609 | 1 added | quiet |
| 2026-11-18 | `remote/co.lovie/company-formation` | 2026-11-13T145949309316 -> 2026-11-18T160651093154 | 15 changed | quiet |
| 2026-11-18 | `remote/services.ottoai/otto` | 2026-11-11T164025887461 -> 2026-11-18T160632693409 | 1 changed, 1 removed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 72286 substantive, 40914 that changed only numbers (a catalogue counter ticking, a date), 1086 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 61815 | 23462 | 38353 | 0 |
| `a2awire.com` | 3240 | 3240 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 471 | 471 | 0 | 0 |
| `civai.co` | 368 | 368 | 0 | 0 |
| `modevc.com` | 349 | 349 | 0 | 0 |
| `revmesh2074.workers.dev` | 302 | 261 | 41 | 0 |
| `sistaminuten.se` | 253 | 6 | 0 | 247 |
| `afbudsrejser.dk` | 252 | 6 | 0 | 246 |
| `akkilahdot.fi` | 252 | 6 | 0 | 246 |
| `restplass.no` | 252 | 6 | 0 | 246 |
| `socialloop.ai` | 243 | 243 | 0 | 0 |
| 10179 other operators | 44148 | 41527 | 2520 | 101 |
