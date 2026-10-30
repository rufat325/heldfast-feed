# MCP server tool changes

Last change observed 2026-10-30T15:24:14+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

64392 changes to a tool definition: 2657 npm releases (2411 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 61735 readings of hosted servers that found their tools changed; 3015 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-30 | `remote/no.restplass/travel-search` | 2026-10-30T133020567590 -> 2026-10-30T152414966306 | 1 changed | quiet |
| 2026-10-30 | `remote/dk.afbudsrejser/travel-search` | 2026-10-30T132936024479 -> 2026-10-30T152411447698 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.ZacharyVorsteg/provenplaza-agent-mcp` | 2026-10-28T133030109839 -> 2026-10-30T152355396132 | 1 changed, 6 added | quiet |
| 2026-10-30 | `remote/fun.pumpdata/pumpdata` | 2026-10-30T063131180025 -> 2026-10-30T152356405726 | 1 changed | quiet |
| 2026-10-30 | `remote/studio.gradients/mcp` | 2026-10-30T133045664047 -> 2026-10-30T152353496319 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.prof-1t/postlyra-mcp` | 2026-10-29T104241306843 -> 2026-10-30T152354888881 | 3 changed | quiet |
| 2026-10-30 | `remote/io.github.SoapyRED/freightutils` | 2026-10-30T133042430588 -> 2026-10-30T152353912831 | 5 changed | quiet |
| 2026-10-30 | `remote/io.github.CodeWever/wever-labs-products` | 2026-10-30T063140750648 -> 2026-10-30T152351311743 | 5 changed | quiet |
| 2026-10-30 | `remote/fi.akkilahdot/travel-search` | 2026-10-30T133018722002 -> 2026-10-30T152351728139 | 1 changed | quiet |
| 2026-10-30 | `remote/se.sistaminuten/travel-search` | 2026-10-30T132916263519 -> 2026-10-30T152351682719 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.untitledfinancial/dpx` | 2026-10-30T132444751216 -> 2026-10-30T152347615962 | 5 changed | quiet |
| 2026-10-30 | `remote/com.swarmmemo/bulletin.1` | 2026-10-30T132854752817 -> 2026-10-30T152345034020 | 3 changed | quiet |
| 2026-10-30 | `remote/com.swarmmemo/bulletin` | 2026-10-30T063135889400 -> 2026-10-30T152344591315 | 2 changed | quiet |
| 2026-10-30 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-30T132835264075 -> 2026-10-30T152342574396 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.sorindecu/vibeshipped` | 2026-10-28T133736148860 -> 2026-10-30T152340358232 | 2 changed | quiet |
| 2026-10-30 | `remote/com.remoshift/jobs` | 2026-10-30T132746140309 -> 2026-10-30T152339045729 | 1 changed | quiet |
| 2026-10-30 | `remote/com.pourwire/pourwire` | 2026-10-28T212353971610 -> 2026-10-30T152336887431 | 2 changed (every tool) | quiet |
| 2026-10-30 | `remote/com.proxmint/mcp` | 2026-10-29T133506755809 -> 2026-10-30T152333170343 | 2 changed | quiet |
| 2026-10-30 | `remote/estate.new/listings` | 2026-10-29T104118543731 -> 2026-10-30T152334190997 | 1 changed | quiet |
| 2026-10-30 | `remote/com.lordevo/shop` | 2026-10-29T212826959766 -> 2026-10-30T152335971551 | 6 changed, 3 added | quiet |
| 2026-10-30 | `remote/com.myanimetracker/myanimetracker-account` | 2026-10-29T212842426375 -> 2026-10-30T152326271361 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.snefhew/factline-kyc` | 2026-10-28T212328506251 -> 2026-10-30T152320891525 | 26 changed | quiet |
| 2026-10-30 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt.2` | 2026-10-30T131838377438 -> 2026-10-30T152319738824 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.Val7h/dados-b3` | 2026-10-28T131606939104 -> 2026-10-30T152316946027 | 7 changed | quiet |
| 2026-10-30 | `remote/com.movingplace/mcp` | 2026-10-29T103822290790 -> 2026-10-30T152314346164 | 16 added | quiet |
| 2026-10-30 | `remote/com.ce-net/ce-net.1` | 2026-10-30T131714182576 -> 2026-10-30T152315385184 | 4 changed, 11 added | quiet |
| 2026-10-30 | `remote/com.esimgomobile/esimgomobile` | 2026-10-30T132227607113 -> 2026-10-30T152311260084 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.obrientt/landfiller` | 2026-10-30T132150102358 -> 2026-10-30T152310494122 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.mk-career-planning/jp-edinet` | 2026-10-28T132242639932 -> 2026-10-30T152310352055 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.Fizzl13/ichimoku-signal` | 2026-10-29T063157575818 -> 2026-10-30T152308009441 | 1 changed, 1 added | quiet |
| 2026-10-30 | `remote/io.github.horizon-pulse/horizon-pulse` | 2026-10-30T131942243619 -> 2026-10-30T152306015538 | 2 added | quiet |
| 2026-10-30 | `remote/com.getcloseknit/close-knit` | 2026-10-30T131945097288 -> 2026-10-30T152304504421 | 4 changed | quiet |
| 2026-10-30 | `remote/online.golfdata/golf-clubs` | 2026-10-30T131920694215 -> 2026-10-30T152304589867 | 1 changed | quiet |
| 2026-10-30 | `remote/app.vercel.fork-for-agents/fork` | 2026-10-30T131924572568 -> 2026-10-30T152302693322 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-30T131746755879 -> 2026-10-30T152301522491 | 3 changed | quiet |
| 2026-10-30 | `remote/io.github.snefhew/factline` | 2026-10-28T212302675036 -> 2026-10-30T152302147256 | 41 changed | quiet |
| 2026-10-30 | `remote/io.github.WellApp-ai/well-mcp` | 2026-10-29T212751660641 -> 2026-10-30T152259078896 | 27 changed, 1 added | quiet |
| 2026-10-30 | `remote/com.editalmd/editalmd` | 2026-10-30T131839216038 -> 2026-10-30T152259615019 | 1 changed | quiet |
| 2026-10-30 | `remote/com.webotee/amazon-product-research-mcp` | 2026-10-29T103153665713 -> 2026-10-30T152254245832 | 2 changed | quiet |
| 2026-10-30 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-10-29T212749146735 -> 2026-10-30T152254678559 | 2 changed | quiet |
| 2026-10-30 | `remote/com.foldlaboratories/art` | 2026-10-28T212225256016 -> 2026-10-30T152255061877 | 2 changed, 1 added, 7 removed | quiet |
| 2026-10-30 | `remote/ai.nobi/shop-nobi` | 2026-10-30T063118735989 -> 2026-10-30T152251280352 | 1 changed | quiet |
| 2026-10-30 | `remote/uk.co.buildbatch/buildbatch` | 2026-10-30T131700699848 -> 2026-10-30T152249372969 | 4 changed (every tool) | quiet |
| 2026-10-30 | `remote/app.vercel.automaton-tx-explainer/base-tools` | 2026-10-30T131630146473 -> 2026-10-30T152247515383 | 5 changed, 1 added | quiet |
| 2026-10-30 | `remote/com.reglyze/mcp` | 2026-10-30T131427389508 -> 2026-10-30T152247043158 | 3 changed | quiet |
| 2026-10-30 | `remote/co.proofsource/proofsource` | 2026-10-30T131608656582 -> 2026-10-30T152246240636 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.Adenion/blog2social-api-mcp` | 2026-10-28T131319221043 -> 2026-10-30T152244141700 | 9 changed, 1 added, 1 removed (every tool) | quiet |
| 2026-10-30 | `remote/app.flaim/mcp` | 2026-10-30T131027843030 -> 2026-10-30T152243377815 | 2 changed | quiet |
| 2026-10-30 | `remote/com.logimu/shopping-mcp` | 2026-10-30T063059968496 -> 2026-10-30T152241558615 | 4 changed | quiet |
| 2026-10-30 | `remote/com.xn--5kvtwv52d/jizhineng-mcp-gateway` | 2026-10-30T063147829817 -> 2026-10-30T133118606051 | 2 added | quiet |
| 2026-10-30 | `remote/io.github.seekdaseek/agentfeed` | 2026-10-25T102716121138 -> 2026-10-30T133115900336 | 19 changed, 3 added | quiet |
| 2026-10-30 | `remote/io.github.mk-career-planning/x402-safety-kit` | 2026-10-19T135617333164 -> 2026-10-30T133114744669 | 1 changed | quiet |
| 2026-10-30 | `remote/com.theprotoclinical/commerce` | 2026-10-22T233941206989 -> 2026-10-30T133107214302 | 4 changed | quiet |
| 2026-10-30 | `remote/com.riddle/creator` | 2026-10-20T104645792704 -> 2026-10-30T133103225743 | 25 changed, 11 added, 4 removed | quiet |
| 2026-10-30 | `remote/com.mintlify/searchmcp` | 2026-10-22T233940384027 -> 2026-10-30T133053144835 | 1 changed | quiet |
| 2026-10-30 | `remote/studio.gradients/mcp` | 2026-10-30T063143345509 -> 2026-10-30T133045664047 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.SoapyRED/freightutils` | 2026-10-30T063143507435 -> 2026-10-30T133042430588 | 25 changed (every tool) | quiet |
| 2026-10-30 | `remote/io.github.zambodotdev/zambo` | 2026-10-29T104524133360 -> 2026-10-30T133036384858 | 3 changed | quiet |
| 2026-10-30 | `remote/dev.zambo/zambo` | 2026-10-29T104524118900 -> 2026-10-30T133036408531 | 3 changed | quiet |
| 2026-10-30 | `remote/app.web.yutai-mcp/yutai-mcp` | 2026-10-17T060427729570 -> 2026-10-30T133036721374 | 1 changed, 2 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 42220 substantive, 21438 that changed only numbers (a catalogue counter ticking, a date), 734 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 35898 | 15833 | 20065 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1126 | 1126 | 0 | 0 |
| `caseyjhand.com` | 282 | 282 | 0 | 0 |
| `sistaminuten.se` | 174 | 6 | 0 | 168 |
| `afbudsrejser.dk` | 173 | 6 | 0 | 167 |
| `akkilahdot.fi` | 173 | 6 | 0 | 167 |
| `restplass.no` | 173 | 6 | 0 | 167 |
| `socialloop.ai` | 167 | 167 | 0 | 0 |
| `remoshift.com` | 143 | 10 | 133 | 0 |
| `fundinglandscape.com` | 133 | 85 | 48 | 0 |
| `revmesh2074.workers.dev` | 129 | 116 | 13 | 0 |
| 6580 other operators | 23480 | 22236 | 1179 | 65 |
