# MCP server tool changes

Last change observed 2026-11-27T17:16:58+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 18238 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 43073 hosted endpoints (read daily, and every four hours while they keep changing).

145561 changes to a tool definition: 5620 npm releases (5374 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 139941 readings of hosted servers that found their tools changed; 5239 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-27 | `remote/studio.gradients/mcp` | 2026-11-27T145512067881 -> 2026-11-27T171700724403 | 1 changed | quiet |
| 2026-11-27 | `remote/fi.akkilahdot/travel-search` | 2026-11-27T145426530374 -> 2026-11-27T171631200406 | 1 changed | quiet |
| 2026-11-27 | `remote/com.easykmarket.vote/votebox-law` | 2026-11-27T145353833793 -> 2026-11-27T171556200643 | 1 changed | quiet |
| 2026-11-27 | `remote/xn--3ds443g.xn--s7y/duan-online` | 2026-11-27T145201575066 -> 2026-11-27T171551677600 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.thrive-fleet/fleet-data` | 2026-11-26T173156336013 -> 2026-11-27T171548202693 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-27T145346147208 -> 2026-11-27T171545899529 | 3 changed | quiet |
| 2026-11-27 | `remote/io.github.sudzikcoin/suverse-agent-assistant` | 2026-11-27T145235358899 -> 2026-11-27T171546517962 | 3 changed | quiet |
| 2026-11-27 | `remote/dev.vetagent/vetagent` | 2026-11-25T174929813851 -> 2026-11-27T171547235079 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.kushkillerjsixx66/vara-mcp-server` | 2026-11-27T145330980090 -> 2026-11-27T171538694238 | 3 changed | quiet |
| 2026-11-27 | `remote/no.restplass/travel-search` | 2026-11-27T145223434510 -> 2026-11-27T171536443833 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.HuangGoodmanAgency/edgar-and-edgarette` | 2026-11-27T091039041477 -> 2026-11-27T171535409030 | 1 added | quiet |
| 2026-11-27 | `remote/com.theagentcolosseum/agent-colosseum` | 2026-11-26T172946185489 -> 2026-11-27T171534308833 | 6 changed (every tool) | quiet |
| 2026-11-27 | `remote/io.suverse.www/catalog` | 2026-11-27T145142683964 -> 2026-11-27T171528956950 | 3 changed | quiet |
| 2026-11-27 | `remote/se.sistaminuten/travel-search` | 2026-11-27T145136246789 -> 2026-11-27T171523723385 | 1 changed | quiet |
| 2026-11-27 | `remote/com.imidaily/data` | 2026-11-16T163317035573 -> 2026-11-27T171514610144 | 4 changed | quiet |
| 2026-11-27 | `remote/com.heroxairdomes/mcp` | 2026-11-25T110354000675 -> 2026-11-27T171509588958 | 5 changed | quiet |
| 2026-11-27 | `remote/io.giftgenius/gift-genius` | 2026-11-24T050428204838 -> 2026-11-27T171506708226 | 5 changed | quiet |
| 2026-11-27 | `remote/io.github.jhonnysabino/moedux` | 2026-11-27T091113688408 -> 2026-11-27T171503999472 | 4 changed | quiet |
| 2026-11-27 | `remote/com.herbertandphyllis/mcp` | 2026-11-26T172904075761 -> 2026-11-27T171451250144 | 1 changed | quiet |
| 2026-11-27 | `remote/com.conved/mcp` | 2026-11-13T200758487649 -> 2026-11-27T171451358051 | 1 changed | quiet |
| 2026-11-27 | `remote/com.breadboardhub/circuits` | 2026-11-27T091007903158 -> 2026-11-27T171447342916 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-27T145233783312 -> 2026-11-27T171441400920 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.jgmale123/blockchainiq-x402-remote` | 2026-11-24T165458505195 -> 2026-11-27T171438026468 | 1 changed | quiet |
| 2026-11-27 | `remote/dk.afbudsrejser/travel-search` | 2026-11-27T145125831160 -> 2026-11-27T171436025118 | 1 changed | quiet |
| 2026-11-27 | `remote/com.vidreno/mcp` | 2026-11-27T091006498617 -> 2026-11-27T171401780556 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.ohad6k/viberaven-guides` | 2026-11-26T004441437504 -> 2026-11-27T171401086428 | 2 changed | quiet |
| 2026-11-27 | `remote/io.github.dimabalony/whentofly` | 2026-11-27T145025591804 -> 2026-11-27T171359929864 | 1 changed | quiet |
| 2026-11-27 | `remote/io.suverse.versum/catalog` | 2026-11-27T145212190426 -> 2026-11-27T171349430010 | 3 changed | quiet |
| 2026-11-27 | `remote/io.github.brawlaphant/vealth` | 2026-11-25T035021087015 -> 2026-11-27T171343760832 | 10 changed | quiet |
| 2026-11-27 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-27T145135419102 -> 2026-11-27T171340723321 | 1 changed | quiet |
| 2026-11-27 | `remote/sh.twitr/twitr` | 2026-09-23T163054036488 -> 2026-11-27T171335640652 | 2 changed | quiet |
| 2026-11-27 | `remote/no.verako/verako` | 2026-11-23T185605520716 -> 2026-11-27T171316821960 | 5 changed | quiet |
| 2026-11-27 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-27T145123026197 -> 2026-11-27T171305831220 | 4 added | quiet |
| 2026-11-27 | `remote/xyz.urbangametheory/urban-game-theory` | 2026-11-27T144946483555 -> 2026-11-27T171304102843 | 11 changed, 2 added, 2 removed | quiet |
| 2026-11-27 | `remote/com.tieredtravel/travel` | 2026-11-27T145116806556 -> 2026-11-27T171300461938 | 2 changed | quiet |
| 2026-11-27 | `remote/co.sailrides/sail` | 2026-11-27T145040805323 -> 2026-11-27T171243507597 | 3 changed | quiet |
| 2026-11-27 | `remote/app.rosmaryn/encyclopedia` | 2026-11-23T185021693124 -> 2026-11-27T171234294672 | 1 changed | quiet |
| 2026-11-27 | `remote/com.studiotvai/llm-vram` | 2026-11-26T134447707443 -> 2026-11-27T171218991212 | 2 changed | quiet |
| 2026-11-27 | `remote/work.agentexchange/chain-reads` | 2026-11-24T165226148506 -> 2026-11-27T171208884294 | 1 changed | review |
| 2026-11-27 | `remote/io.github.spree/ecommerce-docs` | 2026-11-25T174444525673 -> 2026-11-27T171203235767 | 1 changed | quiet |
| 2026-11-27 | `remote/com.radar-cnpj/radar-cnpj` | 2026-11-16T162730838162 -> 2026-11-27T171200897349 | 1 changed | quiet |
| 2026-11-27 | `remote/net.swaptitan/swaptitan` | 2026-11-27T144838950775 -> 2026-11-27T171150920013 | 1 changed | quiet |
| 2026-11-27 | `remote/com.commlo/commute-network` | 2026-11-26T220019878012 -> 2026-11-27T171146851334 | 2 changed | quiet |
| 2026-11-27 | `remote/io.github.cnghockey/sats4ai` | 2026-11-26T220003500155 -> 2026-11-27T171054711138 | 3 changed | quiet |
| 2026-11-27 | `remote/com.ondacast/ondacast` | 2026-11-02T163116246462 -> 2026-11-27T171030699247 | 2 changed | quiet |
| 2026-11-27 | `remote/dev.workers.rugsight.rugsight/rugsight` | 2026-11-26T172503827285 -> 2026-11-27T171022710682 | 1 added | quiet |
| 2026-11-27 | `remote/de.skysolar/sky-solar` | 2026-11-19T123239044964 -> 2026-11-27T171005216148 | 4 changed | quiet |
| 2026-11-27 | `remote/com.radarbg/radar-tools` | 2026-11-27T144651659339 -> 2026-11-27T170959112440 | 1 added | quiet |
| 2026-11-27 | `remote/com.pontofato/pontofato` | 2026-11-27T144750320298 -> 2026-11-27T170939272974 | 1 changed | quiet |
| 2026-11-27 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-27T144725791276 -> 2026-11-27T170934798868 | 1 changed | quiet |
| 2026-11-27 | `remote/com.professorotter/activities` | 2026-11-13T115544071126 -> 2026-11-27T170930884696 | 2 changed, 18 added | quiet |
| 2026-11-27 | `remote/social.poolster/poolster` | 2026-11-26T085914046769 -> 2026-11-27T170913998101 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.Payotte-com/payotte-mcp` | 2026-11-06T214825225581 -> 2026-11-27T170908047273 | 2 changed | quiet |
| 2026-11-27 | `remote/com.paiddev/latent-space` | 2026-11-23T184831244163 -> 2026-11-27T170855187926 | 1 added | quiet |
| 2026-11-27 | `remote/com.toiseai/toise` | 2026-11-27T144642546831 -> 2026-11-27T170848173582 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.sellrock-de/steamwebapi` | 2026-11-26T134739176644 -> 2026-11-27T170832938486 | 2 changed | quiet |
| 2026-11-27 | `remote/com.oneuptime/mcp` | 2026-11-25T105332348100 -> 2026-11-27T170824026808 | 15 changed | quiet |
| 2026-11-27 | `remote/io.github.northstar-trustrail/agent-resort` | 2026-11-27T144520372859 -> 2026-11-27T170822627907 | 4 changed, 20 removed | quiet |
| 2026-11-27 | `remote/sk.nisava/shop` | 2026-11-16T162558965991 -> 2026-11-27T170819820147 | 2 added | quiet |
| 2026-11-27 | `remote/com.rushordertees/rushordertees` | 2026-11-24T050305043430 -> 2026-11-27T170813965115 | 11 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 97131 substantive, 47179 that changed only numbers (a catalogue counter ticking, a date), 1251 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 80486 | 36546 | 43940 | 0 |
| `a2awire.com` | 4238 | 4238 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 549 | 549 | 0 | 0 |
| `modevc.com` | 524 | 524 | 0 | 0 |
| `civai.co` | 403 | 403 | 0 | 0 |
| `revmesh2074.workers.dev` | 373 | 315 | 58 | 0 |
| `sistaminuten.se` | 291 | 7 | 0 | 284 |
| `afbudsrejser.dk` | 290 | 7 | 0 | 283 |
| `akkilahdot.fi` | 290 | 7 | 0 | 283 |
| `restplass.no` | 290 | 7 | 0 | 283 |
| `socialloop.ai` | 281 | 281 | 0 | 0 |
| 11828 other operators | 55205 | 51906 | 3181 | 118 |
