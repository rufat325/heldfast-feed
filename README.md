# MCP server tool changes

Last change observed 2026-11-01T06:54:55+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

65663 changes to a tool definition: 2775 npm releases (2529 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 62888 readings of hosted servers that found their tools changed; 3116 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-01 | `remote/io.taifoon/coordination-layer.1` | 2026-10-31T130314854814 -> 2026-11-01T065456449029 | 1 changed | review |
| 2026-11-01 | `remote/uk.co.gigstamp/gigstamp` | 2026-10-31T202117989272 -> 2026-11-01T065455526241 | 2 changed | quiet |
| 2026-11-01 | `remote/se.sistaminuten/travel-search` | 2026-10-31T234856317455 -> 2026-11-01T065456679986 | 1 changed | quiet |
| 2026-11-01 | `remote/com.intoperson.tools/lottery-numbers` | 2026-10-31T202111939222 -> 2026-11-01T065451925543 | 2 changed | quiet |
| 2026-11-01 | `remote/com.thefomite/fomite` | 2026-10-31T062133864074 -> 2026-11-01T065451180065 | 1 changed | quiet |
| 2026-11-01 | `remote/com.sapiensinteticos/sapiens` | 2026-10-31T130254940874 -> 2026-11-01T065451806643 | 17 changed | quiet |
| 2026-11-01 | `remote/no.restplass/travel-search` | 2026-10-31T234853542626 -> 2026-11-01T065449525350 | 1 changed | quiet |
| 2026-11-01 | `remote/ai.satohub/onchain-agents` | 2026-10-31T130014463322 -> 2026-11-01T065447870064 | 1 changed | quiet |
| 2026-11-01 | `remote/studio.gradients/mcp` | 2026-10-31T234927990550 -> 2026-11-01T065445331687 | 1 changed | quiet |
| 2026-11-01 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-10-31T062139282307 -> 2026-11-01T065443576278 | 1 changed | quiet |
| 2026-11-01 | `remote/fi.akkilahdot/travel-search` | 2026-10-31T234925069916 -> 2026-11-01T065443515433 | 1 changed | quiet |
| 2026-11-01 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-10-31T234927937087 -> 2026-11-01T065443737524 | 3 changed | quiet |
| 2026-11-01 | `remote/io.ddx.pg/archive` | 2026-10-31T144900326262 -> 2026-11-01T065444308851 | 1 changed | quiet |
| 2026-11-01 | `remote/dk.afbudsrejser/travel-search` | 2026-10-31T234848776954 -> 2026-11-01T065444369398 | 1 changed | quiet |
| 2026-11-01 | `remote/si.mttr/mttr` | 2026-10-31T125829304937 -> 2026-11-01T065441112104 | 18 changed | quiet |
| 2026-11-01 | `remote/com.techfabric/techfabric` | 2026-10-30T210625014910 -> 2026-11-01T065441661585 | 2 changed | quiet |
| 2026-11-01 | `remote/com.86hc/hongkong-company` | 2026-10-30T210632326770 -> 2026-11-01T065443751485 | 1 changed | quiet |
| 2026-11-01 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-10-31T062128604399 -> 2026-11-01T065440244559 | 4 changed | quiet |
| 2026-11-01 | `remote/com.swarmmemo/bulletin.1` | 2026-10-31T062150587697 -> 2026-11-01T065441100730 | 4 changed | quiet |
| 2026-11-01 | `remote/com.swarmmemo/bulletin` | 2026-10-31T062150434822 -> 2026-11-01T065440393876 | 4 changed | quiet |
| 2026-11-01 | `remote/com.strongsaga/gear-lookup` | 2026-10-30T210625888855 -> 2026-11-01T065439859762 | 1 changed | quiet |
| 2026-11-01 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-31T234903804064 -> 2026-11-01T065437989094 | 1 changed | quiet |
| 2026-11-01 | `remote/io.github.davidgringras/scrutica` | 2026-10-31T234901072254 -> 2026-11-01T065436910656 | 1 changed | quiet |
| 2026-11-01 | `remote/fr.synergieloc/immobilier` | 2026-10-31T234845261255 -> 2026-11-01T065437906021 | 12 added | quiet |
| 2026-11-01 | `remote/com.saylorinnovations/data` | 2026-10-30T132805013135 -> 2026-11-01T065437347199 | 10 changed, 1 added | review |
| 2026-11-01 | `remote/com.remoshift/jobs` | 2026-10-31T234855168366 -> 2026-11-01T065435721829 | 1 changed | quiet |
| 2026-11-01 | `remote/sg.tanatasa/tanatasa` | 2026-10-31T144902802621 -> 2026-11-01T065435796087 | 9 changed, 2 added, 1 removed | quiet |
| 2026-11-01 | `remote/gl.parse/mcp` | 2026-10-31T234828105564 -> 2026-11-01T065436360424 | 6 changed, 6 added | quiet |
| 2026-11-01 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-31T202115441793 -> 2026-11-01T065435039612 | 3 changed | quiet |
| 2026-11-01 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-31T130055212384 -> 2026-11-01T065434640718 | 3 changed, 1 added | quiet |
| 2026-11-01 | `remote/com.0xpi.sdsentry/sds-lookup` | 2026-10-31T125931861472 -> 2026-11-01T065433904361 | 1 changed | quiet |
| 2026-11-01 | `remote/app.openkrill/site-check` | 2026-10-31T130042615599 -> 2026-11-01T065434217164 | 1 changed | quiet |
| 2026-11-01 | `remote/me.phor/phorme-training` | 2026-10-31T130021511035 -> 2026-11-01T065432694105 | 1 changed, 5 added | quiet |
| 2026-11-01 | `remote/com.jojapi/sms-verify` | 2026-10-31T125624226312 -> 2026-11-01T065435608002 | 1 changed | quiet |
| 2026-11-01 | `remote/ai.rokha/rokha` | 2026-10-31T062133782620 -> 2026-11-01T065433226194 | 7 changed | quiet |
| 2026-11-01 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-31T062120986916 -> 2026-11-01T065434019886 | 1 changed | quiet |
| 2026-11-01 | `remote/com.straelo/relay` | 2026-10-31T062133791953 -> 2026-11-01T065432422731 | 2 changed, 4 added, 4 removed | quiet |
| 2026-11-01 | `remote/com.restaurantdoctorai/profit-check` | 2026-10-31T130002661484 -> 2026-11-01T065431804422 | 1 changed | quiet |
| 2026-11-01 | `remote/com.peerlace/peerlace` | 2026-10-30T132658994452 -> 2026-11-01T065432885332 | 4 changed, 11 added | quiet |
| 2026-11-01 | `remote/app.sallim/korea-realty` | 2026-10-31T125858047512 -> 2026-11-01T065434145252 | 1 changed | quiet |
| 2026-11-01 | `remote/com.probativegrowth/legal-marketing-data` | 2026-10-31T234833412398 -> 2026-11-01T065430854133 | 6 changed | quiet |
| 2026-11-01 | `remote/com.odilelabs/odile` | 2026-10-31T202058844794 -> 2026-11-01T065431633918 | 10 changed | quiet |
| 2026-11-01 | `remote/com.multicinesortega/cartelera` | 2026-10-31T234844115896 -> 2026-11-01T065432052237 | 1 changed | quiet |
| 2026-11-01 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-10-31T234842559682 -> 2026-11-01T065431101401 | 6 changed, 58 removed | quiet |
| 2026-11-01 | `remote/dev.benys/the-pit` | 2026-10-31T125925755735 -> 2026-11-01T065430048098 | 2 changed | quiet |
| 2026-11-01 | `remote/com.partstable/partstable` | 2026-10-31T125820173123 -> 2026-11-01T065430174708 | 1 changed | quiet |
| 2026-11-01 | `remote/com.mrrledger/mrrledger` | 2026-10-31T125834180891 -> 2026-11-01T065427481671 | 1 changed | quiet |
| 2026-11-01 | `remote/io.github.horizon-pulse/horizon-pulse` | 2026-10-31T202035990587 -> 2026-11-01T065425895708 | 5 changed | quiet |
| 2026-11-01 | `remote/io.github.Clipform/mcp-server` | 2026-10-30T063119381139 -> 2026-11-01T065424929272 | 2 changed | quiet |
| 2026-11-01 | `remote/io.github.valuein/mcp-sec-edgar` | 2026-10-31T202100635130 -> 2026-11-01T065423969318 | 9 changed, 1 added, 21 removed | quiet |
| 2026-11-01 | `remote/com.boxerbook/boxing` | 2026-10-31T234830413486 -> 2026-11-01T065423496132 | 1 changed | quiet |
| 2026-11-01 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-31T202032825238 -> 2026-11-01T065423303196 | 2 changed | quiet |
| 2026-11-01 | `remote/com.cielstay/cielstay` | 2026-10-31T202053988145 -> 2026-11-01T065421757378 | 2 changed | quiet |
| 2026-11-01 | `remote/ai.certscore/mcp-light` | 2026-10-30T210552190112 -> 2026-11-01T065422194125 | 3 changed | quiet |
| 2026-11-01 | `remote/io.github.industrial-platform-ai/research-brief` | 2026-10-30T063118387889 -> 2026-11-01T065422950844 | 1 changed | quiet |
| 2026-11-01 | `remote/com.thefilmradar/filmlab` | 2026-10-31T234829363456 -> 2026-11-01T065420512336 | 1 changed, 3 added | quiet |
| 2026-11-01 | `remote/com.problee/problee` | 2026-10-31T202054247053 -> 2026-11-01T065420922278 | 4 changed, 1 added | quiet |
| 2026-11-01 | `remote/com.oneuedu.mcp/oneu-education` | 2026-10-31T062109508654 -> 2026-11-01T065421141071 | 5 changed, 1 added | quiet |
| 2026-11-01 | `remote/co.getclippy/clippy` | 2026-10-30T210550876170 -> 2026-11-01T065420469851 | 2 changed | quiet |
| 2026-11-01 | `remote/cloud.dchub/mcp-server` | 2026-10-31T125106487531 -> 2026-11-01T065420823186 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 43358 substantive, 21540 that changed only numbers (a catalogue counter ticking, a date), 765 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 35899 | 15834 | 20065 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1127 | 1127 | 0 | 0 |
| `caseyjhand.com` | 289 | 289 | 0 | 0 |
| `sistaminuten.se` | 181 | 6 | 0 | 175 |
| `afbudsrejser.dk` | 180 | 6 | 0 | 174 |
| `akkilahdot.fi` | 180 | 6 | 0 | 174 |
| `restplass.no` | 180 | 6 | 0 | 174 |
| `socialloop.ai` | 174 | 174 | 0 | 0 |
| `remoshift.com` | 150 | 10 | 140 | 0 |
| `revmesh2074.workers.dev` | 146 | 128 | 18 | 0 |
| `fundinglandscape.com` | 138 | 87 | 51 | 0 |
| 6730 other operators | 24678 | 23344 | 1266 | 68 |
