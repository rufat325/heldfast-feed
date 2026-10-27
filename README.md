# MCP server tool changes

Last change observed 2026-10-27T14:59:26+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

55554 changes to a tool definition: 2384 npm releases (2138 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 53170 readings of hosted servers that found their tools changed; 2828 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-27 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-10-27T112417817131 -> 2026-10-27T145928035689 | 1 changed | quiet |
| 2026-10-27 | `remote/se.sistaminuten/travel-search` | 2026-10-27T124543672677 -> 2026-10-27T145925327113 | 2 changed (every tool) | quiet |
| 2026-10-27 | `remote/io.kolmo.www/kolmo-mcp-server` | 2026-10-27T112348621966 -> 2026-10-27T145921161218 | 1 changed | quiet |
| 2026-10-27 | `remote/xyz.urbangametheory/urban-game-theory` | 2026-10-27T112239202281 -> 2026-10-27T145914096124 | 2 changed, 2 added | quiet |
| 2026-10-27 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-10-27T112605063614 -> 2026-10-27T145913159587 | 1 changed | quiet |
| 2026-10-27 | `remote/no.restplass/travel-search` | 2026-10-27T124244328265 -> 2026-10-27T145910603890 | 2 changed (every tool) | quiet |
| 2026-10-27 | `remote/dk.afbudsrejser/travel-search` | 2026-10-27T124207580093 -> 2026-10-27T145907085269 | 2 changed (every tool) | quiet |
| 2026-10-27 | `remote/eu.surfbooking/surfbooking` | 2026-10-26T133721865637 -> 2026-10-27T145904517143 | 2 changed | quiet |
| 2026-10-27 | `remote/com.zinvyl/marketplace` | 2026-10-27T112308756473 -> 2026-10-27T145905673499 | 13 changed | quiet |
| 2026-10-27 | `remote/nl.prijsprofeet/prijsprofeet-be` | 2026-10-26T133707535000 -> 2026-10-27T145904553179 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.Ockram4444/agentcompute` | 2026-10-27T124132489515 -> 2026-10-27T145903554815 | 1 changed | quiet |
| 2026-10-27 | `remote/dev.tanod/docs` | 2026-10-25T102350095225 -> 2026-10-27T145901385785 | 1 changed | quiet |
| 2026-10-27 | `remote/dev.tanod/tanod` | 2026-10-27T054050940545 -> 2026-10-27T145901152915 | 7 changed, 3 added | quiet |
| 2026-10-27 | `remote/dev.tanod/agents` | 2026-10-25T102349862586 -> 2026-10-27T145901311199 | 5 changed, 1 added | quiet |
| 2026-10-27 | `remote/ai.1court.state/court-directory` | 2026-10-27T054053996928 -> 2026-10-27T145855856831 | 2 changed | quiet |
| 2026-10-27 | `remote/watch.pcprice/used-prices` | 2026-10-26T133551520255 -> 2026-10-27T145855849708 | 2 changed | quiet |
| 2026-10-27 | `remote/dev.upfork/upfork` | 2026-10-27T112312714545 -> 2026-10-27T145855856662 | 4 changed | quiet |
| 2026-10-27 | `remote/com.skyandsigns/mcp` | 2026-10-26T133644770846 -> 2026-10-27T145855516495 | 8 changed (every tool) | quiet |
| 2026-10-27 | `remote/studio.gradients/mcp` | 2026-10-27T124301438327 -> 2026-10-27T145853669856 | 1 changed | quiet |
| 2026-10-27 | `remote/fi.akkilahdot/travel-search` | 2026-10-27T124237977761 -> 2026-10-27T145850087403 | 2 changed (every tool) | quiet |
| 2026-10-27 | `remote/io.github.SecondShotAI/verifylite` | 2026-10-26T133435075840 -> 2026-10-27T145845813468 | 2 added | quiet |
| 2026-10-27 | `remote/com.redocly/mcp` | 2026-10-26T133600040679 -> 2026-10-27T145849749553 | 1 changed | quiet |
| 2026-10-27 | `remote/gg.unicum/wot-stats` | 2026-10-26T052334538344 -> 2026-10-27T145845094234 | 1 added | quiet |
| 2026-10-27 | `remote/dev.workers.quynguyenbac.quickbuild/agent-tools` | 2026-10-26T133408364645 -> 2026-10-27T145840828155 | 1 added | quiet |
| 2026-10-27 | `remote/io.github.jakegallen/poascan` | 2026-10-26T211451530999 -> 2026-10-27T145838945860 | 1 added | quiet |
| 2026-10-27 | `remote/io.github.Fizzl13/presign-guard` | 2026-10-27T112144840721 -> 2026-10-27T145839786002 | 5 changed | quiet |
| 2026-10-27 | `remote/com.stayotter/stay-otter` | 2026-10-26T211457307593 -> 2026-10-27T145837314828 | 1 changed | quiet |
| 2026-10-27 | `remote/com.partstable/partstable` | 2026-10-26T133334520643 -> 2026-10-27T145837832057 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-27T112045262423 -> 2026-10-27T145835141929 | 1 changed | quiet |
| 2026-10-27 | `remote/com.redstonemarkets/redstone` | 2026-10-26T133344863567 -> 2026-10-27T145834910598 | 4 changed, 2 added (every tool) | quiet |
| 2026-10-27 | `remote/fr.menageparfait/booking` | 2026-10-27T112027863976 -> 2026-10-27T145832243743 | 2 changed | quiet |
| 2026-10-27 | `remote/ai.agentlookups/counterscript` | 2026-10-27T112010929116 -> 2026-10-27T145829900802 | 1 changed | quiet |
| 2026-10-27 | `remote/com.remoshift/jobs` | 2026-10-27T123958233587 -> 2026-10-27T145828492743 | 1 changed | quiet |
| 2026-10-27 | `remote/org.r3js/r3` | 2026-10-27T111928414784 -> 2026-10-27T145828205037 | 2 changed | quiet |
| 2026-10-27 | `remote/io.github.Civops-Platform/open-signals` | 2026-10-27T123850482050 -> 2026-10-27T145820884795 | 1 changed | quiet |
| 2026-10-27 | `remote/de.morgenhimmel/mcp` | 2026-10-26T133211949678 -> 2026-10-27T145821757763 | 8 changed (every tool) | quiet |
| 2026-10-27 | `remote/world.tokenbank/tokenbank` | 2026-10-25T102114707385 -> 2026-10-27T145818107111 | 1 changed | quiet |
| 2026-10-27 | `remote/ca.movahedi/privacy` | 2026-10-26T133056971253 -> 2026-10-27T145817199391 | 1 changed | quiet |
| 2026-10-27 | `remote/ai.sitectrl/sitectrl` | 2026-10-27T123816263314 -> 2026-10-27T145815841575 | 2 changed, 1 added | quiet |
| 2026-10-27 | `remote/io.github.minsooparkk/korea-tax-law-mcp` | 2026-10-25T102452537819 -> 2026-10-27T145815234061 | 1 changed | quiet |
| 2026-10-27 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-10-26T153126677240 -> 2026-10-27T145814165293 | 2 added | review |
| 2026-10-27 | `remote/io.github.TSavo/swapchan` | 2026-10-27T054049575970 -> 2026-10-27T145813416182 | 5 added | quiet |
| 2026-10-27 | `remote/za.co.theahg/ahg-archives` | 2026-10-27T111758239183 -> 2026-10-27T145811007746 | 16 changed (every tool) | quiet |
| 2026-10-27 | `remote/com.socialseal/mcp` | 2026-10-27T054039797248 -> 2026-10-27T145808220924 | 2 changed | quiet |
| 2026-10-27 | `remote/com.movingplace/mcp` | 2026-10-27T111717718548 -> 2026-10-27T145808758477 | 16 added | quiet |
| 2026-10-27 | `remote/com.jojapi/product-barcode-api` | 2026-10-27T111658568763 -> 2026-10-27T145806230234 | 1 changed | quiet |
| 2026-10-27 | `remote/com.ellomind/therapy-booking` | 2026-10-27T123548387768 -> 2026-10-27T145801152629 | 2 changed | quiet |
| 2026-10-27 | `remote/app.genmc/genmc` | 2026-10-27T111519396845 -> 2026-10-27T145757908435 | 4 changed (every tool) | quiet |
| 2026-10-27 | `remote/io.github.industrial-platform-ai/research-brief` | 2026-10-27T123514330442 -> 2026-10-27T145806908224 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.geter-andru/andru-intelligence` | 2026-10-26T132736412600 -> 2026-10-27T145755464192 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.geter-andru/andru-intelligence.1` | 2026-10-26T132719346121 -> 2026-10-27T145753584852 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.wellknownmcp/ia-asso` | 2026-10-27T123418648153 -> 2026-10-27T145754294405 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt.2` | 2026-10-27T111320266720 -> 2026-10-27T145752173152 | 4 changed | quiet |
| 2026-10-27 | `remote/io.github.jamie7893/keelen` | 2026-10-27T054018463035 -> 2026-10-27T145749406927 | 2 changed | quiet |
| 2026-10-27 | `remote/co.homemaster/homemaster` | 2026-10-26T211413812604 -> 2026-10-27T145752467679 | 1 changed | quiet |
| 2026-10-27 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-27T111231908836 -> 2026-10-27T145745170654 | 1 changed | quiet |
| 2026-10-27 | `remote/com.getaroundhongkong/trip-planner` | 2026-10-25T101841389007 -> 2026-10-27T145745494464 | 1 changed | quiet |
| 2026-10-27 | `remote/pro.horustek/horus-flow-mcp` | 2026-10-27T111223696992 -> 2026-10-27T145744281060 | 1 added | quiet |
| 2026-10-27 | `remote/lu.chathome/chathome` | 2026-10-26T132349052077 -> 2026-10-27T145743039986 | 8 changed, 4 added | quiet |
| 2026-10-27 | `remote/io.github.edtool79-collab/hirepulse-gateway` | 2026-10-27T123213159984 -> 2026-10-27T145741915848 | 8 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 35433 substantive, 19442 that changed only numbers (a catalogue counter ticking, a date), 679 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 30394 | 12161 | 18233 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 891 | 891 | 0 | 0 |
| `caseyjhand.com` | 238 | 238 | 0 | 0 |
| `sistaminuten.se` | 161 | 5 | 0 | 156 |
| `afbudsrejser.dk` | 160 | 5 | 0 | 155 |
| `akkilahdot.fi` | 160 | 5 | 0 | 155 |
| `restplass.no` | 160 | 5 | 0 | 155 |
| `socialloop.ai` | 154 | 154 | 0 | 0 |
| `remoshift.com` | 130 | 8 | 122 | 0 |
| `revmesh2074.workers.dev` | 129 | 116 | 13 | 0 |
| `fundinglandscape.com` | 123 | 78 | 45 | 0 |
| 6080 other operators | 20513 | 19426 | 1029 | 58 |
