# MCP server tool changes

Last change observed 2026-11-16T07:23:10+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 15666 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 36287 hosted endpoints (read daily, and every four hours while they keep changing).

104394 changes to a tool definition: 4274 npm releases (4028 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 100120 readings of hosted servers that found their tools changed; 4173 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-16 | `remote/io.github.giorgio44/gateonai-mcp` | 2026-11-15T071624124802 -> 2026-11-16T072312837985 | 2 changed | quiet |
| 2026-11-16 | `remote/io.suverse.versum/catalog` | 2026-11-15T212310533607 -> 2026-11-16T072310260249 | 3 changed | quiet |
| 2026-11-16 | `remote/app.floot.via-router/via-gateway` | 2026-11-15T212301247880 -> 2026-11-16T072309391352 | 8 changed (every tool) | quiet |
| 2026-11-16 | `remote/io.github.TokyoFuturo/tokyo-futuro` | 2026-11-15T002321639616 -> 2026-11-16T072306712183 | 1 added | quiet |
| 2026-11-16 | `remote/io.github.t0ll-xyz/toll` | 2026-11-15T115529951007 -> 2026-11-16T072301797717 | 1 changed | quiet |
| 2026-11-16 | `remote/io.github.PascalSun/talk2geo` | 2026-11-15T212258137297 -> 2026-11-16T072303665846 | 20 added | quiet |
| 2026-11-16 | `remote/app.sunsetstrip/gta6` | 2026-11-14T135916810754 -> 2026-11-16T072300885086 | 4 added | quiet |
| 2026-11-16 | `remote/io.github.ulasarslan6262-ui/speedbot` | 2026-11-15T142440399245 -> 2026-11-16T072257903238 | 2 changed | quiet |
| 2026-11-16 | `remote/wiki.rust/rust-wiki` | 2026-11-15T071612014009 -> 2026-11-16T072252087514 | 100 changed, 77 added (every tool) | review |
| 2026-11-16 | `remote/site.chatgpt.bootyplease.saas-bundlecheck/sideeye` | 2026-11-15T002316111488 -> 2026-11-16T072254782144 | 1 changed | quiet |
| 2026-11-16 | `remote/app.pitbi/pitbi` | 2026-11-15T212247066510 -> 2026-11-16T072251444388 | 1 changed | quiet |
| 2026-11-16 | `remote/com.midasiteurope/civil-nx` | 2026-11-15T212239754131 -> 2026-11-16T072246885486 | 2 changed | quiet |
| 2026-11-16 | `remote/io.github.sudomichael/mcpserverlist-mcp` | 2026-11-15T212239171035 -> 2026-11-16T072245636660 | 1 changed | quiet |
| 2026-11-16 | `remote/com.tkawen/intelligence-gateway` | 2026-11-15T071603618241 -> 2026-11-16T072244666631 | 41 removed | quiet |
| 2026-11-16 | `remote/com.squirrelscan/squirrelscan` | 2026-11-15T212233437376 -> 2026-11-16T072245362942 | 3 changed | quiet |
| 2026-11-16 | `remote/studio.gradients/mcp` | 2026-11-15T212155566377 -> 2026-11-16T072239188337 | 1 changed | quiet |
| 2026-11-16 | `remote/io.github.Steven3265/homechecker-guides` | 2026-11-15T114840856515 -> 2026-11-16T072239189920 | 1 changed | quiet |
| 2026-11-16 | `remote/com.spocont/ifrCoworker` | 2026-11-15T141846292369 -> 2026-11-16T072240947947 | 4 changed | review |
| 2026-11-16 | `remote/com.jojapi/product-barcode-api` | 2026-11-15T114850702604 -> 2026-11-16T072239899423 | 1 changed | quiet |
| 2026-11-16 | `remote/io.github.iyuyoung/wordsearchclub` | 2026-11-15T071612094856 -> 2026-11-16T072238154213 | 1 changed | quiet |
| 2026-11-16 | `remote/fi.akkilahdot/travel-search` | 2026-11-15T212153681635 -> 2026-11-16T072238438666 | 1 changed | quiet |
| 2026-11-16 | `remote/ai.cloudworldmodel/cloud-world-model` | 2026-11-15T212153998547 -> 2026-11-16T072238450875 | 1 changed | quiet |
| 2026-11-16 | `remote/io.github.CodeWever/wever-labs-products` | 2026-11-15T071616148510 -> 2026-11-16T072241101082 | 24 added | quiet |
| 2026-11-16 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-15T212151556755 -> 2026-11-16T072236844588 | 3 changed | quiet |
| 2026-11-16 | `remote/io.github.JustJuice55/telegram-catalog` | 2026-11-15T212148175559 -> 2026-11-16T072234513560 | 1 changed | quiet |
| 2026-11-16 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-15T212148746235 -> 2026-11-16T072235485842 | 2 changed | quiet |
| 2026-11-16 | `remote/io.github.ronrey/federation` | 2026-11-15T002258943796 -> 2026-11-16T072235338594 | 1 changed | quiet |
| 2026-11-16 | `remote/com.complyonsite/tools` | 2026-11-15T212208561502 -> 2026-11-16T072235475540 | 8 changed | quiet |
| 2026-11-16 | `remote/com.comos-federation/gateway` | 2026-11-15T002258677536 -> 2026-11-16T072235471906 | 1 changed | quiet |
| 2026-11-16 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-15T212142468491 -> 2026-11-16T072231700907 | 1 changed | quiet |
| 2026-11-16 | `remote/ai.shorti/shorti` | 2026-11-15T115343533898 -> 2026-11-16T072231954159 | 3 changed | quiet |
| 2026-11-16 | `remote/com.serviche/sergio` | 2026-11-14T183345515065 -> 2026-11-16T072232424803 | 8 changed, 8 removed | quiet |
| 2026-11-16 | `remote/com.seqbench/workbench` | 2026-11-15T142340493368 -> 2026-11-16T072228891048 | 2 changed, 1 added | quiet |
| 2026-11-16 | `remote/co.ainumbers/tools` | 2026-11-15T212201741909 -> 2026-11-16T072232700639 | 2 changed | quiet |
| 2026-11-16 | `remote/app.marselia/marselia` | 2026-11-15T141703351802 -> 2026-11-16T072232036404 | 2 changed | quiet |
| 2026-11-16 | `remote/com.remoshift/jobs` | 2026-11-15T212136379189 -> 2026-11-16T072227602785 | 1 changed | quiet |
| 2026-11-16 | `remote/com.radar-cnpj/radar-cnpj` | 2026-11-15T115253052412 -> 2026-11-16T072227874687 | 5 changed | quiet |
| 2026-11-16 | `remote/com.multicinesortega/cartelera` | 2026-11-15T212131341165 -> 2026-11-16T072222924633 | 1 changed | quiet |
| 2026-11-16 | `remote/uk.minia2a/minia2a-mcp-remote` | 2026-11-15T212129832593 -> 2026-11-16T072221038872 | 2 changed, 21 removed | quiet |
| 2026-11-16 | `remote/co.yougame/yougame` | 2026-11-15T155639996127 -> 2026-11-16T072220040899 | 3 changed, 3 added | quiet |
| 2026-11-16 | `remote/io.github.liad142/yedapo` | 2026-11-15T071545448492 -> 2026-11-16T072219656698 | 2 changed (every tool) | quiet |
| 2026-11-16 | `remote/io.github.jdhart81/smartscale` | 2026-11-15T115034155093 -> 2026-11-16T072219304893 | 2 changed | quiet |
| 2026-11-16 | `remote/io.github.jdhart81/ghg-ledger` | 2026-11-15T071551222597 -> 2026-11-16T072219250139 | 4 changed | quiet |
| 2026-11-16 | `remote/domains.unique/mcp-server` | 2026-11-15T071550516344 -> 2026-11-16T072219195788 | 51 changed (every tool) | quiet |
| 2026-11-16 | `remote/com.vitef/vitef` | 2026-11-14T135610850854 -> 2026-11-16T072220306292 | 1 changed | quiet |
| 2026-11-16 | `remote/com.stocklens/stocklens` | 2026-11-14T183320361034 -> 2026-11-16T072218621297 | 2 changed | quiet |
| 2026-11-16 | `remote/no.restplass/travel-search` | 2026-11-15T212159179995 -> 2026-11-16T072218726942 | 1 changed | quiet |
| 2026-11-16 | `remote/com.juzpost/mcp` | 2026-11-14T140147590850 -> 2026-11-16T072217868356 | 4 changed | quiet |
| 2026-11-16 | `remote/market.populardemand/popular-demand` | 2026-11-15T002309078708 -> 2026-11-16T072218227091 | 2 changed | quiet |
| 2026-11-16 | `remote/ai.ohmyfin/sanctions` | 2026-11-15T114918679624 -> 2026-11-16T072217833957 | 1 changed | quiet |
| 2026-11-16 | `remote/io.github.magichourhq/magic-hour` | 2026-11-14T010634794856 -> 2026-11-16T072216182146 | 2 changed | quiet |
| 2026-11-16 | `remote/io.github.lubobali/lubot` | 2026-11-15T071544853694 -> 2026-11-16T072215551119 | 9 changed (every tool) | quiet |
| 2026-11-16 | `remote/dk.afbudsrejser/travel-search` | 2026-11-15T212156524459 -> 2026-11-16T072216539048 | 1 changed | quiet |
| 2026-11-16 | `remote/org.glolaw/glo-law` | 2026-11-14T183315467697 -> 2026-11-16T072215216580 | 1 changed | quiet |
| 2026-11-16 | `remote/io.github.daniel3303/equibles` | 2026-11-15T212120071941 -> 2026-11-16T072214800419 | 5 changed | quiet |
| 2026-11-16 | `remote/io.github.industrial-platform-ai/research-brief` | 2026-11-15T114701676979 -> 2026-11-16T072212608172 | 1 changed | quiet |
| 2026-11-16 | `remote/com.avnester.mcp/property-intelligence` | 2026-11-14T114945981653 -> 2026-11-16T072215374647 | 5 changed | quiet |
| 2026-11-16 | `remote/com.synoptic/synoptic` | 2026-11-15T114651666671 -> 2026-11-16T072212222485 | 1 changed | quiet |
| 2026-11-16 | `remote/fun.make/makefun` | 2026-11-15T212114964607 -> 2026-11-16T072211045347 | 20 changed | quiet |
| 2026-11-16 | `remote/co.getclippy/clippy` | 2026-11-15T212115560161 -> 2026-11-16T072212063307 | 5 changed | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 62631 substantive, 40721 that changed only numbers (a catalogue counter ticking, a date), 1042 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 56231 | 17878 | 38353 | 0 |
| `a2awire.com` | 2707 | 2707 | 0 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `caseyjhand.com` | 431 | 431 | 0 | 0 |
| `civai.co` | 364 | 364 | 0 | 0 |
| `revmesh2074.workers.dev` | 269 | 236 | 33 | 0 |
| `modevc.com` | 258 | 258 | 0 | 0 |
| `sistaminuten.se` | 243 | 6 | 0 | 237 |
| `afbudsrejser.dk` | 242 | 6 | 0 | 236 |
| `akkilahdot.fi` | 242 | 6 | 0 | 236 |
| `restplass.no` | 242 | 6 | 0 | 236 |
| `socialloop.ai` | 234 | 234 | 0 | 0 |
| 9480 other operators | 40590 | 38158 | 2335 | 97 |
