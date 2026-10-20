# MCP server tool changes

Last change observed 2026-10-20T13:54:41+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

37423 changes to a tool definition: 1522 npm releases (1276 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 35901 readings of hosted servers that found their tools changed; 2253 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-20 | `remote/no.restplass/travel-search` | 2026-10-20T120636602161 -> 2026-10-20T135442038712 | 1 changed | quiet |
| 2026-10-20 | `remote/se.sistaminuten/travel-search` | 2026-10-20T120647528408 -> 2026-10-20T135439085406 | 1 changed | quiet |
| 2026-10-20 | `remote/dk.afbudsrejser/travel-search` | 2026-10-20T120551216613 -> 2026-10-20T135437722954 | 1 changed | quiet |
| 2026-10-20 | `remote/studio.gradients/mcp` | 2026-10-20T120625443978 -> 2026-10-20T135437105486 | 1 changed | quiet |
| 2026-10-20 | `remote/org.warriorsfund/wounded-warriors` | 2026-10-19T212011505677 -> 2026-10-20T135435583983 | 3 changed | quiet |
| 2026-10-20 | `remote/io.github.jukky-source/wealth-agent` | 2026-10-20T120537981167 -> 2026-10-20T135435004044 | 2 added | quiet |
| 2026-10-20 | `remote/fi.akkilahdot/travel-search` | 2026-10-20T120601650558 -> 2026-10-20T135434454765 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.voicehook-ai/voicehook` | 2026-10-20T120548223769 -> 2026-10-20T135428174798 | 4 changed | quiet |
| 2026-10-20 | `remote/com.varioroam/esim-catalog` | 2026-10-19T135403412315 -> 2026-10-20T135427318161 | 7 changed, 1 added (every tool) | quiet |
| 2026-10-20 | `remote/io.github.Schoasch/backtesting-arena` | 2026-10-19T135437667654 -> 2026-10-20T135425064066 | 1 changed | quiet |
| 2026-10-20 | `remote/com.transitmcp/transit-mcp` | 2026-10-20T052446061544 -> 2026-10-20T135425698910 | 1 changed | quiet |
| 2026-10-20 | `remote/com.lazyweb/discovery` | 2026-10-20T104353228241 -> 2026-10-20T135422505401 | 1 changed | quiet |
| 2026-10-20 | `remote/ai.go-rocket/go-rocket` | 2026-10-20T104346981376 -> 2026-10-20T135421601798 | 1 changed | review |
| 2026-10-20 | `remote/com.swarmmemo/bulletin.1` | 2026-10-18T190054686864 -> 2026-10-20T135420074008 | 2 changed | quiet |
| 2026-10-20 | `remote/com.swarmmemo/bulletin` | 2026-10-18T190054706951 -> 2026-10-20T135420055591 | 2 changed | quiet |
| 2026-10-20 | `remote/jobs.robottraining/robot-training-jobs` | 2026-10-19T135600002417 -> 2026-10-20T135415355235 | 2 changed | quiet |
| 2026-10-20 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-20T120437487129 -> 2026-10-20T135415784818 | 1 changed | quiet |
| 2026-10-20 | `remote/com.shipshapedata/shipshape-data-docs` | 2026-10-19T135249672853 -> 2026-10-20T135415204168 | 1 changed | quiet |
| 2026-10-20 | `remote/com.vibe-fixer/vibefix` | 2026-10-20T104312203153 -> 2026-10-20T135414310116 | 2 changed | quiet |
| 2026-10-20 | `remote/io.github.exquad/thecablecode` | 2026-10-20T052310982060 -> 2026-10-20T135411769720 | 1 changed | quiet |
| 2026-10-20 | `remote/com.roamflat/esim-catalog` | 2026-10-18T190043354572 -> 2026-10-20T135410360739 | 7 changed, 1 added (every tool) | quiet |
| 2026-10-20 | `remote/com.remoshift/jobs` | 2026-10-20T120342762701 -> 2026-10-20T135408458587 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.jennipro-engineering/ghost-market-web` | 2026-10-20T052307826450 -> 2026-10-20T135407185552 | 1 changed | quiet |
| 2026-10-20 | `remote/com.shipshapedata/shipshape-data` | 2026-10-19T135044406213 -> 2026-10-20T135407152158 | 1 changed | quiet |
| 2026-10-20 | `remote/com.owlchart/owlchart` | 2026-10-18T223938952783 -> 2026-10-20T135406174718 | 1 added | quiet |
| 2026-10-20 | `remote/io.github.PrivateAISystems/needhave` | 2026-10-20T104000798953 -> 2026-10-20T135401453837 | 6 changed, 1 removed | quiet |
| 2026-10-20 | `remote/online.pageaudit/pageaudit` | 2026-10-20T104240413613 -> 2026-10-20T135402737574 | 1 changed | quiet |
| 2026-10-20 | `remote/com.proofprice/pricepaid` | 2026-10-20T120208004895 -> 2026-10-20T135358292924 | 5 changed, 1 added | quiet |
| 2026-10-20 | `remote/how.mise/mise` | 2026-10-20T103928149216 -> 2026-10-20T135359495781 | 3 changed | quiet |
| 2026-10-20 | `remote/de.viafrei/mcp` | 2026-10-19T135010058819 -> 2026-10-20T135359438146 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.dhamma-seeker/tripitaka-mcp` | 2026-10-19T135343036422 -> 2026-10-20T135357390163 | 8 changed | quiet |
| 2026-10-20 | `remote/com.okstays/okstays` | 2026-10-19T134915632428 -> 2026-10-20T135351954573 | 2 changed | quiet |
| 2026-10-20 | `remote/co.civai.nova/support-agent-admin` | 2026-10-20T120119848230 -> 2026-10-20T135350866043 | 2 added | quiet |
| 2026-10-20 | `remote/com.socialseal/mcp` | 2026-10-20T104116945439 -> 2026-10-20T135350266670 | 2 changed | quiet |
| 2026-10-20 | `remote/io.github.nevermined-io/catalog` | 2026-10-20T103814032545 -> 2026-10-20T135350784855 | 1 changed | quiet |
| 2026-10-20 | `remote/tech.marziale.mcp/marziale` | 2026-10-19T135242777873 -> 2026-10-20T135349218527 | 4 changed | quiet |
| 2026-10-20 | `remote/com.jojapi/sms-verify` | 2026-10-20T052249869740 -> 2026-10-20T135348724324 | 1 changed | quiet |
| 2026-10-20 | `remote/com.pagelemon/pagelemon` | 2026-10-19T155618021963 -> 2026-10-20T135347666539 | 13 changed, 12 added, 1 removed | quiet |
| 2026-10-20 | `remote/io.dropyour/dropyour` | 2026-10-18T051401097139 -> 2026-10-20T135347856053 | 2 changed | quiet |
| 2026-10-20 | `remote/com.wiacode/wiacode` | 2026-10-19T134809949585 -> 2026-10-20T135346069508 | 8 changed (every tool) | quiet |
| 2026-10-20 | `remote/org.brainkb/brainkb` | 2026-10-20T103908048814 -> 2026-10-20T135339601713 | 8 changed | quiet |
| 2026-10-20 | `remote/io.github.Yahhi/aimyear-mcp` | 2026-10-19T211818965214 -> 2026-10-20T135337410870 | 6 changed | quiet |
| 2026-10-20 | `remote/com.wiastandards/standards` | 2026-10-19T134752158635 -> 2026-10-20T135337288571 | 4 changed (every tool) | quiet |
| 2026-10-20 | `remote/com.lebaneselegislation/mcp` | 2026-10-19T134729554971 -> 2026-10-20T135331396862 | 3 changed, 1 added | quiet |
| 2026-10-20 | `remote/io.github.drexthealpha/knos` | 2026-10-19T211806772969 -> 2026-10-20T135329558499 | 1 added | quiet |
| 2026-10-20 | `remote/io.github.horizon-pulse/horizon-pulse` | 2026-10-20T052234421661 -> 2026-10-20T135327164153 | 1 added | review |
| 2026-10-20 | `remote/com.housingfeed/rental-listings` | 2026-10-19T134542344089 -> 2026-10-20T135329536071 | 1 changed | quiet |
| 2026-10-20 | `remote/com.wiastandards/wisdom` | 2026-10-19T134527246674 -> 2026-10-20T135325089177 | 3 changed (every tool) | quiet |
| 2026-10-20 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-20T115615318865 -> 2026-10-20T135322780441 | 1 changed | quiet |
| 2026-10-20 | `remote/com.exchangerebel/exchangerebel` | 2026-10-20T115557570316 -> 2026-10-20T135320628543 | 7 added | quiet |
| 2026-10-20 | `remote/com.onrender.draconic21-x402-api/data-tools.1` | 2026-10-18T112518922988 -> 2026-10-20T135316214317 | 34 changed | quiet |
| 2026-10-20 | `remote/com.onrender.draconic21-x402-api/data-tools` | 2026-10-18T112519031458 -> 2026-10-20T135316246633 | 28 changed | quiet |
| 2026-10-20 | `remote/io.github.Datura-ai/lium-docs` | 2026-10-19T134320687557 -> 2026-10-20T135315043070 | 1 changed | quiet |
| 2026-10-20 | `remote/dev.dnsdoctor/dns-doctor` | 2026-10-20T052225290734 -> 2026-10-20T135316683938 | 1 added | quiet |
| 2026-10-20 | `remote/io.github.edtool79-collab/hirepulse-gateway` | 2026-10-20T103540365815 -> 2026-10-20T135312630645 | 8 changed | quiet |
| 2026-10-20 | `remote/app.sallim/contract-compass` | 2026-10-18T185853016128 -> 2026-10-20T135313652091 | 3 changed | quiet |
| 2026-10-20 | `remote/build.naru/contract-compass` | 2026-10-18T185858862124 -> 2026-10-20T135310188018 | 3 changed | quiet |
| 2026-10-20 | `remote/com.cobaltcapture/cobalt` | 2026-10-20T103339015072 -> 2026-10-20T135304718137 | 1 changed | quiet |
| 2026-10-20 | `remote/com.cooperemail/cooper-email` | 2026-10-20T115357782281 -> 2026-10-20T135301246047 | 2 changed | quiet |
| 2026-10-20 | `remote/com.commsharbor/commsharbor` | 2026-10-19T052259092779 -> 2026-10-20T135300406797 | 1 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 24194 substantive, 12712 that changed only numbers (a catalogue counter ticking, a date), 517 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 19158 | 7228 | 11930 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 170 | 170 | 0 | 0 |
| `sistaminuten.se` | 124 | 4 | 0 | 120 |
| `afbudsrejser.dk` | 123 | 4 | 0 | 119 |
| `akkilahdot.fi` | 123 | 4 | 0 | 119 |
| `restplass.no` | 123 | 4 | 0 | 119 |
| `socialloop.ai` | 120 | 120 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `remoshift.com` | 94 | 6 | 88 | 0 |
| `fundinglandscape.com` | 93 | 59 | 34 | 0 |
| 4621 other operators | 14204 | 13504 | 660 | 40 |
