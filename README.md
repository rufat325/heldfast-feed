# MCP server tool changes

Last change observed 2026-11-24T05:05:21+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 18238 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 43073 hosted endpoints (read daily, and every four hours while they keep changing).

130599 changes to a tool definition: 5227 npm releases (4981 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 125372 readings of hosted servers that found their tools changed; 4785 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-24 | `remote/com.xmlvalid/xmlvalid` | 2026-11-23T204006809426 -> 2026-11-24T050523484065 | 1 changed | quiet |
| 2026-11-24 | `remote/ai.usedby/usedby` | 2026-11-23T204003556349 -> 2026-11-24T050521383822 | 2 changed | quiet |
| 2026-11-24 | `remote/xyz.tereno/tereno` | 2026-11-22T164202607485 -> 2026-11-24T050520205609 | 1 changed | review |
| 2026-11-24 | `remote/com.theagentcolosseum/agent-colosseum` | 2026-11-22T164205108794 -> 2026-11-24T050521846054 | 6 changed (every tool) | quiet |
| 2026-11-24 | `remote/se.sistaminuten/travel-search` | 2026-11-23T204002127918 -> 2026-11-24T050519827840 | 1 changed | quiet |
| 2026-11-24 | `remote/io.suverse.www/catalog` | 2026-11-23T185843261040 -> 2026-11-24T050521539275 | 2 changed | quiet |
| 2026-11-24 | `remote/uk.co.pricegraph/mcp` | 2026-11-23T185823918289 -> 2026-11-24T050517426754 | 1 changed | quiet |
| 2026-11-24 | `remote/com.onlyworlds/mcp` | 2026-11-22T073206643225 -> 2026-11-24T050517696381 | 4 changed, 1 added | quiet |
| 2026-11-24 | `remote/org.omenz.www/agent-tools` | 2026-11-22T221050338696 -> 2026-11-24T050516649487 | 5 changed | quiet |
| 2026-11-24 | `remote/io.github.jhonnysabino/moedux` | 2026-11-23T185812203608 -> 2026-11-24T050516839028 | 2 added | quiet |
| 2026-11-24 | `remote/io.github.techbybuild/vinylscout-mcp` | 2026-11-23T185613780858 -> 2026-11-24T050506786273 | 2 changed | quiet |
| 2026-11-24 | `remote/app.usesnippet/snippet` | 2026-11-22T164153661857 -> 2026-11-24T050504010206 | 1 added | quiet |
| 2026-11-24 | `remote/com.thenetworkery/network-tools` | 2026-11-23T203940857198 -> 2026-11-24T050502179563 | 1 changed | quiet |
| 2026-11-24 | `remote/com.thefomite/fomite` | 2026-11-23T081907584259 -> 2026-11-24T050501827622 | 1 changed | quiet |
| 2026-11-24 | `remote/com.swishrjobs/swishrjobs` | 2026-11-22T104400194176 -> 2026-11-24T050459223157 | 118 changed | quiet |
| 2026-11-24 | `remote/io.github.cryptoconspiracy/vurto-swap` | 2026-11-23T081906427940 -> 2026-11-24T050458653852 | 2 changed | review |
| 2026-11-24 | `remote/com.supercyclehq/supercycle` | 2026-11-23T185420907455 -> 2026-11-24T050457870540 | 1 changed | quiet |
| 2026-11-24 | `remote/com.submitbyhand/directory-submission` | 2026-11-23T185416351665 -> 2026-11-24T050458014340 | 1 changed | quiet |
| 2026-11-24 | `remote/ai.staffbots/dispatch` | 2026-11-23T185403293743 -> 2026-11-24T050455578491 | 1 added | quiet |
| 2026-11-24 | `remote/com.idosgames/platform` | 2026-11-23T185334817760 -> 2026-11-24T050453498165 | 2 changed | quiet |
| 2026-11-24 | `remote/io.github.CustomBlinds/cb-shop` | 2026-11-23T185323989214 -> 2026-11-24T050453685065 | 17 changed | quiet |
| 2026-11-24 | `remote/io.github.modaal-agent/screens-guide` | 2026-11-23T185301861550 -> 2026-11-24T050449831252 | 3 changed | quiet |
| 2026-11-24 | `remote/com.caelaralabs/seo` | 2026-11-23T185310546170 -> 2026-11-24T050450260101 | 15 added | quiet |
| 2026-11-24 | `remote/io.github.SverrirValgeirsson/rustyplan` | 2026-11-23T185247049815 -> 2026-11-24T050448942520 | 6 changed | quiet |
| 2026-11-24 | `remote/com.salonrenter/salonrenter-muse` | 2026-11-23T203919536618 -> 2026-11-24T050448678502 | 4 changed | quiet |
| 2026-11-24 | `remote/net.pwfplatform/prices` | 2026-11-22T104135690555 -> 2026-11-24T050442770740 | 1 changed | quiet |
| 2026-11-24 | `remote/com.profullstack/profullstack` | 2026-11-23T185151284701 -> 2026-11-24T050442583841 | 10 added | quiet |
| 2026-11-24 | `remote/com.prepportglobal/service-planner` | 2026-11-23T185144467057 -> 2026-11-24T050441247901 | 2 changed | quiet |
| 2026-11-24 | `remote/social.poolster/poolster` | 2026-11-23T185133996994 -> 2026-11-24T050440209465 | 24 changed, 2 added (every tool) | quiet |
| 2026-11-24 | `remote/com.peskio/peskio` | 2026-11-23T185113307425 -> 2026-11-24T050437046904 | 1 changed | quiet |
| 2026-11-24 | `remote/io.outil/outil` | 2026-11-23T203909988933 -> 2026-11-24T050435518140 | 3 changed, 7 added | quiet |
| 2026-11-24 | `remote/com.mypivots/mypivots` | 2026-11-23T185325434197 -> 2026-11-24T050431374927 | 2 changed | quiet |
| 2026-11-24 | `remote/io.giftgenius/gift-genius` | 2026-11-23T185305708985 -> 2026-11-24T050428204838 | 1 changed | quiet |
| 2026-11-24 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-23T185305561410 -> 2026-11-24T050429372552 | 2 changed | quiet |
| 2026-11-24 | `remote/com.mindpolling/mindpolling` | 2026-11-23T184940680216 -> 2026-11-24T050427611356 | 1 added | quiet |
| 2026-11-24 | `remote/us.smartypos/syrve-pos` | 2026-11-23T184815647497 -> 2026-11-24T050424263351 | 1 changed | quiet |
| 2026-11-24 | `remote/page.wordy/wordy-page.1` | 2026-11-23T185226926426 -> 2026-11-24T050423132358 | 2 changed | quiet |
| 2026-11-24 | `remote/io.github.priors-agents/priors-read` | 2026-11-22T103837818821 -> 2026-11-24T050423148697 | 1 added | quiet |
| 2026-11-24 | `remote/io.github.Ipayx-stellar/fx-audit` | 2026-11-22T150814929635 -> 2026-11-24T050422593327 | 1 changed | quiet |
| 2026-11-24 | `remote/com.whizbrew/whizbrew` | 2026-11-23T185220647280 -> 2026-11-24T050421699965 | 3 changed, 3 added | quiet |
| 2026-11-24 | `remote/com.rivalsweeper/signals` | 2026-11-22T103846320403 -> 2026-11-24T050423825940 | 1 changed | quiet |
| 2026-11-24 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-11-23T203851094441 -> 2026-11-24T050420391384 | 9 changed | review |
| 2026-11-24 | `remote/site.chatgpt.handy-drake-3041.versionproof-beta/versionproof` | 2026-11-23T185156412631 -> 2026-11-24T050419510287 | 2 changed | quiet |
| 2026-11-24 | `remote/io.suverse.versum/catalog` | 2026-11-23T185158110254 -> 2026-11-24T050428989080 | 2 changed | quiet |
| 2026-11-24 | `remote/com.mofcloud/pricing` | 2026-11-23T184704123959 -> 2026-11-24T050420927251 | 12 changed | quiet |
| 2026-11-24 | `remote/org.townindex/directory` | 2026-11-23T185125472513 -> 2026-11-24T050417621610 | 2 changed | quiet |
| 2026-11-24 | `remote/io.kompare/search` | 2026-11-23T184639875929 -> 2026-11-24T050419400049 | 2 changed | quiet |
| 2026-11-24 | `remote/dev.kitscout/kitscout` | 2026-11-22T073142551795 -> 2026-11-24T050416943662 | 2 changed | quiet |
| 2026-11-24 | `remote/com.jojapi/sms-verify` | 2026-11-23T081854087432 -> 2026-11-24T050417782300 | 1 changed | quiet |
| 2026-11-24 | `remote/com.eduavenues/eduavenues` | 2026-11-22T104423925937 -> 2026-11-24T050416931941 | 5 changed | quiet |
| 2026-11-24 | `remote/com.theaiworldnetwork/aifusionone` | 2026-11-23T185103841650 -> 2026-11-24T050414206067 | 36 added | quiet |
| 2026-11-24 | `remote/io.github.christopherjjellison-maker/zorvu` | 2026-11-23T185624643102 -> 2026-11-24T050413777748 | 2 changed | quiet |
| 2026-11-24 | `remote/org.cemresearchproject/cem` | 2026-11-23T184458069355 -> 2026-11-24T050409880341 | 2 added | quiet |
| 2026-11-24 | `remote/io.github.greatscottatl/x402-cluster` | 2026-11-23T185609317531 -> 2026-11-24T050411177490 | 1 changed | quiet |
| 2026-11-24 | `remote/work.agentexchange/chain-reads` | 2026-11-23T185024963282 -> 2026-11-24T050410933242 | 1 changed | review |
| 2026-11-24 | `remote/io.github.sorzio/sorzio` | 2026-11-23T185552653558 -> 2026-11-24T050409256344 | 10 changed | quiet |
| 2026-11-24 | `remote/io.github.dzhng/bento` | 2026-11-22T145658575223 -> 2026-11-24T050409006304 | 1 changed | quiet |
| 2026-11-24 | `remote/io.github.detongz/alauda-home-equity` | 2026-11-23T184409120399 -> 2026-11-24T050407807495 | 1 changed | quiet |
| 2026-11-24 | `remote/ca.bakhour/profitcollector` | 2026-11-23T203836460345 -> 2026-11-24T050408765282 | 8 changed, 7 added, 1 removed | review |
| 2026-11-24 | `remote/com.caelaralabs/social` | 2026-11-23T185004249731 -> 2026-11-24T050406595583 | 15 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 86286 substantive, 43125 that changed only numbers (a catalogue counter ticking, a date), 1188 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 71149 | 30943 | 40206 | 0 |
| `a2awire.com` | 3704 | 3704 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 522 | 522 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 401 | 401 | 0 | 0 |
| `revmesh2074.workers.dev` | 367 | 312 | 55 | 0 |
| `sistaminuten.se` | 276 | 6 | 0 | 270 |
| `afbudsrejser.dk` | 275 | 6 | 0 | 269 |
| `akkilahdot.fi` | 275 | 6 | 0 | 269 |
| `restplass.no` | 275 | 6 | 0 | 269 |
| `socialloop.ai` | 266 | 266 | 0 | 0 |
| 11068 other operators | 50268 | 47293 | 2864 | 111 |
