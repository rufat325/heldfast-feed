# MCP server tool changes

Last change observed 2026-10-31T23:49:34+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

65554 changes to a tool definition: 2775 npm releases (2529 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 62779 readings of hosted servers that found their tools changed; 3110 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-31 | `remote/io.github.seekdaseek/agentfeed` | 2026-10-30T133115900336 -> 2026-10-31T234938783025 | 5 added | review |
| 2026-10-31 | `remote/studio.gradients/mcp` | 2026-10-31T202132290330 -> 2026-10-31T234927990550 | 1 changed | quiet |
| 2026-10-31 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-10-30T210633489991 -> 2026-10-31T234927937087 | 3 changed | quiet |
| 2026-10-31 | `remote/fi.akkilahdot/travel-search` | 2026-10-31T202111755690 -> 2026-10-31T234925069916 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.WattCoin-Org/wattcoin-mcp-server` | 2026-10-31T130326820841 -> 2026-10-31T234921873343 | 3 changed | quiet |
| 2026-10-31 | `remote/si.thinkhard/prompt-tools` | 2026-10-30T210629725074 -> 2026-10-31T234917726006 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-31T202105101983 -> 2026-10-31T234903804064 | 1 changed | quiet |
| 2026-10-31 | `remote/io.slopit/slopit` | 2026-10-29T212852087430 -> 2026-10-31T234902984010 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.davidgringras/scrutica` | 2026-10-30T210624237944 -> 2026-10-31T234901072254 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.bnth09productions-maker/scrapling-x402-store` | 2026-10-31T202104319681 -> 2026-10-31T234859825976 | 52 changed, 5 added | review |
| 2026-10-31 | `remote/com.sapiensolutions/site` | 2026-10-31T130127740931 -> 2026-10-31T234858985913 | 1 changed | quiet |
| 2026-10-31 | `remote/se.sistaminuten/travel-search` | 2026-10-31T202118675600 -> 2026-10-31T234856317455 | 1 changed | quiet |
| 2026-10-31 | `remote/com.remoshift/jobs` | 2026-10-31T202102593427 -> 2026-10-31T234855168366 | 1 changed | quiet |
| 2026-10-31 | `remote/no.restplass/travel-search` | 2026-10-31T202137465840 -> 2026-10-31T234853542626 | 1 changed | quiet |
| 2026-10-31 | `remote/no.apier/mcp` | 2026-10-31T130235994889 -> 2026-10-31T234853873283 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.Tomalarrrr/cyclesite-mcp-server` | 2026-10-30T132849910521 -> 2026-10-31T234853863408 | 1 changed | quiet |
| 2026-10-31 | `remote/com.votepredictor/elections` | 2026-10-29T104357629949 -> 2026-10-31T234852467649 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.brawlaphant/vealth` | 2026-10-30T063201195806 -> 2026-10-31T234851806416 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.SKalinin909/tradingcalc` | 2026-10-31T202112013809 -> 2026-10-31T234849844348 | 2 changed | quiet |
| 2026-10-31 | `remote/dk.afbudsrejser/travel-search` | 2026-10-31T202130005965 -> 2026-10-31T234848776954 | 1 changed | quiet |
| 2026-10-31 | `remote/cc.thecolony/mcp-server` | 2026-10-30T063159748121 -> 2026-10-31T234849348543 | 3 changed, 1 added | quiet |
| 2026-10-31 | `remote/io.github.ohad6k/viberaven-guides` | 2026-10-31T144908553111 -> 2026-10-31T234845801952 | 2 changed | quiet |
| 2026-10-31 | `remote/fun.publish/mcp` | 2026-10-31T062130159997 -> 2026-10-31T234842856737 | 2 changed | quiet |
| 2026-10-31 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-10-31T202055999947 -> 2026-10-31T234842559682 | 1 changed, 97 added | review |
| 2026-10-31 | `remote/fr.synergieloc/immobilier` | 2026-10-31T202119204458 -> 2026-10-31T234845261255 | 17 added | quiet |
| 2026-10-31 | `remote/es.proceres/proceres` | 2026-10-30T210606843797 -> 2026-10-31T234841711185 | 18 changed, 1 added | quiet |
| 2026-10-31 | `remote/com.multicinesortega/cartelera` | 2026-10-31T062128984736 -> 2026-10-31T234844115896 | 1 changed | quiet |
| 2026-10-31 | `remote/tools.settled/settled` | 2026-10-31T062136328854 -> 2026-10-31T234838708736 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.jakegallen/poascan` | 2026-10-30T063131377219 -> 2026-10-31T234840045275 | 1 added | quiet |
| 2026-10-31 | `remote/com.okstays/okstays` | 2026-10-31T125900260039 -> 2026-10-31T234836297867 | 8 changed (every tool) | review |
| 2026-10-31 | `remote/nl.nltaxcalculator/dutch-tax` | 2026-10-31T125840374373 -> 2026-10-31T234835839650 | 1 changed | quiet |
| 2026-10-31 | `remote/fun.pumpdata/pumpdata` | 2026-10-31T125846080220 -> 2026-10-31T234834308704 | 1 changed | quiet |
| 2026-10-31 | `remote/me.miow/miow` | 2026-10-31T202055965180 -> 2026-10-31T234834073857 | 4 changed | quiet |
| 2026-10-31 | `remote/com.probativegrowth/legal-marketing-data` | 2026-10-30T063130953957 -> 2026-10-31T234833412398 | 1 changed | quiet |
| 2026-10-31 | `remote/com.kernelcad/kernelcad` | 2026-10-31T125710462819 -> 2026-10-31T234834777558 | 2 changed, 1 added | quiet |
| 2026-10-31 | `remote/com.formada3d/mcp` | 2026-10-30T132329108479 -> 2026-10-31T234831746587 | 2 changed | quiet |
| 2026-10-31 | `remote/com.boxerbook/boxing` | 2026-10-31T202047575175 -> 2026-10-31T234830413486 | 10 changed (every tool) | quiet |
| 2026-10-31 | `remote/dev.turva/turva-mcp` | 2026-10-30T132423934266 -> 2026-10-31T234829693743 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.minsooparkk/korea-tax-law-mcp` | 2026-10-29T132924302804 -> 2026-10-31T234829672077 | 1 changed | quiet |
| 2026-10-31 | `remote/com.thefilmradar/filmlab` | 2026-10-31T202046650136 -> 2026-10-31T234829363456 | 1 changed | quiet |
| 2026-10-31 | `remote/gl.parse/mcp` | 2026-10-31T125659162510 -> 2026-10-31T234828105564 | 5 changed | quiet |
| 2026-10-31 | `remote/ai.justdomain/just-domain` | 2026-10-30T132259768892 -> 2026-10-31T234823877552 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.Poiuyhje/eqvps` | 2026-10-30T132228623123 -> 2026-10-31T234822840227 | 2 changed | quiet |
| 2026-10-31 | `remote/com.bankruptcyobserver/mcp` | 2026-10-31T125510907571 -> 2026-10-31T234821858356 | 19 changed (every tool) | quiet |
| 2026-10-31 | `remote/ai.meshtool/meshmarket` | 2026-10-31T125429283870 -> 2026-10-31T234820806672 | 1 removed | quiet |
| 2026-10-31 | `remote/dev.pages.freetier-agent-api/freetier-agent-api` | 2026-10-31T202038675437 -> 2026-10-31T234820000187 | 6 added | review |
| 2026-10-31 | `remote/app.vercel.fork-for-agents/fork` | 2026-10-31T202039031189 -> 2026-10-31T234820978876 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.inchwormz/iter0-mcp` | 2026-10-31T125341602568 -> 2026-10-31T234816258218 | 1 changed, 1 added | quiet |
| 2026-10-31 | `remote/ai.instabids/instabids` | 2026-10-31T125334202226 -> 2026-10-31T234815957738 | 1 changed, 1 added | quiet |
| 2026-10-31 | `remote/page.deed/deed-page` | 2026-10-31T062105205814 -> 2026-10-31T234814515262 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.cyanheads/devops-status-mcp-server` | 2026-10-31T125125914741 -> 2026-10-31T234813952721 | 3 changed | quiet |
| 2026-10-31 | `remote/com.koskamo/koskamo` | 2026-10-31T062101841135 -> 2026-10-31T234812953243 | 1 changed, 1 added | quiet |
| 2026-10-31 | `remote/io.github.skakumanu/llm-pricing-mcp-server` | 2026-10-31T125426484994 -> 2026-10-31T234812501584 | 3 changed, 1 added | quiet |
| 2026-10-31 | `remote/io.github.557tggwysr-ui/golfpriceai` | 2026-10-31T202033823054 -> 2026-10-31T234812353764 | 2 added | quiet |
| 2026-10-31 | `remote/com.cymetica/event-trader-mcp` | 2026-10-30T063109872042 -> 2026-10-31T234814722049 | 1 changed, 1 added | quiet |
| 2026-10-31 | `remote/com.clypmint/clypmint` | 2026-10-30T131730593850 -> 2026-10-31T234810805206 | 2 changed, 17 added, 18 removed | quiet |
| 2026-10-31 | `remote/cc.hlist/hlist-ai-tools` | 2026-10-31T062112967539 -> 2026-10-31T234808537803 | 1 changed | quiet |
| 2026-10-31 | `remote/dev.pages.geoquant-orb/geoquant-orb` | 2026-10-31T125313729522 -> 2026-10-31T234806797631 | 21 changed, 5 removed | quiet |
| 2026-10-31 | `remote/si.claimora/claimora` | 2026-10-31T062105233340 -> 2026-10-31T234805547924 | 5 changed | quiet |
| 2026-10-31 | `remote/com.clippingalpha/mcp` | 2026-10-31T202026560006 -> 2026-10-31T234804342040 | 4 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 43265 substantive, 21529 that changed only numbers (a catalogue counter ticking, a date), 760 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 35899 | 15834 | 20065 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1127 | 1127 | 0 | 0 |
| `caseyjhand.com` | 288 | 288 | 0 | 0 |
| `sistaminuten.se` | 180 | 6 | 0 | 174 |
| `afbudsrejser.dk` | 179 | 6 | 0 | 173 |
| `akkilahdot.fi` | 179 | 6 | 0 | 173 |
| `restplass.no` | 179 | 6 | 0 | 173 |
| `socialloop.ai` | 173 | 173 | 0 | 0 |
| `remoshift.com` | 149 | 10 | 139 | 0 |
| `revmesh2074.workers.dev` | 146 | 128 | 18 | 0 |
| `fundinglandscape.com` | 137 | 86 | 51 | 0 |
| 6729 other operators | 24577 | 23254 | 1256 | 67 |
