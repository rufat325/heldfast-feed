# MCP server tool changes

Last change observed 2026-11-24T18:30:18+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 18238 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 43073 hosted endpoints (read daily, and every four hours while they keep changing).

133589 changes to a tool definition: 5334 npm releases (5088 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 128255 readings of hosted servers that found their tools changed; 4990 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-24 | `remote/io.github.sathya-sankaran/yellide` | 2026-11-16T163411772580 -> 2026-11-24T183018942538 | 3 changed | quiet |
| 2026-11-24 | `remote/io.github.sudzikcoin/suverse-agent-assistant` | 2026-11-24T165818425673 -> 2026-11-24T182959933740 | 3 changed | quiet |
| 2026-11-24 | `remote/no.restplass/travel-search` | 2026-11-24T165806023020 -> 2026-11-24T182948451779 | 1 changed | quiet |
| 2026-11-24 | `remote/com.veridionmarkets/disclosures` | 2026-11-21T215743463741 -> 2026-11-24T182918397507 | 2 changed | quiet |
| 2026-11-24 | `remote/io.taifoon/coordination-layer.1` | 2026-11-24T170243689884 -> 2026-11-24T182909010617 | 1 changed | quiet |
| 2026-11-24 | `remote/io.suverse.www/catalog` | 2026-11-24T170243363702 -> 2026-11-24T182908761624 | 3 changed | quiet |
| 2026-11-24 | `remote/com.breadboardhub/circuits` | 2026-11-24T165712272146 -> 2026-11-24T182904031937 | 2 changed | quiet |
| 2026-11-24 | `remote/se.sistaminuten/travel-search` | 2026-11-24T170230895961 -> 2026-11-24T182903351280 | 1 changed | quiet |
| 2026-11-24 | `remote/dk.afbudsrejser/travel-search` | 2026-11-24T165658951839 -> 2026-11-24T182854228116 | 1 changed | quiet |
| 2026-11-24 | `remote/studio.gradients/mcp` | 2026-11-24T170333856087 -> 2026-11-24T182848006684 | 1 changed | quiet |
| 2026-11-24 | `remote/org.omenz.www/agent-tools` | 2026-11-24T170214509377 -> 2026-11-24T182846286405 | 2 added | quiet |
| 2026-11-24 | `remote/io.github.jhonnysabino/moedux` | 2026-11-24T170208459681 -> 2026-11-24T182842574700 | 4 changed, 1 added | quiet |
| 2026-11-24 | `remote/fi.akkilahdot/travel-search` | 2026-11-24T170301979779 -> 2026-11-24T182816120208 | 1 changed | quiet |
| 2026-11-24 | `remote/com.vidreno/mcp` | 2026-11-24T165620356269 -> 2026-11-24T182816533303 | 1 changed | quiet |
| 2026-11-24 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-24T170217846833 -> 2026-11-24T182734341919 | 3 changed | quiet |
| 2026-11-24 | `remote/expert.tld/tld-expert` | 2026-11-24T165516895016 -> 2026-11-24T182714944568 | 2 changed | quiet |
| 2026-11-24 | `remote/online.waitapp/waitapp` | 2026-11-17T164653165102 -> 2026-11-24T182716405859 | 5 changed, 3 added | quiet |
| 2026-11-24 | `remote/ai.rfsrisk/syri` | 2026-09-23T163024325701 -> 2026-11-24T182632624491 | 1 added | quiet |
| 2026-11-24 | `remote/work.agentexchange/us-macro-regime` | 2026-11-24T050340013191 -> 2026-11-24T182613814947 | 1 changed | review |
| 2026-11-24 | `remote/com.vectorstreamsystems/mbestudio` | 2026-11-23T185205236237 -> 2026-11-24T182552004255 | 1 added | quiet |
| 2026-11-24 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-24T165951412198 -> 2026-11-24T182509443974 | 1 changed | quiet |
| 2026-11-24 | `remote/io.github.CustomBlinds/cb-shop` | 2026-11-24T165729951695 -> 2026-11-24T182443848876 | 1 changed | quiet |
| 2026-11-24 | `remote/com.caelaralabs/seo` | 2026-11-24T165715701498 -> 2026-11-24T182431865705 | 1 added | quiet |
| 2026-11-24 | `remote/io.github.Allanoo99/mizan` | 2026-11-24T165207811279 -> 2026-11-24T182348523151 | 1 changed | quiet |
| 2026-11-24 | `remote/it.proofprofile/isrc-music-copyright-proof-bitcoin` | 2026-11-23T184923884009 -> 2026-11-24T182342046710 | 2 changed | quiet |
| 2026-11-24 | `remote/in.productgrowth/productgrowth` | 2026-11-23T184921806748 -> 2026-11-24T182341258041 | 5 changed | quiet |
| 2026-11-24 | `remote/com.roadcutco/roadcut` | 2026-11-24T165831380121 -> 2026-11-24T182330747512 | 1 changed | quiet |
| 2026-11-24 | `remote/io.github.chandradot99/voicedex` | 2026-11-23T185203610696 -> 2026-11-24T182304277523 | 3 changed | quiet |
| 2026-11-24 | `remote/io.suverse.versum/catalog` | 2026-11-24T165415600700 -> 2026-11-24T182255569973 | 3 changed | quiet |
| 2026-11-24 | `remote/dev.pcbbrew/pcbbrew` | 2026-11-24T165522257490 -> 2026-11-24T182240353264 | 1 changed | quiet |
| 2026-11-24 | `remote/com.partstable/mcp` | 2026-11-23T185101709718 -> 2026-11-24T182235135847 | 1 changed | quiet |
| 2026-11-24 | `remote/io.github.FTHTrading/genesis402-mcp` | 2026-10-20T104302881789 -> 2026-11-24T182232790257 | 22 changed (every tool) | quiet |
| 2026-11-24 | `remote/com.theaiworldnetwork/aifusionone` | 2026-11-24T165303841577 -> 2026-11-24T182138199003 | 45 added | review |
| 2026-11-24 | `remote/com.caelaralabs/media` | 2026-11-24T164935159934 -> 2026-11-24T182119193071 | 1 added | quiet |
| 2026-11-24 | `remote/net.mipiso/spain-property-rules` | 2026-11-23T184944384390 -> 2026-11-24T182122071791 | 1 added | quiet |
| 2026-11-24 | `remote/com.zestplanche.mcp/zp-mcp-server-alpic` | 2026-11-23T184656298595 -> 2026-11-24T182109102828 | 4 changed | quiet |
| 2026-11-24 | `remote/to.stomp/editor` | 2026-11-24T165224803799 -> 2026-11-24T182043021719 | 3 changed | quiet |
| 2026-11-24 | `remote/network.moonbeam.next/paid-calls` | 2026-11-23T184740208995 -> 2026-11-24T182023266829 | 2 removed | quiet |
| 2026-11-24 | `remote/com.caelaralabs/social` | 2026-11-24T165201415437 -> 2026-11-24T182016035466 | 1 added | quiet |
| 2026-11-24 | `remote/com.sigoseguros/auto-quote` | 2026-11-13T150052304462 -> 2026-11-24T182015459603 | 1 changed | quiet |
| 2026-11-24 | `remote/org.r3js/r3` | 2026-11-24T164810213140 -> 2026-11-24T181956061414 | 1 changed | quiet |
| 2026-11-24 | `remote/net.pendingdelete/mcp` | 2026-11-24T164750803916 -> 2026-11-24T181940497675 | 1 changed | quiet |
| 2026-11-24 | `remote/com.productclank/productclank` | 2026-11-24T165229356949 -> 2026-11-24T181920217535 | 3 changed | quiet |
| 2026-11-24 | `remote/com.imagiolabs.www/imagio-relay` | 2026-11-23T203913348128 -> 2026-11-24T181849316507 | 16 changed | review |
| 2026-11-24 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-11-24T050420391384 -> 2026-11-24T181846529273 | 1 changed | review |
| 2026-11-24 | `remote/io.github.roomi-fields/osc-bridge` | 2026-11-23T203854887987 -> 2026-11-24T181843212528 | 1 changed | quiet |
| 2026-11-24 | `remote/com.moneda/mcp` | 2026-11-19T123017086761 -> 2026-11-24T181841744373 | 1 changed | quiet |
| 2026-11-24 | `remote/org.georgiacommons/georgia-commons` | 2026-11-24T164631628645 -> 2026-11-24T181822335182 | 3 changed | quiet |
| 2026-11-24 | `remote/io.github.Kindora-PBC/foundation-discovery` | 2026-11-09T165408147831 -> 2026-11-24T181819051394 | 1 changed | quiet |
| 2026-11-24 | `remote/ai.fudge/fudge` | 2026-11-20T155223652551 -> 2026-11-24T181818080923 | 1 changed | quiet |
| 2026-11-24 | `remote/ai.robowrite/mcp` | 2026-11-23T184528301789 -> 2026-11-24T181816729131 | 1 added | quiet |
| 2026-11-24 | `remote/io.github.echopai/echopai-mcp` | 2026-11-24T165130247823 -> 2026-11-24T181807424366 | 4 changed | quiet |
| 2026-11-24 | `remote/co.deadbrands/arena` | 2026-11-24T164559077183 -> 2026-11-24T181751300737 | 1 changed | quiet |
| 2026-11-24 | `remote/io.github.farenberglord-star/orb-studio` | 2026-11-24T164925710295 -> 2026-11-24T181718787804 | 1 added | quiet |
| 2026-11-24 | `remote/io.github.ocean1547-ui/nspros-mcp-gateway` | 2026-11-24T165300861581 -> 2026-11-24T181705261400 | 6 added | quiet |
| 2026-11-24 | `remote/io.github.magichourhq/magic-hour` | 2026-11-24T165236821094 -> 2026-11-24T181643488214 | 31 changed | quiet |
| 2026-11-24 | `remote/it.lazyanalysis/lazyanalysis` | 2026-11-23T203843383528 -> 2026-11-24T181639084418 | 15 added | quiet |
| 2026-11-24 | `remote/com.zola/zola` | 2026-11-24T164811553567 -> 2026-11-24T181559373947 | 5 added | review |
| 2026-11-24 | `remote/com.itscreo/creo` | 2026-11-20T104718835008 -> 2026-11-24T181449876255 | 1 changed | quiet |
| 2026-11-24 | `remote/hu.kodvena/kodvena` | 2026-11-12T153924062476 -> 2026-11-24T181447625664 | 2 changed, 2 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 89228 substantive, 43168 that changed only numbers (a catalogue counter ticking, a date), 1193 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 73018 | 32811 | 40207 | 0 |
| `a2awire.com` | 3838 | 3838 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 527 | 527 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 401 | 401 | 0 | 0 |
| `revmesh2074.workers.dev` | 367 | 312 | 55 | 0 |
| `sistaminuten.se` | 278 | 7 | 0 | 271 |
| `afbudsrejser.dk` | 277 | 7 | 0 | 270 |
| `akkilahdot.fi` | 277 | 7 | 0 | 270 |
| `restplass.no` | 277 | 7 | 0 | 270 |
| `socialloop.ai` | 268 | 268 | 0 | 0 |
| 11271 other operators | 51240 | 48222 | 2906 | 112 |
