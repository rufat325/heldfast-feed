# MCP server tool changes

Last change observed 2026-11-09T07:16:37+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

83711 changes to a tool definition: 3605 npm releases (3359 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 80106 readings of hosted servers that found their tools changed; 3613 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-09 | `remote/io.github.AnxForever/stylekit-mcp` | 2026-11-07T133736721559 -> 2026-11-09T071641424451 | 1 changed | quiet |
| 2026-11-09 | `remote/ai.robowrite/mcp` | 2026-11-08T064618013578 -> 2026-11-09T071638143944 | 3 changed | quiet |
| 2026-11-09 | `remote/com.patchmcp/patch` | 2026-11-07T064023966197 -> 2026-11-09T071638928946 | 5 changed | quiet |
| 2026-11-09 | `remote/io.github.cooyun/etuki-finops-mcp` | 2026-11-07T133701095451 -> 2026-11-09T071634046028 | 2 changed, 7 added, 2 removed (every tool) | review |
| 2026-11-09 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-08T064611721574 -> 2026-11-09T071633498270 | 1 changed | quiet |
| 2026-11-09 | `remote/fi.akkilahdot/travel-search` | 2026-11-08T204941353308 -> 2026-11-09T071634876967 | 1 changed | quiet |
| 2026-11-09 | `remote/io.github.privatelawattorneys/wiki-private-law` | 2026-11-08T135738350936 -> 2026-11-09T071633474221 | 3 changed | quiet |
| 2026-11-09 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-08T204941001297 -> 2026-11-09T071633833394 | 24 added | review |
| 2026-11-09 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-08T204940220959 -> 2026-11-09T071632650685 | 3 changed | quiet |
| 2026-11-09 | `remote/ca.tonbot.tolca/tolca` | 2026-11-08T204937754233 -> 2026-11-09T071630665528 | 15 changed (every tool) | quiet |
| 2026-11-09 | `remote/xyz.t0ll/toll` | 2026-11-08T204936645471 -> 2026-11-09T071628812010 | 1 changed | quiet |
| 2026-11-09 | `remote/com.tetheredtrust/tethered-trust` | 2026-11-08T204937131046 -> 2026-11-09T071629603676 | 4 added | review |
| 2026-11-09 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-08T204935296291 -> 2026-11-09T071628320267 | 1 changed | quiet |
| 2026-11-09 | `remote/com.duoleads.social/social-media-data` | 2026-11-08T135518047738 -> 2026-11-09T071628004374 | 26 changed (every tool) | quiet |
| 2026-11-09 | `remote/com.risetive/mcp` | 2026-11-08T135419644183 -> 2026-11-09T071626077927 | 1 changed | quiet |
| 2026-11-09 | `remote/io.github.scraping-api-plans/web-data-plan-finder` | 2026-11-08T064602859870 -> 2026-11-09T071625594918 | 1 added | quiet |
| 2026-11-09 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-11-08T064550388278 -> 2026-11-09T071625594178 | 1 removed | quiet |
| 2026-11-09 | `remote/com.odilelabs/answering-lines` | 2026-11-08T135304978369 -> 2026-11-09T071621205684 | 1 changed | quiet |
| 2026-11-09 | `remote/com.obriym-crm/mcp` | 2026-11-08T204925235816 -> 2026-11-09T071621504819 | 3 changed | quiet |
| 2026-11-09 | `remote/co.civai.nova/mcp-slack_android` | 2026-11-07T203321455870 -> 2026-11-09T071620090846 | 1 added, 17 removed | quiet |
| 2026-11-09 | `remote/xyz.tereno/tereno` | 2026-11-08T135910587730 -> 2026-11-09T071620431578 | 1 added | review |
| 2026-11-09 | `remote/co.civai.nova/mcp-saas_studio` | 2026-11-07T203321473527 -> 2026-11-09T071619340954 | 1 added, 32 removed | quiet |
| 2026-11-09 | `remote/se.sistaminuten/travel-search` | 2026-11-08T204928991652 -> 2026-11-09T071619909259 | 1 changed | quiet |
| 2026-11-09 | `remote/io.taifoon/coordination-layer.1` | 2026-11-08T204929221899 -> 2026-11-09T071620204048 | 2 changed | quiet |
| 2026-11-09 | `remote/co.civai.nova/mcp-browsergpt-browser-control` | 2026-11-07T203321312205 -> 2026-11-09T071618821017 | 1 added, 24 removed | quiet |
| 2026-11-09 | `remote/com.multicinesortega/cartelera` | 2026-11-08T064557024151 -> 2026-11-09T071618401915 | 1 changed | quiet |
| 2026-11-09 | `remote/com.sonarconnections/sonar-connections` | 2026-11-08T204921927065 -> 2026-11-09T071615913972 | 3 changed, 1 added | quiet |
| 2026-11-09 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-08T204943327853 -> 2026-11-09T071608181561 | 3 changed | quiet |
| 2026-11-09 | `remote/io.github.brawlaphant/vealth` | 2026-11-07T063954773425 -> 2026-11-09T071606964338 | 3 changed | quiet |
| 2026-11-09 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-08T204939885424 -> 2026-11-09T071607036887 | 1 changed | quiet |
| 2026-11-09 | `remote/io.github.exquad/thecablecode` | 2026-11-07T151336776992 -> 2026-11-09T071606108208 | 1 changed | quiet |
| 2026-11-09 | `remote/com.themassprint/massprint` | 2026-11-08T135650695762 -> 2026-11-09T071605684518 | 4 changed | quiet |
| 2026-11-09 | `remote/com.jobmojito/jobmojito` | 2026-11-08T204914385691 -> 2026-11-09T071604937480 | 35 changed, 34 added, 20 removed (every tool) | quiet |
| 2026-11-09 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-11-08T000126778932 -> 2026-11-09T071603774700 | 1 changed | quiet |
| 2026-11-09 | `remote/now.salesjobs/mcp` | 2026-11-08T135528174909 -> 2026-11-09T071602995596 | 1 changed | quiet |
| 2026-11-09 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-11-08T064604934304 -> 2026-11-09T071602336191 | 1 removed | quiet |
| 2026-11-09 | `remote/io.github.liad142/yedapo` | 2026-11-08T064604186662 -> 2026-11-09T071602634619 | 2 changed (every tool) | quiet |
| 2026-11-09 | `remote/io.github.Clipform/mcp-server` | 2026-11-08T204911267223 -> 2026-11-09T071601064968 | 4 changed | quiet |
| 2026-11-09 | `remote/ai.thewholetorah/thewholetorah` | 2026-11-08T135733659162 -> 2026-11-09T071601597321 | 1 changed | quiet |
| 2026-11-09 | `remote/no.restplass/travel-search` | 2026-11-08T204945785101 -> 2026-11-09T071602041689 | 1 changed | quiet |
| 2026-11-09 | `remote/dev.pdfops/pdfops-mcp` | 2026-11-08T135412539974 -> 2026-11-09T071602922283 | 3 changed | quiet |
| 2026-11-09 | `remote/com.thefilmradar/filmlab` | 2026-11-08T204912068516 -> 2026-11-09T071601185014 | 5 changed | quiet |
| 2026-11-09 | `remote/io.github.jweezy119/Pabandi` | 2026-11-08T204930654023 -> 2026-11-09T071559998827 | 1 changed, 2 added | quiet |
| 2026-11-09 | `remote/io.github.farenberglord-star/orb-studio` | 2026-11-08T204930169754 -> 2026-11-09T071601125288 | 1 changed | quiet |
| 2026-11-09 | `remote/co.civai.nova/mcp-lagos_life` | 2026-11-07T203323127203 -> 2026-11-09T071559098352 | 1 added, 30 removed | quiet |
| 2026-11-09 | `remote/io.github.si-imtiaz/leadquasar` | 2026-11-08T153834684480 -> 2026-11-09T071559583225 | 1 changed | quiet |
| 2026-11-09 | `remote/dk.afbudsrejser/travel-search` | 2026-11-08T204943064767 -> 2026-11-09T071558870743 | 1 changed | quiet |
| 2026-11-09 | `remote/com.thefomite/fomite` | 2026-11-08T000114328617 -> 2026-11-09T071558556578 | 1 changed | quiet |
| 2026-11-09 | `remote/co.civai.nova/mcp-juicyway` | 2026-11-07T203322868303 -> 2026-11-09T071558994878 | 1 added, 21 removed | quiet |
| 2026-11-09 | `remote/co.civai.nova/mcp-hacker_news` | 2026-11-07T203322693150 -> 2026-11-09T071558905800 | 1 added, 12 removed | quiet |
| 2026-11-09 | `remote/co.civai.nova/mcp-bgpt-yarngpt` | 2026-11-07T203322430404 -> 2026-11-09T071558642474 | 1 added, 2 removed | quiet |
| 2026-11-09 | `remote/co.civai.nova/mcp-bgpt-pdf-generator` | 2026-11-07T203322214165 -> 2026-11-09T071558107247 | 1 added, 5 removed | quiet |
| 2026-11-09 | `remote/co.civai.nova/mcp-bgpt-livescore` | 2026-11-07T203322083688 -> 2026-11-09T071557984718 | 1 added, 10 removed | quiet |
| 2026-11-09 | `remote/co.civai.nova/mcp-bgpt-instagram-android` | 2026-11-07T203322005033 -> 2026-11-09T071557976663 | 1 added, 14 removed | quiet |
| 2026-11-09 | `remote/co.civai.nova/mcp-bgpt-cacnigeria` | 2026-11-07T203321955437 -> 2026-11-09T071557832603 | 1 added, 1 removed | quiet |
| 2026-11-09 | `remote/com.idosgames/platform` | 2026-11-08T064541908731 -> 2026-11-09T071558042381 | 1 changed, 10 added | quiet |
| 2026-11-09 | `remote/co.civai.nova/mcp-audience-resolver` | 2026-11-07T203321997856 -> 2026-11-09T071557482271 | 1 added, 41 removed | quiet |
| 2026-11-09 | `remote/net.hotelrefund/price-tracker` | 2026-11-08T000102954861 -> 2026-11-09T071555426385 | 1 changed | quiet |
| 2026-11-09 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-08T153901970219 -> 2026-11-09T071558576960 | 1 changed, 1 removed | quiet |
| 2026-11-09 | `remote/io.github.Marsell-Official/marsell` | 2026-11-08T153829687046 -> 2026-11-09T071555397946 | 44 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 51638 substantive, 31162 that changed only numbers (a catalogue counter ticking, a date), 911 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 45119 | 15889 | 29230 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1843 | 1843 | 0 | 0 |
| `caseyjhand.com` | 354 | 354 | 0 | 0 |
| `sistaminuten.se` | 214 | 6 | 0 | 208 |
| `afbudsrejser.dk` | 213 | 6 | 0 | 207 |
| `akkilahdot.fi` | 213 | 6 | 0 | 207 |
| `restplass.no` | 213 | 6 | 0 | 207 |
| `civai.co` | 211 | 211 | 0 | 0 |
| `socialloop.ai` | 205 | 205 | 0 | 0 |
| `revmesh2074.workers.dev` | 190 | 167 | 23 | 0 |
| `modevc.com` | 174 | 174 | 0 | 0 |
| 8043 other operators | 32421 | 30430 | 1909 | 82 |
