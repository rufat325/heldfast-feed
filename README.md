# MCP server tool changes

Last change observed 2026-10-10T06:25:42+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 10128 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 21701 hosted endpoints (read daily, and every four hours while they keep changing).

25732 changes to a tool definition: 870 npm releases (624 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 24862 readings of hosted servers that found their tools changed; 379 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-10-10 | `remote/com.veterans-rights/bva-corpus` | 2026-10-08T135548621588 -> 2026-10-10T062543337792 | 1 changed | quiet |
| 2026-10-10 | `remote/no.restplass/travel-search` | 2026-10-09T153625133351 -> 2026-10-10T062543081722 | 1 changed | quiet |
| 2026-10-10 | `remote/dk.afbudsrejser/travel-search` | 2026-10-09T153621654449 -> 2026-10-10T062542333478 | 1 changed | quiet |
| 2026-10-10 | `remote/io.github.VoiceScapee/voicescape` | 2026-10-09T153619278994 -> 2026-10-10T062540697633 | 1 changed | quiet |
| 2026-10-10 | `remote/ai.trydock/dock` | 2026-10-09T153617778156 -> 2026-10-10T062539390496 | 35 changed | quiet |
| 2026-10-10 | `remote/dev.pages.smithtalks/smithtalks` | 2026-10-08T213434585977 -> 2026-10-10T062538666875 | 1 changed | quiet |
| 2026-10-10 | `remote/ua.com.quintadb/mcp` | 2026-10-09T153614306600 -> 2026-10-10T062537403071 | 8 changed, 1 added | quiet |
| 2026-10-10 | `remote/io.github.Fizzl13/presign-guard` | 2026-10-09T153611222851 -> 2026-10-10T062535423262 | 3 changed | review |
| 2026-10-10 | `remote/com.qumge/skills` | 2026-10-09T153611973861 -> 2026-10-10T062535289902 | 14 changed | quiet |
| 2026-10-10 | `remote/ai.thebotique.www/sigil` | 2026-10-08T064248933944 -> 2026-10-10T062534611885 | 8 changed | quiet |
| 2026-10-10 | `remote/fr.projet-ariane/ariane-orientation` | 2026-10-09T153626427136 -> 2026-10-10T062534539315 | 1 changed | quiet |
| 2026-10-10 | `remote/ch.kulalabs.pazair/pazair` | 2026-10-09T153611537853 -> 2026-10-10T062534811672 | 1 changed | quiet |
| 2026-10-10 | `remote/app.performix/performix-site` | 2026-10-08T135240398493 -> 2026-10-10T062534377017 | 2 removed | quiet |
| 2026-10-10 | `remote/com.ikeytz/website` | 2026-10-08T135516013721 -> 2026-10-10T062534161949 | 8 changed | quiet |
| 2026-10-10 | `remote/co.civai.nova/research-agent` | 2026-10-08T064213867257 -> 2026-10-10T062532806089 | 2 added | quiet |
| 2026-10-10 | `remote/co.civai.nova/google-sheets-agent` | 2026-10-08T064213754599 -> 2026-10-10T062532610255 | 2 added | quiet |
| 2026-10-10 | `remote/io.github.smarterweather/weather` | 2026-10-09T064802832691 -> 2026-10-10T062532379441 | 5 changed | quiet |
| 2026-10-10 | `remote/io.github.yzlee/opcmenu` | 2026-10-08T135048646971 -> 2026-10-10T062534402334 | 1 changed | quiet |
| 2026-10-10 | `remote/io.github.CodeWever/wever-labs-products` | 2026-10-09T153624138061 -> 2026-10-10T062535742921 | 4 added | quiet |
| 2026-10-10 | `remote/fi.akkilahdot/travel-search` | 2026-10-09T153622675986 -> 2026-10-10T062531983840 | 1 changed | quiet |
| 2026-10-10 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-10-08T213436903042 -> 2026-10-10T062531903064 | 2 changed | quiet |
| 2026-10-10 | `remote/se.sistaminuten/travel-search` | 2026-10-09T153643636368 -> 2026-10-10T062530651966 | 1 changed | quiet |
| 2026-10-10 | `remote/io.github.eamwhite1/xrpl-referee` | 2026-10-09T064746704129 -> 2026-10-10T062531268548 | 23 changed | quiet |
| 2026-10-10 | `remote/ai.ohmyfin/banking-intelligence` | 2026-10-08T135045589302 -> 2026-10-10T062531830124 | 1 changed | quiet |
| 2026-10-10 | `remote/so.darwin/darwin` | 2026-10-08T213402734714 -> 2026-10-10T062530315889 | 1 changed | quiet |
| 2026-10-10 | `remote/ru.vedarai/mcp` | 2026-10-09T064812927624 -> 2026-10-10T062530781192 | 1 changed | quiet |
| 2026-10-10 | `remote/io.github.tjcgraham-rgb/gaip-broker` | 2026-10-08T213559377841 -> 2026-10-10T062533070270 | 1 changed | quiet |
| 2026-10-10 | `remote/com.vermarco/marketplace` | 2026-10-08T064240998030 -> 2026-10-10T062529380863 | 4 changed, 12 added | quiet |
| 2026-10-10 | `remote/ai.verticalmarketplace/vertical-marketplace` | 2026-10-08T135436639363 -> 2026-10-10T062529626460 | 4 changed, 12 added | quiet |
| 2026-10-10 | `remote/ai.certscore/mcp-light` | 2026-10-08T064202157151 -> 2026-10-10T062529537410 | 4 changed (every tool) | quiet |
| 2026-10-10 | `remote/com.tickerinside/tickerinside-mcp` | 2026-10-09T153617827865 -> 2026-10-10T062527530641 | 3 changed | quiet |
| 2026-10-10 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-10-09T153619137833 -> 2026-10-10T062528635484 | 1 changed | quiet |
| 2026-10-10 | `remote/io.github.Jaywestphilly/stock-bloc` | 2026-10-08T213425999232 -> 2026-10-10T062526887577 | 1 removed | quiet |
| 2026-10-10 | `remote/com.thefomite/fomite` | 2026-10-09T064742654734 -> 2026-10-10T062527630266 | 1 changed | quiet |
| 2026-10-10 | `remote/com.swarmmemo/bulletin` | 2026-10-09T064810999641 -> 2026-10-10T062528132730 | 80 changed (every tool) | quiet |
| 2026-10-10 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-10-09T153615804098 -> 2026-10-10T062526360247 | 1 changed | quiet |
| 2026-10-10 | `remote/io.github.SidneyBissoli/senado-br-mcp-cloudflare` | 2026-10-08T213524718354 -> 2026-10-10T062526106548 | 2 changed | quiet |
| 2026-10-10 | `remote/io.github.HelloSafe/travel-insurance` | 2026-10-09T153557967289 -> 2026-10-10T062527215799 | 1 changed | quiet |
| 2026-10-10 | `remote/com.idevice/wearables` | 2026-10-08T213349272670 -> 2026-10-10T062526280101 | 4 added | quiet |
| 2026-10-10 | `remote/ru.quintadb/mcp` | 2026-10-09T153630770758 -> 2026-10-10T062528130871 | 8 changed, 1 added | quiet |
| 2026-10-10 | `remote/io.github.withgrokbot/verified-catalog` | 2026-10-08T064234339691 -> 2026-10-10T062524697128 | 1 changed, 1 added | quiet |
| 2026-10-10 | `remote/io.github.deviljin17/remode` | 2026-10-08T135307136863 -> 2026-10-10T062525313789 | 2 changed | quiet |
| 2026-10-10 | `remote/io.github.HuangGoodmanAgency/edgar-and-edgarette` | 2026-10-09T153606549720 -> 2026-10-10T062525056369 | 1 changed, 1 added | quiet |
| 2026-10-10 | `remote/com.youspot/youspot` | 2026-10-09T153607614488 -> 2026-10-10T062525793948 | 1 added | quiet |
| 2026-10-10 | `remote/com.remoshift/jobs` | 2026-10-09T064805881741 -> 2026-10-10T062525450928 | 1 changed | quiet |
| 2026-10-10 | `remote/app.govauctions/govauctions` | 2026-10-08T134754484610 -> 2026-10-10T062525389553 | 3 changed, 1 added | quiet |
| 2026-10-10 | `remote/ai.satohub/onchain-agents` | 2026-10-09T064741313133 -> 2026-10-10T062526764022 | 6 changed, 1 added | quiet |
| 2026-10-10 | `remote/io.github.yschimke/compose-preview` | 2026-10-09T153612342755 -> 2026-10-10T062525157732 | 1 changed | quiet |
| 2026-10-10 | `remote/re.parcellai/parcellaire` | 2026-10-08T213507981820 -> 2026-10-10T062524759812 | 1 changed | quiet |
| 2026-10-10 | `remote/online.pageaudit/pageaudit` | 2026-10-08T135228690336 -> 2026-10-10T062524069740 | 1 changed | quiet |
| 2026-10-10 | `remote/net.myopl/pickleball-public-knowledge` | 2026-10-08T155603636493 -> 2026-10-10T062523171194 | 2 changed | quiet |
| 2026-10-10 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-10-09T153602930758 -> 2026-10-10T062523229966 | 3 changed, 2 added | review |
| 2026-10-10 | `remote/io.github.getDynamoi/dynamoi` | 2026-10-09T064750759123 -> 2026-10-10T062524798196 | 1 changed | quiet |
| 2026-10-10 | `remote/com.musedin/musedin` | 2026-10-09T153608992061 -> 2026-10-10T062523156371 | 2 changed | quiet |
| 2026-10-10 | `remote/com.multicinesortega/cartelera` | 2026-10-09T064803127284 -> 2026-10-10T062524150198 | 1 changed | quiet |
| 2026-10-10 | `remote/co.civai.nova/google-docs-agent` | 2026-10-09T064735852066 -> 2026-10-10T062522863038 | 2 added | quiet |
| 2026-10-10 | `remote/com.vinktar/mcp` | 2026-10-08T135136445647 -> 2026-10-10T062522329843 | 1 changed | quiet |
| 2026-10-10 | `remote/com.sonarconnections/sonar-connections` | 2026-10-08T213406769371 -> 2026-10-10T062521945197 | 1 changed | quiet |
| 2026-10-10 | `remote/com.mooncatcherwire/wire` | 2026-10-08T155454556636 -> 2026-10-10T062522594411 | 10 changed (every tool) | quiet |
| 2026-10-10 | `remote/com.dechonet/mcp` | 2026-10-09T064748601108 -> 2026-10-10T062522949999 | 1 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 17368 substantive, 7994 that changed only numbers (a catalogue counter ticking, a date), 370 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 13231 | 5706 | 7525 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 538 | 538 | 0 | 0 |
| `usefulapi.io` | 97 | 97 | 0 | 0 |
| `sistaminuten.se` | 89 | 2 | 0 | 87 |
| `afbudsrejser.dk` | 88 | 2 | 0 | 86 |
| `akkilahdot.fi` | 88 | 2 | 0 | 86 |
| `restplass.no` | 88 | 2 | 0 | 86 |
| `socialloop.ai` | 86 | 86 | 0 | 0 |
| `caseyjhand.com` | 77 | 77 | 0 | 0 |
| `dayze.com` | 69 | 69 | 0 | 0 |
| `fundinglandscape.com` | 63 | 36 | 27 | 0 |
| 3054 other operators | 8877 | 8410 | 442 | 25 |
