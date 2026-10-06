# MCP server tool changes

Last change observed 2026-10-06T18:41:22+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10128 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 21701 hosted endpoints (read daily, and every four hours while they keep changing).

22411 changes to a tool definition: 789 npm releases (543 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 21622 readings of hosted servers that found their tools changed; 288 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-06 | `remote/com.zinvyl/marketplace` | 2026-10-06T110440690031 -> 2026-10-06T184124919837 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.Dcroyalty/xrplhub` | 2026-10-06T110430365166 -> 2026-10-06T184122179392 | 1 changed | quiet |
| 2026-10-06 | `remote/ai.thebotique.www/sigil` | 2026-10-06T110427588515 -> 2026-10-06T184121443918 | 2 changed | quiet |
| 2026-10-06 | `remote/no.restplass/travel-search` | 2026-10-06T133912633321 -> 2026-10-06T184120119984 | 1 changed | quiet |
| 2026-10-06 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-10-06T133922313019 -> 2026-10-06T184117312070 | 2 changed | quiet |
| 2026-10-06 | `remote/fi.akkilahdot/travel-search` | 2026-10-06T133917289215 -> 2026-10-06T184116845410 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.CodeWever/wever-labs-products` | 2026-10-06T110336485595 -> 2026-10-06T184114869566 | 6 added | quiet |
| 2026-10-06 | `remote/com.n9t2/xrpl-agent-gateway` | 2026-10-06T133950392013 -> 2026-10-06T184115938859 | 19 changed (every tool) | quiet |
| 2026-10-06 | `remote/com.electionsmcp/electionsmcp` | 2026-10-06T110313198280 -> 2026-10-06T184113911986 | 1 changed | quiet |
| 2026-10-06 | `remote/se.sistaminuten/travel-search` | 2026-10-06T133940955306 -> 2026-10-06T184112694169 | 1 changed | quiet |
| 2026-10-06 | `remote/dk.afbudsrejser/travel-search` | 2026-10-06T133848601956 -> 2026-10-06T184111671750 | 1 changed | quiet |
| 2026-10-06 | `remote/de.overfit/overfit` | 2026-10-06T133937796275 -> 2026-10-06T184112576639 | 3 changed | quiet |
| 2026-10-06 | `remote/io.github.Schoasch/backtesting-arena` | 2026-10-06T113404439888 -> 2026-10-06T184110434021 | 1 changed | quiet |
| 2026-10-06 | `remote/com.getmixwise/mixwise` | 2026-10-06T110150758997 -> 2026-10-06T184109982750 | 1 changed, 1 added | quiet |
| 2026-10-06 | `remote/com.tickerinside/tickerinside-mcp` | 2026-10-04T055005254474 -> 2026-10-06T184108295806 | 11 changed (every tool) | quiet |
| 2026-10-06 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-10-06T110136055284 -> 2026-10-06T184107421368 | 1 added | quiet |
| 2026-10-06 | `remote/com.swarmmemo/bulletin` | 2026-10-06T113401830335 -> 2026-10-06T184108102262 | 71 changed (every tool) | quiet |
| 2026-10-06 | `remote/com.txtreel/txtreel` | 2026-10-06T110235665237 -> 2026-10-06T184105872762 | 2 changed | quiet |
| 2026-10-06 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-06T133810953755 -> 2026-10-06T184102350045 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.everyai-com/report-raja` | 2026-10-06T110155511576 -> 2026-10-06T184055278531 | 4 changed (every tool) | quiet |
| 2026-10-06 | `remote/io.github.everyai-com/recipe-scale` | 2026-10-06T110151548936 -> 2026-10-06T184054684503 | 4 changed (every tool) | quiet |
| 2026-10-06 | `remote/com.remoshift/jobs` | 2026-10-06T133730201246 -> 2026-10-06T184055504200 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.spokenmd/spoken` | 2026-10-06T133810461556 -> 2026-10-06T184057817369 | 8 changed (every tool) | quiet |
| 2026-10-06 | `remote/dev.pages.smithtalks/smithtalks` | 2026-10-06T110147856923 -> 2026-10-06T184055043336 | 2 added | quiet |
| 2026-10-06 | `remote/com.quietstance/productive-opportunity-development` | 2026-10-06T110148930951 -> 2026-10-06T184054800071 | 1 changed, 1 added | quiet |
| 2026-10-06 | `remote/io.github.everyai-com/sheet-shift` | 2026-10-06T110043101614 -> 2026-10-06T184052700282 | 4 changed (every tool) | quiet |
| 2026-10-06 | `remote/io.github.everyai-com/service-schedule` | 2026-10-06T110139225120 -> 2026-10-06T184051934419 | 4 changed (every tool) | quiet |
| 2026-10-06 | `remote/io.github.scraping-api-plans/web-data-plan-finder` | 2026-10-06T110133552624 -> 2026-10-06T184050450400 | 5 changed (every tool) | quiet |
| 2026-10-06 | `remote/io.github.everyai-com/room-split` | 2026-10-06T110022595768 -> 2026-10-06T184048789619 | 4 changed (every tool) | quiet |
| 2026-10-06 | `remote/com.obriym-crm/mcp` | 2026-10-06T110122748259 -> 2026-10-06T184046170606 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.Piloxa/piloxa` | 2026-10-05T172651809060 -> 2026-10-06T184042464692 | 2 changed | review |
| 2026-10-06 | `remote/ch.kulalabs.pazair/pazair` | 2026-10-06T110026752295 -> 2026-10-06T184041470668 | 5 changed, 19 added, 14 removed | quiet |
| 2026-10-06 | `remote/ai.pechincha/deals` | 2026-10-06T113403057858 -> 2026-10-06T184041764479 | 4 changed | quiet |
| 2026-10-06 | `remote/re.parcellai/parcellaire` | 2026-10-06T133654594348 -> 2026-10-06T184041675633 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.moralito311-andr/andreax` | 2026-10-06T133657651282 -> 2026-10-06T184040632494 | 3 changed | review |
| 2026-10-06 | `remote/io.github.everyai-com/party-plan` | 2026-10-06T110025105652 -> 2026-10-06T184039665781 | 4 changed (every tool) | quiet |
| 2026-10-06 | `remote/com.overlap-ai/overlap` | 2026-10-06T105948198425 -> 2026-10-06T184049496519 | 1 changed | quiet |
| 2026-10-06 | `remote/com.oods-foundry/foundry` | 2026-10-06T105939778968 -> 2026-10-06T184039067854 | 6 changed, 3 added, 3 removed (every tool) | quiet |
| 2026-10-06 | `remote/ai.senaro/personal-finance` | 2026-10-06T110006227323 -> 2026-10-06T184039062960 | 1 changed | quiet |
| 2026-10-06 | `remote/com.peppolstatus/api` | 2026-10-06T133524981157 -> 2026-10-06T184037971231 | 3 added | quiet |
| 2026-10-06 | `remote/com.youspot/youspot` | 2026-10-05T061636981249 -> 2026-10-06T184036344855 | 3 added | quiet |
| 2026-10-06 | `remote/io.github.negm17111995/maqami-travel` | 2026-10-06T105934395949 -> 2026-10-06T184035784233 | 15 changed, 1 added, 9 removed | quiet |
| 2026-10-06 | `remote/io.github.nanoparse-dev/nanoparse-mcp` | 2026-10-06T013031430937 -> 2026-10-06T184035760176 | 1 changed | review |
| 2026-10-06 | `remote/com.narrowhighway/concordance` | 2026-10-04T195006634717 -> 2026-10-06T184035731027 | 3 added | quiet |
| 2026-10-06 | `remote/ar.com.muovi/mcp-server` | 2026-10-06T105940270312 -> 2026-10-06T184036622403 | 6 changed | quiet |
| 2026-10-06 | `remote/ai.memestack/mcp` | 2026-10-06T105936551888 -> 2026-10-06T184034702171 | 13 changed | quiet |
| 2026-10-06 | `remote/com.quailos/quailos` | 2026-10-06T110315756360 -> 2026-10-06T184034880813 | 1 added | quiet |
| 2026-10-06 | `remote/com.kernelcad/kernelcad` | 2026-10-06T105926300043 -> 2026-10-06T184035895619 | 5 changed | quiet |
| 2026-10-06 | `remote/com.widely-mobile/widely` | 2026-10-06T105858324256 -> 2026-10-06T184032036724 | 5 changed | quiet |
| 2026-10-06 | `remote/io.github.smarterweather/weather` | 2026-10-06T105920732960 -> 2026-10-06T184030384435 | 1 added | quiet |
| 2026-10-06 | `remote/com.thinkreasonlearn/founderbrain` | 2026-10-06T105930436688 -> 2026-10-06T184030684783 | 2 changed, 1 added (every tool) | quiet |
| 2026-10-06 | `remote/io.github.withgrokbot/verified-catalog` | 2026-10-06T110207881454 -> 2026-10-06T184024569852 | 3 changed | quiet |
| 2026-10-06 | `remote/io.github.cammac-creator/openswissdata` | 2026-10-06T105808515689 -> 2026-10-06T184026805890 | 1 added | quiet |
| 2026-10-06 | `remote/com.thefilmradar/filmlab` | 2026-10-06T105821623142 -> 2026-10-06T184024851638 | 1 changed, 4 added | quiet |
| 2026-10-06 | `remote/org.living-bread.mcp/living-bread` | 2026-10-06T133435152200 -> 2026-10-06T184026027669 | 2 added | quiet |
| 2026-10-06 | `remote/co.getclippy/clippy` | 2026-10-06T133336354832 -> 2026-10-06T184023597462 | 4 changed (every tool) | quiet |
| 2026-10-06 | `remote/com.toolfound/toolfound` | 2026-10-06T110150366053 -> 2026-10-06T184023292694 | 13 changed | quiet |
| 2026-10-06 | `remote/trade.loomdesk/loomdesk` | 2026-10-06T133328088289 -> 2026-10-06T184020729300 | 2 changed | quiet |
| 2026-10-06 | `remote/io.github.firecrawl/firecrawl-mcp-server` | 2026-10-06T105726349396 -> 2026-10-06T184020405440 | 1 changed | quiet |
| 2026-10-06 | `remote/io.github.everyai-com/lease-break` | 2026-10-06T105806367984 -> 2026-10-06T184018837499 | 4 changed (every tool) | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 15660 substantive, 6431 that changed only numbers (a catalogue counter ticking, a date), 320 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 11736 | 5690 | 6046 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 424 | 424 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `sistaminuten.se` | 78 | 2 | 0 | 76 |
| `afbudsrejser.dk` | 77 | 2 | 0 | 75 |
| `akkilahdot.fi` | 77 | 2 | 0 | 75 |
| `restplass.no` | 77 | 2 | 0 | 75 |
| `socialloop.ai` | 75 | 75 | 0 | 0 |
| `caseyjhand.com` | 74 | 74 | 0 | 0 |
| `dayze.com` | 65 | 65 | 0 | 0 |
| `daedalmap.com` | 54 | 54 | 0 | 0 |
| 2731 other operators | 7236 | 6832 | 385 | 19 |
