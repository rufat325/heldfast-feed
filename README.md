# MCP server tool changes

Last change observed 2026-11-15T14:27:55+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

104009 changes to a tool definition: 4274 npm releases (4028 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 99735 readings of hosted servers that found their tools changed; 4159 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-15 | `remote/eu.surfbooking/surfbooking` | 2026-10-27T145904517143 -> 2026-11-15T142756836456 | 3 changed | quiet |
| 2026-11-15 | `remote/com.prenotomenu/menu` | 2026-11-13T150637381460 -> 2026-11-15T142745735024 | 4 added | quiet |
| 2026-11-15 | `remote/ai.oriiion/oriiion` | 2026-11-15T115805168409 -> 2026-11-15T142741411761 | 4 changed, 3 added | quiet |
| 2026-11-15 | `remote/io.github.racharmi/ohgiftplease` | 2026-10-17T055946922859 -> 2026-11-15T142729206406 | 6 changed | quiet |
| 2026-11-15 | `remote/xn--3ds443g.xn--s7y/duan-online` | 2026-11-15T115659446014 -> 2026-11-15T142719484555 | 3 changed | quiet |
| 2026-11-15 | `remote/studio.gradients/mcp` | 2026-11-15T115635965177 -> 2026-11-15T142717379327 | 1 changed | quiet |
| 2026-11-15 | `remote/com.codestringers/mcp` | 2026-10-26T153204083365 -> 2026-11-15T142659794151 | 6 changed | quiet |
| 2026-11-15 | `remote/se.sistaminuten/travel-search` | 2026-11-15T115638093404 -> 2026-11-15T142658512016 | 1 changed | quiet |
| 2026-11-15 | `remote/ai.withby/withby` | 2026-11-09T170055654244 -> 2026-11-15T142649114087 | 2 changed | quiet |
| 2026-11-15 | `remote/io.github.moelayyan90/xguard` | 2026-11-12T074747425788 -> 2026-11-15T142646702529 | 8 added | review |
| 2026-11-15 | `remote/fi.akkilahdot/travel-search` | 2026-11-15T115617093181 -> 2026-11-15T142644315959 | 1 changed | quiet |
| 2026-11-15 | `remote/uk.co.websitedesignguildford/site` | 2026-11-11T145925985618 -> 2026-11-15T142644124993 | 2 changed | quiet |
| 2026-11-15 | `remote/uk.webdesignsuffolk/site` | 2026-11-11T145924689821 -> 2026-11-15T142642180427 | 2 changed | quiet |
| 2026-11-15 | `remote/uk.webdesignsussex/site` | 2026-11-11T150035302572 -> 2026-11-15T142622920905 | 2 changed | quiet |
| 2026-11-15 | `remote/uk.webdesignpoole/site` | 2026-11-11T150035264115 -> 2026-11-15T142622850417 | 2 changed | quiet |
| 2026-11-15 | `remote/no.restplass/travel-search` | 2026-11-15T115347429007 -> 2026-11-15T142616633166 | 1 changed | quiet |
| 2026-11-15 | `remote/app.openkrill/transcript-kit` | 2026-11-13T150451376232 -> 2026-11-15T142601260621 | 2 changed | quiet |
| 2026-11-15 | `remote/com.kulicadvisory/aictionbot-werkbank` | 2026-11-15T071543882563 -> 2026-11-15T142557543331 | 12 added | quiet |
| 2026-11-15 | `remote/ru.vedarai/mcp` | 2026-11-15T071612039015 -> 2026-11-15T142553384011 | 6 changed | quiet |
| 2026-11-15 | `remote/uk.co.websitedesignerssmallbusiness/site` | 2026-11-11T145908917025 -> 2026-11-15T142547249842 | 2 changed | quiet |
| 2026-11-15 | `remote/io.deeplead/deeplead` | 2026-11-15T002355908630 -> 2026-11-15T142539844539 | 2 changed | quiet |
| 2026-11-15 | `remote/com.vet402/vet402` | 2026-11-12T154912948487 -> 2026-11-15T142529915523 | 1 changed | quiet |
| 2026-11-15 | `remote/dk.afbudsrejser/travel-search` | 2026-11-15T115307037273 -> 2026-11-15T142527888831 | 1 changed | quiet |
| 2026-11-15 | `remote/com.86hc/hongkong-company` | 2026-11-11T145828679515 -> 2026-11-15T142526840863 | 6 changed | review |
| 2026-11-15 | `remote/app.wieldr/radar` | 2026-11-13T115910311217 -> 2026-11-15T142518083699 | 14 changed, 1 added (every tool) | quiet |
| 2026-11-15 | `remote/io.github.PascalSun/talk2geo` | 2026-11-15T115533225410 -> 2026-11-15T142514421765 | 20 removed | quiet |
| 2026-11-15 | `remote/uk.webdesigncheltenham/site` | 2026-11-11T145814626953 -> 2026-11-15T142513106429 | 2 changed | quiet |
| 2026-11-15 | `remote/app.openkrill/tariffs` | 2026-10-17T055830039333 -> 2026-11-15T142459766784 | 2 changed | quiet |
| 2026-11-15 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-11-14T010632456750 -> 2026-11-15T142440399245 | 2 changed, 2 added | quiet |
| 2026-11-15 | `remote/io.github.theluckystrike/tariff-lookup` | 2026-11-09T170017100194 -> 2026-11-15T142424245899 | 2 changed (every tool) | quiet |
| 2026-11-15 | `remote/com.sitecomb/check-website` | 2026-11-11T145656818947 -> 2026-11-15T142424676903 | 1 changed | quiet |
| 2026-11-15 | `remote/com.shopyourcolorseason/mcp` | 2026-11-15T002317391778 -> 2026-11-15T142418866659 | 3 changed | quiet |
| 2026-11-15 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-15T115358538812 -> 2026-11-15T142436173655 | 2 changed | quiet |
| 2026-11-15 | `remote/io.github.MorrisMoe/soulintime` | 2026-11-12T074731317514 -> 2026-11-15T142401251214 | 1 changed | quiet |
| 2026-11-15 | `remote/uk.co.tenderlead/tenderlead` | 2026-11-15T115137614119 -> 2026-11-15T142355371881 | 4 changed | quiet |
| 2026-11-15 | `remote/now.salesjobs/mcp` | 2026-11-14T114916013964 -> 2026-11-15T142347364032 | 1 changed | quiet |
| 2026-11-15 | `remote/io.github.CustomBlinds/cb-shop` | 2026-11-11T145642126030 -> 2026-11-15T142345158411 | 5 changed, 2 added, 3 removed | quiet |
| 2026-11-15 | `remote/com.seqbench/workbench` | 2026-11-15T115333606240 -> 2026-11-15T142340493368 | 1 changed | quiet |
| 2026-11-15 | `remote/app.openkrill/seo-audit` | 2026-11-10T152557148859 -> 2026-11-15T142335529423 | 1 changed | quiet |
| 2026-11-15 | `remote/com.searchfragments/search-fragments` | 2026-11-13T145952199635 -> 2026-11-15T142333015599 | 1 changed | quiet |
| 2026-11-15 | `remote/fr.quirecrute/offres-emploi` | 2026-11-09T165718507679 -> 2026-11-15T142315115892 | 3 changed (every tool) | quiet |
| 2026-11-15 | `remote/app.openkrill/remote-jobs` | 2026-11-11T145557763579 -> 2026-11-15T142305201367 | 1 changed | quiet |
| 2026-11-15 | `remote/com.risetive/mcp` | 2026-11-11T071336990812 -> 2026-11-15T142304335623 | 1 added | quiet |
| 2026-11-15 | `remote/io.github.joelp22-maker/referencesource` | 2026-11-15T115236882069 -> 2026-11-15T142259961443 | 3 changed | quiet |
| 2026-11-15 | `remote/com.remoshift/jobs` | 2026-11-15T115301335112 -> 2026-11-15T142254319707 | 1 changed | quiet |
| 2026-11-15 | `remote/app.seatsherpa/rides` | 2026-11-14T115007621479 -> 2026-11-15T142226720476 | 5 changed | quiet |
| 2026-11-15 | `remote/xyz.pokeka/card-prices` | 2026-11-14T135727689290 -> 2026-11-15T142224911466 | 4 changed | quiet |
| 2026-11-15 | `remote/gg.plazmi/plazmi` | 2026-11-15T115200038267 -> 2026-11-15T142220853875 | 9 changed | quiet |
| 2026-11-15 | `remote/app.openkrill/outreach-desk` | 2026-10-22T105613380748 -> 2026-11-15T142212516614 | 1 changed | quiet |
| 2026-11-15 | `remote/com.othermindset/campus` | 2026-11-15T002310197723 -> 2026-11-15T142210621066 | 1 changed | quiet |
| 2026-11-15 | `remote/gg.pixly/mcp` | 2026-11-14T183333623384 -> 2026-11-15T142206988654 | 1 changed | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-lagos_life` | 2026-11-11T230820699886 -> 2026-11-15T142153906752 | 1 added, 32 removed | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-juicyway` | 2026-11-11T230820643684 -> 2026-11-15T142153908128 | 1 added, 23 removed | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-hacker_news` | 2026-11-11T230820670193 -> 2026-11-15T142153891948 | 1 added, 14 removed | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-bgpt-yarngpt` | 2026-11-11T230820581367 -> 2026-11-15T142153729316 | 1 added, 4 removed | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-bgpt-pdf-generator` | 2026-11-11T230820402258 -> 2026-11-15T142153444426 | 1 added, 7 removed | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-bgpt-livescore` | 2026-11-11T230820615032 -> 2026-11-15T142153410018 | 1 added, 12 removed | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-bgpt-instagram-android` | 2026-11-11T230819950082 -> 2026-11-15T142153422281 | 1 added, 16 removed | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-bgpt-cacnigeria` | 2026-11-11T230819752917 -> 2026-11-15T142153319905 | 1 added, 3 removed | quiet |
| 2026-11-15 | `remote/co.civai.nova/mcp-audience-resolver` | 2026-11-12T154344182275 -> 2026-11-15T142153038189 | 1 added, 45 removed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 62293 substantive, 40686 that changed only numbers (a catalogue counter ticking, a date), 1030 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 56231 | 17878 | 38353 | 0 |
| `a2awire.com` | 2707 | 2707 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 431 | 431 | 0 | 0 |
| `civai.co` | 341 | 341 | 0 | 0 |
| `revmesh2074.workers.dev` | 266 | 233 | 33 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `sistaminuten.se` | 240 | 6 | 0 | 234 |
| `afbudsrejser.dk` | 239 | 6 | 0 | 233 |
| `akkilahdot.fi` | 239 | 6 | 0 | 233 |
| `restplass.no` | 239 | 6 | 0 | 233 |
| `socialloop.ai` | 231 | 231 | 0 | 0 |
| 9478 other operators | 40246 | 37849 | 2300 | 97 |
