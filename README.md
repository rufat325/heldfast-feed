# MCP server tool changes

Last change observed 2026-11-06T16:22:06+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

79590 changes to a tool definition: 3402 npm releases (3156 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 76188 readings of hosted servers that found their tools changed; 3493 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-06 | `remote/io.taifoon/coordination-layer.1` | 2026-11-06T144828814506 -> 2026-11-06T162207846341 | 1 changed | quiet |
| 2026-11-06 | `remote/se.sistaminuten/travel-search` | 2026-11-06T144825472912 -> 2026-11-06T162207284267 | 1 changed | quiet |
| 2026-11-06 | `remote/com.synthexforge.x402/paid-agent-services` | 2026-11-06T144942837416 -> 2026-11-06T162155887059 | 1 added | quiet |
| 2026-11-06 | `remote/com.stackerscan/stackerscan` | 2026-11-06T144930785951 -> 2026-11-06T162154138984 | 1 added | quiet |
| 2026-11-06 | `remote/studio.gradients/mcp` | 2026-11-06T144908974179 -> 2026-11-06T162152028457 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.privatelawattorneys/wiki-private-law` | 2026-11-06T144831754441 -> 2026-11-06T162151101161 | 3 changed | quiet |
| 2026-11-06 | `remote/fi.akkilahdot/travel-search` | 2026-11-06T144839106944 -> 2026-11-06T162150796327 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-06T144808246741 -> 2026-11-06T162150141649 | 3 changed | quiet |
| 2026-11-06 | `remote/no.restplass/travel-search` | 2026-11-06T144837630359 -> 2026-11-06T162147289331 | 1 changed | quiet |
| 2026-11-06 | `remote/ca.tonbot.tolca/tolca` | 2026-11-04T150410351419 -> 2026-11-06T162146262102 | 1 changed | quiet |
| 2026-11-06 | `remote/com.iscabox/iscabox` | 2026-11-05T115710157236 -> 2026-11-06T162146257738 | 1 changed | quiet |
| 2026-11-06 | `remote/com.googleapis.stitch/mcp` | 2026-11-05T222214778301 -> 2026-11-06T162143863742 | 3 changed | quiet |
| 2026-11-06 | `remote/dk.afbudsrejser/travel-search` | 2026-11-06T144753165988 -> 2026-11-06T162144128136 | 1 changed | quiet |
| 2026-11-06 | `remote/pl.finwire/data` | 2026-11-06T144428808695 -> 2026-11-06T162144611864 | 2 changed | quiet |
| 2026-11-06 | `remote/es.proceres/proceres` | 2026-11-06T072750337534 -> 2026-11-06T162143070081 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-06T144647264783 -> 2026-11-06T162141907098 | 1 changed | quiet |
| 2026-11-06 | `remote/com.postalref/postalref` | 2026-11-05T222156933876 -> 2026-11-06T162143238698 | 2 changed | quiet |
| 2026-11-06 | `remote/xyz.orkidlabs/orkid-swap` | 2026-11-06T144342340732 -> 2026-11-06T162136129118 | 1 changed, 1 added | quiet |
| 2026-11-06 | `remote/re.rundata/temps-reel` | 2026-11-06T144519476058 -> 2026-11-06T162135945029 | 1 changed | quiet |
| 2026-11-06 | `remote/com.pourwire/pourwire` | 2026-11-04T200738224458 -> 2026-11-06T162133826894 | 2 changed (every tool) | quiet |
| 2026-11-06 | `remote/com.platinumride/transfers` | 2026-11-05T115156578468 -> 2026-11-06T162133162271 | 4 changed (every tool) | quiet |
| 2026-11-06 | `remote/io.github.exquad/thecablecode` | 2026-11-06T144715715706 -> 2026-11-06T162126523941 | 1 changed | quiet |
| 2026-11-06 | `remote/com.skateboardpersonalizado/skateboard-deck` | 2026-11-05T150728864127 -> 2026-11-06T162123845118 | 1 changed | quiet |
| 2026-11-06 | `remote/com.socialseal/mcp` | 2026-11-06T072806792098 -> 2026-11-06T162121207533 | 42 changed | quiet |
| 2026-11-06 | `remote/com.rushordertees/rushordertees` | 2026-11-05T010637681675 -> 2026-11-06T162119924305 | 11 changed | quiet |
| 2026-11-06 | `remote/com.moneda/mcp` | 2026-11-05T222135460046 -> 2026-11-06T162120772417 | 2 changed | quiet |
| 2026-11-06 | `remote/dev.nexbid/discovery` | 2026-11-05T114858499256 -> 2026-11-06T162119372467 | 2 changed | quiet |
| 2026-11-06 | `remote/ai.mapmap/mapmap` | 2026-11-05T222155139523 -> 2026-11-06T162118759498 | 1 changed | quiet |
| 2026-11-06 | `remote/com.getmattered/getmattered` | 2026-11-05T114826428087 -> 2026-11-06T162115999852 | 2 changed | quiet |
| 2026-11-06 | `remote/ai.ahel/ahel` | 2026-11-05T222125716512 -> 2026-11-06T162112830128 | 3 changed | quiet |
| 2026-11-06 | `remote/pro.aicut/aicut` | 2026-11-06T143959657816 -> 2026-11-06T162110993895 | 9 changed | quiet |
| 2026-11-06 | `remote/com.mandarin3d/print` | 2026-11-06T143833047675 -> 2026-11-06T162110794103 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.si-imtiaz/leadquasar` | 2026-11-06T143923728210 -> 2026-11-06T162109997554 | 1 changed | quiet |
| 2026-11-06 | `remote/com.licensesaas/marketplace` | 2026-11-04T005849952891 -> 2026-11-06T162109807319 | 28 changed | review |
| 2026-11-06 | `remote/io.github.schneidavie/fund-momentum` | 2026-11-04T123701652357 -> 2026-11-06T162104674706 | 1 changed | quiet |
| 2026-11-06 | `remote/com.hovercode/mcp` | 2026-11-05T114513889321 -> 2026-11-06T162103422744 | 2 changed | quiet |
| 2026-11-06 | `remote/app.vercel.fork-for-agents/fork` | 2026-11-06T143632021368 -> 2026-11-06T162103304856 | 1 changed | quiet |
| 2026-11-06 | `remote/com.masteringfinancialmarkets/mfm` | 2026-11-05T222124625339 -> 2026-11-06T162059624873 | 2 changed | quiet |
| 2026-11-06 | `remote/app.marselia/marselia` | 2026-11-06T143901494138 -> 2026-11-06T162100203540 | 1 added | quiet |
| 2026-11-06 | `remote/io.github.thiagopatzdorf/fichario` | 2026-11-04T123647587817 -> 2026-11-06T162059204762 | 5 changed, 1 added, 2 removed | quiet |
| 2026-11-06 | `remote/io.github.barneywohl/hugging-bay` | 2026-11-06T143723856035 -> 2026-11-06T162056018805 | 2 changed | quiet |
| 2026-11-06 | `remote/com.brelsfordsoftware/agent-bounty-jobs` | 2026-11-04T200601805448 -> 2026-11-06T162054887869 | 1 changed | quiet |
| 2026-11-06 | `remote/work.doingwork/shop` | 2026-11-06T143421806969 -> 2026-11-06T162050577758 | 2 changed | quiet |
| 2026-11-06 | `remote/work.doingwork/home` | 2026-11-06T143254555290 -> 2026-11-06T162051583001 | 2 changed | quiet |
| 2026-11-06 | `remote/io.taifoon/coordination-layer` | 2026-11-06T143502788425 -> 2026-11-06T162052264412 | 1 changed | quiet |
| 2026-11-06 | `remote/com.googleapis.bigtableadmin/mcp` | 2026-11-06T072715627121 -> 2026-11-06T162049031596 | 6 changed | quiet |
| 2026-11-06 | `remote/com.spendquery/spendquery` | 2026-11-06T072738800654 -> 2026-11-06T162047844216 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.remoet-labs/remoet-mcp` | 2026-11-06T143212034057 -> 2026-11-06T162047493329 | 1 changed | quiet |
| 2026-11-06 | `remote/ai.buildersinfintech/fintech-data` | 2026-11-05T222134331158 -> 2026-11-06T162049200711 | 2 added | quiet |
| 2026-11-06 | `remote/com.beatandraise/sec-filings` | 2026-11-06T143344820775 -> 2026-11-06T162045266800 | 1 changed | quiet |
| 2026-11-06 | `remote/app.auditae/mcp.1` | 2026-11-05T010605700502 -> 2026-11-06T162045532315 | 3 changed | quiet |
| 2026-11-06 | `remote/com.spellbook-finance/mcp` | 2026-11-06T072712642089 -> 2026-11-06T162045687044 | 7 changed, 1 added | quiet |
| 2026-11-06 | `remote/co.trooth/semanto` | 2026-11-06T143143264625 -> 2026-11-06T162044422025 | 11 changed | quiet |
| 2026-11-06 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-11-06T143131913579 -> 2026-11-06T162044295604 | 1 changed | quiet |
| 2026-11-06 | `remote/com.publicwww/publicwww` | 2026-11-06T143124785610 -> 2026-11-06T162043583675 | 4 changed | quiet |
| 2026-11-06 | `remote/io.onchainagentintel/agent-zero-intel` | 2026-11-06T072716176356 -> 2026-11-06T162036735926 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.bleemohr/foodbe` | 2026-11-05T010609414208 -> 2026-11-06T162035162494 | 1 changed | quiet |
| 2026-11-06 | `remote/com.exepal/exepal` | 2026-11-06T072736209323 -> 2026-11-06T162035416360 | 1 added | quiet |
| 2026-11-06 | `remote/io.github.code0xff/1gateway` | 2026-11-06T142500523829 -> 2026-11-06T162028712253 | 4 changed | quiet |
| 2026-11-06 | `remote/io.github.Nutshell2000/agent-data-tools-compliance` | 2026-11-05T222059213307 -> 2026-11-06T162029452731 | 3 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 49533 substantive, 29193 that changed only numbers (a catalogue counter ticking, a date), 864 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 43271 | 15883 | 27388 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1604 | 1604 | 0 | 0 |
| `caseyjhand.com` | 354 | 354 | 0 | 0 |
| `sistaminuten.se` | 203 | 6 | 0 | 197 |
| `afbudsrejser.dk` | 202 | 6 | 0 | 196 |
| `akkilahdot.fi` | 202 | 6 | 0 | 196 |
| `restplass.no` | 202 | 6 | 0 | 196 |
| `socialloop.ai` | 195 | 195 | 0 | 0 |
| `modevc.com` | 174 | 174 | 0 | 0 |
| `revmesh2074.workers.dev` | 173 | 153 | 20 | 0 |
| `remoshift.com` | 165 | 14 | 151 | 0 |
| 7810 other operators | 30504 | 28791 | 1634 | 79 |
