# MCP server tool changes

Last change observed 2026-11-14T14:04:37+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

99128 changes to a tool definition: 4181 npm releases (3935 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 94947 readings of hosted servers that found their tools changed; 4097 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-14 | `remote/io.github.travisseamon-a11y/xemstudio` | 2026-11-04T150828652968 -> 2026-11-14T140437464300 | 9 changed (every tool) | quiet |
| 2026-11-14 | `remote/com.veridionmarkets/disclosures` | 2026-10-20T052335651627 -> 2026-11-14T140422391725 | 3 changed | quiet |
| 2026-11-14 | `remote/eu.trisonia/concerts` | 2026-11-10T030051663651 -> 2026-11-14T140419021534 | 1 changed | quiet |
| 2026-11-14 | `remote/se.sistaminuten/travel-search` | 2026-11-14T114953778067 -> 2026-11-14T140356009127 | 1 changed | quiet |
| 2026-11-14 | `remote/com.oxfordledge/oxford-ledge` | 2026-11-09T170250269893 -> 2026-11-14T140338046084 | 4 changed, 2 added | quiet |
| 2026-11-14 | `remote/io.github.danbuildss/musecourt` | 2026-10-29T212915130704 -> 2026-11-14T140332641546 | 5 added | quiet |
| 2026-11-14 | `remote/com.getcleed/linkedin-buying-signals` | 2026-11-13T115951640826 -> 2026-11-14T140314181239 | 1 changed | quiet |
| 2026-11-14 | `remote/io.github.zodiacs-org/zodiacs` | 2026-11-09T170418872849 -> 2026-11-14T140256936626 | 19 changed (every tool) | quiet |
| 2026-11-14 | `remote/com.coverage-rights/coverage-rights` | 2026-11-10T220224489153 -> 2026-11-14T140254989438 | 5 changed | quiet |
| 2026-11-14 | `remote/ai.gtinfetch/gtinfetch.1` | 2026-10-19T135616385025 -> 2026-11-14T140247563456 | 1 changed | quiet |
| 2026-11-14 | `remote/com.anchorterminal/anchor-terminal` | 2026-11-11T145935694832 -> 2026-11-14T140243503740 | 1 changed | quiet |
| 2026-11-14 | `remote/com.therevenueaireport/the-revenue-ai-report` | 2026-09-23T162958672754 -> 2026-11-14T140243718466 | 1 changed | quiet |
| 2026-11-14 | `remote/io.github.wangjingjing1026uwh-hub/zaoqiniaoer` | 2026-10-19T135917058929 -> 2026-11-14T140230791272 | 2 changed | review |
| 2026-11-14 | `remote/com.parksy/parksy.1` | 2026-11-09T170336432271 -> 2026-11-14T140226171659 | 6 changed (every tool) | quiet |
| 2026-11-14 | `remote/com.washlib/washlib` | 2026-10-17T060412419757 -> 2026-11-14T140220321019 | 3 changed | quiet |
| 2026-11-14 | `remote/de.ladepunktdaten/ladesaeulen` | 2026-10-26T133540064803 -> 2026-11-14T140219478525 | 2 changed | quiet |
| 2026-11-14 | `remote/com.veterans-rights/bva-corpus` | 2026-11-11T145936985987 -> 2026-11-14T140218331312 | 7 changed | quiet |
| 2026-11-14 | `remote/com.verbalexperiment/lab-tools` | 2026-11-02T163633700001 -> 2026-11-14T140218703375 | 8 changed | quiet |
| 2026-11-14 | `remote/am.yerevanestate/yerevan-apartments` | 2026-11-09T170220249149 -> 2026-11-14T140219122622 | 2 changed | quiet |
| 2026-11-14 | `remote/com.workers-rights/employment-law` | 2026-10-23T120709801449 -> 2026-11-14T140217651356 | 9 changed (every tool) | quiet |
| 2026-11-14 | `remote/io.github.Trusgent/trusgent-mcp` | 2026-10-29T104620985139 -> 2026-11-14T140215761007 | 2 changed, 1 added, 4 removed | quiet |
| 2026-11-14 | `remote/studio.gradients/mcp` | 2026-11-14T115034137625 -> 2026-11-14T140212258038 | 1 changed | quiet |
| 2026-11-14 | `remote/io.github.SoapyRED/freightutils` | 2026-11-06T072833318842 -> 2026-11-14T140207738108 | 1 changed, 1 added | quiet |
| 2026-11-14 | `remote/io.github.ceedot-rock/slid-phi-labs` | 2026-11-08T064603445544 -> 2026-11-14T140206471353 | 1 changed, 35 added | review |
| 2026-11-14 | `remote/io.github.bryantrudy24/saax-protocol` | 2026-11-07T133912887551 -> 2026-11-14T140204419750 | 3 changed, 13 added | quiet |
| 2026-11-14 | `remote/no.restplass/travel-search` | 2026-11-14T115023265229 -> 2026-11-14T140204394872 | 1 changed | quiet |
| 2026-11-14 | `remote/io.github.homeaccount7/signaldock` | 2026-11-14T114929711290 -> 2026-11-14T140204706663 | 1 changed | quiet |
| 2026-11-14 | `remote/in.proupiqr/upi-tools` | 2026-11-02T163616859866 -> 2026-11-14T140201489625 | 1 changed | quiet |
| 2026-11-14 | `remote/ai.oriiion/oriiion` | 2026-11-05T010649231896 -> 2026-11-14T140152329220 | 2 added | quiet |
| 2026-11-14 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-13T120549220791 -> 2026-11-14T140152613689 | 1 changed | quiet |
| 2026-11-14 | `remote/trade.buildix/hyperliquid` | 2026-11-08T135753586792 -> 2026-11-14T140151291696 | 1 changed | quiet |
| 2026-11-14 | `remote/com.viraloutliers/viral-outliers` | 2026-11-08T135754080305 -> 2026-11-14T140148610122 | 1 changed | quiet |
| 2026-11-14 | `remote/com.kulicadvisory/aictionbot-werkbank` | 2026-11-14T010700456300 -> 2026-11-14T140148354859 | 1 changed, 5 added | quiet |
| 2026-11-14 | `remote/cn.com.bioinformatics/weishengxin` | 2026-11-11T150101738944 -> 2026-11-14T140150307378 | 1 changed | quiet |
| 2026-11-14 | `remote/com.juzpost/mcp` | 2026-11-02T185416225001 -> 2026-11-14T140147590850 | 5 changed | quiet |
| 2026-11-14 | `remote/org.virtualflybrain/vfb3-mcp` | 2026-10-22T105904537820 -> 2026-11-14T140146282881 | 1 changed, 2 added | quiet |
| 2026-11-14 | `remote/fi.akkilahdot/travel-search` | 2026-11-14T115033541184 -> 2026-11-14T140145572560 | 1 changed | quiet |
| 2026-11-14 | `remote/com.fourwardhq/fourward` | 2026-11-02T163554008863 -> 2026-11-14T140139956238 | 1 changed | quiet |
| 2026-11-14 | `remote/app.fluxgraph/linkedin` | 2026-11-11T145850362987 -> 2026-11-14T140139541542 | 20 changed, 2 added | review |
| 2026-11-14 | `remote/com.wezzet/aicomms` | 2026-11-09T170216983677 -> 2026-11-14T140130114349 | 4 changed, 4 added | quiet |
| 2026-11-14 | `remote/io.github.seasonsagents-art/webaz` | 2026-11-12T155208582628 -> 2026-11-14T140126288514 | 1 added | quiet |
| 2026-11-14 | `remote/dev.emailmd/emailmd` | 2026-09-23T160839653158 -> 2026-11-14T140125563412 | 3 changed (every tool) | quiet |
| 2026-11-14 | `remote/com.walletmcppass/wallet-mcp` | 2026-11-10T220131782547 -> 2026-11-14T140122988522 | 2 added | quiet |
| 2026-11-14 | `remote/io.github.africanuspanga/cv-chap-chap` | 2026-11-02T163846990297 -> 2026-11-14T140121695044 | 1 removed | quiet |
| 2026-11-14 | `remote/dk.afbudsrejser/travel-search` | 2026-11-14T115021488911 -> 2026-11-14T140120563840 | 1 changed | quiet |
| 2026-11-14 | `remote/io.github.emilingemarkarlsson/bilkalkylen` | 2026-11-03T144828778334 -> 2026-11-14T140117582712 | 1 changed | quiet |
| 2026-11-14 | `remote/cl.tuki/travel-mcp` | 2026-09-29T073321692321 -> 2026-11-14T140115687193 | 1 changed | quiet |
| 2026-11-14 | `remote/com.beingso/animated-cards` | 2026-11-09T170109043287 -> 2026-11-14T140112962529 | 3 changed | quiet |
| 2026-11-14 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-14T115030589571 -> 2026-11-14T140111691198 | 1 changed | quiet |
| 2026-11-14 | `remote/com.travelacosta/trip-planning` | 2026-11-09T170058362888 -> 2026-11-14T140109871367 | 1 changed | quiet |
| 2026-11-14 | `remote/com.wht-ai/wai` | 2026-11-08T153902889323 -> 2026-11-14T140109798063 | 11 changed | quiet |
| 2026-11-14 | `remote/ai.rams/rams` | 2026-10-19T135211107287 -> 2026-11-14T140100861823 | 5 changed (every tool) | quiet |
| 2026-11-14 | `remote/tech.dc5.whois/dc5-whois` | 2026-10-31T130219031061 -> 2026-11-14T140055103248 | 3 changed | quiet |
| 2026-11-14 | `remote/com.useaiblocks/library` | 2026-11-13T115848121045 -> 2026-11-14T140043482133 | 14 changed, 3 removed | quiet |
| 2026-11-14 | `remote/io.suverse.versum/catalog` | 2026-11-14T114927179509 -> 2026-11-14T140035733751 | 1 changed | quiet |
| 2026-11-14 | `remote/io.github.89rat/code402-verify-mcp` | 2026-10-26T133558596463 -> 2026-11-14T140032937113 | 16 changed | review |
| 2026-11-14 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-14T115025491560 -> 2026-11-14T140025012636 | 4 changed | quiet |
| 2026-11-14 | `remote/io.github.eyeinthesky6/unseen-workflow-compiler` | 2026-11-07T133334462333 -> 2026-11-14T140021704100 | 6 changed, 2 added | review |
| 2026-11-14 | `remote/fun.trnch/trnch` | 2026-11-11T145735075439 -> 2026-11-14T140018680671 | 6 changed | quiet |
| 2026-11-14 | `remote/io.github.emilingemarkarlsson/foraldraledighetsplanen` | 2026-10-26T133543653199 -> 2026-11-14T140013462284 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 61081 substantive, 37038 that changed only numbers (a catalogue counter ticking, a date), 1009 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 52535 | 17771 | 34764 | 0 |
| `a2awire.com` | 2508 | 2508 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 420 | 420 | 0 | 0 |
| `civai.co` | 318 | 318 | 0 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `revmesh2074.workers.dev` | 251 | 219 | 32 | 0 |
| `sistaminuten.se` | 235 | 6 | 0 | 229 |
| `afbudsrejser.dk` | 234 | 6 | 0 | 228 |
| `akkilahdot.fi` | 234 | 6 | 0 | 228 |
| `restplass.no` | 234 | 6 | 0 | 228 |
| `socialloop.ai` | 226 | 226 | 0 | 0 |
| 9379 other operators | 39334 | 36996 | 2242 | 96 |
