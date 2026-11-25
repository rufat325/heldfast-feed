# MCP server tool changes

Last change observed 2026-11-25T03:50:33+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 18238 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 43073 hosted endpoints (read daily, and every four hours while they keep changing).

133985 changes to a tool definition: 5334 npm releases (5088 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 128651 readings of hosted servers that found their tools changed; 5037 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-25 | `remote/cn.tandiu/data` | 2026-11-23T185347164141 -> 2026-11-25T035036206348 | 1 added | quiet |
| 2026-11-25 | `remote/com.open5500/open5500` | 2026-11-24T165548889664 -> 2026-11-25T035032463997 | 1 changed | quiet |
| 2026-11-25 | `remote/com.notacompany/newsletter` | 2026-11-23T185327479249 -> 2026-11-25T035032000811 | 4 changed, 6 added, 3 removed | quiet |
| 2026-11-25 | `remote/com.qconsultai/qconsul-booking` | 2026-11-23T185917020574 -> 2026-11-25T035030391865 | 6 changed (every tool) | review |
| 2026-11-25 | `remote/xn--3ds443g.xn--s7y/duan-online` | 2026-11-24T170306531344 -> 2026-11-25T035029537072 | 4 changed | quiet |
| 2026-11-25 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-24T165526995777 -> 2026-11-25T035029523510 | 2 changed | quiet |
| 2026-11-25 | `remote/com.veridionmarkets/disclosures` | 2026-11-24T182918397507 -> 2026-11-25T035028151975 | 5 changed, 1 added | quiet |
| 2026-11-25 | `remote/ai.usedby/usedby` | 2026-11-24T170253722934 -> 2026-11-25T035027914133 | 1 changed | quiet |
| 2026-11-25 | `remote/io.taifoon/coordination-layer.1` | 2026-11-24T194724221189 -> 2026-11-25T035026810568 | 1 changed | quiet |
| 2026-11-25 | `remote/io.suverse.www/catalog` | 2026-11-24T194725405646 -> 2026-11-25T035027145577 | 3 changed | quiet |
| 2026-11-25 | `remote/se.sistaminuten/travel-search` | 2026-11-24T194723007528 -> 2026-11-25T035026190307 | 1 changed | quiet |
| 2026-11-25 | `remote/com.whizbrew/whizbrew` | 2026-11-24T165438110556 -> 2026-11-25T035024492723 | 2 changed | quiet |
| 2026-11-25 | `remote/uk.co.paintdial/paintdial` | 2026-11-24T170217261251 -> 2026-11-25T035024146505 | 1 changed | quiet |
| 2026-11-25 | `remote/org.omenz.www/agent-tools` | 2026-11-24T194719818838 -> 2026-11-25T035022991730 | 5 added | review |
| 2026-11-25 | `remote/io.github.jhonnysabino/moedux` | 2026-11-24T182842574700 -> 2026-11-25T035022497900 | 5 added | review |
| 2026-11-25 | `remote/io.suverse.versum/catalog` | 2026-11-24T194847012833 -> 2026-11-25T035024162940 | 3 changed | quiet |
| 2026-11-25 | `remote/io.github.brawlaphant/vealth` | 2026-11-24T165411877811 -> 2026-11-25T035021087015 | 1 changed, 2 added | quiet |
| 2026-11-25 | `remote/com.mfgcalcs/mfgcalcs` | 2026-11-24T170205947810 -> 2026-11-25T035021249897 | 1 changed | quiet |
| 2026-11-25 | `remote/me.divest/divestme` | 2026-11-23T185742420244 -> 2026-11-25T035018040686 | 1 changed | review |
| 2026-11-25 | `remote/com.theskillharbor/skill-harbor` | 2026-11-23T185110320847 -> 2026-11-25T035017840470 | 1 added | quiet |
| 2026-11-25 | `remote/to.stomp/editor` | 2026-11-24T182043021719 -> 2026-11-25T035013295309 | 1 changed, 2 added | quiet |
| 2026-11-25 | `remote/com.caelaralabs/social` | 2026-11-24T182016035466 -> 2026-11-25T035011168607 | 10 added | quiet |
| 2026-11-25 | `remote/ai.modulos/demo-booking` | 2026-11-24T170346988261 -> 2026-11-25T035011578148 | 1 changed | quiet |
| 2026-11-25 | `remote/com.tradermarketcap/prices` | 2026-11-23T185523504184 -> 2026-11-25T035009823615 | 2 added | quiet |
| 2026-11-25 | `remote/com.thefomite/fomite` | 2026-11-24T050501827622 -> 2026-11-25T035009255608 | 1 changed | quiet |
| 2026-11-25 | `remote/studio.gradients/mcp` | 2026-11-24T194753513043 -> 2026-11-25T035007811337 | 1 changed | quiet |
| 2026-11-25 | `remote/io.github.sathya-sankaran/yellide` | 2026-11-24T183018942538 -> 2026-11-25T035006792436 | 2 changed | quiet |
| 2026-11-25 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-11-24T050402509159 -> 2026-11-25T035006698576 | 1 changed | quiet |
| 2026-11-25 | `remote/io.github.EasyGerber/easygerber` | 2026-11-24T194752504343 -> 2026-11-25T035028929206 | 1 changed | quiet |
| 2026-11-25 | `remote/io.github.sudzikcoin/suverse-agent-assistant` | 2026-11-24T194731303840 -> 2026-11-25T035006365271 | 3 changed | quiet |
| 2026-11-25 | `remote/io.github.liad142/yedapo` | 2026-11-24T165828294791 -> 2026-11-25T035005717370 | 2 changed (every tool) | quiet |
| 2026-11-25 | `remote/fi.akkilahdot/travel-search` | 2026-11-24T194750611335 -> 2026-11-25T035004959572 | 1 changed | quiet |
| 2026-11-25 | `remote/ai.aim-shield/mcp` | 2026-11-23T185443583315 -> 2026-11-25T035004804381 | 1 added | quiet |
| 2026-11-25 | `remote/com.redgoodwine/redgoodwine` | 2026-11-23T081914754521 -> 2026-11-25T035003411978 | 1 changed | quiet |
| 2026-11-25 | `remote/tech.recoup-iq/uk-company-facts` | 2026-11-23T184846235793 -> 2026-11-25T035003598935 | 1 changed | quiet |
| 2026-11-25 | `remote/no.restplass/travel-search` | 2026-11-24T194728444544 -> 2026-11-25T035003379639 | 1 changed | quiet |
| 2026-11-25 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-24T050401985574 -> 2026-11-25T035003466800 | 2 changed (every tool) | quiet |
| 2026-11-25 | `remote/com.weverlabs/agentic-rails` | 2026-11-24T194756323493 -> 2026-11-25T035010537967 | 8 added | quiet |
| 2026-11-25 | `remote/com.swishrjobs/swishrjobs` | 2026-11-24T165832579595 -> 2026-11-25T035003442000 | 2 changed, 7 added | review |
| 2026-11-25 | `remote/io.github.veredamonte-glitch/verithic` | 2026-11-24T170219947224 -> 2026-11-25T035004030063 | 5 changed | quiet |
| 2026-11-25 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-24T194746226794 -> 2026-11-25T035006663571 | 3 changed | quiet |
| 2026-11-25 | `remote/com.rowhousesoftware/playtable` | 2026-11-24T164957759927 -> 2026-11-25T035000354886 | 1 changed, 1 added | quiet |
| 2026-11-25 | `remote/ai.staffbots/dispatch` | 2026-11-24T165812712128 -> 2026-11-25T035000162404 | 2 added | quiet |
| 2026-11-25 | `remote/ru.uplanny/uplanny` | 2026-11-23T185331056690 -> 2026-11-25T035000450236 | 1 changed | quiet |
| 2026-11-25 | `remote/dev.pdfops/pdfops-mcp` | 2026-11-24T050354936861 -> 2026-11-25T034959526056 | 1 changed, 1 added | quiet |
| 2026-11-25 | `remote/io.github.Schoasch/backtesting-arena` | 2026-11-24T170131869295 -> 2026-11-25T034958507885 | 1 changed | quiet |
| 2026-11-25 | `remote/dk.afbudsrejser/travel-search` | 2026-11-24T194720386592 -> 2026-11-25T034958512630 | 1 changed | quiet |
| 2026-11-25 | `remote/com.withsilex/x402-mcp` | 2026-11-23T185354939587 -> 2026-11-25T034957494211 | 4 added | review |
| 2026-11-25 | `remote/ai.tracyinterview/tracy-ai-interviewer` | 2026-11-23T185303630708 -> 2026-11-25T034959252056 | 5 changed | quiet |
| 2026-11-25 | `remote/com.whoreadsthe/agents` | 2026-11-24T050349468038 -> 2026-11-25T034957433882 | 1 added | quiet |
| 2026-11-25 | `remote/io.github.ohad6k/viberaven-guides` | 2026-11-24T194715912465 -> 2026-11-25T034955141234 | 2 changed | quiet |
| 2026-11-25 | `remote/dev.workers.stratcheck-ai.neutrino-x402-api/strategy-check` | 2026-11-23T184649464260 -> 2026-11-25T034954606436 | 1 changed | review |
| 2026-11-25 | `remote/com.caelaralabs/seo` | 2026-11-24T182431865705 -> 2026-11-25T034955110740 | 10 added | quiet |
| 2026-11-25 | `remote/io.github.kkfir13/valuedge` | 2026-11-24T194714558469 -> 2026-11-25T034954293173 | 2 changed, 1 added | quiet |
| 2026-11-25 | `remote/io.github.Red-Center-Studio/nocode-migrator` | 2026-11-24T164854119298 -> 2026-11-25T034954824313 | 1 changed | quiet |
| 2026-11-25 | `remote/io.trylode/lode` | 2026-11-24T050347612790 -> 2026-11-25T034953725433 | 1 changed | quiet |
| 2026-11-25 | `remote/com.zola/zola` | 2026-11-24T181559373947 -> 2026-11-25T034950911762 | 16 changed | review |
| 2026-11-25 | `remote/dev.turva/turva-mcp` | 2026-11-24T164745999713 -> 2026-11-25T034950033411 | 1 changed | quiet |
| 2026-11-25 | `remote/ai.rfsrisk/syri` | 2026-11-24T182632624491 -> 2026-11-25T034949772068 | 1 changed, 1 added | review |
| 2026-11-25 | `remote/site.aeon-labs/stratify` | 2026-11-24T050342249777 -> 2026-11-25T034950754009 | 4 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 89581 substantive, 43202 that changed only numbers (a catalogue counter ticking, a date), 1202 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 73018 | 32811 | 40207 | 0 |
| `a2awire.com` | 3838 | 3838 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 528 | 528 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 401 | 401 | 0 | 0 |
| `revmesh2074.workers.dev` | 369 | 314 | 55 | 0 |
| `sistaminuten.se` | 280 | 7 | 0 | 273 |
| `afbudsrejser.dk` | 279 | 7 | 0 | 272 |
| `akkilahdot.fi` | 279 | 7 | 0 | 272 |
| `restplass.no` | 279 | 7 | 0 | 272 |
| `socialloop.ai` | 270 | 270 | 0 | 0 |
| 11328 other operators | 51623 | 48570 | 2940 | 113 |
