# MCP server tool changes

Last change observed 2026-10-20T05:25:19+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

35336 changes to a tool definition: 1387 npm releases (1141 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 33949 readings of hosted servers that found their tools changed; 2213 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-20 | `remote/io.sigmaprep/worksheets` | 2026-10-19T135606962228 -> 2026-10-20T052527371936 | 2 changed (every tool) | quiet |
| 2026-10-20 | `remote/io.peakcam/snow` | 2026-10-19T135601257197 -> 2026-10-20T052528354071 | 5 changed, 6 added | quiet |
| 2026-10-20 | `remote/io.github.kirupa/kirupa` | 2026-10-19T135554920386 -> 2026-10-20T052514792653 | 1 changed | quiet |
| 2026-10-20 | `remote/studio.gradients/mcp` | 2026-10-19T212020481999 -> 2026-10-20T052519685469 | 3 changed (every tool) | quiet |
| 2026-10-20 | `remote/io.github.EasyGerber/easygerber` | 2026-10-19T135539984189 -> 2026-10-20T052509867571 | 2 changed | quiet |
| 2026-10-20 | `remote/fi.akkilahdot/travel-search` | 2026-10-19T212015581205 -> 2026-10-20T052511183752 | 1 changed | quiet |
| 2026-10-20 | `remote/io.soundchain/agents` | 2026-10-19T135512084551 -> 2026-10-20T052506306270 | 4 added | quiet |
| 2026-10-20 | `remote/com.transitmcp/transit-mcp` | 2026-10-19T212000443106 -> 2026-10-20T052446061544 | 5 changed | quiet |
| 2026-10-20 | `remote/io.github.ak10082247-max/stealthguard-402` | 2026-10-19T135357269902 -> 2026-10-20T052434096065 | 15 changed (every tool) | quiet |
| 2026-10-20 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-19T211941384655 -> 2026-10-20T052437574278 | 1 changed | quiet |
| 2026-10-20 | `remote/com.spectacularatlas/events` | 2026-10-19T135347908985 -> 2026-10-20T052429265205 | 2 changed | quiet |
| 2026-10-20 | `remote/com.remoshift/jobs` | 2026-10-19T211929255832 -> 2026-10-20T052418988706 | 1 changed | quiet |
| 2026-10-20 | `remote/com.neblla/neblla` | 2026-10-19T211902721932 -> 2026-10-20T052403456295 | 13 changed, 2 added | quiet |
| 2026-10-20 | `remote/com.multicinesortega/cartelera` | 2026-10-19T211902129587 -> 2026-10-20T052404455609 | 1 changed | quiet |
| 2026-10-20 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-10-19T135910097767 -> 2026-10-20T052358528231 | 45 changed (every tool) | quiet |
| 2026-10-20 | `remote/no.restplass/travel-search` | 2026-10-19T212029390107 -> 2026-10-20T052357561715 | 1 changed | quiet |
| 2026-10-20 | `remote/dk.afbudsrejser/travel-search` | 2026-10-19T212016451965 -> 2026-10-20T052352263826 | 1 changed | quiet |
| 2026-10-20 | `remote/com.widewired/wwnet.1` | 2026-10-19T135822620416 -> 2026-10-20T052353978258 | 1 changed | quiet |
| 2026-10-20 | `remote/com.widewired/wwnet` | 2026-10-19T135820692172 -> 2026-10-20T052354433294 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.jukky-source/wealth-agent` | 2026-10-19T135808786082 -> 2026-10-20T052348909541 | 1 changed, 2 added | quiet |
| 2026-10-20 | `remote/com.servereel/servereel-mcp` | 2026-10-19T135021734767 -> 2026-10-20T052349255523 | 1 changed | quiet |
| 2026-10-20 | `remote/uk.co.ukchargingsolutions/ev-charging` | 2026-10-19T135743573091 -> 2026-10-20T052345773581 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.VoiceScapee/voicescape` | 2026-10-19T135803006551 -> 2026-10-20T052346832474 | 2 added | quiet |
| 2026-10-20 | `remote/com.veritaset/mcp` | 2026-10-19T212007217281 -> 2026-10-20T052347042145 | 1 changed, 1 added | quiet |
| 2026-10-20 | `remote/com.tulugar/tulugar` | 2026-10-19T135740725590 -> 2026-10-20T052345308692 | 1 changed | quiet |
| 2026-10-20 | `remote/ai.trydock/dock` | 2026-10-18T190033204556 -> 2026-10-20T052344238452 | 8 changed | quiet |
| 2026-10-20 | `remote/com.auto-units/auto-message` | 2026-10-19T135714463826 -> 2026-10-20T052342229684 | 1 changed | quiet |
| 2026-10-20 | `remote/com.jobmojito/jobmojito` | 2026-10-19T052359660050 -> 2026-10-20T052343481981 | 2 added | quiet |
| 2026-10-20 | `remote/com.formada3d/mcp` | 2026-10-19T134852874703 -> 2026-10-20T052338279742 | 2 changed | quiet |
| 2026-10-20 | `remote/io.github.Timothymycompc/solana-pulse-gateway` | 2026-10-19T160047204648 -> 2026-10-20T052337185539 | 2 changed | quiet |
| 2026-10-20 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-10-19T135524331149 -> 2026-10-20T052336427431 | 45 changed (every tool) | quiet |
| 2026-10-20 | `remote/io.github.daniel3303/equibles` | 2026-10-19T052355125309 -> 2026-10-20T052337570403 | 3 changed | quiet |
| 2026-10-20 | `remote/com.veridionmarkets/disclosures` | 2026-10-19T212039958066 -> 2026-10-20T052335651627 | 1 changed | quiet |
| 2026-10-20 | `remote/pro.sebbi/governance` | 2026-10-18T223949968194 -> 2026-10-20T052334678386 | 1 changed | quiet |
| 2026-10-20 | `remote/io.taifoon/coordination-layer.1` | 2026-10-19T212038083221 -> 2026-10-20T052333755770 | 1 changed | review |
| 2026-10-20 | `remote/pro.aicut/aicut` | 2026-10-19T155556898433 -> 2026-10-20T052345370142 | 1 changed, 1 added | quiet |
| 2026-10-20 | `remote/com.scanverity/resolution-rules` | 2026-10-18T113159325078 -> 2026-10-20T052334300838 | 2 changed | quiet |
| 2026-10-20 | `remote/se.sistaminuten/travel-search` | 2026-10-19T212037596516 -> 2026-10-20T052332512571 | 1 changed | quiet |
| 2026-10-20 | `remote/land.fabrica/mcp-testnet` | 2026-10-18T051256712189 -> 2026-10-20T052333100847 | 1 changed, 24 added, 24 removed | quiet |
| 2026-10-20 | `remote/ai.rokha/rokha` | 2026-10-19T052411873008 -> 2026-10-20T052332383955 | 1 changed | quiet |
| 2026-10-20 | `remote/co.getclippy/clippy` | 2026-10-19T211816454714 -> 2026-10-20T052331919905 | 5 changed (every tool) | quiet |
| 2026-10-20 | `remote/com.ferntool/ip` | 2026-10-19T135450273974 -> 2026-10-20T052329063693 | 1 added | quiet |
| 2026-10-20 | `remote/fun.pumpdata/pumpdata` | 2026-10-19T135531475828 -> 2026-10-20T052328322675 | 1 changed | quiet |
| 2026-10-20 | `remote/io.github.Fizzl13/presign-guard` | 2026-10-19T211928994832 -> 2026-10-20T052327047741 | 3 changed | quiet |
| 2026-10-20 | `remote/com.youspot/youspot` | 2026-10-19T212024611659 -> 2026-10-20T052321678721 | 1 changed | quiet |
| 2026-10-20 | `remote/com.orbylon/readiness` | 2026-10-19T052403854321 -> 2026-10-20T052322545963 | 2 changed | review |
| 2026-10-20 | `remote/com.orbitstudio3d/orbitstudio` | 2026-10-19T135447238848 -> 2026-10-20T052321932368 | 3 changed | quiet |
| 2026-10-20 | `remote/io.github.rezearcher/tech-risk` | 2026-10-19T212022394863 -> 2026-10-20T052320637504 | 1 added | quiet |
| 2026-10-20 | `remote/com.tryalpy/alpy` | 2026-10-19T135348943352 -> 2026-10-20T052320654736 | 3 changed | quiet |
| 2026-10-20 | `remote/com.kineticist/mcp-server` | 2026-10-19T212015660129 -> 2026-10-20T052317758369 | 10 changed (every tool) | quiet |
| 2026-10-20 | `remote/com.yz-cpa/us-tax-estimator` | 2026-10-19T135416388087 -> 2026-10-20T052317530505 | 1 changed | review |
| 2026-10-20 | `remote/com.thefomite/fomite` | 2026-10-19T052411205646 -> 2026-10-20T052317021047 | 1 changed | quiet |
| 2026-10-20 | `remote/how.mise/mise` | 2026-10-19T211911950658 -> 2026-10-20T052317419631 | 22 changed, 2 added (every tool) | quiet |
| 2026-10-20 | `remote/ai.weio/site-check` | 2026-10-19T212009813511 -> 2026-10-20T052314371726 | 2 added, 3 removed | quiet |
| 2026-10-20 | `remote/io.github.sorindecu/vibeshipped` | 2026-10-19T212005902270 -> 2026-10-20T052313178256 | 1 changed, 2 added | quiet |
| 2026-10-20 | `remote/io.github.muaviamohammed/mizan` | 2026-10-19T211959741224 -> 2026-10-20T052315766316 | 1 changed, 1 added | quiet |
| 2026-10-20 | `remote/team.jogo/mcp` | 2026-10-19T134709517077 -> 2026-10-20T052319163783 | 4 changed | quiet |
| 2026-10-20 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-10-19T135135791774 -> 2026-10-20T052311014286 | 2 changed | quiet |
| 2026-10-20 | `remote/org.r3js/r3` | 2026-10-19T155903726006 -> 2026-10-20T052312174016 | 3 changed | quiet |
| 2026-10-20 | `remote/io.github.nickarstrong/isoba` | 2026-10-19T134703509438 -> 2026-10-20T052317585219 | 3 changed, 4 added (every tool) | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 23646 substantive, 11187 that changed only numbers (a catalogue counter ticking, a date), 503 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 17656 | 7224 | 10432 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 166 | 166 | 0 | 0 |
| `sistaminuten.se` | 121 | 4 | 0 | 117 |
| `afbudsrejser.dk` | 120 | 4 | 0 | 116 |
| `akkilahdot.fi` | 120 | 4 | 0 | 116 |
| `restplass.no` | 120 | 4 | 0 | 116 |
| `socialloop.ai` | 117 | 117 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `remoshift.com` | 91 | 6 | 85 | 0 |
| `fundinglandscape.com` | 90 | 57 | 33 | 0 |
| 4443 other operators | 13644 | 12969 | 637 | 38 |
