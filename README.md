# MCP server tool changes

Last change observed 2026-11-03T19:58:22+00:00. Built by `research/feed/watch.py` on the `main` branch. Watching 14260 npm servers from the official MCP registry (checked for a new release: 154 daily, the rest weekly; a new release is started in a container with no network) and 32847 hosted endpoints (read daily, and every four hours while they keep changing).

74052 changes to a tool definition: 3094 npm releases (2848 observed live, 246 from the [churn study](https://github.com/rufat325/heldfast/blob/main/docs/CHURN.md)) and 70958 readings of hosted servers that found their tools changed; 3281 where `heldfast wrap --drift graded` would refuse something. [Per operator, and by kind of change](#per-operator).

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
| 2026-11-03 | `remote/io.github.Sparkflights-com/sparkflights` | 2026-11-02T163728288853 -> 2026-11-03T195823703353 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.imokokok/insight-oracle` | 2026-11-03T145035154988 -> 2026-11-03T195825404660 | 2 added | quiet |
| 2026-11-03 | `remote/com.patchmcp/patch` | 2026-11-02T185404271267 -> 2026-11-03T195820612253 | 6 changed | quiet |
| 2026-11-03 | `remote/studio.gradients/mcp` | 2026-11-03T145018357216 -> 2026-11-03T195817232434 | 1 changed | quiet |
| 2026-11-03 | `remote/fi.akkilahdot/travel-search` | 2026-11-03T144958884251 -> 2026-11-03T195816343060 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.sudzikcoin/versum-agent-assistant` | 2026-11-03T144915766951 -> 2026-11-03T195814709939 | 3 changed | quiet |
| 2026-11-03 | `remote/com.thecharterdesk/yacht-charter` | 2026-11-03T122626126914 -> 2026-11-03T195803582120 | 1 changed | quiet |
| 2026-11-03 | `remote/com.textforagents/mcp-oauth-client-interop-conformance` | 2026-11-02T163453555982 -> 2026-11-03T195801424199 | 5 changed (every tool) | quiet |
| 2026-11-03 | `remote/xyz.t0ll/toll` | 2026-11-03T122622873122 -> 2026-11-03T195758961832 | 1 changed, 1 added | quiet |
| 2026-11-03 | `remote/app.sallim/korea-stay` | 2026-11-02T163424867825 -> 2026-11-03T195757913838 | 1 changed | quiet |
| 2026-11-03 | `remote/net.stabledomains/registrar` | 2026-11-02T163418599717 -> 2026-11-03T195756815880 | 8 changed, 1 added | quiet |
| 2026-11-03 | `remote/io.github.socialloopai/socialloop-mcp.1` | 2026-11-03T144746776196 -> 2026-11-03T195755166498 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.QDThead/signal-lab` | 2026-11-03T024248488970 -> 2026-11-03T195753390147 | 5 changed | quiet |
| 2026-11-03 | `remote/com.remoshift/jobs` | 2026-11-03T144656200681 -> 2026-11-03T195747793559 | 1 changed | quiet |
| 2026-11-03 | `remote/com.pondchat/pondchat` | 2026-11-01T135031351322 -> 2026-11-03T195743750376 | 5 changed, 1 added | quiet |
| 2026-11-03 | `remote/co.civai.nova/mcp-slack_android` | 2026-11-02T163107882970 -> 2026-11-03T195735975718 | 1 added, 17 removed | quiet |
| 2026-11-03 | `remote/co.civai.nova/mcp-saas_studio` | 2026-11-02T163107835961 -> 2026-11-03T195735984718 | 1 added, 32 removed | quiet |
| 2026-11-03 | `remote/com.sonarconnections/sonar-connections` | 2026-11-03T024227449887 -> 2026-11-03T195731566122 | 1 changed | quiet |
| 2026-11-03 | `remote/com.vendooly/vendooly` | 2026-11-02T162956591428 -> 2026-11-03T195726623792 | 5 added | quiet |
| 2026-11-03 | `remote/ai.switchapp/switch` | 2026-11-03T144420059213 -> 2026-11-03T195723859108 | 4 changed | quiet |
| 2026-11-03 | `remote/org.openindianalaw/indiana-code` | 2026-11-03T144333022582 -> 2026-11-03T195720677345 | 1 added | quiet |
| 2026-11-03 | `remote/com.ortexo/mcp` | 2026-11-03T122555044680 -> 2026-11-03T195721042251 | 2 changed | quiet |
| 2026-11-03 | `remote/com.getfairquery/agent-trust-mcp` | 2026-11-03T122549104116 -> 2026-11-03T195713062506 | 3 changed | quiet |
| 2026-11-03 | `remote/com.getfairquery/company-jobs-feed-mcp` | 2026-11-03T122548827513 -> 2026-11-03T195712806733 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.daniel3303/equibles` | 2026-11-03T122547330263 -> 2026-11-03T195712675851 | 2 changed | quiet |
| 2026-11-03 | `remote/trade.coil/stock-market-scanner.1` | 2026-11-03T024209399666 -> 2026-11-03T195708892847 | 32 changed | quiet |
| 2026-11-03 | `remote/io.taifoon/coordination-layer.1` | 2026-11-03T145013591863 -> 2026-11-03T195708203808 | 1 changed | review |
| 2026-11-03 | `remote/ai.startuphub/startuphub` | 2026-11-03T145009110035 -> 2026-11-03T195707903179 | 1 added | review |
| 2026-11-03 | `remote/se.sistaminuten/travel-search` | 2026-11-03T145005457655 -> 2026-11-03T195707214865 | 1 changed | quiet |
| 2026-11-03 | `remote/pro.aicut/aicut` | 2026-11-03T144107321633 -> 2026-11-03T195705043593 | 28 changed | quiet |
| 2026-11-03 | `remote/io.github.afrotools/afrotools` | 2026-11-03T122538852683 -> 2026-11-03T195705897781 | 3 changed | quiet |
| 2026-11-03 | `remote/io.github.JcJamet/ia-qa-toolbox` | 2026-11-03T122703733460 -> 2026-11-03T195704121922 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.JcJamet/ia-qa-eval` | 2026-11-03T122703635005 -> 2026-11-03T195704225847 | 1 changed | quiet |
| 2026-11-03 | `remote/com.coveragecat/insurance` | 2026-11-02T065457076436 -> 2026-11-03T195701745402 | 2 added | quiet |
| 2026-11-03 | `remote/io.github.si-imtiaz/leadquasar` | 2026-11-03T144028029755 -> 2026-11-03T195702637390 | 2 changed | quiet |
| 2026-11-03 | `remote/io.github.nimitt-IN/india-cyber-regulations` | 2026-11-02T163402980358 -> 2026-11-03T195701042661 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.obrientt/landfiller` | 2026-11-03T024159718336 -> 2026-11-03T195659131083 | 1 changed | quiet |
| 2026-11-03 | `remote/com.anchorterminal/anchor-terminal` | 2026-11-03T122659446355 -> 2026-11-03T195659630979 | 3 added | quiet |
| 2026-11-03 | `remote/br.com.wikijuridica/acervo-juridico` | 2026-11-02T065454348370 -> 2026-11-03T195658538747 | 3 removed | quiet |
| 2026-11-03 | `remote/com.kitchengradeapp/kitchengrade` | 2026-11-03T144013103318 -> 2026-11-03T195657626337 | 1 changed | quiet |
| 2026-11-03 | `remote/io.github.marcoret74/semantic-geometry` | 2026-11-03T144849758279 -> 2026-11-03T195656161429 | 3 added | quiet |
| 2026-11-03 | `remote/io.github.soyeladice-svg/bursia-utils` | 2026-11-02T163310754414 -> 2026-11-03T195653210274 | 2 changed (every tool) | quiet |
| 2026-11-03 | `remote/com.tubesaku/creator-insights` | 2026-11-02T185418715862 -> 2026-11-03T195652869678 | 2 changed | quiet |
| 2026-11-03 | `remote/ca.homecalc/calculators` | 2026-11-03T143929470300 -> 2026-11-03T195650738723 | 22 added | review |
| 2026-11-03 | `remote/com.swishrjobs/swishrjobs` | 2026-11-02T185414227556 -> 2026-11-03T195643495764 | 3 changed, 61 added | quiet |
| 2026-11-03 | `remote/com.idosgames/platform` | 2026-11-01T135459524503 -> 2026-11-03T195641138418 | 2 changed | quiet |
| 2026-11-03 | `remote/app.vercel.fork-for-agents/fork` | 2026-11-03T143721283108 -> 2026-11-03T195641137674 | 1 changed | quiet |
| 2026-11-03 | `remote/ai.satohub/onchain-agents` | 2026-11-01T065447870064 -> 2026-11-03T195637420738 | 1 changed | quiet |
| 2026-11-03 | `remote/com.crm-connector/crm-connector` | 2026-11-03T122633414898 -> 2026-11-03T195630645910 | 2 changed | quiet |
| 2026-11-03 | `remote/com.photoprintagent/mcp-narrow` | 2026-11-02T162944331901 -> 2026-11-03T195630565388 | 8 changed | quiet |
| 2026-11-03 | `remote/pro.dsgvo/dsgvo-pro` | 2026-11-03T143630511286 -> 2026-11-03T195627602480 | 1 changed | quiet |
| 2026-11-03 | `remote/com.organiqgeo/organiq` | 2026-11-03T024237332254 -> 2026-11-03T195629548778 | 1 changed, 1 added | quiet |
| 2026-11-03 | `remote/pl.oleba/remonty` | 2026-11-03T144506857847 -> 2026-11-03T195627979630 | 1 changed | quiet |
| 2026-11-03 | `remote/co.civai.nova/mcp-bgpt-tweet-downloader` | 2026-11-02T162856339279 -> 2026-11-03T195624485950 | 1 added, 1 removed | quiet |
| 2026-11-03 | `remote/co.civai.nova/mcp-bgpt-jiji-recon` | 2026-11-02T162856400202 -> 2026-11-03T195624244849 | 1 added, 23 removed | quiet |
| 2026-11-03 | `remote/co.civai.nova/mcp-bgpt-clannit` | 2026-11-02T162856148220 -> 2026-11-03T195624167519 | 1 added, 11 removed | quiet |
| 2026-11-03 | `remote/co.civai.nova/mcp-bgpt-chowdeck` | 2026-11-02T162856143189 -> 2026-11-03T195623765436 | 1 added, 24 removed | quiet |
| 2026-11-03 | `remote/co.civai.nova/mcp-bgpt-cardpeer` | 2026-11-02T162855634776 -> 2026-11-03T195623686343 | 1 added, 6 removed | quiet |
| 2026-11-03 | `remote/com.nearfine/books` | 2026-11-02T162844028631 -> 2026-11-03T195622240962 | 1 changed | quiet |
| 2026-11-03 | `remote/com.cymetica/event-trader-mcp` | 2026-11-03T143608199951 -> 2026-11-03T195622641610 | 1 changed, 1 added | quiet |

## Per operator

A few operators account for most of the changes, and many changes move only a number or an order: 46081 substantive, 27163 that changed only numbers (a catalogue counter ticking, a date), 808 that only reordered a list. A number can still matter -- a price is one -- so this sorts the count, it excuses nothing. Grouped by hosted servers by registrable domain under the Public Suffix List (2026-09-24_13-26-36_UTC), private section included; npm servers by package. Approximate: it merges different customers of one host the list does not name, and splits an operator who uses several domains. Every event: [stats.json](stats.json).

| operator | changes | substantive | numbers only | reordered only |
|---|---|---|---|---|
| `pipeworx.io` | 41415 | 15875 | 25540 | 0 |
| `nolimit-observatory.workers.dev` | 2341 | 2341 | 0 | 0 |
| `a2awire.com` | 1245 | 1245 | 0 | 0 |
| `caseyjhand.com` | 329 | 329 | 0 | 0 |
| `sistaminuten.se` | 191 | 6 | 0 | 185 |
| `afbudsrejser.dk` | 190 | 6 | 0 | 184 |
| `akkilahdot.fi` | 190 | 6 | 0 | 184 |
| `restplass.no` | 190 | 6 | 0 | 184 |
| `socialloop.ai` | 183 | 183 | 0 | 0 |
| `remoshift.com` | 160 | 12 | 148 | 0 |
| `fundinglandscape.com` | 146 | 89 | 57 | 0 |
| `revmesh2074.workers.dev` | 146 | 128 | 18 | 0 |
| 7303 other operators | 27326 | 25855 | 1400 | 71 |
