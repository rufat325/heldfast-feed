# MCP server tool changes

Last change observed 2026-10-19T21:20:39+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

35154 changes to a tool definition: 1387 npm releases (1141 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 33767 readings of hosted servers that found their tools changed; 2203 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-19 | `remote/com.veridionmarkets/disclosures` | 2026-10-19T052424525816 -> 2026-10-19T212039958066 | 2 changed | quiet |
| 2026-10-19 | `remote/io.taifoon/coordination-layer.1` | 2026-10-19T135517924359 -> 2026-10-19T212038083221 | 1 changed | review |
| 2026-10-19 | `remote/se.sistaminuten/travel-search` | 2026-10-19T160200261652 -> 2026-10-19T212037596516 | 1 changed | quiet |
| 2026-10-19 | `remote/com.menloinsurance/mcp` | 2026-10-18T224012399762 -> 2026-10-19T212034159775 | 3 changed | quiet |
| 2026-10-19 | `remote/com.yardstickoutfitters/mcp` | 2026-10-19T135618658914 -> 2026-10-19T212031843420 | 1 changed | quiet |
| 2026-10-19 | `remote/com.coveragecat/insurance` | 2026-10-19T135445280628 -> 2026-10-19T212030593509 | 23 changed (every tool) | quiet |
| 2026-10-19 | `remote/cz.autoisto/used-cars` | 2026-10-17T055554913396 -> 2026-10-19T212030258576 | 1 changed | quiet |
| 2026-10-19 | `remote/no.restplass/travel-search` | 2026-10-19T160218950325 -> 2026-10-19T212029390107 | 1 changed | quiet |
| 2026-10-19 | `remote/com.ofacscreen/screening` | 2026-10-17T060449788753 -> 2026-10-19T212028445031 | 2 changed, 3 added (every tool) | quiet |
| 2026-10-19 | `remote/dev.zambo/zambo` | 2026-10-18T113517731801 -> 2026-10-19T212024644811 | 35 changed (every tool) | quiet |
| 2026-10-19 | `remote/com.mintlify/searchmcp` | 2026-10-19T135558600554 -> 2026-10-19T212025437457 | 1 changed | quiet |
| 2026-10-19 | `remote/ai.whatsupin/events` | 2026-10-19T135424027635 -> 2026-10-19T212024755284 | 5 changed, 1 added (every tool) | quiet |
| 2026-10-19 | `remote/io.github.zambodotdev/zambo` | 2026-10-18T113517759556 -> 2026-10-19T212023993261 | 35 changed (every tool) | quiet |
| 2026-10-19 | `remote/com.youspot/youspot` | 2026-10-18T190018070678 -> 2026-10-19T212024611659 | 1 added | quiet |
| 2026-10-19 | `remote/cz.livinisto/real-estate` | 2026-10-17T055944294495 -> 2026-10-19T212024265780 | 1 changed | quiet |
| 2026-10-19 | `remote/io.github.rezearcher/tech-risk` | 2026-10-19T135308276305 -> 2026-10-19T212022394863 | 2 changed | review |
| 2026-10-19 | `remote/io.github.Fizzl13/x402-doctor` | 2026-10-18T125104323141 -> 2026-10-19T212022133813 | 3 changed, 2 added | quiet |
| 2026-10-19 | `remote/studio.gradients/mcp` | 2026-10-19T155748657488 -> 2026-10-19T212020481999 | 1 changed | quiet |
| 2026-10-19 | `remote/io.github.voicehook-ai/voicehook` | 2026-10-19T160126924069 -> 2026-10-19T212018770763 | 4 changed, 4 added | quiet |
| 2026-10-19 | `remote/com.casabellaoutdoor/outdoor-kitchen` | 2026-10-17T060425423953 -> 2026-10-19T212017985740 | 5 changed | quiet |
| 2026-10-19 | `remote/sk.livinisto/real-estate` | 2026-10-17T060353667968 -> 2026-10-19T212016556028 | 1 changed | quiet |
| 2026-10-19 | `remote/com.kineticist/mcp-server` | 2026-10-19T155957257173 -> 2026-10-19T212015660129 | 8 changed | quiet |
| 2026-10-19 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-10-19T155956771105 -> 2026-10-19T212015988842 | 1 changed | quiet |
| 2026-10-19 | `remote/fi.akkilahdot/travel-search` | 2026-10-19T155744551447 -> 2026-10-19T212015581205 | 1 changed | quiet |
| 2026-10-19 | `remote/dk.afbudsrejser/travel-search` | 2026-10-19T160157835004 -> 2026-10-19T212016451965 | 1 changed | quiet |
| 2026-10-19 | `remote/io.github.privatelawattorneys/wiki-private-law` | 2026-10-18T051400430577 -> 2026-10-19T212014736882 | 3 changed | quiet |
| 2026-10-19 | `remote/sk.autoisto/used-cars` | 2026-10-17T060332039658 -> 2026-10-19T212012447799 | 1 changed | quiet |
| 2026-10-19 | `remote/org.warriorsfund/wounded-warriors` | 2026-10-19T135808297305 -> 2026-10-19T212011505677 | 3 changed | quiet |
| 2026-10-19 | `remote/ch.greenwave.wall-x/agent-relay` | 2026-10-19T135808587003 -> 2026-10-19T212011836492 | 1 changed | quiet |
| 2026-10-19 | `remote/ai.weio/site-check` | 2026-10-19T135205220706 -> 2026-10-19T212009813511 | 3 added, 2 removed | quiet |
| 2026-10-19 | `remote/direct.vote/vote-direct` | 2026-10-18T051357053995 -> 2026-10-19T212008526967 | 5 changed, 5 added | quiet |
| 2026-10-19 | `remote/com.veritaset/mcp` | 2026-10-19T160132680808 -> 2026-10-19T212007217281 | 1 changed | quiet |
| 2026-10-19 | `remote/io.github.sorindecu/vibeshipped` | 2026-10-19T135154891518 -> 2026-10-19T212005902270 | 2 added | quiet |
| 2026-10-19 | `remote/dev.usaref/reference-data` | 2026-10-17T160016635960 -> 2026-10-19T212009783338 | 7 added | review |
| 2026-10-19 | `remote/com.vibe-fixer/vibefix` | 2026-10-18T113404921501 -> 2026-10-19T212005615808 | 2 changed | review |
| 2026-10-19 | `remote/com.vanitynumbers/vanitynumbers` | 2026-10-19T160133780111 -> 2026-10-19T212006852333 | 5 changed, 1 removed | quiet |
| 2026-10-19 | `remote/io.github.AzielEliab/trades-runtime` | 2026-10-17T060246731013 -> 2026-10-19T212000625929 | 3 changed | quiet |
| 2026-10-19 | `remote/com.transitmcp/transit-mcp` | 2026-10-19T155730211523 -> 2026-10-19T212000443106 | 1 changed | quiet |
| 2026-10-19 | `remote/io.github.muaviamohammed/mizan` | 2026-10-19T135312355268 -> 2026-10-19T211959741224 | 2 changed | quiet |
| 2026-10-19 | `remote/com.thenewengineer/hvac` | 2026-10-17T060234160486 -> 2026-10-19T211957065782 | 1 changed | quiet |
| 2026-10-19 | `remote/com.sssnack/sssnack` | 2026-10-17T055452777593 -> 2026-10-19T211957349161 | 3 changed | quiet |
| 2026-10-19 | `remote/io.thepillar/pillar` | 2026-10-17T055834448556 -> 2026-10-19T211953790600 | 2 changed | quiet |
| 2026-10-19 | `remote/com.tiamatcrypto.sweetai/agent-intel` | 2026-10-17T060327351427 -> 2026-10-19T211954429664 | 1 added | quiet |
| 2026-10-19 | `remote/ru.activatedai/activated-ai` | 2026-10-17T060216926695 -> 2026-10-19T211952448380 | 2 changed | quiet |
| 2026-10-19 | `remote/uk.co.rentercheck/rentercheck` | 2026-10-19T135215771021 -> 2026-10-19T211944056410 | 1 changed | quiet |
| 2026-10-19 | `remote/io.github.jennipro-engineering/ghost-market-web` | 2026-10-19T135045059016 -> 2026-10-19T211944119880 | 1 changed | quiet |
| 2026-10-19 | `remote/dev.pages.scrapemole/scrapemole` | 2026-10-17T060251304865 -> 2026-10-19T211941866669 | 1 removed | quiet |
| 2026-10-19 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-19T155713699740 -> 2026-10-19T211941384655 | 1 changed, 4 added | quiet |
| 2026-10-19 | `remote/com.scienceshot/data-centres` | 2026-10-19T135613839607 -> 2026-10-19T211942733246 | 1 added | quiet |
| 2026-10-19 | `remote/com.signupbouncer/checker` | 2026-10-19T135332949527 -> 2026-10-19T211938286662 | 2 changed | quiet |
| 2026-10-19 | `remote/com.innergcomplete/shearquery` | 2026-10-17T055758090683 -> 2026-10-19T211936187236 | 3 changed | quiet |
| 2026-10-19 | `remote/com.session-exchange/sessions` | 2026-10-17T055757350750 -> 2026-10-19T211936771789 | 6 added | quiet |
| 2026-10-19 | `remote/wiki.radix/radix-wiki` | 2026-10-17T060105739388 -> 2026-10-19T211932994961 | 6 changed, 1 added | quiet |
| 2026-10-19 | `remote/com.pinsvit/api` | 2026-10-17T055356103768 -> 2026-10-19T211935201013 | 3 changed | quiet |
| 2026-10-19 | `remote/io.github.Philongevity/phi-longevity-prism` | 2026-10-17T185326024682 -> 2026-10-19T211932670932 | 1 changed | quiet |
| 2026-10-19 | `remote/io.github.AwakeWeb3/papertax` | 2026-10-19T135125142595 -> 2026-10-19T211929886003 | 1 changed, 4 added | quiet |
| 2026-10-19 | `remote/io.github.Fizzl13/presign-guard` | 2026-10-19T135522968489 -> 2026-10-19T211928994832 | 3 changed | quiet |
| 2026-10-19 | `remote/com.remoshift/jobs` | 2026-10-19T155658802766 -> 2026-10-19T211929255832 | 1 changed | quiet |
| 2026-10-19 | `remote/io.github.cueqzapper/picorn` | 2026-10-18T185947286755 -> 2026-10-19T211924845465 | 2 changed, 1 added | quiet |
| 2026-10-19 | `remote/io.github.kasheik3/penny-engine` | 2026-10-19T134932552576 -> 2026-10-19T211922729159 | 2 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 23483 substantive, 11172 that changed only numbers (a catalogue counter ticking, a date), 499 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 17656 | 7224 | 10432 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 166 | 166 | 0 | 0 |
| `sistaminuten.se` | 120 | 4 | 0 | 116 |
| `afbudsrejser.dk` | 119 | 4 | 0 | 115 |
| `akkilahdot.fi` | 119 | 4 | 0 | 115 |
| `restplass.no` | 119 | 4 | 0 | 115 |
| `socialloop.ai` | 116 | 116 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `remoshift.com` | 90 | 6 | 84 | 0 |
| `fundinglandscape.com` | 89 | 56 | 33 | 0 |
| 4385 other operators | 13469 | 12808 | 623 | 38 |
