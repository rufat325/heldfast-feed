# MCP server tool changes

Last change observed 2026-10-28T15:33:40+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11597 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 29507 hosted endpoints (read daily, and every four hours while they keep changing).

58574 changes to a tool definition: 2482 npm releases (2236 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 56092 readings of hosted servers that found their tools changed; 2891 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-28 | `remote/io.github.eamwhite1/agent-trust` | 2026-10-27T124229493044 -> 2026-10-28T153342107819 | 9 changed | quiet |
| 2026-10-28 | `remote/se.sistaminuten/travel-search` | 2026-10-28T133502244354 -> 2026-10-28T153328709244 | 1 changed | quiet |
| 2026-10-28 | `remote/io.github.danbuildss/musecourt` | 2026-10-26T133902441303 -> 2026-10-28T153325379403 | 2 changed | quiet |
| 2026-10-28 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-10-28T062226905205 -> 2026-10-28T153324942458 | 1 changed | quiet |
| 2026-10-28 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-28T133535955467 -> 2026-10-28T153318943416 | 4 changed, 1 added | quiet |
| 2026-10-28 | `remote/io.github.Embassy-of-the-Free-Mind/sourcelibrary` | 2026-10-27T112155248994 -> 2026-10-28T153315096303 | 2 changed | quiet |
| 2026-10-28 | `remote/com.sfxmint/sounds` | 2026-10-27T112127871654 -> 2026-10-28T153310690596 | 10 changed (every tool) | quiet |
| 2026-10-28 | `remote/no.restplass/travel-search` | 2026-10-28T133500220973 -> 2026-10-28T153308144475 | 1 changed | quiet |
| 2026-10-28 | `remote/dk.afbudsrejser/travel-search` | 2026-10-28T133416061250 -> 2026-10-28T153302527381 | 1 changed | quiet |
| 2026-10-28 | `remote/com.probativegrowth/legal-marketing-data.3` | 2026-10-28T062204614215 -> 2026-10-28T153300829039 | 3 changed | quiet |
| 2026-10-28 | `remote/ai.popdot/popdot-mcp` | 2026-10-28T133314510503 -> 2026-10-28T153300438875 | 2 changed | quiet |
| 2026-10-28 | `remote/pl.przetargowyjanusz/tenders` | 2026-10-28T133123931399 -> 2026-10-28T153252248345 | 4 changed, 2 added | quiet |
| 2026-10-28 | `remote/md.mostlyright/datasets` | 2026-10-27T111909706503 -> 2026-10-28T153248249945 | 2 changed | quiet |
| 2026-10-28 | `remote/com.pagetovid/pagetovid` | 2026-10-26T133504136769 -> 2026-10-28T153244605891 | 1 changed | quiet |
| 2026-10-28 | `remote/io.github.guyvolvo/oceanofjobs` | 2026-10-26T133439616247 -> 2026-10-28T153241732111 | 2 changed, 2 added | quiet |
| 2026-10-28 | `remote/at.space-core/game` | 2026-10-27T054053857921 -> 2026-10-28T153239463777 | 1 changed | quiet |
| 2026-10-28 | `remote/world.tokenbank/tokenbank` | 2026-10-28T132910046248 -> 2026-10-28T153233197463 | 1 changed | quiet |
| 2026-10-28 | `remote/io.insourcia/insourcia` | 2026-10-27T111711313819 -> 2026-10-28T153224734710 | 1 changed | quiet |
| 2026-10-28 | `remote/io.github.eamwhite1/xrpl-referee` | 2026-10-27T123635400967 -> 2026-10-28T153219921771 | 9 changed | quiet |
| 2026-10-28 | `remote/com.probativegrowth/legal-marketing-data` | 2026-10-28T133025417567 -> 2026-10-28T153218880709 | 6 changed, 1 added | quiet |
| 2026-10-28 | `remote/studio.gradients/mcp` | 2026-10-28T133118229466 -> 2026-10-28T153216314931 | 1 changed | quiet |
| 2026-10-28 | `remote/io.github.qxxx5vyd77-byte/directors-lookbook` | 2026-10-27T210100114729 -> 2026-10-28T153212992294 | 1 changed | quiet |
| 2026-10-28 | `remote/fi.akkilahdot/travel-search` | 2026-10-28T133055316646 -> 2026-10-28T153211883998 | 1 changed | quiet |
| 2026-10-28 | `remote/io.github.CodeWever/wever-labs-products` | 2026-10-27T210200371111 -> 2026-10-28T153209461563 | 4 added | quiet |
| 2026-10-28 | `remote/io.github.northstar-trustrail/agent-resort` | 2026-10-26T133308300100 -> 2026-10-28T153208532275 | 19 changed, 1 added (every tool) | quiet |
| 2026-10-28 | `remote/si.divux/divux` | 2026-10-28T132800202478 -> 2026-10-28T153209352489 | 1 changed | quiet |
| 2026-10-28 | `remote/io.github.SecondShotAI/verifylite` | 2026-10-28T133027274915 -> 2026-10-28T153207935105 | 4 changed, 1 added | quiet |
| 2026-10-28 | `remote/io.github.wellknownmcp/ia-asso` | 2026-10-27T145754294405 -> 2026-10-28T153204691271 | 2 changed | quiet |
| 2026-10-28 | `remote/media.thecoop/the-coop` | 2026-10-27T112120310002 -> 2026-10-28T153202162807 | 9 changed (every tool) | quiet |
| 2026-10-28 | `remote/xyz.t0ll/toll` | 2026-10-28T132942354372 -> 2026-10-28T153158541172 | 1 added | quiet |
| 2026-10-28 | `remote/io.github.ygfalcon/solana-wallet-intel` | 2026-10-28T132920646778 -> 2026-10-28T153154372833 | 1 changed | quiet |
| 2026-10-28 | `remote/io.github.tettertotter/fundinglandscape` | 2026-10-28T131820570522 -> 2026-10-28T153155147616 | 1 changed | quiet |
| 2026-10-28 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-28T132919583784 -> 2026-10-28T153154544589 | 1 changed | quiet |
| 2026-10-28 | `remote/com.getmattered/getmattered` | 2026-10-28T132711387803 -> 2026-10-28T153151401978 | 2 changed | quiet |
| 2026-10-28 | `remote/work.finder/jobs` | 2026-10-28T132701152008 -> 2026-10-28T153146182518 | 2 changed | quiet |
| 2026-10-28 | `remote/com.remoshift/jobs` | 2026-10-28T132834042651 -> 2026-10-28T153146657804 | 1 changed | quiet |
| 2026-10-28 | `remote/com.frontrowtickets/frontrowtickets-mcp` | 2026-10-26T133045666766 -> 2026-10-28T153151749287 | 1 added | quiet |
| 2026-10-28 | `remote/co.deadbrands/arena` | 2026-10-28T132645685561 -> 2026-10-28T153145200012 | 5 changed | review |
| 2026-10-28 | `remote/com.gluecron/gluecron` | 2026-10-28T132432326921 -> 2026-10-28T153142359085 | 3 changed | quiet |
| 2026-10-28 | `remote/si.claimora/claimora` | 2026-10-26T211355745665 -> 2026-10-28T153141703606 | 1 changed | quiet |
| 2026-10-28 | `remote/com.clippingalpha/mcp` | 2026-10-27T145731402587 -> 2026-10-28T153140869090 | 1 changed | quiet |
| 2026-10-28 | `remote/io.github.FMagenticL/fmagenticl` | 2026-10-26T132451187551 -> 2026-10-28T153138629226 | 2 changed | quiet |
| 2026-10-28 | `remote/com.aiapplyd/aiapplyd` | 2026-10-28T132605486369 -> 2026-10-28T153143834557 | 2 changed | quiet |
| 2026-10-28 | `remote/io.github.gregpelts/masha-pelts-dds-guide` | 2026-10-27T210115499821 -> 2026-10-28T153138501707 | 2 changed | quiet |
| 2026-10-28 | `remote/dev.nichedb/nichedb` | 2026-10-26T211438326763 -> 2026-10-28T153135618481 | 7 added | quiet |
| 2026-10-28 | `remote/com.neblla/neblla` | 2026-10-28T132711725505 -> 2026-10-28T153136191572 | 1 added | quiet |
| 2026-10-28 | `remote/io.github.peter120525-cmd/lawmadi-os` | 2026-10-27T111635726752 -> 2026-10-28T153133998042 | 1 changed | quiet |
| 2026-10-28 | `remote/com.voicedispatcher/mcp-near-me` | 2026-10-28T132648430858 -> 2026-10-28T153129835542 | 1 changed | quiet |
| 2026-10-28 | `remote/com.difficat/difficat` | 2026-10-26T132232285437 -> 2026-10-28T153130856526 | 4 changed | quiet |
| 2026-10-28 | `remote/io.github.cypher-osiris/lumi-trades-mcp` | 2026-10-26T131850685715 -> 2026-10-28T153124848825 | 9 changed, 1 added (every tool) | quiet |
| 2026-10-28 | `remote/com.computescreener/compute-screener` | 2026-10-28T131647099046 -> 2026-10-28T153124819985 | 1 changed | quiet |
| 2026-10-28 | `remote/io.github.marvo-bd/muse-commerce-mcp` | 2026-10-26T131751569781 -> 2026-10-28T153120367436 | 4 changed (every tool) | quiet |
| 2026-10-28 | `remote/com.botquests/botquests` | 2026-10-28T062055714230 -> 2026-10-28T153117877365 | 1 changed | quiet |
| 2026-10-28 | `remote/com.foundationscounselingllc/practice` | 2026-10-28T132428576657 -> 2026-10-28T153115288976 | 2 changed | quiet |
| 2026-10-28 | `remote/co.getclippy/clippy` | 2026-10-28T132321643076 -> 2026-10-28T153106929864 | 1 changed | quiet |
| 2026-10-28 | `remote/trade.loomdesk/loomdesk` | 2026-10-27T111506572780 -> 2026-10-28T153105159386 | 1 added | quiet |
| 2026-10-28 | `remote/io.github.evolutionlabs-dev/signal-bureau` | 2026-10-28T062047796909 -> 2026-10-28T153107381221 | 2 changed | quiet |
| 2026-10-28 | `remote/io.github.gregpelts/renaissance-dental-guide` | 2026-10-27T210052383565 -> 2026-10-28T153104749140 | 2 changed | quiet |
| 2026-10-28 | `remote/io.github.SergoVashakmadze/iomarkets-ai` | 2026-10-26T132618285001 -> 2026-10-28T153100022346 | 4 changed, 2 removed | quiet |
| 2026-10-28 | `remote/com.helpyself/tools` | 2026-10-28T132210576721 -> 2026-10-28T153101008065 | 1 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 38381 substantive, 19496 that changed only numbers (a catalogue counter ticking, a date), 697 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 32228 | 13994 | 18234 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1009 | 1009 | 0 | 0 |
| `caseyjhand.com` | 244 | 244 | 0 | 0 |
| `sistaminuten.se` | 165 | 5 | 0 | 160 |
| `afbudsrejser.dk` | 164 | 5 | 0 | 159 |
| `akkilahdot.fi` | 164 | 5 | 0 | 159 |
| `restplass.no` | 164 | 5 | 0 | 159 |
| `socialloop.ai` | 158 | 158 | 0 | 0 |
| `remoshift.com` | 134 | 8 | 126 | 0 |
| `revmesh2074.workers.dev` | 129 | 116 | 13 | 0 |
| `fundinglandscape.com` | 127 | 80 | 47 | 0 |
| 6310 other operators | 21547 | 20411 | 1076 | 60 |
