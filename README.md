# MCP server tool changes

Last change observed 2026-10-21T14:11:54+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

40049 changes to a tool definition: 1694 npm releases (1448 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 38355 readings of hosted servers that found their tools changed; 2307 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-21 | `remote/se.sistaminuten/travel-search` | 2026-10-21T122405853584 -> 2026-10-21T141155419341 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-10-21T122354043800 -> 2026-10-21T141153863196 | 1 changed | quiet |
| 2026-10-21 | `remote/no.restplass/travel-search` | 2026-10-21T122156581866 -> 2026-10-21T141150535445 | 1 changed | quiet |
| 2026-10-21 | `remote/dk.afbudsrejser/travel-search` | 2026-10-21T122124250759 -> 2026-10-21T141147173101 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.voicehook-ai/voicehook` | 2026-10-21T122301675981 -> 2026-10-21T141147125472 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-10-19T212015988842 -> 2026-10-21T141143621467 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.VoiceScapee/voicescape` | 2026-10-20T232809506087 -> 2026-10-21T141140979267 | 1 changed | quiet |
| 2026-10-21 | `remote/studio.gradients/mcp` | 2026-10-21T122212124980 -> 2026-10-21T141139126055 | 1 changed | quiet |
| 2026-10-21 | `remote/pro.germanexam/germanexam` | 2026-10-21T052301190279 -> 2026-10-21T141139089081 | 1 changed | quiet |
| 2026-10-21 | `remote/ai.trydock/dock` | 2026-10-20T201157051058 -> 2026-10-21T141138344747 | 1 changed | quiet |
| 2026-10-21 | `remote/fi.akkilahdot/travel-search` | 2026-10-21T122155498756 -> 2026-10-21T141137333969 | 1 changed | quiet |
| 2026-10-21 | `remote/ai.weio/site-check` | 2026-10-21T122126535285 -> 2026-10-21T141138024531 | 2 added, 3 removed | quiet |
| 2026-10-21 | `remote/com.googleapis.sqladmin/mcp` | 2026-10-21T121958031869 -> 2026-10-21T141130461901 | 10 changed | quiet |
| 2026-10-21 | `remote/com.swarmmemo/bulletin.1` | 2026-10-21T122044651219 -> 2026-10-21T141125409411 | 2 changed | quiet |
| 2026-10-21 | `remote/com.swarmmemo/bulletin` | 2026-10-21T122044466290 -> 2026-10-21T141125126517 | 2 changed | quiet |
| 2026-10-21 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-21T122025293565 -> 2026-10-21T141121293203 | 1 changed | quiet |
| 2026-10-21 | `remote/app.sallim/korea-realty` | 2026-10-21T121901260523 -> 2026-10-21T141121141777 | 1 changed | quiet |
| 2026-10-21 | `remote/me.miow/miow` | 2026-10-21T121900252654 -> 2026-10-21T141116122405 | 3 changed | quiet |
| 2026-10-21 | `remote/io.github.ak10082247-max/rugshield-402` | 2026-10-19T135253606204 -> 2026-10-21T141112240333 | 2 added | quiet |
| 2026-10-21 | `remote/com.remoshift/jobs` | 2026-10-21T121931256431 -> 2026-10-21T141111354836 | 1 changed | quiet |
| 2026-10-21 | `remote/com.mrrledger/mrrledger` | 2026-10-21T121808460271 -> 2026-10-21T141109542224 | 17 changed (every tool) | quiet |
| 2026-10-21 | `remote/md.mostlyright/datasets` | 2026-10-21T121806893845 -> 2026-10-21T141107970146 | 10 changed, 6 added | quiet |
| 2026-10-21 | `remote/pl.klyo/games` | 2026-10-21T052235262877 -> 2026-10-21T141105472832 | 1 changed | quiet |
| 2026-10-21 | `remote/com.metricduck/financial-analysis` | 2026-10-21T121704329947 -> 2026-10-21T141103533966 | 6 changed | quiet |
| 2026-10-21 | `remote/io.kompare/search` | 2026-10-20T201045214152 -> 2026-10-21T141102874243 | 1 changed | quiet |
| 2026-10-21 | `remote/estate.new/listings` | 2026-10-19T135127698959 -> 2026-10-21T141101479936 | 1 added | quiet |
| 2026-10-21 | `remote/com.ppn-hub/ppn-hub` | 2026-10-21T121648733827 -> 2026-10-21T141101109053 | 1 changed | quiet |
| 2026-10-21 | `remote/dev.stackscope/stackscope` | 2026-10-20T201056813155 -> 2026-10-21T141101060462 | 1 changed | quiet |
| 2026-10-21 | `remote/com.sportstatsapi/sports-data` | 2026-10-20T103909269702 -> 2026-10-21T141059958237 | 2 changed, 1 added | quiet |
| 2026-10-21 | `remote/com.jojapi/sms-verify` | 2026-10-20T135348724324 -> 2026-10-21T141100545691 | 1 changed | quiet |
| 2026-10-21 | `remote/ca.movahedi/privacy` | 2026-10-21T121815542819 -> 2026-10-21T141059290438 | 1 changed | quiet |
| 2026-10-21 | `remote/com.bitcoincreditstack/mcp` | 2026-10-19T135139334634 -> 2026-10-21T141052390870 | 1 added | quiet |
| 2026-10-21 | `remote/tech.kaiku/kaiku.1` | 2026-10-21T121607606096 -> 2026-10-21T141051950988 | 1 changed, 2 added | quiet |
| 2026-10-21 | `remote/io.llmexpert/transcription` | 2026-10-19T134631084422 -> 2026-10-21T141048790022 | 3 changed | quiet |
| 2026-10-21 | `remote/com.avokata/avokata` | 2026-10-19T211844036977 -> 2026-10-21T141051330109 | 4 changed | quiet |
| 2026-10-21 | `remote/com.pagelemon/pagelemon` | 2026-10-21T052221829354 -> 2026-10-21T141047177433 | 47 changed (every tool) | quiet |
| 2026-10-21 | `remote/com.hireahelper/mcp` | 2026-10-21T121621315094 -> 2026-10-21T141042995119 | 16 removed | quiet |
| 2026-10-21 | `remote/ai.inite/atlas` | 2026-10-21T121357020038 -> 2026-10-21T141035731137 | 1 changed | quiet |
| 2026-10-21 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-21T121210075846 -> 2026-10-21T141033742767 | 3 changed | quiet |
| 2026-10-21 | `remote/io.github.guggach/guggach-apartments` | 2026-10-19T134412729389 -> 2026-10-21T141034222949 | 1 changed | quiet |
| 2026-10-21 | `remote/space.galaxymind/galaxy-mind` | 2026-10-21T052202360147 -> 2026-10-21T141029635140 | 1 changed | quiet |
| 2026-10-21 | `remote/com.fridayflightdeals/deals` | 2026-10-21T121214551381 -> 2026-10-21T141028823806 | 2 changed, 3 added | quiet |
| 2026-10-21 | `remote/io.github.tonic20/extensions-dashboard` | 2026-10-21T121202831170 -> 2026-10-21T141027658789 | 14 changed (every tool) | quiet |
| 2026-10-21 | `remote/io.github.Datura-ai/lium-docs` | 2026-10-21T121123503591 -> 2026-10-21T141027154745 | 1 changed | quiet |
| 2026-10-21 | `remote/app.everloot/knowledge` | 2026-10-20T201051820653 -> 2026-10-21T141033115013 | 1 changed | quiet |
| 2026-10-21 | `remote/fr.hermetics/rgpd` | 2026-10-19T134643820479 -> 2026-10-21T141025391617 | 1 changed | quiet |
| 2026-10-21 | `remote/com.dayze/life-context.1` | 2026-10-21T121108059068 -> 2026-10-21T141024736430 | 9 changed | quiet |
| 2026-10-21 | `remote/com.dayze/life-context` | 2026-10-21T121106969905 -> 2026-10-21T141024482711 | 9 changed | quiet |
| 2026-10-21 | `remote/io.github.fxmacrodata/fxmacrodata` | 2026-10-19T211746868644 -> 2026-10-21T141022055758 | 2 added | quiet |
| 2026-10-21 | `remote/app.sallim/contract-compass` | 2026-10-21T121045210376 -> 2026-10-21T141024144340 | 2 changed | quiet |
| 2026-10-21 | `remote/me.freehire/freehire` | 2026-10-19T134508217819 -> 2026-10-21T141021874489 | 2 changed | quiet |
| 2026-10-21 | `remote/build.naru/contract-compass` | 2026-10-21T121114245876 -> 2026-10-21T141021091372 | 2 changed | quiet |
| 2026-10-21 | `remote/io.github.evictionsapi/evictions-api` | 2026-10-19T134440347988 -> 2026-10-21T141020081566 | 2 changed, 1 added | quiet |
| 2026-10-21 | `remote/io.github.smithdavedesign/botchelor` | 2026-10-21T121025622441 -> 2026-10-21T141010667792 | 10 changed | quiet |
| 2026-10-21 | `remote/io.github.lgs1520/call402` | 2026-10-21T052227064972 -> 2026-10-21T141011644376 | 4 added | quiet |
| 2026-10-21 | `remote/net.ts.tailb4ac3a.ari001/arysphere-x402` | 2026-10-21T121002810063 -> 2026-10-21T141009844082 | 1 added, 2 removed | quiet |
| 2026-10-21 | `remote/app.befana/befana` | 2026-10-21T121022517384 -> 2026-10-21T141006187697 | 2 changed | quiet |
| 2026-10-21 | `remote/com.baseofagi/news` | 2026-10-19T134606136386 -> 2026-10-21T141005612339 | 1 added | quiet |
| 2026-10-21 | `remote/properties.hercules/property-data` | 2026-10-21T052143737769 -> 2026-10-21T141005924202 | 2 changed | quiet |
| 2026-10-21 | `remote/org.aspern/aspern` | 2026-10-21T121012427456 -> 2026-10-21T141005748351 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 25252 substantive, 14257 that changed only numbers (a catalogue counter ticking, a date), 540 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 20653 | 7232 | 13421 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 170 | 170 | 0 | 0 |
| `sistaminuten.se` | 129 | 4 | 0 | 125 |
| `afbudsrejser.dk` | 128 | 4 | 0 | 124 |
| `akkilahdot.fi` | 128 | 4 | 0 | 124 |
| `restplass.no` | 128 | 4 | 0 | 124 |
| `socialloop.ai` | 125 | 125 | 0 | 0 |
| `remoshift.com` | 99 | 6 | 93 | 0 |
| `fundinglandscape.com` | 97 | 63 | 34 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| 4930 other operators | 15301 | 14549 | 709 | 43 |
