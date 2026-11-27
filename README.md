# MCP server tool changes

Last change observed 2026-11-27T21:42:55+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 18238 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 43073 hosted endpoints (read daily, and every four hours while they keep changing).

145715 changes to a tool definition: 5620 npm releases (5374 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 140095 readings of hosted servers that found their tools changed; 5250 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-27 | `remote/com.ticketfairy/ticket-fairy-public-events` | 2026-11-27T091041910644 -> 2026-11-27T214256250761 | 3 changed | quiet |
| 2026-11-27 | `remote/eu.surfbooking/surfbooking` | 2026-11-26T134739497673 -> 2026-11-27T214256168880 | 2 changed | quiet |
| 2026-11-27 | `remote/com.gotfreefax/mcp` | 2026-11-27T145323197682 -> 2026-11-27T214252232679 | 1 changed | quiet |
| 2026-11-27 | `remote/se.sistaminuten/travel-search` | 2026-11-27T171523723385 -> 2026-11-27T214251535317 | 1 changed | quiet |
| 2026-11-27 | `remote/io.taifoon/coordination-layer.1` | 2026-11-27T145143126998 -> 2026-11-27T214252381514 | 1 changed | review |
| 2026-11-27 | `remote/io.suverse.www/catalog` | 2026-11-27T171528956950 -> 2026-11-27T214252493095 | 2 changed | quiet |
| 2026-11-27 | `remote/com.whizbrew/whizbrew` | 2026-11-27T091036882018 -> 2026-11-27T214250875407 | 2 changed | quiet |
| 2026-11-27 | `remote/io.suverse.versum/catalog` | 2026-11-27T171349430010 -> 2026-11-27T214251106146 | 2 changed | quiet |
| 2026-11-27 | `remote/io.github.jhonnysabino/moedux` | 2026-11-27T171503999472 -> 2026-11-27T214249821405 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-27T171305831220 -> 2026-11-27T214248198689 | 1 changed | quiet |
| 2026-11-27 | `remote/com.klarefi/mcp` | 2026-11-25T105921587310 -> 2026-11-27T214248516910 | 2 changed | quiet |
| 2026-11-27 | `remote/com.eduavenues/eduavenues` | 2026-11-26T004627333669 -> 2026-11-27T214248972831 | 1 added | quiet |
| 2026-11-27 | `remote/com.tieredtravel/travel` | 2026-11-27T171300461938 -> 2026-11-27T214247936207 | 2 changed | quiet |
| 2026-11-27 | `remote/work.agentexchange/chain-reads` | 2026-11-27T171208884294 -> 2026-11-27T214245075341 | 1 changed | review |
| 2026-11-27 | `remote/io.github.dimabalony/whentofly` | 2026-11-27T171359929864 -> 2026-11-27T214246578295 | 1 changed | quiet |
| 2026-11-27 | `remote/studio.gradients/mcp` | 2026-11-27T171700724403 -> 2026-11-27T214243321220 | 1 changed | quiet |
| 2026-11-27 | `remote/xyz.urbangametheory/urban-game-theory` | 2026-11-27T171304102843 -> 2026-11-27T214244236181 | 1 changed | quiet |
| 2026-11-27 | `remote/gg.transformer/transformer.1` | 2026-11-27T144926599562 -> 2026-11-27T214242163089 | 1 changed | quiet |
| 2026-11-27 | `remote/dev.tradestats/tradestats` | 2026-11-27T144925044892 -> 2026-11-27T214242709529 | 17 changed | quiet |
| 2026-11-27 | `remote/com.tradermarketcap/prices` | 2026-11-26T135331774417 -> 2026-11-27T214241847764 | 1 added | quiet |
| 2026-11-27 | `remote/fi.akkilahdot/travel-search` | 2026-11-27T171631200406 -> 2026-11-27T214241659661 | 1 changed | quiet |
| 2026-11-27 | `remote/com.weverlabs/agentic-rails` | 2026-11-27T091044830892 -> 2026-11-27T214249761848 | 1 changed, 8 added | quiet |
| 2026-11-27 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-27T171545899529 -> 2026-11-27T214239277158 | 2 changed | quiet |
| 2026-11-27 | `remote/dev.vetagent/vetagent` | 2026-11-27T171547235079 -> 2026-11-27T214238803378 | 1 changed | quiet |
| 2026-11-27 | `remote/de.skysolar/sky-solar` | 2026-11-27T171005216148 -> 2026-11-27T214239040642 | 22 changed, 1 added (every tool) | quiet |
| 2026-11-27 | `remote/io.github.kushkillerjsixx66/vara-mcp-server` | 2026-11-27T171538694238 -> 2026-11-27T214237198750 | 2 changed | quiet |
| 2026-11-27 | `remote/app.pointsorcash/points-or-cash` | 2026-11-27T144746582837 -> 2026-11-27T214237638833 | 7 changed (every tool) | quiet |
| 2026-11-27 | `remote/io.github.24seagull-beep/sense2-catalogue` | 2026-11-26T135148736921 -> 2026-11-27T214237504140 | 2 changed | quiet |
| 2026-11-27 | `remote/io.github.TGS-checker/tracecheck` | 2026-11-27T145258181748 -> 2026-11-27T214235128428 | 2 changed (every tool) | quiet |
| 2026-11-27 | `remote/io.github.jweezy119/Pabandi` | 2026-11-27T144706696173 -> 2026-11-27T214234612431 | 1 changed, 4 added | quiet |
| 2026-11-27 | `remote/io.github.farenberglord-star/orb-studio` | 2026-11-27T144703776003 -> 2026-11-27T214234714116 | 2 added | quiet |
| 2026-11-27 | `remote/xyz.quantumatlas/x402-payment-hub` | 2026-11-27T145247789171 -> 2026-11-27T214233621916 | 1 changed | quiet |
| 2026-11-27 | `remote/com.professorotter/activities` | 2026-11-27T170930884696 -> 2026-11-27T214233298777 | 2 changed, 1 added | quiet |
| 2026-11-27 | `remote/social.poolster/poolster` | 2026-11-27T170913998101 -> 2026-11-27T214232401868 | 2 changed | quiet |
| 2026-11-27 | `remote/io.github.sudzikcoin/suverse-agent-assistant` | 2026-11-27T171546517962 -> 2026-11-27T214233709280 | 2 changed | quiet |
| 2026-11-27 | `remote/no.restplass/travel-search` | 2026-11-27T171536443833 -> 2026-11-27T214230960102 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-27T171340723321 -> 2026-11-27T214230684275 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.Hyatus-Living/hyatus-stays` | 2026-11-27T145156385092 -> 2026-11-27T214229985149 | 3 changed | quiet |
| 2026-11-27 | `remote/com.medarep/medarep` | 2026-11-27T170731283428 -> 2026-11-27T214230257771 | 2 changed | quiet |
| 2026-11-27 | `remote/com.zola/zola` | 2026-11-26T172153327540 -> 2026-11-27T214228859189 | 3 changed | quiet |
| 2026-11-27 | `remote/com.serviche/sergio` | 2026-11-27T091011638502 -> 2026-11-27T214231008343 | 4 changed, 2 removed | quiet |
| 2026-11-27 | `remote/com.seeksat/seeksat` | 2026-11-27T145101821683 -> 2026-11-27T214228308363 | 3 changed | quiet |
| 2026-11-27 | `remote/dk.afbudsrejser/travel-search` | 2026-11-27T171436025118 -> 2026-11-27T214227349226 | 1 changed | quiet |
| 2026-11-27 | `remote/net.repleader/mcp` | 2026-11-26T220023835414 -> 2026-11-27T214226773085 | 1 changed | quiet |
| 2026-11-27 | `remote/co.netstate/netstate` | 2026-11-27T144530837547 -> 2026-11-27T214225525228 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.cyanheads/unhcr-refugees-mcp-server` | 2026-11-25T174611514910 -> 2026-11-27T214223943428 | 8 changed (every tool) | quiet |
| 2026-11-27 | `remote/com.yutai/mcp` | 2026-11-27T144448965603 -> 2026-11-27T214224169790 | 11 changed (every tool) | quiet |
| 2026-11-27 | `remote/no.pristavla/pristavla` | 2026-11-27T091004877970 -> 2026-11-27T214222476734 | 1 changed | quiet |
| 2026-11-27 | `remote/com.osmanthagent/market` | 2026-11-25T105547269264 -> 2026-11-27T214218866253 | 2 changed | quiet |
| 2026-11-27 | `remote/tech.kaiku/kaiku.1` | 2026-11-27T170443461526 -> 2026-11-27T214220544984 | 1 changed, 1 added | quiet |
| 2026-11-27 | `remote/network.moonbeam.next/paid-calls` | 2026-11-26T085904388877 -> 2026-11-27T214217600200 | 1 added | review |
| 2026-11-27 | `remote/io.github.novigapi/novigapi` | 2026-11-27T144806212394 -> 2026-11-27T214217414598 | 1 added | quiet |
| 2026-11-27 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-11-27T170528019191 -> 2026-11-27T214217442821 | 1 changed | review |
| 2026-11-27 | `remote/io.github.gamealia/gamealia-mcp` | 2026-11-27T144241677436 -> 2026-11-27T214217609603 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.KevinCapri/nowcast-mcp` | 2026-11-25T150306615305 -> 2026-11-27T214219396093 | 13 changed (every tool) | quiet |
| 2026-11-27 | `remote/com.flomixy/mcp` | 2026-11-27T144237551068 -> 2026-11-27T214218779155 | 2 changed | quiet |
| 2026-11-27 | `remote/com.multicinesortega/cartelera` | 2026-11-27T090956679085 -> 2026-11-27T214216877647 | 1 changed | quiet |
| 2026-11-27 | `remote/org.referencesource/dockerfile-base-image-end-of-support` | 2026-11-26T134315704280 -> 2026-11-27T214215052003 | 2 changed (every tool) | quiet |
| 2026-11-27 | `remote/com.hustlegotreal/mcp` | 2026-11-26T134625481005 -> 2026-11-27T214216003935 | 1 changed | quiet |
| 2026-11-27 | `remote/io.github.MKagesawa/masadeals` | 2026-11-27T170221017209 -> 2026-11-27T214212546600 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 97269 substantive, 47190 that changed only numbers (a catalogue counter ticking, a date), 1256 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 80486 | 36546 | 43940 | 0 |
| `a2awire.com` | 4238 | 4238 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 550 | 550 | 0 | 0 |
| `modevc.com` | 524 | 524 | 0 | 0 |
| `civai.co` | 403 | 403 | 0 | 0 |
| `revmesh2074.workers.dev` | 373 | 315 | 58 | 0 |
| `sistaminuten.se` | 292 | 7 | 0 | 285 |
| `afbudsrejser.dk` | 291 | 7 | 0 | 284 |
| `akkilahdot.fi` | 291 | 7 | 0 | 284 |
| `restplass.no` | 291 | 7 | 0 | 284 |
| `socialloop.ai` | 282 | 282 | 0 | 0 |
| 11829 other operators | 55353 | 52042 | 3192 | 119 |
