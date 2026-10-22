# MCP server tool changes

Last change observed 2026-10-22T05:26:46+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 11049 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 26489 hosted endpoints (read daily, and every four hours while they keep changing).

40402 changes to a tool definition: 1694 npm releases (1448 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 38708 readings of hosted servers that found their tools changed; 2341 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-22 | `remote/shop.grokzilla/micro-pay.1` | 2026-10-21T122238019343 -> 2026-10-22T052647123824 | 5 added | review |
| 2026-10-22 | `remote/dev.primitive/email` | 2026-10-21T234239967841 -> 2026-10-22T052646146452 | 14 changed (every tool) | quiet |
| 2026-10-22 | `remote/studio.gradients/mcp` | 2026-10-21T234237666374 -> 2026-10-22T052645443837 | 1 changed | quiet |
| 2026-10-22 | `remote/fi.akkilahdot/travel-search` | 2026-10-21T234235343105 -> 2026-10-22T052644979284 | 1 changed | quiet |
| 2026-10-22 | `remote/us.srv.vehcdj664efetfrsolne5umanq/quoteproof-mcp` | 2026-10-21T202513365983 -> 2026-10-22T052644692136 | 1 changed | quiet |
| 2026-10-22 | `remote/com.transitmcp/transit-mcp` | 2026-10-21T202510132239 -> 2026-10-22T052642890773 | 5 changed | quiet |
| 2026-10-22 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-21T122055874639 -> 2026-10-22T052641606405 | 1 changed | quiet |
| 2026-10-22 | `remote/com.swarmmemo/bulletin.1` | 2026-10-21T141125409411 -> 2026-10-22T052641590823 | 27 changed | quiet |
| 2026-10-22 | `remote/com.swarmmemo/bulletin` | 2026-10-21T141125126517 -> 2026-10-22T052640876898 | 43 changed | quiet |
| 2026-10-22 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-21T234216491631 -> 2026-10-22T052638272814 | 1 changed | quiet |
| 2026-10-22 | `remote/com.sellerprofitdoctor/free-tools` | 2026-10-21T234211238385 -> 2026-10-22T052636393300 | 14 changed | review |
| 2026-10-22 | `remote/io.reizer/deal-analysis` | 2026-10-21T121930632408 -> 2026-10-22T052635383442 | 1 changed | quiet |
| 2026-10-22 | `remote/com.remoshift/jobs` | 2026-10-21T234207614750 -> 2026-10-22T052634654888 | 1 changed | quiet |
| 2026-10-22 | `remote/com.odilelabs/odile` | 2026-10-21T202439894629 -> 2026-10-22T052633982779 | 2 added | quiet |
| 2026-10-22 | `remote/com.multicinesortega/cartelera` | 2026-10-21T202437667116 -> 2026-10-22T052633939475 | 1 changed | quiet |
| 2026-10-22 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-10-21T202434242600 -> 2026-10-22T052631313350 | 10 changed | quiet |
| 2026-10-22 | `remote/com.voicedispatcher/mcp-near-me` | 2026-10-21T121804347418 -> 2026-10-22T052629601558 | 2 changed | quiet |
| 2026-10-22 | `remote/ai.switchapp/switch` | 2026-10-21T121739006114 -> 2026-10-22T052627716930 | 6 changed | quiet |
| 2026-10-22 | `remote/com.lightbringer/connector` | 2026-10-21T121639917518 -> 2026-10-22T052625304757 | 2 changed | quiet |
| 2026-10-22 | `remote/io.github.daniel3303/equibles` | 2026-10-21T052218714575 -> 2026-10-22T052624720439 | 4 changed | quiet |
| 2026-10-22 | `remote/com.hireahelper/mcp` | 2026-10-21T234136492083 -> 2026-10-22T052623807496 | 16 removed | quiet |
| 2026-10-22 | `remote/com.gojinko.mcp/jinko` | 2026-10-20T201049001966 -> 2026-10-22T052624148915 | 1 changed | quiet |
| 2026-10-22 | `remote/club.goodleads/new-business-owner-contacts` | 2026-10-21T121615454116 -> 2026-10-22T052624294375 | 6 changed | quiet |
| 2026-10-22 | `remote/io.github.dstrausser83/db-collab-hub` | 2026-10-21T121547393271 -> 2026-10-22T052622463853 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.jamie7893/keelen` | 2026-10-21T202405573973 -> 2026-10-22T052617592744 | 3 changed, 1 added | quiet |
| 2026-10-22 | `remote/no.restplass/travel-search` | 2026-10-21T234607054532 -> 2026-10-22T052611944512 | 1 changed | quiet |
| 2026-10-22 | `remote/com.juzpost/mcp` | 2026-10-21T122144161383 -> 2026-10-22T052611203579 | 1 changed | quiet |
| 2026-10-22 | `remote/dk.afbudsrejser/travel-search` | 2026-10-21T234602276586 -> 2026-10-22T052610775589 | 1 changed | quiet |
| 2026-10-22 | `remote/net.hotelrefund/price-tracker` | 2026-10-21T052204747994 -> 2026-10-22T052611993872 | 1 changed | quiet |
| 2026-10-22 | `remote/org.thealibrary/thea` | 2026-10-21T052456595025 -> 2026-10-22T052607513458 | 2 changed | quiet |
| 2026-10-22 | `remote/io.github.tidytools/tidytools-free` | 2026-10-21T122041582550 -> 2026-10-22T052607494071 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.rccola990-cloud/x402-agent-store` | 2026-10-21T234550045563 -> 2026-10-22T052605788844 | 1 changed | review |
| 2026-10-22 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-10-21T141143621467 -> 2026-10-22T052606759841 | 2 changed | quiet |
| 2026-10-22 | `remote/shop.grokzilla/micro-pay` | 2026-10-21T121350464465 -> 2026-10-22T052607995666 | 5 added | review |
| 2026-10-22 | `remote/io.taifoon/coordination-layer.1` | 2026-10-21T234245159297 -> 2026-10-22T052604185282 | 1 changed | review |
| 2026-10-22 | `remote/se.sistaminuten/travel-search` | 2026-10-21T234244394648 -> 2026-10-22T052603386360 | 1 changed | quiet |
| 2026-10-22 | `remote/it.expatliving/data` | 2026-10-21T122348160826 -> 2026-10-22T052602621891 | 1 changed | quiet |
| 2026-10-22 | `remote/com.swarmbar/swarmbar` | 2026-10-20T201136012022 -> 2026-10-22T052604582696 | 1 added | quiet |
| 2026-10-22 | `remote/com.ferntool/ip` | 2026-10-20T052329063693 -> 2026-10-22T052602436445 | 1 added | quiet |
| 2026-10-22 | `remote/com.sfxmint/sounds` | 2026-10-20T104203320527 -> 2026-10-22T052601164417 | 1 changed | review |
| 2026-10-22 | `remote/io.github.marcoret74/semantic-geometry` | 2026-10-20T104257778611 -> 2026-10-22T052601181198 | 12 changed (every tool) | quiet |
| 2026-10-22 | `remote/io.github.cloakmaster/pact0` | 2026-10-21T234533189298 -> 2026-10-22T052559820167 | 2 changed | quiet |
| 2026-10-22 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-10-21T052247513652 -> 2026-10-22T052600221731 | 1 changed | quiet |
| 2026-10-22 | `remote/com.thefomite/fomite` | 2026-10-21T122213355269 -> 2026-10-22T052558287021 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.muaviamohammed/mizan` | 2026-10-21T234228596708 -> 2026-10-22T052559710105 | 2 changed | quiet |
| 2026-10-22 | `remote/io.github.Capital-W-Holdings/us-property-parcel-real-estate-debt` | 2026-10-21T202354037101 -> 2026-10-22T052559396399 | 1 changed | quiet |
| 2026-10-22 | `remote/com.moaibuy/moa` | 2026-10-20T201125468854 -> 2026-10-22T052556688732 | 1 changed | quiet |
| 2026-10-22 | `remote/io.orbitwan/orbitwan` | 2026-10-21T121644951293 -> 2026-10-22T052553641020 | 2 changed | quiet |
| 2026-10-22 | `remote/com.partstable/partstable` | 2026-10-21T121646556851 -> 2026-10-22T052553862571 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.medprice-ai/mcp-medprice-ai` | 2026-10-21T121629976392 -> 2026-10-22T052550871637 | 3 changed | quiet |
| 2026-10-22 | `remote/com.mosaisley/cantina` | 2026-10-21T121907824061 -> 2026-10-22T052552576912 | 1 removed | quiet |
| 2026-10-22 | `remote/dev.mcphost/mcphost` | 2026-10-20T201103295363 -> 2026-10-22T052550209751 | 1 changed | quiet |
| 2026-10-22 | `remote/com.cielstay/cielstay` | 2026-10-21T121541190075 -> 2026-10-22T052549324484 | 1 changed | quiet |
| 2026-10-22 | `remote/io.github.nanoodlecom/nanoodle-mcp` | 2026-10-21T234157060889 -> 2026-10-22T052544724830 | 1 changed | review |
| 2026-10-22 | `remote/app.everloot/knowledge` | 2026-10-21T202422987713 -> 2026-10-22T052543792358 | 1 added | quiet |
| 2026-10-22 | `remote/io.taifoon/coordination-layer` | 2026-10-21T234206469170 -> 2026-10-22T052543883808 | 1 changed | review |
| 2026-10-22 | `remote/com.convertlyft/convertlyft` | 2026-10-21T202451493379 -> 2026-10-22T052540049547 | 59 changed, 5 added (every tool) | quiet |
| 2026-10-22 | `remote/now.carejobs/healthcare-jobs` | 2026-10-20T201030931172 -> 2026-10-22T052538521070 | 1 changed | quiet |
| 2026-10-22 | `remote/dev.frontmcp.mcp/frontmcp` | 2026-10-20T232722179560 -> 2026-10-22T052540045484 | 2 changed | quiet |
| 2026-10-22 | `remote/ai.makememoneynomistakes/scoreboard` | 2026-10-21T234143239094 -> 2026-10-22T052537859776 | 2 changed | review |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 25564 substantive, 14284 that changed only numbers (a catalogue counter ticking, a date), 554 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 20653 | 7232 | 13421 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 653 | 653 | 0 | 0 |
| `caseyjhand.com` | 171 | 171 | 0 | 0 |
| `sistaminuten.se` | 132 | 4 | 0 | 128 |
| `afbudsrejser.dk` | 131 | 4 | 0 | 127 |
| `akkilahdot.fi` | 131 | 4 | 0 | 127 |
| `restplass.no` | 131 | 4 | 0 | 127 |
| `socialloop.ai` | 127 | 127 | 0 | 0 |
| `remoshift.com` | 102 | 6 | 96 | 0 |
| `fundinglandscape.com` | 100 | 65 | 35 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| 4951 other operators | 15633 | 14856 | 732 | 45 |
