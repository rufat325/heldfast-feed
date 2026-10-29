# MCP server tool changes

Last change observed 2026-10-29T13:39:55+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

61528 changes to a tool definition: 2574 npm releases (2328 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 58954 readings of hosted servers that found their tools changed; 2965 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-29 | `remote/uk.zarvo/padel` | 2026-10-26T211535846943 -> 2026-10-29T133956021075 | 9 changed (every tool) | quiet |
| 2026-10-29 | `remote/io.taifoon/coordination-layer.1` | 2026-10-29T063229943581 -> 2026-10-29T133935285686 | 1 removed | quiet |
| 2026-10-29 | `remote/se.sistaminuten/travel-search` | 2026-10-29T104522254419 -> 2026-10-29T133930982183 | 1 changed | quiet |
| 2026-10-29 | `remote/it.expatliving/data` | 2026-10-28T062225427844 -> 2026-10-29T133853917413 | 9 changed | quiet |
| 2026-10-29 | `remote/studio.gradients/mcp` | 2026-10-29T104536181313 -> 2026-10-29T133839633834 | 1 changed | quiet |
| 2026-10-29 | `remote/pro.germanexam/germanexam` | 2026-10-29T063230101637 -> 2026-10-29T133838803880 | 3 changed | quiet |
| 2026-10-29 | `remote/io.github.SoapyRED/freightutils` | 2026-10-29T063229970222 -> 2026-10-29T133853771947 | 25 changed (every tool) | quiet |
| 2026-10-29 | `remote/fi.akkilahdot/travel-search` | 2026-10-29T104505848745 -> 2026-10-29T133807374031 | 1 changed | quiet |
| 2026-10-29 | `remote/com.testerexchange/tester-exchange` | 2026-10-27T112253788019 -> 2026-10-29T133807084215 | 2 changed | quiet |
| 2026-10-29 | `remote/io.github.voicehook-ai/voicehook` | 2026-10-28T133358078212 -> 2026-10-29T133805084341 | 2 changed | quiet |
| 2026-10-29 | `remote/com.webupcheck/webupcheck` | 2026-10-26T133449175858 -> 2026-10-29T133748635842 | 3 changed | quiet |
| 2026-10-29 | `remote/io.github.domusdeiug/muyiribi` | 2026-10-17T055521958931 -> 2026-10-29T133740851201 | 1 added | quiet |
| 2026-10-29 | `remote/xyz.costrinity/vitna-compliance-preflight` | 2026-10-06T110330646779 -> 2026-10-29T133737119404 | 1 changed | quiet |
| 2026-10-29 | `remote/io.github.Schoasch/backtesting-arena` | 2026-10-29T104414682504 -> 2026-10-29T133706326398 | 41 changed | quiet |
| 2026-10-29 | `remote/dev.tanod/tanod` | 2026-10-29T104330932113 -> 2026-10-29T133655686407 | 2 changed, 1 added | quiet |
| 2026-10-29 | `remote/dev.tanod/agents` | 2026-10-29T063217709581 -> 2026-10-29T133654671641 | 1 changed | quiet |
| 2026-10-29 | `remote/io.github.Tonys-Coding/sysketch` | 2026-10-19T135317111064 -> 2026-10-29T133649963925 | 1 changed | quiet |
| 2026-10-29 | `remote/com.textforagents/lockout-tagout-for-agent-infrastructure` | 2026-10-26T133356857326 -> 2026-10-29T133643042410 | 1 changed | quiet |
| 2026-10-29 | `remote/com.simafri/professional-email` | 2026-10-25T102344745855 -> 2026-10-29T133643516965 | 1 changed | quiet |
| 2026-10-29 | `remote/io.github.LKennedyShare/supplier-payment-verifier` | 2026-10-29T063221122101 -> 2026-10-29T133624706199 | 1 changed, 1 removed | quiet |
| 2026-10-29 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-29T104316978881 -> 2026-10-29T133559849876 | 1 changed | quiet |
| 2026-10-29 | `remote/io.slopit/slopit` | 2026-10-26T133319929734 -> 2026-10-29T133554138579 | 2 changed | quiet |
| 2026-10-29 | `remote/cn.tandiu/data` | 2026-10-29T104512472991 -> 2026-10-29T133532985483 | 2 changed | quiet |
| 2026-10-29 | `remote/ai.oriiion/oriiion` | 2026-10-26T133723922481 -> 2026-10-29T133518984227 | 3 added | quiet |
| 2026-10-29 | `remote/pl.przetargowyjanusz/tenders` | 2026-10-29T104213988933 -> 2026-10-29T133507521688 | 9 changed, 1 added | quiet |
| 2026-10-29 | `remote/com.proxmint/mcp` | 2026-10-17T055407571972 -> 2026-10-29T133506755809 | 1 changed | quiet |
| 2026-10-29 | `remote/es.proceres/proceres` | 2026-10-29T063211159429 -> 2026-10-29T133500676602 | 9 changed | quiet |
| 2026-10-29 | `remote/com.calmido/phone-number-lookup` | 2026-10-23T120631771973 -> 2026-10-29T133456012167 | 1 changed, 2 added | quiet |
| 2026-10-29 | `remote/com.remoshift/jobs` | 2026-10-29T104233133698 -> 2026-10-29T133454351696 | 1 changed | quiet |
| 2026-10-29 | `remote/app.openkrill/page-fetch` | 2026-10-22T105601882930 -> 2026-10-29T133422226331 | 2 changed | quiet |
| 2026-10-29 | `remote/ca.nikolajewdesign/portfolio-mcp` | 2026-10-24T112733055345 -> 2026-10-29T133419608174 | 6 changed | quiet |
| 2026-10-29 | `remote/dev.workers.restockalarm.token-safety-mcp/token-safety` | 2026-10-29T104326972576 -> 2026-10-29T133352614397 | 5 changed (every tool) | quiet |
| 2026-10-29 | `remote/com.odilelabs/odile` | 2026-10-29T104130533842 -> 2026-10-29T133337945486 | 9 removed | quiet |
| 2026-10-29 | `remote/com.thaiprojerseys/motor-soberano` | 2026-10-27T111920318244 -> 2026-10-29T133336049699 | 3 changed | review |
| 2026-10-29 | `remote/dev.tanod/images` | 2026-10-29T104309989373 -> 2026-10-29T133334716847 | 1 added | quiet |
| 2026-10-29 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-29T104239401428 -> 2026-10-29T133308566793 | 8 changed | review |
| 2026-10-29 | `remote/com.skateboardpersonalizado/skateboard-deck` | 2026-10-06T110102275123 -> 2026-10-29T133258713146 | 1 changed | quiet |
| 2026-10-29 | `remote/com.lordevo/shop` | 2026-10-29T104222052149 -> 2026-10-29T133253598446 | 35 changed, 11 added (every tool) | review |
| 2026-10-29 | `remote/no.restplass/travel-search` | 2026-10-29T104612890901 -> 2026-10-29T133228234228 | 1 changed | quiet |
| 2026-10-29 | `remote/dev.pressmark/pressmark` | 2026-10-28T212532047490 -> 2026-10-29T133225313516 | 1 changed | quiet |
| 2026-10-29 | `remote/com.meridiandispatch/travel-guides` | 2026-10-29T063246063702 -> 2026-10-29T133220159396 | 1 changed | quiet |
| 2026-10-29 | `remote/ai.haggl/haggl` | 2026-10-20T232816535929 -> 2026-10-29T133212881494 | 6 added | quiet |
| 2026-10-29 | `remote/dk.afbudsrejser/travel-search` | 2026-10-29T104537170063 -> 2026-10-29T133152673237 | 1 changed | quiet |
| 2026-10-29 | `remote/com.proofprice/pricepaid` | 2026-10-24T112559710404 -> 2026-10-29T133150455848 | 11 changed, 3 added | quiet |
| 2026-10-29 | `remote/io.github.mooshee/pressmark` | 2026-10-28T212345176813 -> 2026-10-29T133146022031 | 1 changed | quiet |
| 2026-10-29 | `remote/es.propertylist/propertylist` | 2026-10-29T103955347807 -> 2026-10-29T133127918758 | 2 changed | quiet |
| 2026-10-29 | `remote/com.ortexo/mcp` | 2026-10-28T212335263421 -> 2026-10-29T133115481244 | 1 changed | quiet |
| 2026-10-29 | `remote/io.theagentforge/forge` | 2026-10-29T104435337209 -> 2026-10-29T133044727038 | 1 changed | quiet |
| 2026-10-29 | `remote/com.hireahelper/mcp` | 2026-10-25T115300450980 -> 2026-10-29T133008089382 | 16 added | quiet |
| 2026-10-29 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-29T104401066330 -> 2026-10-29T133005078088 | 3 changed | quiet |
| 2026-10-29 | `remote/io.github.industrial-platform-ai/link-extractor` | 2026-10-25T115333313367 -> 2026-10-29T133000051361 | 1 changed | quiet |
| 2026-10-29 | `remote/app.getfleek/partners` | 2026-10-19T134859348395 -> 2026-10-29T132955241057 | 2 changed | quiet |
| 2026-10-29 | `remote/com.freightfa.mcp/freightfa` | 2026-10-27T123605602859 -> 2026-10-29T132952275445 | 2 changed | quiet |
| 2026-10-29 | `remote/re.rundata/temps-reel` | 2026-10-29T104322208600 -> 2026-10-29T132927250903 | 1 changed | quiet |
| 2026-10-29 | `remote/io.github.matchawards/matchawards-mcp` | 2026-10-29T103739099997 -> 2026-10-29T132925995715 | 1 added | quiet |
| 2026-10-29 | `remote/io.github.privatebydefault/default-privacy` | 2026-10-23T200800839290 -> 2026-10-29T132924779648 | 3 changed | quiet |
| 2026-10-29 | `remote/io.github.minsooparkk/korea-tax-law-mcp` | 2026-10-27T145815234061 -> 2026-10-29T132924302804 | 20 changed (every tool) | quiet |
| 2026-10-29 | `remote/io.github.dstrausser83/db-collab-hub` | 2026-10-29T103815969847 -> 2026-10-29T132924435562 | 25 changed, 1 added (every tool) | quiet |
| 2026-10-29 | `remote/io.github.Clipform/mcp-server` | 2026-10-28T062117270252 -> 2026-10-29T132916232429 | 1 changed | quiet |
| 2026-10-29 | `remote/io.github.qxxx5vyd77-byte/directors-lookbook` | 2026-10-29T063152655215 -> 2026-10-29T132901477707 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 41267 substantive, 19548 that changed only numbers (a catalogue counter ticking, a date), 713 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 34063 | 15829 | 18234 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1126 | 1126 | 0 | 0 |
| `caseyjhand.com` | 269 | 269 | 0 | 0 |
| `sistaminuten.se` | 169 | 6 | 0 | 163 |
| `afbudsrejser.dk` | 168 | 6 | 0 | 162 |
| `akkilahdot.fi` | 168 | 6 | 0 | 162 |
| `restplass.no` | 168 | 6 | 0 | 162 |
| `socialloop.ai` | 162 | 162 | 0 | 0 |
| `remoshift.com` | 138 | 10 | 128 | 0 |
| `fundinglandscape.com` | 129 | 81 | 48 | 0 |
| `revmesh2074.workers.dev` | 129 | 116 | 13 | 0 |
| 6459 other operators | 22498 | 21309 | 1125 | 64 |
