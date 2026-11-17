# MCP server tool changes

Last change observed 2026-11-17T13:57:00+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

108315 changes to a tool definition: 4382 npm releases (4136 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 103933 readings of hosted servers that found their tools changed; 4260 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-17 | `remote/com.youspot/youspot` | 2026-11-17T031618275644 -> 2026-11-17T135701979327 | 2 changed, 2 added | quiet |
| 2026-11-17 | `remote/com.yikonglu/lunyu` | 2026-11-16T163412018246 -> 2026-11-17T135658023165 | 1 changed | quiet |
| 2026-11-17 | `remote/co.yougame/yougame` | 2026-11-16T123000047324 -> 2026-11-17T135703094387 | 9 changed, 1 added | quiet |
| 2026-11-17 | `remote/io.github.moelayyan90/xguard` | 2026-11-16T122954845610 -> 2026-11-17T135657079747 | 24 added | review |
| 2026-11-17 | `remote/io.github.sudzikcoin/suverse-agent-assistant` | 2026-11-17T031623057425 -> 2026-11-17T135656698438 | 2 changed | quiet |
| 2026-11-17 | `remote/com.tabflows/site` | 2026-11-17T031621339778 -> 2026-11-17T135655499598 | 2 changed | quiet |
| 2026-11-17 | `remote/no.restplass/travel-search` | 2026-11-17T031619259534 -> 2026-11-17T135654184602 | 1 changed | quiet |
| 2026-11-17 | `remote/pl.obligacyjnyinwestor/obligacje-catalyst` | 2026-11-16T163317330895 -> 2026-11-17T135654502099 | 3 added | quiet |
| 2026-11-17 | `remote/io.github.openaccountants/openaccountants` | 2026-11-15T115343302057 -> 2026-11-17T135653583656 | 2 changed | quiet |
| 2026-11-17 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-17T031611052807 -> 2026-11-17T135654290988 | 1 changed | quiet |
| 2026-11-17 | `remote/com.halaltrip/prayer-tools` | 2026-11-16T163313201065 -> 2026-11-17T135655616631 | 1 changed | quiet |
| 2026-11-17 | `remote/ar.mueblito/mueblito` | 2026-11-17T031617600368 -> 2026-11-17T135651668319 | 8 changed | quiet |
| 2026-11-17 | `remote/com.kulicadvisory/aictionbot-werkbank` | 2026-11-17T031615296748 -> 2026-11-17T135651628345 | 1 added | quiet |
| 2026-11-17 | `remote/ai.haggl/haggl` | 2026-11-17T031613853727 -> 2026-11-17T135649550093 | 1 changed | quiet |
| 2026-11-17 | `remote/io.suverse.versum/catalog` | 2026-11-17T031606041186 -> 2026-11-17T135649248864 | 2 changed | quiet |
| 2026-11-17 | `remote/com.businessratechecker/mcp` | 2026-11-16T163230295754 -> 2026-11-17T135647820978 | 1 changed | review |
| 2026-11-17 | `remote/dk.afbudsrejser/travel-search` | 2026-11-17T031611152735 -> 2026-11-17T135645992566 | 1 changed | quiet |
| 2026-11-17 | `remote/ai.usedby/usedby` | 2026-11-16T163300980744 -> 2026-11-17T135644579616 | 1 changed | quiet |
| 2026-11-17 | `remote/xyz.tripgenius/tripgenius` | 2026-11-16T190056731836 -> 2026-11-17T135646557131 | 1 changed | quiet |
| 2026-11-17 | `remote/io.github.Voopa-Corp/render-check` | 2026-11-16T163152207686 -> 2026-11-17T135643741254 | 3 added | quiet |
| 2026-11-17 | `remote/insure.travelprotection/travel-insurance` | 2026-11-16T123108230371 -> 2026-11-17T135644664325 | 1 changed | quiet |
| 2026-11-17 | `remote/ec.tributasoft/documentacion` | 2026-11-16T163136316027 -> 2026-11-17T135647876803 | 4 changed (every tool) | quiet |
| 2026-11-17 | `remote/io.taifoon/coordination-layer.1` | 2026-11-16T072206014483 -> 2026-11-17T135643889303 | 1 changed | review |
| 2026-11-17 | `remote/io.suverse.www/catalog` | 2026-11-17T031627307631 -> 2026-11-17T135644464239 | 2 changed | quiet |
| 2026-11-17 | `remote/studio.gradients/mcp` | 2026-11-17T031608623423 -> 2026-11-17T135642479988 | 1 changed | quiet |
| 2026-11-17 | `remote/se.sistaminuten/travel-search` | 2026-11-17T031625228083 -> 2026-11-17T135642838196 | 1 changed | quiet |
| 2026-11-17 | `remote/cc.thecolony/mcp-server` | 2026-11-16T163102070805 -> 2026-11-17T135643032690 | 4 changed | quiet |
| 2026-11-17 | `remote/io.github.EasyGerber/easygerber` | 2026-11-16T123057185307 -> 2026-11-17T135641002129 | 2 changed | quiet |
| 2026-11-17 | `remote/de.firma/rechner` | 2026-11-17T031609130998 -> 2026-11-17T135642059930 | 4 added | quiet |
| 2026-11-17 | `remote/com.tutuesim/esim` | 2026-11-16T163121585938 -> 2026-11-17T135641869450 | 5 changed (every tool) | quiet |
| 2026-11-17 | `remote/io.github.PascalSun/talk2geo` | 2026-11-16T163043744260 -> 2026-11-17T135641756110 | 20 removed | quiet |
| 2026-11-17 | `remote/fun.trnch/trnch-elysium` | 2026-11-16T163113189751 -> 2026-11-17T135700339037 | 1 changed | quiet |
| 2026-11-17 | `remote/cn.com.bioinformatics/weishengxin` | 2026-11-15T071615791289 -> 2026-11-17T135644674368 | 11 changed (every tool) | quiet |
| 2026-11-17 | `remote/io.github.t0ll-xyz/toll` | 2026-11-17T031554798077 -> 2026-11-17T135639391640 | 1 changed, 1 added | quiet |
| 2026-11-17 | `remote/fi.akkilahdot/travel-search` | 2026-11-17T031606690272 -> 2026-11-17T135639304341 | 1 changed | quiet |
| 2026-11-17 | `remote/com.trackerhacker/mcp` | 2026-11-17T031604586809 -> 2026-11-17T135639884969 | 3 changed, 1 added | quiet |
| 2026-11-17 | `remote/app.sunsetstrip/gta6` | 2026-11-17T031554392730 -> 2026-11-17T135639328785 | 1 changed | quiet |
| 2026-11-17 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-11-16T163004714402 -> 2026-11-17T135636832131 | 1 changed | quiet |
| 2026-11-17 | `remote/io.github.TMcodingarc/bull-otc` | 2026-11-17T031618819484 -> 2026-11-17T135637273877 | 1 changed | quiet |
| 2026-11-17 | `remote/com.eliteaiempire/th-datasets` | 2026-11-16T190010706355 -> 2026-11-17T135636427719 | 1 changed | quiet |
| 2026-11-17 | `remote/pro.telehealthnearme/telehealth-compare` | 2026-11-16T163020976037 -> 2026-11-17T135634643939 | 1 added | quiet |
| 2026-11-17 | `remote/com.shipshapedata/shipshape-data` | 2026-11-16T122543957499 -> 2026-11-17T135634961339 | 1 changed | quiet |
| 2026-11-17 | `remote/ru.vedarai/mcp` | 2026-11-15T155631847191 -> 2026-11-17T135634871691 | 1 changed | quiet |
| 2026-11-17 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-17T031600010194 -> 2026-11-17T135636132524 | 2 changed | quiet |
| 2026-11-17 | `remote/com.wandy3d/wandy3d` | 2026-11-16T163113003014 -> 2026-11-17T135633740031 | 2 changed, 1 added | quiet |
| 2026-11-17 | `remote/wiki.rust/rust-wiki` | 2026-11-16T162858684167 -> 2026-11-17T135632269316 | 2 changed, 1 added | quiet |
| 2026-11-17 | `remote/org.summarizethis/summarizethis` | 2026-11-16T190006400985 -> 2026-11-17T135632454234 | 1 changed | quiet |
| 2026-11-17 | `remote/now.salesjobs/mcp` | 2026-11-15T212250393802 -> 2026-11-17T135631827297 | 1 changed | quiet |
| 2026-11-17 | `remote/com.uncommonear/free-music-sound-effects` | 2026-11-16T163038228940 -> 2026-11-17T135631068151 | 1 changed | quiet |
| 2026-11-17 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-17T031557829198 -> 2026-11-17T135633181746 | 3 added, 11 removed | quiet |
| 2026-11-17 | `remote/io.github.spree/ecommerce-docs` | 2026-11-16T162934798115 -> 2026-11-17T135630003540 | 1 changed | quiet |
| 2026-11-17 | `remote/io.github.Schoasch/backtesting-arena` | 2026-11-15T115511445006 -> 2026-11-17T135628996768 | 10 changed | quiet |
| 2026-11-17 | `remote/io.github.Friezaaaa/smartfetch` | 2026-11-17T031554279043 -> 2026-11-17T135629354781 | 2 added | quiet |
| 2026-11-17 | `remote/com.usetested/reviews` | 2026-11-15T115457743061 -> 2026-11-17T135630030129 | 3 changed | review |
| 2026-11-17 | `remote/com.usdtbanned/mayak` | 2026-11-16T163045756193 -> 2026-11-17T135630920042 | 1 changed | quiet |
| 2026-11-17 | `remote/com.transcript-yt/transcriptyt` | 2026-11-16T163018729272 -> 2026-11-17T135628963038 | 1 changed | quiet |
| 2026-11-17 | `remote/com.socialnetworkforaiagents/agent-socials` | 2026-11-16T122636759814 -> 2026-11-17T135628935570 | 1 changed | quiet |
| 2026-11-17 | `remote/at.space-core/game` | 2026-11-17T031555956335 -> 2026-11-17T135631029201 | 1 changed | quiet |
| 2026-11-17 | `remote/io.github.mastercobeos/tlacuilo` | 2026-11-16T190122399826 -> 2026-11-17T135627995054 | 3 added | quiet |
| 2026-11-17 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-17T031550784230 -> 2026-11-17T135627385332 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 66436 substantive, 40816 that changed only numbers (a catalogue counter ticking, a date), 1063 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 58079 | 19726 | 38353 | 0 |
| `a2awire.com` | 2974 | 2974 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 460 | 460 | 0 | 0 |
| `civai.co` | 367 | 367 | 0 | 0 |
| `modevc.com` | 349 | 349 | 0 | 0 |
| `revmesh2074.workers.dev` | 292 | 253 | 39 | 0 |
| `sistaminuten.se` | 248 | 6 | 0 | 242 |
| `afbudsrejser.dk` | 247 | 6 | 0 | 241 |
| `akkilahdot.fi` | 247 | 6 | 0 | 241 |
| `restplass.no` | 247 | 6 | 0 | 241 |
| `socialloop.ai` | 239 | 239 | 0 | 0 |
| 9808 other operators | 42225 | 39703 | 2424 | 98 |
