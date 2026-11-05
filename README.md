# MCP server tool changes

Last change observed 2026-11-05T22:22:53+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

78480 changes to a tool definition: 3319 npm releases (3073 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 75161 readings of hosted servers that found their tools changed; 3445 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-05 | `remote/io.github.Veniwol-Li-Lambd/lilambd-data` | 2026-11-05T115757964809 -> 2026-11-05T222302487483 | 7 added | quiet |
| 2026-11-05 | `remote/ai.workonit/mcp` | 2026-11-03T145111616856 -> 2026-11-05T222256478214 | 2 changed | quiet |
| 2026-11-05 | `remote/no.restplass/travel-search` | 2026-11-05T150922137348 -> 2026-11-05T222252489127 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.ceedot-rock/slid-phi-labs` | 2026-11-05T115733883920 -> 2026-11-05T222251532332 | 4 changed | quiet |
| 2026-11-05 | `remote/com.sapiensinteticos/sapiens` | 2026-11-04T150937166264 -> 2026-11-05T222251989789 | 5 changed | quiet |
| 2026-11-05 | `remote/app.postel/postel` | 2026-11-04T150910639702 -> 2026-11-05T222250714237 | 4 changed | quiet |
| 2026-11-05 | `remote/dk.afbudsrejser/travel-search` | 2026-11-05T150832223457 -> 2026-11-05T222245520541 | 1 changed | quiet |
| 2026-11-05 | `remote/fun.trnch/trnch` | 2026-11-04T123809419714 -> 2026-11-05T222241946686 | 3 changed, 4 added | quiet |
| 2026-11-05 | `remote/fr.synergieloc/immobilier` | 2026-11-05T124849532181 -> 2026-11-05T222238112696 | 1 added | quiet |
| 2026-11-05 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-05T150635491236 -> 2026-11-05T222237363261 | 1 added, 4 removed | quiet |
| 2026-11-05 | `remote/com.stockcake/stockcake` | 2026-11-03T144812559627 -> 2026-11-05T222234225420 | 1 changed | quiet |
| 2026-11-05 | `remote/com.theprotoclinical/commerce` | 2026-11-04T005909537946 -> 2026-11-05T222230628124 | 9 changed | quiet |
| 2026-11-05 | `remote/com.plyparts/ply` | 2026-11-05T115548746562 -> 2026-11-05T222229856491 | 5 changed | quiet |
| 2026-11-05 | `remote/com.patchmcp/patch` | 2026-11-05T115546586769 -> 2026-11-05T222229477210 | 2 changed | quiet |
| 2026-11-05 | `remote/com.jobcrawls/connector` | 2026-11-03T145022682841 -> 2026-11-05T222229027889 | 1 changed | quiet |
| 2026-11-05 | `remote/studio.gradients/mcp` | 2026-11-05T151044512333 -> 2026-11-05T222227755362 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.SoapyRED/freightutils` | 2026-11-05T115530831371 -> 2026-11-05T222228098181 | 4 changed | quiet |
| 2026-11-05 | `remote/fi.akkilahdot/travel-search` | 2026-11-05T151024796729 -> 2026-11-05T222224219288 | 1 changed | quiet |
| 2026-11-05 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-05T115520943533 -> 2026-11-05T222223252900 | 8 changed | quiet |
| 2026-11-05 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-05T115456228443 -> 2026-11-05T222223661351 | 12 added | review |
| 2026-11-05 | `remote/io.taifoon/coordination-layer.1` | 2026-11-04T200758444812 -> 2026-11-05T222222141955 | 1 changed | quiet |
| 2026-11-05 | `remote/com.socialfaktory/mcp` | 2026-11-03T024315793226 -> 2026-11-05T222221191291 | 3 changed | quiet |
| 2026-11-05 | `remote/se.sistaminuten/travel-search` | 2026-11-05T151117687159 -> 2026-11-05T222221218331 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-05T150955932168 -> 2026-11-05T222222603533 | 3 changed | quiet |
| 2026-11-05 | `remote/dev.workers.makar52nn2016.money-reactor/x402-money-reactor` | 2026-11-05T150315720891 -> 2026-11-05T222218840491 | 33 changed | review |
| 2026-11-05 | `remote/io.github.Tomalarrrr/cyclesite-mcp-server` | 2026-11-05T115404907616 -> 2026-11-05T222219197532 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-05T150911458732 -> 2026-11-05T222219348868 | 1 changed | quiet |
| 2026-11-05 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-05T124823762843 -> 2026-11-05T222219226197 | 4 changed | quiet |
| 2026-11-05 | `remote/xyz.t0ll/toll` | 2026-11-04T200755832937 -> 2026-11-05T222216206801 | 1 changed, 1 added | quiet |
| 2026-11-05 | `remote/io.corpusiq/multi-source-mcp` | 2026-11-05T010629945570 -> 2026-11-05T222216384314 | 1 changed | quiet |
| 2026-11-05 | `remote/com.blitzreels/blitzreels` | 2026-11-05T115400097169 -> 2026-11-05T222217277158 | 3 changed | quiet |
| 2026-11-05 | `remote/xyz.x402helper/mcp` | 2026-11-04T200821305080 -> 2026-11-05T222216338152 | 3 changed, 1 added | quiet |
| 2026-11-05 | `remote/no.apier/mcp` | 2026-11-03T144925671603 -> 2026-11-05T222216469750 | 1 changed | quiet |
| 2026-11-05 | `remote/dev.zambo/zambo` | 2026-11-03T122650437288 -> 2026-11-05T222215569847 | 36 changed (every tool) | quiet |
| 2026-11-05 | `remote/com.yomachichi/shop` | 2026-11-04T005907982491 -> 2026-11-05T222215638545 | 9 changed | quiet |
| 2026-11-05 | `remote/io.github.JacobiusMakes/stienhardt-store` | 2026-11-04T005849059469 -> 2026-11-05T222214248010 | 9 changed | quiet |
| 2026-11-05 | `remote/com.googleapis.stitch/mcp` | 2026-11-04T200754611955 -> 2026-11-05T222214778301 | 10 changed | quiet |
| 2026-11-05 | `remote/ai.whatareyoubuilding/wayb` | 2026-11-05T151017701066 -> 2026-11-05T222214314279 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-05T150829021688 -> 2026-11-05T222213439126 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.smarterweather/weather` | 2026-11-05T010627644342 -> 2026-11-05T222213595648 | 2 changed | quiet |
| 2026-11-05 | `remote/eu.paymentslaw/legislation` | 2026-11-05T150159457229 -> 2026-11-05T222211564516 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.marcoret74/semantic-geometry` | 2026-11-03T195656161429 -> 2026-11-05T222219542786 | 2 changed, 2 added | quiet |
| 2026-11-05 | `remote/io.github.77777R7/octocrawl` | 2026-11-05T114922654402 -> 2026-11-05T222210793135 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.brawlaphant/vealth` | 2026-11-04T200805705293 -> 2026-11-05T222209811899 | 3 changed | quiet |
| 2026-11-05 | `remote/fr.nitech.catalogue/commerce` | 2026-11-03T144326726822 -> 2026-11-05T222211251954 | 2 changed | quiet |
| 2026-11-05 | `remote/net.tichat.tradehub/tradehub.1` | 2026-11-04T200801490213 -> 2026-11-05T222208226821 | 4 changed, 1 added, 1 removed | quiet |
| 2026-11-05 | `remote/io.github.ironflowsh/mcp` | 2026-11-05T114841015465 -> 2026-11-05T222207910331 | 7 changed | quiet |
| 2026-11-05 | `remote/com.lastscanned/lastscanned` | 2026-11-05T114850438747 -> 2026-11-05T222207179810 | 3 changed (every tool) | quiet |
| 2026-11-05 | `remote/com.thejohnsislander/the-johns-islander` | 2026-11-04T005852123442 -> 2026-11-05T222204708176 | 1 changed | quiet |
| 2026-11-05 | `remote/io.stockmap/stockmap` | 2026-11-05T115223439285 -> 2026-11-05T222202643965 | 2 changed | quiet |
| 2026-11-05 | `remote/com.multicinesortega/cartelera` | 2026-11-05T115057998284 -> 2026-11-05T222204001170 | 1 changed | quiet |
| 2026-11-05 | `remote/com.googleapis.monitoring/mcp` | 2026-11-05T150543537294 -> 2026-11-05T222201394757 | 5 changed | quiet |
| 2026-11-05 | `remote/io.github.makar52nn-crypto/x402-money-reactor` | 2026-11-05T150543157927 -> 2026-11-05T222201159008 | 33 changed | review |
| 2026-11-05 | `remote/io.github.makar-aibot/money-reactor-mcp` | 2026-11-05T150543346735 -> 2026-11-05T222201120816 | 33 changed | review |
| 2026-11-05 | `remote/com.budgetpixel/mcp` | 2026-11-04T123721641068 -> 2026-11-05T222200278409 | 2 changed | review |
| 2026-11-05 | `remote/com.vendooly/vendooly` | 2026-11-05T115021247512 -> 2026-11-05T222200365444 | 3 changed | quiet |
| 2026-11-05 | `remote/com.lvl2player/sandbox` | 2026-11-04T005909240608 -> 2026-11-05T222202362922 | 11 changed | quiet |
| 2026-11-05 | `remote/net.tasklite/mcp` | 2026-11-03T144422737569 -> 2026-11-05T222159066688 | 2 changed | quiet |
| 2026-11-05 | `remote/link.rentgpu/gpu-market` | 2026-11-05T115114827657 -> 2026-11-05T222159702388 | 1 changed, 2 added | quiet |
| 2026-11-05 | `remote/com.sfxmint/sounds` | 2026-11-05T115144225541 -> 2026-11-05T222158537162 | 3 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 48482 substantive, 29147 that changed only numbers (a catalogue counter ticking, a date), 851 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 43271 | 15883 | 27388 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1485 | 1485 | 0 | 0 |
| `caseyjhand.com` | 354 | 354 | 0 | 0 |
| `sistaminuten.se` | 200 | 6 | 0 | 194 |
| `afbudsrejser.dk` | 199 | 6 | 0 | 193 |
| `akkilahdot.fi` | 199 | 6 | 0 | 193 |
| `restplass.no` | 199 | 6 | 0 | 193 |
| `socialloop.ai` | 192 | 192 | 0 | 0 |
| `remoshift.com` | 165 | 14 | 151 | 0 |
| `revmesh2074.workers.dev` | 159 | 140 | 19 | 0 |
| `fundinglandscape.com` | 153 | 93 | 60 | 0 |
| 7675 other operators | 29563 | 27956 | 1529 | 78 |
