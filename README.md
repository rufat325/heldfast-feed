# MCP server tool changes

Last change observed 2026-10-20T20:12:12+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

37595 changes to a tool definition: 1522 npm releases (1276 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 36073 readings of hosted servers that found their tools changed; 2260 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-20 | `remote/no.restplass/travel-search` | 2026-10-20T135442038712 -> 2026-10-20T201212969175 | 1 changed | quiet |
| 2026-10-20 | `remote/ai.haggl/haggl` | 2026-10-19T135841379787 -> 2026-10-20T201211024772 | 4 changed | quiet |
| 2026-10-20 | `remote/dk.afbudsrejser/travel-search` | 2026-10-20T135437722954 -> 2026-10-20T201207978598 | 1 changed | quiet |
| 2026-10-20 | `remote/org.warriorsfund/wounded-warriors` | 2026-10-20T135435583983 -> 2026-10-20T201205084074 | 3 changed | quiet |
| 2026-10-20 | `remote/com.veritaset/mcp` | 2026-10-20T120527837211 -> 2026-10-20T201201573114 | 1 changed | quiet |
| 2026-10-20 | `remote/ai.trydock/dock` | 2026-10-20T104204254505 -> 2026-10-20T201157051058 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.zambodotdev/zambo` | 2026-10-19T212023993261 -> 2026-10-20T201155815754 | 35 changed (every tool) | quiet |
| 2026-10-20 | `remote/dev.zambo/zambo` | 2026-10-19T212024644811 -> 2026-10-20T201156306148 | 35 changed (every tool) | quiet |
| 2026-10-20 | `remote/com.zinvyl/marketplace` | 2026-10-19T052510130012 -> 2026-10-20T201156963286 | 1 changed | quiet |
| 2026-10-20 | `remote/com.tradeassi/mcp` | 2026-10-18T051516845710 -> 2026-10-20T201156714123 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.Bosacks/magneta-contract-risk` | 2026-10-19T135616792654 -> 2026-10-20T201155042793 | 1 changed, 1 added | quiet |
| 2026-10-20 | `remote/com.auto-units/findable` | 2026-10-19T135718656894 -> 2026-10-20T201154624939 | 1 changed | quiet |
| 2026-10-20 | `remote/io.peakcam/snow` | 2026-10-20T052528354071 -> 2026-10-20T201151806509 | 4 changed, 1 added | quiet |
| 2026-10-20 | `remote/dev.primitive/email` | 2026-10-18T113318149065 -> 2026-10-20T201152163662 | 14 changed (every tool) | quiet |
| 2026-10-20 | `remote/com.rightshold/rightshold` | 2026-10-18T190014869840 -> 2026-10-20T201151048239 | 17 changed | quiet |
| 2026-10-20 | `remote/com.premierletters/mcp` | 2026-10-19T135602455984 -> 2026-10-20T201151653495 | 1 changed | quiet |
| 2026-10-20 | `remote/com.immersivecommons/floor10` | 2026-10-19T135553806253 -> 2026-10-20T201150303345 | 11 changed, 5 removed | quiet |
| 2026-10-20 | `remote/studio.gradients/mcp` | 2026-10-20T135437105486 -> 2026-10-20T201148952162 | 1 changed | quiet |
| 2026-10-20 | `remote/pro.germanexam/germanexam` | 2026-10-19T135549002076 -> 2026-10-20T201149291724 | 3 changed (every tool) | quiet |
| 2026-10-20 | `remote/com.garagesalessearch.www/directory` | 2026-10-19T135547520449 -> 2026-10-20T201148545796 | 2 changed | quiet |
| 2026-10-20 | `remote/fi.akkilahdot/travel-search` | 2026-10-20T135434454765 -> 2026-10-20T201146773214 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.JakubTrousil/agentsjunction` | 2026-10-20T104332362603 -> 2026-10-20T201144460879 | 1 changed | quiet |
| 2026-10-20 | `remote/io.soundchain/agents` | 2026-10-20T104548067629 -> 2026-10-20T201143508220 | 15 changed (every tool) | quiet |
| 2026-10-20 | `remote/com.scienceshot/data-centres` | 2026-10-19T211942733246 -> 2026-10-20T201144519793 | 1 changed | quiet |
| 2026-10-20 | `remote/com.scanverity/resolution-rules` | 2026-10-20T104054781634 -> 2026-10-20T201143610975 | 2 changed | quiet |
| 2026-10-20 | `remote/site.chatgpt.orellise.relay-agent-services/relay` | 2026-10-19T135548979318 -> 2026-10-20T201141727304 | 2 changed, 1 added | quiet |
| 2026-10-20 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-10-20T052311014286 -> 2026-10-20T201136563187 | 7 added | quiet |
| 2026-10-20 | `remote/io.github.Fizzl13/presign-guard` | 2026-10-20T052327047741 -> 2026-10-20T201136846082 | 3 changed | quiet |
| 2026-10-20 | `remote/io.github.Schoasch/backtesting-arena` | 2026-10-20T135425064066 -> 2026-10-20T201135758961 | 1 changed | quiet |
| 2026-10-20 | `remote/ai.startuphub/startuphub` | 2026-10-19T135515454875 -> 2026-10-20T201135596116 | 7 changed | quiet |
| 2026-10-20 | `remote/se.sistaminuten/travel-search` | 2026-10-20T135439085406 -> 2026-10-20T201134695766 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.exquad/thecablecode` | 2026-10-20T135411769720 -> 2026-10-20T201135588121 | 1 changed | quiet |
| 2026-10-20 | `remote/eu.skavio/paid-micro-apis` | 2026-10-18T113505580564 -> 2026-10-20T201135384107 | 4 changed | quiet |
| 2026-10-20 | `remote/market.payapi/marketplace` | 2026-10-19T211923144178 -> 2026-10-20T201134239846 | 1 added | review |
| 2026-10-20 | `remote/com.theagentsindex/mcp` | 2026-10-19T155725089129 -> 2026-10-20T201134187351 | 1 changed | quiet |
| 2026-10-20 | `remote/com.swarmbar/swarmbar` | 2026-10-19T135121014986 -> 2026-10-20T201136012022 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-20T104455523604 -> 2026-10-20T201133308003 | 1 changed | quiet |
| 2026-10-20 | `remote/com.orbylon/readiness` | 2026-10-20T052322545963 -> 2026-10-20T201131884482 | 9 changed (every tool) | quiet |
| 2026-10-20 | `remote/io.github.jennipro-engineering/ghost-market-web` | 2026-10-20T135407185552 -> 2026-10-20T201129938275 | 5 changed (every tool) | review |
| 2026-10-20 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-20T135415784818 -> 2026-10-20T201125310864 | 4 changed | quiet |
| 2026-10-20 | `remote/com.moaibuy/moa` | 2026-10-19T135410086155 -> 2026-10-20T201125468854 | 4 changed, 3 added | quiet |
| 2026-10-20 | `remote/how.mise/mise` | 2026-10-20T135359495781 -> 2026-10-20T201126086367 | 24 changed (every tool) | quiet |
| 2026-10-20 | `remote/com.mcpcheckup/mcp` | 2026-10-18T113030183433 -> 2026-10-20T201123829310 | 1 changed | quiet |
| 2026-10-20 | `remote/com.tryalpy/alpy` | 2026-10-20T052320654736 -> 2026-10-20T201123485074 | 1 changed | quiet |
| 2026-10-20 | `remote/com.sellerprofitdoctor/free-tools` | 2026-10-19T135311219024 -> 2026-10-20T201120356359 | 4 changed | quiet |
| 2026-10-20 | `remote/ai.signal8/mcp` | 2026-10-19T135325222648 -> 2026-10-20T201121245779 | 3 changed | quiet |
| 2026-10-20 | `remote/org.r3js/r3` | 2026-10-20T103841644992 -> 2026-10-20T201120762293 | 4 changed, 1 added | quiet |
| 2026-10-20 | `remote/wiki.radix/radix-wiki` | 2026-10-19T211932994961 -> 2026-10-20T201118630626 | 9 changed, 4 added | quiet |
| 2026-10-20 | `remote/com.remoshift/jobs` | 2026-10-20T135408458587 -> 2026-10-20T201118387823 | 1 changed | quiet |
| 2026-10-20 | `remote/org.living-bread.mcp/living-bread` | 2026-10-18T223919797721 -> 2026-10-20T201118755584 | 1 changed | quiet |
| 2026-10-20 | `remote/com.proofprice/pricepaid` | 2026-10-20T135358292924 -> 2026-10-20T201115520667 | 4 changed, 2 added | quiet |
| 2026-10-20 | `remote/io.github.muaviamohammed/mizan` | 2026-10-20T104203607902 -> 2026-10-20T201117143080 | 16 added | quiet |
| 2026-10-20 | `remote/com.siliconfloor/silicon-floor` | 2026-10-19T135254439213 -> 2026-10-20T201112487207 | 1 added | quiet |
| 2026-10-20 | `remote/io.github.scraping-api-plans/web-data-plan-finder` | 2026-10-20T104256346246 -> 2026-10-20T201113590990 | 6 changed (every tool) | review |
| 2026-10-20 | `remote/io.github.leewenjie/oxaide` | 2026-10-20T120139551883 -> 2026-10-20T201114301743 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.helferundprofi/helfer-und-profi` | 2026-10-19T135159389472 -> 2026-10-20T201110656318 | 2 changed | quiet |
| 2026-10-20 | `remote/pl.klyo/games` | 2026-10-19T135156598996 -> 2026-10-20T201109912503 | 1 changed, 1 added | quiet |
| 2026-10-20 | `remote/dev.refnusa/refnusa` | 2026-10-19T135212156121 -> 2026-10-20T201110083271 | 4 changed, 1 added | quiet |
| 2026-10-20 | `remote/co.civai.nova/support-agent-admin` | 2026-10-20T135350866043 -> 2026-10-20T201107534450 | 2 changed, 2 added | quiet |
| 2026-10-20 | `remote/uk.co.manchestertonight/whats-on` | 2026-10-19T135056271356 -> 2026-10-20T201106042090 | 4 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 24351 substantive, 12722 that changed only numbers (a catalogue counter ticking, a date), 522 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 19158 | 7228 | 11930 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 170 | 170 | 0 | 0 |
| `sistaminuten.se` | 125 | 4 | 0 | 121 |
| `afbudsrejser.dk` | 124 | 4 | 0 | 120 |
| `akkilahdot.fi` | 124 | 4 | 0 | 120 |
| `restplass.no` | 124 | 4 | 0 | 120 |
| `socialloop.ai` | 121 | 121 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `remoshift.com` | 95 | 6 | 89 | 0 |
| `fundinglandscape.com` | 94 | 60 | 34 | 0 |
| 4650 other operators | 14369 | 13659 | 669 | 41 |
