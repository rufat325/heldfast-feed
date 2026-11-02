# MCP server tool changes

Last change observed 2026-11-02T06:54:58+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

68367 changes to a tool definition: 2873 npm releases (2627 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 65494 readings of hosted servers that found their tools changed; 3160 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-02 | `remote/insure.travelprotection/travel-insurance` | 2026-11-01T135839779497 -> 2026-11-02T065459903591 | 1 changed | quiet |
| 2026-11-02 | `remote/com.synthexforge.x402/paid-agent-services` | 2026-11-01T205304706561 -> 2026-11-02T065458215882 | 2 changed, 1 added | quiet |
| 2026-11-02 | `remote/se.sistaminuten/travel-search` | 2026-11-01T205304652167 -> 2026-11-02T065458164961 | 1 changed | quiet |
| 2026-11-02 | `remote/ng.com.xpressflowsystems.www/esim-domains` | 2026-11-01T135426917009 -> 2026-11-02T065458453485 | 3 changed | quiet |
| 2026-11-02 | `remote/io.github.imokokok/insight-oracle` | 2026-11-01T205304182884 -> 2026-11-02T065458082038 | 1 changed | quiet |
| 2026-11-02 | `remote/studio.gradients/mcp` | 2026-11-01T205301920437 -> 2026-11-02T065455571230 | 1 changed | quiet |
| 2026-11-02 | `remote/io.github.EasyGerber/easygerber` | 2026-11-01T135352706376 -> 2026-11-02T065455169815 | 3 changed | quiet |
| 2026-11-02 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-01T065443576278 -> 2026-11-02T065454105534 | 1 changed | quiet |
| 2026-11-02 | `remote/fi.akkilahdot/travel-search` | 2026-11-01T205301060789 -> 2026-11-02T065454894023 | 1 changed | quiet |
| 2026-11-02 | `remote/com.coveragecat/insurance` | 2026-10-31T202116094041 -> 2026-11-02T065457076436 | 3 changed | quiet |
| 2026-11-02 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-01T153053004824 -> 2026-11-02T065452088489 | 1 changed | quiet |
| 2026-11-02 | `remote/com.theagentsindex/mcp` | 2026-10-31T130239218649 -> 2026-11-02T065452002193 | 1 changed | quiet |
| 2026-11-02 | `remote/com.strongsaga/gear-lookup` | 2026-11-01T205256018985 -> 2026-11-02T065452083384 | 1 changed, 2 added | review |
| 2026-11-02 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-01T205253419213 -> 2026-11-02T065450278530 | 1 changed | quiet |
| 2026-11-02 | `remote/com.warminboxes/deliverability-tools` | 2026-10-31T130213336264 -> 2026-11-02T065451887859 | 1 changed | quiet |
| 2026-11-02 | `remote/com.stayotter/stay-otter` | 2026-10-31T202105053251 -> 2026-11-02T065451287971 | 1 changed | quiet |
| 2026-11-02 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-11-01T205302745270 -> 2026-11-02T065454348370 | 2 added | quiet |
| 2026-11-02 | `remote/xyz.urbangametheory/urban-game-theory` | 2026-10-31T130155470755 -> 2026-11-02T065453036995 | 14 changed, 4 added | quiet |
| 2026-11-02 | `remote/com.remoshift/jobs` | 2026-11-01T205250972402 -> 2026-11-02T065448294834 | 1 changed | quiet |
| 2026-11-02 | `remote/com.radar-cnpj/radar-cnpj` | 2026-11-01T205252147652 -> 2026-11-02T065449446213 | 7 changed, 1 removed | quiet |
| 2026-11-02 | `remote/io.github.teamhandyapps-oss/postlaunchkit` | 2026-10-31T062130049441 -> 2026-11-02T065447640147 | 2 changed | quiet |
| 2026-11-02 | `remote/no.restplass/travel-search` | 2026-11-01T205322102397 -> 2026-11-02T065445788583 | 1 changed | quiet |
| 2026-11-02 | `remote/dk.afbudsrejser/travel-search` | 2026-11-01T205320141486 -> 2026-11-02T065444817421 | 1 changed | quiet |
| 2026-11-02 | `remote/com.timeofmeeting/time-of-meeting` | 2026-11-01T153046600502 -> 2026-11-02T065446623276 | 1 changed | quiet |
| 2026-11-02 | `remote/com.multicinesortega/cartelera` | 2026-11-01T065432052237 -> 2026-11-02T065446828207 | 1 changed | quiet |
| 2026-11-02 | `remote/io.github.tell-and-go/mcp` | 2026-11-01T153036938390 -> 2026-11-02T065444184573 | 1 changed | quiet |
| 2026-11-02 | `remote/com.vidreno/mcp` | 2026-10-31T144910649252 -> 2026-11-02T065443952986 | 1 changed | quiet |
| 2026-11-02 | `remote/com.thefomite/fomite` | 2026-11-01T065451180065 -> 2026-11-02T065445378742 | 1 changed | quiet |
| 2026-11-02 | `remote/ai.trydock/dock` | 2026-10-31T144904375461 -> 2026-11-02T065443506797 | 2 changed | quiet |
| 2026-11-02 | `remote/expert.tld/tld-expert` | 2026-11-01T205316790637 -> 2026-11-02T065443032560 | 2 changed | quiet |
| 2026-11-02 | `remote/com.mosadd/mosadd-mcp` | 2026-10-31T125728462031 -> 2026-11-02T065443724478 | 1 changed, 2 added | quiet |
| 2026-11-02 | `remote/com.kernelcad/kernelcad` | 2026-10-31T234834777558 -> 2026-11-02T065443175842 | 4 changed | quiet |
| 2026-11-02 | `remote/trade.coil/stock-market-scanner.1` | 2026-11-01T134621862931 -> 2026-11-02T065440665195 | 30 changed, 5 added | quiet |
| 2026-11-02 | `remote/com.googleapis.sqladmin/mcp` | 2026-11-01T205313583683 -> 2026-11-02T065440594957 | 3 changed | quiet |
| 2026-11-02 | `remote/com.formada3d/mcp` | 2026-10-31T234831746587 -> 2026-11-02T065441321496 | 1 changed | quiet |
| 2026-11-02 | `remote/io.github.industrial-platform-ai/research-brief` | 2026-11-01T134559954220 -> 2026-11-02T065440705302 | 1 changed | quiet |
| 2026-11-02 | `remote/io.github.Timothymycompc/solana-pulse-gateway` | 2026-10-31T062136019226 -> 2026-11-02T065440014024 | 1 changed | quiet |
| 2026-11-02 | `remote/co.getclippy/clippy` | 2026-11-01T065420469851 -> 2026-11-02T065439690325 | 3 changed | quiet |
| 2026-11-02 | `remote/re.rundata/temps-reel` | 2026-11-01T205312739954 -> 2026-11-02T065439624078 | 1 changed | quiet |
| 2026-11-02 | `remote/com.scienceshot/data-centres` | 2026-10-31T202114973253 -> 2026-11-02T065440458581 | 1 changed, 2 added | quiet |
| 2026-11-02 | `remote/com.straelo/relay` | 2026-11-01T205309996878 -> 2026-11-02T065436828923 | 4 changed, 5 added, 5 removed | quiet |
| 2026-11-02 | `remote/ai.rokha/rokha` | 2026-11-01T205309942680 -> 2026-11-02T065437549791 | 1 changed | quiet |
| 2026-11-02 | `remote/net.hotelrefund/price-tracker` | 2026-11-01T065415506886 -> 2026-11-02T065436178841 | 1 changed | quiet |
| 2026-11-02 | `remote/link.rentgpu/gpu-market` | 2026-10-31T130001544878 -> 2026-11-02T065439129309 | 1 changed, 2 added | quiet |
| 2026-11-02 | `remote/com.probativegrowth/legal-marketing-data` | 2026-11-01T065430854133 -> 2026-11-02T065435825033 | 1 changed | quiet |
| 2026-11-02 | `remote/com.partstable/partstable` | 2026-11-01T065430174708 -> 2026-11-02T065434524163 | 1 changed | quiet |
| 2026-11-02 | `remote/app.vercel.fork-for-agents/fork` | 2026-11-01T205223260663 -> 2026-11-02T065435150980 | 3 changed, 1 added | quiet |
| 2026-11-02 | `remote/io.soldcomps/sold-comps` | 2026-10-31T130309260761 -> 2026-11-02T065432593612 | 4 changed | quiet |
| 2026-11-02 | `remote/com.techfabric/techfabric` | 2026-11-01T205309827317 -> 2026-11-02T065433878799 | 7 changed | quiet |
| 2026-11-02 | `remote/io.github.snefhew/factline` | 2026-11-01T065412719765 -> 2026-11-02T065433675552 | 8 added | quiet |
| 2026-11-02 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-01T065440244559 -> 2026-11-02T065432261317 | 3 changed | quiet |
| 2026-11-02 | `remote/io.github.fmind/portfolio` | 2026-10-31T202124170572 -> 2026-11-02T065431728267 | 1 changed | quiet |
| 2026-11-02 | `remote/io.github.brawlaphant/vealth` | 2026-11-01T205302353480 -> 2026-11-02T065430799510 | 1 changed | quiet |
| 2026-11-02 | `remote/io.github.OsakaSaul/mentionfox` | 2026-11-01T134904882577 -> 2026-11-02T065432457763 | 1 changed | quiet |
| 2026-11-02 | `remote/io.github.smarterweather/weather` | 2026-10-31T062126307482 -> 2026-11-02T065429326512 | 12 changed | quiet |
| 2026-11-02 | `remote/io.github.exquad/thecablecode` | 2026-11-01T205259458781 -> 2026-11-02T065429848364 | 3 changed | quiet |
| 2026-11-02 | `remote/es.proceres/proceres` | 2026-11-01T205248681164 -> 2026-11-02T065430612979 | 6 changed | quiet |
| 2026-11-02 | `remote/com.editalmd/editalmd` | 2026-11-01T205221067404 -> 2026-11-02T065432842786 | 1 changed | quiet |
| 2026-11-02 | `remote/co.deadbrands/arena` | 2026-10-31T062119744248 -> 2026-11-02T065427025777 | 2 changed | quiet |
| 2026-11-02 | `remote/ca.dispola/places` | 2026-11-01T065409765147 -> 2026-11-02T065429544089 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 44169 substantive, 23416 that changed only numbers (a catalogue counter ticking, a date), 782 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 37734 | 15838 | 21896 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1245 | 1245 | 0 | 0 |
| `caseyjhand.com` | 311 | 311 | 0 | 0 |
| `sistaminuten.se` | 185 | 6 | 0 | 179 |
| `afbudsrejser.dk` | 184 | 6 | 0 | 178 |
| `akkilahdot.fi` | 184 | 6 | 0 | 178 |
| `restplass.no` | 184 | 6 | 0 | 178 |
| `socialloop.ai` | 178 | 178 | 0 | 0 |
| `remoshift.com` | 154 | 12 | 142 | 0 |
| `revmesh2074.workers.dev` | 146 | 128 | 18 | 0 |
| `fundinglandscape.com` | 142 | 88 | 54 | 0 |
| 6836 other operators | 25379 | 24004 | 1306 | 69 |
