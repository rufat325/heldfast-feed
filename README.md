# MCP server tool changes

Last change observed 2026-09-27T13:30:38+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 9409 npm servers from the official MCP registry (154 daily, the rest weekly) and 18576 hosted endpoints (daily).

11917 changes to a tool definition: 344 npm releases (98 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 11573 readings of hosted servers that found their tools changed; 13 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

Subscribe: [feed.xml](feed.xml) (Atom) or [feed.json](feed.json). Every event, with the words that moved: [events/](events).

Each day's commit is anchored in Bitcoin with OpenTimestamps: [checkpoints/](checkpoints), and how to check one in [TRANSPARENCY.md](https://github.com/rufat325/heldfast/blob/main/docs/TRANSPARENCY.md#checkpoints).

`quiet`: a graded pin forwards every changed tool (new tools still need approval). `review`: a change introduced an agent-directed instruction, hidden character, credential path or look-alike letter, or, from 2026-09-27, a price the previous version did not state. Events before that date were graded without prices and are kept as they were graded. Review means read it, not that it is hostile.

| published | server | release | tools | grade |
|---|---|---|---|---|
| 2026-09-27 | `remote/se.sistaminuten/travel-search` | 2026-09-27T131221333188 -> 2026-09-27T133039319428 | 1 changed | quiet |
| 2026-09-27 | `remote/no.restplass/travel-search` | 2026-09-27T131150197887 -> 2026-09-27T133036233122 | 1 changed | quiet |
| 2026-09-27 | `remote/fi.akkilahdot/travel-search` | 2026-09-27T131235426008 -> 2026-09-27T133028597521 | 1 changed | quiet |
| 2026-09-27 | `remote/dk.afbudsrejser/travel-search` | 2026-09-27T131134737034 -> 2026-09-27T133019734356 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.lonniev/tollbooth-sample` | 2026-09-23T162910853421 -> 2026-09-27T133004101014 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-27T131141833374 -> 2026-09-27T132946275936 | 1 changed | quiet |
| 2026-09-27 | `remote/io.ppc/postclick-landing-page-cro` | 2026-09-27T105139512025 -> 2026-09-27T132802337694 | 21 changed (every tool) | quiet |
| 2026-09-27 | `remote/org.heathy/nutrition` | 2026-09-26T045118772707 -> 2026-09-27T132707744045 | 3 changed | quiet |
| 2026-09-27 | `remote/com.googleapis.compute/mcp` | 2026-09-27T130518373894 -> 2026-09-27T132401028870 | 10 changed | quiet |
| 2026-09-27 | `remote/io.github.philpof102-svg/mainstreet` | 2026-09-23T162337370258 -> 2026-09-27T132329158832 | 1 removed | quiet |
| 2026-09-27 | `remote/com.phasefolio/phasefolio` | 2026-09-23T160303797880 -> 2026-09-27T132323960645 | 2 changed, 3 removed | quiet |
| 2026-09-27 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-09-26T132419298528 -> 2026-09-27T132300812786 | 2 changed | quiet |
| 2026-09-27 | `remote/xyz.apexfaucet/apex-x1` | 2026-09-27T123951923734 -> 2026-09-27T131949587950 | 2 added | review |
| 2026-09-27 | `remote/fi.akkilahdot/travel-search` | 2026-09-27T124905272896 -> 2026-09-27T131235426008 | 1 changed | quiet |
| 2026-09-27 | `remote/se.sistaminuten/travel-search` | 2026-09-27T125116810921 -> 2026-09-27T131221333188 | 1 changed | quiet |
| 2026-09-27 | `remote/no.restplass/travel-search` | 2026-09-27T125021291886 -> 2026-09-27T131150197887 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-27T124823676542 -> 2026-09-27T131141833374 | 1 changed | quiet |
| 2026-09-27 | `remote/dk.afbudsrejser/travel-search` | 2026-09-27T125004512979 -> 2026-09-27T131134737034 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-09-27T124921473560 -> 2026-09-27T131051121285 | 15 changed | review |
| 2026-09-27 | `remote/com.xoomar/xoomar-mcp` | 2026-09-24T202849325116 -> 2026-09-27T131052237965 | 1 changed | quiet |
| 2026-09-27 | `remote/com.plainfreight/quotes` | 2026-09-27T124859234389 -> 2026-09-27T131029209670 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.moralito311-andr/andreax` | 2026-09-27T113051434838 -> 2026-09-27T131021747178 | 1 changed, 2 added | quiet |
| 2026-09-27 | `remote/se.klassio/eu-customs-tariff-eudr` | 2026-09-23T160455707314 -> 2026-09-27T130554936333 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.tettertotter/fundinglandscape` | 2026-09-27T124418919079 -> 2026-09-27T130553572341 | 2 changed | quiet |
| 2026-09-27 | `remote/com.llmotions.farm/fable-5-agent` | 2026-09-24T115927402436 -> 2026-09-27T130544971704 | 1 changed | quiet |
| 2026-09-27 | `remote/com.googleapis.compute/mcp` | 2026-09-27T120420331937 -> 2026-09-27T130518373894 | 10 changed | quiet |
| 2026-09-27 | `remote/io.github.vassiliylakhonin/agenda-intelligence-md.1` | 2026-09-26T113359880336 -> 2026-09-27T130216992135 | 5 changed (every tool) | quiet |
| 2026-09-27 | `remote/app.agentbit/mcp` | 2026-09-27T123930336384 -> 2026-09-27T130217907053 | 1 changed | quiet |
| 2026-09-27 | `remote/se.sistaminuten/travel-search` | 2026-09-27T123227188781 -> 2026-09-27T125116810921 | 1 changed | quiet |
| 2026-09-27 | `remote/no.restplass/travel-search` | 2026-09-27T123151936152 -> 2026-09-27T125021291886 | 1 changed | quiet |
| 2026-09-27 | `remote/dk.afbudsrejser/travel-search` | 2026-09-27T123133238824 -> 2026-09-27T125004512979 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-09-27T123047177343 -> 2026-09-27T124921473560 | 15 changed | review |
| 2026-09-27 | `remote/fi.akkilahdot/travel-search` | 2026-09-27T123025860978 -> 2026-09-27T124905272896 | 1 changed | quiet |
| 2026-09-27 | `remote/com.plainfreight/quotes` | 2026-09-23T160858396822 -> 2026-09-27T124859234389 | 3 changed (every tool) | quiet |
| 2026-09-27 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-27T122921057598 -> 2026-09-27T124823676542 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.Project-Gifted1/pg1-threat-intel` | 2026-09-26T045253082371 -> 2026-09-27T124817890221 | 1 added | quiet |
| 2026-09-27 | `remote/com.hireahelper/mcp` | 2026-09-27T122641790473 -> 2026-09-27T124551690633 | 16 removed | quiet |
| 2026-09-27 | `remote/io.github.SidneyBissoli/ilo-mcp-server` | 2026-09-23T162534596553 -> 2026-09-27T124423782026 | 6 changed (every tool) | quiet |
| 2026-09-27 | `remote/io.github.tettertotter/fundinglandscape` | 2026-09-27T120249892074 -> 2026-09-27T124418919079 | 2 changed | quiet |
| 2026-09-27 | `remote/com.llmotions.farm/gpt-5-6-luna-agent` | 2026-09-24T115927804800 -> 2026-09-27T124410162779 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.odaiin/assetfare-bridge` | 2026-09-27T110246925232 -> 2026-09-27T123958369066 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.odaiin/assetfare` | 2026-09-27T110219700960 -> 2026-09-27T123955141076 | 1 changed | quiet |
| 2026-09-27 | `remote/xyz.apexfaucet/apex-x1` | 2026-09-27T055141203693 -> 2026-09-27T123951923734 | 10 added | review |
| 2026-09-27 | `remote/app.agentbit/mcp` | 2026-09-27T122001056872 -> 2026-09-27T123930336384 | 1 changed | quiet |
| 2026-09-27 | `umtri-mcp` | 1.3.2 -> 1.3.3 | 1 changed | quiet |
| 2026-09-27 | `remote/se.sistaminuten/travel-search` | 2026-09-27T120949381978 -> 2026-09-27T123227188781 | 1 changed | quiet |
| 2026-09-27 | `remote/no.restplass/travel-search` | 2026-09-27T121157865593 -> 2026-09-27T123151936152 | 1 changed | quiet |
| 2026-09-27 | `remote/dk.afbudsrejser/travel-search` | 2026-09-27T121139321284 -> 2026-09-27T123133238824 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-09-27T055156362632 -> 2026-09-27T123047177343 | 15 changed | review |
| 2026-09-27 | `remote/fi.akkilahdot/travel-search` | 2026-09-27T121222018818 -> 2026-09-27T123025860978 | 1 changed | quiet |
| 2026-09-27 | `remote/app.sallim/korea-realty` | 2026-09-27T121011898111 -> 2026-09-27T123008016036 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-27T121126621324 -> 2026-09-27T122921057598 | 1 changed | quiet |
| 2026-09-27 | `remote/com.hireahelper/mcp` | 2026-09-27T072522159081 -> 2026-09-27T122641790473 | 16 added | quiet |
| 2026-09-27 | `parseapi-mcp` | 1.7.0 -> 1.7.1 | 70 changed (every tool) | quiet |
| 2026-09-27 | `remote/cloud.theprotocol/registry` | 2026-09-24T115815768089 -> 2026-09-27T122338300072 | 32 changed | quiet |
| 2026-09-27 | `remote/app.agentbit/mcp` | 2026-09-27T110202291568 -> 2026-09-27T122001056872 | 1 changed | quiet |
| 2026-09-27 | `remote/fi.akkilahdot/travel-search` | 2026-09-27T114538656141 -> 2026-09-27T121222018818 | 1 changed | quiet |
| 2026-09-27 | `remote/no.restplass/travel-search` | 2026-09-27T113235843857 -> 2026-09-27T121157865593 | 1 changed | quiet |
| 2026-09-27 | `remote/dk.afbudsrejser/travel-search` | 2026-09-27T113217089744 -> 2026-09-27T121139321284 | 1 changed | quiet |
| 2026-09-27 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-09-27T114445125418 -> 2026-09-27T121126621324 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 8737 substantive, 3091 that changed only numbers (a catalogue counter ticking, a date), 89 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 6996 | 4021 | 2975 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `caseyjhand.com` | 55 | 55 | 0 | 0 |
| `daedalmap.com` | 47 | 47 | 0 | 0 |
| `sistaminuten.se` | 24 | 2 | 0 | 22 |
| `afbudsrejser.dk` | 23 | 2 | 0 | 21 |
| `akkilahdot.fi` | 23 | 2 | 0 | 21 |
| `restplass.no` | 23 | 2 | 0 | 21 |
| `socialloop.ai` | 23 | 23 | 0 | 0 |
| `assetfare.dev` | 20 | 20 | 0 | 0 |
| `dayze.com` | 18 | 18 | 0 | 0 |
| 931 other operators | 1900 | 1780 | 116 | 4 |
