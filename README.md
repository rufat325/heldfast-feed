# MCP server tool changes

Last change observed 2026-11-26T00:48:02+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 18238 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 43073 hosted endpoints (read daily, and every four hours while they keep changing).

139160 changes to a tool definition: 5427 npm releases (5181 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 133733 readings of hosted servers that found their tools changed; 5124 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-26 | `remote/studio.gradients/mcp` | 2026-11-25T175045276072 -> 2026-11-26T004803477333 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.EasyGerber/easygerber` | 2026-11-25T035028929206 -> 2026-11-26T004803014396 | 7 changed | quiet |
| 2026-11-26 | `remote/fi.akkilahdot/travel-search` | 2026-11-25T175011757034 -> 2026-11-26T004802714335 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-25T110108909175 -> 2026-11-26T004801553913 | 1 changed | quiet |
| 2026-11-26 | `remote/com.weverlabs/agentic-rails` | 2026-11-25T035010537967 -> 2026-11-26T004807493725 | 8 added | quiet |
| 2026-11-26 | `remote/com.vuntum/mcp` | 2026-11-25T110049900151 -> 2026-11-26T004802586868 | 2 changed | quiet |
| 2026-11-26 | `remote/io.github.veredamonte-glitch/verithic` | 2026-11-25T035004030063 -> 2026-11-26T004803810726 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-25T150344459681 -> 2026-11-26T004801290981 | 3 changed | quiet |
| 2026-11-26 | `remote/tech.upto/up-to-tech` | 2026-11-25T150341269316 -> 2026-11-26T004759586378 | 3 changed, 1 added | quiet |
| 2026-11-26 | `remote/gs.sundo/sundogs` | 2026-11-24T170038003642 -> 2026-11-26T004756106029 | 12 changed | quiet |
| 2026-11-26 | `remote/com.andque/agent-data` | 2026-11-25T174801579695 -> 2026-11-26T004752555588 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-25T174733463275 -> 2026-11-26T004739661561 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.bnth09productions-maker/scrapling-x402-store` | 2026-11-25T174649198808 -> 2026-11-26T004732494532 | 8 changed | review |
| 2026-11-26 | `remote/com.serviche/sergio` | 2026-11-25T034955266252 -> 2026-11-26T004736763822 | 3 changed, 10 added | review |
| 2026-11-26 | `remote/net.repleader/mcp` | 2026-11-24T165822458308 -> 2026-11-26T004725412953 | 1 added | quiet |
| 2026-11-26 | `remote/com.rabbitimport/rabbit` | 2026-11-25T150318275521 -> 2026-11-26T004722304461 | 1 added | quiet |
| 2026-11-26 | `remote/com.qurangallery/mcp` | 2026-11-25T105659894991 -> 2026-11-26T004721658398 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.LusoCryptoLabs/ckb-pulse` | 2026-11-25T174543866475 -> 2026-11-26T004724103809 | 1 added | quiet |
| 2026-11-26 | `remote/com.promptandco/operational-memory` | 2026-11-25T174534696351 -> 2026-11-26T004713991382 | 2 changed | quiet |
| 2026-11-26 | `remote/no.pristavla/pristavla` | 2026-11-25T150313259550 -> 2026-11-26T004711125266 | 1 changed | quiet |
| 2026-11-26 | `remote/me.phor/phorme-training` | 2026-11-24T165707527848 -> 2026-11-26T004707324426 | 1 changed, 2 added | quiet |
| 2026-11-26 | `remote/com.ownyouragent/agentvoordeur` | 2026-11-25T174442910421 -> 2026-11-26T004707607170 | 2 changed | quiet |
| 2026-11-26 | `remote/io.github.ashadow07/karmadue.1` | 2026-11-25T034931933363 -> 2026-11-26T004703406407 | 1 changed | quiet |
| 2026-11-26 | `remote/com.multicinesortega/cartelera` | 2026-11-25T105458529438 -> 2026-11-26T004656558235 | 1 changed | quiet |
| 2026-11-26 | `remote/rent.mera/mera-rent` | 2026-11-25T174328342999 -> 2026-11-26T004648753013 | 1 changed | quiet |
| 2026-11-26 | `remote/il.co.taseli/taseli` | 2026-11-24T050307567310 -> 2026-11-26T004637086331 | 2 changed | quiet |
| 2026-11-26 | `remote/com.toiseai/toise` | 2026-11-25T174250589506 -> 2026-11-26T004641474016 | 2 changed | quiet |
| 2026-11-26 | `remote/com.ticketfairy/ticket-fairy-public-events` | 2026-11-25T110434812640 -> 2026-11-26T004633010042 | 31 changed | quiet |
| 2026-11-26 | `remote/com.robotcantina/robot-cantina` | 2026-11-24T182454591702 -> 2026-11-26T004632345988 | 3 added | quiet |
| 2026-11-26 | `remote/com.notacompany/newsletter` | 2026-11-25T035032000811 -> 2026-11-26T004631753606 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-25T175157231237 -> 2026-11-26T004631169219 | 1 changed | quiet |
| 2026-11-26 | `remote/ai.robowrite/mcp` | 2026-11-25T174221004399 -> 2026-11-26T004633952118 | 1 changed | quiet |
| 2026-11-26 | `remote/com.whizbrew/whizbrew` | 2026-11-25T035024492723 -> 2026-11-26T004628658787 | 15 changed, 3 removed (every tool) | quiet |
| 2026-11-26 | `remote/io.suverse.versum/catalog` | 2026-11-25T150342180528 -> 2026-11-26T004628980048 | 3 changed | quiet |
| 2026-11-26 | `remote/io.bitbucket.markedet/field-notes` | 2026-11-25T110223928882 -> 2026-11-26T004627269154 | 1 changed | quiet |
| 2026-11-26 | `remote/com.theskillharbor/skill-harbor` | 2026-11-25T035017840470 -> 2026-11-26T004626003424 | 1 changed | quiet |
| 2026-11-26 | `remote/com.eduavenues/eduavenues` | 2026-11-25T175008470594 -> 2026-11-26T004627333669 | 6 changed, 1 added | quiet |
| 2026-11-26 | `remote/il.co.taseli/taseli.1` | 2026-11-24T165249373406 -> 2026-11-26T004625769459 | 2 changed | quiet |
| 2026-11-26 | `remote/com.sulihuli/catalog` | 2026-11-25T110101399969 -> 2026-11-26T004624745473 | 2 changed | quiet |
| 2026-11-26 | `remote/com.caelaralabs/social` | 2026-11-25T174822142285 -> 2026-11-26T004623698500 | 1 changed, 1 added | quiet |
| 2026-11-26 | `remote/design.sleek/sleek` | 2026-11-24T165157728820 -> 2026-11-26T004623825405 | 3 changed | quiet |
| 2026-11-26 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-11-25T035006698576 -> 2026-11-26T004622700942 | 1 changed | quiet |
| 2026-11-26 | `remote/io.github.magichourhq/magic-hour` | 2026-11-25T034913516793 -> 2026-11-26T004623027327 | 2 changed | quiet |
| 2026-11-26 | `remote/it.lazyanalysis/lazyanalysis` | 2026-11-25T105203955102 -> 2026-11-26T004622130403 | 1 changed, 2 added | quiet |
| 2026-11-26 | `remote/com.imagiolabs.www/imagio-relay` | 2026-11-25T150318526972 -> 2026-11-26T004617637833 | 20 changed | review |
| 2026-11-26 | `remote/de.jobroulette/jobroulette` | 2026-11-25T150244374250 -> 2026-11-26T004615343247 | 8 changed, 2 added | quiet |
| 2026-11-26 | `remote/com.goalrace/goal-race` | 2026-11-25T034907867094 -> 2026-11-26T004608318204 | 8 changed | quiet |
| 2026-11-26 | `remote/club.goodleads/new-business-owner-contacts` | 2026-11-24T165142317356 -> 2026-11-26T004608329473 | 2 changed | quiet |
| 2026-11-26 | `remote/dev.pdfops/pdfops-mcp` | 2026-11-25T034959526056 -> 2026-11-26T004606323118 | 24 changed (every tool) | quiet |
| 2026-11-26 | `remote/io.github.daniel3303/equibles` | 2026-11-25T173959110468 -> 2026-11-26T004607393040 | 2 changed | quiet |
| 2026-11-26 | `remote/com.veridionmarkets/disclosures` | 2026-11-25T035028151975 -> 2026-11-26T004556846187 | 1 changed | quiet |
| 2026-11-26 | `remote/uk.co.pricegraph/mcp` | 2026-11-24T050517426754 -> 2026-11-26T004554617443 | 21 changed (every tool) | quiet |
| 2026-11-26 | `remote/se.sistaminuten/travel-search` | 2026-11-25T175110541217 -> 2026-11-26T004555230914 | 1 changed | quiet |
| 2026-11-26 | `remote/io.suverse.www/catalog` | 2026-11-25T150408175906 -> 2026-11-26T004556735371 | 3 changed | quiet |
| 2026-11-26 | `remote/io.github.farenberglord-star/orb-studio` | 2026-11-25T174459730514 -> 2026-11-26T004602311392 | 1 changed | quiet |
| 2026-11-26 | `remote/com.boxerbook/boxing` | 2026-11-25T150233940312 -> 2026-11-26T004554026911 | 3 changed | quiet |
| 2026-11-26 | `remote/com.whereboatsanchor/anchorages` | 2026-11-25T105823670366 -> 2026-11-26T004551483461 | 2 changed | quiet |
| 2026-11-26 | `remote/com.viraloutliers/viral-outliers` | 2026-11-25T174911154140 -> 2026-11-26T004550603546 | 1 changed | quiet |
| 2026-11-26 | `remote/pro.aicut/aicut` | 2026-11-25T173845692698 -> 2026-11-26T004545527027 | 5 changed, 1 added | quiet |
| 2026-11-26 | `remote/io.github.Red-Center-Studio/nocode-migrator` | 2026-11-25T034954824313 -> 2026-11-26T004547807483 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 92798 substantive, 45143 that changed only numbers (a catalogue counter ticking, a date), 1219 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 76752 | 34678 | 42074 | 0 |
| `a2awire.com` | 3838 | 3838 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 536 | 536 | 0 | 0 |
| `modevc.com` | 480 | 480 | 0 | 0 |
| `civai.co` | 401 | 401 | 0 | 0 |
| `revmesh2074.workers.dev` | 370 | 315 | 55 | 0 |
| `sistaminuten.se` | 284 | 7 | 0 | 277 |
| `afbudsrejser.dk` | 283 | 7 | 0 | 276 |
| `akkilahdot.fi` | 283 | 7 | 0 | 276 |
| `restplass.no` | 283 | 7 | 0 | 276 |
| `socialloop.ai` | 274 | 274 | 0 | 0 |
| 11495 other operators | 53035 | 49907 | 3014 | 114 |
