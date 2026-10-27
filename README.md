# MCP server tool changes

Last change observed 2026-10-27T05:41:30+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

53040 changes to a tool definition: 2293 npm releases (2047 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 50747 readings of hosted servers that found their tools changed; 2789 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-27 | `remote/com.techfabric/techfabric` | 2026-10-26T211527900484 -> 2026-10-27T054132097760 | 28 changed | quiet |
| 2026-10-27 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-10-26T052307684819 -> 2026-10-27T054129763805 | 2 changed | quiet |
| 2026-10-27 | `remote/com.zinvyl/marketplace` | 2026-10-26T211520170177 -> 2026-10-27T054130238280 | 12 changed | quiet |
| 2026-10-27 | `remote/com.yy-algo/japan-data` | 2026-10-26T133622498602 -> 2026-10-27T054129956698 | 1 added | quiet |
| 2026-10-27 | `remote/com.adrenalinelist/adventures` | 2026-10-26T133628708063 -> 2026-10-27T054126263530 | 4 added | quiet |
| 2026-10-27 | `remote/io.github.Z4KARY/upgrowth-mcp` | 2026-10-26T133613225037 -> 2026-10-27T054128296763 | 6 changed | quiet |
| 2026-10-27 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-10-26T211534777956 -> 2026-10-27T054123813986 | 1 removed | quiet |
| 2026-10-27 | `remote/com.whirrwork/whirrwork` | 2026-10-26T133619063175 -> 2026-10-27T054125302065 | 4 added | quiet |
| 2026-10-27 | `remote/no.restplass/travel-search` | 2026-10-26T211533757807 -> 2026-10-27T054123902346 | 1 changed | quiet |
| 2026-10-27 | `remote/ai.robowrite/mcp` | 2026-10-26T133556218487 -> 2026-10-27T054122865401 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.sf0116/myschoolhub` | 2026-10-26T133757622810 -> 2026-10-27T054122106693 | 2 changed | quiet |
| 2026-10-27 | `remote/dev.upfork/upfork` | 2026-10-26T211518078137 -> 2026-10-27T054123575752 | 6 changed, 1 added | quiet |
| 2026-10-27 | `remote/studio.gradients/mcp` | 2026-10-26T211511362408 -> 2026-10-27T054120732060 | 1 changed | quiet |
| 2026-10-27 | `remote/app.hyperwave.www/wavetable-tools` | 2026-10-26T133535103467 -> 2026-10-27T054120365340 | 1 added | quiet |
| 2026-10-27 | `remote/dk.afbudsrejser/travel-search` | 2026-10-26T211530140893 -> 2026-10-27T054119602293 | 1 changed | quiet |
| 2026-10-27 | `remote/app.wenbu/mcp` | 2026-10-25T102510555938 -> 2026-10-27T054122126916 | 1 changed | quiet |
| 2026-10-27 | `remote/fi.akkilahdot/travel-search` | 2026-10-26T211508290202 -> 2026-10-27T054117384240 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.theguysaccount/syncbook` | 2026-10-26T133510482733 -> 2026-10-27T054116743174 | 2 changed | quiet |
| 2026-10-27 | `remote/com.whoisbrowsing/mcp` | 2026-10-26T133455337539 -> 2026-10-27T054116248518 | 2 changed | quiet |
| 2026-10-27 | `remote/io.github.tinbox-labs/spawnpop` | 2026-10-26T133445495336 -> 2026-10-27T054113122527 | 2 added | quiet |
| 2026-10-27 | `remote/link.snip/snip` | 2026-10-26T211506181557 -> 2026-10-27T054113118623 | 2 changed, 6 removed | quiet |
| 2026-10-27 | `remote/io.github.tokenzero-ai/tokenzero` | 2026-10-26T133409226268 -> 2026-10-27T054110421779 | 5 changed (every tool) | quiet |
| 2026-10-27 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-26T052301196861 -> 2026-10-27T054110435488 | 1 changed | quiet |
| 2026-10-27 | `remote/io.roxskin/hyrox` | 2026-10-26T133403519383 -> 2026-10-27T054109511787 | 1 changed | quiet |
| 2026-10-27 | `remote/is.envelop.unisafe/insight` | 2026-10-26T133647294359 -> 2026-10-27T054109350335 | 1 added | quiet |
| 2026-10-27 | `remote/io.github.mooshee/untax` | 2026-10-26T133647985174 -> 2026-10-27T054109218177 | 20 changed (every tool) | quiet |
| 2026-10-27 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-10-26T211533143277 -> 2026-10-27T054107231391 | 1 removed | quiet |
| 2026-10-27 | `remote/dev.tanod/web` | 2026-10-25T102533610687 -> 2026-10-27T054109623972 | 1 changed | quiet |
| 2026-10-27 | `remote/com.quantagentshop/web-tools` | 2026-10-26T133335505829 -> 2026-10-27T054106985386 | 2 added | review |
| 2026-10-27 | `remote/app.realalpha/moments` | 2026-10-26T133341673411 -> 2026-10-27T054107975805 | 1 changed | quiet |
| 2026-10-27 | `remote/com.strongsaga/gear-lookup` | 2026-10-26T133339102848 -> 2026-10-27T054108804720 | 1 changed | quiet |
| 2026-10-27 | `remote/com.probativegrowth/legal-marketing-data.3` | 2026-10-26T133325342110 -> 2026-10-27T054105382286 | 6 changed (every tool) | quiet |
| 2026-10-27 | `remote/se.sistaminuten/travel-search` | 2026-10-26T211531231686 -> 2026-10-27T054105858936 | 1 changed | quiet |
| 2026-10-27 | `remote/io.taifoon/coordination-layer.1` | 2026-10-26T211531200710 -> 2026-10-27T054105699080 | 1 changed | review |
| 2026-10-27 | `remote/io.github.paulieb89/uk-legal-mcp` | 2026-10-26T211524928553 -> 2026-10-27T054108030855 | 3 changed | quiet |
| 2026-10-27 | `remote/io.github.dtajitdinov-aris/sphere-marketplace` | 2026-10-26T133334859512 -> 2026-10-27T054107353265 | 1 added, 1 removed | quiet |
| 2026-10-27 | `remote/io.github.canoydario847-cloud/privi-quantum` | 2026-10-26T153146494488 -> 2026-10-27T054105653612 | 24 added | quiet |
| 2026-10-27 | `remote/com.probativegrowth/legal-marketing-data.5` | 2026-10-26T133325178713 -> 2026-10-27T054105269400 | 6 changed (every tool) | quiet |
| 2026-10-27 | `remote/io.github.marcpineault/glacier-planner-calculator` | 2026-10-26T133312619930 -> 2026-10-27T054103620397 | 1 changed | quiet |
| 2026-10-27 | `remote/ai.trydock/dock` | 2026-10-26T133637756161 -> 2026-10-27T054110167558 | 1 changed, 1 added | quiet |
| 2026-10-27 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-26T211454937878 -> 2026-10-27T054103697218 | 2 changed | quiet |
| 2026-10-27 | `remote/com.ferntool/ip` | 2026-10-26T052255501633 -> 2026-10-27T054101410804 | 1 added | quiet |
| 2026-10-27 | `remote/com.roasexpert.tools/seo-audit` | 2026-10-26T133627758717 -> 2026-10-27T054101556740 | 5 changed (every tool) | quiet |
| 2026-10-27 | `remote/com.warminboxes/deliverability-tools` | 2026-10-26T153208497841 -> 2026-10-27T054058451294 | 2 changed | quiet |
| 2026-10-27 | `remote/com.remoshift/jobs` | 2026-10-26T211448372492 -> 2026-10-27T054058158081 | 1 changed | quiet |
| 2026-10-27 | `remote/xyz.urbangametheory/urban-game-theory` | 2026-10-26T211520140772 -> 2026-10-27T054057148535 | 3 changed | quiet |
| 2026-10-27 | `remote/org.mylastwill/mylastwill` | 2026-10-26T133217093341 -> 2026-10-27T054056403196 | 1 changed | quiet |
| 2026-10-27 | `remote/fr.synergieloc/immobilier` | 2026-10-26T211517470914 -> 2026-10-27T054057322013 | 14 added | quiet |
| 2026-10-27 | `remote/com.probativegrowth/legal-marketing-data.6` | 2026-10-26T133207629990 -> 2026-10-27T054055098158 | 6 changed (every tool) | quiet |
| 2026-10-27 | `remote/com.probativegrowth/legal-marketing-data.4` | 2026-10-26T133207656932 -> 2026-10-27T054055100504 | 6 changed (every tool) | quiet |
| 2026-10-27 | `remote/net.totallytarot/calculators` | 2026-10-26T211515810895 -> 2026-10-27T054054803643 | 13 changed | quiet |
| 2026-10-27 | `remote/com.claude.platform/docs` | 2026-10-26T133154790279 -> 2026-10-27T054053847547 | 4 changed (every tool) | quiet |
| 2026-10-27 | `remote/uk.co.theamateur/shoot-plan` | 2026-10-26T133720051737 -> 2026-10-27T054054328263 | 23 added | quiet |
| 2026-10-27 | `remote/com.thefomite/fomite` | 2026-10-26T052253273948 -> 2026-10-27T054053583389 | 1 changed | quiet |
| 2026-10-27 | `remote/ai.1court.state/court-directory` | 2026-10-26T133529899850 -> 2026-10-27T054053996928 | 2 changed | quiet |
| 2026-10-27 | `remote/com.webinarignition/mcp` | 2026-10-26T052255781258 -> 2026-10-27T054053192847 | 74 added | quiet |
| 2026-10-27 | `remote/at.space-core/game` | 2026-10-26T133523157631 -> 2026-10-27T054053857921 | 1 changed | quiet |
| 2026-10-27 | `remote/tax.terminal/filing` | 2026-10-26T211443807558 -> 2026-10-27T054051096859 | 2 changed | quiet |
| 2026-10-27 | `remote/com.tensorust/mcp` | 2026-10-26T133118150692 -> 2026-10-27T054050279212 | 1 added | review |
| 2026-10-27 | `remote/pro.sebbi/governance` | 2026-10-26T211505807821 -> 2026-10-27T054049874149 | 2 added, 45 removed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 34838 substantive, 17534 that changed only numbers (a catalogue counter ticking, a date), 668 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 28526 | 12158 | 16368 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 891 | 891 | 0 | 0 |
| `caseyjhand.com` | 233 | 233 | 0 | 0 |
| `sistaminuten.se` | 158 | 4 | 0 | 154 |
| `afbudsrejser.dk` | 157 | 4 | 0 | 153 |
| `akkilahdot.fi` | 157 | 4 | 0 | 153 |
| `restplass.no` | 157 | 4 | 0 | 153 |
| `socialloop.ai` | 152 | 152 | 0 | 0 |
| `remoshift.com` | 127 | 8 | 119 | 0 |
| `revmesh2074.workers.dev` | 123 | 114 | 9 | 0 |
| `fundinglandscape.com` | 121 | 77 | 44 | 0 |
| 5917 other operators | 19897 | 18848 | 994 | 55 |
