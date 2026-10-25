# MCP server tool changes

Last change observed 2026-10-25T22:51:52+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

50065 changes to a tool definition: 2189 npm releases (1943 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 47876 readings of hosted servers that found their tools changed; 2608 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-25 | `remote/no.restplass/travel-search` | 2026-10-25T191908932059 -> 2026-10-25T225154580282 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.cryptoduke01/gloam` | 2026-10-25T102539370376 -> 2026-10-25T225212344393 | 5 changed | quiet |
| 2026-10-25 | `remote/com.meridiandispatch/travel-guides` | 2026-10-25T132418273731 -> 2026-10-25T225152317350 | 1 changed | quiet |
| 2026-10-25 | `remote/dk.afbudsrejser/travel-search` | 2026-10-25T191907563568 -> 2026-10-25T225151159916 | 1 changed | quiet |
| 2026-10-25 | `remote/fr.synergieloc/immobilier` | 2026-10-25T115728297941 -> 2026-10-25T225144076493 | 6 changed, 49 added | quiet |
| 2026-10-25 | `remote/com.tiamatcrypto.sweetai/agent-intel` | 2026-10-24T224629220620 -> 2026-10-25T225143965163 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-10-23T052625290673 -> 2026-10-25T225143008469 | 46 removed | quiet |
| 2026-10-25 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-25T191858773679 -> 2026-10-25T225139857717 | 10 changed | quiet |
| 2026-10-25 | `remote/com.0xpi.sdsentry/sds-lookup` | 2026-10-24T224623971327 -> 2026-10-25T225137861377 | 1 changed | quiet |
| 2026-10-25 | `remote/com.screenrove/screenrove` | 2026-10-24T112828630990 -> 2026-10-25T225143538368 | 7 changed | quiet |
| 2026-10-25 | `remote/site.chatgpt.orellise.relay-agent-services/relay` | 2026-10-23T120359890263 -> 2026-10-25T225137986127 | 6 changed | quiet |
| 2026-10-25 | `remote/io.github.richardsolomou/praetorium` | 2026-10-25T191853439578 -> 2026-10-25T225135865010 | 2 changed | quiet |
| 2026-10-25 | `remote/io.github.fredxhansson-cmyk/noniner` | 2026-10-25T191849912820 -> 2026-10-25T225132464000 | 5 added | quiet |
| 2026-10-25 | `remote/io.github.smarterweather/weather` | 2026-10-24T190400555631 -> 2026-10-25T225130753099 | 3 changed | quiet |
| 2026-10-25 | `remote/io.echelongraph/echelongraph-mcp` | 2026-10-25T115309935047 -> 2026-10-25T225126601343 | 2 changed | quiet |
| 2026-10-25 | `remote/cc.hlist/hlist-ai-tools` | 2026-10-25T132347764249 -> 2026-10-25T225120116446 | 1 changed | quiet |
| 2026-10-25 | `remote/ai.gethal/mcp` | 2026-10-24T112232493692 -> 2026-10-25T225113502747 | 1 removed | quiet |
| 2026-10-25 | `remote/studio.gradients/mcp` | 2026-10-25T191905616013 -> 2026-10-25T225102454182 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.imokokok/insight-oracle` | 2026-10-25T191906389661 -> 2026-10-25T225103979101 | 1 changed, 4 added | quiet |
| 2026-10-25 | `remote/fi.akkilahdot/travel-search` | 2026-10-25T191903916903 -> 2026-10-25T225101485661 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.paulieb89/uk-due-diligence-mcp` | 2026-10-24T112943996800 -> 2026-10-25T225057815179 | 6 changed | quiet |
| 2026-10-25 | `remote/io.github.fredxhansson-cmyk/fuze` | 2026-10-25T191829002076 -> 2026-10-25T225104456454 | 5 added | quiet |
| 2026-10-25 | `remote/io.github.Val7h/dados-b3` | 2026-10-25T101552617236 -> 2026-10-25T225059119754 | 1 added | review |
| 2026-10-25 | `remote/dev.zambo/zambo` | 2026-10-23T233429565694 -> 2026-10-25T225056675617 | 35 changed (every tool) | quiet |
| 2026-10-25 | `remote/se.sistaminuten/travel-search` | 2026-10-25T191849072785 -> 2026-10-25T225056232420 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.zambodotdev/zambo` | 2026-10-23T233429484692 -> 2026-10-25T225056559373 | 35 changed (every tool) | quiet |
| 2026-10-25 | `remote/io.github.Fizzl13/x402-doctor` | 2026-10-24T190430796525 -> 2026-10-25T225056704548 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-25T191857205645 -> 2026-10-25T225053925394 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-10-25T132435618143 -> 2026-10-25T225054032546 | 2 changed | quiet |
| 2026-10-25 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-25T191847014500 -> 2026-10-25T225052985528 | 3 removed | quiet |
| 2026-10-25 | `remote/com.courtlygo/courts` | 2026-10-25T101544873014 -> 2026-10-25T225052464045 | 3 changed (every tool) | quiet |
| 2026-10-25 | `remote/com.remoshift/jobs` | 2026-10-25T191853120444 -> 2026-10-25T225050700733 | 1 changed | quiet |
| 2026-10-25 | `remote/com.multicinesortega/cartelera` | 2026-10-25T052250090701 -> 2026-10-25T225045716520 | 1 changed | quiet |
| 2026-10-25 | `remote/ca.movahedi/privacy` | 2026-10-25T132408495074 -> 2026-10-25T225044139778 | 9 changed, 2 added (every tool) | quiet |
| 2026-10-25 | `remote/com.idosgames/platform` | 2026-10-24T224624143601 -> 2026-10-25T225044276897 | 27 changed | quiet |
| 2026-10-25 | `remote/com.webinarignition/mcp` | 2026-10-24T224618444190 -> 2026-10-25T225041746294 | 3 changed, 1 added | quiet |
| 2026-10-25 | `remote/com.perfboarddesigner/mcp` | 2026-10-24T112529093656 -> 2026-10-25T225039916066 | 2 changed | quiet |
| 2026-10-25 | `remote/com.pagelemon/pagelemon` | 2026-10-25T191840833582 -> 2026-10-25T225039428390 | 67 changed (every tool) | quiet |
| 2026-10-25 | `remote/com.sportstatsapi/sports-data` | 2026-10-25T191824486126 -> 2026-10-25T225038650484 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.ondraulehla/mcpcost` | 2026-10-24T224618408927 -> 2026-10-25T225037455641 | 4 changed | quiet |
| 2026-10-25 | `remote/tech.kaiku/kaiku.1` | 2026-10-25T191820195979 -> 2026-10-25T225034061864 | 2 changed | quiet |
| 2026-10-25 | `remote/io.github.OptimNow/cloud-finops` | 2026-10-25T102041106522 -> 2026-10-25T225032939087 | 1 added | quiet |
| 2026-10-25 | `remote/ai.tunnelmind/data` | 2026-10-23T052616036877 -> 2026-10-25T225032984261 | 3 changed | quiet |
| 2026-10-25 | `remote/io.github.jamie7893/keelen` | 2026-10-24T190401586657 -> 2026-10-25T225031740817 | 2 changed, 1 added, 2 removed | quiet |
| 2026-10-25 | `remote/io.github.AKzar1el/god-prompt-mcp` | 2026-10-25T191829948207 -> 2026-10-25T225030220146 | 2 changed | quiet |
| 2026-10-25 | `remote/io.github.schneidavie/fund-momentum` | 2026-10-25T101734330208 -> 2026-10-25T225030716151 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.Mironfvjr/br-intelligence` | 2026-10-24T111826004516 -> 2026-10-25T225031536855 | 1 added | quiet |
| 2026-10-25 | `remote/dev.pages.freetier-agent-api/freetier-agent-api` | 2026-10-25T132353253836 -> 2026-10-25T225029934768 | 22 changed, 7 added | review |
| 2026-10-25 | `remote/co.ainumbers/tools` | 2026-10-25T191816475755 -> 2026-10-25T225030630429 | 3 changed | quiet |
| 2026-10-25 | `remote/app.vercel.fork-for-agents/fork` | 2026-10-25T191829017493 -> 2026-10-25T225028939955 | 2 changed | quiet |
| 2026-10-25 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt` | 2026-10-25T052238397042 -> 2026-10-25T225027949479 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.edtool79-collab/hirepulse-gateway` | 2026-10-25T191812591066 -> 2026-10-25T225025895792 | 11 changed | quiet |
| 2026-10-25 | `remote/com.freerateupdate/mortgage-home-equity` | 2026-10-25T101757670107 -> 2026-10-25T225025454849 | 1 added | quiet |
| 2026-10-25 | `remote/express.convert/transcribe` | 2026-10-23T233348429173 -> 2026-10-25T225026014154 | 3 changed | quiet |
| 2026-10-25 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-25T191813607278 -> 2026-10-25T225023541531 | 2 changed | quiet |
| 2026-10-25 | `remote/com.clypmint/clypmint` | 2026-10-24T050455772739 -> 2026-10-25T225022432973 | 1 changed | quiet |
| 2026-10-25 | `remote/io.github.stand-out-of-my-sun/diogenes-gateway` | 2026-10-23T233350219628 -> 2026-10-25T225020882909 | 71 changed, 36 added (every tool) | review |
| 2026-10-25 | `remote/io.github.CacheCarti/dmoera-creator` | 2026-10-24T111909277676 -> 2026-10-25T225022450306 | 4 changed, 15 added | quiet |
| 2026-10-25 | `remote/com.ce-net/ce-net` | 2026-10-25T132342858248 -> 2026-10-25T225022000184 | 26 added | quiet |
| 2026-10-25 | `remote/site.cryptofeed402/feed` | 2026-10-24T224600671336 -> 2026-10-25T225019912252 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 31964 substantive, 17454 that changed only numbers (a catalogue counter ticking, a date), 647 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 26731 | 10363 | 16368 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 775 | 775 | 0 | 0 |
| `caseyjhand.com` | 220 | 220 | 0 | 0 |
| `sistaminuten.se` | 153 | 4 | 0 | 149 |
| `afbudsrejser.dk` | 152 | 4 | 0 | 148 |
| `akkilahdot.fi` | 152 | 4 | 0 | 148 |
| `restplass.no` | 152 | 4 | 0 | 148 |
| `socialloop.ai` | 147 | 147 | 0 | 0 |
| `remoshift.com` | 122 | 8 | 114 | 0 |
| `fundinglandscape.com` | 117 | 76 | 41 | 0 |
| `openkrill.app` | 111 | 111 | 0 | 0 |
| 5609 other operators | 18892 | 17907 | 931 | 54 |
