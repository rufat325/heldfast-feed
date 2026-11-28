# MCP server tool changes

Last change observed 2026-11-28T17:15:33+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 18238 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 43073 hosted endpoints (read daily, and every four hours while they keep changing).

148770 changes to a tool definition: 5722 npm releases (5476 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 143048 readings of hosted servers that found their tools changed; 5306 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-28 | `remote/studio.gradients/mcp` | 2026-11-28T160623833217 -> 2026-11-28T171534925619 | 1 changed | quiet |
| 2026-11-28 | `remote/fi.akkilahdot/travel-search` | 2026-11-28T160550197227 -> 2026-11-28T171532760173 | 1 changed | quiet |
| 2026-11-28 | `remote/se.sistaminuten/travel-search` | 2026-11-28T160323350852 -> 2026-11-28T171528059430 | 1 changed | quiet |
| 2026-11-28 | `remote/no.restplass/travel-search` | 2026-11-28T160612765491 -> 2026-11-28T171527305951 | 1 changed | quiet |
| 2026-11-28 | `remote/com.andque/agent-data` | 2026-11-26T172810871334 -> 2026-11-28T171525175409 | 1 changed | quiet |
| 2026-11-28 | `remote/dk.afbudsrejser/travel-search` | 2026-11-28T160513966557 -> 2026-11-28T171523561530 | 1 changed | quiet |
| 2026-11-28 | `remote/com.stickerbyvin/window-sticker` | 2026-11-26T135232788485 -> 2026-11-28T171523958471 | 1 changed | quiet |
| 2026-11-28 | `remote/net.stabledomains/registrar` | 2026-11-28T145904511608 -> 2026-11-28T171522806936 | 1 changed, 9 added | review |
| 2026-11-28 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-28T160258057100 -> 2026-11-28T171521791283 | 1 changed | quiet |
| 2026-11-28 | `remote/com.vynqlo/vynqlo-mcp` | 2026-11-28T145849787705 -> 2026-11-28T171522992094 | 1 changed | quiet |
| 2026-11-28 | `remote/no.verako/verako` | 2026-11-28T160139600167 -> 2026-11-28T171521625160 | 1 changed | quiet |
| 2026-11-28 | `remote/com.trackerhacker/mcp` | 2026-11-28T083136899220 -> 2026-11-28T171519988234 | 1 changed | quiet |
| 2026-11-28 | `remote/work.agentexchange/us-macro-regime` | 2026-11-28T160301726904 -> 2026-11-28T171517342439 | 1 changed | review |
| 2026-11-28 | `remote/com.swishrjobs/swishrjobs` | 2026-11-28T145716376037 -> 2026-11-28T171516926455 | 2 changed, 3 added | review |
| 2026-11-28 | `remote/gg.pixly/mcp` | 2026-11-27T144907881756 -> 2026-11-28T171517157915 | 1 changed | quiet |
| 2026-11-28 | `remote/com.radarbg/radar-tools` | 2026-11-28T145655108039 -> 2026-11-28T171511880081 | 5 changed | quiet |
| 2026-11-28 | `remote/io.github.codytodd-ui/pitchspark` | 2026-11-28T145612702269 -> 2026-11-28T171508454315 | 1 changed | quiet |
| 2026-11-28 | `remote/com.professorotter/activities` | 2026-11-28T083230311078 -> 2026-11-28T171508558241 | 5 changed | quiet |
| 2026-11-28 | `remote/ch.kulalabs.pazair/pazair` | 2026-11-27T214213046577 -> 2026-11-28T171509602716 | 4 changed | quiet |
| 2026-11-28 | `remote/io.github.llm-9-to-5/nightshift-agent-tools` | 2026-11-28T155938431604 -> 2026-11-28T171507352219 | 1 added | quiet |
| 2026-11-28 | `remote/biz.valuein/mcp` | 2026-11-28T083123015126 -> 2026-11-28T171502456374 | 1 changed | quiet |
| 2026-11-28 | `remote/ca.fonciq/fonciq` | 2026-11-28T083114581569 -> 2026-11-28T171452814591 | 2 changed | quiet |
| 2026-11-28 | `remote/dk.cvrradar/cvrradar` | 2026-11-28T155525591826 -> 2026-11-28T171451960376 | 1 changed | quiet |
| 2026-11-28 | `remote/com.foundationscounselingllc/practice` | 2026-11-28T083128902108 -> 2026-11-28T171447041485 | 2 changed | quiet |
| 2026-11-28 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-28T160309020818 -> 2026-11-28T171443097094 | 2 added | quiet |
| 2026-11-28 | `remote/com.getmarsell/marsell` | 2026-11-28T144723723930 -> 2026-11-28T171439684476 | 2 changed, 5 added | quiet |
| 2026-11-28 | `remote/network.skv/skv` | 2026-11-28T145951716180 -> 2026-11-28T171438904087 | 1 changed | quiet |
| 2026-11-28 | `remote/fr.ip73/ip73` | 2026-11-28T144832435355 -> 2026-11-28T171437378232 | 2 changed | quiet |
| 2026-11-28 | `remote/com.imagiolabs.www/imagio-relay` | 2026-11-28T160019464494 -> 2026-11-28T171435057860 | 2 changed | quiet |
| 2026-11-28 | `remote/com.danerolne/dane-rolne` | 2026-11-28T083059926306 -> 2026-11-28T171436042331 | 5 added, 5 removed | quiet |
| 2026-11-28 | `remote/app.vercel.fork-for-agents/fork` | 2026-11-28T155049872771 -> 2026-11-28T171434499077 | 2 changed | quiet |
| 2026-11-28 | `remote/ai.duami/intent-exchange` | 2026-11-28T144433174592 -> 2026-11-28T171432949105 | 1 changed, 1 added | quiet |
| 2026-11-28 | `remote/io.github.thiagopatzdorf/fichario` | 2026-11-28T154829607254 -> 2026-11-28T171427497087 | 7 changed, 2 added | quiet |
| 2026-11-28 | `remote/io.forthclear/liquidation` | 2026-11-28T154642086986 -> 2026-11-28T171426021955 | 1 changed | quiet |
| 2026-11-28 | `remote/at.sporthotelideal/booking` | 2026-11-28T144229742555 -> 2026-11-28T171427316207 | 1 changed, 1 added | quiet |
| 2026-11-28 | `remote/xyz.trusteed/mcp-gateway` | 2026-11-28T144023803795 -> 2026-11-28T171423405300 | 1 changed, 1 added | quiet |
| 2026-11-28 | `remote/io.github.gamealia/gamealia-mcp` | 2026-11-28T083127048389 -> 2026-11-28T171420672560 | 1 changed | quiet |
| 2026-11-28 | `remote/ai.dotsy/mcp` | 2026-11-28T145159615678 -> 2026-11-28T171420349857 | 45 changed | quiet |
| 2026-11-28 | `remote/com.cumplida/biblioteca` | 2026-11-28T145150799408 -> 2026-11-28T171419273852 | 1 changed | quiet |
| 2026-11-28 | `remote/com.lokand/lokand` | 2026-11-27T142903475075 -> 2026-11-28T171422407967 | 2 changed | quiet |
| 2026-11-28 | `remote/ai.llpro/campus` | 2026-11-28T155225349519 -> 2026-11-28T171416717640 | 3 changed | quiet |
| 2026-11-28 | `remote/com.engagemii/citation-watch` | 2026-11-28T083043458189 -> 2026-11-28T171416146098 | 1 changed | quiet |
| 2026-11-28 | `remote/com.invoicefatura/fatura-go` | 2026-11-28T143821620025 -> 2026-11-28T171414638266 | 1 changed | quiet |
| 2026-11-28 | `remote/org.defade/defade` | 2026-11-27T142829729570 -> 2026-11-28T171412995433 | 1 changed, 2 added | quiet |
| 2026-11-28 | `remote/com.dataxapi/mcp` | 2026-11-28T143754113541 -> 2026-11-28T171412612011 | 2 changed | quiet |
| 2026-11-28 | `remote/com.affix-io/agent-commons` | 2026-11-28T154327573993 -> 2026-11-28T171413443069 | 2 changed, 3 added | quiet |
| 2026-11-28 | `remote/com.spellbook-finance/mcp` | 2026-11-26T170958880731 -> 2026-11-28T171413174530 | 2 changed | quiet |
| 2026-11-28 | `remote/io.github.MikeyPetrillo/agent402` | 2026-11-26T215846072307 -> 2026-11-28T171411151443 | 1 changed | quiet |
| 2026-11-28 | `remote/org.polyform/polyform` | 2026-11-28T154512298457 -> 2026-11-28T171409795253 | 6 added | quiet |
| 2026-11-28 | `remote/io.agentsla/agentsla` | 2026-11-28T154253407018 -> 2026-11-28T171410468931 | 1 changed | quiet |
| 2026-11-28 | `remote/app.chopit/chopit` | 2026-11-28T144327673036 -> 2026-11-28T171405793456 | 7 changed, 1 added | quiet |
| 2026-11-28 | `remote/io.github.0xinsider/mcp` | 2026-11-28T154328205701 -> 2026-11-28T171404301000 | 3 changed | quiet |
| 2026-11-28 | `remote/jp.cloneai.ai/agent-hub` | 2026-11-27T214111102176 -> 2026-11-28T171404642073 | 2 changed | quiet |
| 2026-11-28 | `remote/io.sslip.2-29-135-242/radar-agent-tools` | 2026-11-28T143510857734 -> 2026-11-28T171400666577 | 5 changed | quiet |
| 2026-11-28 | `remote/com.hashn/hashn` | 2026-11-28T083043126014 -> 2026-11-28T171353488977 | 1 added | quiet |
| 2026-11-28 | `remote/xyz.octio/octio` | 2026-11-27T091026087596 -> 2026-11-28T160642744662 | 1 changed | quiet |
| 2026-11-28 | `remote/studio.gradients/mcp` | 2026-11-28T150219884074 -> 2026-11-28T160623833217 | 1 changed | quiet |
| 2026-11-28 | `remote/no.restplass/travel-search` | 2026-11-28T150211272426 -> 2026-11-28T160612765491 | 1 changed | quiet |
| 2026-11-28 | `remote/fi.akkilahdot/travel-search` | 2026-11-28T150135040201 -> 2026-11-28T160550197227 | 1 changed | quiet |
| 2026-11-28 | `remote/com.visdenda/public` | 2026-11-28T150056092361 -> 2026-11-28T160516688924 | 1 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 100241 substantive, 47255 that changed only numbers (a catalogue counter ticking, a date), 1274 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 82353 | 38412 | 43941 | 0 |
| `a2awire.com` | 4371 | 4371 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 571 | 571 | 0 | 0 |
| `modevc.com` | 568 | 568 | 0 | 0 |
| `civai.co` | 403 | 403 | 0 | 0 |
| `revmesh2074.workers.dev` | 381 | 321 | 60 | 0 |
| `sistaminuten.se` | 296 | 7 | 0 | 289 |
| `afbudsrejser.dk` | 295 | 7 | 0 | 288 |
| `akkilahdot.fi` | 295 | 7 | 0 | 288 |
| `restplass.no` | 295 | 7 | 0 | 288 |
| `socialloop.ai` | 285 | 285 | 0 | 0 |
| 11973 other operators | 56316 | 52941 | 3254 | 121 |
