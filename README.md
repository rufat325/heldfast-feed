# MCP server tool changes

Last change observed 2026-10-21T05:25:15+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

37866 changes to a tool definition: 1522 npm releases (1276 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 36344 readings of hosted servers that found their tools changed; 2279 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-21 | `remote/dev.xpansion/xfms` | 2026-10-19T135912214353 -> 2026-10-21T052516449348 | 1 changed | quiet |
| 2026-10-21 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-10-20T232819873596 -> 2026-10-21T052515549208 | 1 changed, 5 added | review |
| 2026-10-21 | `remote/no.restplass/travel-search` | 2026-10-20T232819220307 -> 2026-10-21T052512759045 | 1 changed | quiet |
| 2026-10-21 | `remote/dk.afbudsrejser/travel-search` | 2026-10-20T232814188704 -> 2026-10-21T052506741328 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.taux-io/twse-mcp` | 2026-10-19T135742377493 -> 2026-10-21T052506067878 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.tidytools/tidytools-free` | 2026-10-19T160117000525 -> 2026-10-21T052446923989 | 4 changed | review |
| 2026-10-21 | `remote/org.thealibrary/thea` | 2026-10-19T135718095420 -> 2026-10-21T052456595025 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.GriffMurder/taskbullet-site` | 2026-10-19T135706190467 -> 2026-10-21T052443716993 | 1 changed | quiet |
| 2026-10-21 | `remote/at.space-core/game` | 2026-10-20T104121909732 -> 2026-10-21T052437338278 | 1 changed | quiet |
| 2026-10-21 | `remote/com.withnocatch/shiplist` | 2026-10-19T135627477801 -> 2026-10-21T052432011925 | 2 changed | quiet |
| 2026-10-21 | `remote/com.moonshotlab1/inventory` | 2026-10-20T232739581020 -> 2026-10-21T052407481737 | 6 changed | quiet |
| 2026-10-21 | `remote/com.modevc/stage-series-b` | 2026-10-19T135411207378 -> 2026-10-21T052406802609 | 3 changed (every tool) | quiet |
| 2026-10-21 | `remote/com.modevc/stage-seed` | 2026-10-19T135411251155 -> 2026-10-21T052406709925 | 3 changed (every tool) | quiet |
| 2026-10-21 | `remote/com.modevc/stage-pre-seed` | 2026-10-19T135411244394 -> 2026-10-21T052406413255 | 3 changed (every tool) | quiet |
| 2026-10-21 | `remote/com.modevc/firm-translink-capital` | 2026-10-19T135411016662 -> 2026-10-21T052406344824 | 3 changed (every tool) | quiet |
| 2026-10-21 | `remote/com.modevc/firm-summit-partners` | 2026-10-19T135411002768 -> 2026-10-21T052406329797 | 3 changed (every tool) | quiet |
| 2026-10-21 | `remote/com.modevc/firm-new-enterprise-associates-nea` | 2026-10-19T135410940018 -> 2026-10-21T052406267154 | 3 changed (every tool) | quiet |
| 2026-10-21 | `remote/com.modevc/firm-menlo-ventures` | 2026-10-19T135410918341 -> 2026-10-21T052406240263 | 3 changed (every tool) | quiet |
| 2026-10-21 | `remote/com.modevc/firm-insight-partners` | 2026-10-19T135410811210 -> 2026-10-21T052406149511 | 3 changed (every tool) | quiet |
| 2026-10-21 | `remote/com.modevc/firm-cultivation-capital` | 2026-10-19T135410788185 -> 2026-10-21T052405835602 | 3 changed (every tool) | quiet |
| 2026-10-21 | `remote/com.modevc/firm-cathay-innovation` | 2026-10-19T135410734887 -> 2026-10-21T052405896155 | 3 changed (every tool) | quiet |
| 2026-10-21 | `remote/com.modevc/firm-atland-ventures` | 2026-10-19T135410666333 -> 2026-10-21T052405738177 | 3 changed (every tool) | quiet |
| 2026-10-21 | `remote/com.modevc/chart-vercel-ai-sdk-downloads-vs-lab-sdks` | 2026-10-19T135410519148 -> 2026-10-21T052405885745 | 3 changed (every tool) | quiet |
| 2026-10-21 | `remote/com.modevc/chart-llm-api-pricing-history` | 2026-10-19T135410569997 -> 2026-10-21T052405804773 | 3 changed (every tool) | quiet |
| 2026-10-21 | `remote/com.modevc/chart-generative-ai-usage-statistics` | 2026-10-19T135410475001 -> 2026-10-21T052405431577 | 3 changed (every tool) | quiet |
| 2026-10-21 | `remote/com.modevc/chart-claude-vs-chatgpt-leaderboard` | 2026-10-19T135410416649 -> 2026-10-21T052405339822 | 3 changed (every tool) | quiet |
| 2026-10-21 | `remote/com.modevc/chart-chatbot-arena-votes-by-ai-lab` | 2026-10-19T135410324042 -> 2026-10-21T052405392223 | 3 changed (every tool) | quiet |
| 2026-10-21 | `remote/com.modevc/chart-best-llm-for-coding` | 2026-10-19T135410261549 -> 2026-10-21T052405458239 | 3 changed (every tool) | quiet |
| 2026-10-21 | `remote/io.github.GrayWolf8-creator/gw8-signal-api` | 2026-10-20T232736833396 -> 2026-10-21T052403765485 | 1 changed | quiet |
| 2026-10-21 | `remote/how.mise/mise` | 2026-10-20T201126086367 -> 2026-10-21T052405986356 | 2 changed | quiet |
| 2026-10-21 | `remote/org.r3js/r3` | 2026-10-20T201120762293 -> 2026-10-21T052401966409 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-10-20T232831584143 -> 2026-10-21T052331369647 | 1 changed, 5 added | review |
| 2026-10-21 | `remote/se.sistaminuten/travel-search` | 2026-10-20T232829163715 -> 2026-10-21T052327452863 | 1 changed | quiet |
| 2026-10-21 | `remote/io.kolmo.www/kolmo-mcp-server` | 2026-10-20T120633955955 -> 2026-10-21T052325223300 | 1 changed | quiet |
| 2026-10-21 | `remote/com.coveragecat/insurance` | 2026-10-19T212030593509 -> 2026-10-21T052324024334 | 21 changed | review |
| 2026-10-21 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-19T135428124281 -> 2026-10-21T052323250389 | 2 added | quiet |
| 2026-10-21 | `remote/com.thefomite/fomite` | 2026-10-20T104219084998 -> 2026-10-21T052312210070 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.muaviamohammed/mizan` | 2026-10-20T201117143080 -> 2026-10-21T052308886582 | 1 changed, 7 added | quiet |
| 2026-10-21 | `remote/com.zinvyl/marketplace` | 2026-10-20T232827179474 -> 2026-10-21T052307547540 | 5 changed | quiet |
| 2026-10-21 | `remote/io.github.Z4KARY/upgrowth-mcp` | 2026-10-20T104658347324 -> 2026-10-21T052308453010 | 15 changed | quiet |
| 2026-10-21 | `remote/dev.primitive/email` | 2026-10-20T232821946675 -> 2026-10-21T052303454393 | 14 changed (every tool) | review |
| 2026-10-21 | `remote/ai.satohub/onchain-agents` | 2026-10-20T052309644288 -> 2026-10-21T052302160659 | 4 changed | quiet |
| 2026-10-21 | `remote/studio.gradients/mcp` | 2026-10-20T232818623081 -> 2026-10-21T052301494692 | 1 changed | quiet |
| 2026-10-21 | `remote/pro.germanexam/germanexam` | 2026-10-20T201149291724 -> 2026-10-21T052301190279 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.joelp22-maker/referencesource` | 2026-10-19T135210265249 -> 2026-10-21T052259779627 | 1 changed, 1 added | quiet |
| 2026-10-21 | `remote/fi.akkilahdot/travel-search` | 2026-10-20T232816642641 -> 2026-10-21T052259572120 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.sorindecu/vibeshipped` | 2026-10-20T052313178256 -> 2026-10-21T052252980614 | 16 changed (every tool) | review |
| 2026-10-21 | `remote/app.pagecritic/pagecritic` | 2026-10-20T201101715250 -> 2026-10-21T052253533771 | 1 changed | quiet |
| 2026-10-21 | `remote/ai.patchdesign/patch-designer` | 2026-10-20T104026728220 -> 2026-10-21T052253671990 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.vassiliylakhonin/agenda-intelligence-md.1` | 2026-10-19T135119321926 -> 2026-10-21T052252502178 | 1 changed, 2 added | quiet |
| 2026-10-21 | `remote/com.transitmcp/transit-mcp` | 2026-10-20T232808280012 -> 2026-10-21T052252862359 | 2 changed | quiet |
| 2026-10-21 | `remote/com.oneuptime/mcp` | 2026-10-20T052300484897 -> 2026-10-21T052251174544 | 4 changed | quiet |
| 2026-10-21 | `remote/io.github.jennipro-engineering/ghost-market-web` | 2026-10-20T232754664158 -> 2026-10-21T052246778752 | 5 changed, 1 added (every tool) | quiet |
| 2026-10-21 | `remote/com.ssanvps/vps-prices` | 2026-10-19T135352927546 -> 2026-10-21T052247254518 | 2 added | quiet |
| 2026-10-21 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-20T052306788234 -> 2026-10-21T052247513652 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-20T232759197472 -> 2026-10-21T052244552087 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.jake-zaiba/deai-research` | 2026-10-19T135011770453 -> 2026-10-21T052242445529 | 2 changed | quiet |
| 2026-10-21 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-10-20T232742345453 -> 2026-10-21T052240077511 | 1 changed | review |
| 2026-10-21 | `remote/io.github.profitphil/qmax` | 2026-10-19T134957012746 -> 2026-10-21T052240286566 | 2 changed | quiet |
| 2026-10-21 | `remote/com.remoshift/jobs` | 2026-10-20T232751082635 -> 2026-10-21T052238833048 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 24597 substantive, 12739 that changed only numbers (a catalogue counter ticking, a date), 530 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 19158 | 7228 | 11930 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 170 | 170 | 0 | 0 |
| `sistaminuten.se` | 127 | 4 | 0 | 123 |
| `afbudsrejser.dk` | 126 | 4 | 0 | 122 |
| `akkilahdot.fi` | 126 | 4 | 0 | 122 |
| `restplass.no` | 126 | 4 | 0 | 122 |
| `socialloop.ai` | 123 | 123 | 0 | 0 |
| `remoshift.com` | 97 | 6 | 91 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `fundinglandscape.com` | 95 | 61 | 34 | 0 |
| 4679 other operators | 14627 | 13902 | 684 | 41 |
