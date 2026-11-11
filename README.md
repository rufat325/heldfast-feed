# MCP server tool changes

Last change observed 2026-11-11T15:01:55+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

91117 changes to a tool definition: 3941 npm releases (3695 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 87176 readings of hosted servers that found their tools changed; 3779 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-11 | `remote/com.xquik/mcp` | 2026-11-06T214845675242 -> 2026-11-11T150156730815 | 1 changed | quiet |
| 2026-11-11 | `remote/com.uselauda/lauda` | 2026-11-02T163740608869 -> 2026-11-11T150149223543 | 3 changed | quiet |
| 2026-11-11 | `remote/com.unifiedchambers/legal` | 2026-10-17T055956506893 -> 2026-11-11T150147658660 | 1 changed | quiet |
| 2026-11-11 | `remote/com.theprotoclinical/commerce` | 2026-11-05T222230628124 -> 2026-11-11T150145153753 | 5 changed | quiet |
| 2026-11-11 | `remote/com.serverscan/mcp` | 2026-10-31T130426372251 -> 2026-11-11T150138911261 | 1 changed | quiet |
| 2026-11-11 | `remote/design.overflow/mcp` | 2026-11-10T130432443457 -> 2026-11-11T150132047214 | 1 changed | quiet |
| 2026-11-11 | `remote/com.mintlify/searchmcp` | 2026-10-31T062142328289 -> 2026-11-11T150127780779 | 1 changed | quiet |
| 2026-11-11 | `remote/studio.gradients/mcp` | 2026-11-11T071411673043 -> 2026-11-11T150117004957 | 1 changed | quiet |
| 2026-11-11 | `remote/com.yomachichi/shop` | 2026-11-05T222215638545 -> 2026-11-11T150106601993 | 5 changed | quiet |
| 2026-11-11 | `remote/dev.workers.moneytools.x402-pay-precheck/pay-precheck` | 2026-11-10T130357484165 -> 2026-11-11T150101226869 | 2 changed, 1 removed | quiet |
| 2026-11-11 | `remote/app.cleanchart/cleanchart` | 2026-10-26T133509293436 -> 2026-11-11T150101440651 | 2 changed, 1 removed | quiet |
| 2026-11-11 | `remote/io.github.Fizzl13/x402-doctor` | 2026-11-05T124829107710 -> 2026-11-11T150100196919 | 2 changed | quiet |
| 2026-11-11 | `remote/cn.com.bioinformatics/weishengxin` | 2026-11-11T071410506200 -> 2026-11-11T150101738944 | 4 changed | quiet |
| 2026-11-11 | `remote/fi.akkilahdot/travel-search` | 2026-11-11T071404930378 -> 2026-11-11T150055787693 | 1 changed | quiet |
| 2026-11-11 | `remote/com.vedutum/vedutum` | 2026-11-07T133504629703 -> 2026-11-11T150053887225 | 1 changed | quiet |
| 2026-11-11 | `remote/com.supersetapp/public` | 2026-11-07T133456379640 -> 2026-11-11T150046736969 | 1 changed | review |
| 2026-11-11 | `remote/xn--3ds443g.xn--s7y/duan-online` | 2026-11-10T153029087384 -> 2026-11-11T150041699586 | 2 changed, 5 added | quiet |
| 2026-11-11 | `remote/help.servicebuddy/mcp` | 2026-11-06T144912725291 -> 2026-11-11T150041194516 | 2 changed | quiet |
| 2026-11-11 | `remote/uk.webdesignsussex/site` | 2026-10-06T110335709243 -> 2026-11-11T150035302572 | 1 changed | quiet |
| 2026-11-11 | `remote/uk.webdesignpoole/site` | 2026-10-06T110335436844 -> 2026-11-11T150035264115 | 1 changed | quiet |
| 2026-11-11 | `remote/com.twominutetoolkit/toolkit` | 2026-11-02T163448050912 -> 2026-11-11T150029323738 | 20 changed (every tool) | quiet |
| 2026-11-11 | `remote/com.test-well/testwell` | 2026-10-26T211531997454 -> 2026-11-11T150024588172 | 1 changed | quiet |
| 2026-11-11 | `remote/io.linkjolt/linkjolt` | 2026-11-09T170139239588 -> 2026-11-11T150020278168 | 1 changed | quiet |
| 2026-11-11 | `remote/com.socialfaktory/mcp` | 2026-11-05T222221191291 -> 2026-11-11T150018971930 | 3 changed | quiet |
| 2026-11-11 | `remote/se.sistaminuten/travel-search` | 2026-11-11T071425435926 -> 2026-11-11T150018387525 | 1 changed | quiet |
| 2026-11-11 | `remote/ai.snowsure/snow` | 2026-10-28T133502175193 -> 2026-11-11T150018845561 | 1 changed | quiet |
| 2026-11-11 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-11T071400900516 -> 2026-11-11T150027763006 | 3 changed | quiet |
| 2026-11-11 | `remote/cz.iustoria/pruvodci` | 2026-11-10T220145215044 -> 2026-11-11T150017340348 | 1 changed | quiet |
| 2026-11-11 | `remote/ru.vedarai/mcp` | 2026-11-11T071401966882 -> 2026-11-11T150015477575 | 1 changed | quiet |
| 2026-11-11 | `remote/io.github.cyanheads/usda-mcp-server` | 2026-10-26T133427919441 -> 2026-11-11T150008052999 | 4 changed | quiet |
| 2026-11-11 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-11T071426804656 -> 2026-11-11T150008969702 | 1 changed | quiet |
| 2026-11-11 | `remote/io.github.fmind/portfolio` | 2026-11-10T220141596740 -> 2026-11-11T150006099562 | 2 changed | quiet |
| 2026-11-11 | `remote/com.menloinsurance/mcp` | 2026-11-05T115419183959 -> 2026-11-11T150002949500 | 1 changed | quiet |
| 2026-11-11 | `remote/app.openkrill/trending` | 2026-11-04T150423741066 -> 2026-11-11T145951482748 | 1 added | quiet |
| 2026-11-11 | `remote/nl.darioa/webdev` | 2026-11-02T163407523612 -> 2026-11-11T145944949222 | 1 changed | quiet |
| 2026-11-11 | `remote/la.desky/mcp` | 2026-11-02T163408215643 -> 2026-11-11T145945582037 | 5 changed (every tool) | quiet |
| 2026-11-11 | `remote/co.developh/studio` | 2026-11-08T135837299634 -> 2026-11-11T145946743118 | 1 changed | quiet |
| 2026-11-11 | `remote/com.coveragecat/insurance` | 2026-11-05T010737155360 -> 2026-11-11T145944294123 | 12 changed | quiet |
| 2026-11-11 | `remote/io.github.nimitt-IN/india-cyber-regulations` | 2026-11-04T123830086938 -> 2026-11-11T145939294894 | 2 changed | quiet |
| 2026-11-11 | `remote/com.veterans-rights/bva-corpus` | 2026-10-10T062543337792 -> 2026-11-11T145936985987 | 1 changed | quiet |
| 2026-11-11 | `remote/page.wordy/wordy-page.1` | 2026-11-02T163827979880 -> 2026-11-11T145935310164 | 1 changed | quiet |
| 2026-11-11 | `remote/com.anchorterminal/anchor-terminal` | 2026-11-08T204924969681 -> 2026-11-11T145935694832 | 4 changed, 1 added, 1 removed | quiet |
| 2026-11-11 | `remote/com.tabflows/site` | 2026-11-04T151031259008 -> 2026-11-11T145931082370 | 2 changed | quiet |
| 2026-11-11 | `remote/com.1stdibs/1stDibs` | 2026-11-05T115351738921 -> 2026-11-11T145930963672 | 5 changed (every tool) | quiet |
| 2026-11-11 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-11T071354098088 -> 2026-11-11T145931258963 | 2 changed | quiet |
| 2026-11-11 | `remote/io.theagentindex/agent-index` | 2026-11-05T115400398349 -> 2026-11-11T145929203611 | 6 changed (every tool) | quiet |
| 2026-11-11 | `remote/uk.co.websitedesignwoking/site` | 2026-10-06T110221568787 -> 2026-11-11T145926400725 | 1 changed | quiet |
| 2026-11-11 | `remote/uk.co.websitedesignguildford/site` | 2026-10-06T110221600556 -> 2026-11-11T145925985618 | 1 changed | quiet |
| 2026-11-11 | `remote/uk.webdesignsuffolk/site` | 2026-10-06T110220065063 -> 2026-11-11T145924689821 | 1 changed | quiet |
| 2026-11-11 | `remote/no.restplass/travel-search` | 2026-11-11T071457298003 -> 2026-11-11T145920951614 | 1 changed | quiet |
| 2026-11-11 | `remote/com.withresumeai/ats` | 2026-10-17T055548367007 -> 2026-11-11T145921093533 | 2 changed | quiet |
| 2026-11-11 | `remote/com.taskhold/taskhold` | 2026-11-04T150333021852 -> 2026-11-11T145917545773 | 1 changed, 1 added | quiet |
| 2026-11-11 | `remote/uk.co.whitelabelseomarketing/site` | 2026-10-06T110135867402 -> 2026-11-11T145916541760 | 1 changed | quiet |
| 2026-11-11 | `remote/io.github.vassiliylakhonin/vizier` | 2026-10-27T112328680521 -> 2026-11-11T145915005451 | 1 changed | quiet |
| 2026-11-11 | `remote/com.tamingdns/mcp` | 2026-11-10T220120688734 -> 2026-11-11T145914713997 | 4 changed | quiet |
| 2026-11-11 | `remote/network.lucie/sync` | 2026-10-19T135411970585 -> 2026-11-11T145912629729 | 2 changed, 1 added | quiet |
| 2026-11-11 | `remote/com.swellcabin/surf` | 2026-11-11T071348466316 -> 2026-11-11T145909212968 | 2 changed | quiet |
| 2026-11-11 | `remote/uk.co.websitedesignerssmallbusiness/site` | 2026-10-06T110132777610 -> 2026-11-11T145908917025 | 1 changed | quiet |
| 2026-11-11 | `remote/io.suverse.versum/catalog` | 2026-11-11T071422155044 -> 2026-11-11T145910247839 | 3 changed | quiet |
| 2026-11-11 | `remote/com.swarmmemo/bulletin.1` | 2026-11-11T071348897910 -> 2026-11-11T145910211995 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 57003 substantive, 33163 that changed only numbers (a catalogue counter ticking, a date), 951 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 48830 | 17746 | 31084 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 2108 | 2108 | 0 | 0 |
| `caseyjhand.com` | 383 | 383 | 0 | 0 |
| `civai.co` | 286 | 286 | 0 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `revmesh2074.workers.dev` | 222 | 195 | 27 | 0 |
| `sistaminuten.se` | 222 | 6 | 0 | 216 |
| `afbudsrejser.dk` | 221 | 6 | 0 | 215 |
| `akkilahdot.fi` | 221 | 6 | 0 | 215 |
| `restplass.no` | 221 | 6 | 0 | 215 |
| `socialloop.ai` | 213 | 213 | 0 | 0 |
| 8782 other operators | 35591 | 33449 | 2052 | 90 |
