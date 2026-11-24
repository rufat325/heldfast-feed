# MCP server tool changes

Last change observed 2026-11-24T19:48:43+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 18238 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 43073 hosted endpoints (read daily, and every four hours while they keep changing).

133691 changes to a tool definition: 5334 npm releases (5088 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 128357 readings of hosted servers that found their tools changed; 4997 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-24 | `remote/io.suverse.versum/catalog` | 2026-11-24T182255569973 -> 2026-11-24T194847012833 | 3 changed | quiet |
| 2026-11-24 | `remote/com.theaiworldnetwork/aifusionone` | 2026-11-24T182138199003 -> 2026-11-24T194830764409 | 75 added | quiet |
| 2026-11-24 | `remote/com.imagiolabs.www/imagio-relay` | 2026-11-24T181849316507 -> 2026-11-24T194812567492 | 16 changed | review |
| 2026-11-24 | `remote/io.github.farenberglord-star/orb-studio` | 2026-11-24T181718787804 -> 2026-11-24T194805626178 | 2 added | quiet |
| 2026-11-24 | `remote/studio.gradients/mcp` | 2026-11-24T182848006684 -> 2026-11-24T194753513043 | 1 changed | quiet |
| 2026-11-24 | `remote/io.github.EasyGerber/easygerber` | 2026-11-24T170321520574 -> 2026-11-24T194752504343 | 1 changed | quiet |
| 2026-11-24 | `remote/fi.akkilahdot/travel-search` | 2026-11-24T182816120208 -> 2026-11-24T194750611335 | 1 changed | quiet |
| 2026-11-24 | `remote/com.weverlabs/agentic-rails` | 2026-11-24T050410060006 -> 2026-11-24T194756323493 | 8 added | quiet |
| 2026-11-24 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-24T182734341919 -> 2026-11-24T194746226794 | 3 changed | quiet |
| 2026-11-24 | `remote/com.spocont/ifrCoworker` | 2026-11-24T050333850512 -> 2026-11-24T194740858206 | 1 changed | quiet |
| 2026-11-24 | `remote/cloud.pandy/tickets` | 2026-11-23T185246952365 -> 2026-11-24T194738213148 | 1 changed | quiet |
| 2026-11-24 | `remote/com.airsidelabs/aviation-tools` | 2026-11-24T164411009689 -> 2026-11-24T194731896865 | 2 changed | quiet |
| 2026-11-24 | `remote/io.github.sudzikcoin/suverse-agent-assistant` | 2026-11-24T182959933740 -> 2026-11-24T194731303840 | 3 changed | quiet |
| 2026-11-24 | `remote/com.statutewire/psv` | 2026-11-24T050339408715 -> 2026-11-24T194731266549 | 2 changed | quiet |
| 2026-11-24 | `remote/no.restplass/travel-search` | 2026-11-24T182948451779 -> 2026-11-24T194728444544 | 1 changed | quiet |
| 2026-11-24 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-24T182509443974 -> 2026-11-24T194729070985 | 1 changed | quiet |
| 2026-11-24 | `remote/io.github.MKagesawa/masadeals` | 2026-11-24T164351902917 -> 2026-11-24T194727980247 | 1 changed | quiet |
| 2026-11-24 | `remote/app.vercel.mare-liberum/sea` | 2026-11-24T164350373486 -> 2026-11-24T194728410711 | 55 changed (every tool) | quiet |
| 2026-11-24 | `remote/io.github.QDThead/signal-lab` | 2026-11-24T050334413009 -> 2026-11-24T194727006175 | 4 changed | quiet |
| 2026-11-24 | `remote/se.sistaminuten/travel-search` | 2026-11-24T182903351280 -> 2026-11-24T194723007528 | 1 changed | quiet |
| 2026-11-24 | `remote/io.taifoon/coordination-layer.1` | 2026-11-24T182909010617 -> 2026-11-24T194724221189 | 1 changed | review |
| 2026-11-24 | `remote/io.suverse.www/catalog` | 2026-11-24T182908761624 -> 2026-11-24T194725405646 | 3 changed | quiet |
| 2026-11-24 | `remote/org.omenz.www/agent-tools` | 2026-11-24T182846286405 -> 2026-11-24T194719818838 | 1 changed | quiet |
| 2026-11-24 | `remote/dk.afbudsrejser/travel-search` | 2026-11-24T182854228116 -> 2026-11-24T194720386592 | 1 changed | quiet |
| 2026-11-24 | `remote/com.remoshift/jobs` | 2026-11-24T165820601324 -> 2026-11-24T194719585030 | 1 changed | quiet |
| 2026-11-24 | `remote/com.vidreno/mcp` | 2026-11-24T182816533303 -> 2026-11-24T194716536048 | 1 changed | quiet |
| 2026-11-24 | `remote/io.github.ohad6k/viberaven-guides` | 2026-11-24T165619501282 -> 2026-11-24T194715912465 | 4 changed | quiet |
| 2026-11-24 | `remote/io.github.kkfir13/valuedge` | 2026-11-24T165610995817 -> 2026-11-24T194714558469 | 1 added | quiet |
| 2026-11-24 | `remote/no.pristavla/pristavla` | 2026-11-23T184923992361 -> 2026-11-24T194714680582 | 1 changed | quiet |
| 2026-11-24 | `remote/online.agentes-lqn.plugin/lqn-broker` | 2026-11-23T184906394429 -> 2026-11-24T194712451293 | 1 changed | quiet |
| 2026-11-24 | `remote/expert.tld/tld-expert` | 2026-11-24T182714944568 -> 2026-11-24T194711405598 | 1 changed | quiet |
| 2026-11-24 | `remote/ai.guestlogic/guest-logic` | 2026-11-24T180838118132 -> 2026-11-24T194709365694 | 13 added | quiet |
| 2026-11-24 | `remote/work.agentexchange/us-macro-regime` | 2026-11-24T182613814947 -> 2026-11-24T194706188603 | 1 changed | review |
| 2026-11-24 | `remote/network.moonbeam.next/paid-calls` | 2026-11-24T182023266829 -> 2026-11-24T194708187919 | 2 added | review |
| 2026-11-24 | `remote/ae.brainy.tipline/gta6` | 2026-11-23T185504609523 -> 2026-11-24T194702463977 | 2 added | quiet |
| 2026-11-24 | `remote/re.rundata/temps-reel` | 2026-11-24T165302285620 -> 2026-11-24T194656161017 | 1 changed | quiet |
| 2026-11-24 | `remote/com.radarbg/radar-tools` | 2026-11-24T165219733608 -> 2026-11-24T194651571810 | 166 changed (every tool) | quiet |
| 2026-11-24 | `remote/io.github.CustomBlinds/cb-shop` | 2026-11-24T182443848876 -> 2026-11-24T194650194776 | 1 changed | quiet |
| 2026-11-24 | `remote/xyz.pokter/marketplace` | 2026-11-23T184905284434 -> 2026-11-24T194643688277 | 1 changed | quiet |
| 2026-11-24 | `remote/net.placeprofile/evidence` | 2026-11-23T184902390650 -> 2026-11-24T194644416239 | 2 changed | quiet |
| 2026-11-24 | `remote/com.kernelcad/kernelcad` | 2026-11-24T165222330914 -> 2026-11-24T194642416662 | 4 changed | quiet |
| 2026-11-24 | `remote/io.github.daniel3303/equibles` | 2026-11-24T165115438333 -> 2026-11-24T194636999368 | 1 changed | quiet |
| 2026-11-24 | `remote/ai.poly/docs-mcp` | 2026-11-23T183534555024 -> 2026-11-24T194636659466 | 1 changed | quiet |
| 2026-11-24 | `remote/io.github.GrayWolf8-creator/gw8-signal-api` | 2026-11-22T103810051409 -> 2026-11-24T194631699515 | 3 changed | quiet |
| 2026-11-24 | `remote/com.zestplanche.mcp/zp-mcp-server-alpic` | 2026-11-24T182109102828 -> 2026-11-24T194631915284 | 5 changed (every tool) | quiet |
| 2026-11-24 | `remote/com.dcblueprint/data-centres` | 2026-11-24T163837113259 -> 2026-11-24T194631585155 | 2 changed | quiet |
| 2026-11-24 | `remote/app.lonepair/lonepair` | 2026-11-24T050306132205 -> 2026-11-24T194622574595 | 1 changed | quiet |
| 2026-11-24 | `remote/site.cryptofeed402/feed` | 2026-11-22T220954256976 -> 2026-11-24T194624142497 | 1 changed | quiet |
| 2026-11-24 | `remote/ai.fudge/fudge` | 2026-11-24T181818080923 -> 2026-11-24T194619544448 | 1 changed | quiet |
| 2026-11-24 | `remote/fr.ip73/ip73` | 2026-11-24T181205920911 -> 2026-11-24T194620150670 | 2 changed | quiet |
| 2026-11-24 | `remote/co.deadbrands/arena` | 2026-11-24T181751300737 -> 2026-11-24T194616194785 | 1 changed | quiet |
| 2026-11-24 | `remote/app.chopit/chopit` | 2026-11-24T163734327310 -> 2026-11-24T194616850234 | 1 changed | quiet |
| 2026-11-24 | `remote/au.com.getneatly/neatly` | 2026-11-24T164626400514 -> 2026-11-24T194613108271 | 1 changed | quiet |
| 2026-11-24 | `remote/com.gameshopenter/shop` | 2026-11-23T203807135610 -> 2026-11-24T194613877886 | 2 changed | quiet |
| 2026-11-24 | `remote/us.consci/conscius.1` | 2026-11-24T165028892324 -> 2026-11-24T194609680145 | 2 changed | quiet |
| 2026-11-24 | `remote/com.manusights/manusights` | 2026-11-24T050254476073 -> 2026-11-24T194609261415 | 1 changed | quiet |
| 2026-11-24 | `remote/app.vercel.fork-for-agents/fork` | 2026-11-24T180910849384 -> 2026-11-24T194609630997 | 1 changed | quiet |
| 2026-11-24 | `remote/com.licensesaas/marketplace` | 2026-11-24T164406318770 -> 2026-11-24T194607471785 | 3 changed, 2 added | quiet |
| 2026-11-24 | `remote/dev.mareliberum/sea` | 2026-11-24T164913720944 -> 2026-11-24T194605022919 | 55 changed (every tool) | quiet |
| 2026-11-24 | `remote/app.mahonia/mahonia` | 2026-11-23T081848805738 -> 2026-11-24T194602965966 | 3 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 89318 substantive, 43176 that changed only numbers (a catalogue counter ticking, a date), 1197 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 73018 | 32811 | 40207 | 0 |
| `a2awire.com` | 3838 | 3838 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 527 | 527 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 401 | 401 | 0 | 0 |
| `revmesh2074.workers.dev` | 368 | 313 | 55 | 0 |
| `sistaminuten.se` | 279 | 7 | 0 | 272 |
| `afbudsrejser.dk` | 278 | 7 | 0 | 271 |
| `akkilahdot.fi` | 278 | 7 | 0 | 271 |
| `restplass.no` | 278 | 7 | 0 | 271 |
| `socialloop.ai` | 269 | 269 | 0 | 0 |
| 11280 other operators | 51336 | 48310 | 2914 | 112 |
