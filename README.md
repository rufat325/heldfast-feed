# MCP server tool changes

Last change observed 2026-10-21T20:26:06+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

40219 changes to a tool definition: 1694 npm releases (1448 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 38525 readings of hosted servers that found their tools changed; 2321 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-21 | `remote/io.taifoon/coordination-layer.1` | 2026-10-20T104352268056 -> 2026-10-21T202608383804 | 1 changed | review |
| 2026-10-21 | `remote/se.sistaminuten/travel-search` | 2026-10-21T141155419341 -> 2026-10-21T202606924635 | 1 changed | quiet |
| 2026-10-21 | `remote/no.restplass/travel-search` | 2026-10-21T141150535445 -> 2026-10-21T202602271062 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.oaleviola/arroway` | 2026-10-19T135823377411 -> 2026-10-21T202557796630 | 2 changed | quiet |
| 2026-10-21 | `remote/dk.afbudsrejser/travel-search` | 2026-10-21T141147173101 -> 2026-10-21T202557146412 | 1 changed | quiet |
| 2026-10-21 | `remote/org.warriorsfund/wounded-warriors` | 2026-10-20T201205084074 -> 2026-10-21T202554890863 | 1 changed | quiet |
| 2026-10-21 | `remote/online.waitapp/waitapp` | 2026-10-20T232821757978 -> 2026-10-21T202556315564 | 6 changed | quiet |
| 2026-10-21 | `remote/io.github.voicehook-ai/voicehook` | 2026-10-21T141147125472 -> 2026-10-21T202555809362 | 3 changed, 1 added | quiet |
| 2026-10-21 | `remote/com.veritaset/mcp` | 2026-10-21T122102511133 -> 2026-10-21T202553147535 | 1 changed | quiet |
| 2026-10-21 | `remote/ai.trydock/dock` | 2026-10-21T141138344747 -> 2026-10-21T202549089118 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.muaviamohammed/mizan` | 2026-10-21T122153687249 -> 2026-10-21T202545788786 | 3 added, 40 removed | quiet |
| 2026-10-21 | `remote/studio.sleeperhit/public-discovery` | 2026-10-19T052407689376 -> 2026-10-21T202540897631 | 1 changed | quiet |
| 2026-10-21 | `remote/com.soxoa/automation-planning` | 2026-10-20T104123279630 -> 2026-10-21T202543376162 | 1 added | quiet |
| 2026-10-21 | `remote/com.siliconfloor/silicon-floor` | 2026-10-21T122125317599 -> 2026-10-21T202540410884 | 1 changed | quiet |
| 2026-10-21 | `remote/app.openkrill/seo-audit` | 2026-10-19T135241485412 -> 2026-10-21T202537375121 | 1 removed | quiet |
| 2026-10-21 | `remote/ai.satohub/onchain-agents` | 2026-10-21T052302160659 -> 2026-10-21T202535886148 | 1 changed | quiet |
| 2026-10-21 | `remote/com.asksakina/islamic-knowledge` | 2026-10-21T122059118137 -> 2026-10-21T202535784086 | 4 changed (every tool) | quiet |
| 2026-10-21 | `remote/pl.przetargowyjanusz/tenders` | 2026-10-21T122023637041 -> 2026-10-21T202530508063 | 2 added | quiet |
| 2026-10-21 | `remote/site.chatgpt.orellise.relay-agent-services/relay` | 2026-10-21T121905177350 -> 2026-10-21T202530893555 | 3 changed | quiet |
| 2026-10-21 | `remote/com.portravo/construction-takeoff` | 2026-10-20T104043505986 -> 2026-10-21T202535647279 | 3 changed, 2 added | quiet |
| 2026-10-21 | `remote/com.pinsvit/api` | 2026-10-19T211935201013 -> 2026-10-21T202527814783 | 2 changed | quiet |
| 2026-10-21 | `remote/io.github.Philongevity/phi-longevity-prism` | 2026-10-20T052303836839 -> 2026-10-21T202525739006 | 2 added | quiet |
| 2026-10-21 | `remote/io.github.vassiliylakhonin/agenda-intelligence-md.1` | 2026-10-21T052252502178 -> 2026-10-21T202523827250 | 1 changed | quiet |
| 2026-10-21 | `remote/com.premierletters/mcp` | 2026-10-20T201151653495 -> 2026-10-21T202524324666 | 1 changed | quiet |
| 2026-10-21 | `remote/studio.gradients/mcp` | 2026-10-21T141139126055 -> 2026-10-21T202520792500 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.cloakmaster/pact0` | 2026-10-21T121822509220 -> 2026-10-21T202518736534 | 2 changed | quiet |
| 2026-10-21 | `remote/fi.akkilahdot/travel-search` | 2026-10-21T141137333969 -> 2026-10-21T202518149491 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.Nuvraxis/nuvui` | 2026-10-19T135435289069 -> 2026-10-21T202517823055 | 2 changed | quiet |
| 2026-10-21 | `remote/me.miow/miow` | 2026-10-21T141116122405 -> 2026-10-21T202516865182 | 2 changed | quiet |
| 2026-10-21 | `remote/ai.smilestory/musiccheck` | 2026-10-21T121752292363 -> 2026-10-21T202514691756 | 3 changed | quiet |
| 2026-10-21 | `remote/com.moonshotlab1/inventory` | 2026-10-21T121749535857 -> 2026-10-21T202513695952 | 2 changed, 5 added | quiet |
| 2026-10-21 | `remote/us.srv.vehcdj664efetfrsolne5umanq/quoteproof-mcp` | 2026-10-20T104532790733 -> 2026-10-21T202513365983 | 3 changed, 1 added | quiet |
| 2026-10-21 | `remote/gg.unicum/wot-stats` | 2026-10-19T135450073989 -> 2026-10-21T202510868638 | 3 changed | quiet |
| 2026-10-21 | `remote/de.viafrei/mcp` | 2026-10-20T135359438146 -> 2026-10-21T202512488244 | 3 changed | quiet |
| 2026-10-21 | `remote/com.youspot/youspot` | 2026-10-20T052321678721 -> 2026-10-21T202510356705 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.rezearcher/tech-risk` | 2026-10-20T052320637504 -> 2026-10-21T202508683328 | 2 changed | review |
| 2026-10-21 | `remote/io.github.GrayWolf8-creator/gw8-signal-api` | 2026-10-21T052403765485 -> 2026-10-21T202508736545 | 2 added | quiet |
| 2026-10-21 | `remote/com.transitmcp/transit-mcp` | 2026-10-21T052252862359 -> 2026-10-21T202510132239 | 1 changed | quiet |
| 2026-10-21 | `remote/com.mentioned-on/ai-discovery-readiness` | 2026-10-20T103925937673 -> 2026-10-21T202512789298 | 6 added | quiet |
| 2026-10-21 | `remote/lol.memepad/memepad` | 2026-10-19T135403230882 -> 2026-10-21T202508630586 | 9 changed (every tool) | quiet |
| 2026-10-21 | `remote/com.quailos/quailos` | 2026-10-21T122207544139 -> 2026-10-21T202508026596 | 4 changed, 3 added | quiet |
| 2026-10-21 | `remote/com.thinkreasonlearn/founderbrain` | 2026-10-19T135338065461 -> 2026-10-21T202505845028 | 3 changed (every tool) | quiet |
| 2026-10-21 | `remote/ai.go-rocket/go-rocket` | 2026-10-20T135421601798 -> 2026-10-21T202505861183 | 1 changed | quiet |
| 2026-10-21 | `remote/org.r3js/r3` | 2026-10-21T052401966409 -> 2026-10-21T202505081043 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-10-21T052240077511 -> 2026-10-21T202502223540 | 2 changed | review |
| 2026-10-21 | `remote/io.github.Rakesh1002/namemyapp.1` | 2026-10-20T103820460698 -> 2026-10-21T202502071403 | 1 changed, 1 added | quiet |
| 2026-10-21 | `remote/eu.paymentslaw/legislation` | 2026-10-19T211858236895 -> 2026-10-21T202504122735 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.withgrokbot/verified-catalog.1` | 2026-10-21T122113646775 -> 2026-10-21T202500354831 | 1 added | review |
| 2026-10-21 | `remote/io.github.nevermined-io/catalog` | 2026-10-20T135350784855 -> 2026-10-21T202500940855 | 11 changed | quiet |
| 2026-10-21 | `remote/ch.opencaselaw/swiss-caselaw` | 2026-10-20T103831459715 -> 2026-10-21T202501529939 | 1 changed | quiet |
| 2026-10-21 | `remote/app.sallim/korea-stay` | 2026-10-21T122036227405 -> 2026-10-21T202501654779 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-10-20T201136563187 -> 2026-10-21T202457785755 | 1 added | quiet |
| 2026-10-21 | `remote/ai.shorti/shorti` | 2026-10-19T155711152214 -> 2026-10-21T202455982007 | 3 changed | quiet |
| 2026-10-21 | `remote/app.openkrill/site-check` | 2026-10-19T135049833821 -> 2026-10-21T202453198551 | 1 removed | quiet |
| 2026-10-21 | `remote/com.convertlyft/convertlyft` | 2026-10-21T121557508533 -> 2026-10-21T202451493379 | 3 changed | quiet |
| 2026-10-21 | `remote/io.github.ronrey/comos-federation` | 2026-10-20T232734261505 -> 2026-10-21T202450362641 | 1 changed | quiet |
| 2026-10-21 | `remote/com.remoshift/jobs` | 2026-10-21T141111354836 -> 2026-10-21T202450211012 | 1 changed | quiet |
| 2026-10-21 | `remote/wiki.radix/radix-wiki` | 2026-10-20T201118630626 -> 2026-10-21T202446049617 | 2 changed | quiet |
| 2026-10-21 | `remote/io.github.sustany/alcbar-match` | 2026-10-20T201035338284 -> 2026-10-21T202446208702 | 2 changed | quiet |
| 2026-10-21 | `remote/io.github.profitphil/qmax` | 2026-10-21T052240286566 -> 2026-10-21T202445236783 | 17 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 25410 substantive, 14264 that changed only numbers (a catalogue counter ticking, a date), 545 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 20653 | 7232 | 13421 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 171 | 171 | 0 | 0 |
| `sistaminuten.se` | 130 | 4 | 0 | 126 |
| `afbudsrejser.dk` | 129 | 4 | 0 | 125 |
| `akkilahdot.fi` | 129 | 4 | 0 | 125 |
| `restplass.no` | 129 | 4 | 0 | 125 |
| `socialloop.ai` | 125 | 125 | 0 | 0 |
| `remoshift.com` | 100 | 6 | 94 | 0 |
| `fundinglandscape.com` | 98 | 63 | 35 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| 4941 other operators | 15464 | 14706 | 714 | 44 |
