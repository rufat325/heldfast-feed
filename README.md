# MCP server tool changes

Last change observed 2026-10-31T20:21:34+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

65469 changes to a tool definition: 2775 npm releases (2529 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 62694 readings of hosted servers that found their tools changed; 3101 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-31 | `remote/no.restplass/travel-search` | 2026-10-31T144916501464 -> 2026-10-31T202137465840 | 1 changed | quiet |
| 2026-10-31 | `remote/com.meridiandispatch/travel-guides` | 2026-10-31T062155770876 -> 2026-10-31T202136666006 | 1 changed, 1 added | quiet |
| 2026-10-31 | `remote/io.github.cryptoduke01/gloam` | 2026-10-30T133004309034 -> 2026-10-31T202133831449 | 5 changed | quiet |
| 2026-10-31 | `remote/com.naxytra/xytara-mcp-executor` | 2026-10-30T133032832049 -> 2026-10-31T202126674295 | 13 removed | quiet |
| 2026-10-31 | `remote/io.github.rezearcher/tech-risk` | 2026-10-31T130319223654 -> 2026-10-31T202127594043 | 1 changed, 1 added | review |
| 2026-10-31 | `remote/dk.afbudsrejser/travel-search` | 2026-10-31T144912703987 -> 2026-10-31T202130005965 | 1 changed | quiet |
| 2026-10-31 | `remote/ai.wem3/wem-price-compare` | 2026-10-29T212856845911 -> 2026-10-31T202130310790 | 3 changed | quiet |
| 2026-10-31 | `remote/io.github.fmind/portfolio` | 2026-10-30T132949599602 -> 2026-10-31T202124170572 | 10 changed (every tool) | quiet |
| 2026-10-31 | `remote/com.veritula/veritula` | 2026-10-29T104350617286 -> 2026-10-31T202122932804 | 1 changed | quiet |
| 2026-10-31 | `remote/se.sistaminuten/travel-search` | 2026-10-31T144915478639 -> 2026-10-31T202118675600 | 1 changed | quiet |
| 2026-10-31 | `remote/ai.greyridgesignals/tech-risk` | 2026-10-31T130439828269 -> 2026-10-31T202117935063 | 1 changed, 1 added | review |
| 2026-10-31 | `remote/uk.co.gigstamp/gigstamp` | 2026-10-31T130250970045 -> 2026-10-31T202117989272 | 3 changed | quiet |
| 2026-10-31 | `remote/fr.synergieloc/immobilier` | 2026-10-31T144901777566 -> 2026-10-31T202119204458 | 32 added | quiet |
| 2026-10-31 | `remote/com.coveragecat/insurance` | 2026-10-31T130241563120 -> 2026-10-31T202116094041 | 14 changed, 1 added | quiet |
| 2026-10-31 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-31T130004650059 -> 2026-10-31T202115441793 | 3 changed | quiet |
| 2026-10-31 | `remote/com.seoaix/seo-audit` | 2026-10-31T130027549746 -> 2026-10-31T202112965099 | 6 added | quiet |
| 2026-10-31 | `remote/com.scienceshot/data-centres` | 2026-10-31T125929353471 -> 2026-10-31T202114973253 | 1 changed | quiet |
| 2026-10-31 | `remote/studio.gradients/mcp` | 2026-10-31T144919375280 -> 2026-10-31T202132290330 | 1 changed | quiet |
| 2026-10-31 | `remote/re.rundata/temps-reel` | 2026-10-31T062135456742 -> 2026-10-31T202113608100 | 3 changed, 1 added | quiet |
| 2026-10-31 | `remote/fi.akkilahdot/travel-search` | 2026-10-31T144918394052 -> 2026-10-31T202111755690 | 1 changed | quiet |
| 2026-10-31 | `remote/site.chatgpt.orellise.relay-agent-services/relay` | 2026-10-30T210611929052 -> 2026-10-31T202112777724 | 16 changed (every tool) | quiet |
| 2026-10-31 | `remote/io.github.SKalinin909/tradingcalc` | 2026-10-31T130138859479 -> 2026-10-31T202112013809 | 2 added | quiet |
| 2026-10-31 | `remote/com.intoperson.tools/lottery-numbers` | 2026-10-31T130134759901 -> 2026-10-31T202111939222 | 2 changed | quiet |
| 2026-10-31 | `remote/wiki.radix/radix-wiki` | 2026-10-30T132636511588 -> 2026-10-31T202110657076 | 1 added | quiet |
| 2026-10-31 | `remote/io.github.MohDev212/verifypulse` | 2026-10-29T104435576653 -> 2026-10-31T202109936098 | 1 changed | review |
| 2026-10-31 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-31T144912848913 -> 2026-10-31T202108336138 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.Fizzl13/presign-guard` | 2026-10-31T062131796999 -> 2026-10-31T202108764207 | 1 changed | quiet |
| 2026-10-31 | `remote/ch.kulalabs.pazair/pazair` | 2026-10-31T125823483906 -> 2026-10-31T202109917468 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-31T144909279246 -> 2026-10-31T202105101983 | 1 changed | quiet |
| 2026-10-31 | `remote/com.stayotter/stay-otter` | 2026-10-30T210625972971 -> 2026-10-31T202105053251 | 9 changed (every tool) | quiet |
| 2026-10-31 | `remote/com.i2dev/snap` | 2026-10-31T130202501358 -> 2026-10-31T202104577292 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.bnth09productions-maker/scrapling-x402-store` | 2026-10-31T062133237846 -> 2026-10-31T202104319681 | 4 added | quiet |
| 2026-10-31 | `remote/net.rpscripts/fivem` | 2026-10-30T132758323362 -> 2026-10-31T202103560880 | 1 changed | quiet |
| 2026-10-31 | `remote/com.remoshift/jobs` | 2026-10-31T144906204940 -> 2026-10-31T202102593427 | 1 changed | quiet |
| 2026-10-31 | `remote/com.moonsox/moonsox` | 2026-10-31T062114039319 -> 2026-10-31T202103518128 | 3 changed | quiet |
| 2026-10-31 | `remote/io.github.lbailey94/whitemagic-mcp` | 2026-10-31T062113086105 -> 2026-10-31T202059687107 | 1 changed | quiet |
| 2026-10-31 | `remote/org.r3js/r3` | 2026-10-30T210601161019 -> 2026-10-31T202101973152 | 2 changed | quiet |
| 2026-10-31 | `remote/io.github.valuein/mcp-sec-edgar` | 2026-10-31T125746994549 -> 2026-10-31T202100635130 | 6 changed, 1 added | quiet |
| 2026-10-31 | `remote/com.odilelabs/odile` | 2026-10-31T144901205471 -> 2026-10-31T202058844794 | 20 changed (every tool) | quiet |
| 2026-10-31 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-10-31T144859210322 -> 2026-10-31T202055999947 | 4 changed, 1 added | quiet |
| 2026-10-31 | `remote/me.miow/miow` | 2026-10-29T212841078213 -> 2026-10-31T202055965180 | 5 changed, 1 added | quiet |
| 2026-10-31 | `remote/com.problee/problee` | 2026-10-30T063139229230 -> 2026-10-31T202054247053 | 6 changed, 1 added | review |
| 2026-10-31 | `remote/com.cielstay/cielstay` | 2026-10-30T063118836962 -> 2026-10-31T202053988145 | 4 changed | quiet |
| 2026-10-31 | `remote/com.senzing/mcp` | 2026-10-30T063125392747 -> 2026-10-31T202052070588 | 1 changed | quiet |
| 2026-10-31 | `remote/com.movingplace/mcp` | 2026-10-31T144842655284 -> 2026-10-31T202052496277 | 16 removed | quiet |
| 2026-10-31 | `remote/ai.rayana/rayana-ai` | 2026-10-30T132458294083 -> 2026-10-31T202052028452 | 1 changed | quiet |
| 2026-10-31 | `remote/com.ortexo/mcp` | 2026-10-30T210601611466 -> 2026-10-31T202051461678 | 1 changed | quiet |
| 2026-10-31 | `remote/ai.skuit/catalog` | 2026-10-31T062120738069 -> 2026-10-31T202050947488 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.allooloo/cm-kg` | 2026-10-31T125558286349 -> 2026-10-31T202050956461 | 1 added | quiet |
| 2026-10-31 | `remote/com.rivalsweeper/signals` | 2026-10-30T132309004600 -> 2026-10-31T202051771613 | 1 changed | quiet |
| 2026-10-31 | `remote/com.hireahelper/mcp` | 2026-10-31T144849461304 -> 2026-10-31T202049662618 | 16 removed | quiet |
| 2026-10-31 | `remote/io.github.hail-hq/hail-mcp` | 2026-10-30T210557544828 -> 2026-10-31T202050015469 | 2 changed | quiet |
| 2026-10-31 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-10-31T062119945510 -> 2026-10-31T202048399995 | 1 changed | review |
| 2026-10-31 | `remote/com.boxerbook/boxing` | 2026-10-31T125558091865 -> 2026-10-31T202047575175 | 10 changed (every tool) | quiet |
| 2026-10-31 | `remote/com.thefilmradar/filmlab` | 2026-10-31T144845469621 -> 2026-10-31T202046650136 | 1 added | quiet |
| 2026-10-31 | `remote/com.getprepsheet/prepsheet` | 2026-10-30T132015349959 -> 2026-10-31T202045055330 | 2 changed | quiet |
| 2026-10-31 | `remote/com.convertlyft/convertlyft` | 2026-10-31T144844448559 -> 2026-10-31T202044983224 | 2 changed | quiet |
| 2026-10-31 | `remote/io.github.grzesir/botspot-trading` | 2026-10-29T212826240451 -> 2026-10-31T202044498676 | 1 changed | quiet |
| 2026-10-31 | `remote/io.github.snefhew/factline-nl` | 2026-10-31T125155094801 -> 2026-10-31T202042531360 | 3 changed | quiet |
| 2026-10-31 | `remote/io.github.snefhew/factline-kyc` | 2026-10-31T062110517981 -> 2026-10-31T202042212724 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 43186 substantive, 21527 that changed only numbers (a catalogue counter ticking, a date), 756 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 35899 | 15834 | 20065 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1127 | 1127 | 0 | 0 |
| `caseyjhand.com` | 287 | 287 | 0 | 0 |
| `sistaminuten.se` | 179 | 6 | 0 | 173 |
| `afbudsrejser.dk` | 178 | 6 | 0 | 172 |
| `akkilahdot.fi` | 178 | 6 | 0 | 172 |
| `restplass.no` | 178 | 6 | 0 | 172 |
| `socialloop.ai` | 172 | 172 | 0 | 0 |
| `remoshift.com` | 148 | 10 | 138 | 0 |
| `revmesh2074.workers.dev` | 146 | 128 | 18 | 0 |
| `fundinglandscape.com` | 137 | 86 | 51 | 0 |
| 6728 other operators | 24499 | 23177 | 1255 | 67 |
