# MCP server tool changes

Last change observed 2026-10-29T06:32:47+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

58947 changes to a tool definition: 2482 npm releases (2236 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 56465 readings of hosted servers that found their tools changed; 2922 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-29 | `remote/com.rycrentals/deals` | 2026-10-28T212532296711 -> 2026-10-29T063251893261 | 4 changed | quiet |
| 2026-10-29 | `remote/no.restplass/travel-search` | 2026-10-28T212531878769 -> 2026-10-29T063248080987 | 1 changed | quiet |
| 2026-10-29 | `remote/com.meridiandispatch/travel-guides` | 2026-10-27T112539053316 -> 2026-10-29T063246063702 | 1 changed | quiet |
| 2026-10-29 | `remote/dk.afbudsrejser/travel-search` | 2026-10-28T212519986941 -> 2026-10-29T063241168584 | 1 changed | quiet |
| 2026-10-29 | `remote/io.github.rezearcher/tech-risk` | 2026-10-28T212418210827 -> 2026-10-29T063236190999 | 1 changed, 1 added | review |
| 2026-10-29 | `remote/com.quailos/quailos` | 2026-10-28T133914347459 -> 2026-10-29T063235053570 | 1 changed | quiet |
| 2026-10-29 | `remote/com.xn--5kvtwv52d/jizhineng-mcp-gateway` | 2026-10-28T133150070600 -> 2026-10-29T063235113600 | 1 added | quiet |
| 2026-10-29 | `remote/ai.greyridgesignals/tech-risk` | 2026-10-28T212437160595 -> 2026-10-29T063232488560 | 1 changed, 1 added | review |
| 2026-10-29 | `remote/io.github.travisseamon-a11y/xemstudio` | 2026-10-28T062232212494 -> 2026-10-29T063230197751 | 3 changed, 1 added | quiet |
| 2026-10-29 | `remote/io.github.brawlaphant/vealth` | 2026-10-27T112319325037 -> 2026-10-29T063230030399 | 1 added | quiet |
| 2026-10-29 | `remote/studio.gradients/mcp` | 2026-10-28T212428826898 -> 2026-10-29T063230249476 | 1 changed | quiet |
| 2026-10-29 | `remote/se.sistaminuten/travel-search` | 2026-10-28T212421415818 -> 2026-10-29T063229226386 | 1 changed | quiet |
| 2026-10-29 | `remote/pro.germanexam/germanexam` | 2026-10-28T133117700014 -> 2026-10-29T063230101637 | 5 changed (every tool) | quiet |
| 2026-10-29 | `remote/io.taifoon/coordination-layer.1` | 2026-10-28T212422299355 -> 2026-10-29T063229943581 | 2 changed | review |
| 2026-10-29 | `remote/io.github.SoapyRED/freightutils` | 2026-10-28T212427113050 -> 2026-10-29T063229970222 | 3 changed | quiet |
| 2026-10-29 | `remote/co.totalcms/docs` | 2026-10-27T210151533871 -> 2026-10-29T063228167174 | 3 changed | quiet |
| 2026-10-29 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-10-28T062200692457 -> 2026-10-29T063229088636 | 3 changed | quiet |
| 2026-10-29 | `remote/uk.co.gigstamp/gigstamp` | 2026-10-28T212416657528 -> 2026-10-29T063227216539 | 3 changed | quiet |
| 2026-10-29 | `remote/fi.akkilahdot/travel-search` | 2026-10-28T212422693092 -> 2026-10-29T063228030297 | 1 changed | quiet |
| 2026-10-29 | `remote/dev.tanod/util` | 2026-10-28T133620726773 -> 2026-10-29T063229067745 | 1 changed | quiet |
| 2026-10-29 | `remote/io.github.CodeWever/wever-labs-products` | 2026-10-28T153209461563 -> 2026-10-29T063226226813 | 10 added | quiet |
| 2026-10-29 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-28T212356429412 -> 2026-10-29T063226388365 | 3 changed | quiet |
| 2026-10-29 | `remote/io.github.miketwalker/tubepull` | 2026-10-28T133015620856 -> 2026-10-29T063224912421 | 2 changed (every tool) | quiet |
| 2026-10-29 | `remote/io.github.Embassy-of-the-Free-Mind/sourcelibrary` | 2026-10-28T153315096303 -> 2026-10-29T063225512360 | 2 changed | quiet |
| 2026-10-29 | `remote/com.sfxmint/sounds` | 2026-10-28T153310690596 -> 2026-10-29T063223869720 | 2 changed | quiet |
| 2026-10-29 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-28T062210641032 -> 2026-10-29T063223568786 | 1 changed | quiet |
| 2026-10-29 | `remote/io.github.cnghockey/sats4ai` | 2026-10-28T133420392817 -> 2026-10-29T063223723110 | 2 changed | quiet |
| 2026-10-29 | `remote/dev.tanod/web` | 2026-10-28T062153516632 -> 2026-10-29T063224498171 | 2 changed | quiet |
| 2026-10-29 | `remote/io.github.Timothymycompc/solana-pulse-gateway` | 2026-10-27T210157412477 -> 2026-10-29T063220557788 | 1 changed | quiet |
| 2026-10-29 | `remote/io.github.LKennedyShare/supplier-payment-verifier` | 2026-10-28T062148466767 -> 2026-10-29T063221122101 | 1 changed | quiet |
| 2026-10-29 | `remote/fr.synergieloc/immobilier` | 2026-10-28T212447096043 -> 2026-10-29T063223991470 | 26 added | quiet |
| 2026-10-29 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-28T212404921731 -> 2026-10-29T063220945712 | 1 changed | quiet |
| 2026-10-29 | `remote/com.probativegrowth/legal-marketing-data.5` | 2026-10-28T212345536424 -> 2026-10-29T063220291521 | 6 changed (every tool) | quiet |
| 2026-10-29 | `remote/com.probativegrowth/legal-marketing-data.3` | 2026-10-28T212345544361 -> 2026-10-29T063219836110 | 6 changed (every tool) | quiet |
| 2026-10-29 | `remote/io.pocketcaddie/drills` | 2026-10-28T062204010596 -> 2026-10-29T063238960858 | 3 changed | quiet |
| 2026-10-29 | `remote/br.com.scrypta/scrypta-mcp-server` | 2026-10-27T112240031665 -> 2026-10-29T063219824985 | 7 changed (every tool) | review |
| 2026-10-29 | `remote/io.github.connectivehub/sg-event-print` | 2026-10-27T111948926987 -> 2026-10-29T063217592630 | 2 changed | quiet |
| 2026-10-29 | `remote/com.thefomite/fomite` | 2026-10-28T062217364131 -> 2026-10-29T063218481425 | 1 changed | quiet |
| 2026-10-29 | `remote/com.remoshift/jobs` | 2026-10-28T212358378489 -> 2026-10-29T063218658333 | 1 changed | quiet |
| 2026-10-29 | `remote/com.aex402/rpc` | 2026-10-28T133106396802 -> 2026-10-29T063218786370 | 1 changed | quiet |
| 2026-10-29 | `remote/com.probativegrowth/legal-marketing-data.6` | 2026-10-28T212355183555 -> 2026-10-29T063217248053 | 7 changed (every tool) | quiet |
| 2026-10-29 | `remote/com.probativegrowth/legal-marketing-data.4` | 2026-10-28T212355263050 -> 2026-10-29T063217227275 | 6 changed (every tool) | quiet |
| 2026-10-29 | `remote/ai.rokha/rokha` | 2026-10-27T054045686852 -> 2026-10-29T063217427332 | 7 changed, 1 added, 266 removed | quiet |
| 2026-10-29 | `remote/io.github.scraping-api-plans/web-data-plan-finder` | 2026-10-27T210136346977 -> 2026-10-29T063217926983 | 4 changed | quiet |
| 2026-10-29 | `remote/fun.pumpdata/pumpdata` | 2026-10-28T133032427970 -> 2026-10-29T063216199953 | 12 changed (every tool) | quiet |
| 2026-10-29 | `remote/dev.tanod/tanod` | 2026-10-28T062212001620 -> 2026-10-29T063218589908 | 6 changed, 3 added | quiet |
| 2026-10-29 | `remote/dev.tanod/docs` | 2026-10-28T062211650952 -> 2026-10-29T063217974285 | 2 changed | quiet |
| 2026-10-29 | `remote/dev.tanod/agents` | 2026-10-28T062211295650 -> 2026-10-29T063217709581 | 1 changed | quiet |
| 2026-10-29 | `remote/dev.nichedb/nichedb` | 2026-10-28T212348670692 -> 2026-10-29T063215761210 | 1 added | quiet |
| 2026-10-29 | `remote/com.probativegrowth/legal-marketing-data.2` | 2026-10-28T212427646326 -> 2026-10-29T063215158029 | 6 changed (every tool) | quiet |
| 2026-10-29 | `remote/com.probativegrowth/legal-marketing-data` | 2026-10-28T212427865830 -> 2026-10-29T063214993019 | 23 changed | quiet |
| 2026-10-29 | `remote/io.github.Fizzl13/presign-guard` | 2026-10-27T210143016733 -> 2026-10-29T063215208942 | 10 changed (every tool) | quiet |
| 2026-10-29 | `remote/com.multicinesortega/cartelera` | 2026-10-28T212347840282 -> 2026-10-29T063215616574 | 1 changed | quiet |
| 2026-10-29 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-10-28T212346194861 -> 2026-10-29T063214363192 | 18 changed | quiet |
| 2026-10-29 | `remote/im.peoplesearch/email-finder` | 2026-10-28T133001917778 -> 2026-10-29T063213764673 | 1 changed | quiet |
| 2026-10-29 | `remote/com.voicedispatcher/mcp-near-me` | 2026-10-28T153129835542 -> 2026-10-29T063212929555 | 2 changed | quiet |
| 2026-10-29 | `remote/io.github.alanwang100/jizhineng-mcp` | 2026-10-28T133058692621 -> 2026-10-29T063215208033 | 1 added | quiet |
| 2026-10-29 | `remote/io.github.lbailey94/whitemagic-mcp` | 2026-10-28T133049417709 -> 2026-10-29T063211012204 | 1 added | quiet |
| 2026-10-29 | `remote/com.xn--5kvtwv52d/jizhineng-mcp` | 2026-10-28T133058526782 -> 2026-10-29T063214541081 | 1 added | quiet |
| 2026-10-29 | `remote/ai.switchapp/switch` | 2026-10-28T132615991586 -> 2026-10-29T063211440100 | 4 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 38725 substantive, 19516 that changed only numbers (a catalogue counter ticking, a date), 706 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 32228 | 13994 | 18234 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1009 | 1009 | 0 | 0 |
| `caseyjhand.com` | 245 | 245 | 0 | 0 |
| `sistaminuten.se` | 167 | 5 | 0 | 162 |
| `afbudsrejser.dk` | 166 | 5 | 0 | 161 |
| `akkilahdot.fi` | 166 | 5 | 0 | 161 |
| `restplass.no` | 166 | 5 | 0 | 161 |
| `socialloop.ai` | 160 | 160 | 0 | 0 |
| `remoshift.com` | 136 | 8 | 128 | 0 |
| `revmesh2074.workers.dev` | 129 | 116 | 13 | 0 |
| `fundinglandscape.com` | 128 | 81 | 47 | 0 |
| 6331 other operators | 21906 | 20751 | 1094 | 61 |
