# MCP server tool changes

Last change observed 2026-11-04T12:38:35+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

74487 changes to a tool definition: 3094 npm releases (2848 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 71393 readings of hosted servers that found their tools changed; 3311 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-04 | `remote/io.taifoon/coordination-layer.1` | 2026-11-03T195708203808 -> 2026-11-04T123836537441 | 1 changed | quiet |
| 2026-11-04 | `remote/ai.startuphub/startuphub` | 2026-11-03T195707903179 -> 2026-11-04T123836607897 | 80 changed | quiet |
| 2026-11-04 | `remote/se.sistaminuten/travel-search` | 2026-11-04T005934227684 -> 2026-11-04T123836362637 | 1 changed | quiet |
| 2026-11-04 | `remote/com.diveratlas/diver-atlas` | 2026-11-02T163408617039 -> 2026-11-04T123830777842 | 2 changed, 8 added | quiet |
| 2026-11-04 | `remote/io.github.Tomalarrrr/cyclesite-mcp-server` | 2026-11-03T144934781383 -> 2026-11-04T123830452824 | 2 changed | quiet |
| 2026-11-04 | `remote/sg.cashew/mcp` | 2026-11-02T163406976921 -> 2026-11-04T123831112600 | 21 changed | quiet |
| 2026-11-04 | `remote/io.github.nimitt-IN/india-cyber-regulations` | 2026-11-03T195701042661 -> 2026-11-04T123830086938 | 2 changed | quiet |
| 2026-11-04 | `remote/no.restplass/travel-search` | 2026-11-04T005952989329 -> 2026-11-04T123822599020 | 1 changed | quiet |
| 2026-11-04 | `remote/com.themachinerentalscam/rental-quotes` | 2026-11-02T163629955814 -> 2026-11-04T123822641845 | 5 changed (every tool) | quiet |
| 2026-11-04 | `remote/co.vincap/listed-wine-companies` | 2026-11-02T163324878228 -> 2026-11-04T123822594247 | 1 added | quiet |
| 2026-11-04 | `remote/com.usepiku/piku` | 2026-11-02T163313476732 -> 2026-11-04T123825341750 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.imokokok/insight-oracle` | 2026-11-03T195825404660 -> 2026-11-04T123823384665 | 1 changed | quiet |
| 2026-11-04 | `remote/com.tubesaku/creator-insights` | 2026-11-03T195652869678 -> 2026-11-04T123820229475 | 3 changed | quiet |
| 2026-11-04 | `remote/show.globalconnect.www/gcs` | 2026-11-02T163558906536 -> 2026-11-04T123820187346 | 2 changed | quiet |
| 2026-11-04 | `remote/studio.gradients/mcp` | 2026-11-04T005903971358 -> 2026-11-04T123817129914 | 1 changed | quiet |
| 2026-11-04 | `remote/dk.afbudsrejser/travel-search` | 2026-11-04T005945322215 -> 2026-11-04T123816156368 | 1 changed | quiet |
| 2026-11-04 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-04T005902144022 -> 2026-11-04T123815100060 | 2 changed | quiet |
| 2026-11-04 | `remote/fi.akkilahdot/travel-search` | 2026-11-04T005901830436 -> 2026-11-04T123815205762 | 1 changed | quiet |
| 2026-11-04 | `remote/de.objelio/immobiliensuche` | 2026-11-03T024246172485 -> 2026-11-04T123815393471 | 3 changed | quiet |
| 2026-11-04 | `remote/tech.tchin/tchin` | 2026-11-02T163212697333 -> 2026-11-04T123815118806 | 1 changed | quiet |
| 2026-11-04 | `remote/com.walletmcppass/wallet-mcp` | 2026-11-02T163549895115 -> 2026-11-04T123812527413 | 2 changed (every tool) | quiet |
| 2026-11-04 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-03T144938447502 -> 2026-11-04T123812684663 | 2 changed | quiet |
| 2026-11-04 | `remote/io.github.Billibo6/unlockpulse` | 2026-11-03T122742887332 -> 2026-11-04T123810083689 | 5 changed (every tool) | quiet |
| 2026-11-04 | `remote/com.swishrjobs/swishrjobs` | 2026-11-03T195643495764 -> 2026-11-04T123810608516 | 2 changed, 14 added | quiet |
| 2026-11-04 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-04T005859599314 -> 2026-11-04T123811798377 | 3 changed | quiet |
| 2026-11-04 | `remote/fun.trnch/trnch` | 2026-11-03T024218559038 -> 2026-11-04T123809419714 | 2 changed | quiet |
| 2026-11-04 | `remote/io.github.soyeladice-svg/bursia-utils.1` | 2026-11-02T163534793148 -> 2026-11-04T123808407971 | 1 changed | quiet |
| 2026-11-04 | `remote/fyi.toothache/dentists` | 2026-11-03T122741065889 -> 2026-11-04T123808011423 | 1 changed | quiet |
| 2026-11-04 | `remote/com.tealmac/ui` | 2026-11-03T144859595774 -> 2026-11-04T123810233459 | 5 added | quiet |
| 2026-11-04 | `remote/com.shipshapedata/shipshape-data-docs` | 2026-11-03T122641215703 -> 2026-11-04T123809221216 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-04T005933984663 -> 2026-11-04T123804345045 | 2 changed, 6 added, 3 removed | review |
| 2026-11-04 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-04T005853563942 -> 2026-11-04T123804851642 | 1 changed | quiet |
| 2026-11-04 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-04T005853783170 -> 2026-11-04T123806205247 | 2 changed | quiet |
| 2026-11-04 | `remote/xyz.t0ll/toll` | 2026-11-03T195758961832 -> 2026-11-04T123801294898 | 1 changed | quiet |
| 2026-11-04 | `remote/media.southpow/fact` | 2026-11-03T144756877653 -> 2026-11-04T123801056580 | 500 added | review |
| 2026-11-04 | `remote/io.github.exquad/thecablecode` | 2026-11-03T195501177499 -> 2026-11-04T123802968225 | 5 changed, 2 added | review |
| 2026-11-04 | `remote/io.github.cyanheads/secedgar-mcp-server` | 2026-11-03T144724757367 -> 2026-11-04T123759893477 | 3 changed | quiet |
| 2026-11-04 | `remote/app.seatsherpa/rides` | 2026-11-03T195539555213 -> 2026-11-04T123759933028 | 5 changed | quiet |
| 2026-11-04 | `remote/app.openkrill/buyersignals` | 2026-11-03T144743449108 -> 2026-11-04T123801340850 | 4 changed | quiet |
| 2026-11-04 | `remote/com.tallybuy/tallybuy` | 2026-11-03T195457363195 -> 2026-11-04T123759966734 | 1 changed | quiet |
| 2026-11-04 | `remote/com.starlecta/influencer-tools` | 2026-11-02T163420467198 -> 2026-11-04T123801304150 | 1 changed | quiet |
| 2026-11-04 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-04T005847661575 -> 2026-11-04T123758976314 | 1 changed | quiet |
| 2026-11-04 | `remote/com.crm-connector/crm-connector` | 2026-11-03T195630645910 -> 2026-11-04T123757947954 | 3 changed, 2 added | quiet |
| 2026-11-04 | `remote/re.rundata/temps-reel` | 2026-11-03T144708069593 -> 2026-11-04T123759606648 | 3 changed | quiet |
| 2026-11-04 | `remote/app.sunsetstrip/gta6` | 2026-11-04T005848339496 -> 2026-11-04T123757525361 | 1 changed | quiet |
| 2026-11-04 | `remote/ai.shorti/shorti` | 2026-11-02T185342346589 -> 2026-11-04T123758708353 | 1 changed | quiet |
| 2026-11-04 | `remote/ai.rokha/rokha` | 2026-11-04T005928180041 -> 2026-11-04T123757001729 | 14 changed | quiet |
| 2026-11-04 | `remote/page.ship/ship-page` | 2026-11-02T163347951716 -> 2026-11-04T123756285395 | 4 changed | quiet |
| 2026-11-04 | `remote/io.stockmap/stockmap` | 2026-11-02T163625117564 -> 2026-11-04T123756093061 | 2 changed | quiet |
| 2026-11-04 | `remote/io.github.opennodes-io/opennodes` | 2026-11-04T005927606175 -> 2026-11-04T123757148871 | 1 changed | quiet |
| 2026-11-04 | `remote/app.sprkly/sprkly` | 2026-11-03T122632100449 -> 2026-11-04T123756817311 | 10 changed, 4 added | review |
| 2026-11-04 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-11-04T005846704604 -> 2026-11-04T123755346776 | 2 changed | quiet |
| 2026-11-04 | `remote/io.github.donofdebt/ouncescout` | 2026-11-02T162922557231 -> 2026-11-04T123754884357 | 4 added | quiet |
| 2026-11-04 | `remote/io.github.davidgringras/scrutica` | 2026-11-03T024247313787 -> 2026-11-04T123755460460 | 1 changed | quiet |
| 2026-11-04 | `remote/com.risetive/mcp` | 2026-11-02T163254325552 -> 2026-11-04T123753955730 | 1 changed | review |
| 2026-11-04 | `remote/com.remoshift/jobs` | 2026-11-04T005843022648 -> 2026-11-04T123752789366 | 1 changed | quiet |
| 2026-11-04 | `remote/asia.simpler/simpler-asia` | 2026-11-03T144717180053 -> 2026-11-04T123753982705 | 3 changed | review |
| 2026-11-04 | `remote/com.shipshapedata/shipshape-data` | 2026-11-03T122627479128 -> 2026-11-04T123753098887 | 1 changed | quiet |
| 2026-11-04 | `remote/com.sfxmint/sounds` | 2026-11-03T122626738365 -> 2026-11-04T123752237623 | 2 changed | quiet |
| 2026-11-04 | `remote/com.serdaroztetik/call-me` | 2026-11-03T144701210682 -> 2026-11-04T123752379069 | 9 changed (every tool) | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 46472 substantive, 27198 that changed only numbers (a catalogue counter ticking, a date), 817 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 41415 | 15875 | 25540 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1249 | 1249 | 0 | 0 |
| `caseyjhand.com` | 333 | 333 | 0 | 0 |
| `sistaminuten.se` | 193 | 6 | 0 | 187 |
| `afbudsrejser.dk` | 192 | 6 | 0 | 186 |
| `akkilahdot.fi` | 192 | 6 | 0 | 186 |
| `restplass.no` | 192 | 6 | 0 | 186 |
| `socialloop.ai` | 185 | 185 | 0 | 0 |
| `remoshift.com` | 162 | 13 | 149 | 0 |
| `fundinglandscape.com` | 147 | 89 | 58 | 0 |
| `revmesh2074.workers.dev` | 146 | 128 | 18 | 0 |
| 7362 other operators | 27740 | 26235 | 1433 | 72 |
