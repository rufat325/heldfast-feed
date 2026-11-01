# MCP server tool changes

Last change observed 2026-11-01T20:53:20+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

68235 changes to a tool definition: 2873 npm releases (2627 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 65362 readings of hosted servers that found their tools changed; 3156 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-01 | `remote/no.restplass/travel-search` | 2026-11-01T153100825004 -> 2026-11-01T205322102397 | 1 changed | quiet |
| 2026-11-01 | `remote/dk.afbudsrejser/travel-search` | 2026-11-01T153059437000 -> 2026-11-01T205320141486 | 1 changed | quiet |
| 2026-11-01 | `remote/expert.tld/tld-expert` | 2026-11-01T135211353616 -> 2026-11-01T205316790637 | 1 changed | quiet |
| 2026-11-01 | `remote/com.googleapis.sqladmin/mcp` | 2026-11-01T135130861995 -> 2026-11-01T205313583683 | 3 changed | quiet |
| 2026-11-01 | `remote/re.rundata/temps-reel` | 2026-11-01T135051157147 -> 2026-11-01T205312739954 | 1 changed | quiet |
| 2026-11-01 | `remote/ai.rokha/rokha` | 2026-11-01T065433226194 -> 2026-11-01T205309942680 | 2 changed | quiet |
| 2026-11-01 | `remote/com.straelo/relay` | 2026-11-01T065432422731 -> 2026-11-01T205309996878 | 4 changed, 1 added, 1 removed | quiet |
| 2026-11-01 | `remote/com.youspot/youspot` | 2026-10-30T133035063652 -> 2026-11-01T205306752834 | 1 removed | quiet |
| 2026-11-01 | `remote/com.naxytra/xytara-mcp-executor` | 2026-10-31T202126674295 -> 2026-11-01T205306252699 | 14 added | review |
| 2026-11-01 | `remote/ch.kulalabs.pazair/pazair` | 2026-10-31T202109917468 -> 2026-11-01T205306460784 | 1 changed | quiet |
| 2026-11-01 | `remote/io.taifoon/coordination-layer.1` | 2026-11-01T153054366027 -> 2026-11-01T205305117565 | 1 changed | review |
| 2026-11-01 | `remote/io.github.cyanheads/openfoodfacts-mcp-server` | 2026-10-31T125809167383 -> 2026-11-01T205304605763 | 4 changed (every tool) | quiet |
| 2026-11-01 | `remote/io.github.cloakmaster/pact0` | 2026-11-01T153044782511 -> 2026-11-01T205305512433 | 1 changed | quiet |
| 2026-11-01 | `remote/com.techfabric/techfabric` | 2026-11-01T065441661585 -> 2026-11-01T205309827317 | 2 changed | quiet |
| 2026-11-01 | `remote/se.sistaminuten/travel-search` | 2026-11-01T153053784431 -> 2026-11-01T205304652167 | 1 changed | quiet |
| 2026-11-01 | `remote/io.github.seekdaseek/agentfeed` | 2026-10-31T234938783025 -> 2026-11-01T205304818568 | 4 added | review |
| 2026-11-01 | `remote/com.votepredictor/elections` | 2026-10-31T234852467649 -> 2026-11-01T205303293276 | 2 changed | quiet |
| 2026-11-01 | `remote/com.synthexforge.x402/paid-agent-services` | 2026-11-01T135429261721 -> 2026-11-01T205304706561 | 1 added | quiet |
| 2026-11-01 | `remote/io.github.imokokok/insight-oracle` | 2026-10-31T130420420527 -> 2026-11-01T205304182884 | 1 added | quiet |
| 2026-11-01 | `remote/io.github.brawlaphant/vealth` | 2026-11-01T153042815558 -> 2026-11-01T205302353480 | 1 changed | quiet |
| 2026-11-01 | `remote/studio.gradients/mcp` | 2026-11-01T153055678476 -> 2026-11-01T205301920437 | 1 changed | quiet |
| 2026-11-01 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-11-01T135706077268 -> 2026-11-01T205302745270 | 2 removed | quiet |
| 2026-11-01 | `remote/fi.akkilahdot/travel-search` | 2026-11-01T153054210168 -> 2026-11-01T205301060789 | 1 changed | quiet |
| 2026-11-01 | `remote/io.github.exquad/thecablecode` | 2026-10-31T144904089077 -> 2026-11-01T205259458781 | 4 changed | quiet |
| 2026-11-01 | `remote/io.github.CodeWever/wever-labs-products` | 2026-10-30T152351311743 -> 2026-11-01T205300155113 | 1 added | quiet |
| 2026-11-01 | `remote/com.tickerdb/mcp-server` | 2026-11-01T153038569657 -> 2026-11-01T205259882830 | 6 changed, 6 added | review |
| 2026-11-01 | `remote/cc.thecolony/mcp-server` | 2026-11-01T135317982771 -> 2026-11-01T205259720957 | 2 added | quiet |
| 2026-11-01 | `remote/ai.surfingdog/search` | 2026-11-01T135300586199 -> 2026-11-01T205257954458 | 5 changed | quiet |
| 2026-11-01 | `remote/app.openkrill/site-check` | 2026-11-01T065434217164 -> 2026-11-01T205256256741 | 2 changed | quiet |
| 2026-11-01 | `remote/com.strongsaga/gear-lookup` | 2026-11-01T065439859762 -> 2026-11-01T205256018985 | 10 changed (every tool) | quiet |
| 2026-11-01 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-01T153046558407 -> 2026-11-01T205253419213 | 1 changed | quiet |
| 2026-11-01 | `remote/io.github.bnth09productions-maker/scrapling-x402-store` | 2026-10-31T234859825976 -> 2026-11-01T205252327651 | 4 changed | quiet |
| 2026-11-01 | `remote/wiki.radix/radix-wiki` | 2026-10-31T202110657076 -> 2026-11-01T205251212705 | 1 changed | quiet |
| 2026-11-01 | `remote/eu.nulegal/recht` | 2026-11-01T135141497003 -> 2026-11-01T205252154221 | 1 changed | quiet |
| 2026-11-01 | `remote/com.remoshift/jobs` | 2026-11-01T153045421028 -> 2026-11-01T205250972402 | 1 changed | quiet |
| 2026-11-01 | `remote/com.radar-cnpj/radar-cnpj` | 2026-10-31T144906630214 -> 2026-11-01T205252147652 | 5 changed | quiet |
| 2026-11-01 | `remote/es.proceres/proceres` | 2026-11-01T153036313544 -> 2026-11-01T205248681164 | 2 changed | quiet |
| 2026-11-01 | `remote/com.pontofato/pontofato` | 2026-10-31T125932606496 -> 2026-11-01T205249378784 | 1 changed | quiet |
| 2026-11-01 | `remote/xyz.pokeka/card-prices` | 2026-11-01T135316674233 -> 2026-11-01T205247622642 | 1 changed | quiet |
| 2026-11-01 | `remote/net.hookpulse/hookpulse` | 2026-10-31T144831956161 -> 2026-11-01T205247244504 | 3 changed | quiet |
| 2026-11-01 | `remote/com.okstays/okstays` | 2026-11-01T135035857145 -> 2026-11-01T205246295771 | 3 changed | quiet |
| 2026-11-01 | `remote/online.pageaudit/pageaudit` | 2026-10-31T144902754883 -> 2026-11-01T205247965113 | 3 changed | quiet |
| 2026-11-01 | `remote/com.okfindex/okfindex` | 2026-10-31T125853854142 -> 2026-11-01T205245171146 | 2 changed | quiet |
| 2026-11-01 | `remote/com.odilelabs/odile` | 2026-11-01T065431633918 -> 2026-11-01T205245565642 | 1 changed | quiet |
| 2026-11-01 | `remote/ai.morphareels/morpha` | 2026-11-01T135008645378 -> 2026-11-01T205244834316 | 4 changed, 2 added | quiet |
| 2026-11-01 | `remote/si.mttr/mttr` | 2026-11-01T153030775967 -> 2026-11-01T205242928214 | 17 added, 17 removed | quiet |
| 2026-11-01 | `remote/me.miow/miow` | 2026-10-31T234834073857 -> 2026-11-01T205302526567 | 1 changed | quiet |
| 2026-11-01 | `remote/com.drmaker3d/shop` | 2026-10-31T202041946497 -> 2026-11-01T205244001510 | 2 changed | quiet |
| 2026-11-01 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-01T134925749200 -> 2026-11-01T205243209727 | 1 changed, 6 added | review |
| 2026-11-01 | `remote/us.corpuslaw/corpus-legal` | 2026-11-01T134207359844 -> 2026-11-01T205238949950 | 1 added | quiet |
| 2026-11-01 | `remote/io.taifoon/coordination-layer` | 2026-11-01T134208696111 -> 2026-11-01T205241016012 | 1 changed | review |
| 2026-11-01 | `remote/io.github.valuein/mcp-sec-edgar` | 2026-11-01T065423969318 -> 2026-11-01T205241458478 | 1 changed | quiet |
| 2026-11-01 | `remote/com.convocaliteraria/convoca` | 2026-10-31T202037912257 -> 2026-11-01T205238657992 | 2 changed | quiet |
| 2026-11-01 | `remote/com.ortexo/mcp` | 2026-10-31T202051461678 -> 2026-11-01T205238068870 | 1 changed | quiet |
| 2026-11-01 | `remote/com.commercialbuses/commercialbuses` | 2026-10-31T234759665766 -> 2026-11-01T205238213718 | 1 added | quiet |
| 2026-11-01 | `remote/tax.terminal/filing` | 2026-10-31T125736708539 -> 2026-11-01T205238165999 | 1 changed | quiet |
| 2026-11-01 | `remote/io.github.minsooparkk/korea-tax-law-mcp` | 2026-10-31T234829672077 -> 2026-11-01T205238979254 | 1 changed | quiet |
| 2026-11-01 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-10-31T202048399995 -> 2026-11-01T205235881281 | 1 changed | review |
| 2026-11-01 | `remote/com.movingplace/mcp` | 2026-10-31T202052496277 -> 2026-11-01T205234997299 | 16 added | quiet |
| 2026-11-01 | `remote/uk.co.hopi/hopi` | 2026-11-01T134941932967 -> 2026-11-01T205234222296 | 5 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 44052 substantive, 23405 that changed only numbers (a catalogue counter ticking, a date), 778 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 37734 | 15838 | 21896 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1245 | 1245 | 0 | 0 |
| `caseyjhand.com` | 311 | 311 | 0 | 0 |
| `sistaminuten.se` | 184 | 6 | 0 | 178 |
| `afbudsrejser.dk` | 183 | 6 | 0 | 177 |
| `akkilahdot.fi` | 183 | 6 | 0 | 177 |
| `restplass.no` | 183 | 6 | 0 | 177 |
| `socialloop.ai` | 177 | 177 | 0 | 0 |
| `remoshift.com` | 153 | 12 | 141 | 0 |
| `revmesh2074.workers.dev` | 146 | 128 | 18 | 0 |
| `fundinglandscape.com` | 141 | 87 | 54 | 0 |
| 6834 other operators | 25254 | 23889 | 1296 | 69 |
