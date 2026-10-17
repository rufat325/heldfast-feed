# MCP server tool changes

Last change observed 2026-10-17T06:05:12+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10495 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 23695 hosted endpoints (read daily, and every four hours while they keep changing).

29924 changes to a tool definition: 1050 npm releases (804 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 28874 readings of hosted servers that found their tools changed; 1981 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-17 | `remote/io.github.oppenheimervonbraun/zerostart-agent` | 2026-10-06T110341405097 -> 2026-10-17T060512583558 | 1 changed | review |
| 2026-10-17 | `remote/dev.zhiyong/knowledge-graph` | 2026-10-08T135555884727 -> 2026-10-17T060513001327 | 1 changed, 1 added | quiet |
| 2026-10-17 | `remote/io.github.TRDEFI/liquidity` | 2026-10-02T072204798265 -> 2026-10-17T060511214312 | 2 changed | quiet |
| 2026-10-17 | `remote/com.yieldprobe/defi-intel` | 2026-09-28T142335871789 -> 2026-10-17T060511882764 | 4 changed | review |
| 2026-10-17 | `remote/io.github.XRPDomains/xrpname-mcp-server` | 2026-09-23T163152550019 -> 2026-10-17T060509703866 | 10 changed (every tool) | quiet |
| 2026-10-17 | `remote/world.agentindex/x402` | 2026-10-08T135552481414 -> 2026-10-17T060508406944 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.industrial-platform-ai/industrial-platform` | 2026-10-06T110337646449 -> 2026-10-17T060506317024 | 11 added | quiet |
| 2026-10-17 | `remote/io.github.Trusgent/trusgent-mcp` | 2026-09-23T163148063171 -> 2026-10-17T060502421577 | 2 changed | quiet |
| 2026-10-17 | `remote/com.tabflows/site` | 2026-09-23T163147349392 -> 2026-10-17T060501011749 | 13 changed, 3 added | review |
| 2026-10-17 | `remote/org.steadysteel/steady-steel` | 2026-10-06T110330407419 -> 2026-10-17T060457309536 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.bryantrudy24/saax-protocol` | 2026-10-07T154828596308 -> 2026-10-17T060454177423 | 8 changed, 3 added (every tool) | quiet |
| 2026-10-17 | `remote/no.restplass/travel-search` | 2026-10-14T052711204570 -> 2026-10-17T060452368842 | 2 changed (every tool) | quiet |
| 2026-10-17 | `remote/it.prezzinvista/radar-volantini` | 2026-10-06T110327417484 -> 2026-10-17T060451748536 | 2 changed | quiet |
| 2026-10-17 | `remote/io.github.openaccountants/openaccountants` | 2026-10-09T153624233130 -> 2026-10-17T060449812765 | 8 changed, 1 added | quiet |
| 2026-10-17 | `remote/com.openmapp/openmapp` | 2026-09-23T163140006280 -> 2026-10-17T060450045720 | 4 changed, 1 added (every tool) | quiet |
| 2026-10-17 | `remote/com.ofacscreen/screening` | 2026-09-23T163139610264 -> 2026-10-17T060449788753 | 1 changed, 1 added | quiet |
| 2026-10-17 | `remote/ar.mueblito/mueblito` | 2026-10-06T110323874509 -> 2026-10-17T060447494976 | 9 changed | quiet |
| 2026-10-17 | `remote/com.iscabox/iscabox` | 2026-09-23T163136402126 -> 2026-10-17T060444033099 | 2 changed, 2 added, 2 removed | quiet |
| 2026-10-17 | `remote/fr.hypotheques-en-ligne/hel` | 2026-09-23T163138852889 -> 2026-10-17T060448904986 | 2 changed, 1 added | quiet |
| 2026-10-17 | `remote/com.insta-pola/photo-gallery` | 2026-10-06T110319703042 -> 2026-10-17T060442160235 | 2 changed | quiet |
| 2026-10-17 | `remote/work.funfriday/funfriday` | 2026-10-07T001331723562 -> 2026-10-17T060441369085 | 7 changed (every tool) | quiet |
| 2026-10-17 | `remote/io.github.maxschnee74-source/alpinelead` | 2026-10-06T110344097452 -> 2026-10-17T060432741549 | 22 removed | quiet |
| 2026-10-17 | `remote/com.electionsmcp/electionsmcp` | 2026-10-06T184113911986 -> 2026-10-17T060433976478 | 2 changed, 8 added, 111 removed | quiet |
| 2026-10-17 | `remote/de.drgsystem/medical-catalogs` | 2026-10-08T135521703564 -> 2026-10-17T060432861586 | 2 changed | quiet |
| 2026-10-17 | `remote/ai.dsght/public` | 2026-09-23T163130137592 -> 2026-10-17T060431641669 | 10 changed, 2 added (every tool) | quiet |
| 2026-10-17 | `remote/io.github.jakzaizzat/cukaimax-tax-authority` | 2026-09-23T163129340717 -> 2026-10-17T060431801670 | 4 changed | quiet |
| 2026-10-17 | `remote/io.deeplead/deeplead` | 2026-10-03T121336741314 -> 2026-10-17T060430762269 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.clairwave/clairwave` | 2026-09-26T114459963884 -> 2026-10-17T060427963320 | 2 changed | quiet |
| 2026-10-17 | `remote/ru.krasoft/zakupki` | 2026-09-23T160903932493 -> 2026-10-17T060431450363 | 2 changed | quiet |
| 2026-10-17 | `remote/io.github.zambodotdev/zambo` | 2026-10-04T233814465294 -> 2026-10-17T060428488218 | 19 changed, 16 added (every tool) | quiet |
| 2026-10-17 | `remote/dev.zambo/zambo` | 2026-10-04T233814844835 -> 2026-10-17T060428448690 | 19 changed, 16 added (every tool) | quiet |
| 2026-10-17 | `remote/de.caspar-manufaktur/materialberater` | 2026-10-06T110304605690 -> 2026-10-17T060427301137 | 2 changed | quiet |
| 2026-10-17 | `remote/com.youspot/youspot` | 2026-10-13T235700267240 -> 2026-10-17T060427162725 | 11 changed, 9 added | quiet |
| 2026-10-17 | `remote/com.xtracticle/xtracticle` | 2026-10-06T110341238324 -> 2026-10-17T060423755111 | 1 changed | quiet |
| 2026-10-17 | `remote/com.naxytra/xytara-mcp-executor` | 2026-10-02T183019009653 -> 2026-10-17T060423918327 | 12 added | review |
| 2026-10-17 | `remote/io.github.oaleviola/arroway` | 2026-10-08T135511384818 -> 2026-10-17T060422595894 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.Fizzl13/x402-doctor` | 2026-10-03T121413275113 -> 2026-10-17T060420311410 | 8 changed, 3 added (every tool) | review |
| 2026-10-17 | `remote/dk.afbudsrejser/travel-search` | 2026-10-14T052710860022 -> 2026-10-17T060420444996 | 2 changed (every tool) | quiet |
| 2026-10-17 | `remote/com.workers-rights/employment-law` | 2026-10-06T110336636186 -> 2026-10-17T060419395667 | 1 changed | quiet |
| 2026-10-17 | `remote/com.dondego/wikidata-google-knowledge-mcp` | 2026-10-06T110255516226 -> 2026-10-17T060419262033 | 7 changed | quiet |
| 2026-10-17 | `remote/com.whenisbins/bin-collections` | 2026-10-02T182944757113 -> 2026-10-17T060414085717 | 4 changed (every tool) | quiet |
| 2026-10-17 | `remote/com.tippingrules/tipping-rules` | 2026-09-23T160854434531 -> 2026-10-17T060413844197 | 3 changed (every tool) | quiet |
| 2026-10-17 | `remote/com.datakoot/us-weather-forecast-alerts` | 2026-10-03T192908429948 -> 2026-10-17T060411987164 | 6 changed (every tool) | quiet |
| 2026-10-17 | `remote/com.washlib/washlib` | 2026-09-23T163109690278 -> 2026-10-17T060412419757 | 5 changed, 3 added (every tool) | quiet |
| 2026-10-17 | `remote/io.github.Atenkai/smasher-studio` | 2026-09-23T160852360088 -> 2026-10-17T060410552261 | 1 changed | quiet |
| 2026-10-17 | `remote/uk.co.shipmycar/quote` | 2026-09-23T160852681230 -> 2026-10-17T060409794269 | 3 changed (every tool) | quiet |
| 2026-10-17 | `remote/com.satellitequotes/satellitequotes` | 2026-10-06T110322709268 -> 2026-10-17T060408894491 | 1 changed | quiet |
| 2026-10-17 | `remote/io.github.rubenmarcus/portfolio` | 2026-09-23T160852867769 -> 2026-10-17T060410351160 | 1 changed | quiet |
| 2026-10-17 | `remote/com.resollo/agent-api` | 2026-10-01T134410201622 -> 2026-10-17T060409162748 | 15 changed, 1 added | quiet |
| 2026-10-17 | `remote/io.github.ohad6k/viberaven-guides` | 2026-10-09T064815606118 -> 2026-10-17T060406037265 | 2 changed | quiet |
| 2026-10-17 | `remote/ai.vetaid/vetaid` | 2026-09-23T163102514728 -> 2026-10-17T060405712402 | 4 changed | quiet |
| 2026-10-17 | `remote/com.quailos/quailos` | 2026-10-06T184034880813 -> 2026-10-17T060404686975 | 3 changed, 39 added | quiet |
| 2026-10-17 | `remote/io.github.falsalama/proper-job` | 2026-10-08T135457963773 -> 2026-10-17T060403428761 | 4 changed (every tool) | quiet |
| 2026-10-17 | `remote/io.github.HuangGoodmanAgency/edgar-and-edgarette` | 2026-10-10T062525056369 -> 2026-10-17T060401632469 | 1 changed, 1 added | quiet |
| 2026-10-17 | `remote/dev.usaref/reference-data` | 2026-09-26T192554885556 -> 2026-10-17T060402857259 | 16 changed, 6 added (every tool) | quiet |
| 2026-10-17 | `remote/io.github.upforge-dev/upforge` | 2026-10-04T055040696213 -> 2026-10-17T060358822956 | 1 changed, 2 added | quiet |
| 2026-10-17 | `remote/com.underpricedai/underpriced-ai` | 2026-10-09T064814944302 -> 2026-10-17T060357950206 | 3 changed, 1 removed | quiet |
| 2026-10-17 | `remote/io.github.SidneyBissoli/uis-mcp-server` | 2026-10-08T213443499289 -> 2026-10-17T060356682970 | 1 changed | quiet |
| 2026-10-17 | `remote/com.mexsaas/mcp` | 2026-10-06T110308564610 -> 2026-10-17T060357764164 | 4 changed | quiet |
| 2026-10-17 | `remote/il.co.makore.www/makore` | 2026-10-06T110307067605 -> 2026-10-17T060355775291 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 21383 substantive, 8112 that changed only numbers (a catalogue counter ticking, a date), 429 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 14668 | 7143 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 126 | 126 | 0 | 0 |
| `sistaminuten.se` | 104 | 4 | 0 | 100 |
| `afbudsrejser.dk` | 103 | 4 | 0 | 99 |
| `akkilahdot.fi` | 103 | 4 | 0 | 99 |
| `restplass.no` | 103 | 4 | 0 | 99 |
| `socialloop.ai` | 101 | 101 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `remoshift.com` | 76 | 4 | 72 | 0 |
| `fundinglandscape.com` | 74 | 43 | 31 | 0 |
| 3726 other operators | 11375 | 10859 | 484 | 32 |
