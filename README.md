# MCP server tool changes

Last change observed 2026-11-25T17:53:21+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 18238 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 43073 hosted endpoints (read daily, and every four hours while they keep changing).

138918 changes to a tool definition: 5427 npm releases (5181 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 133491 readings of hosted servers that found their tools changed; 5109 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-25 | `remote/xyz.x402helper/mcp` | 2026-11-20T105719878849 -> 2026-11-25T175323115648 | 1 changed, 1 added | review |
| 2026-11-25 | `remote/nl.prijsprofeet/prijsprofeet-be` | 2026-11-21T130617679944 -> 2026-11-25T175231974669 | 1 changed, 1 added | quiet |
| 2026-11-25 | `remote/nl.prijsprofeet/prijsprofeet` | 2026-11-21T130618221794 -> 2026-11-25T175232310744 | 1 changed, 1 added | quiet |
| 2026-11-25 | `remote/nl.postkamer/postkamer` | 2026-11-23T185332441329 -> 2026-11-25T175230589348 | 3 changed | quiet |
| 2026-11-25 | `remote/com.oltechx.www/marketplace` | 2026-11-17T164831907027 -> 2026-11-25T175225831485 | 1 changed | quiet |
| 2026-11-25 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-25T110351580327 -> 2026-11-25T175157231237 | 3 changed | quiet |
| 2026-11-25 | `remote/io.github.christopherjjellison-maker/zorvu` | 2026-11-24T170435253254 -> 2026-11-25T175147492455 | 1 added | quiet |
| 2026-11-25 | `remote/io.github.Ments123/dmd-costs-tools` | 2026-11-19T123704818107 -> 2026-11-25T175146470419 | 1 changed | quiet |
| 2026-11-25 | `remote/io.github.dwiel/buyusbcables` | 2026-11-25T110331575623 -> 2026-11-25T175137943785 | 4 changed | quiet |
| 2026-11-25 | `remote/au.com.campwatch/campwatch` | 2026-10-26T133635880031 -> 2026-11-25T175138950810 | 3 changed, 1 removed | quiet |
| 2026-11-25 | `remote/software.brainiac/wallet-intelligence` | 2026-11-23T185245468774 -> 2026-11-25T175135849747 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/vehicle-transport` | 2026-11-23T185245383536 -> 2026-11-25T175135799606 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/tokenomics` | 2026-11-23T185245192991 -> 2026-11-25T175135739704 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/threat-intelligence` | 2026-11-23T185245704092 -> 2026-11-25T175136067738 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/telecom-billing` | 2026-11-23T185244899898 -> 2026-11-25T175135415878 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/statistics` | 2026-11-23T185244943795 -> 2026-11-25T175135292739 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/staking-operations` | 2026-11-23T185244975887 -> 2026-11-25T175135071488 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/solar-design` | 2026-11-23T185244841282 -> 2026-11-25T175135198269 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/social-content` | 2026-11-23T185244829672 -> 2026-11-25T175135186533 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/soap-contracts` | 2026-11-23T185244602496 -> 2026-11-25T175134868285 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/security-signals` | 2026-11-23T185244504237 -> 2026-11-25T175135053950 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/security-configuration` | 2026-11-23T185244328281 -> 2026-11-25T175134623557 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/security` | 2026-11-23T185244265582 -> 2026-11-25T175134576448 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/sanctions-export-control` | 2026-11-23T185244176382 -> 2026-11-25T175134385058 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/route-optimization` | 2026-11-23T185244292456 -> 2026-11-25T175134424409 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/rental-operations` | 2026-11-23T185244392127 -> 2026-11-25T175134277480 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/public-infrastructure` | 2026-11-23T185244101990 -> 2026-11-25T175134168246 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/property-official` | 2026-11-23T185243677523 -> 2026-11-25T175133933488 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/property-intelligence` | 2026-11-23T185243576524 -> 2026-11-25T175133971237 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/privacy-operations` | 2026-11-23T185243605103 -> 2026-11-25T175133746680 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/portfolio-analytics` | 2026-11-23T185243507738 -> 2026-11-25T175133226725 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/options-analytics` | 2026-11-23T185243475721 -> 2026-11-25T175133152722 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/marketplace-health` | 2026-11-23T185243528244 -> 2026-11-25T175133237795 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/inventory-intelligence` | 2026-11-23T185243486067 -> 2026-11-25T175132961702 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/hr-operations` | 2026-11-23T185243135495 -> 2026-11-25T175133068526 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/health-codes` | 2026-11-23T185242929991 -> 2026-11-25T175132571277 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/fx` | 2026-11-23T185242852553 -> 2026-11-25T175132521143 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/fintech` | 2026-11-23T185242918027 -> 2026-11-25T175132213441 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/equity-analytics` | 2026-11-23T185242799489 -> 2026-11-25T175132506405 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/energy-intelligence` | 2026-11-23T185242738925 -> 2026-11-25T175132265387 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/email-domain` | 2026-11-23T185242711979 -> 2026-11-25T175132110144 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/defi-intelligence` | 2026-11-23T185242224878 -> 2026-11-25T175131584678 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/crypto-security` | 2026-11-23T185242232100 -> 2026-11-25T175131668104 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/crypto-payments` | 2026-11-23T185242073833 -> 2026-11-25T175131576478 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/crm-intelligence` | 2026-11-23T185242269823 -> 2026-11-25T175131610602 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/corporate-intelligence` | 2026-11-23T185242367724 -> 2026-11-25T175131871861 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/code` | 2026-11-23T185241511318 -> 2026-11-25T175131129398 | 1 changed, 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/claims` | 2026-11-23T185241613703 -> 2026-11-25T175130722318 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/chain-data` | 2026-11-23T185241585097 -> 2026-11-25T175130711924 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/building-energy` | 2026-11-23T185241925310 -> 2026-11-25T175130662768 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/brand-protection` | 2026-11-23T185241501674 -> 2026-11-25T175130439872 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/agriculture-intelligence` | 2026-11-23T185242005269 -> 2026-11-25T175130801812 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/agent-networks` | 2026-11-23T185241258944 -> 2026-11-25T175130146068 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/agent-contracts` | 2026-11-23T185240935854 -> 2026-11-25T175130039323 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/account-abstraction` | 2026-11-23T185240751514 -> 2026-11-25T175129740090 | 1 added | quiet |
| 2026-11-25 | `remote/software.brainiac/accessibility` | 2026-11-23T185240641435 -> 2026-11-25T175129809300 | 1 added | quiet |
| 2026-11-25 | `remote/uk.co.speedi/availability` | 2026-11-24T170406508872 -> 2026-11-25T175117333161 | 1 added, 1 removed | quiet |
| 2026-11-25 | `remote/design.overflow/mcp` | 2026-11-22T150547072657 -> 2026-11-25T175104616394 | 1 changed | quiet |
| 2026-11-25 | `remote/xyz.octio/octio` | 2026-11-23T185535065102 -> 2026-11-25T175100593050 | 1 changed | quiet |
| 2026-11-25 | `remote/se.sistaminuten/travel-search` | 2026-11-25T150406591420 -> 2026-11-25T175110541217 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 92576 substantive, 45128 that changed only numbers (a catalogue counter ticking, a date), 1214 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 76752 | 34678 | 42074 | 0 |
| `a2awire.com` | 3838 | 3838 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 536 | 536 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 401 | 401 | 0 | 0 |
| `revmesh2074.workers.dev` | 370 | 315 | 55 | 0 |
| `sistaminuten.se` | 283 | 7 | 0 | 276 |
| `afbudsrejser.dk` | 282 | 7 | 0 | 275 |
| `akkilahdot.fi` | 282 | 7 | 0 | 275 |
| `restplass.no` | 282 | 7 | 0 | 275 |
| `socialloop.ai` | 273 | 273 | 0 | 0 |
| 11490 other operators | 52798 | 49686 | 2999 | 113 |
