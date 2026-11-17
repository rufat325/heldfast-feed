# MCP server tool changes

Last change observed 2026-11-17T03:16:28+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

107962 changes to a tool definition: 4382 npm releases (4136 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 103580 readings of hosted servers that found their tools changed; 4244 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-17 | `remote/xn--3ds443g.xn--s7y/duan-online` | 2026-11-15T142719484555 -> 2026-11-17T031630127698 | 2 changed | quiet |
| 2026-11-17 | `remote/com.veridionmarkets/disclosures` | 2026-11-16T163302527977 -> 2026-11-17T031627880551 | 1 changed | quiet |
| 2026-11-17 | `remote/se.sistaminuten/travel-search` | 2026-11-16T190145638745 -> 2026-11-17T031625228083 | 1 changed | quiet |
| 2026-11-17 | `remote/io.suverse.www/catalog` | 2026-11-16T190148372526 -> 2026-11-17T031627307631 | 3 changed | quiet |
| 2026-11-17 | `remote/org.omenz.www/agent-tools` | 2026-11-16T163232805204 -> 2026-11-17T031623261196 | 73 changed, 1 added (every tool) | quiet |
| 2026-11-17 | `remote/io.github.liad142/yedapo` | 2026-11-16T072219656698 -> 2026-11-17T031623725978 | 2 changed (every tool) | quiet |
| 2026-11-17 | `remote/io.github.sudzikcoin/suverse-agent-assistant` | 2026-11-16T190037802009 -> 2026-11-17T031623057425 | 3 changed | quiet |
| 2026-11-17 | `remote/com.tabflows/site` | 2026-11-15T071544867268 -> 2026-11-17T031621339778 | 2 changed, 3 added, 2 removed | quiet |
| 2026-11-17 | `remote/com.kaicalls/kaicalls` | 2026-11-16T163220349920 -> 2026-11-17T031621513477 | 4 changed, 3 added | quiet |
| 2026-11-17 | `remote/no.restplass/travel-search` | 2026-11-16T190035759244 -> 2026-11-17T031619259534 | 1 changed | quiet |
| 2026-11-17 | `remote/io.github.TMcodingarc/bull-otc` | 2026-11-16T163158352120 -> 2026-11-17T031618819484 | 2 changed, 2 added | quiet |
| 2026-11-17 | `remote/com.youspot/youspot` | 2026-11-16T123040624495 -> 2026-11-17T031618275644 | 1 changed | quiet |
| 2026-11-17 | `remote/ar.mueblito/mueblito` | 2026-11-16T122926736818 -> 2026-11-17T031617600368 | 8 changed | quiet |
| 2026-11-17 | `remote/ai.arcreport/ask` | 2026-11-16T190136029530 -> 2026-11-17T031617223476 | 2 changed | quiet |
| 2026-11-17 | `remote/com.kulicadvisory/aictionbot-werkbank` | 2026-11-16T190025347025 -> 2026-11-17T031615296748 | 2 added | quiet |
| 2026-11-17 | `remote/com.rightshold/rightshold` | 2026-11-16T163342743082 -> 2026-11-17T031613962953 | 1 changed | quiet |
| 2026-11-17 | `remote/ai.haggl/haggl` | 2026-11-16T122914397597 -> 2026-11-17T031613853727 | 1 changed | quiet |
| 2026-11-17 | `remote/dev.workers.lucciocarmino.x402-probe/x402-tools` | 2026-11-16T163250557686 -> 2026-11-17T031612489044 | 1 added | quiet |
| 2026-11-17 | `remote/dk.afbudsrejser/travel-search` | 2026-11-16T190022313942 -> 2026-11-17T031611152735 | 1 changed | quiet |
| 2026-11-17 | `remote/ai.arcreport/mcp` | 2026-11-16T122854809460 -> 2026-11-17T031611642890 | 1 changed | quiet |
| 2026-11-17 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-16T122907350909 -> 2026-11-17T031611052807 | 2 changed | quiet |
| 2026-11-17 | `remote/studio.gradients/mcp` | 2026-11-16T190149058392 -> 2026-11-17T031608623423 | 1 changed | quiet |
| 2026-11-17 | `remote/de.firma/rechner` | 2026-11-16T163158552689 -> 2026-11-17T031609130998 | 1 added | quiet |
| 2026-11-17 | `remote/com.vibecodepicks/vibecodepicks` | 2026-11-16T163147557228 -> 2026-11-17T031608317410 | 2 changed | quiet |
| 2026-11-17 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-16T163146438632 -> 2026-11-17T031607311450 | 1 changed | quiet |
| 2026-11-17 | `remote/io.github.RafaCoelho33/web3-systemic-agent` | 2026-11-16T122814994531 -> 2026-11-17T031605927120 | 1 changed | quiet |
| 2026-11-17 | `remote/fi.akkilahdot/travel-search` | 2026-11-16T190139473791 -> 2026-11-17T031606690272 | 1 changed | quiet |
| 2026-11-17 | `remote/xyz.wunderlust/wunderlust` | 2026-11-16T163132775911 -> 2026-11-17T031604702458 | 1 changed | quiet |
| 2026-11-17 | `remote/io.suverse.versum/catalog` | 2026-11-16T190100840448 -> 2026-11-17T031606041186 | 3 changed | quiet |
| 2026-11-17 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-16T072238154213 -> 2026-11-17T031604403251 | 1 changed | quiet |
| 2026-11-17 | `remote/com.trackerhacker/mcp` | 2026-11-15T155624094481 -> 2026-11-17T031604586809 | 5 changed, 2 added, 1 removed | quiet |
| 2026-11-17 | `remote/io.github.tollnodemcp/tollnode` | 2026-11-16T163000720186 -> 2026-11-17T031603908661 | 88 changed, 14 added | review |
| 2026-11-17 | `remote/com.trygoppa/goppa` | 2026-11-16T190056010568 -> 2026-11-17T031602736253 | 1 changed | quiet |
| 2026-11-17 | `remote/com.thefomite/fomite` | 2026-11-16T072200278786 -> 2026-11-17T031602528181 | 1 changed | quiet |
| 2026-11-17 | `remote/com.thebitcoinadviser/mcp` | 2026-11-15T115146592104 -> 2026-11-17T031602291514 | 1 changed | quiet |
| 2026-11-17 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-16T190133210593 -> 2026-11-17T031600010194 | 3 changed | quiet |
| 2026-11-17 | `remote/com.telastricotela/catalog` | 2026-11-16T163051748339 -> 2026-11-17T031558380890 | 3 changed | quiet |
| 2026-11-17 | `remote/io.standoutmcp/standout` | 2026-11-16T122759463667 -> 2026-11-17T031556477755 | 2 added | quiet |
| 2026-11-17 | `remote/com.usta-bul/usta-bul` | 2026-11-16T163046190079 -> 2026-11-17T031558407850 | 2 added | quiet |
| 2026-11-17 | `remote/io.github.t0ll-xyz/toll` | 2026-11-16T190046268434 -> 2026-11-17T031554798077 | 1 changed | quiet |
| 2026-11-17 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-16T162945450681 -> 2026-11-17T031557829198 | 1 removed | quiet |
| 2026-11-17 | `remote/app.sunsetstrip/gta6` | 2026-11-16T072300885086 -> 2026-11-17T031554392730 | 2 changed | review |
| 2026-11-17 | `remote/io.github.Friezaaaa/smartfetch` | 2026-11-16T162918159713 -> 2026-11-17T031554279043 | 1 added | quiet |
| 2026-11-17 | `remote/at.space-core/game` | 2026-11-16T162930029212 -> 2026-11-17T031555956335 | 1 changed | quiet |
| 2026-11-17 | `remote/net.setget/setget` | 2026-11-16T122617953351 -> 2026-11-17T031551946857 | 5 added | quiet |
| 2026-11-17 | `remote/fr.souslagelule/complements` | 2026-11-16T163004574082 -> 2026-11-17T031557944177 | 1 changed, 1 added | quiet |
| 2026-11-17 | `remote/com.sharpleftturn/ai-battle-arena` | 2026-11-16T162837789606 -> 2026-11-17T031552794783 | 2 changed, 1 added | quiet |
| 2026-11-17 | `remote/sk.rybarstvo/portal` | 2026-11-16T162807494249 -> 2026-11-17T031552193194 | 1 added | quiet |
| 2026-11-17 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-16T122925335588 -> 2026-11-17T031550784230 | 1 changed | quiet |
| 2026-11-17 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-16T190122105934 -> 2026-11-17T031551378698 | 2 changed | quiet |
| 2026-11-17 | `remote/com.eliteaiempire/scrubline` | 2026-11-16T162822537291 -> 2026-11-17T031551648723 | 2 changed | quiet |
| 2026-11-17 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-11-16T072254782144 -> 2026-11-17T031547134081 | 1 changed | quiet |
| 2026-11-17 | `remote/com.radialswitchboard/matchmaker` | 2026-11-16T185952961750 -> 2026-11-17T031546385208 | 1 changed | quiet |
| 2026-11-17 | `remote/com.qrcodedinosaur/qr-codes` | 2026-11-16T162719077799 -> 2026-11-17T031546617929 | 1 changed | quiet |
| 2026-11-17 | `remote/app.qrcodecreator/qr-codes` | 2026-11-16T162730975234 -> 2026-11-17T031545312730 | 1 changed | quiet |
| 2026-11-17 | `remote/app.storyshort/storyshort` | 2026-11-16T162924964198 -> 2026-11-17T031544019220 | 2 changed, 3 added | review |
| 2026-11-17 | `remote/io.github.ryankaye212-tech/probeline` | 2026-11-16T162714740081 -> 2026-11-17T031542595211 | 5 added | review |
| 2026-11-17 | `remote/io.github.richardsolomou/praetorium` | 2026-11-16T185951709525 -> 2026-11-17T031544811371 | 6 changed, 4 added | quiet |
| 2026-11-17 | `remote/dev.releasealert/mcp` | 2026-11-16T162834781108 -> 2026-11-17T031543110285 | 1 changed | quiet |
| 2026-11-17 | `remote/com.renderior/renderior` | 2026-11-16T162837877826 -> 2026-11-17T031543496721 | 1 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 66119 substantive, 40785 that changed only numbers (a catalogue counter ticking, a date), 1058 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 58079 | 19726 | 38353 | 0 |
| `a2awire.com` | 2974 | 2974 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 460 | 460 | 0 | 0 |
| `civai.co` | 367 | 367 | 0 | 0 |
| `modevc.com` | 349 | 349 | 0 | 0 |
| `revmesh2074.workers.dev` | 289 | 252 | 37 | 0 |
| `sistaminuten.se` | 247 | 6 | 0 | 241 |
| `afbudsrejser.dk` | 246 | 6 | 0 | 240 |
| `akkilahdot.fi` | 246 | 6 | 0 | 240 |
| `restplass.no` | 246 | 6 | 0 | 240 |
| `socialloop.ai` | 238 | 238 | 0 | 0 |
| 9749 other operators | 41880 | 39388 | 2395 | 97 |
