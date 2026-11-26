# MCP server tool changes

Last change observed 2026-11-26T09:00:10+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 18238 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 43073 hosted endpoints (read daily, and every four hours while they keep changing).

139340 changes to a tool definition: 5427 npm releases (5181 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 133913 readings of hosted servers that found their tools changed; 5139 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-26 | `remote/studio.gradients/mcp` | 2026-11-26T004803477333 -> 2026-11-26T090015051194 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.EasyGerber/easygerber` | 2026-11-26T004803014396 -> 2026-11-26T090014631742 | 5 changed | quiet |
| 2026-11-26 | `remote/fi.akkilahdot/travel-search` | 2026-11-26T004802714335 -> 2026-11-26T090010440723 | 1 changed | quiet |
| 2026-11-26 | `remote/com.weverlabs/agentic-rails` | 2026-11-26T004807493725 -> 2026-11-26T090025992480 | 8 added | quiet |
| 2026-11-26 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-26T004801290981 -> 2026-11-26T090004526196 | 1 changed | quiet |
| 2026-11-26 | `remote/gg.unicum/wot-stats` | 2026-11-25T110020685555 -> 2026-11-26T085954890985 | 4 added | quiet |
| 2026-11-26 | `remote/com.andque/agent-data` | 2026-11-26T004752555588 -> 2026-11-26T085939225118 | 1 changed | quiet |
| 2026-11-26 | `remote/com.qconsultai/qconsul-booking` | 2026-11-25T035030391865 -> 2026-11-26T085934543485 | 1 changed | quiet |
| 2026-11-26 | `remote/com.theagentcolosseum/agent-colosseum` | 2026-11-24T170249928515 -> 2026-11-26T085933458344 | 6 changed (every tool) | quiet |
| 2026-11-26 | `remote/se.sistaminuten/travel-search` | 2026-11-26T004555230914 -> 2026-11-26T085931097041 | 1 changed | quiet |
| 2026-11-26 | `remote/io.suverse.www/catalog` | 2026-11-26T004556735371 -> 2026-11-26T085933410268 | 1 changed | quiet |
| 2026-11-26 | `remote/uk.co.pricegraph/mcp` | 2026-11-26T004554617443 -> 2026-11-26T085929896316 | 2 changed, 1 added | quiet |
| 2026-11-26 | `remote/io.github.jhonnysabino/moedux` | 2026-11-25T150403056138 -> 2026-11-26T085929341313 | 1 changed, 2 added | quiet |
| 2026-11-26 | `remote/io.github.TMcodingarc/bull-otc` | 2026-11-24T170126488829 -> 2026-11-26T085926995847 | 2 changed | quiet |
| 2026-11-26 | `remote/com.viraloutliers/viral-outliers` | 2026-11-26T004550603546 -> 2026-11-26T085924147970 | 1 changed | review |
| 2026-11-26 | `remote/xyz.urbangametheory/urban-game-theory` | 2026-11-25T150348488273 -> 2026-11-26T085924945022 | 3 changed, 1 added | quiet |
| 2026-11-26 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-26T004739661561 -> 2026-11-26T085924774542 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.cryptoconspiracy/vurto-swap` | 2026-11-25T174737909857 -> 2026-11-26T085919912746 | 2 changed | quiet |
| 2026-11-26 | `remote/io.github.sudzikcoin/suverse-agent-assistant` | 2026-11-26T004451737975 -> 2026-11-26T085921393468 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.liad142/yedapo` | 2026-11-25T035005717370 -> 2026-11-26T085920448239 | 2 changed (every tool) | quiet |
| 2026-11-26 | `remote/com.strvest/strvest-public` | 2026-11-25T105625078665 -> 2026-11-26T085919642455 | 1 changed | quiet |
| 2026-11-26 | `remote/ai.staffbots/dispatch` | 2026-11-25T035000162404 -> 2026-11-26T085918778602 | 1 changed | quiet |
| 2026-11-26 | `remote/no.restplass/travel-search` | 2026-11-26T004445153088 -> 2026-11-26T085918799098 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.rodriguem75/datarespublica` | 2026-11-24T165722630708 -> 2026-11-26T085917965414 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.joelp22-maker/referencesource-registrars` | 2026-11-25T174558969964 -> 2026-11-26T085915850686 | 4 changed | quiet |
| 2026-11-26 | `remote/io.github.joelp22-maker/referencesource` | 2026-11-24T165626855285 -> 2026-11-26T085915913845 | 1 changed | quiet |
| 2026-11-26 | `remote/dk.afbudsrejser/travel-search` | 2026-11-26T004442598076 -> 2026-11-26T085915991947 | 1 changed | quiet |
| 2026-11-26 | `remote/social.poolster/poolster` | 2026-11-24T165543345804 -> 2026-11-26T085914046769 | 1 changed | quiet |
| 2026-11-26 | `remote/com.prepportglobal/service-planner` | 2026-11-26T004516726896 -> 2026-11-26T085914081212 | 3 changed (every tool) | quiet |
| 2026-11-26 | `remote/io.github.bnth09productions-maker/scrapling-x402-store` | 2026-11-26T004732494532 -> 2026-11-26T085913035933 | 6 added | quiet |
| 2026-11-26 | `remote/io.github.joelp22-maker/referencesource-import-alerts` | 2026-11-25T174605102670 -> 2026-11-26T085911716526 | 5 changed | quiet |
| 2026-11-26 | `remote/com.trendtemplate/templates` | 2026-11-25T150326468209 -> 2026-11-26T085912265318 | 2 changed | quiet |
| 2026-11-26 | `remote/com.robodebut/submissions` | 2026-11-24T165832614841 -> 2026-11-26T085912153660 | 5 added | quiet |
| 2026-11-26 | `remote/com.supapark/agent-api` | 2026-11-25T174503248299 -> 2026-11-26T085910923644 | 3 changed | quiet |
| 2026-11-26 | `remote/ai.catalystdesk/mcp-server` | 2026-11-24T165620862907 -> 2026-11-26T085910221830 | 2 changed | quiet |
| 2026-11-26 | `remote/io.pagetool/pagetool` | 2026-11-25T105347840902 -> 2026-11-26T085909772640 | 41 changed (every tool) | quiet |
| 2026-11-26 | `remote/io.github.zsraduly77/defi-flow-price-gap` | 2026-11-24T165452989776 -> 2026-11-26T085909120122 | 4 changed | quiet |
| 2026-11-26 | `remote/io.github.yonatangross/orchestkit` | 2026-11-24T165501715325 -> 2026-11-26T085910431725 | 1 added | quiet |
| 2026-11-26 | `remote/io.github.tendercrestai/tendercrest-ai` | 2026-11-25T110433729654 -> 2026-11-26T085909442968 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.gimarcus/signal` | 2026-11-25T105714141029 -> 2026-11-26T085909579944 | 3 changed | quiet |
| 2026-11-26 | `remote/com.ticketfairy/ticket-fairy-public-events` | 2026-11-26T004633010042 -> 2026-11-26T085909552463 | 25 changed | quiet |
| 2026-11-26 | `remote/com.nabarfinder/nabarfinder` | 2026-11-24T165427964329 -> 2026-11-26T085908575288 | 1 changed | quiet |
| 2026-11-26 | `remote/no.pristavla/pristavla` | 2026-11-26T004711125266 -> 2026-11-26T085908169265 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.patrickbdevaney/modelread` | 2026-11-26T004508834793 -> 2026-11-26T085907738381 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-26T004631169219 -> 2026-11-26T085908562655 | 3 changed | quiet |
| 2026-11-26 | `remote/io.github.Djangode/sjothr-mcp` | 2026-11-25T105647669938 -> 2026-11-26T085908955872 | 1 changed, 1 added | quiet |
| 2026-11-26 | `remote/app.seatsherpa/rides` | 2026-11-25T105624307615 -> 2026-11-26T085906532558 | 5 changed | quiet |
| 2026-11-26 | `remote/re.rundata/temps-reel` | 2026-11-25T034942362177 -> 2026-11-26T085905693118 | 2 changed | quiet |
| 2026-11-26 | `remote/io.suverse.versum/catalog` | 2026-11-26T004628980048 -> 2026-11-26T085905624487 | 1 changed | quiet |
| 2026-11-26 | `remote/co.roterminal/roterminal` | 2026-11-24T165300271599 -> 2026-11-26T085905178584 | 9 changed, 8 added | quiet |
| 2026-11-26 | `remote/network.moonbeam.next/paid-calls` | 2026-11-24T194708187919 -> 2026-11-26T085904388877 | 1 removed | quiet |
| 2026-11-26 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-25T150337539551 -> 2026-11-26T085903938211 | 2 changed, 2 added | quiet |
| 2026-11-26 | `remote/com.neblla/neblla` | 2026-11-25T150302730516 -> 2026-11-26T085903608218 | 4 changed, 2 added | quiet |
| 2026-11-26 | `remote/com.multicinesortega/cartelera` | 2026-11-26T004656558235 -> 2026-11-26T085903533252 | 1 changed | quiet |
| 2026-11-26 | `remote/com.mexcheck/mexcheck` | 2026-11-25T034925056774 -> 2026-11-26T085902194884 | 2 added | review |
| 2026-11-26 | `remote/to.stomp/editor` | 2026-11-25T110049503663 -> 2026-11-26T085901438916 | 4 changed, 4 added | review |
| 2026-11-26 | `remote/io.github.MelanieABC/misim-tax-research` | 2026-11-24T165154563722 -> 2026-11-26T085900322358 | 3 changed | quiet |
| 2026-11-26 | `remote/io.github.wms-why/flowmails-mcp` | 2026-11-24T165123172924 -> 2026-11-26T085858905877 | 2 changed | quiet |
| 2026-11-26 | `remote/io.github.supplementscanner/scanner` | 2026-11-25T150253691919 -> 2026-11-26T085900036552 | 4 changed (every tool) | quiet |
| 2026-11-26 | `remote/io.github.cnghockey/sats4ai` | 2026-11-24T050402731073 -> 2026-11-26T085859470311 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 92951 substantive, 45165 that changed only numbers (a catalogue counter ticking, a date), 1224 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 76752 | 34678 | 42074 | 0 |
| `a2awire.com` | 3838 | 3838 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 536 | 536 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 401 | 401 | 0 | 0 |
| `revmesh2074.workers.dev` | 370 | 315 | 55 | 0 |
| `sistaminuten.se` | 285 | 7 | 0 | 278 |
| `afbudsrejser.dk` | 284 | 7 | 0 | 277 |
| `akkilahdot.fi` | 284 | 7 | 0 | 277 |
| `restplass.no` | 284 | 7 | 0 | 277 |
| `socialloop.ai` | 275 | 275 | 0 | 0 |
| 11496 other operators | 53210 | 50059 | 3036 | 115 |
