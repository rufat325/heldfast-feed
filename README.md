# MCP server tool changes

Last change observed 2026-10-20T10:47:02+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

37281 changes to a tool definition: 1521 npm releases (1275 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 35760 readings of hosted servers that found their tools changed; 2247 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-20 | `remote/com.zoningverdict/mcp` | 2026-09-23T163001675431 -> 2026-10-20T104703515032 | 1 added | quiet |
| 2026-10-20 | `remote/io.github.Z4KARY/upgrowth-mcp` | 2026-10-17T060001778287 -> 2026-10-20T104658347324 | 2 added | quiet |
| 2026-10-20 | `remote/io.github.switchwize/switchwize-mcp` | 2026-10-17T055954182755 -> 2026-10-20T104647313007 | 2 changed | quiet |
| 2026-10-20 | `remote/com.riddle/creator` | 2026-10-17T055953060245 -> 2026-10-20T104645792704 | 7 changed | quiet |
| 2026-10-20 | `remote/studio.gradients/mcp` | 2026-10-20T052519685469 -> 2026-10-20T104626963222 | 1 changed | quiet |
| 2026-10-20 | `remote/fi.akkilahdot/travel-search` | 2026-10-20T052511183752 -> 2026-10-20T104604115095 | 1 changed | quiet |
| 2026-10-20 | `remote/io.soundchain/agents` | 2026-10-20T052506306270 -> 2026-10-20T104548067629 | 2 added | quiet |
| 2026-10-20 | `remote/cloud.verifi/human-verification` | 2026-10-01T134548562237 -> 2026-10-20T104535051291 | 1 changed | quiet |
| 2026-10-20 | `remote/us.srv.vehcdj664efetfrsolne5umanq/quoteproof-mcp` | 2026-10-19T052457797879 -> 2026-10-20T104532790733 | 7 changed | quiet |
| 2026-10-20 | `remote/io.github.trip2g/trip2g` | 2026-10-08T135428115498 -> 2026-10-20T104518234037 | 2 changed, 1 added | quiet |
| 2026-10-20 | `remote/io.github.devlollc/torneo` | 2026-10-17T055846065016 -> 2026-10-20T104512897437 | 2 changed, 1 added | quiet |
| 2026-10-20 | `remote/com.thecastlemap/castles` | 2026-09-28T073134496939 -> 2026-10-20T104457314613 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-19T155725318112 -> 2026-10-20T104455523604 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.dtajitdinov-aris/sphere-marketplace` | 2026-10-19T155718399572 -> 2026-10-20T104433598317 | 3 changed, 2 added, 1 removed | quiet |
| 2026-10-20 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-20T052437574278 -> 2026-10-20T104422593517 | 1 changed | quiet |
| 2026-10-20 | `remote/com.naxytra/xytara-mcp-executor` | 2026-10-19T052421583850 -> 2026-10-20T104419126307 | 2 changed | review |
| 2026-10-20 | `remote/io.github.eamwhite1/xrpl-referee` | 2026-10-10T062531268548 -> 2026-10-20T104402416108 | 2 changed, 2 added | quiet |
| 2026-10-20 | `remote/com.n9t2/xrpl-agent-gateway` | 2026-10-17T055629679939 -> 2026-10-20T104401177785 | 1 changed | quiet |
| 2026-10-20 | `remote/nl.prijsprofeet/prijsprofeet` | 2026-10-19T135242363839 -> 2026-10-20T104358559893 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.HillTan/tiktikluck` | 2026-10-19T135518845908 -> 2026-10-20T104353857597 | 1 changed | quiet |
| 2026-10-20 | `remote/io.taifoon/coordination-layer.1` | 2026-10-20T052333755770 -> 2026-10-20T104352268056 | 1 changed | review |
| 2026-10-20 | `remote/com.lazyweb/discovery` | 2026-10-17T060353470644 -> 2026-10-20T104353228241 | 1 changed | quiet |
| 2026-10-20 | `remote/com.searchfragments/search-fragments` | 2026-10-17T055744195573 -> 2026-10-20T104350668244 | 2 changed | quiet |
| 2026-10-20 | `remote/se.sistaminuten/travel-search` | 2026-10-20T052332512571 -> 2026-10-20T104349850541 | 1 changed | quiet |
| 2026-10-20 | `remote/nl.prijsprofeet/prijsprofeet.1` | 2026-10-19T135510909600 -> 2026-10-20T104347094514 | 1 changed | quiet |
| 2026-10-20 | `remote/ai.go-rocket/go-rocket` | 2026-10-03T121345079899 -> 2026-10-20T104346981376 | 1 changed | review |
| 2026-10-20 | `remote/world.byway/mcp` | 2026-09-23T160837187423 -> 2026-10-20T104336771753 | 5 changed | quiet |
| 2026-10-20 | `remote/io.github.JakubTrousil/agentsjunction` | 2026-10-04T195028694714 -> 2026-10-20T104332362603 | 3 changed | quiet |
| 2026-10-20 | `remote/io.github.Tomalarrrr/cyclesite-mcp-server` | 2026-10-06T110145719917 -> 2026-10-20T104328809951 | 1 changed | review |
| 2026-10-20 | `remote/com.remoshift/jobs` | 2026-10-20T052418988706 -> 2026-10-20T104327265907 | 1 changed | quiet |
| 2026-10-20 | `remote/com.recipebooq/recipebooq` | 2026-10-17T055722139807 -> 2026-10-20T104322473178 | 1 changed | quiet |
| 2026-10-20 | `remote/ai.weio/site-check` | 2026-10-20T052314371726 -> 2026-10-20T104322945147 | 3 added, 2 removed | quiet |
| 2026-10-20 | `remote/com.aiseparations/color-separations` | 2026-10-17T055553904028 -> 2026-10-20T104320648947 | 5 changed (every tool) | quiet |
| 2026-10-20 | `remote/io.github.cryptoplayer/crypto-casinos` | 2026-09-23T160828460743 -> 2026-10-20T104319068803 | 12 changed (every tool) | quiet |
| 2026-10-20 | `remote/in.zelta/waist-check` | 2026-10-06T110214981244 -> 2026-10-20T104315856587 | 2 changed (every tool) | quiet |
| 2026-10-20 | `remote/io.github.TRDEFI/liquidity` | 2026-10-17T060511214312 -> 2026-10-20T104313567482 | 2 changed | quiet |
| 2026-10-20 | `remote/com.vibe-fixer/vibefix` | 2026-10-19T212005615808 -> 2026-10-20T104312203153 | 2 changed | quiet |
| 2026-10-20 | `remote/io.github.ihen404/x402-scraper-api` | 2026-10-07T001334925807 -> 2026-10-20T104309761334 | 2 added, 3 removed | review |
| 2026-10-20 | `remote/io.github.FTHTrading/genesis402-mcp` | 2026-10-19T135145138277 -> 2026-10-20T104302881789 | 1 changed | quiet |
| 2026-10-20 | `remote/com.starcovery/mcp` | 2026-10-19T135859547205 -> 2026-10-20T104302629157 | 3 changed | quiet |
| 2026-10-20 | `remote/io.github.voicehook-ai/voicehook` | 2026-10-19T212018770763 -> 2026-10-20T104300714834 | 2 changed, 1 added | quiet |
| 2026-10-20 | `remote/no.restplass/travel-search` | 2026-10-20T052357561715 -> 2026-10-20T104259582074 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.marcoret74/semantic-geometry` | 2026-10-19T135407843614 -> 2026-10-20T104257778611 | 12 changed (every tool) | quiet |
| 2026-10-20 | `remote/io.github.scraping-api-plans/web-data-plan-finder` | 2026-10-18T113047207537 -> 2026-10-20T104256346246 | 2 changed | quiet |
| 2026-10-20 | `remote/com.vaanzari/commerce` | 2026-10-03T192904103548 -> 2026-10-20T104250848940 | 5 changed | quiet |
| 2026-10-20 | `remote/com.ivisa.www/mcp` | 2026-09-23T163135816611 -> 2026-10-20T104250709459 | 1 changed | quiet |
| 2026-10-20 | `remote/online.pageaudit/pageaudit` | 2026-10-17T155934422328 -> 2026-10-20T104240413613 | 3 added | quiet |
| 2026-10-20 | `remote/ai.surfingdog/search` | 2026-10-19T135117475484 -> 2026-10-20T104234286063 | 2 changed | quiet |
| 2026-10-20 | `remote/dk.afbudsrejser/travel-search` | 2026-10-20T052352263826 -> 2026-10-20T104233386326 | 1 changed | quiet |
| 2026-10-20 | `remote/com.opointo/opointo` | 2026-10-17T055637171631 -> 2026-10-20T104234040047 | 1 changed | quiet |
| 2026-10-20 | `remote/com.suomiatlas/area-statistics` | 2026-10-08T135334735832 -> 2026-10-20T104232644882 | 1 changed | quiet |
| 2026-10-20 | `remote/net.totallytarot/calculators` | 2026-10-02T072153895302 -> 2026-10-20T104230433864 | 2 changed, 4 added | quiet |
| 2026-10-20 | `remote/com.topologyindex/topology-index` | 2026-10-02T210140340559 -> 2026-10-20T104230114181 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.jukky-source/wealth-agent` | 2026-10-20T052348909541 -> 2026-10-20T104224149021 | 3 changed, 7 added | review |
| 2026-10-20 | `remote/com.obriym-crm/mcp` | 2026-10-18T190045023069 -> 2026-10-20T104225279679 | 2 changed | quiet |
| 2026-10-20 | `remote/com.theneuralnet/model-register` | 2026-10-19T135328343551 -> 2026-10-20T104218887052 | 1 changed | quiet |
| 2026-10-20 | `remote/com.thefomite/fomite` | 2026-10-20T052317021047 -> 2026-10-20T104219084998 | 1 changed | quiet |
| 2026-10-20 | `remote/com.veritaset/mcp` | 2026-10-20T052347042145 -> 2026-10-20T104217267586 | 2 changed | quiet |
| 2026-10-20 | `remote/io.github.cyanheads/usgs-water-mcp-server` | 2026-10-04T124245095092 -> 2026-10-20T104214150930 | 4 changed, 1 added | quiet |
| 2026-10-20 | `remote/io.github.cyanheads/unhcr-refugees-mcp-server` | 2026-10-06T110235507819 -> 2026-10-20T104209993802 | 7 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 24075 substantive, 12697 that changed only numbers (a catalogue counter ticking, a date), 509 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 19153 | 7228 | 11925 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 170 | 170 | 0 | 0 |
| `sistaminuten.se` | 122 | 4 | 0 | 118 |
| `afbudsrejser.dk` | 121 | 4 | 0 | 117 |
| `akkilahdot.fi` | 121 | 4 | 0 | 117 |
| `restplass.no` | 121 | 4 | 0 | 117 |
| `socialloop.ai` | 118 | 118 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `remoshift.com` | 92 | 6 | 86 | 0 |
| `fundinglandscape.com` | 91 | 58 | 33 | 0 |
| 4606 other operators | 14081 | 13388 | 653 | 40 |
