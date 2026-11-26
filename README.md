# MCP server tool changes

Last change observed 2026-11-26T13:56:05+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 18238 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 43073 hosted endpoints (read daily, and every four hours while they keep changing).

141843 changes to a tool definition: 5520 npm releases (5274 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 136323 readings of hosted servers that found their tools changed; 5168 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-26 | `remote/com.theagentcolosseum/agent-colosseum` | 2026-11-26T085933458344 -> 2026-11-26T135608056894 | 6 changed (every tool) | quiet |
| 2026-11-26 | `remote/com.test-well/testwell` | 2026-11-20T105601872905 -> 2026-11-26T135606493878 | 2 changed | quiet |
| 2026-11-26 | `remote/io.github.makloai/yoya-booking` | 2026-11-19T124127409918 -> 2026-11-26T135559390023 | 2 changed | quiet |
| 2026-11-26 | `remote/se.sistaminuten/travel-search` | 2026-11-26T085931097041 -> 2026-11-26T135555952843 | 1 changed | quiet |
| 2026-11-26 | `remote/com.xn--5kvtwv52d/jizhineng-mcp-gateway` | 2026-11-21T130618103710 -> 2026-11-26T135558021220 | 3 added | quiet |
| 2026-11-26 | `remote/io.github.jhonnysabino/moedux` | 2026-11-26T085929341313 -> 2026-11-26T135536501930 | 2 added | quiet |
| 2026-11-26 | `remote/fr.projet-ariane/ariane-orientation` | 2026-11-24T170356727111 -> 2026-11-26T135532932394 | 1 changed | quiet |
| 2026-11-26 | `remote/design.overflow/mcp` | 2026-11-25T175104616394 -> 2026-11-26T135530438754 | 1 changed | quiet |
| 2026-11-26 | `remote/ai.modulos/demo-booking` | 2026-11-25T110159014611 -> 2026-11-26T135526773592 | 16 changed (every tool) | quiet |
| 2026-11-26 | `remote/eu.iban-test.www/iban-validation` | 2026-09-23T161028570791 -> 2026-11-26T135527417704 | 4 changed, 6 added (every tool) | quiet |
| 2026-11-26 | `remote/com.lingodew/lingodew` | 2026-11-05T115540413006 -> 2026-11-26T135523294605 | 1 added | quiet |
| 2026-11-26 | `remote/io.github.tjcgraham-rgb/gaip-integration-protocol` | 2026-10-17T055610801832 -> 2026-11-26T135521452370 | 1 changed | quiet |
| 2026-11-26 | `remote/studio.gradients/mcp` | 2026-11-26T090015051194 -> 2026-11-26T135515295764 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.tjcgraham-rgb/gaip-integration-repair` | 2026-10-17T055939593850 -> 2026-11-26T135511676099 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.Tomalarrrr/cyclesite-mcp-server` | 2026-11-15T115600641266 -> 2026-11-26T135511562336 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.TMcodingarc/bull-otc` | 2026-11-26T085926995847 -> 2026-11-26T135505014814 | 1 changed | quiet |
| 2026-11-26 | `remote/com.autoridaddigital.www/geo` | 2026-11-21T151038142686 -> 2026-11-26T135457235987 | 1 changed | quiet |
| 2026-11-26 | `remote/com.anahana/content-mcp` | 2026-09-29T073845920929 -> 2026-11-26T135448507125 | 2 changed, 4 added | quiet |
| 2026-11-26 | `remote/fi.akkilahdot/travel-search` | 2026-11-26T090010440723 -> 2026-11-26T135446392153 | 1 changed | quiet |
| 2026-11-26 | `remote/fyi.whatsnew/changelogs` | 2026-11-03T144909612709 -> 2026-11-26T135433390892 | 3 changed | quiet |
| 2026-11-26 | `remote/com.wenreceipts/site` | 2026-11-12T154935343092 -> 2026-11-26T135430538353 | 2 changed | quiet |
| 2026-11-26 | `remote/com.whatsonvegas/whats-on-vegas` | 2026-11-16T163119139695 -> 2026-11-26T135427193563 | 1 changed | quiet |
| 2026-11-26 | `remote/jp.vsinger-moment/vsinger-moment` | 2026-11-22T104258300579 -> 2026-11-26T135418159495 | 1 changed | quiet |
| 2026-11-26 | `remote/com.testerexchange/tester-exchange` | 2026-11-05T115327041031 -> 2026-11-26T135415390143 | 1 added | quiet |
| 2026-11-26 | `remote/com.easykmarket.vote/votebox-law` | 2026-11-18T161823448055 -> 2026-11-26T135417234828 | 2 changed | quiet |
| 2026-11-26 | `remote/com.visdenda/public` | 2026-11-25T174936537149 -> 2026-11-26T135415494810 | 3 added | quiet |
| 2026-11-26 | `remote/dev.workers.veritas-silicea.veritas-silicea-shop/art` | 2026-11-24T170214913600 -> 2026-11-26T135405839318 | 1 changed | quiet |
| 2026-11-26 | `remote/ru.vedarai/mcp` | 2026-11-21T215752053597 -> 2026-11-26T135404096017 | 25 changed (every tool) | quiet |
| 2026-11-26 | `remote/app.usesnippet/snippet` | 2026-11-24T050504010206 -> 2026-11-26T135358463671 | 2 changed | quiet |
| 2026-11-26 | `remote/io.github.cyanheads/usaspending-mcp-server` | 2026-11-14T115027612067 -> 2026-11-26T135355945555 | 9 changed | quiet |
| 2026-11-26 | `remote/io.github.donniertf-hub/us-bank-check-mcp` | 2026-11-02T163305488606 -> 2026-11-26T135354020256 | 4 changed (every tool) | quiet |
| 2026-11-26 | `remote/com.trymaglev/parts` | 2026-11-20T105356863280 -> 2026-11-26T135339906289 | 2 changed | quiet |
| 2026-11-26 | `remote/com.trip1/mcp` | 2026-11-07T133554091981 -> 2026-11-26T135337606632 | 1 changed | quiet |
| 2026-11-26 | `remote/com.tradermarketcap/prices` | 2026-11-25T035009823615 -> 2026-11-26T135331774417 | 1 added | quiet |
| 2026-11-26 | `remote/io.github.TGS-checker/tracecheck` | 2026-11-23T185301395213 -> 2026-11-26T135330478579 | 1 changed | quiet |
| 2026-11-26 | `remote/com.tofubofu/ai-visibility` | 2026-10-31T130125724412 -> 2026-11-26T135318843261 | 10 added | quiet |
| 2026-11-26 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-25T150335742363 -> 2026-11-26T135308836050 | 1 changed | quiet |
| 2026-11-26 | `remote/mx.techstore/catalog` | 2026-11-23T185223652251 -> 2026-11-26T135258212723 | 3 added | quiet |
| 2026-11-26 | `remote/com.taskhold/taskhold` | 2026-11-17T164712278893 -> 2026-11-26T135255107500 | 1 changed | quiet |
| 2026-11-26 | `remote/com.tamingdns/mcp` | 2026-11-22T150311006538 -> 2026-11-26T135251749471 | 4 changed | quiet |
| 2026-11-26 | `remote/com.swishrjobs/swishrjobs` | 2026-11-26T004531480153 -> 2026-11-26T135248954237 | 3 changed | quiet |
| 2026-11-26 | `remote/io.github.cryptoconspiracy/vurto-swap` | 2026-11-26T085919912746 -> 2026-11-26T135247029186 | 5 changed | quiet |
| 2026-11-26 | `remote/com.swarmmemo/bulletin.1` | 2026-11-23T185211134724 -> 2026-11-26T135246684106 | 2 changed | quiet |
| 2026-11-26 | `remote/com.swarmmemo/bulletin` | 2026-11-23T185210747090 -> 2026-11-26T135246396625 | 2 changed | quiet |
| 2026-11-26 | `remote/com.stickerbyvin/window-sticker` | 2026-11-23T185155067638 -> 2026-11-26T135232788485 | 2 changed (every tool) | quiet |
| 2026-11-26 | `remote/io.squidmaps/squidmaps` | 2026-11-13T115721380038 -> 2026-11-26T135230112706 | 2 changed | quiet |
| 2026-11-26 | `remote/dev.sparkpay/sparkpay` | 2026-11-18T135440877405 -> 2026-11-26T135227220878 | 2 changed | quiet |
| 2026-11-26 | `remote/com.achivx/stablescan` | 2026-11-21T215743599024 -> 2026-11-26T135224989884 | 1 changed | quiet |
| 2026-11-26 | `remote/net.stabledomains/registrar` | 2026-11-21T014927820827 -> 2026-11-26T135224242293 | 5 changed, 2 added | quiet |
| 2026-11-26 | `remote/io.github.majidkabir/sootcase` | 2026-11-23T185354563320 -> 2026-11-26T135225154265 | 5 changed | quiet |
| 2026-11-26 | `remote/ai.stablenews/news` | 2026-11-24T170006472584 -> 2026-11-26T135224583072 | 1 changed | quiet |
| 2026-11-26 | `remote/xyz.sofinancelab/sofinance` | 2026-11-23T185351994939 -> 2026-11-26T135223841267 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.chrisschouk/spotcheck` | 2026-11-09T170022279364 -> 2026-11-26T135221923783 | 2 changed, 5 removed (every tool) | quiet |
| 2026-11-26 | `remote/fyi.smartfin/smartfin` | 2026-11-21T014801293971 -> 2026-11-26T135219964484 | 1 changed | quiet |
| 2026-11-26 | `remote/us.spacenexus/spacenexus` | 2026-10-07T063409058838 -> 2026-11-26T135217098266 | 13 added | quiet |
| 2026-11-26 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-26T085924774542 -> 2026-11-26T135210898752 | 1 changed | quiet |
| 2026-11-26 | `remote/com.socalpitch/socal-pitch` | 2026-11-23T185131133523 -> 2026-11-26T135212250652 | 4 added | quiet |
| 2026-11-26 | `remote/com.dividendsolo.situation/situation` | 2026-11-16T162849605949 -> 2026-11-26T135200749565 | 1 added | quiet |
| 2026-11-26 | `remote/ai.shopfetch/shopfetch` | 2026-11-09T165927100985 -> 2026-11-26T135158604152 | 1 changed | quiet |
| 2026-11-26 | `remote/com.shipshapedata/shipshape-data-docs` | 2026-11-25T105549187267 -> 2026-11-26T135157875616 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 95418 substantive, 45196 that changed only numbers (a catalogue counter ticking, a date), 1229 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 78618 | 36544 | 42074 | 0 |
| `a2awire.com` | 3838 | 3838 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 546 | 546 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 402 | 402 | 0 | 0 |
| `revmesh2074.workers.dev` | 370 | 315 | 55 | 0 |
| `sistaminuten.se` | 286 | 7 | 0 | 279 |
| `afbudsrejser.dk` | 285 | 7 | 0 | 278 |
| `akkilahdot.fi` | 285 | 7 | 0 | 278 |
| `restplass.no` | 285 | 7 | 0 | 278 |
| `socialloop.ai` | 276 | 276 | 0 | 0 |
| 11640 other operators | 53831 | 50648 | 3067 | 116 |
