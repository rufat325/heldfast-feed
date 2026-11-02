# MCP server tool changes

Last change observed 2026-11-02T18:54:31+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

70973 changes to a tool definition: 2981 npm releases (2735 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 67992 readings of hosted servers that found their tools changed; 3214 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-02 | `remote/io.taifoon/coordination-layer.1` | 2026-11-01T205305117565 -> 2026-11-02T185432522626 | 1 changed | review |
| 2026-11-02 | `remote/eu.tekaem/product-catalog` | 2026-11-02T163447430472 -> 2026-11-02T185437321317 | 3 changed (every tool) | quiet |
| 2026-11-02 | `remote/se.sistaminuten/travel-search` | 2026-11-02T163438451535 -> 2026-11-02T185431406393 | 1 changed | quiet |
| 2026-11-02 | `remote/pl.izoprofil.www/product-catalog` | 2026-11-02T163421028781 -> 2026-11-02T185433074623 | 3 changed (every tool) | quiet |
| 2026-11-02 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-11-01T135744042242 -> 2026-11-02T185429129003 | 2 changed | quiet |
| 2026-11-02 | `remote/io.github.JcJamet/ia-qa-eval` | 2026-11-02T163417179787 -> 2026-11-02T185429253802 | 1 changed | quiet |
| 2026-11-02 | `remote/pl.ecoprofil.www/product-catalog` | 2026-11-02T163413204265 -> 2026-11-02T185431472595 | 3 changed (every tool) | quiet |
| 2026-11-02 | `remote/com.youspot/youspot` | 2026-11-01T205306752834 -> 2026-11-02T185426210875 | 1 changed, 1 added | quiet |
| 2026-11-02 | `remote/org.budowlanka.www/product-catalog` | 2026-11-02T163405076216 -> 2026-11-02T185428795858 | 3 changed (every tool) | quiet |
| 2026-11-02 | `remote/pl.sandwich-panel.www/product-catalog` | 2026-11-02T163927017548 -> 2026-11-02T185424901398 | 3 changed (every tool) | quiet |
| 2026-11-02 | `remote/no.restplass/travel-search` | 2026-11-02T163619829288 -> 2026-11-02T185419439687 | 1 changed | quiet |
| 2026-11-02 | `remote/net.izoprofil.www/product-catalog` | 2026-11-02T163906981693 -> 2026-11-02T185423238680 | 3 changed (every tool) | quiet |
| 2026-11-02 | `remote/io.github.SKalinin909/tradingcalc` | 2026-11-02T163245149029 -> 2026-11-02T185416519973 | 10 changed | quiet |
| 2026-11-02 | `remote/com.tubesaku/creator-insights` | 2026-11-02T163255555984 -> 2026-11-02T185418715862 | 10 changed (every tool) | quiet |
| 2026-11-02 | `remote/com.kulicadvisory/aictionbot-werkbank` | 2026-11-02T163603502022 -> 2026-11-02T185416572629 | 3 added | quiet |
| 2026-11-02 | `remote/com.juzpost/mcp` | 2026-11-02T163602658212 -> 2026-11-02T185416225001 | 3 changed | quiet |
| 2026-11-02 | `remote/io.github.cryptoduke01/gloam` | 2026-10-31T202133831449 -> 2026-11-02T185414976995 | 1 added | quiet |
| 2026-11-02 | `remote/co.videoupscaler/video-upscaler` | 2026-11-02T163801384385 -> 2026-11-02T185414249035 | 1 changed | quiet |
| 2026-11-02 | `remote/dk.afbudsrejser/travel-search` | 2026-11-02T163532132041 -> 2026-11-02T185412108041 | 1 changed | quiet |
| 2026-11-02 | `remote/com.swishrjobs/swishrjobs` | 2026-11-02T163200968517 -> 2026-11-02T185414227556 | 2 changed, 1 added | quiet |
| 2026-11-02 | `remote/ai.swarmnest/mcp` | 2026-10-31T062131763058 -> 2026-11-02T185409019420 | 1 added | quiet |
| 2026-11-02 | `remote/io.github.ohad6k/viberaven-guides` | 2026-10-31T234845801952 -> 2026-11-02T185408440035 | 4 changed | quiet |
| 2026-11-02 | `remote/io.github.chungty/thetennisdesk` | 2026-11-02T163708896993 -> 2026-11-02T185408923786 | 2 changed | quiet |
| 2026-11-02 | `remote/eu.sandwich-panel.www/product-catalog` | 2026-11-02T163726974649 -> 2026-11-02T185410086158 | 3 changed (every tool) | quiet |
| 2026-11-02 | `remote/com.tradoshi/rankings` | 2026-11-02T163434656997 -> 2026-11-02T185404999349 | 2 changed | quiet |
| 2026-11-02 | `remote/com.patchmcp/patch` | 2026-11-02T163714198137 -> 2026-11-02T185404271267 | 2 changed | quiet |
| 2026-11-02 | `remote/io.github.imokokok/insight-oracle` | 2026-11-02T163714939893 -> 2026-11-02T185406240811 | 5 changed, 4 added | quiet |
| 2026-11-02 | `remote/org.izoprofil.www/product-catalog` | 2026-11-02T163704262740 -> 2026-11-02T185406504758 | 3 changed (every tool) | quiet |
| 2026-11-02 | `remote/eu.izoprofil.www/product-catalog` | 2026-11-02T163703463818 -> 2026-11-02T185406062587 | 3 changed (every tool) | quiet |
| 2026-11-02 | `remote/com.izoprofil.www/product-catalog` | 2026-11-02T163703709515 -> 2026-11-02T185406207852 | 3 changed (every tool) | quiet |
| 2026-11-02 | `remote/app.sunsetstrip/gta6` | 2026-11-02T163635285240 -> 2026-11-02T185402263315 | 3 changed | quiet |
| 2026-11-02 | `remote/ai.tendeck/crm` | 2026-11-02T163356822855 -> 2026-11-02T185401899317 | 2 added | quiet |
| 2026-11-02 | `remote/studio.gradients/mcp` | 2026-11-02T163653070129 -> 2026-11-02T185401552244 | 1 changed | quiet |
| 2026-11-02 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-01T153053819524 -> 2026-11-02T185359974095 | 3 changed | quiet |
| 2026-11-02 | `remote/fi.akkilahdot/travel-search` | 2026-11-02T163617501603 -> 2026-11-02T185359850983 | 1 changed | quiet |
| 2026-11-02 | `remote/es.proceres/proceres` | 2026-11-02T163008788331 -> 2026-11-02T185358667862 | 6 changed, 2 added | quiet |
| 2026-11-02 | `remote/com.sitecomb/check-website` | 2026-11-02T163556155533 -> 2026-11-02T185358499569 | 2 changed (every tool) | quiet |
| 2026-11-02 | `remote/io.printpal/printpal` | 2026-11-02T163003520809 -> 2026-11-02T185356732810 | 1 changed | quiet |
| 2026-11-02 | `remote/com.mouseedge/mouseedge-skipper.1` | 2026-11-02T163552442432 -> 2026-11-02T185357245721 | 1 changed, 2 added | quiet |
| 2026-11-02 | `remote/now.salesjobs/mcp` | 2026-11-02T163518320215 -> 2026-11-02T185355027023 | 1 changed | quiet |
| 2026-11-02 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-02T163542713309 -> 2026-11-02T185355997272 | 2 added | quiet |
| 2026-11-02 | `remote/com.straelo/relay` | 2026-11-02T065436828923 -> 2026-11-02T185352929474 | 4 changed | quiet |
| 2026-11-02 | `remote/io.github.opennodes-io/opennodes` | 2026-11-02T163201434907 -> 2026-11-02T185353038467 | 3 changed, 1 added | quiet |
| 2026-11-02 | `remote/com.organiqgeo/organiq` | 2026-11-02T162918411246 -> 2026-11-02T185353212958 | 39 changed | quiet |
| 2026-11-02 | `remote/io.github.MikhailSagalaev/openradar` | 2026-11-02T162915797264 -> 2026-11-02T185352612012 | 1 added | quiet |
| 2026-11-02 | `remote/dev.workers.quynguyenbac.quickbuild/agent-tools` | 2026-11-02T163150107090 -> 2026-11-02T185351974446 | 1 added | quiet |
| 2026-11-02 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-02T163456784176 -> 2026-11-02T185350251392 | 1 changed | quiet |
| 2026-11-02 | `remote/io.github.Fizzl13/presign-guard` | 2026-10-31T202108764207 -> 2026-11-02T185349478604 | 3 changed | quiet |
| 2026-11-02 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-02T163458464533 -> 2026-11-02T185350732944 | 2 changed | quiet |
| 2026-11-02 | `remote/xyz.t0ll/toll` | 2026-11-02T163439009309 -> 2026-11-02T185347559520 | 3 added | quiet |
| 2026-11-02 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-02T163405790375 -> 2026-11-02T185344167542 | 1 changed | quiet |
| 2026-11-02 | `remote/io.github.farenberglord-star/orb-studio` | 2026-11-02T163327035923 -> 2026-11-02T185343378800 | 1 changed | quiet |
| 2026-11-02 | `remote/co.neverapply/neverapply` | 2026-11-01T134922384227 -> 2026-11-02T185340553857 | 1 changed | quiet |
| 2026-11-02 | `remote/ai.shorti/shorti` | 2026-11-02T163350472777 -> 2026-11-02T185342346589 | 1 changed | quiet |
| 2026-11-02 | `remote/com.myndock/observatory` | 2026-11-02T163015537125 -> 2026-11-02T185340127570 | 1 changed, 3 added | quiet |
| 2026-11-02 | `remote/io.github.ppcvote/mindthread` | 2026-11-02T163000290578 -> 2026-11-02T185338684297 | 2 changed | quiet |
| 2026-11-02 | `remote/de.viafrei/mcp` | 2026-11-02T162751666646 -> 2026-11-02T185340172999 | 3 changed, 1 added | quiet |
| 2026-11-02 | `remote/com.remoshift/jobs` | 2026-11-02T163248574629 -> 2026-11-02T185337327958 | 1 changed | quiet |
| 2026-11-02 | `remote/com.mouseedge/mouseedge-skipper` | 2026-11-02T163241834623 -> 2026-11-02T185337011456 | 1 changed, 2 added | quiet |
| 2026-11-02 | `remote/com.radar-cnpj/radar-cnpj` | 2026-11-02T065449446213 -> 2026-11-02T185337486937 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 44928 substantive, 25255 that changed only numbers (a catalogue counter ticking, a date), 790 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 39567 | 15869 | 23698 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1245 | 1245 | 0 | 0 |
| `caseyjhand.com` | 313 | 313 | 0 | 0 |
| `sistaminuten.se` | 187 | 6 | 0 | 181 |
| `afbudsrejser.dk` | 186 | 6 | 0 | 180 |
| `akkilahdot.fi` | 186 | 6 | 0 | 180 |
| `restplass.no` | 186 | 6 | 0 | 180 |
| `socialloop.ai` | 180 | 180 | 0 | 0 |
| `remoshift.com` | 156 | 12 | 144 | 0 |
| `revmesh2074.workers.dev` | 146 | 128 | 18 | 0 |
| `fundinglandscape.com` | 143 | 89 | 54 | 0 |
| 7043 other operators | 26137 | 24727 | 1341 | 69 |
