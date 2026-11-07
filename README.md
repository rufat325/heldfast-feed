# MCP server tool changes

Last change observed 2026-11-07T20:34:04+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

82593 changes to a tool definition: 3503 npm releases (3257 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 79090 readings of hosted servers that found their tools changed; 3557 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-07 | `remote/io.taifoon/coordination-layer.1` | 2026-11-07T151356303434 -> 2026-11-07T203405642923 | 1 changed | review |
| 2026-11-07 | `remote/se.sistaminuten/travel-search` | 2026-11-07T151354826291 -> 2026-11-07T203404724228 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.cryptoconspiracy/vurto-swap` | 2026-11-07T063957742338 -> 2026-11-07T203352729796 | 5 changed | review |
| 2026-11-07 | `remote/dev.sparkpay/sparkpay` | 2026-11-06T144543151948 -> 2026-11-07T203351165090 | 1 changed | quiet |
| 2026-11-07 | `remote/com.idosgames/platform` | 2026-11-06T072753994120 -> 2026-11-07T203348636539 | 2 changed, 2 added | quiet |
| 2026-11-07 | `remote/com.recallcanary/recall-canary` | 2026-11-06T144440243841 -> 2026-11-07T203345764802 | 1 changed | quiet |
| 2026-11-07 | `remote/pl.finwire/data` | 2026-11-07T063954138522 -> 2026-11-07T203345248780 | 1 changed, 1 added | quiet |
| 2026-11-07 | `remote/ng.com.xpressflowsystems.www/esim-domains` | 2026-11-05T115604467264 -> 2026-11-07T203345536211 | 2 changed | quiet |
| 2026-11-07 | `remote/com.synthexforge.x402/paid-agent-services` | 2026-11-07T151348006868 -> 2026-11-07T203345091207 | 1 added | quiet |
| 2026-11-07 | `remote/no.restplass/travel-search` | 2026-11-07T151403205080 -> 2026-11-07T203340906326 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.ceedot-rock/slid-phi-labs` | 2026-11-06T144839767747 -> 2026-11-07T203341199464 | 45 changed, 2 removed (every tool) | review |
| 2026-11-07 | `remote/studio.gradients/mcp` | 2026-11-07T151344334577 -> 2026-11-07T203340545060 | 1 changed | quiet |
| 2026-11-07 | `remote/dev.zambo/zambo` | 2026-11-07T151343381731 -> 2026-11-07T203338741694 | 2 changed | quiet |
| 2026-11-07 | `remote/com.iscabox/iscabox` | 2026-11-06T162146257738 -> 2026-11-07T203340411782 | 1 changed | quiet |
| 2026-11-07 | `remote/fi.akkilahdot/travel-search` | 2026-11-07T151343647975 -> 2026-11-07T203338376499 | 1 changed | quiet |
| 2026-11-07 | `remote/dk.afbudsrejser/travel-search` | 2026-11-07T151359511430 -> 2026-11-07T203337740724 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-07T064018644703 -> 2026-11-07T203338085297 | 8 added | quiet |
| 2026-11-07 | `remote/co.civai.nova/mcp-bgpt-tweet-downloader` | 2026-11-07T133345083466 -> 2026-11-07T203337624034 | 1 added, 1 removed | quiet |
| 2026-11-07 | `remote/co.civai.nova/mcp-bgpt-jiji-recon` | 2026-11-07T133344800012 -> 2026-11-07T203337397984 | 23 added, 1 removed | quiet |
| 2026-11-07 | `remote/co.civai.nova/mcp-bgpt-clannit` | 2026-11-07T133344880450 -> 2026-11-07T203337347973 | 11 added, 1 removed | quiet |
| 2026-11-07 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-07T151342617589 -> 2026-11-07T203337532534 | 3 changed | quiet |
| 2026-11-07 | `remote/co.civai.nova/mcp-bgpt-chowdeck` | 2026-11-07T133344823469 -> 2026-11-07T203336834693 | 24 added, 1 removed | quiet |
| 2026-11-07 | `remote/co.civai.nova/mcp-bgpt-cardpeer` | 2026-11-07T133344502292 -> 2026-11-07T203336768879 | 6 added, 1 removed | quiet |
| 2026-11-07 | `remote/ai.trydock/dock` | 2026-11-06T214837860595 -> 2026-11-07T203336100139 | 1 added | quiet |
| 2026-11-07 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-07T063956842241 -> 2026-11-07T203335755073 | 2 changed | quiet |
| 2026-11-07 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-07T064016724447 -> 2026-11-07T203335971364 | 2 changed | quiet |
| 2026-11-07 | `remote/ca.tonbot.tolca/tolca` | 2026-11-07T133542844380 -> 2026-11-07T203335453367 | 3 changed | review |
| 2026-11-07 | `remote/com.tetheredtrust/tethered-trust` | 2026-11-07T064014307636 -> 2026-11-07T203334019691 | 2 changed, 3 added | review |
| 2026-11-07 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-07T151336213396 -> 2026-11-07T203332189313 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-07T151353625670 -> 2026-11-07T203332044872 | 1 changed, 13 added, 1 removed | review |
| 2026-11-07 | `remote/com.supercatch/supercatch` | 2026-11-07T133423339693 -> 2026-11-07T203333873605 | 1 added | quiet |
| 2026-11-07 | `remote/com.signupbouncer/checker` | 2026-11-06T072818156656 -> 2026-11-07T203330820859 | 4 changed, 2 removed (every tool) | quiet |
| 2026-11-07 | `remote/cc.thecolony/mcp-server` | 2026-11-06T144716101645 -> 2026-11-07T203332181684 | 1 added | quiet |
| 2026-11-07 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-11-07T133235116099 -> 2026-11-07T203329936366 | 4 changed | quiet |
| 2026-11-07 | `remote/com.slashtel/slashtel` | 2026-11-07T133332332253 -> 2026-11-07T203330237092 | 1 added | quiet |
| 2026-11-07 | `remote/ai.pensionhunter/pensionhunter` | 2026-11-07T133131869002 -> 2026-11-07T203331015983 | 1 changed | review |
| 2026-11-07 | `remote/io.github.NeoDemosHQ/neodemos` | 2026-11-07T133111120510 -> 2026-11-07T203329434352 | 2 changed | quiet |
| 2026-11-07 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-11-07T063941091103 -> 2026-11-07T203328238319 | 1 changed | review |
| 2026-11-07 | `remote/now.salesjobs/mcp` | 2026-11-07T151331663419 -> 2026-11-07T203327240060 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.LuxAlgo/luxalgo-mcp-server` | 2026-11-07T133052541262 -> 2026-11-07T203328132980 | 3 changed, 6 removed | quiet |
| 2026-11-07 | `remote/com.rolefig/rolefig` | 2026-11-07T133253867392 -> 2026-11-07T203327346476 | 1 changed | quiet |
| 2026-11-07 | `remote/com.psychologieetserenite/catalogue` | 2026-11-06T214825049886 -> 2026-11-07T203326446134 | 11 changed (every tool) | quiet |
| 2026-11-07 | `remote/dev.precleared/contact-check` | 2026-11-07T133220661862 -> 2026-11-07T203326628869 | 1 changed | quiet |
| 2026-11-07 | `remote/io.github.lx1112/agent-data-api` | 2026-11-06T072756947999 -> 2026-11-07T203324627330 | 15 changed | quiet |
| 2026-11-07 | `remote/com.getcheapgames/getcheapgames` | 2026-11-07T063938821704 -> 2026-11-07T203325268789 | 9 changed (every tool) | quiet |
| 2026-11-07 | `remote/co.civai.nova/mcp-lagos_life` | 2026-11-07T133018370881 -> 2026-11-07T203323127203 | 30 added, 1 removed | quiet |
| 2026-11-07 | `remote/co.civai.nova/mcp-bgpt-polymarket` | 2026-11-07T133130636089 -> 2026-11-07T203323413422 | 18 added, 1 removed | quiet |
| 2026-11-07 | `remote/co.civai.nova/mcp-bgpt-giglogistics` | 2026-11-07T133130587955 -> 2026-11-07T203323273239 | 1 added, 1 removed | quiet |
| 2026-11-07 | `remote/co.civai.nova/mcp-apple_developer` | 2026-11-07T133130108537 -> 2026-11-07T203323249922 | 55 added, 1 removed | quiet |
| 2026-11-07 | `remote/co.civai.nova/mcp-apple_ads` | 2026-11-07T133130024089 -> 2026-11-07T203323136485 | 25 added, 1 removed | quiet |
| 2026-11-07 | `remote/io.github.grzesir/botspot-trading` | 2026-11-07T063937173955 -> 2026-11-07T203322597682 | 5 changed | quiet |
| 2026-11-07 | `remote/com.obriym-crm/mcp` | 2026-11-07T133238495753 -> 2026-11-07T203322625350 | 1 changed, 15 added | quiet |
| 2026-11-07 | `remote/co.civai.nova/mcp-juicyway` | 2026-11-07T133018137286 -> 2026-11-07T203322868303 | 21 added, 1 removed | quiet |
| 2026-11-07 | `remote/co.civai.nova/mcp-hacker_news` | 2026-11-07T133018185031 -> 2026-11-07T203322693150 | 12 added, 1 removed | quiet |
| 2026-11-07 | `remote/co.civai.nova/mcp-bgpt-yarngpt` | 2026-11-07T133018032463 -> 2026-11-07T203322430404 | 2 added, 1 removed | quiet |
| 2026-11-07 | `remote/co.civai.nova/mcp-bgpt-pdf-generator` | 2026-11-07T133017954684 -> 2026-11-07T203322214165 | 5 added, 1 removed | quiet |
| 2026-11-07 | `remote/co.civai.nova/mcp-bgpt-livescore` | 2026-11-07T133017932919 -> 2026-11-07T203322083688 | 10 added, 1 removed | quiet |
| 2026-11-07 | `remote/co.civai.nova/mcp-bgpt-instagram-android` | 2026-11-07T133017715415 -> 2026-11-07T203322005033 | 14 added, 1 removed | quiet |
| 2026-11-07 | `remote/co.civai.nova/mcp-bgpt-cacnigeria` | 2026-11-07T133017430737 -> 2026-11-07T203321955437 | 1 added, 1 removed | quiet |
| 2026-11-07 | `remote/co.civai.nova/mcp-android_developer` | 2026-11-07T133129598717 -> 2026-11-07T203323057742 | 38 added, 1 removed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 50609 substantive, 31098 that changed only numbers (a catalogue counter ticking, a date), 886 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 45119 | 15889 | 29230 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1723 | 1723 | 0 | 0 |
| `caseyjhand.com` | 354 | 354 | 0 | 0 |
| `sistaminuten.se` | 208 | 6 | 0 | 202 |
| `afbudsrejser.dk` | 207 | 6 | 0 | 201 |
| `akkilahdot.fi` | 207 | 6 | 0 | 201 |
| `restplass.no` | 207 | 6 | 0 | 201 |
| `socialloop.ai` | 199 | 199 | 0 | 0 |
| `revmesh2074.workers.dev` | 190 | 167 | 23 | 0 |
| `civai.co` | 187 | 187 | 0 | 0 |
| `modevc.com` | 174 | 174 | 0 | 0 |
| 7916 other operators | 31477 | 29551 | 1845 | 81 |
