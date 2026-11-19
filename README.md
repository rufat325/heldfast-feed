# MCP server tool changes

Last change observed 2026-11-19T23:18:51+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

117992 changes to a tool definition: 4741 npm releases (4495 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 113251 readings of hosted servers that found their tools changed; 4472 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-19 | `remote/lol.shopat/deals` | 2026-11-19T162508222885 -> 2026-11-19T231853281569 | 6 added | quiet |
| 2026-11-19 | `remote/no.restplass/travel-search` | 2026-11-19T162504560527 -> 2026-11-19T231851959067 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.roomza-inc/roomza` | 2026-11-19T123904920861 -> 2026-11-19T231851480789 | 1 changed, 2 added | quiet |
| 2026-11-19 | `remote/com.kulicadvisory/aictionbot-werkbank` | 2026-11-19T020449871681 -> 2026-11-19T231847002088 | 9 added | quiet |
| 2026-11-19 | `remote/io.deeplead/deeplead` | 2026-11-17T234346973926 -> 2026-11-19T231845769628 | 4 changed, 4 added | quiet |
| 2026-11-19 | `remote/ai.usedby/usedby` | 2026-11-18T135950026259 -> 2026-11-19T231843518621 | 1 changed | quiet |
| 2026-11-19 | `remote/dk.afbudsrejser/travel-search` | 2026-11-19T162412636664 -> 2026-11-19T231843861545 | 1 changed | quiet |
| 2026-11-19 | `remote/se.sistaminuten/travel-search` | 2026-11-19T162257586677 -> 2026-11-19T231842695128 | 1 changed | quiet |
| 2026-11-19 | `remote/com.youspot/youspot` | 2026-11-19T020438917463 -> 2026-11-19T231842711974 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.LAHutchins91/xyvenra` | 2026-11-17T164905300399 -> 2026-11-19T231841639734 | 11 changed (every tool) | quiet |
| 2026-11-19 | `remote/io.github.wyroapi/wyro` | 2026-11-19T123801168702 -> 2026-11-19T231840353335 | 6 changed (every tool) | quiet |
| 2026-11-19 | `remote/com.kaicalls/kaicalls` | 2026-11-19T162225924387 -> 2026-11-19T231839917746 | 3 added | quiet |
| 2026-11-19 | `remote/studio.gradients/mcp` | 2026-11-19T162551451934 -> 2026-11-19T231839183331 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.philpof102-svg/tokenizedblock` | 2026-11-19T123647416603 -> 2026-11-19T231837619562 | 1 removed | quiet |
| 2026-11-19 | `remote/io.github.EasyGerber/easygerber` | 2026-11-19T124031853757 -> 2026-11-19T231838049864 | 2 changed | quiet |
| 2026-11-19 | `remote/ai.arcreport/ask` | 2026-11-18T135746653978 -> 2026-11-19T231837611012 | 2 changed | quiet |
| 2026-11-19 | `remote/fi.akkilahdot/travel-search` | 2026-11-19T162527457992 -> 2026-11-19T231837185767 | 1 changed | quiet |
| 2026-11-19 | `remote/com.rightshold/rightshold` | 2026-11-18T080207105226 -> 2026-11-19T231836859406 | 1 changed | quiet |
| 2026-11-19 | `remote/org.thealibrary/thea` | 2026-11-18T135541438642 -> 2026-11-19T231836108050 | 2 changed | quiet |
| 2026-11-19 | `remote/com.workinsiders/directory` | 2026-11-19T123815331431 -> 2026-11-19T231836959017 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-19T123713700221 -> 2026-11-19T231835490445 | 1 changed | quiet |
| 2026-11-19 | `remote/com.weverlabs/agentic-rails` | 2026-11-19T123933719010 -> 2026-11-19T231839611462 | 8 added | quiet |
| 2026-11-19 | `remote/com.vet402/vet402` | 2026-11-17T234348245249 -> 2026-11-19T231834454605 | 5 changed (every tool) | quiet |
| 2026-11-19 | `remote/ru.vargov/vargov-design` | 2026-11-19T135851736672 -> 2026-11-19T231832927046 | 2 changed | quiet |
| 2026-11-19 | `remote/dev.vetagent/vetagent` | 2026-11-19T162445834406 -> 2026-11-19T231833478214 | 1 changed | quiet |
| 2026-11-19 | `remote/com.tronrelic/mcp` | 2026-11-19T123653265075 -> 2026-11-19T231833011552 | 1 changed | quiet |
| 2026-11-19 | `remote/com.aguasto.www/tools` | 2026-11-19T123650009741 -> 2026-11-19T231833109149 | 1 changed | quiet |
| 2026-11-19 | `remote/coach.upskill/agent-coach` | 2026-11-19T123852051424 -> 2026-11-19T231831965273 | 1 changed | quiet |
| 2026-11-19 | `remote/net.setget/setget` | 2026-11-19T123510934663 -> 2026-11-19T231831746296 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.SeoScoreAPI/seoscoreapi-mcp` | 2026-11-18T161337394819 -> 2026-11-19T231830980383 | 3 changed, 1 added | review |
| 2026-11-19 | `remote/io.github.cryptoconspiracy/vurto-swap` | 2026-11-19T123601078472 -> 2026-11-19T231828747915 | 1 changed | review |
| 2026-11-19 | `remote/io.github.MsingathiM/swapeazi` | 2026-11-19T161920375800 -> 2026-11-19T231829304265 | 1 changed, 1 added | quiet |
| 2026-11-19 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-19T123759877205 -> 2026-11-19T231827642539 | 1 changed | quiet |
| 2026-11-19 | `remote/fyi.smartfin/smartfin` | 2026-11-17T164416642319 -> 2026-11-19T231826550796 | 1 changed | quiet |
| 2026-11-19 | `remote/com.swellcabin/surf` | 2026-11-19T135844225401 -> 2026-11-19T231825859776 | 1 changed | quiet |
| 2026-11-19 | `remote/com.radarbg/radar-tools` | 2026-11-19T020432187957 -> 2026-11-19T231827725529 | 31 added | review |
| 2026-11-19 | `remote/com.idosgames/platform` | 2026-11-19T123526333410 -> 2026-11-19T231827491469 | 1 changed | quiet |
| 2026-11-19 | `remote/com.qrcodedinosaur/qr-codes` | 2026-11-19T123401397020 -> 2026-11-19T231825941432 | 1 changed | quiet |
| 2026-11-19 | `remote/com.achivx/stablescan` | 2026-11-19T123715361333 -> 2026-11-19T231826066879 | 1 changed | quiet |
| 2026-11-19 | `remote/ai.stablenews/news` | 2026-11-17T164631272950 -> 2026-11-19T231824960266 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-19T162246264461 -> 2026-11-19T231823893375 | 1 changed | quiet |
| 2026-11-19 | `remote/finance.souvenir/coins` | 2026-11-19T123705177814 -> 2026-11-19T231824577163 | 5 changed | quiet |
| 2026-11-19 | `remote/com.lvl2player/sandbox` | 2026-11-19T161801021720 -> 2026-11-19T231824680291 | 3 changed | quiet |
| 2026-11-19 | `remote/ai.satohub/onchain-agents` | 2026-11-18T135347862466 -> 2026-11-19T231823770819 | 3 changed | quiet |
| 2026-11-19 | `remote/io.github.joseanu/presupuestos-red` | 2026-11-19T135838820016 -> 2026-11-19T231824692039 | 2 changed, 3 added | quiet |
| 2026-11-19 | `remote/io.github.QDThead/signal-lab` | 2026-11-19T020327015168 -> 2026-11-19T231822751374 | 27 changed (every tool) | quiet |
| 2026-11-19 | `remote/app.lovable.privacy-pill-consent-studio/privacypill` | 2026-11-18T080151749888 -> 2026-11-19T231826297553 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.Playpowerpolitics/powerplayers` | 2026-11-19T135837099646 -> 2026-11-19T231822621175 | 2 changed, 1 added | quiet |
| 2026-11-19 | `remote/app.sunsetstrip/gta6` | 2026-11-19T123446125878 -> 2026-11-19T231822442938 | 3 changed, 1 added | review |
| 2026-11-19 | `remote/io.github.codytodd-ui/pitchspark` | 2026-11-19T161852851175 -> 2026-11-19T231821972354 | 2 changed | quiet |
| 2026-11-19 | `remote/com.photoprintagent/mcp` | 2026-11-17T164310556892 -> 2026-11-19T231821461527 | 1 changed, 1 added, 1 removed | quiet |
| 2026-11-19 | `remote/fr.scorelook/capucine` | 2026-11-18T135530677022 -> 2026-11-19T231820612949 | 1 changed, 1 added | quiet |
| 2026-11-19 | `remote/com.seeksat/seeksat` | 2026-11-19T123620355887 -> 2026-11-19T231819944715 | 8 changed, 4 added, 3 removed (every tool) | quiet |
| 2026-11-19 | `remote/com.ordkort/ordkort` | 2026-11-19T123304004157 -> 2026-11-19T231819856186 | 1 changed | quiet |
| 2026-11-19 | `remote/org.evebrief.oracle/risk-check` | 2026-11-19T161822018060 -> 2026-11-19T231820337817 | 2 changed | quiet |
| 2026-11-19 | `remote/com.roadcutco/roadcut` | 2026-11-19T123544221307 -> 2026-11-19T231819409893 | 1 changed | quiet |
| 2026-11-19 | `remote/com.postthisdeal/handpicked-deals` | 2026-11-19T020336701586 -> 2026-11-19T231820879890 | 1 added | quiet |
| 2026-11-19 | `remote/com.postalref/postalref` | 2026-11-17T135610425670 -> 2026-11-19T231821955511 | 1 changed, 2 added, 4 removed | quiet |
| 2026-11-19 | `remote/io.github.LusoCryptoLabs/ckb-pulse` | 2026-11-19T135840113958 -> 2026-11-19T231821403224 | 1 added | quiet |
| 2026-11-19 | `remote/io.ddx.pg/archive` | 2026-11-19T020333776936 -> 2026-11-19T231818581320 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 75879 substantive, 41001 that changed only numbers (a catalogue counter ticking, a date), 1112 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 63683 | 25330 | 38353 | 0 |
| `a2awire.com` | 3438 | 3438 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 477 | 477 | 0 | 0 |
| `modevc.com` | 392 | 392 | 0 | 0 |
| `civai.co` | 369 | 369 | 0 | 0 |
| `revmesh2074.workers.dev` | 330 | 285 | 45 | 0 |
| `sistaminuten.se` | 259 | 6 | 0 | 253 |
| `afbudsrejser.dk` | 258 | 6 | 0 | 252 |
| `akkilahdot.fi` | 258 | 6 | 0 | 252 |
| `restplass.no` | 258 | 6 | 0 | 252 |
| `socialloop.ai` | 249 | 249 | 0 | 0 |
| 10377 other operators | 45680 | 42974 | 2603 | 103 |
