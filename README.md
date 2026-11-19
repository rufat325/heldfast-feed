# MCP server tool changes

Last change observed 2026-11-19T12:41:26+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

117317 changes to a tool definition: 4732 npm releases (4486 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 112585 readings of hosted servers that found their tools changed; 4437 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-19 | `remote/io.github.makloai/yoya-booking` | 2026-11-17T165015350749 -> 2026-11-19T124127409918 | 2 changed | quiet |
| 2026-11-19 | `remote/com.xn--5kvtwv52d/jizhineng-mcp-gateway` | 2026-11-08T135934783178 -> 2026-11-19T124126177828 | 1 added | quiet |
| 2026-11-19 | `remote/io.github.Z4KARY/upgrowth-mcp` | 2026-11-04T150642775136 -> 2026-11-19T124120433243 | 1 changed | quiet |
| 2026-11-19 | `remote/com.stratalize/realestate` | 2026-11-16T163239313544 -> 2026-11-19T124111010889 | 201 changed (every tool) | quiet |
| 2026-11-19 | `remote/com.riddle/creator` | 2026-11-02T163723813316 -> 2026-11-19T124107103400 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.northsideventuresllc-sketch/northside-intelligence` | 2026-11-10T152948069087 -> 2026-11-19T124054888564 | 4 changed | review |
| 2026-11-19 | `remote/com.kaicalls/kaicalls.1` | 2026-11-17T164935431019 -> 2026-11-19T124046823725 | 1 changed | quiet |
| 2026-11-19 | `remote/app.hyperwave.www/wavetable-tools` | 2026-10-27T054120365340 -> 2026-11-19T124042443104 | 1 changed | quiet |
| 2026-11-19 | `remote/studio.gradients/mcp` | 2026-11-19T020340721568 -> 2026-11-19T124040324912 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.EasyGerber/easygerber` | 2026-11-17T135641002129 -> 2026-11-19T124031853757 | 3 changed | quiet |
| 2026-11-19 | `remote/app.cleanchart/cleanchart` | 2026-11-11T150101440651 -> 2026-11-19T124024155455 | 1 added | quiet |
| 2026-11-19 | `remote/dev.buddylists.www/buddylists` | 2026-11-18T135905345865 -> 2026-11-19T124018177435 | 1 added | quiet |
| 2026-11-19 | `remote/fi.akkilahdot/travel-search` | 2026-11-19T020339030764 -> 2026-11-19T124001906848 | 1 changed | quiet |
| 2026-11-19 | `remote/org.sky-1/rate-hub` | 2026-10-17T055628346065 -> 2026-11-19T123935563305 | 1 changed | quiet |
| 2026-11-19 | `remote/com.zap-hosting/zapx` | 2026-11-18T080232117364 -> 2026-11-19T123930240398 | 2 changed | quiet |
| 2026-11-19 | `remote/com.weverlabs/agentic-rails` | 2026-11-19T020354795014 -> 2026-11-19T123933719010 | 16 added | quiet |
| 2026-11-19 | `remote/io.taifoon/coordination-layer.1` | 2026-11-19T020401569959 -> 2026-11-19T123918740175 | 1 changed | quiet |
| 2026-11-19 | `remote/com.stratalize/oracle` | 2026-11-16T163249447841 -> 2026-11-19T123917014516 | 201 changed (every tool) | quiet |
| 2026-11-19 | `remote/com.stratalize/finance` | 2026-11-16T163249339882 -> 2026-11-19T123916455389 | 201 changed (every tool) | quiet |
| 2026-11-19 | `remote/se.sistaminuten/travel-search` | 2026-11-19T020359948598 -> 2026-11-19T123915373874 | 1 changed | quiet |
| 2026-11-19 | `remote/com.stratalize/healthcare` | 2026-11-16T163336110047 -> 2026-11-19T123911468533 | 201 changed (every tool) | quiet |
| 2026-11-19 | `remote/com.receptionistprices/pricing` | 2026-11-09T170258261480 -> 2026-11-19T123909154078 | 6 changed (every tool) | quiet |
| 2026-11-19 | `remote/com.smsvertpro/mcp` | 2026-10-06T110330567216 -> 2026-11-19T123909218627 | 10 changed (every tool) | quiet |
| 2026-11-19 | `remote/lol.shopat/deals` | 2026-11-16T163331707051 -> 2026-11-19T123908371126 | 5 added | quiet |
| 2026-11-19 | `remote/dev.vetagent/vetagent` | 2026-11-16T190133798077 -> 2026-11-19T123908891271 | 2 changed | quiet |
| 2026-11-19 | `remote/nl.prijsprofeet/prijsprofeet-de` | 2026-11-10T130416269824 -> 2026-11-19T123906308994 | 2 changed (every tool) | quiet |
| 2026-11-19 | `remote/loans.sbaexpress.www/sbaexpress-loans` | 2026-11-11T230936197947 -> 2026-11-19T123905439349 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.roomza-inc/roomza` | 2026-10-27T112548421524 -> 2026-11-19T123904920861 | 1 changed, 2 added | quiet |
| 2026-11-19 | `remote/no.restplass/travel-search` | 2026-11-19T020451372171 -> 2026-11-19T123903826542 | 1 changed | quiet |
| 2026-11-19 | `remote/uk.co.paintdial/paintdial` | 2026-11-16T163235537312 -> 2026-11-19T123902008936 | 1 changed | quiet |
| 2026-11-19 | `remote/com.oxfordledge/oxford-ledge` | 2026-11-14T183357869199 -> 2026-11-19T123901376128 | 1 changed | quiet |
| 2026-11-19 | `remote/ru.vedarai/mcp` | 2026-11-17T135634871691 -> 2026-11-19T123903496933 | 7 changed | quiet |
| 2026-11-19 | `remote/ru.vargov/vargov-design` | 2026-11-09T170154625484 -> 2026-11-19T123904961661 | 1 changed | quiet |
| 2026-11-19 | `remote/org.omenz.www/agent-tools` | 2026-11-18T135911132345 -> 2026-11-19T123858900179 | 4 added | review |
| 2026-11-19 | `remote/com.metaltakip/digest` | 2026-10-24T112926090428 -> 2026-11-19T123854694543 | 2 changed, 5 added, 2 removed (every tool) | quiet |
| 2026-11-19 | `remote/com.menloinsurance/mcp` | 2026-11-16T123028123242 -> 2026-11-19T123853910199 | 3 changed | quiet |
| 2026-11-19 | `remote/dev.upstar/upstar` | 2026-11-09T170148728491 -> 2026-11-19T123853003936 | 1 changed | quiet |
| 2026-11-19 | `remote/coach.upskill/agent-coach` | 2026-11-16T163040670935 -> 2026-11-19T123852051424 | 13 changed (every tool) | quiet |
| 2026-11-19 | `remote/io.kolmo.www/kolmo-mcp-server` | 2026-11-18T135831316633 -> 2026-11-19T123848583503 | 43 changed (every tool) | quiet |
| 2026-11-19 | `remote/io.github.eteleieto/lection-mcp` | 2026-10-19T135847874305 -> 2026-11-19T123848682266 | 1 changed | quiet |
| 2026-11-19 | `remote/com.kaicalls/kaicalls` | 2026-11-18T135827258858 -> 2026-11-19T123847926950 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-11-18T135822378601 -> 2026-11-19T123847093786 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.JcJamet/ia-qa-security` | 2026-11-18T135822936394 -> 2026-11-19T123846937278 | 1 changed | quiet |
| 2026-11-19 | `remote/com.juzpost/mcp` | 2026-11-18T161817922803 -> 2026-11-19T123846504952 | 7 changed | quiet |
| 2026-11-19 | `remote/com.herbertandphyllis/mcp` | 2026-11-17T164816650292 -> 2026-11-19T123845264546 | 3 changed | quiet |
| 2026-11-19 | `remote/za.co.twvs/twvs-mcp` | 2026-11-02T163526116288 -> 2026-11-19T123843004917 | 5 changed (every tool) | quiet |
| 2026-11-19 | `remote/io.github.cryptoduke01/gloam` | 2026-11-11T071454042656 -> 2026-11-19T123840879331 | 6 changed | quiet |
| 2026-11-19 | `remote/io.github.21-million-wall/twentyone-million` | 2026-11-09T170140488989 -> 2026-11-19T123841398350 | 1 changed | quiet |
| 2026-11-19 | `remote/dev.workers.panda198271.tw-search-seo/search-seo` | 2026-09-28T142557322070 -> 2026-11-19T123839970678 | 14 changed (every tool) | quiet |
| 2026-11-19 | `remote/dev.workers.panda198271.tw-real-voices/real-voices` | 2026-09-28T142557339142 -> 2026-11-19T123839890034 | 5 changed (every tool) | quiet |
| 2026-11-19 | `remote/dev.workers.panda198271.tw-life-info/life-info` | 2026-10-06T110320231748 -> 2026-11-19T123839746382 | 11 changed (every tool) | quiet |
| 2026-11-19 | `remote/dev.workers.panda198271.tw-game-release/game-release` | 2026-10-04T055015681689 -> 2026-11-19T123839800497 | 11 changed (every tool) | quiet |
| 2026-11-19 | `remote/com.ferntool/ip` | 2026-11-18T080243532310 -> 2026-11-19T123839867834 | 1 added | quiet |
| 2026-11-19 | `remote/dev.workers.panda198271.tw-creator-shop/creator-shop` | 2026-09-28T142556957347 -> 2026-11-19T123839312065 | 8 changed (every tool) | quiet |
| 2026-11-19 | `remote/io.github.Lokendrakushwah12/engg-space` | 2026-11-04T150720075867 -> 2026-11-19T123837494212 | 1 changed, 3 added | quiet |
| 2026-11-19 | `remote/app.fluxgraph/linkedin` | 2026-11-15T002353886627 -> 2026-11-19T123836538687 | 1 changed, 1 added | quiet |
| 2026-11-19 | `remote/io.github.TMcodingarc/bull-otc` | 2026-11-17T135637273877 -> 2026-11-19T123829158201 | 2 added | quiet |
| 2026-11-19 | `remote/com.penguindriver/toys` | 2026-10-06T110312868599 -> 2026-11-19T123826468239 | 9 changed (every tool) | quiet |
| 2026-11-19 | `remote/al.toyshub/catalog` | 2026-09-28T142554245788 -> 2026-11-19T123828028289 | 3 changed | quiet |
| 2026-11-19 | `remote/com.answeringprices/pricing` | 2026-11-09T170220232349 -> 2026-11-19T123823519228 | 4 changed (every tool) | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 75243 substantive, 40976 that changed only numbers (a catalogue counter ticking, a date), 1098 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 63683 | 25330 | 38353 | 0 |
| `a2awire.com` | 3305 | 3305 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 471 | 471 | 0 | 0 |
| `civai.co` | 369 | 369 | 0 | 0 |
| `modevc.com` | 349 | 349 | 0 | 0 |
| `revmesh2074.workers.dev` | 316 | 273 | 43 | 0 |
| `sistaminuten.se` | 256 | 6 | 0 | 250 |
| `afbudsrejser.dk` | 255 | 6 | 0 | 249 |
| `akkilahdot.fi` | 255 | 6 | 0 | 249 |
| `restplass.no` | 255 | 6 | 0 | 249 |
| `socialloop.ai` | 246 | 246 | 0 | 0 |
| 10349 other operators | 45216 | 42535 | 2580 | 101 |
