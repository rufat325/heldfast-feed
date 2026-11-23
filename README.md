# MCP server tool changes

Last change observed 2026-11-23T08:19:57+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

127310 changes to a tool definition: 5105 npm releases (4859 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 122205 readings of hosted servers that found their tools changed; 4702 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-23 | `remote/com.metaintro/job-search` | 2026-11-22T150541223133 -> 2026-11-23T081958357116 | 3 changed | quiet |
| 2026-11-23 | `remote/studio.gradients/mcp` | 2026-11-22T221047910811 -> 2026-11-23T081957802655 | 1 changed | quiet |
| 2026-11-23 | `remote/app.hyperwave.www/wavetable-tools` | 2026-11-22T164202303469 -> 2026-11-23T081957052112 | 1 changed | quiet |
| 2026-11-23 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-22T073230636540 -> 2026-11-23T081955494922 | 1 changed | quiet |
| 2026-11-23 | `remote/fi.akkilahdot/travel-search` | 2026-11-22T221046666683 -> 2026-11-23T081955773431 | 1 changed | quiet |
| 2026-11-23 | `remote/com.weverlabs/agentic-rails` | 2026-11-22T221052257976 -> 2026-11-23T082003605453 | 8 added | quiet |
| 2026-11-23 | `remote/com.uxcontinuum/ship-check` | 2026-11-22T104243387902 -> 2026-11-23T081953225788 | 12 changed (every tool) | quiet |
| 2026-11-23 | `remote/io.github.pugarte7/spanish-top-tech-companies` | 2026-11-22T221038840084 -> 2026-11-23T081949181989 | 1 added | quiet |
| 2026-11-23 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-22T221037686100 -> 2026-11-23T081947998767 | 1 changed | quiet |
| 2026-11-23 | `remote/fr.scorelook/capucine` | 2026-11-22T104040059949 -> 2026-11-23T081948077705 | 2 changed | quiet |
| 2026-11-23 | `remote/com.serviche/sergio` | 2026-11-22T221037882151 -> 2026-11-23T081952196247 | 1 changed | quiet |
| 2026-11-23 | `remote/com.remoshift/jobs` | 2026-11-22T221033022371 -> 2026-11-23T081943753215 | 1 changed | quiet |
| 2026-11-23 | `remote/io.github.yschimke/compose-preview` | 2026-11-21T215735311789 -> 2026-11-23T081943778977 | 59 added | quiet |
| 2026-11-23 | `remote/today.nyangi/oneul-nyangi` | 2026-11-22T221026441800 -> 2026-11-23T081939881649 | 1 changed | quiet |
| 2026-11-23 | `remote/io.github.KevinCapri/nowcast-mcp` | 2026-11-22T145938433384 -> 2026-11-23T081939811825 | 13 changed (every tool) | quiet |
| 2026-11-23 | `remote/com.multicinesortega/cartelera` | 2026-11-22T221024730518 -> 2026-11-23T081938772485 | 1 changed | quiet |
| 2026-11-23 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-22T221022855022 -> 2026-11-23T081935909921 | 4 added | review |
| 2026-11-23 | `remote/com.sonarconnections/sonar-connections` | 2026-11-22T221021044509 -> 2026-11-23T081934329143 | 3 changed | quiet |
| 2026-11-23 | `remote/il.co.taseli/taseli` | 2026-11-22T145810181225 -> 2026-11-23T081933444815 | 1 changed | quiet |
| 2026-11-23 | `remote/com.trooprally/trooprally` | 2026-11-22T103735383152 -> 2026-11-23T081933358672 | 4 changed | quiet |
| 2026-11-23 | `remote/com.ortexo/mcp` | 2026-11-22T221016256199 -> 2026-11-23T081931194468 | 2 changed | quiet |
| 2026-11-23 | `remote/io.github.hail-hq/hail-mcp` | 2026-11-22T145625513479 -> 2026-11-23T081929888184 | 1 changed | quiet |
| 2026-11-23 | `remote/com.kernelcad/kernelcad` | 2026-11-22T164128425999 -> 2026-11-23T081930112057 | 21 changed | quiet |
| 2026-11-23 | `remote/pro.aicut/aicut` | 2026-11-22T221004306065 -> 2026-11-23T081925942255 | 5 changed | quiet |
| 2026-11-23 | `remote/no.restplass/travel-search` | 2026-11-22T221027242502 -> 2026-11-23T081924867280 | 1 changed | quiet |
| 2026-11-23 | `remote/io.github.JcJamet/ia-qa-data` | 2026-11-22T104615037992 -> 2026-11-23T081924670511 | 1 changed, 16 added, 35 removed | review |
| 2026-11-23 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-22T164201064873 -> 2026-11-23T081924990189 | 2 changed | quiet |
| 2026-11-23 | `remote/se.sistaminuten/travel-search` | 2026-11-22T221050649641 -> 2026-11-23T081925243594 | 1 changed | quiet |
| 2026-11-23 | `remote/io.github.m2mfreedom/freedom-m2m-mcp-server` | 2026-11-22T221001902252 -> 2026-11-23T081922310060 | 1 added | quiet |
| 2026-11-23 | `remote/fun.make/makefun` | 2026-11-22T221001820791 -> 2026-11-23T081922180850 | 15 changed, 4 added | quiet |
| 2026-11-23 | `remote/dk.afbudsrejser/travel-search` | 2026-11-22T221024592329 -> 2026-11-23T081922508892 | 1 changed | quiet |
| 2026-11-23 | `remote/io.github.si-imtiaz/leadquasar` | 2026-11-22T221001321222 -> 2026-11-23T081922058553 | 2 changed | quiet |
| 2026-11-23 | `remote/com.vidreno/mcp` | 2026-11-21T014812450181 -> 2026-11-23T081921926165 | 1 changed, 1 added | quiet |
| 2026-11-23 | `remote/com.velvetcompanionai/velvet` | 2026-11-22T104254151896 -> 2026-11-23T081921381671 | 2 changed | quiet |
| 2026-11-23 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-22T073254412937 -> 2026-11-23T081922070088 | 3 changed | quiet |
| 2026-11-23 | `remote/com.trackerhacker/mcp` | 2026-11-22T073144186774 -> 2026-11-23T081920340212 | 2 changed | quiet |
| 2026-11-23 | `remote/sg.tanatasa/tanatasa` | 2026-11-22T164153940500 -> 2026-11-23T081919687467 | 2 changed | quiet |
| 2026-11-23 | `remote/il.co.taseli/taseli.1` | 2026-11-22T150641270504 -> 2026-11-23T081919750246 | 1 changed | quiet |
| 2026-11-23 | `remote/net.hotelrefund/price-tracker` | 2026-11-22T073150724090 -> 2026-11-23T081917470593 | 1 changed | quiet |
| 2026-11-23 | `remote/io.github.andzar22/offstereo` | 2026-11-22T104815188519 -> 2026-11-23T081921746827 | 5 changed | quiet |
| 2026-11-23 | `remote/fr.ip73/ip73` | 2026-11-22T220958177980 -> 2026-11-23T081918951598 | 2 changed | quiet |
| 2026-11-23 | `remote/net.homonoia/homonoia` | 2026-11-21T145853365183 -> 2026-11-23T081918619148 | 9 changed, 6 added | quiet |
| 2026-11-23 | `remote/io.github.SeoScoreAPI/seoscoreapi-mcp` | 2026-11-22T164153149931 -> 2026-11-23T081916830987 | 12 changed, 2 removed | quiet |
| 2026-11-23 | `remote/com.helpyself/tools` | 2026-11-22T220958588296 -> 2026-11-23T081922028808 | 21 changed | quiet |
| 2026-11-23 | `remote/io.github.f-tiger/hvac-btu-heat-klimaanlage` | 2026-11-22T164116073063 -> 2026-11-23T081917912786 | 1 changed | quiet |
| 2026-11-23 | `remote/com.gameshopenter/shop` | 2026-11-22T220957731508 -> 2026-11-23T081917882799 | 2 changed | quiet |
| 2026-11-23 | `remote/com.gameshipkit/gameshipkit` | 2026-11-22T145148925233 -> 2026-11-23T081916332802 | 2 changed | quiet |
| 2026-11-23 | `remote/app.seatsherpa/rides` | 2026-11-22T104043775619 -> 2026-11-23T081916458521 | 5 changed | quiet |
| 2026-11-23 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-11-22T073249875107 -> 2026-11-23T081916273859 | 1 changed | quiet |
| 2026-11-23 | `remote/io.github.JcJamet/ia-qa-security` | 2026-11-22T073205888224 -> 2026-11-23T081915797069 | 3 changed, 13 added, 27 removed | review |
| 2026-11-23 | `remote/io.github.JcJamet/ia-qa-eval` | 2026-11-22T104731864448 -> 2026-11-23T081915747766 | 5 changed, 12 added, 34 removed (every tool) | review |
| 2026-11-23 | `remote/com.straelo/relay` | 2026-11-22T221015609759 -> 2026-11-23T081915621683 | 1 changed | quiet |
| 2026-11-23 | `remote/com.redgoodwine/redgoodwine` | 2026-11-22T104154734148 -> 2026-11-23T081914754521 | 1 changed | quiet |
| 2026-11-23 | `remote/com.radarbg/radar-tools` | 2026-11-22T221016063424 -> 2026-11-23T081917206857 | 5 added | quiet |
| 2026-11-23 | `remote/app.vercel.fork-for-agents/fork` | 2026-11-22T220956494309 -> 2026-11-23T081915689085 | 1 changed | quiet |
| 2026-11-23 | `remote/io.github.Playpowerpolitics/powerplayers` | 2026-11-22T221013331140 -> 2026-11-23T081914289594 | 3 changed | quiet |
| 2026-11-23 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-11-22T104730806867 -> 2026-11-23T081915703525 | 9 changed, 5 added, 144 removed | review |
| 2026-11-23 | `remote/com.provyan/provyan` | 2026-11-21T130603919743 -> 2026-11-23T081913977028 | 13 changed (every tool) | quiet |
| 2026-11-23 | `remote/com.herbertandphyllis/mcp` | 2026-11-22T221048409448 -> 2026-11-23T081915284498 | 1 changed | quiet |
| 2026-11-23 | `remote/io.github.cloakmaster/pact0` | 2026-11-21T130543888902 -> 2026-11-23T081913520366 | 1 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 83079 substantive, 43057 that changed only numbers (a catalogue counter ticking, a date), 1174 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 69283 | 29077 | 40206 | 0 |
| `a2awire.com` | 3571 | 3571 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 516 | 516 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 401 | 401 | 0 | 0 |
| `revmesh2074.workers.dev` | 362 | 307 | 55 | 0 |
| `sistaminuten.se` | 273 | 6 | 0 | 267 |
| `afbudsrejser.dk` | 272 | 6 | 0 | 266 |
| `akkilahdot.fi` | 272 | 6 | 0 | 266 |
| `restplass.no` | 272 | 6 | 0 | 266 |
| `socialloop.ai` | 263 | 263 | 0 | 0 |
| 10827 other operators | 49004 | 46099 | 2796 | 109 |
