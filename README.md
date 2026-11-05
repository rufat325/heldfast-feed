# MCP server tool changes

Last change observed 2026-11-05T11:57:55+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

78085 changes to a tool definition: 3309 npm releases (3063 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 74776 readings of hosted servers that found their tools changed; 3406 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-05 | `remote/ru.zakazat-zvezdu/stars` | 2026-10-27T124305012697 -> 2026-11-05T115759241000 | 1 changed, 1 removed | quiet |
| 2026-11-05 | `remote/io.github.Veniwol-Li-Lambd/lilambd-data` | 2026-11-04T010006333998 -> 2026-11-05T115757964809 | 1 changed, 1 added | quiet |
| 2026-11-05 | `remote/ai.thewholetorah/thewholetorah` | 2026-09-23T163147783910 -> 2026-11-05T115741322588 | 4 added | quiet |
| 2026-11-05 | `remote/io.github.ceedot-rock/slid-phi-labs` | 2026-10-31T130301034590 -> 2026-11-05T115733883920 | 3 added | quiet |
| 2026-11-05 | `remote/no.restplass/travel-search` | 2026-11-05T010649043462 -> 2026-11-05T115729628083 | 1 changed | quiet |
| 2026-11-05 | `remote/com.kulicadvisory/aictionbot-werkbank` | 2026-11-02T185416572629 -> 2026-11-05T115711391409 | 7 changed, 6 added (every tool) | quiet |
| 2026-11-05 | `remote/com.iscabox/iscabox` | 2026-11-04T150839518822 -> 2026-11-05T115710157236 | 1 changed | quiet |
| 2026-11-05 | `remote/show.globalconnect.www/gcs` | 2026-11-04T123820187346 -> 2026-11-05T115708206343 | 2 changed | quiet |
| 2026-11-05 | `remote/uk.co.cruisify/cruise-search` | 2026-10-17T060429827498 -> 2026-11-05T115654826006 | 2 changed | quiet |
| 2026-11-05 | `remote/ae.beachclubs/mcp` | 2026-10-26T133732229387 -> 2026-11-05T115650852456 | 1 changed | quiet |
| 2026-11-05 | `remote/dk.afbudsrejser/travel-search` | 2026-11-05T010644812555 -> 2026-11-05T115642264721 | 1 changed | quiet |
| 2026-11-05 | `remote/xyz.wafermap/wafermap` | 2026-11-02T163512568559 -> 2026-11-05T115617138387 | 3 changed | quiet |
| 2026-11-05 | `remote/com.zoningsignal/observatory` | 2026-09-28T055536408246 -> 2026-11-05T115614148126 | 2 changed | quiet |
| 2026-11-05 | `remote/io.github.zerotohundred-admin/marketplace` | 2026-10-28T133153884804 -> 2026-11-05T115612848453 | 2 changed | quiet |
| 2026-11-05 | `remote/io.github.MattJeff/orizn-visa-mcp` | 2026-11-02T163509492541 -> 2026-11-05T115616012994 | 2 changed | review |
| 2026-11-05 | `remote/com.xquik/mcp` | 2026-10-30T133117130245 -> 2026-11-05T115608347455 | 4 changed (every tool) | review |
| 2026-11-05 | `remote/com.veritaset/mcp` | 2026-11-04T005942617107 -> 2026-11-05T115609038484 | 2 changed | quiet |
| 2026-11-05 | `remote/ng.com.xpressflowsystems.www/esim-domains` | 2026-11-02T065458453485 -> 2026-11-05T115604467264 | 6 changed | quiet |
| 2026-11-05 | `remote/io.github.paulieb89/uk-legal-mcp` | 2026-10-27T054108030855 -> 2026-11-05T115554393774 | 4 changed | quiet |
| 2026-11-05 | `remote/com.plyparts/ply` | 2026-11-02T163737257516 -> 2026-11-05T115548746562 | 3 changed, 2 added | quiet |
| 2026-11-05 | `remote/ai.trydock/dock` | 2026-11-02T065443506797 -> 2026-11-05T115548086790 | 4 changed | quiet |
| 2026-11-05 | `remote/net.pagong/auctions` | 2026-11-02T163713738035 -> 2026-11-05T115545974267 | 5 changed, 2 added (every tool) | quiet |
| 2026-11-05 | `remote/com.patchmcp/patch` | 2026-11-03T195820612253 -> 2026-11-05T115546586769 | 18 added | review |
| 2026-11-05 | `remote/io.metodic/metodic` | 2026-10-08T213440459184 -> 2026-11-05T115543340139 | 1 changed | quiet |
| 2026-11-05 | `remote/com.tradeassi/mcp` | 2026-11-01T135219452228 -> 2026-11-05T115542326646 | 3 changed | quiet |
| 2026-11-05 | `remote/com.lingodew/lingodew` | 2026-11-02T163705734375 -> 2026-11-05T115540413006 | 1 changed, 1 removed | quiet |
| 2026-11-05 | `remote/com.hoteldiscount24/hotels` | 2026-10-31T130411531156 -> 2026-11-05T115536151493 | 1 changed | quiet |
| 2026-11-05 | `remote/com.hillsignal/hillsignalapp` | 2026-10-27T112236800256 -> 2026-11-05T115535166822 | 3 changed, 2 added | quiet |
| 2026-11-05 | `remote/studio.gradients/mcp` | 2026-11-05T010659916036 -> 2026-11-05T115534125652 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.philpof102-svg/tokenizedblock` | 2026-10-24T224628578659 -> 2026-11-05T115530382954 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.SoapyRED/freightutils` | 2026-11-04T200818276889 -> 2026-11-05T115530831371 | 3 changed, 1 added | quiet |
| 2026-11-05 | `remote/expert.tld/tld-expert` | 2026-11-02T163421033925 -> 2026-11-05T115532642948 | 1 changed | quiet |
| 2026-11-05 | `remote/ar.com.consignatarias/cattle-market` | 2026-11-02T163656394618 -> 2026-11-05T115522308093 | 1 changed | quiet |
| 2026-11-05 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-05T010657399743 -> 2026-11-05T115520943533 | 1 changed | quiet |
| 2026-11-05 | `remote/io.theagentforge/forge` | 2026-10-29T133044727038 -> 2026-11-05T115520374501 | 4 changed | quiet |
| 2026-11-05 | `remote/com.bookresorts/hotel-booking` | 2026-10-17T055923605841 -> 2026-11-05T115518474402 | 3 changed (every tool) | quiet |
| 2026-11-05 | `remote/io.github.kwizzlesurp10-ctrl/x402-mcp` | 2026-10-18T190017509313 -> 2026-11-05T115516324144 | 3 changed | review |
| 2026-11-05 | `remote/fi.akkilahdot/travel-search` | 2026-11-05T010657948288 -> 2026-11-05T115515101780 | 1 changed | quiet |
| 2026-11-05 | `remote/com.vedutum/vedutum` | 2026-11-04T200820456580 -> 2026-11-05T115512650460 | 1 changed | quiet |
| 2026-11-05 | `remote/com.ticketfairy/ticket-fairy-public-events` | 2026-11-04T005905173093 -> 2026-11-05T115506723251 | 1 changed | quiet |
| 2026-11-05 | `remote/cn.tandiu/data` | 2026-10-29T133532985483 -> 2026-11-05T115506254268 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.whisper-sec/whisper` | 2026-09-28T142609656348 -> 2026-11-05T115505604251 | 24 added | quiet |
| 2026-11-05 | `remote/com.rightshold/rightshold` | 2026-11-01T135456842923 -> 2026-11-05T115456109987 | 9 changed | quiet |
| 2026-11-05 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-05T010657997506 -> 2026-11-05T115456228443 | 26 added | review |
| 2026-11-05 | `remote/io.github.seasonsagents-art/webaz` | 2026-11-05T010656426119 -> 2026-11-05T115452124081 | 1 changed | quiet |
| 2026-11-05 | `remote/com.privacypolicyurl/privacy-policy-url` | 2026-10-26T133707238154 -> 2026-11-05T115452794339 | 1 changed, 1 added | review |
| 2026-11-05 | `remote/org.thorchain.swap/thorchain-swap` | 2026-10-21T122011926141 -> 2026-11-05T115450425306 | 15 changed, 1 added, 111 removed (every tool) | quiet |
| 2026-11-05 | `remote/com.supercatch/supercatch` | 2026-11-03T195543219207 -> 2026-11-05T115447567565 | 2 changed, 31 added | quiet |
| 2026-11-05 | `remote/tech.viewprinter/viewprinter` | 2026-10-28T133030788240 -> 2026-11-05T115444151966 | 17 changed | quiet |
| 2026-11-05 | `remote/ai.usedby/usedby` | 2026-11-04T150814049836 -> 2026-11-05T115441940901 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-05T010656669208 -> 2026-11-05T115442364269 | 5 changed | quiet |
| 2026-11-05 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-11-04T200746540697 -> 2026-11-05T115440624726 | 1 changed, 4 added | quiet |
| 2026-11-05 | `remote/cz.iustoria/pruvodci` | 2026-10-06T110304733858 -> 2026-11-05T115440749992 | 5 changed, 4 added | quiet |
| 2026-11-05 | `remote/se.sistaminuten/travel-search` | 2026-11-05T010741886993 -> 2026-11-05T115431916747 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-05T010649654641 -> 2026-11-05T115432598184 | 1 changed | quiet |
| 2026-11-05 | `remote/io.github.cyanheads/un-comtrade-mcp-server` | 2026-11-03T144901114782 -> 2026-11-05T115428952591 | 9 changed (every tool) | quiet |
| 2026-11-05 | `remote/co.scorekeeper/scorekeeper` | 2026-11-02T163437774402 -> 2026-11-05T115430451031 | 1 changed | quiet |
| 2026-11-05 | `remote/de.overfit/overfit` | 2026-11-03T144954238480 -> 2026-11-05T115424151619 | 2 changed | quiet |
| 2026-11-05 | `remote/io.github.vmalyshev1/vat-support` | 2026-09-23T163008842842 -> 2026-11-05T115421467540 | 2 added | quiet |
| 2026-11-05 | `remote/com.menloinsurance/mcp` | 2026-11-05T010740618615 -> 2026-11-05T115419183959 | 3 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 48124 substantive, 29124 that changed only numbers (a catalogue counter ticking, a date), 837 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 43267 | 15879 | 27388 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1485 | 1485 | 0 | 0 |
| `caseyjhand.com` | 354 | 354 | 0 | 0 |
| `sistaminuten.se` | 197 | 6 | 0 | 191 |
| `afbudsrejser.dk` | 196 | 6 | 0 | 190 |
| `akkilahdot.fi` | 196 | 6 | 0 | 190 |
| `restplass.no` | 196 | 6 | 0 | 190 |
| `socialloop.ai` | 189 | 189 | 0 | 0 |
| `remoshift.com` | 165 | 14 | 151 | 0 |
| `openkrill.app` | 153 | 153 | 0 | 0 |
| `revmesh2074.workers.dev` | 153 | 135 | 18 | 0 |
| 7655 other operators | 29193 | 27550 | 1567 | 76 |
