# MCP server tool changes

Last change observed 2026-10-28T06:22:35+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

55926 changes to a tool definition: 2384 npm releases (2138 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 53542 readings of hosted servers that found their tools changed; 2854 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-28 | `remote/no.restplass/travel-search` | 2026-10-27T210234305559 -> 2026-10-28T062236628544 | 1 changed | quiet |
| 2026-10-28 | `remote/com.techfabric/techfabric` | 2026-10-27T210206045584 -> 2026-10-28T062238617862 | 2 added | quiet |
| 2026-10-28 | `remote/sk.livinisto/intents` | 2026-10-26T133657474228 -> 2026-10-28T062232876957 | 1 added | quiet |
| 2026-10-28 | `remote/io.github.travisseamon-a11y/xemstudio` | 2026-10-26T133928302774 -> 2026-10-28T062232212494 | 8 changed (every tool) | quiet |
| 2026-10-28 | `remote/cz.livinisto/intents` | 2026-10-26T133657165027 -> 2026-10-28T062232985146 | 1 added | quiet |
| 2026-10-28 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-10-27T054129763805 -> 2026-10-28T062232554920 | 2 changed | quiet |
| 2026-10-28 | `remote/io.taifoon/coordination-layer.1` | 2026-10-27T210219076370 -> 2026-10-28T062231495497 | 1 changed | review |
| 2026-10-28 | `remote/se.sistaminuten/travel-search` | 2026-10-27T210218276586 -> 2026-10-28T062229730783 | 1 changed | quiet |
| 2026-10-28 | `remote/lol.wukong.world/agent-world` | 2026-10-27T210157929401 -> 2026-10-28T062229838130 | 2 changed, 2 added | quiet |
| 2026-10-28 | `remote/sk.autoisto/intents` | 2026-10-26T133729073679 -> 2026-10-28T062228637598 | 1 added | quiet |
| 2026-10-28 | `remote/io.kolmo.www/kolmo-mcp-server` | 2026-10-27T145921161218 -> 2026-10-28T062226424116 | 1 changed | quiet |
| 2026-10-28 | `remote/io.github.maggat/valentines-gifts` | 2026-10-26T133554216188 -> 2026-10-28T062227282384 | 5 changed | quiet |
| 2026-10-28 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-10-27T112348281796 -> 2026-10-28T062226905205 | 8 changed | quiet |
| 2026-10-28 | `remote/dk.afbudsrejser/travel-search` | 2026-10-27T210230412140 -> 2026-10-28T062229104200 | 1 changed | quiet |
| 2026-10-28 | `remote/online.gofigure/data-figure-studio` | 2026-10-26T133854148463 -> 2026-10-28T062225527279 | 2 changed | review |
| 2026-10-28 | `remote/it.expatliving/data` | 2026-10-27T112340362804 -> 2026-10-28T062225427844 | 1 changed | quiet |
| 2026-10-28 | `remote/com.ferntool/ip` | 2026-10-27T054101410804 -> 2026-10-28T062224893713 | 1 changed | quiet |
| 2026-10-28 | `remote/com.86hc/hongkong-company` | 2026-10-26T133725225097 -> 2026-10-28T062227726522 | 3 added | quiet |
| 2026-10-28 | `remote/cz.autoisto/intents` | 2026-10-26T133839264095 -> 2026-10-28T062223944712 | 1 added | quiet |
| 2026-10-28 | `remote/de.vitality-fit/prices` | 2026-10-26T133808713287 -> 2026-10-28T062222187421 | 1 changed | quiet |
| 2026-10-28 | `remote/xyz.urbangametheory/urban-game-theory` | 2026-10-27T210206250778 -> 2026-10-28T062221130144 | 1 changed | quiet |
| 2026-10-28 | `remote/cc.thecolony/mcp-server` | 2026-10-26T052305148613 -> 2026-10-28T062221582238 | 3 changed, 4 added | quiet |
| 2026-10-28 | `remote/xyz.unfee/mcp` | 2026-10-26T133749349052 -> 2026-10-28T062219515319 | 1 changed | review |
| 2026-10-28 | `remote/com.textforagents/elicitation-bridge-unsupported-clients` | 2026-10-26T133519305170 -> 2026-10-28T062219586618 | 1 changed | quiet |
| 2026-10-28 | `remote/com.topologyindex/topology-index` | 2026-10-27T112219651348 -> 2026-10-28T062218574634 | 1 changed | quiet |
| 2026-10-28 | `remote/sg.tanatasa/tanatasa` | 2026-10-27T112226138368 -> 2026-10-28T062218132739 | 2 changed, 3 added | quiet |
| 2026-10-28 | `remote/com.thefomite/fomite` | 2026-10-27T054053583389 -> 2026-10-28T062217364131 | 1 changed | quiet |
| 2026-10-28 | `remote/build.swapi/star-wars` | 2026-10-27T112219879135 -> 2026-10-28T062217294999 | 3 changed | quiet |
| 2026-10-28 | `remote/ai.surfingdog/search` | 2026-10-27T112217626652 -> 2026-10-28T062217235767 | 4 changed | quiet |
| 2026-10-28 | `remote/io.github.Ockram4444/agentcompute` | 2026-10-27T210223646724 -> 2026-10-28T062215787848 | 1 changed | quiet |
| 2026-10-28 | `remote/link.snip/snip` | 2026-10-27T210141707271 -> 2026-10-28T062212834935 | 1 changed | quiet |
| 2026-10-28 | `remote/ai.trydock/dock` | 2026-10-27T054110167558 -> 2026-10-28T062214054907 | 2 changed | quiet |
| 2026-10-28 | `remote/com.skinwinking/agent-tollgate` | 2026-10-27T210139340972 -> 2026-10-28T062211620993 | 1 changed, 4 added | review |
| 2026-10-28 | `remote/dev.tanod/docs` | 2026-10-27T145901385785 -> 2026-10-28T062211650952 | 34 changed | quiet |
| 2026-10-28 | `remote/dev.tanod/agents` | 2026-10-27T145901311199 -> 2026-10-28T062211295650 | 1 changed, 2 added | quiet |
| 2026-10-28 | `remote/com.zinvyl/marketplace` | 2026-10-27T210214291968 -> 2026-10-28T062211140616 | 13 changed | quiet |
| 2026-10-28 | `remote/ai.tazilo/profiles` | 2026-10-26T133710698429 -> 2026-10-28T062211347651 | 1 changed | quiet |
| 2026-10-28 | `remote/wiki.rust/rust-wiki` | 2026-10-26T133406184938 -> 2026-10-28T062214410270 | 1 changed | quiet |
| 2026-10-28 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-27T054110435488 -> 2026-10-28T062210641032 | 1 changed | quiet |
| 2026-10-28 | `remote/dev.tanod/tanod` | 2026-10-27T145901152915 -> 2026-10-28T062212001620 | 59 changed, 2 added | quiet |
| 2026-10-28 | `remote/ai.susurration/playground` | 2026-10-27T112149261023 -> 2026-10-28T062209601004 | 1 changed | quiet |
| 2026-10-28 | `remote/com.allthepossibles/toolbox` | 2026-10-26T133622359741 -> 2026-10-28T062207371834 | 1 changed | quiet |
| 2026-10-28 | `remote/io.github.CYAN-ECLIPSE-TECHNOLOGIES-LLC/white-report` | 2026-10-26T133615084591 -> 2026-10-28T062206915161 | 1 changed | quiet |
| 2026-10-28 | `remote/fr.synergieloc/immobilier` | 2026-10-27T210205457328 -> 2026-10-28T062207789832 | 24 added | quiet |
| 2026-10-28 | `remote/eu.nulegal/recht` | 2026-10-27T210134811336 -> 2026-10-28T062207153364 | 4 changed | quiet |
| 2026-10-28 | `remote/social.spoofy/mcp` | 2026-10-27T112138661465 -> 2026-10-28T062207736646 | 1 changed, 1 added | quiet |
| 2026-10-28 | `remote/io.github.canoydario847-cloud/privi-quantum` | 2026-10-27T210130805600 -> 2026-10-28T062204799359 | 4 changed, 8 added | quiet |
| 2026-10-28 | `remote/com.probativegrowth/legal-marketing-data.5` | 2026-10-27T054105269400 -> 2026-10-28T062204604036 | 6 changed (every tool) | quiet |
| 2026-10-28 | `remote/com.probativegrowth/legal-marketing-data.3` | 2026-10-27T054105382286 -> 2026-10-28T062204614215 | 6 changed (every tool) | quiet |
| 2026-10-28 | `remote/ai.1court.state/court-directory` | 2026-10-27T145855856831 -> 2026-10-28T062204834915 | 2 changed | quiet |
| 2026-10-28 | `remote/io.pocketcaddie/drills` | 2026-10-26T211454963942 -> 2026-10-28T062204010596 | 2 changed, 1 added | quiet |
| 2026-10-28 | `remote/com.siliconfloor/silicon-floor` | 2026-10-27T112127775426 -> 2026-10-28T062203133431 | 15 changed | quiet |
| 2026-10-28 | `remote/com.idosgames/platform` | 2026-10-26T052249345394 -> 2026-10-28T062204052698 | 2 changed, 1 added | quiet |
| 2026-10-28 | `remote/studio.gradients/mcp` | 2026-10-27T210205208947 -> 2026-10-28T062202484658 | 1 changed | quiet |
| 2026-10-28 | `remote/io.pitchboom/pitchboom` | 2026-10-27T210128780259 -> 2026-10-28T062202853565 | 2 changed | quiet |
| 2026-10-28 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-10-27T112221268375 -> 2026-10-28T062200692457 | 2 changed | quiet |
| 2026-10-28 | `remote/fi.akkilahdot/travel-search` | 2026-10-27T210202175744 -> 2026-10-28T062158703773 | 1 changed | quiet |
| 2026-10-28 | `remote/io.github.wwwnlab/rest-area` | 2026-10-26T133426446038 -> 2026-10-28T062157895236 | 5 changed | quiet |
| 2026-10-28 | `remote/site.chatgpt.orellise.relay-agent-services/relay` | 2026-10-27T112210927158 -> 2026-10-28T062157648723 | 1 added | quiet |
| 2026-10-28 | `remote/io.github.jakegallen/poascan` | 2026-10-27T210136274770 -> 2026-10-28T062155547808 | 1 changed, 3 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 35776 substantive, 19463 that changed only numbers (a catalogue counter ticking, a date), 687 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 30394 | 12161 | 18233 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 891 | 891 | 0 | 0 |
| `caseyjhand.com` | 238 | 238 | 0 | 0 |
| `sistaminuten.se` | 163 | 5 | 0 | 158 |
| `afbudsrejser.dk` | 162 | 5 | 0 | 157 |
| `akkilahdot.fi` | 162 | 5 | 0 | 157 |
| `restplass.no` | 162 | 5 | 0 | 157 |
| `socialloop.ai` | 156 | 156 | 0 | 0 |
| `remoshift.com` | 132 | 8 | 124 | 0 |
| `revmesh2074.workers.dev` | 129 | 116 | 13 | 0 |
| `fundinglandscape.com` | 125 | 80 | 45 | 0 |
| 6145 other operators | 20871 | 19765 | 1048 | 58 |
