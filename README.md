# MCP server tool changes

Last change observed 2026-11-07T15:14:01+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

82464 changes to a tool definition: 3503 npm releases (3257 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 78961 readings of hosted servers that found their tools changed; 3540 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-07 | `remote/no.restplass/travel-search` | 2026-11-07T133909417311 -> 2026-11-07T151403205080 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.openaccountants/openaccountants` | 2026-11-07T133858897591 -> 2026-11-07T151401761155 | 5 changed, 4 removed | quiet |
| 2026-11-07 | `remote/dk.afbudsrejser/travel-search` | 2026-11-07T133742429735 -> 2026-11-07T151359511430 | 1 changed | quiet |
| 2026-11-07 | `remote/io.taifoon/coordination-layer.1` | 2026-11-07T064006496416 -> 2026-11-07T151356303434 | 1 changed | quiet |
| 2026-11-07 | `remote/se.sistaminuten/travel-search` | 2026-11-07T133923666911 -> 2026-11-07T151354826291 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-07T064001637851 -> 2026-11-07T151353625670 | 4 added | review |
| 2026-11-07 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-11-05T124842711966 -> 2026-11-07T151352773634 | 1 changed, 1 added | quiet |
| 2026-11-07 | `remote/io.github.JcJamet/ia-qa-eval` | 2026-11-05T124843078408 -> 2026-11-07T151353340974 | 1 changed, 1 added | quiet |
| 2026-11-07 | `remote/com.blitzreels/blitzreels` | 2026-11-05T222217277158 -> 2026-11-07T151351448189 | 1 changed | quiet |
| 2026-11-07 | `remote/re.rundata/temps-reel` | 2026-11-06T162135945029 -> 2026-11-07T151349862559 | 2 changed | quiet |
| 2026-11-07 | `remote/com.synthexforge.x402/paid-agent-services` | 2026-11-07T133743428366 -> 2026-11-07T151348006868 | 1 added | quiet |
| 2026-11-07 | `remote/studio.gradients/mcp` | 2026-11-07T133707036689 -> 2026-11-07T151344334577 | 1 changed | quiet |
| 2026-11-07 | `remote/fi.akkilahdot/travel-search` | 2026-11-07T133644603055 -> 2026-11-07T151343647975 | 1 changed | quiet |
| 2026-11-07 | `remote/dev.zambo/zambo` | 2026-11-05T222215569847 -> 2026-11-07T151343381731 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-07T133614030242 -> 2026-11-07T151342617589 | 3 changed | quiet |
| 2026-11-07 | `remote/com.shipshapedata/shipshape-data-docs` | 2026-11-06T144524116849 -> 2026-11-07T151340541013 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.untitledfinancial/dpx` | 2026-11-07T133038071550 -> 2026-11-07T151336763487 | 111 changed (every tool) | quiet |
| 2026-11-07 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-07T133447315124 -> 2026-11-07T151336213396 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.exquad/thecablecode` | 2026-11-07T063953462701 -> 2026-11-07T151336776992 | 5 changed | quiet |
| 2026-11-07 | `remote/dev.silvertongue/silvertongue` | 2026-11-07T133018717709 -> 2026-11-07T151335576440 | 2 changed | quiet |
| 2026-11-07 | `remote/com.shipshapedata/shipshape-data` | 2026-11-06T144606967558 -> 2026-11-07T151332508883 | 1 changed | quiet |
| 2026-11-07 | `remote/com.getmattered/getmattered` | 2026-11-07T132907790636 -> 2026-11-07T151334102053 | 2 changed | quiet |
| 2026-11-07 | `remote/now.salesjobs/mcp` | 2026-11-07T133155646404 -> 2026-11-07T151331663419 | 1 changed | quiet |
| 2026-11-07 | `remote/io.saascity/saascity` | 2026-11-07T133153326979 -> 2026-11-07T151331580276 | 1 added | quiet |
| 2026-11-07 | `remote/io.github.priors-agents/priors-read` | 2026-11-06T144127261876 -> 2026-11-07T151323586245 | 2 added | quiet |
| 2026-11-07 | `remote/com.googleapis.monitoring/mcp` | 2026-11-07T063955858366 -> 2026-11-07T151323410281 | 5 changed | quiet |
| 2026-11-07 | `remote/nl.supplementenscanner/scanner` | 2026-11-07T132855387616 -> 2026-11-07T151316482180 | 4 changed (every tool) | quiet |
| 2026-11-07 | `remote/com.kernelcad/kernelcad` | 2026-11-07T132954480448 -> 2026-11-07T151315600535 | 13 changed, 3 added | quiet |
| 2026-11-07 | `remote/com.makehybrid/mcp` | 2026-11-07T132805420296 -> 2026-11-07T151313692960 | 3 changed, 4 added | quiet |
| 2026-11-07 | `remote/co.ivfcost/ivf-cost-data` | 2026-11-07T063932507439 -> 2026-11-07T151311680624 | 1 added | quiet |
| 2026-11-07 | `remote/tech.kaiku/kaiku.1` | 2026-11-07T132745693726 -> 2026-11-07T151311455496 | 1 changed | quiet |
| 2026-11-07 | `remote/co.esimcompare/travel-esim-prices` | 2026-11-07T132418496339 -> 2026-11-07T151310722843 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.si-imtiaz/leadquasar` | 2026-11-07T063939965151 -> 2026-11-07T151307969470 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.tettertotter/fundinglandscape` | 2026-11-07T132449620018 -> 2026-11-07T151306489169 | 3 changed | quiet |
| 2026-11-07 | `remote/io.github.Marsell-Official/marsell` | 2026-11-07T132534626726 -> 2026-11-07T151303243273 | 1 changed, 4 added | quiet |
| 2026-11-07 | `remote/io.drint/drint` | 2026-11-07T132355860212 -> 2026-11-07T151305220335 | 1 changed | quiet |
| 2026-11-07 | `remote/com.ce-net/ce-net.1` | 2026-11-06T072726187047 -> 2026-11-07T151305103350 | 5 added | quiet |
| 2026-11-07 | `remote/com.dayze/life-context.1` | 2026-11-07T132332369656 -> 2026-11-07T151302478969 | 1 changed | quiet |
| 2026-11-07 | `remote/com.dayze/life-context` | 2026-11-07T132332103498 -> 2026-11-07T151302054412 | 1 changed | quiet |
| 2026-11-07 | `remote/app.vercel.fork-for-agents/fork` | 2026-11-07T132414919893 -> 2026-11-07T151302598876 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.emmanuelorta/crawlcheck` | 2026-11-07T132251251648 -> 2026-11-07T151259302286 | 27 changed (every tool) | quiet |
| 2026-11-07 | `remote/com.brelsfordsoftware/agent-bounty-jobs` | 2026-11-06T162054887869 -> 2026-11-07T151255202428 | 7 added | quiet |
| 2026-11-07 | `remote/io.github.portpowered/portos` | 2026-11-07T131957911786 -> 2026-11-07T151253071082 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.stophydotdev/mcp` | 2026-11-07T131942221247 -> 2026-11-07T151245316002 | 4 changed | review |
| 2026-11-07 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-11-07T063911806774 -> 2026-11-07T151244690293 | 2 changed | quiet |
| 2026-11-07 | `remote/io.github.craigmbrown/blindoracle` | 2026-11-07T063913339173 -> 2026-11-07T151241677111 | 53 changed, 1 removed (every tool) | quiet |
| 2026-11-07 | `remote/me.crowdspark.agents/agent-tools` | 2026-11-06T142652462936 -> 2026-11-07T151237540786 | 1 added | quiet |
| 2026-11-07 | `remote/io.github.Nutshell2000/agent-data-tools-utilities` | 2026-11-07T063909377900 -> 2026-11-07T151236508542 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.Nutshell2000/agent-data-tools` | 2026-11-07T131610635627 -> 2026-11-07T151236900616 | 1 changed | quiet |
| 2026-11-07 | `remote/com.graunt/marketplace` | 2026-11-06T162021467181 -> 2026-11-07T151231464824 | 4 changed | quiet |
| 2026-11-07 | `remote/com.exepal/exepal` | 2026-11-07T131757692485 -> 2026-11-07T151228823185 | 15 changed (every tool) | quiet |
| 2026-11-07 | `remote/io.github.KKKKhazix/aihot` | 2026-11-06T142658449583 -> 2026-11-07T151241077878 | 2 added | quiet |
| 2026-11-07 | `remote/dev.workers.jbarkules.agent-tools/agent-tools` | 2026-11-06T142636142541 -> 2026-11-07T151225087873 | 1 added | quiet |
| 2026-11-07 | `remote/com.a2a2p/a2a2p` | 2026-11-06T214717779070 -> 2026-11-07T151223588845 | 2 changed | quiet |
| 2026-11-07 | `remote/io.github.TRDEFI/liquidity` | 2026-10-31T130331146475 -> 2026-11-07T134006993933 | 1 changed | quiet |
| 2026-11-07 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-11-04T151018392204 -> 2026-11-07T133955945065 | 44 changed (every tool) | quiet |
| 2026-11-07 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-11-04T150823754916 -> 2026-11-07T133940474166 | 44 changed (every tool) | quiet |
| 2026-11-07 | `remote/io.github.matt-moon/sonatina` | 2026-11-02T163439326968 -> 2026-11-07T133925921472 | 1 changed | quiet |
| 2026-11-07 | `remote/se.sistaminuten/travel-search` | 2026-11-07T064005711096 -> 2026-11-07T133923666911 | 1 changed | quiet |
| 2026-11-07 | `remote/com.starcovery/mcp` | 2026-10-28T133505083144 -> 2026-11-07T133924375910 | 2 changed, 36 added | review |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 50498 substantive, 31085 that changed only numbers (a catalogue counter ticking, a date), 881 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 45119 | 15889 | 29230 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1723 | 1723 | 0 | 0 |
| `caseyjhand.com` | 354 | 354 | 0 | 0 |
| `sistaminuten.se` | 207 | 6 | 0 | 201 |
| `afbudsrejser.dk` | 206 | 6 | 0 | 200 |
| `akkilahdot.fi` | 206 | 6 | 0 | 200 |
| `restplass.no` | 206 | 6 | 0 | 200 |
| `socialloop.ai` | 198 | 198 | 0 | 0 |
| `revmesh2074.workers.dev` | 190 | 167 | 23 | 0 |
| `modevc.com` | 174 | 174 | 0 | 0 |
| `civai.co` | 165 | 165 | 0 | 0 |
| 7916 other operators | 31375 | 29463 | 1832 | 80 |
