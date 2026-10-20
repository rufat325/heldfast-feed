# MCP server tool changes

Last change observed 2026-10-20T12:06:54+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

37348 changes to a tool definition: 1522 npm releases (1276 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 35826 readings of hosted servers that found their tools changed; 2251 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-20 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-10-20T052336427431 -> 2026-10-20T120655719381 | 1 changed | quiet |
| 2026-10-20 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-10-20T052358528231 -> 2026-10-20T120653230932 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.HillTan/tiktikluck` | 2026-10-20T104353857597 -> 2026-10-20T120651435607 | 25 changed | quiet |
| 2026-10-20 | `remote/se.sistaminuten/travel-search` | 2026-10-20T104349850541 -> 2026-10-20T120647528408 | 1 changed | quiet |
| 2026-10-20 | `remote/no.restplass/travel-search` | 2026-10-20T104259582074 -> 2026-10-20T120636602161 | 1 changed | quiet |
| 2026-10-20 | `remote/io.kolmo.www/kolmo-mcp-server` | 2026-10-18T051346378685 -> 2026-10-20T120633955955 | 1 changed | quiet |
| 2026-10-20 | `remote/studio.gradients/mcp` | 2026-10-20T104626963222 -> 2026-10-20T120625443978 | 1 changed | quiet |
| 2026-10-20 | `remote/fi.akkilahdot/travel-search` | 2026-10-20T104604115095 -> 2026-10-20T120601650558 | 1 changed | quiet |
| 2026-10-20 | `remote/dk.afbudsrejser/travel-search` | 2026-10-20T104233386326 -> 2026-10-20T120551216613 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.voicehook-ai/voicehook` | 2026-10-20T104300714834 -> 2026-10-20T120548223769 | 6 changed | quiet |
| 2026-10-20 | `remote/io.github.jukky-source/wealth-agent` | 2026-10-20T104224149021 -> 2026-10-20T120537981167 | 2 added | quiet |
| 2026-10-20 | `remote/com.veritaset/mcp` | 2026-10-20T104217267586 -> 2026-10-20T120527837211 | 5 changed | quiet |
| 2026-10-20 | `remote/com.trustbaselab/rcb-data` | 2026-10-18T190034460908 -> 2026-10-20T120508909503 | 5 changed | quiet |
| 2026-10-20 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-20T104422593517 -> 2026-10-20T120437487129 | 1 changed | quiet |
| 2026-10-20 | `remote/com.remoshift/jobs` | 2026-10-20T104327265907 -> 2026-10-20T120342762701 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.everyai-com/sahadeva` | 2026-10-18T190016581978 -> 2026-10-20T120326629669 | 1 added | quiet |
| 2026-10-20 | `remote/com.sagots/sagot` | 2026-10-19T135607169792 -> 2026-10-20T120328297529 | 2 changed | quiet |
| 2026-10-20 | `remote/xyz.presio/presio` | 2026-09-23T162921954507 -> 2026-10-20T120251357959 | 1 added | quiet |
| 2026-10-20 | `remote/me.miow/miow` | 2026-10-20T052301225942 -> 2026-10-20T120225243180 | 2 changed | quiet |
| 2026-10-20 | `remote/com.proofprice/pricepaid` | 2026-10-20T104116042444 -> 2026-10-20T120208004895 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.leewenjie/oxaide` | 2026-10-06T105942558883 -> 2026-10-20T120139551883 | 1 changed | quiet |
| 2026-10-20 | `remote/co.civai.nova/support-agent-admin` | 2026-10-17T060010791611 -> 2026-10-20T120119848230 | 2 removed | quiet |
| 2026-10-20 | `remote/io.github.spruikco/send16-mcp` | 2026-10-17T060003786181 -> 2026-10-20T120059212738 | 82 changed, 5 added (every tool) | quiet |
| 2026-10-20 | `remote/io.mediawork/mediawork` | 2026-10-08T135031618068 -> 2026-10-20T120037380674 | 1 changed | quiet |
| 2026-10-20 | `remote/io.kompare/search` | 2026-10-19T134839813182 -> 2026-10-20T120029555922 | 4 changed (every tool) | quiet |
| 2026-10-20 | `remote/io.github.ZenRows/zenrows-mcp` | 2026-10-20T103948609822 -> 2026-10-20T120026438863 | 3 changed, 5 added, 1 removed | quiet |
| 2026-10-20 | `remote/io.github.France-Care/france-care` | 2026-10-20T103747611235 -> 2026-10-20T115959711192 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.daniel3303/equibles` | 2026-10-20T103930294700 -> 2026-10-20T115949049805 | 4 changed | quiet |
| 2026-10-20 | `remote/com.synoptic/synoptic` | 2026-10-19T134806343011 -> 2026-10-20T115910083748 | 2 changed | quiet |
| 2026-10-20 | `remote/com.airport-pickups-london/london-airport-transfers` | 2026-10-20T103658089780 -> 2026-10-20T115855886073 | 11 changed (every tool) | quiet |
| 2026-10-20 | `remote/online.sasame/research` | 2026-10-20T103630426485 -> 2026-10-20T115826873446 | 2 changed, 95 removed | quiet |
| 2026-10-20 | `remote/io.github.jamie7893/keelen` | 2026-10-18T112707820109 -> 2026-10-20T115822518823 | 1 changed, 3 added | quiet |
| 2026-10-20 | `remote/io.github.Desearch-ai/mcp-desearch` | 2026-10-20T103738439869 -> 2026-10-20T115816586631 | 2 changed | quiet |
| 2026-10-20 | `remote/io.github.nickarstrong/isoba` | 2026-10-20T052317585219 -> 2026-10-20T115809160921 | 1 added | quiet |
| 2026-10-20 | `remote/io.github.leanrads/leanriq` | 2026-10-19T211800707288 -> 2026-10-20T115808229982 | 3 changed | quiet |
| 2026-10-20 | `remote/com.idevice/wearables` | 2026-10-20T103618692041 -> 2026-10-20T115748757841 | 2 changed | quiet |
| 2026-10-20 | `remote/tech.marketcalendar/seasonality` | 2026-10-19T211822231926 -> 2026-10-20T115728527276 | 3 changed | quiet |
| 2026-10-20 | `remote/io.github.pipeworx-io/scrapingdog` | 2026-10-19T134610286385 -> 2026-10-20T115716970438 | 4 changed | quiet |
| 2026-10-20 | `remote/io.github.pipeworx-io/statuspage` | 2026-10-19T134920427808 -> 2026-10-20T115708267191 | 4 changed | quiet |
| 2026-10-20 | `remote/io.github.pipeworx-io/password` | 2026-10-19T134455973312 -> 2026-10-20T115658207733 | 4 changed | quiet |
| 2026-10-20 | `remote/io.github.pipeworx-io/openrouter` | 2026-10-19T134454818827 -> 2026-10-20T115657016306 | 4 changed | quiet |
| 2026-10-20 | `remote/com.gameshopenter/shop` | 2026-10-19T211748310002 -> 2026-10-20T115644883572 | 3 changed | quiet |
| 2026-10-20 | `remote/ai.inite/atlas` | 2026-10-19T134436552101 -> 2026-10-20T115637834759 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-20T103409495427 -> 2026-10-20T115615318865 | 2 changed | quiet |
| 2026-10-20 | `remote/io.github.whoyoujoshin/aether-wallet` | 2026-10-18T051231375294 -> 2026-10-20T115613515101 | 1 changed | quiet |
| 2026-10-20 | `remote/com.exchangerebel/exchangerebel` | 2026-10-20T103354088252 -> 2026-10-20T115557570316 | 6 added | review |
| 2026-10-20 | `remote/io.github.pipeworx-io/spotify` | 2026-10-19T134355322915 -> 2026-10-20T115552963273 | 4 changed | quiet |
| 2026-10-20 | `remote/com.algotrada.cubicle/cubicle` | 2026-10-17T054230167644 -> 2026-10-20T115509685263 | 2 added | quiet |
| 2026-10-20 | `remote/now.carejobs/healthcare-jobs` | 2026-10-19T211733444944 -> 2026-10-20T115445659881 | 1 changed | quiet |
| 2026-10-20 | `remote/com.entangleit/agentpay` | 2026-10-17T224302904282 -> 2026-10-20T115440839271 | 2 changed, 1 added | review |
| 2026-10-20 | `remote/cc.registrai/arc-data` | 2026-10-19T211730515549 -> 2026-10-20T115436706082 | 2 added | quiet |
| 2026-10-20 | `remote/com.beleeg/beleeg-public` | 2026-10-03T054721902219 -> 2026-10-20T115418822252 | 2 removed | quiet |
| 2026-10-20 | `remote/org.aspern/aspern` | 2026-10-20T103302401847 -> 2026-10-20T115409649418 | 1 changed | quiet |
| 2026-10-20 | `remote/com.cooperemail/cooper-email` | 2026-10-19T134124348609 -> 2026-10-20T115357782281 | 2 added | quiet |
| 2026-10-20 | `remote/io.github.valetdotdev/valet` | 2026-10-20T103146425386 -> 2026-10-20T115335616035 | 4 changed, 4 added, 4 removed | quiet |
| 2026-10-20 | `remote/io.voidjet/empty-legs` | 2026-10-17T054222130339 -> 2026-10-20T115326538348 | 2 changed | quiet |
| 2026-10-20 | `remote/io.github.joleschmidt/palim` | 2026-10-17T054218180052 -> 2026-10-20T115324448930 | 2 changed | quiet |
| 2026-10-20 | `remote/tech.geosensor.atlas/absence-index` | 2026-10-20T103232438400 -> 2026-10-20T115303618005 | 1 changed | review |
| 2026-10-20 | `remote/com.marketintelligenceapi.api/market-intelligence` | 2026-10-19T211659940154 -> 2026-10-20T115133027392 | 1 changed | review |
| 2026-10-20 | `remote/io.github.tryflask/flask` | 2026-10-20T102905895783 -> 2026-10-20T115028020724 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 24129 substantive, 12706 that changed only numbers (a catalogue counter ticking, a date), 513 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 19158 | 7228 | 11930 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 170 | 170 | 0 | 0 |
| `sistaminuten.se` | 123 | 4 | 0 | 119 |
| `afbudsrejser.dk` | 122 | 4 | 0 | 118 |
| `akkilahdot.fi` | 122 | 4 | 0 | 118 |
| `restplass.no` | 122 | 4 | 0 | 118 |
| `socialloop.ai` | 119 | 119 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `remoshift.com` | 93 | 6 | 87 | 0 |
| `fundinglandscape.com` | 92 | 59 | 33 | 0 |
| 4613 other operators | 14136 | 13440 | 656 | 40 |
