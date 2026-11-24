# MCP server tool changes

Last change observed 2026-11-24T17:04:34+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 18238 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 43073 hosted endpoints (read daily, and every four hours while they keep changing).

133462 changes to a tool definition: 5329 npm releases (5083 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 128133 readings of hosted servers that found their tools changed; 4980 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-24 | `remote/io.github.christopherjjellison-maker/zorvu` | 2026-11-24T050413777748 -> 2026-11-24T170435253254 | 1 added | quiet |
| 2026-11-24 | `remote/today.thekorean/news` | 2026-11-21T130616359978 -> 2026-11-24T170411759259 | 1 added | quiet |
| 2026-11-24 | `remote/uk.co.speedi/availability` | 2026-11-21T130615212851 -> 2026-11-24T170406508872 | 1 added | quiet |
| 2026-11-24 | `remote/fr.publicoffre/marches-publics` | 2026-11-23T185544324540 -> 2026-11-24T170358274618 | 2 changed, 2 added | quiet |
| 2026-11-24 | `remote/fr.projet-ariane/ariane-orientation` | 2026-10-11T203728363973 -> 2026-11-24T170356727111 | 1 changed | quiet |
| 2026-11-24 | `remote/ai.modulos/demo-booking` | 2026-11-18T135945954785 -> 2026-11-24T170346988261 | 2 changed | quiet |
| 2026-11-24 | `remote/io.github.Seifollahi/markolis` | 2026-11-10T220145799353 -> 2026-11-24T170344879089 | 5 changed (every tool) | quiet |
| 2026-11-24 | `remote/studio.gradients/mcp` | 2026-11-24T050405041818 -> 2026-11-24T170333856087 | 1 changed | quiet |
| 2026-11-24 | `remote/io.github.EasyGerber/easygerber` | 2026-11-21T130613153877 -> 2026-11-24T170321520574 | 5 changed | quiet |
| 2026-11-24 | `remote/com.conferencefindr/events` | 2026-11-03T145007485565 -> 2026-11-24T170315988938 | 1 changed, 1 added | quiet |
| 2026-11-24 | `remote/com.zaimhub/catalog` | 2026-11-11T230904208849 -> 2026-11-24T170313749828 | 4 changed | quiet |
| 2026-11-24 | `remote/com.yangopen/mcp` | 2026-11-17T234414073179 -> 2026-11-24T170306945002 | 1 changed | quiet |
| 2026-11-24 | `remote/xn--3ds443g.xn--s7y/duan-online` | 2026-11-22T150815975344 -> 2026-11-24T170306531344 | 13 changed | quiet |
| 2026-11-24 | `remote/com.xmlvalid/xmlvalid` | 2026-11-24T050523484065 -> 2026-11-24T170305992739 | 1 changed | quiet |
| 2026-11-24 | `remote/io.github.XGamesFun/solana-kit` | 2026-11-22T104930868058 -> 2026-11-24T170304242917 | 1 changed | quiet |
| 2026-11-24 | `remote/fi.akkilahdot/travel-search` | 2026-11-24T050403207320 -> 2026-11-24T170301979779 | 1 changed | quiet |
| 2026-11-24 | `remote/io.github.worklore/worklore` | 2026-10-27T112209409562 -> 2026-11-24T170254264706 | 1 added | quiet |
| 2026-11-24 | `remote/ai.usedby/usedby` | 2026-11-24T050521383822 -> 2026-11-24T170253722934 | 1 changed | quiet |
| 2026-11-24 | `remote/com.theagentcolosseum/agent-colosseum` | 2026-11-24T050521846054 -> 2026-11-24T170249928515 | 6 changed (every tool) | quiet |
| 2026-11-24 | `remote/io.taifoon/coordination-layer.1` | 2026-11-23T185843448187 -> 2026-11-24T170243689884 | 1 changed | quiet |
| 2026-11-24 | `remote/io.suverse.www/catalog` | 2026-11-24T050521539275 -> 2026-11-24T170243363702 | 3 changed | quiet |
| 2026-11-24 | `remote/se.sistaminuten/travel-search` | 2026-11-24T050519827840 -> 2026-11-24T170230895961 | 1 changed | quiet |
| 2026-11-24 | `remote/io.github.christianscode1994/volatiai` | 2026-11-23T185354590314 -> 2026-11-24T170225796768 | 1 added | quiet |
| 2026-11-24 | `remote/com.visdenda/public` | 2026-11-23T185354442547 -> 2026-11-24T170224212100 | 1 changed, 2 added | quiet |
| 2026-11-24 | `remote/nl.prijsprofeet/prijsprofeet-de` | 2026-11-21T130648767032 -> 2026-11-24T170221027709 | 1 removed | quiet |
| 2026-11-24 | `remote/io.github.suanrongbaicai/vibecodepicks` | 2026-11-17T164828060047 -> 2026-11-24T170218387097 | 2 changed | quiet |
| 2026-11-24 | `remote/uk.co.paintdial/paintdial` | 2026-11-19T123902008936 -> 2026-11-24T170217261251 | 1 changed | quiet |
| 2026-11-24 | `remote/dev.vetagent/vetagent` | 2026-11-23T185347326416 -> 2026-11-24T170217706933 | 1 changed | quiet |
| 2026-11-24 | `remote/com.orbitfour/domains` | 2026-11-04T150744484527 -> 2026-11-24T170216134919 | 3 changed | quiet |
| 2026-11-24 | `remote/io.github.veredamonte-glitch/verithic` | 2026-10-26T133439967461 -> 2026-11-24T170219947224 | 13 changed | quiet |
| 2026-11-24 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-23T185346197554 -> 2026-11-24T170217846833 | 3 changed | quiet |
| 2026-11-24 | `remote/dev.workers.veritas-silicea.veritas-silicea-shop/art` | 2026-11-23T185344060794 -> 2026-11-24T170214913600 | 1 changed | quiet |
| 2026-11-24 | `remote/org.omenz.www/agent-tools` | 2026-11-24T050516649487 -> 2026-11-24T170214509377 | 3 added | quiet |
| 2026-11-24 | `remote/io.github.SecondShotAI/verifylite` | 2026-11-23T185343524806 -> 2026-11-24T170215807111 | 1 changed | quiet |
| 2026-11-24 | `remote/com.onecoworking.www/mcp` | 2026-10-26T133904850222 -> 2026-11-24T170215112811 | 1 changed | quiet |
| 2026-11-24 | `remote/io.github.jhonnysabino/moedux` | 2026-11-24T050516839028 -> 2026-11-24T170208459681 | 6 added | quiet |
| 2026-11-24 | `remote/com.mfgcalcs/mfgcalcs` | 2026-09-23T161030564360 -> 2026-11-24T170205947810 | 1 changed | quiet |
| 2026-11-24 | `remote/io.untax/untax` | 2026-11-20T105638832571 -> 2026-11-24T170156442588 | 12 changed, 8 added, 69 removed (every tool) | quiet |
| 2026-11-24 | `remote/gg.unicum/wot-stats` | 2026-11-24T050356289093 -> 2026-11-24T170156233624 | 3 added | quiet |
| 2026-11-24 | `remote/com.herbertandphyllis/mcp` | 2026-11-23T185756675215 -> 2026-11-24T170149996656 | 1 changed | quiet |
| 2026-11-24 | `remote/io.github.paulieb89/uk-due-diligence-mcp` | 2026-11-21T151020411045 -> 2026-11-24T170148219822 | 2 changed | quiet |
| 2026-11-24 | `remote/io.github.gokaytr/geoniks.1` | 2026-11-17T164813108221 -> 2026-11-24T170145808543 | 1 changed | review |
| 2026-11-24 | `remote/com.ferntool/ip` | 2026-11-21T130644046619 -> 2026-11-24T170141028624 | 1 changed | quiet |
| 2026-11-24 | `remote/it.expatliving/data` | 2026-11-21T151053590186 -> 2026-11-24T170139544936 | 2 changed | quiet |
| 2026-11-24 | `remote/app.designmdpro/designmdpro` | 2026-11-23T185739612134 -> 2026-11-24T170133013291 | 4 changed (every tool) | quiet |
| 2026-11-24 | `remote/io.github.tradinglookup/data` | 2026-11-24T050352315184 -> 2026-11-24T170131067582 | 1 changed | quiet |
| 2026-11-24 | `remote/io.github.Schoasch/backtesting-arena` | 2026-11-17T135628996768 -> 2026-11-24T170131869295 | 4 changed | quiet |
| 2026-11-24 | `remote/sg.cashew/mcp` | 2026-11-13T150606996409 -> 2026-11-24T170129141310 | 1 changed | quiet |
| 2026-11-24 | `remote/io.github.TMcodingarc/bull-otc` | 2026-11-23T185732582332 -> 2026-11-24T170126488829 | 15 changed, 2 added | quiet |
| 2026-11-24 | `remote/online.aypiai.www/rever` | 2026-11-23T185724258811 -> 2026-11-24T170120272917 | 39 changed | quiet |
| 2026-11-24 | `remote/io.github.rodriguem75/assuranceslabs` | 2026-11-22T104627854689 -> 2026-11-24T170119709039 | 1 changed, 1 added | quiet |
| 2026-11-24 | `remote/ca.tonbot.tolca/tolca` | 2026-11-09T170121476817 -> 2026-11-24T170119912335 | 1 changed | quiet |
| 2026-11-24 | `remote/com.todayinabq/abq` | 2026-11-16T163008112347 -> 2026-11-24T170117986202 | 6 changed, 4 added (every tool) | quiet |
| 2026-11-24 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-23T185236767097 -> 2026-11-24T170102668244 | 1 changed | quiet |
| 2026-11-24 | `remote/com.swellcabin/surf` | 2026-11-22T104139497900 -> 2026-11-24T170037636391 | 3 changed | quiet |
| 2026-11-24 | `remote/gs.sundo/sundogs` | 2026-11-15T115429082603 -> 2026-11-24T170038003642 | 1 changed | quiet |
| 2026-11-24 | `remote/com.andque/agent-data` | 2026-11-24T050344060981 -> 2026-11-24T170022663789 | 18 added, 126 removed | quiet |
| 2026-11-24 | `remote/ai.stimhaus/emma-for-agents` | 2026-11-13T120345579444 -> 2026-11-24T170017300443 | 1 changed, 1 added | quiet |
| 2026-11-24 | `remote/com.stayotter/stay-otter` | 2026-11-21T215743958711 -> 2026-11-24T170014819650 | 1 changed | quiet |
| 2026-11-24 | `remote/ai.stablenews/news` | 2026-11-19T231824960266 -> 2026-11-24T170006472584 | 3 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 89112 substantive, 43161 that changed only numbers (a catalogue counter ticking, a date), 1189 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 73016 | 32809 | 40207 | 0 |
| `a2awire.com` | 3838 | 3838 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 527 | 527 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 401 | 401 | 0 | 0 |
| `revmesh2074.workers.dev` | 367 | 312 | 55 | 0 |
| `sistaminuten.se` | 277 | 7 | 0 | 270 |
| `afbudsrejser.dk` | 276 | 7 | 0 | 269 |
| `akkilahdot.fi` | 276 | 7 | 0 | 269 |
| `restplass.no` | 276 | 7 | 0 | 269 |
| `socialloop.ai` | 267 | 267 | 0 | 0 |
| 11256 other operators | 51120 | 48109 | 2899 | 112 |
