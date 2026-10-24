# MCP server tool changes

Last change observed 2026-10-24T12:58:32+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

47290 changes to a tool definition: 2087 npm releases (1841 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 45203 readings of hosted servers that found their tools changed; 2457 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-24 | `remote/studio.gradients/mcp` | 2026-10-24T113031104830 -> 2026-10-24T125833778569 | 1 changed | quiet |
| 2026-10-24 | `remote/fi.akkilahdot/travel-search` | 2026-10-24T113015533409 -> 2026-10-24T125832088069 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.MohDev212/verifypulse` | 2026-10-24T112951100124 -> 2026-10-24T125829925540 | 2 changed, 5 added | quiet |
| 2026-10-24 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-24T050524496511 -> 2026-10-24T125827676566 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-24T112848433877 -> 2026-10-24T125823432283 | 1 changed | quiet |
| 2026-10-24 | `remote/com.odilelabs/odile` | 2026-10-22T105637074975 -> 2026-10-24T125815026811 | 3 changed | review |
| 2026-10-24 | `remote/ai.terra-lab/terralab` | 2026-10-24T112602575661 -> 2026-10-24T125810596532 | 1 added | quiet |
| 2026-10-24 | `remote/ai.usedby/usedby` | 2026-10-24T112940669381 -> 2026-10-24T125808196711 | 1 changed | quiet |
| 2026-10-24 | `remote/se.sistaminuten/travel-search` | 2026-10-24T112934143980 -> 2026-10-24T125807391212 | 1 changed | quiet |
| 2026-10-24 | `remote/no.apier/mcp` | 2026-10-23T200840965952 -> 2026-10-24T125805115796 | 2 changed | quiet |
| 2026-10-24 | `remote/com.sfxmint/sounds` | 2026-10-24T050514303007 -> 2026-10-24T125803350796 | 1 changed | quiet |
| 2026-10-24 | `remote/com.thefilmradar/filmlab` | 2026-10-23T233356592715 -> 2026-10-24T125801320747 | 4 changed, 3 added | quiet |
| 2026-10-24 | `remote/no.restplass/travel-search` | 2026-10-24T113109859257 -> 2026-10-24T125757170980 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.cyanheads/wikipedia-mcp-server` | 2026-10-24T113021062233 -> 2026-10-24T125755966934 | 2 changed | quiet |
| 2026-10-24 | `remote/dk.afbudsrejser/travel-search` | 2026-10-24T113026753581 -> 2026-10-24T125756588393 | 1 changed | quiet |
| 2026-10-24 | `remote/dev.specpilot/specpilot` | 2026-10-23T115855103121 -> 2026-10-24T125756606646 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.cyanheads/gbif-biodiversity-mcp-server` | 2026-10-23T115820549425 -> 2026-10-24T125755274584 | 9 changed | quiet |
| 2026-10-24 | `remote/com.trustbaselab/rcb-data` | 2026-10-23T120549482237 -> 2026-10-24T125755865524 | 1 changed | quiet |
| 2026-10-24 | `remote/co.civai.nova/support-agent-admin` | 2026-10-23T120315982166 -> 2026-10-24T125802081663 | 3 changed | quiet |
| 2026-10-24 | `remote/org.worldgdp/nowcasts` | 2026-10-23T200756848340 -> 2026-10-24T125749408711 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.cyanheads/secedgar-mcp-server` | 2026-10-24T112829723795 -> 2026-10-24T125749692636 | 4 changed | quiet |
| 2026-10-24 | `remote/org.r3js/r3` | 2026-10-24T112544051521 -> 2026-10-24T125741363066 | 1 changed, 1 removed | quiet |
| 2026-10-24 | `remote/io.github.edtool79-collab/hirepulse-gateway` | 2026-10-24T112043171260 -> 2026-10-24T125734218779 | 8 changed | quiet |
| 2026-10-24 | `remote/io.github.whiteknightonhorse/apibase` | 2026-10-24T111738956864 -> 2026-10-24T125727719325 | 5 added | quiet |
| 2026-10-24 | `remote/io.taifoon/coordination-layer` | 2026-10-24T111916897421 -> 2026-10-24T125725422881 | 1 changed | review |
| 2026-10-24 | `remote/io.github.cyanheads/crossref-mcp-server` | 2026-10-23T115634707136 -> 2026-10-24T125723842122 | 2 changed | quiet |
| 2026-10-24 | `remote/directory.nohumans/registry` | 2026-10-24T111639420616 -> 2026-10-24T125722993896 | 1 changed | quiet |
| 2026-10-24 | `remote/com.agentdrives/directory.1` | 2026-10-24T111459902504 -> 2026-10-24T125717694175 | 1 changed | quiet |
| 2026-10-24 | `remote/xyz.groundtruths/groundtruth` | 2026-10-24T050442181446 -> 2026-10-24T125712944966 | 1 added | quiet |
| 2026-10-24 | `remote/com.ashareapi/ashare-data-api` | 2026-10-24T111559926750 -> 2026-10-24T125714631798 | 7 changed, 1 removed | quiet |
| 2026-10-24 | `remote/au.com.vividads/vivid-ads-commerce` | 2026-10-23T114953985143 -> 2026-10-24T125713374831 | 2 changed | quiet |
| 2026-10-24 | `remote/io.github.pournasserian/mcp-my-site` | 2026-10-23T200716915759 -> 2026-10-24T125710692214 | 1 changed | quiet |
| 2026-10-24 | `remote/com.a2awire/agent-inbox` | 2026-10-23T233340903153 -> 2026-10-24T125708571930 | 1 added | quiet |
| 2026-10-24 | `remote/io.github.TRDEFI/liquidity` | 2026-10-20T104313567482 -> 2026-10-24T113129682085 | 3 added | quiet |
| 2026-10-24 | `remote/no.restplass/travel-search` | 2026-10-24T050519373197 -> 2026-10-24T113109859257 | 1 changed | quiet |
| 2026-10-24 | `remote/com.praxikon/praxikon` | 2026-10-17T060452093488 -> 2026-10-24T113108001401 | 9 changed (every tool) | quiet |
| 2026-10-24 | `remote/com.zinvyl/marketplace` | 2026-10-24T050529428221 -> 2026-10-24T113103919985 | 5 changed | quiet |
| 2026-10-24 | `remote/ro.meseriasi/meseriasi-mcp-server` | 2026-09-23T163138214181 -> 2026-10-24T113100905394 | 1 added | quiet |
| 2026-10-24 | `remote/com.meridiandispatch/travel-guides` | 2026-10-21T234606155205 -> 2026-10-24T113059947268 | 5 added | quiet |
| 2026-10-24 | `remote/io.github.agentsherpa/yieldsentinel` | 2026-09-23T162959355110 -> 2026-10-24T113059027064 | 1 changed | quiet |
| 2026-10-24 | `remote/ca.commercialgaragedoorman/business-card` | 2026-09-23T163127256747 -> 2026-10-24T113036922994 | 1 added | quiet |
| 2026-10-24 | `remote/studio.gradients/mcp` | 2026-10-24T050528486032 -> 2026-10-24T113031104830 | 1 changed | quiet |
| 2026-10-24 | `remote/dk.afbudsrejser/travel-search` | 2026-10-24T050519252592 -> 2026-10-24T113026753581 | 1 changed | quiet |
| 2026-10-24 | `remote/com.elements-live/elements-live` | 2026-10-17T055931632872 -> 2026-10-24T113024367251 | 9 changed (every tool) | quiet |
| 2026-10-24 | `remote/io.github.witanmarkets/witan` | 2026-10-23T120619621397 -> 2026-10-24T113023397754 | 32 removed | quiet |
| 2026-10-24 | `remote/io.github.EasyGerber/easygerber` | 2026-10-20T052509867571 -> 2026-10-24T113023221834 | 8 changed | quiet |
| 2026-10-24 | `remote/io.github.cyanheads/wikipedia-mcp-server` | 2026-09-23T163113650296 -> 2026-10-24T113021062233 | 5 changed | quiet |
| 2026-10-24 | `remote/co.blackcarservice.www/ride-quotes` | 2026-10-17T055925522477 -> 2026-10-24T113019378567 | 1 changed, 2 added | quiet |
| 2026-10-24 | `remote/fi.akkilahdot/travel-search` | 2026-10-24T050527349410 -> 2026-10-24T113015533409 | 1 changed | quiet |
| 2026-10-24 | `remote/io.github.privatelawattorneys/wiki-private-law` | 2026-10-20T232816103737 -> 2026-10-24T113010283074 | 3 changed | quiet |
| 2026-10-24 | `remote/io.soundchain/agents` | 2026-10-20T201143508220 -> 2026-10-24T113001784298 | 6 added | quiet |
| 2026-10-24 | `remote/com.vouchernaut/deals` | 2026-10-23T120615537462 -> 2026-10-24T112957408374 | 4 changed | quiet |
| 2026-10-24 | `remote/io.github.paulieb89/uk-legal-mcp` | 2026-09-23T163055378482 -> 2026-10-24T112954697031 | 7 changed, 2 added | quiet |
| 2026-10-24 | `remote/io.github.MohDev212/verifypulse` | 2026-10-17T055900489748 -> 2026-10-24T112951100124 | 1 changed | quiet |
| 2026-10-24 | `remote/ai.trydock/dock` | 2026-10-23T233441604959 -> 2026-10-24T112950829888 | 2 changed | quiet |
| 2026-10-24 | `remote/com.trimtabist/us-tariff-ledger` | 2026-09-23T163051216722 -> 2026-10-24T112949605899 | 4 changed | quiet |
| 2026-10-24 | `remote/io.github.agentsherpa/yieldhunter` | 2026-09-23T161042919630 -> 2026-10-24T112949055071 | 3 changed | quiet |
| 2026-10-24 | `remote/io.github.eamwhite1/xrpl-referee` | 2026-10-20T104402416108 -> 2026-10-24T112948284114 | 5 changed, 2 added | quiet |
| 2026-10-24 | `remote/io.github.sharan01x/usetested` | 2026-10-17T111201777627 -> 2026-10-24T112945968048 | 1 added | review |
| 2026-10-24 | `remote/io.github.philpof102-svg/tokenizedblock` | 2026-10-18T190031018595 -> 2026-10-24T112940947537 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 29302 substantive, 17377 that changed only numbers (a catalogue counter ticking, a date), 611 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 25144 | 8777 | 16367 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 658 | 658 | 0 | 0 |
| `caseyjhand.com` | 198 | 198 | 0 | 0 |
| `sistaminuten.se` | 145 | 4 | 0 | 141 |
| `afbudsrejser.dk` | 144 | 4 | 0 | 140 |
| `akkilahdot.fi` | 144 | 4 | 0 | 140 |
| `restplass.no` | 144 | 4 | 0 | 140 |
| `socialloop.ai` | 140 | 140 | 0 | 0 |
| `remoshift.com` | 114 | 8 | 106 | 0 |
| `openkrill.app` | 111 | 111 | 0 | 0 |
| `fundinglandscape.com` | 109 | 71 | 38 | 0 |
| 5473 other operators | 17898 | 16982 | 866 | 50 |
