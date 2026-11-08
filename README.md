# MCP server tool changes

Last change observed 2026-11-08T13:59:31+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

83393 changes to a tool definition: 3605 npm releases (3359 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 79788 readings of hosted servers that found their tools changed; 3597 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-08 | `remote/com.xn--5kvtwv52d/jizhineng-mcp-gateway` | 2026-11-02T163754140872 -> 2026-11-08T135934783178 | 10 changed | quiet |
| 2026-11-08 | `remote/de.wirstartenki/wirstartenki` | 2026-11-02T163452112884 -> 2026-11-08T135918877025 | 1 added, 1 removed | quiet |
| 2026-11-08 | `remote/xyz.tereno/tereno` | 2026-11-08T064549977009 -> 2026-11-08T135910587730 | 2 changed | review |
| 2026-11-08 | `remote/io.taifoon/coordination-layer.1` | 2026-11-07T203405642923 -> 2026-11-08T135909400727 | 1 changed | quiet |
| 2026-11-08 | `remote/se.sistaminuten/travel-search` | 2026-11-08T064549361066 -> 2026-11-08T135905844949 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.andzar22/offstereo` | 2026-11-04T150743288119 -> 2026-11-08T135855112441 | 2 changed | quiet |
| 2026-11-08 | `remote/io.kolmo.www/kolmo-mcp-server` | 2026-10-28T062226424116 -> 2026-11-08T135848255293 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.Yodaisgaming/seelig-ai-booking` | 2026-10-17T060408984147 -> 2026-11-08T135847212199 | 2 added | quiet |
| 2026-11-08 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-11-07T151352773634 -> 2026-11-08T135847356836 | 22 changed | quiet |
| 2026-11-08 | `remote/io.github.JcJamet/ia-qa-security` | 2026-11-05T124842978292 -> 2026-11-08T135847096130 | 3 changed | quiet |
| 2026-11-08 | `remote/io.github.JcJamet/ia-qa-eval` | 2026-11-07T151353340974 -> 2026-11-08T135847104774 | 9 changed | quiet |
| 2026-11-08 | `remote/uk.co.gigstamp/gigstamp` | 2026-11-01T135741455315 -> 2026-11-08T135844435433 | 2 changed | quiet |
| 2026-11-08 | `remote/com.plyparts/ply` | 2026-11-05T222229856491 -> 2026-11-08T135840254261 | 5 changed | quiet |
| 2026-11-08 | `remote/design.overflow/mcp` | 2026-11-02T163716551491 -> 2026-11-08T135837030522 | 1 changed | quiet |
| 2026-11-08 | `remote/co.developh/studio` | 2026-11-02T163408729937 -> 2026-11-08T135837299634 | 4 changed (every tool) | quiet |
| 2026-11-08 | `remote/io.github.imokokok/insight-oracle` | 2026-11-06T214845226825 -> 2026-11-08T135838548017 | 16 changed, 4 added (every tool) | quiet |
| 2026-11-08 | `remote/com.cameronsutcliff/magpie` | 2026-10-26T133843935096 -> 2026-11-08T135831976488 | 1 changed | quiet |
| 2026-11-08 | `remote/no.apier/mcp` | 2026-11-05T222216469750 -> 2026-11-08T135828328710 | 1 added | quiet |
| 2026-11-08 | `remote/com.anchorterminal/anchor-terminal` | 2026-11-06T214853868046 -> 2026-11-08T135827038838 | 6 changed, 1 added | quiet |
| 2026-11-08 | `remote/studio.gradients/mcp` | 2026-11-08T064614573280 -> 2026-11-08T135817838030 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.incwo/incwo` | 2026-11-07T133433024587 -> 2026-11-08T135817348302 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.JcJamet/ia-qa-data` | 2026-11-05T124826875484 -> 2026-11-08T135815272617 | 5 changed | quiet |
| 2026-11-08 | `remote/io.github.bostanyshop-rgb/growtsy` | 2026-11-02T163857856688 -> 2026-11-08T135812049792 | 2 added | quiet |
| 2026-11-08 | `remote/io.github.fmind/portfolio` | 2026-11-03T144937495088 -> 2026-11-08T135810020976 | 2 changed | quiet |
| 2026-11-08 | `remote/io.github.charleswei118/web2mcp` | 2026-11-02T163334889860 -> 2026-11-08T135803112378 | 1 added | quiet |
| 2026-11-08 | `remote/com.viraloutliers/viral-outliers` | 2026-11-03T024303802786 -> 2026-11-08T135754080305 | 4 changed, 6 added | quiet |
| 2026-11-08 | `remote/trade.buildix/hyperliquid` | 2026-10-27T112220139851 -> 2026-11-08T135753586792 | 1 changed | quiet |
| 2026-11-08 | `remote/fi.akkilahdot/travel-search` | 2026-11-08T064611983997 -> 2026-11-08T135747611108 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.moelayyan90/xguard` | 2026-11-06T072811623045 -> 2026-11-08T135745656137 | 9 added | review |
| 2026-11-08 | `remote/io.github.privatelawattorneys/wiki-private-law` | 2026-11-08T064613774870 -> 2026-11-08T135738350936 | 3 changed | quiet |
| 2026-11-08 | `remote/ai.thewholetorah/thewholetorah` | 2026-11-05T115741322588 -> 2026-11-08T135733659162 | 1 changed | quiet |
| 2026-11-08 | `remote/com.tubesaku/creator-insights` | 2026-11-06T072802350460 -> 2026-11-08T135728793760 | 2 changed | quiet |
| 2026-11-08 | `remote/no.restplass/travel-search` | 2026-11-08T064603918673 -> 2026-11-08T135723324647 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.intoApex/tradingagentstack` | 2026-11-05T115252595121 -> 2026-11-08T135720987490 | 1 added | quiet |
| 2026-11-08 | `remote/com.walletmcppass/wallet-mcp` | 2026-11-04T150502046253 -> 2026-11-08T135717699238 | 1 changed | quiet |
| 2026-11-08 | `remote/com.vuntum/mcp` | 2026-11-04T150501093108 -> 2026-11-08T135717132307 | 1 added | quiet |
| 2026-11-08 | `remote/com.voyscout/price-history` | 2026-10-13T021642604994 -> 2026-11-08T135715656540 | 3 changed | quiet |
| 2026-11-08 | `remote/com.usepickly/pickly` | 2026-11-05T150918312102 -> 2026-11-08T135718247789 | 1 changed, 1 added | quiet |
| 2026-11-08 | `remote/io.tooloracle/quantum` | 2026-09-23T160953923892 -> 2026-11-08T135714046570 | 1 changed | quiet |
| 2026-11-08 | `remote/ai.makeviral/makeviral` | 2026-11-02T163606857506 -> 2026-11-08T135712754967 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.roleworthylabs/layiq-jobs` | 2026-11-02T163605454380 -> 2026-11-08T135710672122 | 2 changed (every tool) | quiet |
| 2026-11-08 | `remote/com.ucpchecker/ucp-checker` | 2026-10-17T060252629604 -> 2026-11-08T135709984266 | 1 changed | quiet |
| 2026-11-08 | `remote/com.turbomaxai/mcp` | 2026-11-02T163733606345 -> 2026-11-08T135709253697 | 2 changed | quiet |
| 2026-11-08 | `remote/dev.tlly/tlly` | 2026-11-07T133700800565 -> 2026-11-08T135709147350 | 4 changed | quiet |
| 2026-11-08 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-08T064618497530 -> 2026-11-08T135706151396 | 3 changed | quiet |
| 2026-11-08 | `remote/com.theaitoolsindex/aitoolsindex` | 2026-09-23T160949084636 -> 2026-11-08T135702016249 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.TGM-Ventures/tgmcharts` | 2026-10-17T224407464891 -> 2026-11-08T135700454432 | 1 changed | quiet |
| 2026-11-08 | `remote/ru.vedarai/mcp` | 2026-11-07T133610054157 -> 2026-11-08T135659167127 | 8 changed | quiet |
| 2026-11-08 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-03T144815822143 -> 2026-11-08T135656998655 | 7 added | quiet |
| 2026-11-08 | `remote/io.doply/doply` | 2026-11-02T163546795530 -> 2026-11-08T135656588640 | 4 changed (every tool) | quiet |
| 2026-11-08 | `remote/tech.varexis/varexis-index` | 2026-10-23T120608653084 -> 2026-11-08T135655644464 | 2 changed | quiet |
| 2026-11-08 | `remote/io.github.jordanburke/temporal-mcp-server` | 2026-11-02T163712588057 -> 2026-11-08T135654924695 | 5 changed (every tool) | quiet |
| 2026-11-08 | `remote/io.github.chungty/thetennisdesk` | 2026-11-02T185408923786 -> 2026-11-08T135652271341 | 1 changed | quiet |
| 2026-11-08 | `remote/domains.cheapest/cheapest-domains` | 2026-11-04T150755046579 -> 2026-11-08T135651301858 | 2 changed | quiet |
| 2026-11-08 | `remote/com.themassprint/massprint` | 2026-09-23T160808726607 -> 2026-11-08T135650695762 | 3 changed | quiet |
| 2026-11-08 | `remote/net.swaptitan/swaptitan` | 2026-09-23T160945388880 -> 2026-11-08T135645986169 | 2 added | quiet |
| 2026-11-08 | `remote/com.textforagents/paired-twin-change-trials-for-agents` | 2026-10-26T133519712185 -> 2026-11-08T135646240401 | 1 added | quiet |
| 2026-11-08 | `remote/dk.afbudsrejser/travel-search` | 2026-11-08T064601395653 -> 2026-11-08T135643318049 | 1 changed | quiet |
| 2026-11-08 | `remote/com.truepeptidesource/peptides` | 2026-10-26T133419223715 -> 2026-11-08T135638313247 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.SQLazy/tabularium` | 2026-11-02T163646100224 -> 2026-11-08T135634999340 | 1 changed, 1 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 51356 substantive, 31138 that changed only numbers (a catalogue counter ticking, a date), 899 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 45119 | 15889 | 29230 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1843 | 1843 | 0 | 0 |
| `caseyjhand.com` | 354 | 354 | 0 | 0 |
| `sistaminuten.se` | 211 | 6 | 0 | 205 |
| `afbudsrejser.dk` | 210 | 6 | 0 | 204 |
| `akkilahdot.fi` | 210 | 6 | 0 | 204 |
| `restplass.no` | 210 | 6 | 0 | 204 |
| `socialloop.ai` | 202 | 202 | 0 | 0 |
| `revmesh2074.workers.dev` | 190 | 167 | 23 | 0 |
| `civai.co` | 188 | 188 | 0 | 0 |
| `modevc.com` | 174 | 174 | 0 | 0 |
| 8042 other operators | 32141 | 30174 | 1885 | 82 |
