# MCP server tool changes

Last change observed 2026-10-19T05:25:09+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10495 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 23695 hosted endpoints (read daily, and every four hours while they keep changing).

32856 changes to a tool definition: 1188 npm releases (942 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 31668 readings of hosted servers that found their tools changed; 2117 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-19 | `remote/com.zinvyl/marketplace` | 2026-10-18T113330249000 -> 2026-10-19T052510130012 | 1 changed | quiet |
| 2026-10-19 | `remote/fi.akkilahdot/travel-search` | 2026-10-18T223953555965 -> 2026-10-19T052500241961 | 1 changed | quiet |
| 2026-10-19 | `remote/us.srv.vehcdj664efetfrsolne5umanq/quoteproof-mcp` | 2026-10-18T223949075287 -> 2026-10-19T052457797879 | 1 changed | quiet |
| 2026-10-19 | `remote/com.achivx/stablescan` | 2026-10-18T223938382874 -> 2026-10-19T052442585298 | 1 changed | quiet |
| 2026-10-19 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-18T223937142282 -> 2026-10-19T052441243839 | 1 changed | quiet |
| 2026-10-19 | `remote/no.restplass/travel-search` | 2026-10-18T224016162575 -> 2026-10-19T052440777376 | 1 changed | quiet |
| 2026-10-19 | `remote/com.meridiandispatch/travel-guides` | 2026-10-18T113407145263 -> 2026-10-19T052438895865 | 4 changed, 1 removed | quiet |
| 2026-10-19 | `remote/com.remoshift/jobs` | 2026-10-18T223932302534 -> 2026-10-19T052435866942 | 1 changed | quiet |
| 2026-10-19 | `remote/dk.afbudsrejser/travel-search` | 2026-10-18T224008491674 -> 2026-10-19T052433173313 | 1 changed | quiet |
| 2026-10-19 | `remote/app.openkrill/postkit` | 2026-10-18T190032248176 -> 2026-10-19T052430372557 | 1 changed | quiet |
| 2026-10-19 | `remote/com.viarapidaservices/mcp` | 2026-10-18T224005479181 -> 2026-10-19T052429574384 | 9 changed (every tool) | quiet |
| 2026-10-19 | `remote/me.phor/phorme-training` | 2026-10-18T223925152129 -> 2026-10-19T052428232222 | 3 changed, 12 added | quiet |
| 2026-10-19 | `remote/com.plainrecords/us-recalls-food-products-vehicles` | 2026-10-18T125033549748 -> 2026-10-19T052428568651 | 2 changed | quiet |
| 2026-10-19 | `remote/io.taifoon/coordination-layer.1` | 2026-10-18T224014380994 -> 2026-10-19T052423545284 | 1 changed | review |
| 2026-10-19 | `remote/com.veridionmarkets/disclosures` | 2026-10-18T051350481933 -> 2026-10-19T052424525816 | 2 changed | quiet |
| 2026-10-19 | `remote/com.odilelabs/odile` | 2026-10-18T051325385199 -> 2026-10-19T052424810977 | 2 added | quiet |
| 2026-10-19 | `remote/se.sistaminuten/travel-search` | 2026-10-18T224013712807 -> 2026-10-19T052423432371 | 1 changed | quiet |
| 2026-10-19 | `remote/com.neblla/neblla` | 2026-10-18T190022110957 -> 2026-10-19T052422541274 | 8 changed, 2 added | quiet |
| 2026-10-19 | `remote/io.github.girapphe/memostem` | 2026-10-17T055615236133 -> 2026-10-19T052423671763 | 1 changed | quiet |
| 2026-10-19 | `remote/com.naxytra/xytara-mcp-executor` | 2026-10-17T060423918327 -> 2026-10-19T052421583850 | 17 changed (every tool) | review |
| 2026-10-19 | `remote/com.multicinesortega/cartelera` | 2026-10-18T223919577008 -> 2026-10-19T052422832387 | 1 changed | quiet |
| 2026-10-19 | `remote/cn.tandiu/data` | 2026-10-17T060414387662 -> 2026-10-19T052422071185 | 1 added | quiet |
| 2026-10-19 | `remote/com.statisticsoftheworld/sotw` | 2026-10-17T060315766168 -> 2026-10-19T052419323825 | 1 changed | quiet |
| 2026-10-19 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-18T190013737800 -> 2026-10-19T052419231190 | 5 changed | quiet |
| 2026-10-19 | `remote/at.space-core/game` | 2026-10-18T051507549107 -> 2026-10-19T052419992262 | 2 changed | quiet |
| 2026-10-19 | `remote/io.github.cyanheads/secedgar-mcp-server` | 2026-10-17T060251975810 -> 2026-10-19T052416148348 | 13 changed | quiet |
| 2026-10-19 | `remote/app.openkrill/videograb` | 2026-10-17T055532652394 -> 2026-10-19T052414818257 | 3 changed | quiet |
| 2026-10-19 | `remote/ai.weio/site-check` | 2026-10-18T190011686832 -> 2026-10-19T052415663940 | 3 added, 2 removed | quiet |
| 2026-10-19 | `remote/app.soclo/soclo-mcp` | 2026-10-18T051316444223 -> 2026-10-19T052415050206 | 19 changed | quiet |
| 2026-10-19 | `remote/com.shipstatic/mcp` | 2026-10-17T055520864376 -> 2026-10-19T052412270904 | 1 changed | quiet |
| 2026-10-19 | `remote/app.openkrill/transcript-kit` | 2026-10-18T190006715060 -> 2026-10-19T052412017083 | 1 changed | quiet |
| 2026-10-19 | `remote/org.sellthenews/sellthenews` | 2026-10-17T055519638971 -> 2026-10-19T052411131860 | 1 changed | quiet |
| 2026-10-19 | `remote/io.github.wygogogo19/robotbase-mcp` | 2026-10-18T190015616339 -> 2026-10-19T052413155261 | 10 added | review |
| 2026-10-19 | `remote/com.thefomite/fomite` | 2026-10-18T051335886119 -> 2026-10-19T052411205646 | 1 changed | quiet |
| 2026-10-19 | `remote/com.thefilmmap/filming-locations` | 2026-10-17T055506437410 -> 2026-10-19T052411363965 | 1 changed | quiet |
| 2026-10-19 | `remote/ai.rokha/rokha` | 2026-10-18T223945709920 -> 2026-10-19T052411873008 | 1 added | quiet |
| 2026-10-19 | `remote/studio.sleeperhit/public-discovery` | 2026-10-17T055448203928 -> 2026-10-19T052407689376 | 1 changed | quiet |
| 2026-10-19 | `remote/io.github.richardsolomou/praetorium` | 2026-10-17T224348788138 -> 2026-10-19T052407658714 | 2 changed | quiet |
| 2026-10-19 | `remote/app.openkrill/shop-duty` | 2026-10-17T055443106152 -> 2026-10-19T052406466065 | 4 changed | quiet |
| 2026-10-19 | `remote/im.peoplesearch/email-finder` | 2026-10-18T051443725538 -> 2026-10-19T052404955466 | 2 changed | quiet |
| 2026-10-19 | `remote/app.openkrill/seo-audit` | 2026-10-17T055438239170 -> 2026-10-19T052405076577 | 1 changed | quiet |
| 2026-10-19 | `remote/com.orbylon/readiness` | 2026-10-18T223936205306 -> 2026-10-19T052403854321 | 2 changed | quiet |
| 2026-10-19 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-18T051331459064 -> 2026-10-19T052403058602 | 1 changed | quiet |
| 2026-10-19 | `remote/rs.rides/airport-transfers` | 2026-10-17T224431994518 -> 2026-10-19T052401810373 | 1 changed | quiet |
| 2026-10-19 | `remote/com.restaurantdoctorai/profit-check` | 2026-10-17T060112370318 -> 2026-10-19T052400769399 | 7 changed | quiet |
| 2026-10-19 | `remote/how.mise/mise` | 2026-10-18T223932448842 -> 2026-10-19T052359680872 | 20 changed (every tool) | review |
| 2026-10-19 | `remote/com.jobmojito/jobmojito` | 2026-10-17T055424948712 -> 2026-10-19T052359660050 | 1 changed, 7 added | quiet |
| 2026-10-19 | `remote/com.gojinko.mcp/jinko` | 2026-10-18T051304896958 -> 2026-10-19T052356437915 | 1 changed | quiet |
| 2026-10-19 | `remote/io.github.vassiliylakhonin/agenda-intelligence-md.1` | 2026-10-18T051312384184 -> 2026-10-19T052355180695 | 1 changed, 1 added | quiet |
| 2026-10-19 | `remote/io.github.daniel3303/equibles` | 2026-10-18T223900360816 -> 2026-10-19T052355125309 | 3 changed, 1 added | quiet |
| 2026-10-19 | `remote/io.github.proplineapi/propline-mcp` | 2026-10-17T055954488618 -> 2026-10-19T052350944203 | 2 added | quiet |
| 2026-10-19 | `remote/app.openkrill/outreach-desk` | 2026-10-17T224413400763 -> 2026-10-19T052350771083 | 5 changed | quiet |
| 2026-10-19 | `remote/io.github.Clipform/mcp-server` | 2026-10-17T055339008854 -> 2026-10-19T052350370684 | 1 changed | quiet |
| 2026-10-19 | `remote/de.viafrei/mcp` | 2026-10-17T055248430656 -> 2026-10-19T052347061775 | 9 changed | quiet |
| 2026-10-19 | `remote/com.myinsurancecity/mcp` | 2026-10-18T223926471477 -> 2026-10-19T052346570991 | 9 changed (every tool) | quiet |
| 2026-10-19 | `remote/io.github.vassiliylakhonin/agenda-intelligence-md.2` | 2026-10-17T224401370277 -> 2026-10-19T052343686983 | 1 changed, 1 added | quiet |
| 2026-10-19 | `remote/io.github.vassiliylakhonin/agenda-intelligence-md.11` | 2026-10-17T224257602371 -> 2026-10-19T052344214669 | 1 changed, 1 added | quiet |
| 2026-10-19 | `remote/dev.mcphost/mcphost` | 2026-10-18T223921196139 -> 2026-10-19T052342636071 | 1 changed | quiet |
| 2026-10-19 | `remote/io.chainhelix/intel` | 2026-10-17T055849776236 -> 2026-10-19T052341918888 | 1 changed | quiet |
| 2026-10-19 | `remote/app.openkrill/company-jobs` | 2026-10-17T055233021258 -> 2026-10-19T052338757941 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 22684 substantive, 9687 that changed only numbers (a catalogue counter ticking, a date), 485 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 16224 | 7212 | 9012 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 149 | 149 | 0 | 0 |
| `sistaminuten.se` | 117 | 4 | 0 | 113 |
| `afbudsrejser.dk` | 116 | 4 | 0 | 112 |
| `akkilahdot.fi` | 116 | 4 | 0 | 112 |
| `restplass.no` | 116 | 4 | 0 | 112 |
| `socialloop.ai` | 113 | 113 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `remoshift.com` | 87 | 6 | 81 | 0 |
| `fundinglandscape.com` | 86 | 53 | 33 | 0 |
| 3998 other operators | 12641 | 12044 | 561 | 36 |
