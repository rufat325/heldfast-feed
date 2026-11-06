# MCP server tool changes

Last change observed 2026-11-06T21:48:58+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

79771 changes to a tool definition: 3402 npm releases (3156 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 76369 readings of hosted servers that found their tools changed; 3503 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-06 | `remote/ai.usedby/usedby` | 2026-11-05T115441940901 -> 2026-11-06T214859019491 | 6 changed | quiet |
| 2026-11-06 | `remote/io.taifoon/coordination-layer.1` | 2026-11-06T162207846341 -> 2026-11-06T214858637210 | 2 changed | review |
| 2026-11-06 | `remote/se.sistaminuten/travel-search` | 2026-11-06T162207284267 -> 2026-11-06T214857920209 | 1 changed | quiet |
| 2026-11-06 | `remote/com.anchorterminal/anchor-terminal` | 2026-11-05T010736416095 -> 2026-11-06T214853868046 | 1 changed, 2 added | quiet |
| 2026-11-06 | `remote/ai.arcreport/ask` | 2026-11-06T144745271829 -> 2026-11-06T214853427224 | 1 changed | quiet |
| 2026-11-06 | `remote/com.xquik/mcp` | 2026-11-06T144945607537 -> 2026-11-06T214845675242 | 1 changed | quiet |
| 2026-11-06 | `remote/com.synthexforge.x402/paid-agent-services` | 2026-11-06T162155887059 -> 2026-11-06T214846441518 | 2 changed, 3 added | quiet |
| 2026-11-06 | `remote/no.restplass/travel-search` | 2026-11-06T162147289331 -> 2026-11-06T214843078606 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.imokokok/insight-oracle` | 2026-11-06T144922038341 -> 2026-11-06T214845226825 | 5 changed, 11 added, 76 removed (every tool) | quiet |
| 2026-11-06 | `remote/io.github.openaccountants/openaccountants` | 2026-11-06T144832066134 -> 2026-11-06T214842732975 | 2 changed | quiet |
| 2026-11-06 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-06T144849989880 -> 2026-11-06T214842282227 | 1 changed | quiet |
| 2026-11-06 | `remote/de.objelio/immobiliensuche` | 2026-11-04T150751453589 -> 2026-11-06T214843299241 | 3 changed | quiet |
| 2026-11-06 | `remote/dk.afbudsrejser/travel-search` | 2026-11-06T162144128136 -> 2026-11-06T214839860593 | 1 changed | quiet |
| 2026-11-06 | `remote/studio.gradients/mcp` | 2026-11-06T162152028457 -> 2026-11-06T214840470251 | 1 changed | quiet |
| 2026-11-06 | `remote/es.proceres/proceres` | 2026-11-06T162143070081 -> 2026-11-06T214837599076 | 1 changed, 1 added | quiet |
| 2026-11-06 | `remote/ai.trydock/dock` | 2026-11-05T115548086790 -> 2026-11-06T214837860595 | 2 changed | quiet |
| 2026-11-06 | `remote/org.thealibrary/thea` | 2026-11-06T144640332919 -> 2026-11-06T214835054265 | 1 changed | quiet |
| 2026-11-06 | `remote/fi.akkilahdot/travel-search` | 2026-11-06T162150796327 -> 2026-11-06T214836180260 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.seasonsagents-art/webaz` | 2026-11-05T124827584743 -> 2026-11-06T214832601250 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.privatelawattorneys/wiki-private-law` | 2026-11-06T162151101161 -> 2026-11-06T214835011151 | 3 changed | quiet |
| 2026-11-06 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-06T072825763836 -> 2026-11-06T214833636033 | 16 added | review |
| 2026-11-06 | `remote/xyz.orkidlabs/orkid-swap` | 2026-11-06T162136129118 -> 2026-11-06T214832076877 | 1 added | review |
| 2026-11-06 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-06T162150141649 -> 2026-11-06T214836277096 | 11 changed | quiet |
| 2026-11-06 | `remote/io.github.suanrongbaicai/vibecodepicks` | 2026-11-06T144805878780 -> 2026-11-06T214831609433 | 3 changed | quiet |
| 2026-11-06 | `remote/com.supercatch/supercatch` | 2026-11-06T072803666154 -> 2026-11-06T214831993492 | 12 changed, 27 added, 21 removed | quiet |
| 2026-11-06 | `remote/io.github.spree/ecommerce-docs` | 2026-11-04T200743365032 -> 2026-11-06T214831065079 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-06T072804505667 -> 2026-11-06T214833517849 | 1 removed | quiet |
| 2026-11-06 | `remote/co.civai.nova/mcp-firecrawl` | 2026-11-06T144324715484 -> 2026-11-06T214831423822 | 3 added | review |
| 2026-11-06 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-06T144725796384 -> 2026-11-06T214830150241 | 2 changed | quiet |
| 2026-11-06 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-06T144724234858 -> 2026-11-06T214829378386 | 1 changed | quiet |
| 2026-11-06 | `remote/com.tetheredtrust/tethered-trust` | 2026-11-06T144718663913 -> 2026-11-06T214828266217 | 4 changed, 1 added | quiet |
| 2026-11-06 | `remote/com.scienceshot/data-centres` | 2026-11-05T115350959044 -> 2026-11-06T214829053698 | 2 changed, 5 added, 5 removed | quiet |
| 2026-11-06 | `remote/xyz.t0ll/toll` | 2026-11-06T072820862514 -> 2026-11-06T214827482631 | 5 added | quiet |
| 2026-11-06 | `remote/io.github.theluckystrike/work-order` | 2026-11-06T144244186348 -> 2026-11-06T214827045036 | 11 changed | quiet |
| 2026-11-06 | `remote/io.github.theluckystrike/timer-tracking` | 2026-11-06T144244084066 -> 2026-11-06T214826696899 | 16 changed | quiet |
| 2026-11-06 | `remote/io.github.theluckystrike/supplier-list` | 2026-11-06T144244072823 -> 2026-11-06T214826574616 | 9 changed | quiet |
| 2026-11-06 | `remote/io.github.theluckystrike/prices-deal` | 2026-11-06T144244761504 -> 2026-11-06T214827066191 | 7 changed | quiet |
| 2026-11-06 | `remote/io.github.theluckystrike/onboarding` | 2026-11-06T144244392080 -> 2026-11-06T214826441389 | 8 changed | quiet |
| 2026-11-06 | `remote/io.github.theluckystrike/image-resize-convert-compress-watermark` | 2026-11-06T144243690948 -> 2026-11-06T214826942681 | 13 changed | quiet |
| 2026-11-06 | `remote/io.github.theluckystrike/deliverable-tracker` | 2026-11-06T144242719606 -> 2026-11-06T214827526178 | 11 changed | quiet |
| 2026-11-06 | `remote/io.github.theluckystrike/bill-of-sale` | 2026-11-06T144243165398 -> 2026-11-06T214826255523 | 8 changed | quiet |
| 2026-11-06 | `remote/io.github.theluckystrike/bank-statement-csv-categorize-reconcile-ledger` | 2026-11-06T144243780263 -> 2026-11-06T214826171545 | 12 changed | quiet |
| 2026-11-06 | `remote/io.github.theluckystrike/backlink-checker` | 2026-11-06T144243063024 -> 2026-11-06T214826060537 | 7 changed | quiet |
| 2026-11-06 | `remote/io.github.theluckystrike/asset-register` | 2026-11-06T144243936582 -> 2026-11-06T214825805732 | 8 changed | quiet |
| 2026-11-06 | `remote/com.yutai/mcp` | 2026-11-05T222146929578 -> 2026-11-06T214826981051 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.Payotte-com/payotte-mcp` | 2026-11-04T150132466403 -> 2026-11-06T214825225581 | 1 added | quiet |
| 2026-11-06 | `remote/com.psychologieetserenite/catalogue` | 2026-11-05T150436811296 -> 2026-11-06T214825049886 | 4 changed | quiet |
| 2026-11-06 | `remote/com.probativegrowth/legal-marketing-data` | 2026-11-05T115251043894 -> 2026-11-06T214824641071 | 1 changed | quiet |
| 2026-11-06 | `remote/io.github.theluckystrike/zip-archive-create-extract-bomb-guard` | 2026-11-06T144242238114 -> 2026-11-06T214820187103 | 10 changed | quiet |
| 2026-11-06 | `remote/io.github.theluckystrike/timezone-world-clock-meeting-slots-overlap-ics` | 2026-11-06T144242884120 -> 2026-11-06T214820180224 | 9 changed | quiet |
| 2026-11-06 | `remote/io.github.theluckystrike/time-tracker-timesheet-billable-hours` | 2026-11-06T144242032387 -> 2026-11-06T214821075141 | 16 changed | quiet |
| 2026-11-06 | `remote/io.github.theluckystrike/service-agreement` | 2026-11-06T144242025856 -> 2026-11-06T214820033782 | 8 changed | quiet |
| 2026-11-06 | `remote/io.github.theluckystrike/recurring-invoice-scheduler-subscription-billing-due-reminders` | 2026-11-06T144241656675 -> 2026-11-06T214820571812 | 13 changed | quiet |
| 2026-11-06 | `remote/io.github.theluckystrike/leave` | 2026-11-06T144242005547 -> 2026-11-06T214819649729 | 11 changed | quiet |
| 2026-11-06 | `remote/io.github.theluckystrike/job-card` | 2026-11-06T144242212011 -> 2026-11-06T214819695672 | 10 changed | quiet |
| 2026-11-06 | `remote/io.github.theluckystrike/invoice-pdf-billing-generator` | 2026-11-06T144241757347 -> 2026-11-06T214819715889 | 11 changed | quiet |
| 2026-11-06 | `remote/io.github.theluckystrike/expense-tracker-receipts-mileage` | 2026-11-06T144241281462 -> 2026-11-06T214819664758 | 13 changed | quiet |
| 2026-11-06 | `remote/io.github.theluckystrike/dunning-letters` | 2026-11-06T144240992224 -> 2026-11-06T214820207114 | 10 changed | quiet |
| 2026-11-06 | `remote/io.github.theluckystrike/docx-document-generator-proposal-contract-markdown` | 2026-11-06T144241286236 -> 2026-11-06T214820826934 | 12 changed | quiet |
| 2026-11-06 | `remote/io.github.theluckystrike/contract-clause-library-proposal-template-docx` | 2026-11-06T144240728730 -> 2026-11-06T214819211809 | 11 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 49702 substantive, 29201 that changed only numbers (a catalogue counter ticking, a date), 868 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 43271 | 15883 | 27388 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1604 | 1604 | 0 | 0 |
| `caseyjhand.com` | 354 | 354 | 0 | 0 |
| `sistaminuten.se` | 204 | 6 | 0 | 198 |
| `afbudsrejser.dk` | 203 | 6 | 0 | 197 |
| `akkilahdot.fi` | 203 | 6 | 0 | 197 |
| `restplass.no` | 203 | 6 | 0 | 197 |
| `socialloop.ai` | 195 | 195 | 0 | 0 |
| `modevc.com` | 174 | 174 | 0 | 0 |
| `revmesh2074.workers.dev` | 173 | 153 | 20 | 0 |
| `remoshift.com` | 165 | 14 | 151 | 0 |
| 7810 other operators | 30681 | 28960 | 1642 | 79 |
