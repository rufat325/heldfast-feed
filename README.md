# MCP server tool changes

Last change observed 2026-11-28T08:32:41+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 18238 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 43073 hosted endpoints (read daily, and every four hours while they keep changing).

145969 changes to a tool definition: 5620 npm releases (5374 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 140349 readings of hosted servers that found their tools changed; 5269 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-28 | `remote/uk.co.pricegraph/mcp` | 2026-11-26T085929896316 -> 2026-11-28T083241790995 | 2 added | quiet |
| 2026-11-28 | `remote/se.sistaminuten/travel-search` | 2026-11-27T214251535317 -> 2026-11-28T083242890152 | 1 changed | quiet |
| 2026-11-28 | `remote/io.taifoon/coordination-layer.1` | 2026-11-27T214252381514 -> 2026-11-28T083242680172 | 1 changed | review |
| 2026-11-28 | `remote/io.suverse.www/catalog` | 2026-11-27T214252493095 -> 2026-11-28T083243425278 | 1 changed | quiet |
| 2026-11-28 | `remote/io.github.dimabalony/whentofly` | 2026-11-27T214246578295 -> 2026-11-28T083241074537 | 1 changed | quiet |
| 2026-11-28 | `remote/ai.whatsupin/events` | 2026-11-27T145024063735 -> 2026-11-28T083239037949 | 5 changed | quiet |
| 2026-11-28 | `remote/no.verako/verako` | 2026-11-27T171316821960 -> 2026-11-28T083239445014 | 2 changed, 2 added | quiet |
| 2026-11-28 | `remote/xyz.urbangametheory/urban-game-theory` | 2026-11-27T214244236181 -> 2026-11-28T083239055916 | 7 changed | quiet |
| 2026-11-28 | `remote/com.thefomite/fomite` | 2026-11-27T091107871898 -> 2026-11-28T083236541957 | 1 changed | quiet |
| 2026-11-28 | `remote/com.idosgames/platform` | 2026-11-26T220028045209 -> 2026-11-28T083233533257 | 3 changed | quiet |
| 2026-11-28 | `remote/io.github.kfx2026/sanyu-research` | 2026-11-26T172513512632 -> 2026-11-28T083238025452 | 5 changed, 151 removed | quiet |
| 2026-11-28 | `remote/pl.finwire/data` | 2026-11-26T220022820891 -> 2026-11-28T083231035574 | 3 changed, 4 added | quiet |
| 2026-11-28 | `remote/online.putit/put-it-online` | 2026-11-27T144652836768 -> 2026-11-28T083231517628 | 1 changed, 1 added | quiet |
| 2026-11-28 | `remote/com.professorotter/activities` | 2026-11-27T214233298777 -> 2026-11-28T083230311078 | 1 changed | quiet |
| 2026-11-28 | `remote/com.paidhandshake/exchange` | 2026-11-26T220017427526 -> 2026-11-28T083227663799 | 8 changed | quiet |
| 2026-11-28 | `remote/io.github.moralito311-andr/andreax` | 2026-11-26T135001054765 -> 2026-11-28T083227656307 | 6 changed, 94 removed | quiet |
| 2026-11-28 | `remote/io.github.donofdebt/ouncescout` | 2026-11-27T091055896562 -> 2026-11-28T083226505260 | 6 changed, 1 added | review |
| 2026-11-28 | `remote/co.netstate/netstate` | 2026-11-27T214225525228 -> 2026-11-28T083224744686 | 1 changed | quiet |
| 2026-11-28 | `remote/com.modevc/stage-series-a` | 2026-11-27T144515645715 -> 2026-11-28T083224080715 | 6 changed | quiet |
| 2026-11-28 | `remote/com.modevc/chart-openai-leaderboard-ranking` | 2026-11-27T144514347013 -> 2026-11-28T083224007617 | 6 changed | quiet |
| 2026-11-28 | `remote/com.modevc/chart-open-weights-vs-proprietary-arena-gap` | 2026-11-27T144514488389 -> 2026-11-28T083223960847 | 6 changed | quiet |
| 2026-11-28 | `remote/com.modevc/chart-llm-leaderboard-top-10-gap` | 2026-11-27T144514294412 -> 2026-11-28T083223891687 | 6 changed | quiet |
| 2026-11-28 | `remote/com.modevc/chart-how-long-number-one-ai-model-stays-on-top` | 2026-11-27T144514277148 -> 2026-11-28T083223934972 | 6 changed | quiet |
| 2026-11-28 | `remote/com.modevc/chart-best-ai-model-vs-most-popular-ai-chatbot` | 2026-11-27T144514074008 -> 2026-11-28T083223843645 | 6 changed | quiet |
| 2026-11-28 | `remote/com.modevc/chart-best-ai-for-creative-writing` | 2026-11-27T144514079656 -> 2026-11-28T083223757420 | 6 changed | quiet |
| 2026-11-28 | `remote/com.modevc/chart-anthropic-sdk-vs-openai-sdk-npm-downloads` | 2026-11-27T144513845191 -> 2026-11-28T083223574658 | 6 changed | quiet |
| 2026-11-28 | `remote/com.modevc/chart-ai-model-releases-2026` | 2026-11-27T144513714996 -> 2026-11-28T083223566231 | 6 changed | quiet |
| 2026-11-28 | `remote/com.modevc/chart-ai-model-launch-strategy` | 2026-11-27T144513539497 -> 2026-11-28T083223586344 | 6 changed | quiet |
| 2026-11-28 | `remote/com.modevc/chart-ai-coding-assistant-statistics` | 2026-11-27T144513426439 -> 2026-11-28T083223461994 | 6 changed | quiet |
| 2026-11-28 | `remote/com.modevc/chart-ai-adoption-rate-us-businesses` | 2026-11-27T144513247244 -> 2026-11-28T083223394839 | 6 changed | quiet |
| 2026-11-28 | `remote/com.xipfax/fax` | 2026-11-26T134839878145 -> 2026-11-28T083224396427 | 1 changed | quiet |
| 2026-11-28 | `remote/com.rivalsweeper/signals` | 2026-11-27T091048810121 -> 2026-11-28T083218522821 | 9 changed, 1 added | review |
| 2026-11-28 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-11-27T214217442821 -> 2026-11-28T083212981834 | 1 changed | review |
| 2026-11-28 | `remote/studio.gradients/mcp` | 2026-11-27T214243321220 -> 2026-11-28T083206221462 | 1 changed | quiet |
| 2026-11-28 | `remote/dev.kitscout/kitscout` | 2026-11-27T091044782848 -> 2026-11-28T083207523780 | 4 changed (every tool) | quiet |
| 2026-11-28 | `remote/fi.akkilahdot/travel-search` | 2026-11-27T214241659661 -> 2026-11-28T083204810264 | 1 changed | quiet |
| 2026-11-28 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-27T091022789963 -> 2026-11-28T083203359532 | 1 changed | quiet |
| 2026-11-28 | `remote/com.whatsonvegas/whats-on-vegas` | 2026-11-27T091022873037 -> 2026-11-28T083203451979 | 1 changed | quiet |
| 2026-11-28 | `remote/com.weverlabs/agentic-rails` | 2026-11-27T214249761848 -> 2026-11-28T083212871608 | 16 added | quiet |
| 2026-11-28 | `remote/com.ticketfairy/ticket-fairy-public-events` | 2026-11-27T214256250761 -> 2026-11-28T083203022023 | 7 changed | quiet |
| 2026-11-28 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-27T214239277158 -> 2026-11-28T083203057587 | 1 changed | quiet |
| 2026-11-28 | `remote/com.visdenda/public` | 2026-11-27T145350533863 -> 2026-11-28T083201954827 | 2 changed | quiet |
| 2026-11-28 | `remote/tech.upto/up-to-tech` | 2026-11-26T220036080519 -> 2026-11-28T083200197819 | 1 added | quiet |
| 2026-11-28 | `remote/io.github.TGS-checker/tracecheck` | 2026-11-27T214235128428 -> 2026-11-28T083159567787 | 1 changed | quiet |
| 2026-11-28 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-27T145321939782 -> 2026-11-28T083159364899 | 4 changed | quiet |
| 2026-11-28 | `remote/com.conved/mcp` | 2026-11-27T171451358051 -> 2026-11-28T083158601656 | 1 changed, 1 added | quiet |
| 2026-11-28 | `remote/com.whizbrew/whizbrew` | 2026-11-27T214250875407 -> 2026-11-28T083156693106 | 2 changed | quiet |
| 2026-11-28 | `remote/io.suverse.versum/catalog` | 2026-11-27T214251106146 -> 2026-11-28T083157167765 | 1 changed | quiet |
| 2026-11-28 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-27T214230684275 -> 2026-11-28T083156232504 | 1 changed | quiet |
| 2026-11-28 | `remote/io.github.brawlaphant/vealth` | 2026-11-27T171343760832 -> 2026-11-28T083156157381 | 2 changed | quiet |
| 2026-11-28 | `remote/io.trueinterview/trueinterview` | 2026-11-27T091034637323 -> 2026-11-28T083155158952 | 1 changed | quiet |
| 2026-11-28 | `remote/com.serviche/sergio` | 2026-11-27T214231008343 -> 2026-11-28T083159225317 | 1 changed | quiet |
| 2026-11-28 | `remote/com.seeksat/seeksat` | 2026-11-27T214228308363 -> 2026-11-28T083153938257 | 1 changed | quiet |
| 2026-11-28 | `remote/com.convertlyft/convertlyft` | 2026-11-27T144142065436 -> 2026-11-28T083156411388 | 1 changed | quiet |
| 2026-11-28 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-27T214248198689 -> 2026-11-28T083153314024 | 4 changed, 5 added | quiet |
| 2026-11-28 | `remote/com.cuelark/tools` | 2026-11-27T145128719356 -> 2026-11-28T083154767196 | 12 added | quiet |
| 2026-11-28 | `remote/app.rosmaryn/encyclopedia` | 2026-11-27T171234294672 -> 2026-11-28T083154342469 | 3 changed (every tool) | quiet |
| 2026-11-28 | `remote/ai.codegene/codegene` | 2026-11-27T144139521629 -> 2026-11-28T083155630000 | 10 changed, 7 added | quiet |
| 2026-11-28 | `remote/io.github.bitcoinresearchkit/bitview` | 2026-11-27T144127868055 -> 2026-11-28T083154803771 | 1 changed | quiet |
| 2026-11-28 | `remote/com.tapeperp/tape` | 2026-11-26T220006562065 -> 2026-11-28T083151153281 | 1 changed | review |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 97489 substantive, 47219 that changed only numbers (a catalogue counter ticking, a date), 1261 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 80486 | 36546 | 43940 | 0 |
| `a2awire.com` | 4238 | 4238 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `modevc.com` | 567 | 567 | 0 | 0 |
| `caseyjhand.com` | 550 | 550 | 0 | 0 |
| `civai.co` | 403 | 403 | 0 | 0 |
| `revmesh2074.workers.dev` | 376 | 317 | 59 | 0 |
| `sistaminuten.se` | 293 | 7 | 0 | 286 |
| `afbudsrejser.dk` | 292 | 7 | 0 | 285 |
| `akkilahdot.fi` | 292 | 7 | 0 | 285 |
| `restplass.no` | 292 | 7 | 0 | 285 |
| `socialloop.ai` | 283 | 283 | 0 | 0 |
| 11829 other operators | 55556 | 52216 | 3220 | 120 |
