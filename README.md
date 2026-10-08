# MCP server tool changes

Last change observed 2026-10-08T15:57:01+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10128 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 21701 hosted endpoints (read daily, and every four hours while they keep changing).

25226 changes to a tool definition: 870 npm releases (624 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 24356 readings of hosted servers that found their tools changed; 356 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-08 | `remote/se.sistaminuten/travel-search` | 2026-10-08T135536052149 -> 2026-10-08T155701836637 | 1 changed | quiet |
| 2026-10-08 | `remote/com.followontours/cricket-travel` | 2026-10-08T135515710975 -> 2026-10-08T155658481928 | 3 changed | quiet |
| 2026-10-08 | `remote/no.apier/mcp` | 2026-10-07T001239575454 -> 2026-10-08T155654060135 | 24 changed | quiet |
| 2026-10-08 | `remote/com.thefomite/fomite` | 2026-10-08T064237860918 -> 2026-10-08T155635911034 | 1 changed | quiet |
| 2026-10-08 | `remote/io.github.SidneyBissoli/senado-br-mcp-cloudflare` | 2026-10-07T001222981472 -> 2026-10-08T155624960373 | 2 changed | quiet |
| 2026-10-08 | `remote/net.myopl/pickleball-public-knowledge` | 2026-10-06T105952900339 -> 2026-10-08T155603636493 | 1 changed | quiet |
| 2026-10-08 | `remote/com.stackerscan/stackerscan` | 2026-10-08T135528673807 -> 2026-10-08T155540213075 | 5 changed (every tool) | quiet |
| 2026-10-08 | `remote/fr.projet-ariane/ariane-orientation` | 2026-10-08T135522732198 -> 2026-10-08T155539499873 | 2 changed | quiet |
| 2026-10-08 | `remote/no.restplass/travel-search` | 2026-10-08T135539163965 -> 2026-10-08T155535402373 | 1 changed | quiet |
| 2026-10-08 | `remote/fi.akkilahdot/travel-search` | 2026-10-08T135454454766 -> 2026-10-08T155533847297 | 1 changed | quiet |
| 2026-10-08 | `remote/dk.afbudsrejser/travel-search` | 2026-10-08T135509970340 -> 2026-10-08T155530153893 | 1 changed | quiet |
| 2026-10-08 | `remote/io.github.VoiceScapee/voicescape` | 2026-10-08T135454873573 -> 2026-10-08T155527832487 | 3 changed | quiet |
| 2026-10-08 | `remote/io.github.SidneyBissoli/uis-mcp-server` | 2026-10-06T110234812981 -> 2026-10-08T155525607938 | 1 changed | quiet |
| 2026-10-08 | `remote/io.github.ogasurfproject-jpg/horizon-shield` | 2026-10-08T134941597162 -> 2026-10-08T155523745767 | 2 changed, 1 added, 1 removed | quiet |
| 2026-10-08 | `remote/dev.horizonshield/horizon-shield` | 2026-10-08T134941918818 -> 2026-10-08T155524160386 | 2 changed, 1 added, 1 removed | quiet |
| 2026-10-08 | `remote/com.tickerinside/tickerinside-mcp` | 2026-10-06T184108295806 -> 2026-10-08T155522755067 | 1 changed, 11 added, 10 removed | quiet |
| 2026-10-08 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-07T213829898889 -> 2026-10-08T155522663521 | 1 changed | quiet |
| 2026-10-08 | `remote/com.theoddsgap/answers` | 2026-10-07T063314442624 -> 2026-10-08T155520226030 | 3 changed | quiet |
| 2026-10-08 | `remote/ch.swisslivingindex/swiss-living-index` | 2026-10-08T135405538627 -> 2026-10-08T155520536103 | 2 changed, 4 added | quiet |
| 2026-10-08 | `remote/com.swarmmemo/bulletin` | 2026-10-08T135406888707 -> 2026-10-08T155522389588 | 80 changed (every tool) | quiet |
| 2026-10-08 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-08T135349639237 -> 2026-10-08T155516783535 | 1 changed | quiet |
| 2026-10-08 | `remote/io.github.Ahmet11159/x402-agent-services` | 2026-10-08T134918044011 -> 2026-10-08T155516583059 | 1 changed | quiet |
| 2026-10-08 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-07T154936755025 -> 2026-10-08T155515423310 | 13 changed | quiet |
| 2026-10-08 | `remote/site.chatgpt.lorh89.the-knowledge-commons/evidence` | 2026-10-06T110144358513 -> 2026-10-08T155515051794 | 1 changed, 1 added | quiet |
| 2026-10-08 | `remote/com.pv-solaire-energie/devis-solaire` | 2026-10-08T135258681083 -> 2026-10-08T155508691189 | 1 changed | quiet |
| 2026-10-08 | `remote/io.github.richardsolomou/praetorium` | 2026-10-06T110044787682 -> 2026-10-08T155504371969 | 1 changed | quiet |
| 2026-10-08 | `remote/co.lumman/mail` | 2026-10-08T134822305977 -> 2026-10-08T155500565078 | 4 changed | quiet |
| 2026-10-08 | `remote/com.thetempleofdoom.osint-mcp/osint-terminal` | 2026-10-08T135232816328 -> 2026-10-08T155459377753 | 4 added | quiet |
| 2026-10-08 | `remote/com.musedin/musedin` | 2026-10-06T110049684450 -> 2026-10-08T155454857518 | 1 changed | quiet |
| 2026-10-08 | `remote/com.mooncatcherwire/wire` | 2026-10-06T110046540091 -> 2026-10-08T155454556636 | 3 changed | quiet |
| 2026-10-08 | `remote/io.github.mirabello-consultancy/mcp-server` | 2026-10-08T135032874418 -> 2026-10-08T155447954879 | 63 changed, 1 added (every tool) | quiet |
| 2026-10-08 | `remote/market.nostos/nostos` | 2026-10-08T135104107620 -> 2026-10-08T155506243294 | 6 changed | quiet |
| 2026-10-08 | `remote/io.github.marian-kamenistak/elc-conference-mcp-tickets` | 2026-10-08T134959785392 -> 2026-10-08T155443787333 | 4 changed | quiet |
| 2026-10-08 | `remote/so.darwin/darwin` | 2026-10-08T134953697211 -> 2026-10-08T155442001757 | 1 changed, 1 added | quiet |
| 2026-10-08 | `remote/co.homemaster/homemaster` | 2026-10-07T154844743399 -> 2026-10-08T155442013491 | 4 changed | quiet |
| 2026-10-08 | `remote/ai.forkmate/forkmate` | 2026-10-08T134957430661 -> 2026-10-08T155441374747 | 1 added | quiet |
| 2026-10-08 | `remote/com.cielstay/cielstay` | 2026-10-06T105807141825 -> 2026-10-08T155440778620 | 1 changed | quiet |
| 2026-10-08 | `remote/com.squirrelscan/squirrelscan` | 2026-10-08T135053826298 -> 2026-10-08T155445041075 | 2 changed | quiet |
| 2026-10-08 | `remote/app.aiponge/mcp` | 2026-10-08T134919229232 -> 2026-10-08T155439283630 | 12 changed, 7 added | quiet |
| 2026-10-08 | `remote/co.marketmayhem/mcp` | 2026-10-08T134902197403 -> 2026-10-08T155437733773 | 4 changed, 1 added | quiet |
| 2026-10-08 | `remote/com.kenwea.www/notary` | 2026-10-08T134958154055 -> 2026-10-08T155433249456 | 1 changed | quiet |
| 2026-10-08 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-08T134621209536 -> 2026-10-08T155431126792 | 1 changed | quiet |
| 2026-10-08 | `remote/com.jojapi/product-barcode-api` | 2026-10-08T134954542060 -> 2026-10-08T155433901727 | 2 changed | quiet |
| 2026-10-08 | `remote/app.sallim/contract-compass` | 2026-10-08T134520191474 -> 2026-10-08T155415056420 | 1 changed | quiet |
| 2026-10-08 | `remote/io.github.getDynamoi/dynamoi` | 2026-10-08T134634854641 -> 2026-10-08T155413041707 | 2 added, 1 removed | quiet |
| 2026-10-08 | `remote/com.editalmd/editalmd` | 2026-10-07T154845526967 -> 2026-10-08T155409014576 | 2 added | quiet |
| 2026-10-08 | `remote/build.naru/contract-compass` | 2026-10-08T134558207212 -> 2026-10-08T155405683257 | 1 changed | quiet |
| 2026-10-08 | `remote/online.disputes/mcp` | 2026-10-08T134540775752 -> 2026-10-08T155356668483 | 3 changed | quiet |
| 2026-10-08 | `remote/com.blockvectra/docs` | 2026-10-08T134541326157 -> 2026-10-08T155356342103 | 3 changed | quiet |
| 2026-10-08 | `remote/ai.buildersinfintech/fintech-data` | 2026-10-06T105349654362 -> 2026-10-08T155356954483 | 1 added | quiet |
| 2026-10-08 | `remote/com.uplika/uplika` | 2026-10-07T154817095640 -> 2026-10-08T155351941035 | 1 changed | quiet |
| 2026-10-08 | `remote/org.aspern/aspern` | 2026-10-08T064132347756 -> 2026-10-08T155351049803 | 7 changed | quiet |
| 2026-10-08 | `remote/kr.xdata/xdata-mcp` | 2026-10-08T134426202397 -> 2026-10-08T155346660449 | 3 changed, 1 added | quiet |
| 2026-10-08 | `remote/io.github.magiccadai/magicon` | 2026-10-08T134340600221 -> 2026-10-08T155344798187 | 3 added | quiet |
| 2026-10-08 | `remote/eu.sirenic/sirenic` | 2026-10-08T134415573314 -> 2026-10-08T155346597584 | 4 changed | quiet |
| 2026-10-08 | `remote/com.hookdetector/hookdetector` | 2026-10-08T134200414451 -> 2026-10-08T155342703044 | 2 changed | quiet |
| 2026-10-08 | `remote/br.com.brasilnfe/fiscal` | 2026-10-06T105038128208 -> 2026-10-08T155341802785 | 3 changed | quiet |
| 2026-10-08 | `remote/io.github.assetfare/assetfare` | 2026-10-07T063203660180 -> 2026-10-08T155340540064 | 4 changed | quiet |
| 2026-10-08 | `remote/xyz.apexfaucet/apex-x1` | 2026-10-08T134152703693 -> 2026-10-08T155339316360 | 3 changed | review |
| 2026-10-08 | `remote/app.awardia/awardia` | 2026-10-07T213720754281 -> 2026-10-08T155340665346 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 16906 substantive, 7969 that changed only numbers (a catalogue counter ticking, a date), 351 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 13231 | 5706 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 538 | 538 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `sistaminuten.se` | 85 | 2 | 0 | 83 |
| `afbudsrejser.dk` | 84 | 2 | 0 | 82 |
| `akkilahdot.fi` | 84 | 2 | 0 | 82 |
| `restplass.no` | 84 | 2 | 0 | 82 |
| `socialloop.ai` | 82 | 82 | 0 | 0 |
| `caseyjhand.com` | 77 | 77 | 0 | 0 |
| `dayze.com` | 67 | 67 | 0 | 0 |
| `fundinglandscape.com` | 59 | 34 | 25 | 0 |
| 3042 other operators | 8397 | 7956 | 419 | 22 |
