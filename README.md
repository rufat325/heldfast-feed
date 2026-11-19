# MCP server tool changes

Last change observed 2026-11-19T16:26:53+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

117721 changes to a tool definition: 4741 npm releases (4495 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 112980 readings of hosted servers that found their tools changed; 4451 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-19 | `remote/io.github.Fizzl13/x402-doctor` | 2026-11-17T164859750815 -> 2026-11-19T162654486747 | 6 changed | quiet |
| 2026-11-19 | `remote/com.step2gcode/step2gcode` | 2026-11-16T163350454646 -> 2026-11-19T162626801692 | 1 changed | quiet |
| 2026-11-19 | `remote/de.stellenonline/jobsearch` | 2026-10-17T060412042590 -> 2026-11-19T162626150410 | 3 changed (every tool) | quiet |
| 2026-11-19 | `remote/coach.marian/eng-leadership-toolkit` | 2026-10-17T055945905363 -> 2026-11-19T162603559462 | 10 changed | quiet |
| 2026-11-19 | `remote/studio.gradients/mcp` | 2026-11-19T135858876977 -> 2026-11-19T162551451934 | 1 changed | quiet |
| 2026-11-19 | `remote/app.cleanchart/cleanchart` | 2026-11-19T124024155455 -> 2026-11-19T162534487697 | 1 changed | quiet |
| 2026-11-19 | `remote/fi.akkilahdot/travel-search` | 2026-11-19T135856390523 -> 2026-11-19T162527457992 | 1 changed | quiet |
| 2026-11-19 | `remote/com.step2gcode/step2gcode.1` | 2026-11-16T163335313737 -> 2026-11-19T162512421374 | 1 changed | quiet |
| 2026-11-19 | `remote/io.engineeringleaders/elc-trade` | 2026-10-26T133644220130 -> 2026-11-19T162515678840 | 8 changed | quiet |
| 2026-11-19 | `remote/io.engineeringleaders/elc-toolkit` | 2026-10-17T060342014954 -> 2026-11-19T162519978344 | 5 changed | quiet |
| 2026-11-19 | `remote/lol.shopat/deals` | 2026-11-19T123908371126 -> 2026-11-19T162508222885 | 1 changed, 1 added | quiet |
| 2026-11-19 | `remote/no.restplass/travel-search` | 2026-11-19T135905638841 -> 2026-11-19T162504560527 | 1 changed | quiet |
| 2026-11-19 | `remote/com.ou-reports/just-signal` | 2026-09-23T163140188972 -> 2026-11-19T162456850033 | 5 changed (every tool) | quiet |
| 2026-11-19 | `remote/dev.vetagent/vetagent` | 2026-11-19T123908891271 -> 2026-11-19T162445834406 | 2 changed | quiet |
| 2026-11-19 | `remote/io.github.cyanheads/worldbank-mcp-server` | 2026-11-12T154858105116 -> 2026-11-19T162442229678 | 9 changed (every tool) | quiet |
| 2026-11-19 | `remote/cz.gelato/eshop` | 2026-11-16T163250299919 -> 2026-11-19T162436779613 | 8 changed | quiet |
| 2026-11-19 | `remote/ai.withby/withby` | 2026-11-15T142649114087 -> 2026-11-19T162435627062 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.cyanheads/usda-mcp-server` | 2026-11-15T115532361793 -> 2026-11-19T162433099011 | 5 changed (every tool) | quiet |
| 2026-11-19 | `remote/gg.unicum/wot-stats` | 2026-11-19T020333767046 -> 2026-11-19T162429850769 | 1 changed, 3 added | quiet |
| 2026-11-19 | `remote/fr.capepartners/cape-exchange` | 2026-11-16T163230853220 -> 2026-11-19T162420467707 | 1 changed | quiet |
| 2026-11-19 | `remote/dk.afbudsrejser/travel-search` | 2026-11-19T135900406628 -> 2026-11-19T162412636664 | 1 changed | quiet |
| 2026-11-19 | `remote/app.wieldr/radar` | 2026-11-18T161718928253 -> 2026-11-19T162401360724 | 4 changed | quiet |
| 2026-11-19 | `remote/com.vidreno/mcp` | 2026-11-19T123746348354 -> 2026-11-19T162338259398 | 10 changed | quiet |
| 2026-11-19 | `remote/com.yedabase/yedabase` | 2026-11-02T163504123920 -> 2026-11-19T162331145559 | 1 changed | quiet |
| 2026-11-19 | `remote/com.usefreebox/freebox` | 2026-10-30T132906051631 -> 2026-11-19T162325992093 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-17T164606102522 -> 2026-11-19T162317671276 | 2 changed | quiet |
| 2026-11-19 | `remote/xyz.tereno/tereno` | 2026-11-18T135940122375 -> 2026-11-19T162307736004 | 2 changed, 1 added | quiet |
| 2026-11-19 | `remote/com.theagentcolosseum/agent-colosseum` | 2026-11-18T161748317963 -> 2026-11-19T162310215663 | 6 changed (every tool) | quiet |
| 2026-11-19 | `remote/com.trustbaselab/rcb-data` | 2026-11-18T161608343976 -> 2026-11-19T162303420451 | 1 changed | quiet |
| 2026-11-19 | `remote/fun.trnch/trnch-elysium` | 2026-11-19T020441779106 -> 2026-11-19T162301062452 | 1 changed | quiet |
| 2026-11-19 | `remote/fun.trnch/trnch` | 2026-11-19T020440986720 -> 2026-11-19T162259894317 | 1 changed | quiet |
| 2026-11-19 | `remote/io.smartvisuals/catalog` | 2026-10-26T133912654191 -> 2026-11-19T162318077446 | 2 added | quiet |
| 2026-11-19 | `remote/se.sistaminuten/travel-search` | 2026-11-19T135912666283 -> 2026-11-19T162257586677 | 1 changed | quiet |
| 2026-11-19 | `remote/com.trendtemplate/templates` | 2026-11-19T123704399334 -> 2026-11-19T162258076516 | 3 changed | quiet |
| 2026-11-19 | `remote/io.github.pugarte7/spanish-top-tech-companies` | 2026-11-16T162906823142 -> 2026-11-19T162252540514 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-19T135842534225 -> 2026-11-19T162246264461 | 1 changed | quiet |
| 2026-11-19 | `remote/com.skyalo/travel-connectivity-guide` | 2026-11-12T154948319984 -> 2026-11-19T162237581924 | 4 changed (every tool) | quiet |
| 2026-11-19 | `remote/io.github.cyanheads/switzerland-parliament-mcp-server` | 2026-11-16T122648568610 -> 2026-11-19T162235842803 | 7 changed (every tool) | quiet |
| 2026-11-19 | `remote/coach.marian/mentoring-inquiry-builder` | 2026-10-18T113457366909 -> 2026-11-19T162234205330 | 3 changed | quiet |
| 2026-11-19 | `remote/com.kondevs/content-hub` | 2026-11-16T163222888097 -> 2026-11-19T162229496464 | 1 changed | quiet |
| 2026-11-19 | `remote/com.sunflowerclinic/clinic` | 2026-11-09T165909857018 -> 2026-11-19T162226512478 | 3 changed | quiet |
| 2026-11-19 | `remote/com.kaicalls/kaicalls` | 2026-11-19T123847926950 -> 2026-11-19T162225924387 | 1 changed | quiet |
| 2026-11-19 | `remote/io.engineeringleaders/elc-partnership-builder` | 2026-10-25T102509735388 -> 2026-11-19T162212715464 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.bnth09productions-maker/scrapling-x402-store` | 2026-11-16T162813250945 -> 2026-11-19T162203242809 | 4 changed | review |
| 2026-11-19 | `remote/com.snaptoll/snaptoll` | 2026-10-27T112144723265 -> 2026-11-19T162154442300 | 1 changed | quiet |
| 2026-11-19 | `remote/com.sitecomb/check-website` | 2026-11-16T122552326794 -> 2026-11-19T162144002741 | 1 changed | quiet |
| 2026-11-19 | `remote/com.remoshift/jobs` | 2026-11-19T135837952224 -> 2026-11-19T162130663762 | 1 changed | quiet |
| 2026-11-19 | `remote/com.wardzo/wardzo.1` | 2026-11-02T163333621443 -> 2026-11-19T162112059389 | 2 changed | quiet |
| 2026-11-19 | `remote/co.productaura/productaura.1` | 2026-11-18T080226858960 -> 2026-11-19T162058778658 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.yschimke/compose-preview` | 2026-11-19T123501809049 -> 2026-11-19T162057077622 | 2 changed | quiet |
| 2026-11-19 | `remote/app.usesnippet/snippet` | 2026-11-19T123714250565 -> 2026-11-19T162044735334 | 1 changed | quiet |
| 2026-11-19 | `remote/com.screenrove/screenrove` | 2026-11-19T123502153045 -> 2026-11-19T162041087684 | 1 changed | quiet |
| 2026-11-19 | `remote/com.paywithprompt/pay-with-prompt` | 2026-11-16T162639858700 -> 2026-11-19T162024655490 | 2 added | review |
| 2026-11-19 | `remote/net.tnapplianceexchange/repair` | 2026-11-19T123632658957 -> 2026-11-19T161957117380 | 3 changed | quiet |
| 2026-11-19 | `remote/io.github.MsingathiM/swapeazi` | 2026-11-19T123603331424 -> 2026-11-19T161920375800 | 4 changed | quiet |
| 2026-11-19 | `remote/com.simafri/professional-email` | 2026-11-15T115351307866 -> 2026-11-19T161915080254 | 3 changed | quiet |
| 2026-11-19 | `remote/io.github.Fizzl13/presign-guard` | 2026-11-18T135221441513 -> 2026-11-19T161909846587 | 7 changed | quiet |
| 2026-11-19 | `remote/com.othermindset/campus` | 2026-11-19T020407641730 -> 2026-11-19T161900481904 | 1 changed | quiet |
| 2026-11-19 | `remote/io.github.codytodd-ui/pitchspark` | 2026-11-18T174039795717 -> 2026-11-19T161852851175 | 9 changed, 2 removed | quiet |
| 2026-11-19 | `remote/io.github.cloakmaster/pact0` | 2026-11-04T200724863310 -> 2026-11-19T161827568250 | 4 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 75624 substantive, 40990 that changed only numbers (a catalogue counter ticking, a date), 1107 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 63683 | 25330 | 38353 | 0 |
| `a2awire.com` | 3438 | 3438 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 477 | 477 | 0 | 0 |
| `civai.co` | 369 | 369 | 0 | 0 |
| `modevc.com` | 349 | 349 | 0 | 0 |
| `revmesh2074.workers.dev` | 321 | 276 | 45 | 0 |
| `sistaminuten.se` | 258 | 6 | 0 | 252 |
| `afbudsrejser.dk` | 257 | 6 | 0 | 251 |
| `akkilahdot.fi` | 257 | 6 | 0 | 251 |
| `restplass.no` | 257 | 6 | 0 | 251 |
| `socialloop.ai` | 248 | 248 | 0 | 0 |
| 10374 other operators | 45466 | 42772 | 2592 | 102 |
