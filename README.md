# MCP server tool changes

Last change observed 2026-11-03T02:43:15+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

71210 changes to a tool definition: 2981 npm releases (2735 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 68229 readings of hosted servers that found their tools changed; 3227 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-03 | `remote/io.taifoon/coordination-layer.1` | 2026-11-02T185432522626 -> 2026-11-03T024316718049 | 1 changed | review |
| 2026-11-03 | `remote/se.sistaminuten/travel-search` | 2026-11-02T185431406393 -> 2026-11-03T024315532036 | 1 changed | quiet |
| 2026-11-03 | `remote/com.socialfaktory/mcp` | 2026-11-02T163439032082 -> 2026-11-03T024315793226 | 1 changed | quiet |
| 2026-11-03 | `remote/cz.ubytovani-broumov/vila-marcelka` | 2026-11-02T163739040324 -> 2026-11-03T024316573621 | 1 added | quiet |
| 2026-11-03 | `remote/io.github.lifenplanner/babynews` | 2026-11-02T163417621864 -> 2026-11-03T024313875111 | 1 added | quiet |
| 2026-11-03 | `remote/com.mailbypony/mail-by-pony` | 2026-11-02T163421626825 -> 2026-11-03T024313696422 | 4 changed | quiet |
| 2026-11-03 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-11-02T185429129003 -> 2026-11-03T024313983143 | 6 changed | quiet |
| 2026-11-03 | `remote/io.github.JcJamet/ia-qa-security` | 2026-11-02T163417317105 -> 2026-11-03T024313609110 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.JcJamet/ia-qa-eval` | 2026-11-02T185429253802 -> 2026-11-03T024313677875 | 5 changed | quiet |
| 2026-11-03 | `remote/io.github.imokokok/insight-oracle` | 2026-11-02T185406240811 -> 2026-11-03T024311766228 | 2 added | quiet |
| 2026-11-03 | `remote/studio.gradients/mcp` | 2026-11-02T185401552244 -> 2026-11-03T024308669092 | 1 changed | quiet |
| 2026-11-03 | `remote/com.anchorterminal/anchor-terminal` | 2026-11-02T163357522181 -> 2026-11-03T024309018113 | 1 changed | quiet |
| 2026-11-03 | `remote/ai.arcreport/ask` | 2026-11-02T163359579124 -> 2026-11-03T024308288741 | 1 changed | quiet |
| 2026-11-03 | `remote/fi.akkilahdot/travel-search` | 2026-11-02T185359850983 -> 2026-11-03T024306840541 | 1 changed | quiet |
| 2026-11-03 | `remote/com.diariobitcoin/news` | 2026-11-02T163638282779 -> 2026-11-03T024307698759 | 2 changed, 1 added, 1 removed | quiet |
| 2026-11-03 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-02T185359974095 -> 2026-11-03T024307204625 | 2 changed | quiet |
| 2026-11-03 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-02T065454105534 -> 2026-11-03T024306356643 | 1 changed | quiet |
| 2026-11-03 | `remote/com.viraloutliers/viral-outliers` | 2026-11-01T135642607252 -> 2026-11-03T024303802786 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.marcoret74/semantic-geometry` | 2026-11-02T163321733754 -> 2026-11-03T024311373745 | 5 added | quiet |
| 2026-11-03 | `remote/com.veyrul/media-hub` | 2026-11-02T163322941028 -> 2026-11-03T024303583097 | 6 changed | quiet |
| 2026-11-03 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-02T185355997272 -> 2026-11-03T024303976967 | 3 changed | quiet |
| 2026-11-03 | `remote/io.github.SKalinin909/tradingcalc` | 2026-11-02T185416519973 -> 2026-11-03T024300254535 | 3 changed | quiet |
| 2026-11-03 | `remote/io.github.yungsuper16-eng/tokenomics-unlock-calendar` | 2026-11-02T163508887608 -> 2026-11-03T024257544991 | 1 changed | review |
| 2026-11-03 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-02T185350732944 -> 2026-11-03T024257596206 | 2 changed | quiet |
| 2026-11-03 | `remote/xyz.t0ll/toll` | 2026-11-02T185347559520 -> 2026-11-03T024253411453 | 1 added | quiet |
| 2026-11-03 | `remote/com.thefomite/fomite` | 2026-11-02T065445378742 -> 2026-11-03T024255474127 | 1 changed | quiet |
| 2026-11-03 | `remote/com.strongsaga/gear-lookup` | 2026-11-02T065452083384 -> 2026-11-03T024253452048 | 1 changed | quiet |
| 2026-11-03 | `remote/dev.tanod/tanod` | 2026-11-02T163202437872 -> 2026-11-03T024253947752 | 1 changed, 1 added | quiet |
| 2026-11-03 | `remote/com.stayingasia/mcp` | 2026-11-02T163144504729 -> 2026-11-03T024251541732 | 5 changed (every tool) | quiet |
| 2026-11-03 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-02T185344167542 -> 2026-11-03T024249967287 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.QDThead/signal-lab` | 2026-11-02T163353296263 -> 2026-11-03T024248488970 | 1 added | quiet |
| 2026-11-03 | `remote/dev.x402check/mcp` | 2026-11-02T163945412821 -> 2026-11-03T024248407181 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.davidgringras/scrutica` | 2026-11-01T065436910656 -> 2026-11-03T024247313787 | 2 changed | quiet |
| 2026-11-03 | `remote/com.remoshift/jobs` | 2026-11-02T185337327958 -> 2026-11-03T024245280348 | 1 changed | quiet |
| 2026-11-03 | `remote/de.objelio/immobiliensuche` | 2026-11-02T163916279039 -> 2026-11-03T024246172485 | 1 changed | quiet |
| 2026-11-03 | `remote/pl.finwire/data` | 2026-11-02T163015615292 -> 2026-11-03T024242954080 | 2 changed, 3 added | quiet |
| 2026-11-03 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-02T065432261317 -> 2026-11-03T024242849859 | 2 changed | quiet |
| 2026-11-03 | `remote/io.github.fmind/portfolio` | 2026-11-02T065431728267 -> 2026-11-03T024241600863 | 3 changed | quiet |
| 2026-11-03 | `remote/es.proceres/proceres` | 2026-11-02T185358667862 -> 2026-11-03T024242065921 | 12 changed, 1 added | quiet |
| 2026-11-03 | `remote/link.morningbrief/drinking-water` | 2026-11-02T163811411219 -> 2026-11-03T024238563914 | 9 changed (every tool) | quiet |
| 2026-11-03 | `remote/io.printpal/printpal` | 2026-11-02T185356732810 -> 2026-11-03T024239086238 | 1 changed, 1 added, 1 removed | quiet |
| 2026-11-03 | `remote/io.github.Philongevity/phi-longevity-prism` | 2026-11-02T162944945931 -> 2026-11-03T024238335778 | 9 changed, 1 added | quiet |
| 2026-11-03 | `remote/ai.softskillsacademy/destrava` | 2026-11-02T163127300903 -> 2026-11-03T024238283412 | 2 changed (every tool) | quiet |
| 2026-11-03 | `remote/com.organiqgeo/organiq` | 2026-11-02T185353212958 -> 2026-11-03T024237332254 | 2 changed | quiet |
| 2026-11-03 | `remote/com.triremes/triremes` | 2026-11-02T163729814588 -> 2026-11-03T024233962692 | 3 changed | quiet |
| 2026-11-03 | `remote/io.github.vicentesurraco/offpeak` | 2026-11-02T162901274467 -> 2026-11-03T024233819271 | 3 changed | quiet |
| 2026-11-03 | `remote/com.odilelabs/odile` | 2026-11-02T163111683377 -> 2026-11-03T024237359675 | 4 changed | quiet |
| 2026-11-03 | `remote/agency.thirdhemisphere/ai-authority-index` | 2026-11-02T163713324944 -> 2026-11-03T024234383981 | 5 added | quiet |
| 2026-11-03 | `remote/com.thenewengineer/hvac` | 2026-11-01T135320684698 -> 2026-11-03T024233491021 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.exquad/thecablecode` | 2026-11-02T163705161780 -> 2026-11-03T024232815781 | 2 changed | quiet |
| 2026-11-03 | `remote/no.restplass/travel-search` | 2026-11-02T185419439687 -> 2026-11-03T024229712582 | 1 changed | quiet |
| 2026-11-03 | `remote/com.myhumanrep/agent-contact` | 2026-11-02T162841565456 -> 2026-11-03T024230240990 | 6 added | quiet |
| 2026-11-03 | `remote/io.github.makar-aibot/money-reactor-mcp` | 2026-11-02T163042712548 -> 2026-11-03T024228343085 | 1 changed | review |
| 2026-11-03 | `remote/com.multicinesortega/cartelera` | 2026-11-02T065446828207 -> 2026-11-03T024230496926 | 1 changed | quiet |
| 2026-11-03 | `remote/app.sunsetstrip/gta6` | 2026-11-02T185402263315 -> 2026-11-03T024227996002 | 1 added | quiet |
| 2026-11-03 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-02T163027777639 -> 2026-11-03T024229847905 | 10 added | review |
| 2026-11-03 | `remote/me.miow/miow` | 2026-11-02T162829740213 -> 2026-11-03T024228148368 | 3 changed | quiet |
| 2026-11-03 | `remote/com.sonarconnections/sonar-connections` | 2026-11-02T185322299950 -> 2026-11-03T024227449887 | 1 changed, 2 added | quiet |
| 2026-11-03 | `remote/com.yutai/mcp` | 2026-11-02T162813008564 -> 2026-11-03T024227210938 | 2 changed | quiet |
| 2026-11-03 | `remote/io.github.sniffpup/sniffpup` | 2026-11-02T163604077067 -> 2026-11-03T024224979598 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 45142 substantive, 25273 that changed only numbers (a catalogue counter ticking, a date), 795 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 39567 | 15869 | 23698 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1245 | 1245 | 0 | 0 |
| `caseyjhand.com` | 313 | 313 | 0 | 0 |
| `sistaminuten.se` | 188 | 6 | 0 | 182 |
| `afbudsrejser.dk` | 187 | 6 | 0 | 181 |
| `akkilahdot.fi` | 187 | 6 | 0 | 181 |
| `restplass.no` | 187 | 6 | 0 | 181 |
| `socialloop.ai` | 181 | 181 | 0 | 0 |
| `remoshift.com` | 157 | 12 | 145 | 0 |
| `revmesh2074.workers.dev` | 146 | 128 | 18 | 0 |
| `fundinglandscape.com` | 144 | 89 | 55 | 0 |
| 7108 other operators | 26367 | 24940 | 1357 | 70 |
