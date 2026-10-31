# MCP server tool changes

Last change observed 2026-10-31T14:49:18+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

65361 changes to a tool definition: 2775 npm releases (2529 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 62586 readings of hosted servers that found their tools changed; 3096 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-31 | `remote/studio.gradients/mcp` | 2026-10-31T130409944307 -> 2026-10-31T144919375280 | 1 changed | quiet |
| 2026-10-31 | `remote/fi.akkilahdot/travel-search` | 2026-10-31T130345218290 -> 2026-10-31T144918394052 | 1 changed | quiet |
| 2026-10-31 | `remote/no.restplass/travel-search` | 2026-10-31T130252406320 -> 2026-10-31T144916501464 | 1 changed | quiet |
| 2026-10-31 | `remote/se.sistaminuten/travel-search` | 2026-10-31T130312550036 -> 2026-10-31T144915478639 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-31T130239226716 -> 2026-10-31T144912848913 | 1 changed | quiet |
| 2026-10-31 | `remote/xyz.t0ll/toll` | 2026-10-31T130226334160 -> 2026-10-31T144910963268 | 1 added | quiet |
| 2026-10-31 | `remote/eu.madeinro/rotv-mcp` | 2026-10-31T130147131332 -> 2026-10-31T144911721348 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-31T130204146903 -> 2026-10-31T144909279246 | 1 changed | quiet |
| 2026-10-31 | `remote/dk.afbudsrejser/travel-search` | 2026-10-31T130208131631 -> 2026-10-31T144912703987 | 1 changed | quiet |
| 2026-10-31 | `remote/com.vidreno/mcp` | 2026-10-31T130149793028 -> 2026-10-31T144910649252 | 2 changed | quiet |
| 2026-10-31 | `remote/io.github.ohad6k/viberaven-guides` | 2026-10-31T130149361544 -> 2026-10-31T144908553111 | 6 changed (every tool) | quiet |
| 2026-10-31 | `remote/com.remoshift/jobs` | 2026-10-31T130108283646 -> 2026-10-31T144906204940 | 1 changed | quiet |
| 2026-10-31 | `remote/com.radar-cnpj/radar-cnpj` | 2026-10-31T130101640293 -> 2026-10-31T144906630214 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.exquad/thecablecode` | 2026-10-31T130127964516 -> 2026-10-31T144904089077 | 1 changed | quiet |
| 2026-10-31 | `remote/ai.trydock/dock` | 2026-10-30T063138030534 -> 2026-10-31T144904375461 | 2 changed | quiet |
| 2026-10-31 | `remote/sg.tanatasa/tanatasa` | 2026-10-30T063157720621 -> 2026-10-31T144902802621 | 2 changed | quiet |
| 2026-10-31 | `remote/online.pageaudit/pageaudit` | 2026-10-31T130009397790 -> 2026-10-31T144902754883 | 1 changed | quiet |
| 2026-10-31 | `remote/com.odilelabs/odile` | 2026-10-31T062129106840 -> 2026-10-31T144901205471 | 1 changed, 2 added | quiet |
| 2026-10-31 | `remote/fr.synergieloc/immobilier` | 2026-10-31T130022171114 -> 2026-10-31T144901777566 | 6 added | quiet |
| 2026-10-31 | `remote/io.ddx.pg/archive` | 2026-10-29T104151080513 -> 2026-10-31T144900326262 | 1 changed | quiet |
| 2026-10-31 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-10-31T125912594889 -> 2026-10-31T144859210322 | 4 changed, 1 added | quiet |
| 2026-10-31 | `remote/io.github.supplementscanner/scanner` | 2026-10-31T125829464477 -> 2026-10-31T144855941099 | 4 changed (every tool) | quiet |
| 2026-10-31 | `remote/ai.switchapp/switch` | 2026-10-31T062124572563 -> 2026-10-31T144855023365 | 1 changed | quiet |
| 2026-10-31 | `remote/com.ontarioprotocol/ontario-protocol` | 2026-10-30T132545688081 -> 2026-10-31T144850301159 | 6 changed | quiet |
| 2026-10-31 | `remote/com.hireahelper/mcp` | 2026-10-31T062119617918 -> 2026-10-31T144849461304 | 16 added | quiet |
| 2026-10-31 | `remote/com.tkawen/intelligence-gateway` | 2026-10-31T125739244739 -> 2026-10-31T144847539329 | 1 changed | quiet |
| 2026-10-31 | `remote/nl.supplementenscanner/scanner` | 2026-10-31T125733777413 -> 2026-10-31T144846287041 | 4 changed (every tool) | quiet |
| 2026-10-31 | `remote/com.sportstatsapi/sports-data` | 2026-10-30T132411754908 -> 2026-10-31T144845860774 | 1 changed | quiet |
| 2026-10-31 | `remote/com.thefilmradar/filmlab` | 2026-10-31T125523754527 -> 2026-10-31T144845469621 | 1 changed | quiet |
| 2026-10-31 | `remote/com.convertlyft/convertlyft` | 2026-10-30T210549238869 -> 2026-10-31T144844448559 | 1 changed, 1 added | quiet |
| 2026-10-31 | `remote/xyz.cabalspy/wallet-tracker` | 2026-10-31T125519806017 -> 2026-10-31T144844620891 | 1 changed, 3 added | quiet |
| 2026-10-31 | `remote/com.movingplace/mcp` | 2026-10-30T210551933274 -> 2026-10-31T144842655284 | 16 added | quiet |
| 2026-10-31 | `remote/tech.kaiku/kaiku.1` | 2026-10-31T125621458795 -> 2026-10-31T144843484138 | 1 changed | quiet |
| 2026-10-31 | `remote/com.kushbitx/agentproof` | 2026-10-31T125444097002 -> 2026-10-31T144841961949 | 1 changed | quiet |
| 2026-10-31 | `remote/com.genexxis/data-apis` | 2026-10-30T132241075274 -> 2026-10-31T144841191121 | 2 added | quiet |
| 2026-10-31 | `remote/app.frankki/letters` | 2026-10-31T125553600773 -> 2026-10-31T144840705556 | 4 changed (every tool) | quiet |
| 2026-10-31 | `remote/io.agentweather/agent-weather` | 2026-10-29T103648225927 -> 2026-10-31T144838032291 | 1 changed | quiet |
| 2026-10-31 | `remote/com.leadmarina/leadmarina` | 2026-10-31T125421754304 -> 2026-10-31T144837298220 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.wellknownmcp/ia-asso` | 2026-10-29T103641549842 -> 2026-10-31T144836425620 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.horizon-pulse/horizon-pulse` | 2026-10-31T062111578613 -> 2026-10-31T144834208829 | 1 added | quiet |
| 2026-10-31 | `remote/net.gradetv/grade` | 2026-10-31T125300987441 -> 2026-10-31T144833820469 | 1 changed | quiet |
| 2026-10-31 | `remote/app.vercel.fork-for-agents/fork` | 2026-10-31T125220701240 -> 2026-10-31T144833610114 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.uponex/gisgp` | 2026-10-31T125253326048 -> 2026-10-31T144837785774 | 1 changed | quiet |
| 2026-10-31 | `remote/com.howtomakemoneyonsnapchat/creator-monetization` | 2026-10-30T132014061088 -> 2026-10-31T144833584697 | 6 changed | quiet |
| 2026-10-31 | `remote/net.hookpulse/hookpulse` | 2026-10-31T125341199388 -> 2026-10-31T144831956161 | 1 changed | quiet |
| 2026-10-31 | `remote/io.helious/market-intelligence` | 2026-10-31T125333294927 -> 2026-10-31T144831432128 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.edtool79-collab/hirepulse-gateway` | 2026-10-31T125302530013 -> 2026-10-31T144831240846 | 8 changed | quiet |
| 2026-10-31 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-31T125202815112 -> 2026-10-31T144830630951 | 3 changed | quiet |
| 2026-10-31 | `remote/io.github.Timwal78/402proof` | 2026-10-31T125159896116 -> 2026-10-31T144829879074 | 1 changed | quiet |
| 2026-10-31 | `remote/club.elron/public-rentals` | 2026-10-31T125148485722 -> 2026-10-31T144832376945 | 4 changed, 25 added | quiet |
| 2026-10-31 | `remote/com.editalmd/editalmd` | 2026-10-31T125144860891 -> 2026-10-31T144830487372 | 1 changed | quiet |
| 2026-10-31 | `remote/com.directmailamerica/mcp` | 2026-10-31T125128141811 -> 2026-10-31T144828993029 | 1 changed | quiet |
| 2026-10-31 | `remote/ai.emberverse/emberverse` | 2026-10-31T125122536962 -> 2026-10-31T144828229215 | 2 added | quiet |
| 2026-10-31 | `remote/app.web.dealer-direct-mcp/dealer-direct-inventory` | 2026-10-31T125108067326 -> 2026-10-31T144826746864 | 1 changed | quiet |
| 2026-10-31 | `remote/app.sallim/contract-compass` | 2026-10-30T210535148969 -> 2026-10-31T144827227941 | 1 changed | quiet |
| 2026-10-31 | `remote/build.naru/contract-compass` | 2026-10-30T210537635659 -> 2026-10-31T144825542738 | 1 changed | quiet |
| 2026-10-31 | `remote/br.app.classificado/meta-agent-tools` | 2026-10-31T125043322837 -> 2026-10-31T144826735084 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.Devabubakar/atsprep` | 2026-10-30T210529294216 -> 2026-10-31T144821226433 | 4 changed | quiet |
| 2026-10-31 | `remote/ai.zindex/zindex` | 2026-10-29T212748971065 -> 2026-10-31T144820577323 | 5 changed | quiet |
| 2026-10-31 | `remote/com.ufcalendar/fight-api` | 2026-10-30T131515509285 -> 2026-10-31T144819765663 | 5 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 43090 substantive, 21520 that changed only numbers (a catalogue counter ticking, a date), 751 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 35899 | 15834 | 20065 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1127 | 1127 | 0 | 0 |
| `caseyjhand.com` | 287 | 287 | 0 | 0 |
| `sistaminuten.se` | 178 | 6 | 0 | 172 |
| `afbudsrejser.dk` | 177 | 6 | 0 | 171 |
| `akkilahdot.fi` | 177 | 6 | 0 | 171 |
| `restplass.no` | 177 | 6 | 0 | 171 |
| `socialloop.ai` | 171 | 171 | 0 | 0 |
| `remoshift.com` | 147 | 10 | 137 | 0 |
| `revmesh2074.workers.dev` | 144 | 126 | 18 | 0 |
| `fundinglandscape.com` | 136 | 86 | 50 | 0 |
| 6725 other operators | 24400 | 23084 | 1250 | 66 |
