# MCP server tool changes

Last change observed 2026-10-18T22:40:15+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10495 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 23695 hosted endpoints (read daily, and every four hours while they keep changing).

32732 changes to a tool definition: 1188 npm releases (942 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 31544 readings of hosted servers that found their tools changed; 2107 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-18 | `remote/no.restplass/travel-search` | 2026-10-18T190050013401 -> 2026-10-18T224016162575 | 1 changed | quiet |
| 2026-10-18 | `remote/io.taifoon/coordination-layer.1` | 2026-10-18T190021054412 -> 2026-10-18T224014380994 | 6 changed, 9 added, 104 removed (every tool) | quiet |
| 2026-10-18 | `remote/se.sistaminuten/travel-search` | 2026-10-18T190018736939 -> 2026-10-18T224013712807 | 1 changed | quiet |
| 2026-10-18 | `remote/com.menloinsurance/mcp` | 2026-10-17T055612411287 -> 2026-10-18T224012399762 | 11 changed, 1 added (every tool) | quiet |
| 2026-10-18 | `remote/com.blitzreels/blitzreels` | 2026-10-18T190014690273 -> 2026-10-18T224010926553 | 2 changed | quiet |
| 2026-10-18 | `remote/dk.afbudsrejser/travel-search` | 2026-10-18T190040877224 -> 2026-10-18T224008491674 | 1 changed | quiet |
| 2026-10-18 | `remote/com.viarapidaservices/mcp` | 2026-10-18T113327660292 -> 2026-10-18T224005479181 | 8 changed, 1 added (every tool) | quiet |
| 2026-10-18 | `remote/com.thegtmdirectory/mcp` | 2026-10-18T051514789852 -> 2026-10-18T223959536635 | 1 changed | quiet |
| 2026-10-18 | `remote/ch.antevo/trademark` | 2026-10-17T224455668637 -> 2026-10-18T224000425584 | 15 changed, 1 removed (every tool) | quiet |
| 2026-10-18 | `remote/com.tabzoola/pricing` | 2026-10-17T055502906745 -> 2026-10-18T224000420903 | 1 added | quiet |
| 2026-10-18 | `remote/fi.akkilahdot/travel-search` | 2026-10-18T190112384591 -> 2026-10-18T223953555965 | 1 changed | quiet |
| 2026-10-18 | `remote/pro.sebbi/governance` | 2026-10-18T190019319808 -> 2026-10-18T223949968194 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.SidneyBissoli/senado-br-mcp-cloudflare` | 2026-10-18T185956688883 -> 2026-10-18T223949924847 | 2 changed | quiet |
| 2026-10-18 | `remote/us.srv.vehcdj664efetfrsolne5umanq/quoteproof-mcp` | 2026-10-18T190108008209 -> 2026-10-18T223949075287 | 5 changed | review |
| 2026-10-18 | `remote/tech.varexis/varexis-index` | 2026-10-17T111203065169 -> 2026-10-18T223951810357 | 1 changed | quiet |
| 2026-10-18 | `remote/ai.rokha/rokha` | 2026-10-17T224353125286 -> 2026-10-18T223945709920 | 1 changed | quiet |
| 2026-10-18 | `remote/com.poolproflorida/pool-pro-florida` | 2026-10-17T060142594216 -> 2026-10-18T223939271842 | 1 added | quiet |
| 2026-10-18 | `remote/io.github.dtajitdinov-aris/sphere-marketplace` | 2026-10-18T113156275244 -> 2026-10-18T223940421721 | 13 changed | quiet |
| 2026-10-18 | `remote/com.owlchart/owlchart` | 2026-10-18T185946827559 -> 2026-10-18T223938952783 | 2 changed, 10 added | quiet |
| 2026-10-18 | `remote/com.achivx/stablescan` | 2026-10-17T055815091232 -> 2026-10-18T223938382874 | 1 changed | quiet |
| 2026-10-18 | `remote/app.steadywrk/mcp-dispatch` | 2026-10-18T190051659145 -> 2026-10-18T223938343815 | 3 changed | quiet |
| 2026-10-18 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-18T190048249229 -> 2026-10-18T223937142282 | 1 changed | quiet |
| 2026-10-18 | `remote/com.orbylon/readiness` | 2026-10-17T060122065878 -> 2026-10-18T223936205306 | 2 changed, 2 added | quiet |
| 2026-10-18 | `remote/com.remoshift/jobs` | 2026-10-18T190040874186 -> 2026-10-18T223932302534 | 1 changed | quiet |
| 2026-10-18 | `remote/how.mise/mise` | 2026-10-18T185959825778 -> 2026-10-18T223932448842 | 2 changed | quiet |
| 2026-10-18 | `remote/io.github.valuein/mcp-sec-edgar.2` | 2026-10-18T113020459630 -> 2026-10-18T223929474772 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.valuein/mcp-sec-edgar.1` | 2026-10-18T051431329533 -> 2026-10-18T223929610145 | 1 changed | quiet |
| 2026-10-18 | `remote/me.phor/phorme-training` | 2026-10-18T051328257225 -> 2026-10-18T223925152129 | 1 changed, 2 added | quiet |
| 2026-10-18 | `remote/md.mostlyright/datasets` | 2026-10-17T055938651481 -> 2026-10-18T223925249949 | 15 added | quiet |
| 2026-10-18 | `remote/com.myinsurancecity/mcp` | 2026-10-18T113113955261 -> 2026-10-18T223926471477 | 8 changed, 1 added (every tool) | quiet |
| 2026-10-18 | `remote/com.partstable/partstable` | 2026-10-18T051414349329 -> 2026-10-18T223923137517 | 1 changed | quiet |
| 2026-10-18 | `remote/com.ableandagent/sandbox` | 2026-10-17T055220005670 -> 2026-10-18T223922821250 | 1 changed | quiet |
| 2026-10-18 | `remote/dev.mcphost/mcphost` | 2026-10-18T113050950669 -> 2026-10-18T223921196139 | 1 changed | quiet |
| 2026-10-18 | `remote/com.multicinesortega/cartelera` | 2026-10-18T051324132856 -> 2026-10-18T223919577008 | 1 changed | quiet |
| 2026-10-18 | `remote/org.living-bread.mcp/living-bread` | 2026-10-17T055929327910 -> 2026-10-18T223919797721 | 8 changed | quiet |
| 2026-10-18 | `remote/io.github.valuein/mcp-sec-edgar` | 2026-10-18T185932759608 -> 2026-10-18T223917192346 | 1 changed | quiet |
| 2026-10-18 | `remote/com.tkawen/intelligence-gateway` | 2026-10-18T185931058547 -> 2026-10-18T223915973655 | 37 added | quiet |
| 2026-10-18 | `remote/com.avokata/avokata` | 2026-10-17T055841970681 -> 2026-10-18T223912711583 | 7 changed | quiet |
| 2026-10-18 | `remote/io.github.endoflife-ai/endoflife-mcp` | 2026-10-17T055115104709 -> 2026-10-18T223907963733 | 1 changed | quiet |
| 2026-10-18 | `remote/com.uxfront/open-components` | 2026-10-17T055740833469 -> 2026-10-18T223908818945 | 5 changed | quiet |
| 2026-10-18 | `remote/co.marketmayhem/mcp` | 2026-10-17T055810757196 -> 2026-10-18T223907777698 | 2 changed, 1 removed | quiet |
| 2026-10-18 | `remote/tech.kaiku/kaiku.1` | 2026-10-18T185922169715 -> 2026-10-18T223905768768 | 1 changed, 3 added | quiet |
| 2026-10-18 | `remote/com.kernelcad/kernelcad` | 2026-10-18T051309055112 -> 2026-10-18T223905049457 | 3 changed | quiet |
| 2026-10-18 | `remote/app.himalayas/mcp` | 2026-10-18T124954970690 -> 2026-10-18T223906042865 | 1 changed, 13 added | quiet |
| 2026-10-18 | `remote/org.bull-run/bullrun` | 2026-10-18T185917808429 -> 2026-10-18T223903493469 | 4 added | quiet |
| 2026-10-18 | `remote/com.freqblog/music-metadata` | 2026-10-17T055648727861 -> 2026-10-18T223903688461 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.hail-hq/hail-mcp` | 2026-10-18T051306357033 -> 2026-10-18T223903170957 | 3 changed | quiet |
| 2026-10-18 | `remote/com.hireahelper/mcp` | 2026-10-18T125012392921 -> 2026-10-18T223902471218 | 16 removed | quiet |
| 2026-10-18 | `remote/com.jobsbylevel/level-jobs` | 2026-10-17T224304729307 -> 2026-10-18T223901745734 | 2 changed | quiet |
| 2026-10-18 | `remote/com.ableandagent/able-and-agent` | 2026-10-17T055040977039 -> 2026-10-18T223901073487 | 1 changed | quiet |
| 2026-10-18 | `remote/com.foundationscounselingllc/practice` | 2026-10-17T055403605623 -> 2026-10-18T223900436552 | 2 changed | quiet |
| 2026-10-18 | `remote/io.github.daniel3303/equibles` | 2026-10-18T185955005486 -> 2026-10-18T223900360816 | 2 added | quiet |
| 2026-10-18 | `remote/uk.co.harktech/quotes` | 2026-10-17T055659195821 -> 2026-10-18T223858346945 | 1 changed, 4 added | quiet |
| 2026-10-18 | `remote/co.ainumbers/tools` | 2026-10-18T124948561980 -> 2026-10-18T223859867423 | 3 changed | quiet |
| 2026-10-18 | `remote/ai.makememoneynomistakes/scoreboard` | 2026-10-17T224310172064 -> 2026-10-18T223858298135 | 6 added | review |
| 2026-10-18 | `remote/io.github.industrial-platform-ai/research-brief` | 2026-10-18T051257794747 -> 2026-10-18T223854784344 | 1 changed | quiet |
| 2026-10-18 | `remote/io.github.kirillradchenko96/fresh402` | 2026-10-18T112553974921 -> 2026-10-18T223854035509 | 4 changed | quiet |
| 2026-10-18 | `remote/com.787daily/mcp` | 2026-10-17T055311171931 -> 2026-10-18T223853564492 | 9 added | quiet |
| 2026-10-18 | `remote/app.lovable.jessica-hill-holm/leadership-coach` | 2026-10-17T155857804833 -> 2026-10-18T223853104684 | 1 added | quiet |
| 2026-10-18 | `remote/com.essentras/placements` | 2026-10-18T185907861864 -> 2026-10-18T223848460807 | 1 changed, 2 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 22576 substantive, 9676 that changed only numbers (a catalogue counter ticking, a date), 480 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 16224 | 7212 | 9012 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 145 | 145 | 0 | 0 |
| `sistaminuten.se` | 116 | 4 | 0 | 112 |
| `afbudsrejser.dk` | 115 | 4 | 0 | 111 |
| `akkilahdot.fi` | 115 | 4 | 0 | 111 |
| `restplass.no` | 115 | 4 | 0 | 111 |
| `socialloop.ai` | 112 | 112 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `remoshift.com` | 86 | 6 | 80 | 0 |
| `fundinglandscape.com` | 85 | 52 | 33 | 0 |
| 3989 other operators | 12528 | 11942 | 551 | 35 |
