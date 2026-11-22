# MCP server tool changes

Last change observed 2026-11-22T16:42:03+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

126986 changes to a tool definition: 5105 npm releases (4859 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 121881 readings of hosted servers that found their tools changed; 4683 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-22 | `remote/com.patchmcp/patch` | 2026-11-22T104353285019 -> 2026-11-22T164203878266 | 1 changed | quiet |
| 2026-11-22 | `remote/xyz.tereno/tereno` | 2026-11-21T215742299704 -> 2026-11-22T164202607485 | 2 changed, 1 added | review |
| 2026-11-22 | `remote/com.theagentcolosseum/agent-colosseum` | 2026-11-21T215743989221 -> 2026-11-22T164205108794 | 6 changed (every tool) | quiet |
| 2026-11-22 | `remote/studio.gradients/mcp` | 2026-11-22T150527495354 -> 2026-11-22T164202478506 | 1 changed | quiet |
| 2026-11-22 | `remote/se.sistaminuten/travel-search` | 2026-11-22T150747112822 -> 2026-11-22T164202469899 | 1 changed | quiet |
| 2026-11-22 | `remote/io.suverse.www/catalog` | 2026-11-22T150751761338 -> 2026-11-22T164203441615 | 1 changed | quiet |
| 2026-11-22 | `remote/co.ibda/ibda` | 2026-11-22T073231845266 -> 2026-11-22T164202035845 | 1 added | quiet |
| 2026-11-22 | `remote/app.hyperwave.www/wavetable-tools` | 2026-11-21T014934250120 -> 2026-11-22T164202303469 | 13 changed (every tool) | quiet |
| 2026-11-22 | `remote/org.omenz.www/agent-tools` | 2026-11-22T150729785969 -> 2026-11-22T164201624480 | 2 changed, 2 added | quiet |
| 2026-11-22 | `remote/fi.akkilahdot/travel-search` | 2026-11-22T150502433683 -> 2026-11-22T164200917183 | 1 changed | quiet |
| 2026-11-22 | `remote/no.restplass/travel-search` | 2026-11-22T150457184686 -> 2026-11-22T164159779653 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.sudzikcoin/suverse-agent-assistant` | 2026-11-22T150511561514 -> 2026-11-22T164200438871 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-22T150905998191 -> 2026-11-22T164201064873 | 1 changed | quiet |
| 2026-11-22 | `remote/com.kulicadvisory/aictionbot-werkbank` | 2026-11-22T150440724867 -> 2026-11-22T164158580326 | 1 changed, 1 added | quiet |
| 2026-11-22 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-22T150425635893 -> 2026-11-22T164159444715 | 1 changed | quiet |
| 2026-11-22 | `remote/dk.afbudsrejser/travel-search` | 2026-11-22T150409729193 -> 2026-11-22T164157668417 | 1 changed | quiet |
| 2026-11-22 | `remote/com.uncommonear/free-music-sound-effects` | 2026-11-22T150409781935 -> 2026-11-22T164157556782 | 1 changed | quiet |
| 2026-11-22 | `remote/io.suverse.versum/catalog` | 2026-11-22T150754309969 -> 2026-11-22T164158164785 | 1 changed | quiet |
| 2026-11-22 | `remote/tools.systra/systra-tools` | 2026-11-21T150842978252 -> 2026-11-22T164155971288 | 2 changed | quiet |
| 2026-11-22 | `remote/io.github.IDNSIDNS/tenderapi-mcp` | 2026-11-22T150319476155 -> 2026-11-22T164155503091 | 1 changed | quiet |
| 2026-11-22 | `remote/app.usesnippet/snippet` | 2026-11-22T150547322975 -> 2026-11-22T164153661857 | 1 changed | quiet |
| 2026-11-22 | `remote/sg.tanatasa/tanatasa` | 2026-11-22T104352783223 -> 2026-11-22T164153940500 | 2 changed | quiet |
| 2026-11-22 | `remote/io.github.SeoScoreAPI/seoscoreapi-mcp` | 2026-11-22T150111073730 -> 2026-11-22T164153149931 | 5 changed | review |
| 2026-11-22 | `remote/com.sulihuli/catalog` | 2026-11-21T215701615452 -> 2026-11-22T164152426555 | 1 changed | quiet |
| 2026-11-22 | `remote/com.timeofmeeting/time-of-meeting` | 2026-11-20T074930347025 -> 2026-11-22T164150869280 | 3 changed | quiet |
| 2026-11-22 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-22T150224640728 -> 2026-11-22T164150461007 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.codytodd-ui/pitchspark` | 2026-11-21T130544674767 -> 2026-11-22T164147919164 | 8 changed, 2 added | quiet |
| 2026-11-22 | `remote/io.github.MorrisMoe/soulintime` | 2026-11-22T150355094382 -> 2026-11-22T164148930857 | 2 changed | quiet |
| 2026-11-22 | `remote/com.risetive/mcp` | 2026-11-20T105332023907 -> 2026-11-22T164147519575 | 1 changed | quiet |
| 2026-11-22 | `remote/uk.co.mygrocerypal/grocery-prices` | 2026-11-21T130540959173 -> 2026-11-22T164143955551 | 1 changed | quiet |
| 2026-11-22 | `remote/guru.myproduct/product-lookup` | 2026-11-20T105310917003 -> 2026-11-22T164144853934 | 1 added | quiet |
| 2026-11-22 | `remote/app.pitbi/pitbi` | 2026-11-22T150308123409 -> 2026-11-22T164147663142 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.farenberglord-star/orb-studio` | 2026-11-22T150233070738 -> 2026-11-22T164142831835 | 2 changed, 1 added | quiet |
| 2026-11-22 | `remote/io.github.Fractal-Neurons/pacta` | 2026-11-21T014918937138 -> 2026-11-22T164140204083 | 2 changed | quiet |
| 2026-11-22 | `remote/com.tickerdb/mcp-server` | 2026-11-20T105210036035 -> 2026-11-22T164140723206 | 2 changed | quiet |
| 2026-11-22 | `remote/ai.signal8/mcp` | 2026-11-21T215703440726 -> 2026-11-22T164140361316 | 2 changed | quiet |
| 2026-11-22 | `remote/net.pendingdelete/mcp` | 2026-11-22T145713766374 -> 2026-11-22T164138018660 | 1 changed | quiet |
| 2026-11-22 | `remote/com.meettempi/tempi` | 2026-11-22T103951269638 -> 2026-11-22T164137848334 | 2 changed | quiet |
| 2026-11-22 | `remote/com.loopxxi/loop-mcp` | 2026-11-22T103623559040 -> 2026-11-22T164135807219 | 7 changed | quiet |
| 2026-11-22 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-22T145852805120 -> 2026-11-22T164136326261 | 9 changed | quiet |
| 2026-11-22 | `remote/io.github.ivaavimusic/singularity` | 2026-11-22T150055421009 -> 2026-11-22T164135288105 | 2 changed, 2 added | quiet |
| 2026-11-22 | `remote/social.weir/weir` | 2026-11-21T150450636521 -> 2026-11-22T164134629045 | 3 changed, 3 added (every tool) | quiet |
| 2026-11-22 | `remote/io.github.roomi-fields/osc-bridge` | 2026-11-22T073207594856 -> 2026-11-22T164133470039 | 11 changed | quiet |
| 2026-11-22 | `remote/com.toiseai/toise` | 2026-11-22T145815523558 -> 2026-11-22T164133752710 | 1 changed | quiet |
| 2026-11-22 | `remote/com.cielstay/cielstay` | 2026-11-22T103523363907 -> 2026-11-22T164131072536 | 1 changed, 1 added | quiet |
| 2026-11-22 | `remote/rent.beep/car-rental` | 2026-11-21T150112143050 -> 2026-11-22T164131646081 | 2 changed | quiet |
| 2026-11-22 | `remote/tech.kaiku/kaiku.1` | 2026-11-21T014844881650 -> 2026-11-22T164130447420 | 6 changed | quiet |
| 2026-11-22 | `remote/com.ortexo/mcp` | 2026-11-22T073203633210 -> 2026-11-22T164129972718 | 2 changed | quiet |
| 2026-11-22 | `remote/com.dilutionscan/mcp` | 2026-11-21T130611305267 -> 2026-11-22T164130569196 | 2 changed | quiet |
| 2026-11-22 | `remote/com.kernelcad/kernelcad` | 2026-11-22T145643345127 -> 2026-11-22T164128425999 | 6 changed | quiet |
| 2026-11-22 | `remote/dev.cloro/cloro` | 2026-11-21T215709731641 -> 2026-11-22T164124931153 | 1 changed | quiet |
| 2026-11-22 | `remote/com.heynutcracker/nutcracker` | 2026-11-21T215641868561 -> 2026-11-22T164123723077 | 1 changed | quiet |
| 2026-11-22 | `remote/pro.aicut/aicut` | 2026-11-22T145454847093 -> 2026-11-22T164123064379 | 1 changed | quiet |
| 2026-11-22 | `remote/io.github.genmnz/jean` | 2026-11-21T130608903526 -> 2026-11-22T164124238675 | 3 changed | quiet |
| 2026-11-22 | `remote/net.libertycity/mods` | 2026-11-22T145424807944 -> 2026-11-22T164120879029 | 2 changed | quiet |
| 2026-11-22 | `remote/ai.llpro/campus` | 2026-11-22T145621788479 -> 2026-11-22T164122358762 | 1 changed, 2 added | quiet |
| 2026-11-22 | `remote/it.heera/agentimus` | 2026-11-22T145422690690 -> 2026-11-22T164120134357 | 6 added | quiet |
| 2026-11-22 | `remote/io.github.f-tiger/getecoback-raumklima` | 2026-11-22T145352209743 -> 2026-11-22T164118252621 | 1 changed | quiet |
| 2026-11-22 | `remote/ru.electroatlas/catalog` | 2026-11-20T104323640612 -> 2026-11-22T164122195141 | 2 added | quiet |
| 2026-11-22 | `remote/io.github.ashadow07/karmadue` | 2026-11-22T103321839443 -> 2026-11-22T164119104084 | 1 changed, 1 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 82794 substantive, 43027 that changed only numbers (a catalogue counter ticking, a date), 1165 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 69283 | 29077 | 40206 | 0 |
| `a2awire.com` | 3571 | 3571 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 516 | 516 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 401 | 401 | 0 | 0 |
| `revmesh2074.workers.dev` | 361 | 307 | 54 | 0 |
| `sistaminuten.se` | 271 | 6 | 0 | 265 |
| `afbudsrejser.dk` | 270 | 6 | 0 | 264 |
| `akkilahdot.fi` | 270 | 6 | 0 | 264 |
| `restplass.no` | 270 | 6 | 0 | 264 |
| `socialloop.ai` | 261 | 261 | 0 | 0 |
| 10827 other operators | 48691 | 45816 | 2767 | 108 |
