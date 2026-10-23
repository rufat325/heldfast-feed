# MCP server tool changes

Last change observed 2026-10-23T12:09:50+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

44935 changes to a tool definition: 1988 npm releases (1742 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 42947 readings of hosted servers that found their tools changed; 2413 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-23 | `remote/io.github.ZadenGG/x402-zadenworks` | 2026-10-17T055627578834 -> 2026-10-23T120951067782 | 4 added | quiet |
| 2026-10-23 | `remote/io.github.HillTan/tiktikluck` | 2026-10-20T120651435607 -> 2026-10-23T120945001414 | 4 added | quiet |
| 2026-10-23 | `remote/ai.snowsure/snow` | 2026-10-17T055617814957 -> 2026-10-23T120940608152 | 2 changed | quiet |
| 2026-10-23 | `remote/se.sistaminuten/travel-search` | 2026-10-23T052628036840 -> 2026-10-23T120940432806 | 1 changed | quiet |
| 2026-10-23 | `remote/io.kolmo.www/kolmo-mcp-server` | 2026-10-21T052325223300 -> 2026-10-23T120928227431 | 38 changed, 1 added | quiet |
| 2026-10-23 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-10-21T141153863196 -> 2026-10-23T120928574658 | 2 changed | quiet |
| 2026-10-23 | `remote/app.housefile/licensing` | 2026-10-19T135459115109 -> 2026-10-23T120929560273 | 2 changed | quiet |
| 2026-10-23 | `remote/com.artbooksociety/public-catalog` | 2026-10-17T055555132136 -> 2026-10-23T120915352871 | 1 changed | quiet |
| 2026-10-23 | `remote/no.apier/mcp` | 2026-10-18T113435235185 -> 2026-10-23T120915274396 | 1 changed, 7 removed | quiet |
| 2026-10-23 | `remote/com.aiseparations/color-separations` | 2026-10-20T104320648947 -> 2026-10-23T120911233920 | 1 changed | review |
| 2026-10-23 | `remote/ai.whatsupin/events` | 2026-10-21T122323534960 -> 2026-10-23T120857473229 | 4 changed | quiet |
| 2026-10-23 | `remote/me.walalook/tools.13` | 2026-10-19T135415728731 -> 2026-10-23T120843645848 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.voicehook-ai/voicehook` | 2026-10-22T202058197892 -> 2026-10-23T120839238722 | 1 changed | quiet |
| 2026-10-23 | `remote/com.vaultrubric/vaultrubric` | 2026-10-17T055528547024 -> 2026-10-23T120830829457 | 1 changed | quiet |
| 2026-10-23 | `remote/com.udansa/udansa` | 2026-10-19T135354768646 -> 2026-10-23T120820780793 | 7 changed (every tool) | quiet |
| 2026-10-23 | `remote/com.trycommonplace/seller` | 2026-10-18T113357769257 -> 2026-10-23T120816304653 | 2 changed | quiet |
| 2026-10-23 | `remote/uk.co.transitradar/transitradar` | 2026-10-17T055516896518 -> 2026-10-23T120813076796 | 1 added | quiet |
| 2026-10-23 | `remote/io.github.intoApex/tradingagentstack` | 2026-10-21T122228985213 -> 2026-10-23T120811325357 | 2 added | quiet |
| 2026-10-23 | `remote/com.tofubofu/ai-visibility` | 2026-09-25T120523279459 -> 2026-10-23T120756458829 | 1 changed | quiet |
| 2026-10-23 | `remote/rentals.threshold/stays` | 2026-10-17T055507201602 -> 2026-10-23T120754617983 | 1 changed | quiet |
| 2026-10-23 | `remote/com.thefomite/fomite` | 2026-10-23T052621676919 -> 2026-10-23T120751955261 | 1 changed | quiet |
| 2026-10-23 | `remote/com.tektolo/rental-property` | 2026-10-19T135323136656 -> 2026-10-23T120746831177 | 5 changed (every tool) | quiet |
| 2026-10-23 | `remote/dev.sportsapis/sportsapis` | 2026-10-19T135304338106 -> 2026-10-23T120723500940 | 1 changed | quiet |
| 2026-10-23 | `remote/info.yank/yank` | 2026-10-08T135553399426 -> 2026-10-23T120722331592 | 2 changed | quiet |
| 2026-10-23 | `remote/com.uicapsule/components` | 2026-10-06T110334428078 -> 2026-10-23T120711625523 | 2 changed (every tool) | quiet |
| 2026-10-23 | `remote/io.github.Fizzl13/x402-doctor` | 2026-10-21T122222497942 -> 2026-10-23T120711750894 | 1 changed | quiet |
| 2026-10-23 | `remote/com.skillspicker/recommend` | 2026-10-19T135258291957 -> 2026-10-23T120710594408 | 1 changed | quiet |
| 2026-10-23 | `remote/com.workers-rights/employment-law` | 2026-10-17T060419395667 -> 2026-10-23T120709801449 | 2 changed | quiet |
| 2026-10-23 | `remote/io.github.Z4KARY/upgrowth-mcp` | 2026-10-21T052308453010 -> 2026-10-23T120710208994 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.ceedot-rock/slid-phi-labs` | 2026-09-23T163143392042 -> 2026-10-23T120703796898 | 2 changed | quiet |
| 2026-10-23 | `remote/no.restplass/travel-search` | 2026-10-23T052629572740 -> 2026-10-23T120701191102 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.CustomBlinds/cb-shop` | 2026-10-22T202048199442 -> 2026-10-23T120701389593 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.TMCHALK/sftunes` | 2026-09-23T160935106404 -> 2026-10-23T120658838685 | 1 changed | quiet |
| 2026-10-23 | `remote/com.orlandu/arcade` | 2026-10-17T055947620462 -> 2026-10-23T120654698285 | 1 changed, 1 added | quiet |
| 2026-10-23 | `remote/io.github.aanari/loacare-healthcare-pricing` | 2026-10-17T055944370353 -> 2026-10-23T120651166350 | 1 changed | quiet |
| 2026-10-23 | `remote/ai.kavel/kavel-mcp` | 2026-10-19T135233815368 -> 2026-10-23T120646449589 | 1 changed | quiet |
| 2026-10-23 | `remote/studio.gradients/mcp` | 2026-10-23T052644638425 -> 2026-10-23T120646168528 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.cryptoduke01/gloam` | 2026-10-22T110254033011 -> 2026-10-23T120643404378 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-10-23T052619113642 -> 2026-10-23T120642034333 | 2 changed | quiet |
| 2026-10-23 | `remote/co.foodose/glp1-nutrition` | 2026-10-17T060344204750 -> 2026-10-23T120640303360 | 2 changed | quiet |
| 2026-10-23 | `remote/com.asksakina/islamic-knowledge` | 2026-10-21T202535784086 -> 2026-10-23T120639331395 | 1 changed | quiet |
| 2026-10-23 | `remote/io.atilab/mcp` | 2026-10-19T135530685168 -> 2026-10-23T120632946651 | 5 changed | quiet |
| 2026-10-23 | `remote/ai.rocketsloth/rocketsloth` | 2026-10-17T055423553774 -> 2026-10-23T120633896826 | 1 changed | quiet |
| 2026-10-23 | `remote/fi.akkilahdot/travel-search` | 2026-10-23T052644836774 -> 2026-10-23T120631530160 | 1 changed | quiet |
| 2026-10-23 | `remote/com.calmido/phone-number-lookup` | 2026-10-19T135221102721 -> 2026-10-23T120631771973 | 1 changed | quiet |
| 2026-10-23 | `remote/com.basischarts/basis` | 2026-10-19T155952291661 -> 2026-10-23T120629126982 | 14 changed, 1 added | quiet |
| 2026-10-23 | `remote/io.github.slookisen/lokal-mcp` | 2026-10-19T135217700703 -> 2026-10-23T120627978483 | 2 changed | quiet |
| 2026-10-23 | `remote/dk.afbudsrejser/travel-search` | 2026-10-23T052628908106 -> 2026-10-23T120623562469 | 1 changed | quiet |
| 2026-10-23 | `remote/com.actualgroup/jobs` | 2026-10-22T140858156820 -> 2026-10-23T120623679123 | 6 changed (every tool) | quiet |
| 2026-10-23 | `remote/io.github.witanmarkets/witan` | 2026-10-17T185402886350 -> 2026-10-23T120619621397 | 1 changed | quiet |
| 2026-10-23 | `remote/com.rattlesnakesbymail/rattlesnakesbymail` | 2026-09-23T160912152404 -> 2026-10-23T120617334442 | 1 changed, 1 added | quiet |
| 2026-10-23 | `remote/com.vouchernaut/deals` | 2026-10-19T135506736097 -> 2026-10-23T120615537462 | 3 changed | quiet |
| 2026-10-23 | `remote/io.github.jukky-source/wealth-agent` | 2026-10-20T232811121733 -> 2026-10-23T120612517757 | 6 changed | quiet |
| 2026-10-23 | `remote/com.washbodega/service-discovery` | 2026-10-17T060312937145 -> 2026-10-23T120610171498 | 1 changed | quiet |
| 2026-10-23 | `remote/pl.przetargowyjanusz/tenders` | 2026-10-22T202044673497 -> 2026-10-23T120607904835 | 2 changed | quiet |
| 2026-10-23 | `remote/ru.vedarai/mcp` | 2026-10-23T052644033552 -> 2026-10-23T120608160595 | 1 changed | quiet |
| 2026-10-23 | `remote/tech.varexis/varexis-index` | 2026-10-18T223951810357 -> 2026-10-23T120608653084 | 1 changed | quiet |
| 2026-10-23 | `remote/io.github.ohad6k/viberaven-guides` | 2026-10-17T060406037265 -> 2026-10-23T120605256503 | 1 added | quiet |
| 2026-10-23 | `remote/io.github.kushkillerjsixx66/vara-mcp-server` | 2026-10-17T055858229416 -> 2026-10-23T120604742937 | 1 changed | quiet |
| 2026-10-23 | `remote/com.programscape/programscape` | 2026-10-17T055405370374 -> 2026-10-23T120603979111 | 3 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 28501 substantive, 15849 that changed only numbers (a catalogue counter ticking, a date), 585 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 23651 | 8749 | 14902 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 655 | 655 | 0 | 0 |
| `caseyjhand.com` | 187 | 187 | 0 | 0 |
| `sistaminuten.se` | 139 | 4 | 0 | 135 |
| `afbudsrejser.dk` | 138 | 4 | 0 | 134 |
| `akkilahdot.fi` | 138 | 4 | 0 | 134 |
| `restplass.no` | 138 | 4 | 0 | 134 |
| `socialloop.ai` | 134 | 134 | 0 | 0 |
| `remoshift.com` | 109 | 8 | 101 | 0 |
| `fundinglandscape.com` | 107 | 71 | 36 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| 5336 other operators | 17101 | 16243 | 810 | 48 |
