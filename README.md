# MCP server tool changes

Last change observed 2026-10-25T05:23:03+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

47594 changes to a tool definition: 2087 npm releases (1841 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 45507 readings of hosted servers that found their tools changed; 2480 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-25 | `remote/io.github.eamwhite1/xrpl-referee` | 2026-10-24T224652156832 -> 2026-10-25T052304569005 | 12 changed, 2 added | review |
| 2026-10-25 | `remote/com.zinvyl/marketplace` | 2026-10-24T113103919985 -> 2026-10-25T052305112160 | 8 changed | quiet |
| 2026-10-25 | `remote/studio.gradients/mcp` | 2026-10-24T224631389507 -> 2026-10-25T052303646928 | 1 changed | quiet |
| 2026-10-25 | `remote/io.taifoon/coordination-layer.1` | 2026-10-24T190428356416 -> 2026-10-25T052303266733 | 1 changed | review |
| 2026-10-25 | `remote/se.sistaminuten/travel-search` | 2026-10-24T224650501068 -> 2026-10-25T052304004614 | 1 changed | quiet |
| 2026-10-25 | `remote/no.restplass/travel-search` | 2026-10-24T224632652633 -> 2026-10-25T052303839958 | 1 changed | quiet |
| 2026-10-25 | `remote/fi.akkilahdot/travel-search` | 2026-10-24T224630716122 -> 2026-10-25T052302556033 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.CodeWever/wever-labs-products` | 2026-10-24T050526925867 -> 2026-10-25T052301574689 | 2 changed | quiet |
| 2026-10-25 | `remote/io.github.cryptoduke01/gloam` | 2026-10-23T120643404378 -> 2026-10-25T052301702090 | 5 changed | quiet |
| 2026-10-25 | `remote/com.meridiandispatch/travel-guides` | 2026-10-24T190418411592 -> 2026-10-25T052302343003 | 7 changed | quiet |
| 2026-10-25 | `remote/com.ferntool/ip` | 2026-10-24T050516076202 -> 2026-10-25T052300353320 | 1 added | quiet |
| 2026-10-25 | `remote/gg.unicum/wot-stats` | 2026-10-23T200850648118 -> 2026-10-25T052300350674 | 1 added | quiet |
| 2026-10-25 | `remote/dk.afbudsrejser/travel-search` | 2026-10-24T224631672260 -> 2026-10-25T052300406873 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.eamwhite1/agent-trust` | 2026-10-24T224638388688 -> 2026-10-25T052258299269 | 12 changed, 2 added | review |
| 2026-10-25 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-24T125827676566 -> 2026-10-25T052258693861 | 1 changed | quiet |
| 2026-10-25 | `remote/com.theagentsindex/mcp` | 2026-10-24T050524540379 -> 2026-10-25T052258583469 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.intoApex/tradingagentstack` | 2026-10-23T135202695259 -> 2026-10-25T052256714092 | 1 added | quiet |
| 2026-10-25 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-10-24T190429723603 -> 2026-10-25T052258508003 | 2 changed | quiet |
| 2026-10-25 | `remote/io.github.LE-VAI/designesy-org` | 2026-10-24T224637245545 -> 2026-10-25T052257784749 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-24T224623929002 -> 2026-10-25T052256454699 | 1 changed | quiet |
| 2026-10-25 | `remote/com.swarmmemo/bulletin.1` | 2026-10-24T112908346500 -> 2026-10-25T052257415633 | 2 changed | quiet |
| 2026-10-25 | `remote/com.swarmmemo/bulletin` | 2026-10-24T112908038284 -> 2026-10-25T052257102206 | 1 changed | quiet |
| 2026-10-25 | `remote/ai.trydock/dock` | 2026-10-24T112950829888 -> 2026-10-25T052256456529 | 1 changed | quiet |
| 2026-10-25 | `remote/fr.synergieloc/immobilier` | 2026-10-24T112918427299 -> 2026-10-25T052256724706 | 20 added | quiet |
| 2026-10-25 | `remote/com.thefomite/fomite` | 2026-10-24T050511253732 -> 2026-10-25T052255664696 | 1 changed | quiet |
| 2026-10-25 | `remote/com.tektolo/rental-property` | 2026-10-23T233423898509 -> 2026-10-25T052254726681 | 4 changed | quiet |
| 2026-10-25 | `remote/com.tektolo/capabilities` | 2026-10-23T233424298041 -> 2026-10-25T052254183621 | 4 changed | quiet |
| 2026-10-25 | `remote/com.stockcake/stockcake` | 2026-10-23T120451657592 -> 2026-10-25T052254282972 | 1 changed | quiet |
| 2026-10-25 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-24T050515093392 -> 2026-10-25T052253609167 | 1 changed | quiet |
| 2026-10-25 | `remote/io.songlinks/songlinks` | 2026-10-24T112743318620 -> 2026-10-25T052253782345 | 1 changed | quiet |
| 2026-10-25 | `remote/com.remoshift/jobs` | 2026-10-24T224622066043 -> 2026-10-25T052253928908 | 1 changed | quiet |
| 2026-10-25 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-24T224625622584 -> 2026-10-25T052253080115 | 10 changed | quiet |
| 2026-10-25 | `remote/ai.spelunking/hub` | 2026-10-24T190410867747 -> 2026-10-25T052254835421 | 1 changed | quiet |
| 2026-10-25 | `remote/ai.sfomo/events` | 2026-10-23T233421225276 -> 2026-10-25T052252613688 | 3 changed | quiet |
| 2026-10-25 | `remote/me.phor/phorme-training` | 2026-10-24T112723290088 -> 2026-10-25T052251021014 | 3 changed | quiet |
| 2026-10-25 | `remote/io.github.samuelzcom/chauffeur-booking` | 2026-10-24T112549930392 -> 2026-10-25T052250812741 | 1 changed | quiet |
| 2026-10-25 | `remote/com.odilelabs/odile` | 2026-10-24T125815026811 -> 2026-10-25T052249868799 | 4 changed, 1 added | review |
| 2026-10-25 | `remote/co.civai.nova/support-agent-admin` | 2026-10-24T224621156653 -> 2026-10-25T052249937838 | 2 removed | quiet |
| 2026-10-25 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-10-24T224616378123 -> 2026-10-25T052248947590 | 5 removed | quiet |
| 2026-10-25 | `remote/com.widely-mobile/widely` | 2026-10-23T120419686182 -> 2026-10-25T052248742339 | 4 changed | quiet |
| 2026-10-25 | `remote/com.multicinesortega/cartelera` | 2026-10-24T224616775895 -> 2026-10-25T052250090701 | 1 changed | quiet |
| 2026-10-25 | `remote/org.newmexicoliteracyproject/nmlp-mcp` | 2026-10-23T120258044860 -> 2026-10-25T052247391886 | 1 changed | quiet |
| 2026-10-25 | `remote/app.toolsnap/toolsnap-mcp` | 2026-10-24T050503445890 -> 2026-10-25T052247227166 | 6 changed | review |
| 2026-10-25 | `remote/ai.switchapp/switch` | 2026-10-24T050510587918 -> 2026-10-25T052246389565 | 1 changed, 3 added | quiet |
| 2026-10-25 | `remote/ai.skuit/catalog` | 2026-10-24T190400390745 -> 2026-10-25T052245956965 | 1 changed | quiet |
| 2026-10-25 | `remote/com.sportstatsapi/sports-data` | 2026-10-24T224616597180 -> 2026-10-25T052246076381 | 2 added | quiet |
| 2026-10-25 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-10-24T190358737985 -> 2026-10-25T052244149949 | 2 changed | quiet |
| 2026-10-25 | `remote/io.github.chrisryugj/korean-law-mcp` | 2026-10-24T112429038631 -> 2026-10-25T052245239808 | 10 changed (every tool) | quiet |
| 2026-10-25 | `remote/io.github.Kindora-PBC/foundation-discovery` | 2026-10-23T200805826172 -> 2026-10-25T052244347412 | 1 changed | quiet |
| 2026-10-25 | `remote/com.kernelcad/kernelcad` | 2026-10-24T112451284371 -> 2026-10-25T052245135295 | 1 changed | quiet |
| 2026-10-25 | `remote/com.jojapi/sms-verify` | 2026-10-24T112400051871 -> 2026-10-25T052246942789 | 1 changed | quiet |
| 2026-10-25 | `remote/com.thaifishsashimicatalog/fish-market` | 2026-10-24T190358040134 -> 2026-10-25T052243761269 | 7 changed, 3 removed | quiet |
| 2026-10-25 | `remote/com.getgovinbox/govinbox` | 2026-10-24T112424547981 -> 2026-10-25T052243802609 | 8 changed, 1 added | quiet |
| 2026-10-25 | `remote/com.movingplace/mcp` | 2026-10-24T224612496916 -> 2026-10-25T052242592953 | 16 removed | quiet |
| 2026-10-25 | `remote/com.convertlyft/convertlyft` | 2026-10-24T224610829049 -> 2026-10-25T052242792298 | 1 changed | quiet |
| 2026-10-25 | `remote/tech.kaiku/kaiku.1` | 2026-10-24T190400862233 -> 2026-10-25T052242942645 | 1 added | quiet |
| 2026-10-25 | `remote/io.github.jasp402/hypercodemotion-mcp` | 2026-10-24T224611749627 -> 2026-10-25T052242360151 | 1 added | quiet |
| 2026-10-25 | `remote/net.hotelrefund/price-tracker` | 2026-10-24T050459672743 -> 2026-10-25T052239493299 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.peter120525-cmd/lawmadi-os` | 2026-10-24T190351199882 -> 2026-10-25T052241477747 | 1 changed | quiet |
| 2026-10-25 | `remote/co.ainumbers/tools` | 2026-10-24T112211289157 -> 2026-10-25T052240669878 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 29565 substantive, 17406 that changed only numbers (a catalogue counter ticking, a date), 623 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 25144 | 8777 | 16367 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 659 | 659 | 0 | 0 |
| `caseyjhand.com` | 200 | 200 | 0 | 0 |
| `sistaminuten.se` | 148 | 4 | 0 | 144 |
| `afbudsrejser.dk` | 147 | 4 | 0 | 143 |
| `akkilahdot.fi` | 147 | 4 | 0 | 143 |
| `restplass.no` | 147 | 4 | 0 | 143 |
| `socialloop.ai` | 143 | 143 | 0 | 0 |
| `remoshift.com` | 117 | 8 | 109 | 0 |
| `fundinglandscape.com` | 112 | 72 | 40 | 0 |
| `openkrill.app` | 111 | 111 | 0 | 0 |
| 5473 other operators | 18178 | 17238 | 890 | 50 |
