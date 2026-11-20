# MCP server tool changes

Last change observed 2026-11-20T07:50:00+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 16578 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 39505 hosted endpoints (read daily, and every four hours while they keep changing).

118211 changes to a tool definition: 4741 npm releases (4495 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 113470 readings of hosted servers that found their tools changed; 4524 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-20 | `remote/studio.gradients/mcp` | 2026-11-19T231839183331 -> 2026-11-20T075001871915 | 1 changed | quiet |
| 2026-11-20 | `remote/io.github.EasyGerber/easygerber` | 2026-11-19T231838049864 -> 2026-11-20T075000999084 | 6 changed | quiet |
| 2026-11-20 | `remote/io.github.seasonsagents-art/webaz` | 2026-11-18T135830306308 -> 2026-11-20T074958698187 | 3 changed | quiet |
| 2026-11-20 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-19T020338716192 -> 2026-11-20T074959766448 | 1 changed | quiet |
| 2026-11-20 | `remote/fi.akkilahdot/travel-search` | 2026-11-19T231837185767 -> 2026-11-20T075000855144 | 1 changed | quiet |
| 2026-11-20 | `remote/ru.vedarai/mcp` | 2026-11-19T123903496933 -> 2026-11-20T074959293731 | 1 changed | quiet |
| 2026-11-20 | `remote/dev.vetagent/vetagent` | 2026-11-19T231833478214 -> 2026-11-20T074958384963 | 1 changed | quiet |
| 2026-11-20 | `remote/au.vetjobs/vetjobs` | 2026-11-18T135816491744 -> 2026-11-20T074958943659 | 3 changed | quiet |
| 2026-11-20 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-19T123803414069 -> 2026-11-20T074956137910 | 2 changed | quiet |
| 2026-11-20 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-19T231823893375 -> 2026-11-20T074951669904 | 3 changed, 2 added | quiet |
| 2026-11-20 | `remote/io.github.QDThead/signal-lab` | 2026-11-19T231822751374 -> 2026-11-20T074949885291 | 1 changed | quiet |
| 2026-11-20 | `remote/io.github.bnth09productions-maker/scrapling-x402-store` | 2026-11-19T162203242809 -> 2026-11-20T074946505827 | 19 added | quiet |
| 2026-11-20 | `remote/com.youspot/youspot` | 2026-11-19T231842711974 -> 2026-11-20T074945721235 | 2 changed | quiet |
| 2026-11-20 | `remote/com.seeksat/seeksat` | 2026-11-19T231819944715 -> 2026-11-20T074945962545 | 4 changed | quiet |
| 2026-11-20 | `remote/com.remoshift/jobs` | 2026-11-19T162130663762 -> 2026-11-20T074945351862 | 1 changed | quiet |
| 2026-11-20 | `remote/io.github.yschimke/compose-preview` | 2026-11-19T162057077622 -> 2026-11-20T074945027918 | 4 changed | quiet |
| 2026-11-20 | `remote/no.restplass/travel-search` | 2026-11-19T231851959067 -> 2026-11-20T074941987088 | 1 changed | quiet |
| 2026-11-20 | `remote/today.nyangi/oneul-nyangi` | 2026-11-18T080220321771 -> 2026-11-20T074941325695 | 2 changed | quiet |
| 2026-11-20 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-19T231835490445 -> 2026-11-20T074940331617 | 2 changed | quiet |
| 2026-11-20 | `remote/se.sistaminuten/travel-search` | 2026-11-19T231842695128 -> 2026-11-20T074939075933 | 1 changed | quiet |
| 2026-11-20 | `remote/dk.afbudsrejser/travel-search` | 2026-11-19T231843861545 -> 2026-11-20T074940321406 | 1 changed | quiet |
| 2026-11-20 | `remote/com.multicinesortega/cartelera` | 2026-11-19T231809483370 -> 2026-11-20T074941391452 | 1 changed | quiet |
| 2026-11-20 | `remote/io.github.dwiel/buyusbcables` | 2026-11-18T174017488409 -> 2026-11-20T074938957768 | 3 changed | quiet |
| 2026-11-20 | `remote/com.modevc/chart-pre-seed-valuation-dispersion` | 2026-11-19T231807376832 -> 2026-11-20T074938280119 | 1 changed, 2 added | review |
| 2026-11-20 | `remote/com.modevc/chart-mcp-adoption-model-context-protocol-downloads` | 2026-11-19T231807220242 -> 2026-11-20T074938613149 | 1 changed, 2 added | review |
| 2026-11-20 | `remote/com.modevc/chart-llm-rankings-by-category-specialists` | 2026-11-19T231807088174 -> 2026-11-20T074938252208 | 1 changed, 2 added | review |
| 2026-11-20 | `remote/com.modevc/chart-how-many-ai-models-are-there` | 2026-11-19T231807353997 -> 2026-11-20T074938264552 | 1 changed, 2 added | review |
| 2026-11-20 | `remote/com.modevc/chart-chatgpt-vs-gemini-vs-meta-ai-users` | 2026-11-19T231807099950 -> 2026-11-20T074938238523 | 1 changed, 2 added | review |
| 2026-11-20 | `remote/com.modevc/chart-best-ai-models-by-category` | 2026-11-19T231806730510 -> 2026-11-20T074937603705 | 1 changed, 2 added | review |
| 2026-11-20 | `remote/io.trylode/lode` | 2026-11-19T123710233340 -> 2026-11-20T074937950669 | 6 changed, 3 added (every tool) | quiet |
| 2026-11-20 | `remote/com.modevc/radar` | 2026-11-19T231806138091 -> 2026-11-20T074937286952 | 1 changed, 2 added | review |
| 2026-11-20 | `remote/com.modevc/chart-ai-inference-cost-comparison` | 2026-11-19T231806559333 -> 2026-11-20T074937300360 | 1 changed, 2 added | review |
| 2026-11-20 | `remote/com.modevc/chart-ai-in-the-workplace-statistics` | 2026-11-19T231806148230 -> 2026-11-20T074937317782 | 1 changed, 2 added | review |
| 2026-11-20 | `remote/com.herbertandphyllis/mcp` | 2026-11-19T123845264546 -> 2026-11-20T074937150860 | 6 changed, 1 added | quiet |
| 2026-11-20 | `remote/ai.trydock/dock` | 2026-11-19T123708776670 -> 2026-11-20T074937029773 | 3 changed | quiet |
| 2026-11-20 | `remote/com.trendtemplate/templates` | 2026-11-19T162258076516 -> 2026-11-20T074936026457 | 2 changed | quiet |
| 2026-11-20 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-19T231805788736 -> 2026-11-20T074937897547 | 8 changed | quiet |
| 2026-11-20 | `remote/io.github.eyeinthesky6/unseen-workflow-compiler` | 2026-11-18T135629847659 -> 2026-11-20T074935722662 | 4 changed | quiet |
| 2026-11-20 | `remote/io.github.brawlaphant/vealth` | 2026-11-18T080151804789 -> 2026-11-20T074935414600 | 2 changed | quiet |
| 2026-11-20 | `remote/com.halpii/latam-tax-api` | 2026-11-19T123616929098 -> 2026-11-20T074934526414 | 1 changed | quiet |
| 2026-11-20 | `remote/com.vet402/vet402` | 2026-11-19T231834454605 -> 2026-11-20T074934046620 | 1 changed | quiet |
| 2026-11-20 | `remote/io.github.streamloop/mcp` | 2026-11-19T231802517792 -> 2026-11-20T074933165552 | 3 changed | quiet |
| 2026-11-20 | `remote/io.github.SeoScoreAPI/seoscoreapi-mcp` | 2026-11-19T231830980383 -> 2026-11-20T074932551393 | 1 changed | quiet |
| 2026-11-20 | `remote/ai.switchapp/switch` | 2026-11-18T135123487694 -> 2026-11-20T074933877841 | 4 added | quiet |
| 2026-11-20 | `remote/re.rundata/temps-reel` | 2026-11-18T135335070395 -> 2026-11-20T074931917166 | 2 changed | quiet |
| 2026-11-20 | `remote/app.sunsetstrip/gta6` | 2026-11-19T231822442938 -> 2026-11-20T074931865880 | 21 changed, 2 added | quiet |
| 2026-11-20 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-11-19T020417219547 -> 2026-11-20T074930394683 | 1 changed | quiet |
| 2026-11-20 | `remote/com.timeofmeeting/time-of-meeting` | 2026-11-18T135543998643 -> 2026-11-20T074930347025 | 1 changed | quiet |
| 2026-11-20 | `remote/com.thefomite/fomite` | 2026-11-19T020347159654 -> 2026-11-20T074930839493 | 1 changed | quiet |
| 2026-11-20 | `remote/com.radarbg/radar-tools` | 2026-11-19T231827725529 -> 2026-11-20T074932036706 | 2 changed, 1 added | quiet |
| 2026-11-20 | `remote/com.qrcodedinosaur/qr-codes` | 2026-11-19T231825941432 -> 2026-11-20T074930197254 | 1 changed, 1 added | quiet |
| 2026-11-20 | `remote/io.github.Playpowerpolitics/powerplayers` | 2026-11-19T231822621175 -> 2026-11-20T074929135153 | 2 changed | quiet |
| 2026-11-20 | `remote/io.github.MsingathiM/swapeazi` | 2026-11-19T231829304265 -> 2026-11-20T074929109562 | 1 added | quiet |
| 2026-11-20 | `remote/app.lovable.privacy-pill-consent-studio/privacypill` | 2026-11-19T231826297553 -> 2026-11-20T074930673665 | 1 changed | quiet |
| 2026-11-20 | `remote/io.github.magichourhq/magic-hour` | 2026-11-19T123036220061 -> 2026-11-20T074928870854 | 4 changed | quiet |
| 2026-11-20 | `remote/io.github.codytodd-ui/pitchspark` | 2026-11-19T231821972354 -> 2026-11-20T074928438440 | 1 changed | quiet |
| 2026-11-20 | `remote/io.github.adamgraymon/agent-finops-budget-spend-guard` | 2026-11-19T161825609275 -> 2026-11-20T074927964392 | 2 changed | review |
| 2026-11-20 | `remote/fyi.levels/levels-fyi` | 2026-11-19T161542763073 -> 2026-11-20T074928815001 | 1 changed | quiet |
| 2026-11-20 | `remote/com.partstable/partstable` | 2026-11-19T123312516744 -> 2026-11-20T074929351322 | 1 changed | quiet |
| 2026-11-20 | `remote/app.lovable.peppol-invoice-compass/invoiceverify` | 2026-11-18T080148107135 -> 2026-11-20T074928864548 | 2 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 76079 substantive, 41016 that changed only numbers (a catalogue counter ticking, a date), 1116 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 63683 | 25330 | 38353 | 0 |
| `a2awire.com` | 3438 | 3438 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 477 | 477 | 0 | 0 |
| `modevc.com` | 435 | 435 | 0 | 0 |
| `civai.co` | 369 | 369 | 0 | 0 |
| `revmesh2074.workers.dev` | 334 | 287 | 47 | 0 |
| `sistaminuten.se` | 260 | 6 | 0 | 254 |
| `afbudsrejser.dk` | 259 | 6 | 0 | 253 |
| `akkilahdot.fi` | 259 | 6 | 0 | 253 |
| `restplass.no` | 259 | 6 | 0 | 253 |
| `socialloop.ai` | 250 | 250 | 0 | 0 |
| 10378 other operators | 45847 | 43128 | 2616 | 103 |
