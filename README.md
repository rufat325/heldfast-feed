# MCP server tool changes

Last change observed 2026-10-30T13:31:15+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

64343 changes to a tool definition: 2657 npm releases (2411 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 61686 readings of hosted servers that found their tools changed; 3015 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-30 | `remote/com.youspot/youspot` | 2026-10-23T233429748902 -> 2026-10-30T133035063652 | 61 changed, 1 added, 1 removed | quiet |
| 2026-10-30 | `remote/com.naxytra/xytara-mcp-executor` | 2026-10-26T153219349777 -> 2026-10-30T133032832049 | 13 changed, 1 removed | review |
| 2026-10-30 | `remote/no.restplass/travel-search` | 2026-10-30T063149097364 -> 2026-10-30T133020567590 | 1 changed | quiet |
| 2026-10-30 | `remote/fi.akkilahdot/travel-search` | 2026-10-30T063141708229 -> 2026-10-30T133018722002 | 1 changed | quiet |
| 2026-10-30 | `remote/tech.spriteforge/editor` | 2026-10-26T133717912645 -> 2026-10-30T133017584718 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.Atenkai/smasher-studio` | 2026-10-17T060410552261 -> 2026-10-30T133016947916 | 1 changed | quiet |
| 2026-10-30 | `remote/dev.pressmark/pressmark` | 2026-10-29T212908496589 -> 2026-10-30T133017776758 | 6 changed (every tool) | quiet |
| 2026-10-30 | `remote/app.postel/postel` | 2026-10-28T133456729138 -> 2026-10-30T133018036411 | 1 changed | quiet |
| 2026-10-30 | `remote/io.huntertech/vendor-insights.3` | 2026-10-26T211531882709 -> 2026-10-30T133006009028 | 3 changed | quiet |
| 2026-10-30 | `remote/io.github.cryptoduke01/gloam` | 2026-10-26T133747071952 -> 2026-10-30T133004309034 | 1 changed | quiet |
| 2026-10-30 | `remote/me.fone.www/agents` | 2026-10-17T060439358990 -> 2026-10-30T133001572834 | 1 added | quiet |
| 2026-10-30 | `remote/com.kineticist/mcp-server` | 2026-10-20T052317758369 -> 2026-10-30T132956797755 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.fmind/portfolio` | 2026-10-17T060343917142 -> 2026-10-30T132949599602 | 3 changed | quiet |
| 2026-10-30 | `remote/de.drgsystem/medical-catalogs` | 2026-10-17T060432861586 -> 2026-10-30T132951568388 | 24 changed, 8 added | quiet |
| 2026-10-30 | `remote/ru.vedarai/mcp` | 2026-10-30T063141020608 -> 2026-10-30T132945295596 | 1 changed | quiet |
| 2026-10-30 | `remote/app.vaultbags/vaultbags` | 2026-10-17T055858785086 -> 2026-10-30T132942539934 | 3 added | quiet |
| 2026-10-30 | `remote/dk.afbudsrejser/travel-search` | 2026-10-30T063143827625 -> 2026-10-30T132936024479 | 1 changed | quiet |
| 2026-10-30 | `remote/com.86hc/hongkong-company` | 2026-10-28T062227726522 -> 2026-10-30T132935278645 | 2 changed | quiet |
| 2026-10-30 | `remote/io.github.cyanheads/wikipedia-mcp-server` | 2026-10-24T125755966934 -> 2026-10-30T132928030018 | 1 changed, 1 added | quiet |
| 2026-10-30 | `remote/io.taifoon/coordination-layer.1` | 2026-10-30T063200235181 -> 2026-10-30T132920831368 | 1 changed | review |
| 2026-10-30 | `remote/ai.startuphub/startuphub` | 2026-10-21T122407721440 -> 2026-10-30T132918564508 | 9 added | quiet |
| 2026-10-30 | `remote/se.sistaminuten/travel-search` | 2026-10-30T063159575235 -> 2026-10-30T132916263519 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.ohad6k/viberaven-guides` | 2026-10-28T133346947097 -> 2026-10-30T132912964403 | 3 changed | quiet |
| 2026-10-30 | `remote/media.thecoop/the-coop` | 2026-10-29T104359898912 -> 2026-10-30T132908870763 | 3 added | quiet |
| 2026-10-30 | `remote/net.bigfloppy.utils/utils` | 2026-10-26T133655239052 -> 2026-10-30T132907970874 | 1 added | quiet |
| 2026-10-30 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-25T191859493020 -> 2026-10-30T132908170599 | 1 changed | quiet |
| 2026-10-30 | `remote/com.menloinsurance/mcp` | 2026-10-30T063159096531 -> 2026-10-30T132904284728 | 3 changed | quiet |
| 2026-10-30 | `remote/io.github.cyanheads/uk-police-crime-mcp-server` | 2026-10-18T113317484466 -> 2026-10-30T132859990499 | 2 changed | quiet |
| 2026-10-30 | `remote/io.github.cyanheads/uk-legislation-mcp-server` | 2026-10-17T060357033195 -> 2026-10-30T132859915486 | 3 changed | quiet |
| 2026-10-30 | `remote/com.klarefi/mcp` | 2026-10-10T202059030052 -> 2026-10-30T132859751653 | 4 changed | quiet |
| 2026-10-30 | `remote/io.github.fursatdev-tech/fursat` | 2026-09-23T161026556179 -> 2026-10-30T132854317946 | 3 changed (every tool) | quiet |
| 2026-10-30 | `remote/ch.swisslivingindex/swiss-living-index` | 2026-10-25T102527772608 -> 2026-10-30T132855213619 | 1 changed | quiet |
| 2026-10-30 | `remote/com.trustbaselab/rcb-data` | 2026-10-26T153232233748 -> 2026-10-30T132853705563 | 1 changed | quiet |
| 2026-10-30 | `remote/com.swarmmemo/bulletin.1` | 2026-10-30T063136173736 -> 2026-10-30T132854752817 | 2 changed | quiet |
| 2026-10-30 | `remote/io.github.Tomalarrrr/cyclesite-mcp-server` | 2026-10-28T212415861260 -> 2026-10-30T132849910521 | 2 changed | quiet |
| 2026-10-30 | `remote/eu.gridgarden/studio` | 2026-10-24T190427023263 -> 2026-10-30T132851579404 | 1 changed | quiet |
| 2026-10-30 | `remote/dev.upfork/upfork` | 2026-10-27T210152953692 -> 2026-10-30T132850274133 | 6 changed, 1 added, 31 removed | quiet |
| 2026-10-30 | `remote/io.github.JacobiusMakes/stienhardt-store` | 2026-10-22T233932645909 -> 2026-10-30T132845326078 | 4 changed | quiet |
| 2026-10-30 | `remote/com.googleapis.stitch/mcp` | 2026-10-21T122036375265 -> 2026-10-30T132845913106 | 3 changed | quiet |
| 2026-10-30 | `remote/com.blitzreels/blitzreels` | 2026-10-27T112333505639 -> 2026-10-30T132845551961 | 2 changed | quiet |
| 2026-10-30 | `remote/com.adadiamonds/ada-diamonds` | 2026-10-24T112903346890 -> 2026-10-30T132839687468 | 8 changed (every tool) | quiet |
| 2026-10-30 | `remote/com.traffalyzer/traffalyzer` | 2026-10-29T104334964738 -> 2026-10-30T132838426386 | 1 changed | quiet |
| 2026-10-30 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-30T063134850247 -> 2026-10-30T132835264075 | 1 changed | quiet |
| 2026-10-30 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-28T133415953691 -> 2026-10-30T132832080230 | 3 added | quiet |
| 2026-10-30 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-10-25T225054032546 -> 2026-10-30T132827591660 | 8 changed, 43 added, 1 removed | quiet |
| 2026-10-30 | `remote/com.thenewengineer/hvac` | 2026-10-23T233425705178 -> 2026-10-30T132821945650 | 2 changed | quiet |
| 2026-10-30 | `remote/io.github.exquad/thecablecode` | 2026-10-26T052304338173 -> 2026-10-30T132818499088 | 6 changed, 12 added | review |
| 2026-10-30 | `remote/com.seqbench/workbench` | 2026-10-26T133304388146 -> 2026-10-30T132817978981 | 5 changed | quiet |
| 2026-10-30 | `remote/com.textforagents/collusion-sentinel-agent-markets` | 2026-10-26T133518730139 -> 2026-10-30T132814210536 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 42180 substantive, 21433 that changed only numbers (a catalogue counter ticking, a date), 730 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 35898 | 15833 | 20065 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1126 | 1126 | 0 | 0 |
| `caseyjhand.com` | 282 | 282 | 0 | 0 |
| `sistaminuten.se` | 173 | 6 | 0 | 167 |
| `afbudsrejser.dk` | 172 | 6 | 0 | 166 |
| `akkilahdot.fi` | 172 | 6 | 0 | 166 |
| `restplass.no` | 172 | 6 | 0 | 166 |
| `socialloop.ai` | 166 | 166 | 0 | 0 |
| `remoshift.com` | 142 | 10 | 132 | 0 |
| `fundinglandscape.com` | 132 | 84 | 48 | 0 |
| `revmesh2074.workers.dev` | 129 | 116 | 13 | 0 |
| 6580 other operators | 23438 | 22198 | 1175 | 65 |
