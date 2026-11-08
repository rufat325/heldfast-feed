# MCP server tool changes

Last change observed 2026-11-08T06:46:18+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

82761 changes to a tool definition: 3503 npm releases (3257 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 79258 readings of hosted servers that found their tools changed; 3566 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-08 | `remote/ng.com.xpressflowsystems.www/esim-domains` | 2026-11-07T203345536211 -> 2026-11-08T064621459527 | 2 changed | quiet |
| 2026-11-08 | `remote/ai.robowrite/mcp` | 2026-11-07T133727016803 -> 2026-11-08T064618013578 | 5 changed, 8 added | quiet |
| 2026-11-08 | `remote/studio.gradients/mcp` | 2026-11-08T000130786620 -> 2026-11-08T064614573280 | 1 changed | quiet |
| 2026-11-08 | `remote/fi.akkilahdot/travel-search` | 2026-11-08T000129808124 -> 2026-11-08T064611983997 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.privatelawattorneys/wiki-private-law` | 2026-11-07T133635099731 -> 2026-11-08T064613774870 | 3 changed | quiet |
| 2026-11-08 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-07T064017991496 -> 2026-11-08T064611721574 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-07T203338085297 -> 2026-11-08T064612406163 | 16 added | review |
| 2026-11-08 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-08T000129441517 -> 2026-11-08T064618497530 | 3 changed | quiet |
| 2026-11-08 | `remote/xyz.t0ll/toll` | 2026-11-06T214827482631 -> 2026-11-08T064607765099 | 2 changed | quiet |
| 2026-11-08 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-06T214829378386 -> 2026-11-08T064608924826 | 1 changed | quiet |
| 2026-11-08 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-07T203335971364 -> 2026-11-08T064610242578 | 3 changed | quiet |
| 2026-11-08 | `remote/com.tetheredtrust/tethered-trust` | 2026-11-08T000125816986 -> 2026-11-08T064608306132 | 1 added | quiet |
| 2026-11-08 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-08T000124949271 -> 2026-11-08T064607013315 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.liad142/yedapo` | 2026-11-07T064010995335 -> 2026-11-08T064604186662 | 2 changed (every tool) | quiet |
| 2026-11-08 | `remote/dev.workers.x402-bazaar-rank-worker.x402-bazaar-rank/x402-bazaar-rank` | 2026-11-07T133955945065 -> 2026-11-08T064604934304 | 7 changed, 1 removed | quiet |
| 2026-11-08 | `remote/no.restplass/travel-search` | 2026-11-08T000131943493 -> 2026-11-08T064603918673 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.ceedot-rock/slid-phi-labs` | 2026-11-07T203341199464 -> 2026-11-08T064603445544 | 1 added | quiet |
| 2026-11-08 | `remote/com.sapiensinteticos/sapiens` | 2026-11-07T064009802160 -> 2026-11-08T064603534011 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.scraping-api-plans/web-data-plan-finder` | 2026-11-07T133319675253 -> 2026-11-08T064602859870 | 5 changed, 2 added | review |
| 2026-11-08 | `remote/com.droneclearthailand/droneclear-thailand` | 2026-11-07T133810489463 -> 2026-11-08T064602269731 | 1 changed | quiet |
| 2026-11-08 | `remote/dk.afbudsrejser/travel-search` | 2026-11-08T000129376952 -> 2026-11-08T064601395653 | 1 changed | quiet |
| 2026-11-08 | `remote/com.supercatch/supercatch` | 2026-11-07T203333873605 -> 2026-11-08T064556976821 | 8 changed, 3 added | quiet |
| 2026-11-08 | `remote/com.obriym-crm/mcp` | 2026-11-07T203322625350 -> 2026-11-08T064557668189 | 3 changed, 5 added | quiet |
| 2026-11-08 | `remote/com.multicinesortega/cartelera` | 2026-11-08T000118786970 -> 2026-11-08T064557024151 | 1 changed | quiet |
| 2026-11-08 | `remote/com.googleapis.monitoring/mcp` | 2026-11-07T151323410281 -> 2026-11-08T064553843189 | 5 changed | quiet |
| 2026-11-08 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-07T133205074658 -> 2026-11-08T064554766441 | 4 added | quiet |
| 2026-11-08 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-08T000126047972 -> 2026-11-08T064558107556 | 1 added, 24 removed | quiet |
| 2026-11-08 | `remote/media.southpow/fact` | 2026-11-07T133338264912 -> 2026-11-08T064552665377 | 3 added | quiet |
| 2026-11-08 | `remote/xyz.tereno/tereno` | 2026-11-06T144831259794 -> 2026-11-08T064549977009 | 2 changed, 1 added | quiet |
| 2026-11-08 | `remote/io.github.mike-lblc/x402-bazaar-rank` | 2026-11-07T133940474166 -> 2026-11-08T064550388278 | 7 changed, 1 removed | quiet |
| 2026-11-08 | `remote/se.sistaminuten/travel-search` | 2026-11-08T000119274818 -> 2026-11-08T064549361066 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-07T203335755073 -> 2026-11-08T064544530918 | 3 changed | quiet |
| 2026-11-08 | `remote/to.trustmebro/trust-me-bro` | 2026-11-07T133328142445 -> 2026-11-08T064542480684 | 5 changed (every tool) | quiet |
| 2026-11-08 | `remote/io.github.untitledfinancial/dpx` | 2026-11-07T151336763487 -> 2026-11-08T064542313909 | 111 changed (every tool) | review |
| 2026-11-08 | `remote/io.github.Yahhi/aimyear-mcp` | 2026-11-07T132752988101 -> 2026-11-08T064542310981 | 10 changed, 4 added | quiet |
| 2026-11-08 | `remote/com.animatedwebs/animatedwebs` | 2026-11-07T132801854180 -> 2026-11-08T064544232632 | 11 changed, 4 added, 6 removed (every tool) | quiet |
| 2026-11-08 | `remote/com.idosgames/platform` | 2026-11-07T203348636539 -> 2026-11-08T064541908731 | 1 changed | review |
| 2026-11-08 | `remote/com.esqcopilot/matching-engine` | 2026-11-07T063940541910 -> 2026-11-08T064542164977 | 2 changed | quiet |
| 2026-11-08 | `remote/ai.signal8/mcp` | 2026-11-07T063948734611 -> 2026-11-08T064541844276 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.si-imtiaz/leadquasar` | 2026-11-08T000106522081 -> 2026-11-08T064543448779 | 1 changed | quiet |
| 2026-11-08 | `remote/es.proceres/proceres` | 2026-11-08T000110862251 -> 2026-11-08T064539148206 | 2 changed | quiet |
| 2026-11-08 | `remote/com.indiainsurances/mcp` | 2026-11-06T143839310678 -> 2026-11-08T064539805810 | 5 changed, 9 added | quiet |
| 2026-11-08 | `remote/io.github.jake-zaiba/deai-research` | 2026-11-07T063947860138 -> 2026-11-08T064538262686 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.Marsell-Official/marsell` | 2026-11-07T203259170367 -> 2026-11-08T064537578459 | 2 changed | quiet |
| 2026-11-08 | `remote/me.freehire/freehire` | 2026-11-08T000101561396 -> 2026-11-08T064537748845 | 2 changed | quiet |
| 2026-11-08 | `remote/app.vercel.fork-for-agents/fork` | 2026-11-08T000101201893 -> 2026-11-08T064536968213 | 1 changed | quiet |
| 2026-11-08 | `remote/ca.dispola/places` | 2026-11-06T143528346020 -> 2026-11-08T064534242880 | 1 changed | quiet |
| 2026-11-08 | `remote/co.civai.nova/mcp-firecrawl` | 2026-11-07T063949698948 -> 2026-11-08T064534345957 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.haiyunsky/hpsilab-quant-finance-mcp` | 2026-11-07T132621145747 -> 2026-11-08T064530112844 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.Ishan73744/aurelmark` | 2026-11-07T132122037610 -> 2026-11-08T064529873479 | 2 changed | quiet |
| 2026-11-08 | `remote/com.atabooking/mcp` | 2026-11-06T072743467873 -> 2026-11-08T064530125410 | 5 changed (every tool) | quiet |
| 2026-11-08 | `remote/io.github.sean0007/free-agent-tools` | 2026-11-07T132442958670 -> 2026-11-08T064527454496 | 1 added | quiet |
| 2026-11-08 | `remote/io.github.troothllc/trooth-network` | 2026-11-07T132021286789 -> 2026-11-08T064526879984 | 2 changed | quiet |
| 2026-11-08 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt.2` | 2026-11-08T000051353608 -> 2026-11-08T064525987234 | 1 changed | quiet |
| 2026-11-08 | `remote/dev.turva/turva-mcp` | 2026-11-07T132904833164 -> 2026-11-08T064524767605 | 1 changed | quiet |
| 2026-11-08 | `remote/com.jojapi/sms-verify` | 2026-11-06T072735378976 -> 2026-11-08T064526185792 | 1 changed | quiet |
| 2026-11-08 | `remote/com.dechonet/mcp` | 2026-11-07T203256383458 -> 2026-11-08T064525010029 | 1 added | quiet |
| 2026-11-08 | `remote/org.georgiahomeroom/georgia-homeroom` | 2026-11-07T133019193842 -> 2026-11-08T064522289248 | 1 changed | quiet |
| 2026-11-08 | `remote/io.github.firecrawl/firecrawl-mcp-server` | 2026-11-07T063938014689 -> 2026-11-08T064522694951 | 1 changed | quiet |
| 2026-11-08 | `remote/com.problee/problee` | 2026-11-07T063935063303 -> 2026-11-08T064523029019 | 4 changed, 1 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 50750 substantive, 31117 that changed only numbers (a catalogue counter ticking, a date), 894 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 45119 | 15889 | 29230 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1723 | 1723 | 0 | 0 |
| `caseyjhand.com` | 354 | 354 | 0 | 0 |
| `sistaminuten.se` | 210 | 6 | 0 | 204 |
| `afbudsrejser.dk` | 209 | 6 | 0 | 203 |
| `akkilahdot.fi` | 209 | 6 | 0 | 203 |
| `restplass.no` | 209 | 6 | 0 | 203 |
| `socialloop.ai` | 201 | 201 | 0 | 0 |
| `revmesh2074.workers.dev` | 190 | 167 | 23 | 0 |
| `civai.co` | 188 | 188 | 0 | 0 |
| `modevc.com` | 174 | 174 | 0 | 0 |
| 7919 other operators | 31634 | 29689 | 1864 | 81 |
