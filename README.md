# MCP server tool changes

Last change observed 2026-11-25T15:04:06+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 18238 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 43073 hosted endpoints (read daily, and every four hours while they keep changing).

136596 changes to a tool definition: 5421 npm releases (5175 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 131175 readings of hosted servers that found their tools changed; 5091 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-25 | `remote/io.suverse.www/catalog` | 2026-11-25T105951892046 -> 2026-11-25T150408175906 | 3 changed | quiet |
| 2026-11-25 | `remote/se.sistaminuten/travel-search` | 2026-11-25T105947625014 -> 2026-11-25T150406591420 | 1 changed | quiet |
| 2026-11-25 | `remote/com.ridekick/ridekick` | 2026-11-25T105943538977 -> 2026-11-25T150405827629 | 1 changed | quiet |
| 2026-11-25 | `remote/nl.prijsprofeet/prijsprofeet-de` | 2026-11-24T170221027709 -> 2026-11-25T150406618030 | 1 changed | quiet |
| 2026-11-25 | `remote/org.omenz.www/agent-tools` | 2026-11-25T035022991730 -> 2026-11-25T150403473363 | 2 added | review |
| 2026-11-25 | `remote/io.github.jhonnysabino/moedux` | 2026-11-25T035022497900 -> 2026-11-25T150403056138 | 3 added | review |
| 2026-11-25 | `remote/com.herbertandphyllis/mcp` | 2026-11-24T170149996656 -> 2026-11-25T150358464613 | 1 changed | quiet |
| 2026-11-25 | `remote/it.expatliving/data` | 2026-11-24T170139544936 -> 2026-11-25T150357716339 | 2 changed | quiet |
| 2026-11-25 | `remote/dev.workers.moneytools.x402-pay-precheck/pay-precheck` | 2026-11-24T165619499749 -> 2026-11-25T150356395602 | 2 changed | quiet |
| 2026-11-25 | `remote/io.github.renderedfits/open-data` | 2026-11-23T185337108847 -> 2026-11-25T150355485178 | 3 added | quiet |
| 2026-11-25 | `remote/fr.publicoffre/marches-publics` | 2026-11-24T170358274618 -> 2026-11-25T150354317148 | 1 changed | quiet |
| 2026-11-25 | `remote/studio.gradients/mcp` | 2026-11-25T110145636841 -> 2026-11-25T150349718337 | 1 changed | quiet |
| 2026-11-25 | `remote/fi.akkilahdot/travel-search` | 2026-11-25T110116727274 -> 2026-11-25T150348191315 | 1 changed | quiet |
| 2026-11-25 | `remote/xyz.urbangametheory/urban-game-theory` | 2026-11-25T105747506434 -> 2026-11-25T150348488273 | 9 changed | quiet |
| 2026-11-25 | `remote/io.github.sathya-sankaran/yellide` | 2026-11-25T035006792436 -> 2026-11-25T150346014089 | 2 changed | quiet |
| 2026-11-25 | `remote/dev.moneytools/tools` | 2026-11-24T165919113559 -> 2026-11-25T150344104570 | 2 changed | quiet |
| 2026-11-25 | `remote/com.aurioapp/calculadoras` | 2026-11-23T185238131514 -> 2026-11-25T150344863148 | 2 changed | quiet |
| 2026-11-25 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-25T110038635865 -> 2026-11-25T150344459681 | 3 changed | quiet |
| 2026-11-25 | `remote/io.github.sudzikcoin/suverse-agent-assistant` | 2026-11-25T110054762229 -> 2026-11-25T150344924715 | 3 changed | quiet |
| 2026-11-25 | `remote/io.github.SecondShotAI/verifylite` | 2026-11-24T170215807111 -> 2026-11-25T150342898997 | 3 changed | quiet |
| 2026-11-25 | `remote/dev.vetagent/vetagent` | 2026-11-24T170217706933 -> 2026-11-25T150343614236 | 1 changed | quiet |
| 2026-11-25 | `remote/no.restplass/travel-search` | 2026-11-25T110041346832 -> 2026-11-25T150342699369 | 1 changed | quiet |
| 2026-11-25 | `remote/tech.upto/up-to-tech` | 2026-11-25T110022537554 -> 2026-11-25T150341269316 | 5 changed, 8 added | quiet |
| 2026-11-25 | `remote/pl.podziemieanalityczne/dane` | 2026-11-24T165800364341 -> 2026-11-25T150341677008 | 1 changed | quiet |
| 2026-11-25 | `remote/io.suverse.versum/catalog` | 2026-11-25T110237462933 -> 2026-11-25T150342180528 | 3 changed | quiet |
| 2026-11-25 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-24T165332908597 -> 2026-11-25T150337539551 | 1 added | quiet |
| 2026-11-25 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-24T170102668244 -> 2026-11-25T150335742363 | 1 changed | quiet |
| 2026-11-25 | `remote/io.github.Parthuss/skwirl` | 2026-11-24T165749410944 -> 2026-11-25T150333927568 | 13 changed (every tool) | quiet |
| 2026-11-25 | `remote/dk.afbudsrejser/travel-search` | 2026-11-25T105933467876 -> 2026-11-25T150334605945 | 1 changed | quiet |
| 2026-11-25 | `remote/com.whoreadsthe/agents` | 2026-11-25T105924399442 -> 2026-11-25T150333525473 | 1 changed | quiet |
| 2026-11-25 | `remote/com.caelaralabs/seo` | 2026-11-25T034955110740 -> 2026-11-25T150330703929 | 1 added | quiet |
| 2026-11-25 | `remote/com.vidreno/mcp` | 2026-11-24T194716536048 -> 2026-11-25T150330945924 | 1 changed | quiet |
| 2026-11-25 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-11-25T110033999262 -> 2026-11-25T150328348682 | 3 changed | quiet |
| 2026-11-25 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-25T105834402629 -> 2026-11-25T150328740027 | 1 changed | quiet |
| 2026-11-25 | `remote/com.soundiiz/soundiiz` | 2026-11-23T185014610190 -> 2026-11-25T150328569606 | 3 changed | quiet |
| 2026-11-25 | `remote/com.caelaralabs/social` | 2026-11-25T035011168607 -> 2026-11-25T150327838627 | 1 added | quiet |
| 2026-11-25 | `remote/com.trendtemplate/templates` | 2026-11-25T105822792996 -> 2026-11-25T150326468209 | 2 changed | quiet |
| 2026-11-25 | `remote/io.quantumdev/site` | 2026-11-23T185205684087 -> 2026-11-25T150323034135 | 2 changed, 2 added | quiet |
| 2026-11-25 | `remote/io.github.davidgringras/scrutica` | 2026-11-25T105753835059 -> 2026-11-25T150323608746 | 2 changed | quiet |
| 2026-11-25 | `remote/pl.finwire/data` | 2026-11-25T105439081464 -> 2026-11-25T150324798122 | 2 changed, 1 added | quiet |
| 2026-11-25 | `remote/com.prepportglobal/service-planner` | 2026-11-25T105425307873 -> 2026-11-25T150320830887 | 1 changed | quiet |
| 2026-11-25 | `remote/com.imagiolabs.www/imagio-relay` | 2026-11-24T194812567492 -> 2026-11-25T150318526972 | 1 changed, 8 added | quiet |
| 2026-11-25 | `remote/io.github.spree/ecommerce-docs` | 2026-11-24T165410499313 -> 2026-11-25T150317450741 | 1 changed | quiet |
| 2026-11-25 | `remote/com.realcryptocap/realcryptocap` | 2026-11-23T184842742273 -> 2026-11-25T150317003422 | 3 changed, 6 removed | quiet |
| 2026-11-25 | `remote/com.rabbitimport/rabbit` | 2026-11-23T184947552094 -> 2026-11-25T150318275521 | 1 added | quiet |
| 2026-11-25 | `remote/bot.qed/register` | 2026-11-23T184832776533 -> 2026-11-25T150316641639 | 3 changed, 2 added | quiet |
| 2026-11-25 | `remote/com.papyrascoupons/coupons` | 2026-11-23T185059529402 -> 2026-11-25T150313970011 | 2 added | quiet |
| 2026-11-25 | `remote/com.sitesinthewoods/monitor` | 2026-11-25T105645360678 -> 2026-11-25T150312987104 | 7 changed, 2 added | quiet |
| 2026-11-25 | `remote/online.agentes-lqn.plugin/lqn-broker` | 2026-11-24T194712451293 -> 2026-11-25T150311990718 | 3 changed | quiet |
| 2026-11-25 | `remote/no.pristavla/pristavla` | 2026-11-25T105640145634 -> 2026-11-25T150313259550 | 1 changed | quiet |
| 2026-11-25 | `remote/shop.photosweat/remove-background` | 2026-11-25T105807644717 -> 2026-11-25T150310314205 | 1 changed | quiet |
| 2026-11-25 | `remote/io.github.KevinCapri/nowcast-mcp` | 2026-11-25T105525681591 -> 2026-11-25T150306615305 | 13 changed (every tool) | quiet |
| 2026-11-25 | `remote/com.radarbg/radar-tools` | 2026-11-25T105529024299 -> 2026-11-25T150303949660 | 1 changed | quiet |
| 2026-11-25 | `remote/ai.reevi/find-buyers` | 2026-11-25T105540455673 -> 2026-11-25T150303193979 | 1 changed | quiet |
| 2026-11-25 | `remote/com.neblla/neblla` | 2026-11-25T105506732735 -> 2026-11-25T150302730516 | 5 changed | quiet |
| 2026-11-25 | `remote/com.mylatinlife/data` | 2026-11-23T081910822649 -> 2026-11-25T150302521299 | 4 changed | quiet |
| 2026-11-25 | `remote/md.mostlyright/datasets` | 2026-11-24T164839020873 -> 2026-11-25T150300025766 | 2 changed | quiet |
| 2026-11-25 | `remote/com.mooncatcherwire/wire` | 2026-11-23T184715418019 -> 2026-11-25T150300197927 | 1 changed | quiet |
| 2026-11-25 | `remote/ca.movahedi/privacy` | 2026-11-24T165538587514 -> 2026-11-25T150300553250 | 1 changed | quiet |
| 2026-11-25 | `remote/io.github.Playpowerpolitics/powerplayers` | 2026-11-24T050325734860 -> 2026-11-25T150258536155 | 1 changed, 1 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 92141 substantive, 43245 that changed only numbers (a catalogue counter ticking, a date), 1210 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 74885 | 34677 | 40208 | 0 |
| `a2awire.com` | 3838 | 3838 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 533 | 533 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 401 | 401 | 0 | 0 |
| `revmesh2074.workers.dev` | 370 | 315 | 55 | 0 |
| `sistaminuten.se` | 282 | 7 | 0 | 275 |
| `afbudsrejser.dk` | 281 | 7 | 0 | 274 |
| `akkilahdot.fi` | 281 | 7 | 0 | 274 |
| `restplass.no` | 281 | 7 | 0 | 274 |
| `socialloop.ai` | 272 | 272 | 0 | 0 |
| 11452 other operators | 52351 | 49256 | 2982 | 113 |
