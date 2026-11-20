# MCP server tool changes

Last change observed 2026-11-20T10:59:36+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

120753 changes to a tool definition: 4843 npm releases (4597 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 115910 readings of hosted servers that found their tools changed; 4545 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-20 | `remote/io.github.liad142/yedapo` | 2026-11-19T020453830084 -> 2026-11-20T105940371734 | 2 changed (every tool) | quiet |
| 2026-11-20 | `remote/io.github.speeedy10/foxify-x402-agent-commerce-payment-preflight` | 2026-10-26T133618872802 -> 2026-11-20T105937487687 | 2 changed | quiet |
| 2026-11-20 | `remote/com.veterans-rights/bva-corpus` | 2026-11-14T140218331312 -> 2026-11-20T105934297666 | 1 changed | quiet |
| 2026-11-20 | `remote/no.restplass/travel-search` | 2026-11-20T074941987088 -> 2026-11-20T105921121135 | 1 changed | quiet |
| 2026-11-20 | `remote/com.superstables/superstables.1` | 2026-11-10T030051728435 -> 2026-11-20T105907259787 | 1 changed | quiet |
| 2026-11-20 | `remote/io.github.rich937/lendmail` | 2026-11-16T163305106065 -> 2026-11-20T105905673274 | 3 changed | quiet |
| 2026-11-20 | `remote/com.kulicadvisory/aictionbot-werkbank` | 2026-11-19T231847002088 -> 2026-11-20T105904658437 | 2 changed | quiet |
| 2026-11-20 | `remote/io.deeplead/deeplead` | 2026-11-19T231845769628 -> 2026-11-20T105848577265 | 1 changed | quiet |
| 2026-11-20 | `remote/design.overflow/mcp` | 2026-11-16T163223283038 -> 2026-11-20T105843386704 | 1 changed | quiet |
| 2026-11-20 | `remote/dk.afbudsrejser/travel-search` | 2026-11-20T074940321406 -> 2026-11-20T105835939902 | 1 changed | quiet |
| 2026-11-20 | `remote/com.whatsonmiami/whats-on-miami` | 2026-11-16T163227130590 -> 2026-11-20T105821836920 | 1 changed | quiet |
| 2026-11-20 | `remote/studio.gradients/mcp` | 2026-11-20T075001871915 -> 2026-11-20T105820230772 | 1 changed | quiet |
| 2026-11-20 | `remote/io.github.wygogogo19/robotbase-web3` | 2026-11-06T144741214736 -> 2026-11-20T105818770774 | 2 changed | quiet |
| 2026-11-20 | `remote/io.github.ohad6k/viberaven-guides` | 2026-11-18T174112342928 -> 2026-11-20T105804472592 | 3 changed | quiet |
| 2026-11-20 | `remote/io.github.mooshee/untax` | 2026-11-16T163133817803 -> 2026-11-20T105748837502 | 2 changed, 8 removed | quiet |
| 2026-11-20 | `remote/fi.akkilahdot/travel-search` | 2026-11-20T075000855144 -> 2026-11-20T105746245043 | 1 changed | quiet |
| 2026-11-20 | `remote/global.uain/network` | 2026-11-18T080214434073 -> 2026-11-20T105741532929 | 1 changed, 1 added | quiet |
| 2026-11-20 | `remote/com.tutuesim/esim` | 2026-11-17T135641869450 -> 2026-11-20T105739847464 | 1 changed | quiet |
| 2026-11-20 | `remote/com.trendtemplate/templates` | 2026-11-20T074936026457 -> 2026-11-20T105732156501 | 2 changed | quiet |
| 2026-11-20 | `remote/io.zsign/zsign.1` | 2026-11-16T163420083960 -> 2026-11-20T105728428917 | 2 changed | quiet |
| 2026-11-20 | `remote/si.zazidljiva/mcp` | 2026-11-09T170237997000 -> 2026-11-20T105727654100 | 4 changed | quiet |
| 2026-11-20 | `remote/dev.zambo/zambo` | 2026-11-19T123811456503 -> 2026-11-20T105724312501 | 15 changed | quiet |
| 2026-11-20 | `remote/xyz.x402helper/mcp` | 2026-11-10T153331100910 -> 2026-11-20T105719878849 | 1 changed | quiet |
| 2026-11-20 | `remote/io.github.kwizzlesurp10-ctrl/x402orcle` | 2026-10-19T135311599960 -> 2026-11-20T105719070163 | 7 changed (every tool) | review |
| 2026-11-20 | `remote/com.todaywp/todaywp` | 2026-11-16T163053623479 -> 2026-11-20T105719404549 | 3 changed, 3 added, 5 removed (every tool) | quiet |
| 2026-11-20 | `remote/com.workers-rights/employment-law` | 2026-11-14T183345978292 -> 2026-11-20T105714229777 | 4 changed | quiet |
| 2026-11-20 | `remote/io.github.christianscode1994/volatiai` | 2026-11-16T163101663443 -> 2026-11-20T105711277461 | 1 added | quiet |
| 2026-11-20 | `remote/com.tfrooms/tf-rooms` | 2026-11-17T164655603686 -> 2026-11-20T105706524701 | 8 changed (every tool) | quiet |
| 2026-11-20 | `remote/uk.co.teas/shop` | 2026-11-15T115136304455 -> 2026-11-20T105656705154 | 4 added, 26 removed | quiet |
| 2026-11-20 | `remote/io.github.sonnykatongola-ops/resumakeai-mcp` | 2026-09-23T160851801051 -> 2026-11-20T105655400280 | 1 changed | quiet |
| 2026-11-20 | `remote/com.resollo/agent-api` | 2026-10-27T112434337692 -> 2026-11-20T105655497872 | 2 changed | quiet |
| 2026-11-20 | `remote/ai.oriiion/oriiion` | 2026-11-15T212306226425 -> 2026-11-20T105647125991 | 49 changed, 1 added | quiet |
| 2026-11-20 | `remote/io.untax/untax` | 2026-11-16T163039339980 -> 2026-11-20T105638832571 | 2 changed, 8 removed | quiet |
| 2026-11-20 | `remote/io.github.boriskendev/stormap` | 2026-11-02T163332698253 -> 2026-11-20T105635690586 | 1 changed, 1 added | review |
| 2026-11-20 | `remote/com.lazyweb/discovery` | 2026-11-04T200814340556 -> 2026-11-20T105637479860 | 8 changed | quiet |
| 2026-11-20 | `remote/com.launchshots/launchshots` | 2026-11-02T163906304383 -> 2026-11-20T105635792752 | 2 changed | quiet |
| 2026-11-20 | `remote/io.github.bostanyshop-rgb/growtsy` | 2026-11-10T220142428761 -> 2026-11-20T105622815243 | 11 changed, 5 added (every tool) | quiet |
| 2026-11-20 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-20T074940331617 -> 2026-11-20T105621665931 | 1 changed | quiet |
| 2026-11-20 | `remote/com.spacexploration/listings` | 2026-11-17T164559220816 -> 2026-11-20T105620419142 | 1 changed | quiet |
| 2026-11-20 | `remote/com.werop/catalog` | 2026-11-16T163303948034 -> 2026-11-20T105611299447 | 2 added | quiet |
| 2026-11-20 | `remote/com.veridionmarkets/disclosures` | 2026-11-17T031627880551 -> 2026-11-20T105609275007 | 1 changed | quiet |
| 2026-11-20 | `remote/ai.usedby/usedby` | 2026-11-19T231843518621 -> 2026-11-20T105608742098 | 1 changed | quiet |
| 2026-11-20 | `remote/com.test-well/testwell` | 2026-11-11T150024588172 -> 2026-11-20T105601872905 | 2 changed | quiet |
| 2026-11-20 | `remote/io.github.nirholas/threews-grok` | 2026-10-24T112922776695 -> 2026-11-20T105556751487 | 4 changed | quiet |
| 2026-11-20 | `remote/se.sistaminuten/travel-search` | 2026-11-20T074939075933 -> 2026-11-20T105556079210 | 1 changed | quiet |
| 2026-11-20 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-20T074956137910 -> 2026-11-20T105552729560 | 1 changed | quiet |
| 2026-11-20 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-19T231827642539 -> 2026-11-20T105549511865 | 1 changed | quiet |
| 2026-11-20 | `remote/app.seatsherpa/rides` | 2026-11-19T123503030187 -> 2026-11-20T105546372219 | 5 changed | quiet |
| 2026-11-20 | `remote/io.github.Ipayx-stellar/fx-audit` | 2026-09-23T160831138154 -> 2026-11-20T105545290071 | 4 changed (every tool) | quiet |
| 2026-11-20 | `remote/io.github.suprraz/webzum` | 2026-11-03T144902244048 -> 2026-11-20T105539916938 | 1 changed | quiet |
| 2026-11-20 | `remote/com.onlyworlds/mcp` | 2026-11-17T164839429341 -> 2026-11-20T105540659865 | 7 changed, 1 added | quiet |
| 2026-11-20 | `remote/io.github.hks409/nanukamachi` | 2026-11-09T170247644925 -> 2026-11-20T105539348443 | 6 changed | quiet |
| 2026-11-20 | `remote/fr.francestack/tax-payroll` | 2026-11-16T162946835495 -> 2026-11-20T105539906306 | 6 changed | quiet |
| 2026-11-20 | `remote/re.rundata/temps-reel` | 2026-11-20T074931917166 -> 2026-11-20T105532644655 | 2 changed | quiet |
| 2026-11-20 | `remote/ai.rokha/rokha` | 2026-11-17T164442874653 -> 2026-11-20T105527480980 | 1 changed | quiet |
| 2026-11-20 | `remote/io.github.wygogogo19/robotbase-mcp` | 2026-11-06T144512772060 -> 2026-11-20T105527572845 | 2 changed | quiet |
| 2026-11-20 | `remote/studio.restinprint/obituaries` | 2026-11-12T154629175372 -> 2026-11-20T105518924622 | 2 added | quiet |
| 2026-11-20 | `remote/com.coverage-rights/coverage-rights` | 2026-11-14T140254989438 -> 2026-11-20T105513718263 | 6 changed | quiet |
| 2026-11-20 | `remote/io.github.TMcodingarc/bull-otc` | 2026-11-19T123829158201 -> 2026-11-20T105509253533 | 1 changed | quiet |
| 2026-11-20 | `remote/com.achivx/stablescan` | 2026-11-19T231826066879 -> 2026-11-20T105504957504 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 78587 substantive, 41045 that changed only numbers (a catalogue counter ticking, a date), 1121 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 65549 | 27195 | 38354 | 0 |
| `a2awire.com` | 3571 | 3571 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 479 | 479 | 0 | 0 |
| `modevc.com` | 436 | 436 | 0 | 0 |
| `civai.co` | 384 | 384 | 0 | 0 |
| `revmesh2074.workers.dev` | 335 | 287 | 48 | 0 |
| `sistaminuten.se` | 261 | 6 | 0 | 255 |
| `afbudsrejser.dk` | 260 | 6 | 0 | 254 |
| `akkilahdot.fi` | 260 | 6 | 0 | 254 |
| `restplass.no` | 260 | 6 | 0 | 254 |
| `socialloop.ai` | 251 | 251 | 0 | 0 |
| 10514 other operators | 46366 | 43619 | 2643 | 104 |
