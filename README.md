# MCP server tool changes

Last change observed 2026-11-25T11:04:55+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 18238 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 43073 hosted endpoints (read daily, and every four hours while they keep changing).

136414 changes to a tool definition: 5421 npm releases (5175 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 130993 readings of hosted servers that found their tools changed; 5083 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-25 | `remote/io.github.noareyenoar/x402-counterparty-reputation` | 2026-11-23T185408370019 -> 2026-11-25T110455721029 | 1 changed | quiet |
| 2026-11-25 | `remote/com.youspot/youspot` | 2026-11-21T151242937146 -> 2026-11-25T110454452920 | 9 changed | quiet |
| 2026-11-25 | `remote/io.github.jimmybr-PDX/rugradar` | 2026-10-19T135310257871 -> 2026-11-25T110446989557 | 4 changed, 6 added (every tool) | review |
| 2026-11-25 | `remote/com.workers-rights/employment-law` | 2026-11-20T105714229777 -> 2026-11-25T110442851083 | 1 changed | quiet |
| 2026-11-25 | `remote/com.ticketfairy/ticket-fairy-public-events` | 2026-11-18T161839373886 -> 2026-11-25T110434812640 | 1 changed, 35 added | quiet |
| 2026-11-25 | `remote/io.github.tendercrestai/tendercrest-ai` | 2026-11-19T123753391606 -> 2026-11-25T110433729654 | 14 changed (every tool) | quiet |
| 2026-11-25 | `remote/com.techfabric/techfabric` | 2026-11-19T123753007108 -> 2026-11-25T110435285048 | 2 changed | quiet |
| 2026-11-25 | `remote/cn.tandiu/data` | 2026-11-25T035036206348 -> 2026-11-25T110434995041 | 1 added | quiet |
| 2026-11-25 | `remote/com.resollo/agent-api` | 2026-11-20T105655497872 -> 2026-11-25T110424770581 | 2 changed | quiet |
| 2026-11-25 | `remote/io.github.VadimModa/moda` | 2026-11-09T170143756936 -> 2026-11-25T110411162354 | 1 changed | quiet |
| 2026-11-25 | `remote/io.linkjolt/linkjolt` | 2026-11-12T154935293312 -> 2026-11-25T110405722270 | 1 added | quiet |
| 2026-11-25 | `remote/com.heroxairdomes/mcp` | 2026-11-16T163312014769 -> 2026-11-25T110354000675 | 2 changed | quiet |
| 2026-11-25 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-25T035029523510 -> 2026-11-25T110351580327 | 2 changed | quiet |
| 2026-11-25 | `remote/co.foodose/glp1-nutrition` | 2026-10-23T120640303360 -> 2026-11-25T110348786063 | 2 changed | quiet |
| 2026-11-25 | `remote/io.github.cantorfi/cantorfi-mcp` | 2026-11-23T185249111747 -> 2026-11-25T110333830764 | 1 changed | quiet |
| 2026-11-25 | `remote/io.github.dwiel/buyusbcables` | 2026-11-24T165507537428 -> 2026-11-25T110331575623 | 3 changed | quiet |
| 2026-11-25 | `remote/io.github.delicious28/wuming-books` | 2026-09-23T160835301010 -> 2026-11-25T110324709580 | 1 changed | quiet |
| 2026-11-25 | `remote/io.github.brunopompeo1/web-enrichment-x402` | 2026-11-16T163217523161 -> 2026-11-25T110253363769 | 3 added, 1 removed | quiet |
| 2026-11-25 | `remote/agency.zoll/ausfuhr` | 2026-11-10T220201678122 -> 2026-11-25T110243311535 | 3 changed | quiet |
| 2026-11-25 | `remote/io.suverse.versum/catalog` | 2026-11-25T035024162940 -> 2026-11-25T110237462933 | 3 changed | quiet |
| 2026-11-25 | `remote/io.bitbucket.markedet/field-notes` | 2026-11-18T135629129872 -> 2026-11-25T110223928882 | 1 changed | quiet |
| 2026-11-25 | `remote/com.triremes/triremes` | 2026-11-20T172129407070 -> 2026-11-25T110211796455 | 1 changed | quiet |
| 2026-11-25 | `remote/ai.modulos/demo-booking` | 2026-11-25T035011578148 -> 2026-11-25T110159014611 | 3 changed | quiet |
| 2026-11-25 | `remote/com.hillsignal/hillsignalapp` | 2026-11-22T150528749249 -> 2026-11-25T110147083909 | 1 changed | quiet |
| 2026-11-25 | `remote/studio.gradients/mcp` | 2026-11-25T035007811337 -> 2026-11-25T110145636841 | 1 changed | quiet |
| 2026-11-25 | `remote/ai.dincat/dincat` | 2026-11-24T050404625423 -> 2026-11-25T110133385719 | 5 changed (every tool) | quiet |
| 2026-11-25 | `remote/com.zap-hosting/zapx` | 2026-11-21T130600384332 -> 2026-11-25T110124178530 | 1 changed | quiet |
| 2026-11-25 | `remote/sg.tanatasa/tanatasa` | 2026-11-23T081919687467 -> 2026-11-25T110118080409 | 1 changed | quiet |
| 2026-11-25 | `remote/fi.akkilahdot/travel-search` | 2026-11-25T035004959572 -> 2026-11-25T110116727274 | 1 changed | quiet |
| 2026-11-25 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-25T035003466800 -> 2026-11-25T110108909175 | 1 changed | quiet |
| 2026-11-25 | `remote/com.sulihuli/catalog` | 2026-11-23T185034621934 -> 2026-11-25T110101399969 | 1 added | quiet |
| 2026-11-25 | `remote/io.github.sudzikcoin/suverse-agent-assistant` | 2026-11-25T035006365271 -> 2026-11-25T110054762229 | 3 changed | quiet |
| 2026-11-25 | `remote/to.stomp/editor` | 2026-11-25T035013295309 -> 2026-11-25T110049503663 | 4 changed, 1 added | quiet |
| 2026-11-25 | `remote/com.vuntum/mcp` | 2026-11-13T120516327282 -> 2026-11-25T110049900151 | 22 changed | quiet |
| 2026-11-25 | `remote/io.github.roomza-inc/roomza` | 2026-11-19T231851480789 -> 2026-11-25T110042808883 | 1 changed | quiet |
| 2026-11-25 | `remote/com.visdenda/public` | 2026-11-24T170224212100 -> 2026-11-25T110045794383 | 5 changed, 9 added, 38 removed | quiet |
| 2026-11-25 | `remote/no.restplass/travel-search` | 2026-11-25T035003379639 -> 2026-11-25T110041346832 | 1 changed | quiet |
| 2026-11-25 | `remote/com.reportgem/global-research` | 2026-11-07T133909278367 -> 2026-11-25T110041679349 | 5 changed (every tool) | quiet |
| 2026-11-25 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-25T035006663571 -> 2026-11-25T110038635865 | 3 changed | quiet |
| 2026-11-25 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-11-24T165212119912 -> 2026-11-25T110033999262 | 1 changed | quiet |
| 2026-11-25 | `remote/com.ascent-partners/vision-driven-design` | 2026-10-19T135453156749 -> 2026-11-25T110030958764 | 8 changed, 1 removed | quiet |
| 2026-11-25 | `remote/tech.upto/up-to-tech` | 2026-11-09T170148494742 -> 2026-11-25T110022537554 | 2 changed, 8 added | quiet |
| 2026-11-25 | `remote/gg.unicum/wot-stats` | 2026-11-24T170156233624 -> 2026-11-25T110020685555 | 1 changed | quiet |
| 2026-11-25 | `remote/io.github.unbrowse-ai/unbrowse` | 2026-11-22T150410548753 -> 2026-11-25T110020088921 | 3 changed | quiet |
| 2026-11-25 | `remote/fun.unbundle/unbundle` | 2026-11-16T163038126853 -> 2026-11-25T110019248032 | 1 added | quiet |
| 2026-11-25 | `remote/com.yippigo/yippigo` | 2026-11-23T185915062078 -> 2026-11-25T110017253642 | 2 changed | quiet |
| 2026-11-25 | `remote/com.auto-units/sigil` | 2026-11-18T135433396400 -> 2026-11-25T110009924183 | 1 removed | quiet |
| 2026-11-25 | `remote/com.shipshapedata/shipshape-data` | 2026-11-24T165145032015 -> 2026-11-25T110004987965 | 1 changed | quiet |
| 2026-11-25 | `remote/ai.flamel/public-content` | 2026-09-23T163132986677 -> 2026-11-25T110002163392 | 1 changed | quiet |
| 2026-11-25 | `remote/com.finerxfinder/finerx` | 2026-10-04T055105706945 -> 2026-11-25T110000998856 | 7 changed | quiet |
| 2026-11-25 | `remote/com.theveilpress.www/veilpress` | 2026-11-16T163257600415 -> 2026-11-25T105958322207 | 1 added | quiet |
| 2026-11-25 | `remote/io.github.jakzaizzat/cukaimax-tax-authority` | 2026-10-17T060431801670 -> 2026-11-25T105954264992 | 5 changed (every tool) | quiet |
| 2026-11-25 | `remote/io.suverse.www/catalog` | 2026-11-25T035027145577 -> 2026-11-25T105951892046 | 3 changed | quiet |
| 2026-11-25 | `remote/se.sistaminuten/travel-search` | 2026-11-25T035026190307 -> 2026-11-25T105947625014 | 1 changed | quiet |
| 2026-11-25 | `remote/com.breadboardhub/circuits` | 2026-11-24T182904031937 -> 2026-11-25T105944763619 | 3 added | quiet |
| 2026-11-25 | `remote/com.ridekick/ridekick` | 2026-11-23T185831847081 -> 2026-11-25T105943538977 | 3 changed | quiet |
| 2026-11-25 | `remote/eu.proofpass/proofpass` | 2026-11-16T163240053232 -> 2026-11-25T105939695591 | 5 added | quiet |
| 2026-11-25 | `remote/com.scorecompute/scorecompute` | 2026-11-24T050403433114 -> 2026-11-25T105939073288 | 2 changed | quiet |
| 2026-11-25 | `remote/ai.arcreport/mcp` | 2026-11-17T031611642890 -> 2026-11-25T105936342357 | 1 changed | quiet |
| 2026-11-25 | `remote/dk.afbudsrejser/travel-search` | 2026-11-25T034958512630 -> 2026-11-25T105933467876 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 91977 substantive, 43231 that changed only numbers (a catalogue counter ticking, a date), 1206 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 74885 | 34677 | 40208 | 0 |
| `a2awire.com` | 3838 | 3838 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 533 | 533 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 401 | 401 | 0 | 0 |
| `revmesh2074.workers.dev` | 370 | 315 | 55 | 0 |
| `sistaminuten.se` | 281 | 7 | 0 | 274 |
| `afbudsrejser.dk` | 280 | 7 | 0 | 273 |
| `akkilahdot.fi` | 280 | 7 | 0 | 273 |
| `restplass.no` | 280 | 7 | 0 | 273 |
| `socialloop.ai` | 271 | 271 | 0 | 0 |
| 11437 other operators | 52174 | 49093 | 2968 | 113 |
