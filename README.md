# MCP server tool changes

Last change observed 2026-10-09T15:36:42+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10128 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 21701 hosted endpoints (read daily, and every four hours while they keep changing).

25590 changes to a tool definition: 870 npm releases (624 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 24720 readings of hosted servers that found their tools changed; 372 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-09 | `remote/se.sistaminuten/travel-search` | 2026-10-09T064744759159 -> 2026-10-09T153643636368 | 1 changed | quiet |
| 2026-10-09 | `remote/coach.marian/mentoring-inquiry-builder` | 2026-10-08T135527776217 -> 2026-10-09T153647411777 | 3 changed | quiet |
| 2026-10-09 | `remote/no.apier/mcp` | 2026-10-08T155654060135 -> 2026-10-09T153641796306 | 25 changed (every tool) | quiet |
| 2026-10-09 | `remote/ru.quintadb/mcp` | 2026-10-08T135302111760 -> 2026-10-09T153630770758 | 7 changed, 6 added | quiet |
| 2026-10-09 | `remote/fr.projet-ariane/ariane-orientation` | 2026-10-08T213440733116 -> 2026-10-09T153626427136 | 1 changed | quiet |
| 2026-10-09 | `remote/ai.plith/plith` | 2026-10-08T213513082980 -> 2026-10-09T153637435455 | 1 changed | quiet |
| 2026-10-09 | `remote/tennis.courts/nyc-tennis-courts` | 2026-10-09T064815316698 -> 2026-10-09T153624772999 | 3 changed | quiet |
| 2026-10-09 | `remote/no.restplass/travel-search` | 2026-10-09T064818896164 -> 2026-10-09T153625133351 | 1 changed | quiet |
| 2026-10-09 | `remote/io.github.openaccountants/openaccountants` | 2026-10-08T135536472557 -> 2026-10-09T153624233130 | 14 changed (every tool) | quiet |
| 2026-10-09 | `remote/fi.akkilahdot/travel-search` | 2026-10-09T064814384034 -> 2026-10-09T153622675986 | 1 changed | quiet |
| 2026-10-09 | `remote/io.github.CodeWever/wever-labs-products` | 2026-10-09T064815403338 -> 2026-10-09T153624138061 | 2 added | quiet |
| 2026-10-09 | `remote/dk.afbudsrejser/travel-search` | 2026-10-09T064817083217 -> 2026-10-09T153621654449 | 1 changed | quiet |
| 2026-10-09 | `remote/com.warmthengine/observatory` | 2026-10-08T135443219417 -> 2026-10-09T153621617096 | 3 changed | quiet |
| 2026-10-09 | `remote/io.github.VoiceScapee/voicescape` | 2026-10-09T064814750744 -> 2026-10-09T153619278994 | 1 changed, 14 added | review |
| 2026-10-09 | `remote/ai.wem3/wem-price-compare` | 2026-10-07T001326051584 -> 2026-10-09T153620446261 | 8 changed | quiet |
| 2026-10-09 | `remote/com.trustbaselab/rcb-data` | 2026-10-09T064815028150 -> 2026-10-09T153620176241 | 25 added | quiet |
| 2026-10-09 | `remote/com.tickerinside/tickerinside-mcp` | 2026-10-08T155522755067 -> 2026-10-09T153617827865 | 4 changed | quiet |
| 2026-10-09 | `remote/ai.trydock/dock` | 2026-10-09T064813619331 -> 2026-10-09T153617778156 | 4 changed, 1 added | quiet |
| 2026-10-09 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-09T064810830711 -> 2026-10-09T153619137833 | 1 changed | quiet |
| 2026-10-09 | `remote/ch.swisslivingindex/swiss-living-index` | 2026-10-08T155520536103 -> 2026-10-09T153617646123 | 1 changed, 4 added | quiet |
| 2026-10-09 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-09T064808281080 -> 2026-10-09T153615804098 | 1 changed | quiet |
| 2026-10-09 | `remote/ai.shorti/shorti` | 2026-10-09T064809004787 -> 2026-10-09T153616338823 | 2 changed | quiet |
| 2026-10-09 | `remote/com.saaskr/korean-saas-directory` | 2026-10-08T135320460231 -> 2026-10-09T153614652305 | 1 changed | quiet |
| 2026-10-09 | `remote/ai.searchshop/apostleman` | 2026-10-08T135326786211 -> 2026-10-09T153613897002 | 4 removed | quiet |
| 2026-10-09 | `remote/ua.com.quintadb/mcp` | 2026-10-08T135304115006 -> 2026-10-09T153614306600 | 7 changed, 6 added | quiet |
| 2026-10-09 | `remote/com.qumge/skills` | 2026-10-08T135301988789 -> 2026-10-09T153611973861 | 1 changed | quiet |
| 2026-10-09 | `remote/io.github.yschimke/compose-preview` | 2026-10-08T213416906263 -> 2026-10-09T153612342755 | 4 changed | quiet |
| 2026-10-09 | `remote/io.github.Fizzl13/presign-guard` | 2026-10-08T135252202109 -> 2026-10-09T153611222851 | 7 changed (every tool) | quiet |
| 2026-10-09 | `remote/com.metricduck/financial-analysis` | 2026-10-08T135000164442 -> 2026-10-09T153610571246 | 2 changed | quiet |
| 2026-10-09 | `remote/com.knowjudges/knowjudges` | 2026-10-08T213442575126 -> 2026-10-09T153610680119 | 2 added | quiet |
| 2026-10-09 | `remote/ch.kulalabs.pazair/pazair` | 2026-10-09T064806629570 -> 2026-10-09T153611537853 | 2 changed, 7 added | quiet |
| 2026-10-09 | `remote/io.github.firecrawl/firecrawl-mcp-server` | 2026-10-08T213438723126 -> 2026-10-09T153608218809 | 2 changed | quiet |
| 2026-10-09 | `remote/io.github.Ahmet11159/x402-agent-services` | 2026-10-08T213439122010 -> 2026-10-09T153608378838 | 1 added | quiet |
| 2026-10-09 | `remote/com.musedin/musedin` | 2026-10-09T064802394988 -> 2026-10-09T153608992061 | 8 changed | quiet |
| 2026-10-09 | `remote/com.youspot/youspot` | 2026-10-09T064745979939 -> 2026-10-09T153607614488 | 1 changed, 3 added | quiet |
| 2026-10-09 | `remote/com.sourcey/sourcey` | 2026-10-08T135120326153 -> 2026-10-09T153607381190 | 2 changed | quiet |
| 2026-10-09 | `remote/io.github.HuangGoodmanAgency/edgar-and-edgarette` | 2026-10-08T135457031542 -> 2026-10-09T153606549720 | 1 added | quiet |
| 2026-10-09 | `remote/com.vendooly/vendooly` | 2026-10-07T001207362290 -> 2026-10-09T153607033082 | 2 added | quiet |
| 2026-10-09 | `remote/eu.paymentslaw/legislation` | 2026-10-08T064206277000 -> 2026-10-09T153605907896 | 3 changed | quiet |
| 2026-10-09 | `remote/io.github.mirabello-consultancy/mcp-server` | 2026-10-08T155447954879 -> 2026-10-09T153606025019 | 1 added | quiet |
| 2026-10-09 | `remote/io.github.medprice-ai/mcp-medprice-ai` | 2026-10-08T135029869432 -> 2026-10-09T153604596190 | 4 changed | quiet |
| 2026-10-09 | `remote/io.github.LambdaTest/mcp` | 2026-10-08T135021687330 -> 2026-10-09T153603659719 | 16 changed, 10 removed | quiet |
| 2026-10-09 | `remote/es.propertylist/propertylist` | 2026-10-08T135100128736 -> 2026-10-09T153604461856 | 2 added | quiet |
| 2026-10-09 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-09T064741467617 -> 2026-10-09T153602930758 | 1 changed, 5 added | quiet |
| 2026-10-09 | `remote/com.lightbringer/connector` | 2026-10-08T135027739369 -> 2026-10-09T153602556876 | 1 changed, 3 added | quiet |
| 2026-10-09 | `remote/com.courtdelta/court-delta` | 2026-10-08T213401818983 -> 2026-10-09T153601811930 | 3 changed | quiet |
| 2026-10-09 | `remote/io.github.hail-hq/hail-mcp` | 2026-10-08T213357656314 -> 2026-10-09T153601960478 | 1 changed | quiet |
| 2026-10-09 | `remote/com.sfxmint/sounds` | 2026-10-09T064740136616 -> 2026-10-09T153602098888 | 4 changed | review |
| 2026-10-09 | `remote/com.microsoft/microsoft-learn-mcp` | 2026-10-08T134808661625 -> 2026-10-09T153558807387 | 2 changed | quiet |
| 2026-10-09 | `remote/io.github.tang-vu/keryx` | 2026-10-09T064755905726 -> 2026-10-09T153559842841 | 3 added | quiet |
| 2026-10-09 | `remote/com.quintadb/mcp` | 2026-10-08T135236409962 -> 2026-10-09T153559462932 | 7 changed, 6 added | quiet |
| 2026-10-09 | `remote/io.github.HelloSafe/travel-insurance` | 2026-10-08T134807936013 -> 2026-10-09T153557967289 | 1 changed | quiet |
| 2026-10-09 | `remote/io.github.filipbolcek-ctrl/forest-factory` | 2026-10-07T154846160001 -> 2026-10-09T153604695090 | 6 changed (every tool) | quiet |
| 2026-10-09 | `remote/io.github.Perufitlife/postwire-mcp` | 2026-10-09T064735869409 -> 2026-10-09T153556030497 | 5 changed | quiet |
| 2026-10-09 | `remote/com.grabgpu/gpu-finder` | 2026-10-08T134755322436 -> 2026-10-09T153556306209 | 1 changed | quiet |
| 2026-10-09 | `remote/trade.loomdesk/loomdesk` | 2026-10-09T064753537146 -> 2026-10-09T153555325544 | 2 changed | quiet |
| 2026-10-09 | `remote/fun.lesgooo/lesgooo` | 2026-10-08T134843337611 -> 2026-10-09T153554455949 | 1 changed | quiet |
| 2026-10-09 | `remote/co.getclippy/clippy` | 2026-10-08T213351031140 -> 2026-10-09T153555307070 | 4 changed (every tool) | quiet |
| 2026-10-09 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-09T064725069814 -> 2026-10-09T153552833014 | 1 changed | quiet |
| 2026-10-09 | `remote/io.github.bosmdavid-gif/dropthehassle` | 2026-10-08T134632631427 -> 2026-10-09T153552844442 | 1 changed, 2 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 17239 substantive, 7986 that changed only numbers (a catalogue counter ticking, a date), 365 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 13231 | 5706 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 538 | 538 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `sistaminuten.se` | 88 | 2 | 0 | 86 |
| `afbudsrejser.dk` | 87 | 2 | 0 | 85 |
| `akkilahdot.fi` | 87 | 2 | 0 | 85 |
| `restplass.no` | 87 | 2 | 0 | 85 |
| `socialloop.ai` | 85 | 85 | 0 | 0 |
| `caseyjhand.com` | 77 | 77 | 0 | 0 |
| `dayze.com` | 69 | 69 | 0 | 0 |
| `fundinglandscape.com` | 62 | 36 | 26 | 0 |
| 3052 other operators | 8741 | 8282 | 435 | 24 |
