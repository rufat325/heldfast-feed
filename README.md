# MCP server tool changes

Last change observed 2026-11-18T08:03:31+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

111466 changes to a tool definition: 4505 npm releases (4259 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 106961 readings of hosted servers that found their tools changed; 4330 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-18 | `remote/app.zolvaagent/zolva` | 2026-11-17T165020324478 -> 2026-11-18T080332487107 | 2 changed | quiet |
| 2026-11-18 | `remote/com.onancap/supplier` | 2026-11-16T163220019026 -> 2026-11-18T080324732758 | 1 added | quiet |
| 2026-11-18 | `remote/com.mintlify/searchmcp` | 2026-11-17T234408002983 -> 2026-11-18T080324842599 | 1 changed | quiet |
| 2026-11-18 | `remote/studio.gradients/mcp` | 2026-11-17T234404950235 -> 2026-11-18T080321818516 | 1 changed | quiet |
| 2026-11-18 | `remote/com.baldwinpergolas/pergola` | 2026-11-16T163140246246 -> 2026-11-18T080313495484 | 4 changed | quiet |
| 2026-11-18 | `remote/fi.akkilahdot/travel-search` | 2026-11-17T234359076544 -> 2026-11-18T080306183857 | 1 changed | quiet |
| 2026-11-18 | `remote/de.mapumi/wunschzettel` | 2026-11-16T163132945409 -> 2026-11-18T080304589144 | 2 added | quiet |
| 2026-11-18 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-17T031604403251 -> 2026-11-18T080303215649 | 1 changed | quiet |
| 2026-11-18 | `remote/com.weverlabs/agentic-rails` | 2026-11-16T190141496226 -> 2026-11-18T080305022928 | 9 added | quiet |
| 2026-11-18 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-17T164827671816 -> 2026-11-18T080258592756 | 3 changed | quiet |
| 2026-11-18 | `remote/io.taifoon/coordination-layer.1` | 2026-11-17T234408987574 -> 2026-11-18T080251121118 | 1 changed | quiet |
| 2026-11-18 | `remote/se.sistaminuten/travel-search` | 2026-11-17T234411531681 -> 2026-11-18T080251491026 | 1 changed | quiet |
| 2026-11-18 | `remote/io.suverse.www/catalog` | 2026-11-17T164911182784 -> 2026-11-18T080251978876 | 3 changed | quiet |
| 2026-11-18 | `remote/org.omenz.www/agent-tools` | 2026-11-17T164838708105 -> 2026-11-18T080247165291 | 15 added | review |
| 2026-11-18 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-17T234345729927 -> 2026-11-18T080247977133 | 2 changed | quiet |
| 2026-11-18 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-17T234344818868 -> 2026-11-18T080245973478 | 1 changed | quiet |
| 2026-11-18 | `remote/dev.tanod/text` | 2026-11-16T122909609567 -> 2026-11-18T080244529775 | 1 changed | quiet |
| 2026-11-18 | `remote/com.ferntool/ip` | 2026-11-16T072202697328 -> 2026-11-18T080243532310 | 1 added | quiet |
| 2026-11-18 | `remote/com.blitzreels/blitzreels` | 2026-11-16T163158014096 -> 2026-11-18T080243094492 | 7 changed | quiet |
| 2026-11-18 | `remote/com.achivx/stablescan` | 2026-11-17T164632231222 -> 2026-11-18T080241835809 | 1 changed | quiet |
| 2026-11-18 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-17T234335292612 -> 2026-11-18T080240241481 | 1 changed | quiet |
| 2026-11-18 | `remote/com.viraloutliers/viral-outliers` | 2026-11-16T163101262344 -> 2026-11-18T080233728780 | 4 changed | quiet |
| 2026-11-18 | `remote/ai.shorti/shorti` | 2026-11-17T164557286547 -> 2026-11-18T080236795212 | 1 changed | quiet |
| 2026-11-18 | `remote/com.serviche/sergio` | 2026-11-17T234334385378 -> 2026-11-18T080238747237 | 1 changed | quiet |
| 2026-11-18 | `remote/com.zap-hosting/zapx` | 2026-11-16T163414621998 -> 2026-11-18T080232117364 | 1 changed | quiet |
| 2026-11-18 | `remote/io.github.moelayyan90/xguard` | 2026-11-17T135657079747 -> 2026-11-18T080231302818 | 50 changed | quiet |
| 2026-11-18 | `remote/io.github.liad142/yedapo` | 2026-11-17T031623725978 -> 2026-11-18T080231528894 | 2 changed (every tool) | quiet |
| 2026-11-18 | `remote/com.it.scorptech/x402` | 2026-11-17T164525435856 -> 2026-11-18T080232402880 | 2 added | review |
| 2026-11-18 | `remote/io.github.utilify-io/utilify-mcp` | 2026-11-17T234346473446 -> 2026-11-18T080230514924 | 2 changed | quiet |
| 2026-11-18 | `remote/io.github.sudzikcoin/suverse-agent-assistant` | 2026-11-17T164954946001 -> 2026-11-18T080230689323 | 3 changed | quiet |
| 2026-11-18 | `remote/com.remoshift/jobs` | 2026-11-17T234326374817 -> 2026-11-18T080229262601 | 1 changed | quiet |
| 2026-11-18 | `remote/no.restplass/travel-search` | 2026-11-17T234355504743 -> 2026-11-18T080228201075 | 1 changed | quiet |
| 2026-11-18 | `remote/co.productaura/productaura.1` | 2026-11-17T164418035092 -> 2026-11-18T080226858960 | 5 added | quiet |
| 2026-11-18 | `remote/com.thefomite/fomite` | 2026-11-17T031602528181 -> 2026-11-18T080224734410 | 1 changed | quiet |
| 2026-11-18 | `remote/com.podbenchmark/podbenchmark` | 2026-11-17T164402781555 -> 2026-11-18T080224226523 | 2 changed | quiet |
| 2026-11-18 | `remote/io.github.Fractal-Neurons/pacta` | 2026-11-17T164329486725 -> 2026-11-18T080221168977 | 1 changed | quiet |
| 2026-11-18 | `remote/today.nyangi/oneul-nyangi` | 2026-11-17T164304312252 -> 2026-11-18T080220321771 | 2 changed | quiet |
| 2026-11-18 | `remote/dk.afbudsrejser/travel-search` | 2026-11-17T234341825577 -> 2026-11-18T080219420547 | 1 changed | quiet |
| 2026-11-18 | `remote/dev.tanod/document-to-markdown` | 2026-11-16T162930902973 -> 2026-11-18T080219693350 | 1 changed | quiet |
| 2026-11-18 | `remote/dev.tanod/docs` | 2026-11-16T162931524485 -> 2026-11-18T080220213281 | 1 changed | quiet |
| 2026-11-18 | `remote/io.github.Voopa-Corp/render-check` | 2026-11-17T234337019177 -> 2026-11-18T080217376967 | 3 changed | quiet |
| 2026-11-18 | `remote/dev.tanod/tanod` | 2026-11-16T162932063187 -> 2026-11-18T080220603563 | 2 changed | quiet |
| 2026-11-18 | `remote/network.moonbeam.next/paid-calls` | 2026-11-17T234312975346 -> 2026-11-18T080217746896 | 1 changed | review |
| 2026-11-18 | `remote/io.github.cryptoconspiracy/vurto-swap` | 2026-11-17T164453398968 -> 2026-11-18T080216912969 | 7 changed, 2 added | quiet |
| 2026-11-18 | `remote/com.eliteaiempire/newsletterproai` | 2026-11-17T234312436460 -> 2026-11-18T080219257033 | 1 changed | quiet |
| 2026-11-18 | `remote/global.uain/network` | 2026-11-16T163125790482 -> 2026-11-18T080214434073 | 1 changed | quiet |
| 2026-11-18 | `remote/com.multicinesortega/cartelera` | 2026-11-17T135605063560 -> 2026-11-18T080216146814 | 1 changed | quiet |
| 2026-11-18 | `remote/com.mondschein/hotel` | 2026-11-17T135603308587 -> 2026-11-18T080213668770 | 1 changed | quiet |
| 2026-11-18 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-17T234307706081 -> 2026-11-18T080213960941 | 17 changed | quiet |
| 2026-11-18 | `remote/com.trendtemplate/templates` | 2026-11-16T163110856058 -> 2026-11-18T080210960825 | 2 changed | quiet |
| 2026-11-18 | `remote/ai.trydock/dock` | 2026-11-17T234332806690 -> 2026-11-18T080211650462 | 5 added | quiet |
| 2026-11-18 | `remote/io.github.tidybytetools/api` | 2026-11-16T163046116885 -> 2026-11-18T080208902463 | 19 changed (every tool) | quiet |
| 2026-11-18 | `remote/io.github.customxx/solar-mcp` | 2026-11-16T163351841582 -> 2026-11-18T080208975631 | 1 changed | quiet |
| 2026-11-18 | `remote/com.toiseai/toise` | 2026-11-17T164121902108 -> 2026-11-18T080208748737 | 2 changed | quiet |
| 2026-11-18 | `remote/com.rightshold/rightshold` | 2026-11-17T031613962953 -> 2026-11-18T080207105226 | 2 changed | quiet |
| 2026-11-18 | `remote/ai.senaro/personal-finance` | 2026-11-16T122423294848 -> 2026-11-18T080205837622 | 1 changed | quiet |
| 2026-11-18 | `remote/io.github.joelp22-maker/referencesource` | 2026-11-17T164305717010 -> 2026-11-18T080204539085 | 1 changed | quiet |
| 2026-11-18 | `remote/io.github.magichourhq/magic-hour` | 2026-11-17T234257363227 -> 2026-11-18T080203683674 | 5 changed | quiet |
| 2026-11-18 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-17T135654290988 -> 2026-11-18T080204149916 | 2 changed | quiet |
| 2026-11-18 | `remote/app.qrcodecreator/qr-codes` | 2026-11-17T031545312730 -> 2026-11-18T080204563073 | 1 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 69514 substantive, 40875 that changed only numbers (a catalogue counter ticking, a date), 1077 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 59946 | 21593 | 38353 | 0 |
| `a2awire.com` | 3107 | 3107 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 461 | 461 | 0 | 0 |
| `civai.co` | 368 | 368 | 0 | 0 |
| `modevc.com` | 349 | 349 | 0 | 0 |
| `revmesh2074.workers.dev` | 297 | 258 | 39 | 0 |
| `sistaminuten.se` | 251 | 6 | 0 | 245 |
| `afbudsrejser.dk` | 250 | 6 | 0 | 244 |
| `akkilahdot.fi` | 250 | 6 | 0 | 244 |
| `restplass.no` | 250 | 6 | 0 | 244 |
| `socialloop.ai` | 242 | 242 | 0 | 0 |
| 10017 other operators | 43354 | 40771 | 2483 | 100 |
