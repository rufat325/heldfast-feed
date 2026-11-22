# MCP server tool changes

Last change observed 2026-11-22T15:09:31+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

126898 changes to a tool definition: 5105 npm releases (4859 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 121793 readings of hosted servers that found their tools changed; 4681 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-22 | `remote/com.mikefluff/mikefluff` | 2026-11-20T160156445764 -> 2026-11-22T150932814932 | 6 changed | quiet |
| 2026-11-22 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-22T073258065020 -> 2026-11-22T150905998191 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.fmind/portfolio` | 2026-11-11T150006099562 -> 2026-11-22T150902199481 | 12 changed (every tool) | quiet |
| 2026-11-22 | `remote/xn--3ds443g.xn--s7y/duan-online` | 2026-11-18T140016139446 -> 2026-11-22T150815975344 | 2 added | quiet |
| 2026-11-22 | `remote/io.github.Ipayx-stellar/fx-audit` | 2026-11-21T151116248969 -> 2026-11-22T150814929635 | 2 changed | quiet |
| 2026-11-22 | `remote/io.suverse.versum/catalog` | 2026-11-22T104511964914 -> 2026-11-22T150754309969 | 3 changed | quiet |
| 2026-11-22 | `remote/io.taifoon/coordination-layer.1` | 2026-11-20T160033224874 -> 2026-11-22T150751986469 | 1 changed | quiet |
| 2026-11-22 | `remote/io.suverse.www/catalog` | 2026-11-22T104839006389 -> 2026-11-22T150751761338 | 3 changed | quiet |
| 2026-11-22 | `remote/se.sistaminuten/travel-search` | 2026-11-22T104833116365 -> 2026-11-22T150747112822 | 1 changed | quiet |
| 2026-11-22 | `remote/org.omenz.www/agent-tools` | 2026-11-22T073206539447 -> 2026-11-22T150729785969 | 1 changed, 3 added | quiet |
| 2026-11-22 | `remote/com.cadprops/cadprops` | 2026-11-01T135721816163 -> 2026-11-22T150654870679 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.TMcodingarc/bull-otc` | 2026-11-22T104631793243 -> 2026-11-22T150653286367 | 3 changed, 2 added | review |
| 2026-11-22 | `remote/il.co.taseli/taseli.1` | 2026-11-16T190048593848 -> 2026-11-22T150641270504 | 5 added | quiet |
| 2026-11-22 | `remote/io.github.1145-am/syracuse-mcp-server` | 2026-11-22T104349602760 -> 2026-11-22T150633301401 | 3 changed | review |
| 2026-11-22 | `remote/net.vaguslab/research` | 2026-09-23T161004144189 -> 2026-11-22T150549601665 | 3 changed (every tool) | quiet |
| 2026-11-22 | `remote/app.usesnippet/snippet` | 2026-11-22T073201163166 -> 2026-11-22T150547322975 | 1 added | quiet |
| 2026-11-22 | `remote/design.overflow/mcp` | 2026-11-20T105843386704 -> 2026-11-22T150547072657 | 1 changed | quiet |
| 2026-11-22 | `remote/com.metaintro/job-search` | 2026-11-21T151151303041 -> 2026-11-22T150541223133 | 7 changed, 1 added (every tool) | quiet |
| 2026-11-22 | `remote/com.uipolish/mcp` | 2026-11-22T104502699978 -> 2026-11-22T150529257381 | 1 changed | quiet |
| 2026-11-22 | `remote/com.hillsignal/hillsignalapp` | 2026-11-05T115535166822 -> 2026-11-22T150528749249 | 1 added | quiet |
| 2026-11-22 | `remote/studio.gradients/mcp` | 2026-11-22T104338833009 -> 2026-11-22T150527495354 | 1 changed | quiet |
| 2026-11-22 | `remote/network.skv/skv` | 2026-11-21T150910188167 -> 2026-11-22T150527528184 | 3 changed | quiet |
| 2026-11-22 | `remote/io.github.sudzikcoin/suverse-agent-assistant` | 2026-11-22T104456073980 -> 2026-11-22T150511561514 | 3 changed | quiet |
| 2026-11-22 | `remote/cn.com.bioinformatics/weishengxin` | 2026-11-17T135644674368 -> 2026-11-22T150510384501 | 1 changed | quiet |
| 2026-11-22 | `remote/io.atilab/mcp` | 2026-10-23T120632946651 -> 2026-11-22T150504873015 | 4 added | quiet |
| 2026-11-22 | `remote/fi.akkilahdot/travel-search` | 2026-11-22T104320041624 -> 2026-11-22T150502433683 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.send21io/mcp` | 2026-10-22T121848849023 -> 2026-11-22T150501000987 | 1 changed | quiet |
| 2026-11-22 | `remote/no.restplass/travel-search` | 2026-11-22T104435338754 -> 2026-11-22T150457184686 | 1 changed | quiet |
| 2026-11-22 | `remote/com.kulicadvisory/aictionbot-werkbank` | 2026-11-22T104405377603 -> 2026-11-22T150440724867 | 2 added, 93 removed | quiet |
| 2026-11-22 | `remote/io.github.christianscode1994/volatiai` | 2026-11-22T104256223582 -> 2026-11-22T150431662375 | 9 removed | quiet |
| 2026-11-22 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-22T104251069187 -> 2026-11-22T150425635893 | 3 changed | quiet |
| 2026-11-22 | `remote/io.github.cryptoconspiracy/vurto-swap` | 2026-11-19T231828747915 -> 2026-11-22T150416718412 | 1 changed | quiet |
| 2026-11-22 | `remote/com.supercyclehq/supercycle` | 2026-11-10T152653856922 -> 2026-11-22T150413290773 | 2 changed | quiet |
| 2026-11-22 | `remote/com.upheron/upheron` | 2026-11-16T163041467353 -> 2026-11-22T150412648315 | 2 changed | quiet |
| 2026-11-22 | `remote/dk.afbudsrejser/travel-search` | 2026-11-22T104322104452 -> 2026-11-22T150409729193 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.unbrowse-ai/unbrowse` | 2026-11-22T104237919674 -> 2026-11-22T150410548753 | 11 changed | quiet |
| 2026-11-22 | `remote/com.uncommonear/free-music-sound-effects` | 2026-11-17T135631068151 -> 2026-11-22T150409781935 | 18 changed (every tool) | quiet |
| 2026-11-22 | `remote/com.uibrik/components` | 2026-11-12T155139625742 -> 2026-11-22T150407676125 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.wygogogo19/robotbase-web3` | 2026-11-21T130556740812 -> 2026-11-22T150356250667 | 15 changed, 14 added | review |
| 2026-11-22 | `remote/io.github.MorrisMoe/soulintime` | 2026-11-17T234331183164 -> 2026-11-22T150355094382 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.kkfir13/valuedge` | 2026-11-19T123737220490 -> 2026-11-22T150334986854 | 2 changed | quiet |
| 2026-11-22 | `remote/com.sharpleftturn/ai-battle-arena` | 2026-11-22T104244836813 -> 2026-11-22T150331996850 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-21T130608232805 -> 2026-11-22T150326644258 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.IDNSIDNS/tenderapi-mcp` | 2026-11-15T115442360049 -> 2026-11-22T150319476155 | 1 changed | quiet |
| 2026-11-22 | `remote/com.tamingdns/mcp` | 2026-11-22T073225652069 -> 2026-11-22T150311006538 | 1 changed | quiet |
| 2026-11-22 | `remote/io.trylode/lode` | 2026-11-22T104227450937 -> 2026-11-22T150308617256 | 1 added | quiet |
| 2026-11-22 | `remote/app.pitbi/pitbi` | 2026-11-22T104110962853 -> 2026-11-22T150308123409 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.joelp22-maker/referencesource` | 2026-11-20T105148494585 -> 2026-11-22T150240305660 | 5 changed | quiet |
| 2026-11-22 | `remote/com.othermindset/campus` | 2026-11-21T215650154911 -> 2026-11-22T150236944901 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.farenberglord-star/orb-studio` | 2026-11-21T130602102659 -> 2026-11-22T150233070738 | 9 added | quiet |
| 2026-11-22 | `remote/io.github.OptimNow/ai-pricing-hub` | 2026-11-21T130601966040 -> 2026-11-22T150232195057 | 8 changed (every tool) | quiet |
| 2026-11-22 | `remote/io.github.pugarte7/spanish-top-tech-companies` | 2026-11-21T215743053994 -> 2026-11-22T150235263645 | 1 changed | quiet |
| 2026-11-22 | `remote/finance.souvenir/coins` | 2026-11-19T231824577163 -> 2026-11-22T150229601564 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-22T104114056210 -> 2026-11-22T150224640728 | 1 changed | quiet |
| 2026-11-22 | `remote/com.tailthemes/tailthemes` | 2026-09-23T163023437657 -> 2026-11-22T150223688843 | 1 changed | quiet |
| 2026-11-22 | `remote/com.notematics/notematics` | 2026-11-19T020407052904 -> 2026-11-22T150215640025 | 3 changed | quiet |
| 2026-11-22 | `remote/com.studiotvai/llm-vram` | 2026-11-22T104134153572 -> 2026-11-22T150210765262 | 2 changed | quiet |
| 2026-11-22 | `remote/io.strategyarena/strategyarena` | 2026-11-22T104131999595 -> 2026-11-22T150209007144 | 3 changed | quiet |
| 2026-11-22 | `remote/com.praesago/praesago` | 2026-11-13T013152012233 -> 2026-11-22T150206666569 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.Kromatic-Innovation/neumann` | 2026-11-21T150628030615 -> 2026-11-22T150203876002 | 10 changed, 3 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 82717 substantive, 43020 that changed only numbers (a catalogue counter ticking, a date), 1161 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 69283 | 29077 | 40206 | 0 |
| `a2awire.com` | 3571 | 3571 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 516 | 516 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 401 | 401 | 0 | 0 |
| `revmesh2074.workers.dev` | 361 | 307 | 54 | 0 |
| `sistaminuten.se` | 270 | 6 | 0 | 264 |
| `afbudsrejser.dk` | 269 | 6 | 0 | 263 |
| `akkilahdot.fi` | 269 | 6 | 0 | 263 |
| `restplass.no` | 269 | 6 | 0 | 263 |
| `socialloop.ai` | 260 | 260 | 0 | 0 |
| 10826 other operators | 48608 | 45740 | 2760 | 108 |
