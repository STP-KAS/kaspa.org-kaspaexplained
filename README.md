# kaspa.org / kaspaexplained.com

**Independent comparison of two Kaspa websites.**  
Not official. Not investment advice. Not a protocol audit.

| Field | Value |
| --- | --- |
| Report date | 16 September 2026 |
| Compared URLs | https://kaspa.org/ · https://kaspaexplained.com/ |
| GitHub repo | [STP-KAS/kaspa.org-kaspaexplained](https://github.com/STP-KAS/kaspa.org-kaspaexplained) |
| Method | Primary-page reads, GitHub source checks, live REST API snapshot, third-party market data, related-URL mapping |

GitHub repository names cannot contain `/`. This report is published as `kaspa.org-kaspaexplained`.

---

## Verdict

These sites do different jobs. Treating them as substitutes is a category error.

- **[kaspa.org](https://kaspa.org/)** is the public project homepage: brand, narrative, wallets, buy routes, lore, and a developer doorway. It is the URL people expect when they search “Kaspa official site.” It is **not** a complete or uniformly current record of protocol status. On 16 September 2026, `/lore` still described Toccata as the *next* hardfork, while `/build` correctly said Toccata had been live on mainnet since 30 June 2026.
- **[kaspaexplained.com](https://kaspaexplained.com/)** is an independent explainer: mechanism, status labels, source ranking, and interactive demos. It is **not** official, not a wallet or exchange, and not a substitute for `docs.kaspa.org` or `github.com/kaspanet`. On the same date it correctly treated Toccata as live and DAGKnight as research.

**If the question is “is feature X live?”** neither homepage is the settlement source. Settlement is: a Rusty Kaspa release tag, a merged KIP status, and a mainnet DAA score past the activation threshold. Both sites should be checked against those.

**Practical split**

| Job | Better first stop | Why |
| --- | --- | --- |
| Brand, wallets, buy, vision copy | kaspa.org | That is the public face |
| “Is this live, testnet, roadmap, or research?” | kaspaexplained.com/status, then GitHub | Status is labeled and dated |
| How GHOSTDAG / UTXO / mass actually work | kaspaexplained.com/what-is-kaspa | Demos + code links |
| Integrate a node, SDK, or covenant | [docs.kaspa.org](https://docs.kaspa.org/) + [rusty-kaspa](https://github.com/kaspanet/rusty-kaspa) | Builder docs, not marketing |
| Tokenomics numbers | wiki + REST API, not the old FAQ | See recency section |
| Price | CoinGecko / CoinMarketCap | Neither site is a market data feed |

---

## What I did, and why

The comparison is of **two websites**, not of Kaspa as an investment. I treated marketing copy, independent explainers, GitHub, and live chain data as different evidence classes.

1. **Read the live sites.** Fetched homepages and inner pages on 16 September 2026: kaspa.org `/`, `/lore`, `/build`; kaspaexplained.com `/`, `/status`, `/what-is-kaspa`, `/sources`, `/skeptical-case`. Why: homepage-only comparison would miss the split between kaspa.org lore and kaspa.org build, and would miss kaspaexplained’s status system.
2. **Read the source repositories.** [kaspanet/rusty-kaspa](https://github.com/kaspanet/rusty-kaspa) (reference node), [v2.0.0](https://github.com/kaspanet/rusty-kaspa/releases/tag/v2.0.0) and [v2.0.1](https://github.com/kaspanet/rusty-kaspa/releases/tag/v2.0.1) release notes, [parker2017code/kaspa-explained](https://github.com/parker2017code/kaspa-explained) README and about/editorial material. Why: protocol status is decided in code and releases, not in website prose.
3. **Took a live mainnet snapshot** from the community REST API (`api.kaspa.org`) for DAA score, supply, block reward, difficulty, tips, and hashrate. Why: a dated chain read beats quoting either site’s frozen numbers.
4. **Checked domain and hosting facts** (WHOIS, DNS, CDN). Why: official-looking clones exist; domain age and DNS are weak but useful identity signals.
5. **Pulled third-party market snapshots** (CoinGecko-derived pages, 15–16 September 2026). Why: market cap is not a protocol fact, but it is the context people mix into both sites.
6. **Mapped related URLs** in the Kaspa stack and in broader proof-of-work / consensus research. Why: these two sites sit in a larger graph; using the wrong neighbor (for example `kaspa.com`) is a common error.

**What I did not do**

- Did not run the genesis-proof notebook.
- Did not line-audit every kaspaexplained demo against rusty-kaspa.
- Did not obtain Similarweb or other paid traffic ranks.
- Did not treat social posts as settlement evidence.
- Did not review either site as a security audit of Kaspa.

---

## What each site is

### kaspa.org

**Role.** Public project site for Kaspa (ticker KAS), a proof-of-work blockDAG using GHOSTDAG. Mainnet launched 7 November 2021. The site presents fair launch (no premine, no hidden allocation), a cryptographic genesis-proof path, wallets, buy routes, lore, and a build page.

**Identity signals (public, not a legal opinion)**

| Item | Observation | Source |
| --- | --- | --- |
| Domain | kaspa.org, created 14 August 2021, expires 14 August 2029 | WHOIS (GoDaddy) |
| DNS | Cloudflare nameservers `elmo` / `ollie` | WHOIS / host.io |
| Hosting | Amazon CloudFront (AS16509) | host.io |
| Contact on old FAQ | `w@kaspa.org` | [kaspa.org/kaspa-faq](https://kaspa.org/kaspa-faq/) |
| Code org | [github.com/kaspanet](https://github.com/kaspanet) | FAQ and lore |
| Whitepaper | PHANTOM/GHOSTDAG, IACR ePrint 2018/104 | lore, FAQ |

The project describes itself as community-run, open source, no central company, no ICO. Kaspa Ecosystem Foundation ([kaspafoundation.org](https://www.kaspafoundation.org/)) is a later funding/advocacy body (domain created 2024). It is **not** the same object as kaspa.org.

**What the homepage actually argues.** “bitcoin's proof-of-work without the wait” plus a fair-launch proof. That is a positioning claim. Inclusion at 10 blocks per second is live (Crescendo, May 2025). Instant irreversibility is not what the protocol papers or the node code say. Confirmation confidence still accumulates with stacked work.

### kaspaexplained.com

**Role.** Independent static explainer, source repo [parker2017code/kaspa-explained](https://github.com/parker2017code/kaspa-explained). Hosted on Cloudflare Workers. Content CC BY 4.0; code MIT. The README states it is not an official Kaspa website and not investment advice. The about/editorial text states no official Kaspa role, no paid coverage, and that the maintainer may hold KAS.

**Identity signals**

| Item | Observation | Source |
| --- | --- | --- |
| Domain | kaspaexplained.com (CNAME in repo) | repo `CNAME` |
| Hosting | Cloudflare Workers serving generated `dist/` | README |
| Repo activity | 768 commits on `main` when checked 16 Sep 2026 | GitHub |
| GitHub traction | 0 stars, 0 forks at check time | GitHub |
| Editorial stance | Rank sources; label live / testnet / roadmap / research / wrong | `/sources`, `/status` |

**What the homepage actually argues.** Kaspa is Bitcoin-style proof of work, but parallel blocks are kept and ordered by GHOSTDAG. The front door is a collision demo, not a buy button.

---

## Side-by-side

| Dimension | kaspa.org | kaspaexplained.com |
| --- | --- | --- |
| Official? | De facto public homepage | Explicitly independent |
| Audience | Newcomers, holders, press, builders arriving cold | Readers who want mechanism and status |
| Voice | Narrative / manifesto (“real-time decentralization”) | Claim-labeled explainer |
| Primary CTA | Get started, wallet, buy | Two doors: new to crypto vs already know crypto |
| Status discipline | Mixed across pages | Central `/status` table with dates |
| Source ranking | Links papers, GitHub, Medium, X | Explicit 4-tier hierarchy; marketing pages excluded |
| Recency (16 Sep 2026) | `/build` current; `/lore` and FAQ stale | Status snapshot dated 14 Sep 2026 |
| Interactivity | Genesis-proof link; `/build` WASM examples | Collision, GHOSTDAG, mass, fee/security-budget demos |
| Conflict disclosure | Community site; buy onramp on site | Maintainer may hold KAS; no paid coverage claimed |
| Bus factor | Community site with multiple surfaces | Single public maintainer (`parker2017code`) |
| GitHub social proof | Points at kaspanet (rusty-kaspa ~846 stars) | Explainer repo 0 stars |
| Desktop note | General web | Demos are dense; some interactions are PC-first |
| Use as a citation | Weak for activation dates | Stronger for labeled status, still secondary to GitHub |

---

## Recency and accuracy audit (the load-bearing check)

This is the factual core. Protocol truth on 16 September 2026:

| Fact | Evidence |
| --- | --- |
| Crescendo (1 → 10 BPS) activated 5 May 2025, DAA 110,165,000 | rusty-kaspa README; KIP-14 line; Kaspalytics upgrade note |
| Toccata activation score set at DAA **474,165,565**, ~30 June 2026 16:15 UTC | [rusty-kaspa v2.0.0](https://github.com/kaspanet/rusty-kaspa/releases/tag/v2.0.0) |
| Recommended node at check time | rusty-kaspa **v2.0.1** (15 June 2026) |
| Live virtual DAA on 16 Sep 2026 | **541,172,304** (`GET https://api.kaspa.org/info/blockdag`) |
| Therefore Toccata is past activation | 541,172,304 ≫ 474,165,565 |
| DAGKnight | [KIP-2](https://github.com/kaspanet/kips/blob/master/kip-0002.md) still Proposed; no release activates it |

### kaspa.org — page by page

| Page | What it said on 16 Sep 2026 | Verdict |
| --- | --- | --- |
| `/` | Fair launch, genesis proof, 10 BPS framing | Current enough for a homepage |
| `/lore` | “The next hardfork is Toccata”; “A mature implementation is already up and running on TN12”; closing line “Toccata next” | **Stale.** Toccata activated ~30 June 2026. TN12 is not the activation record. |
| `/build` | “Toccata … live on mainnet since June 30, 2026.” Points at rusty-kaspa v2.0.1 | **Current.** |
| `/kaspa-faq/` | Circulating supply and block reward dated **24 July 2023** (19.8B KAS, reward 196); “latest update: Crescendo” | **Stale.** Live circulating ~27.70B KAS; reward 2.18267645 KAS/block. |

Search indexes still surface older WordPress-era kaspa.org pages that talk about 1 block per second. Those URLs are historical residue. The live Next.js lore/build split is the current problem: **two pages on the same official domain disagree about whether Toccata has shipped.**

That does not make kaspa.org a fake site. It makes it a **poor unique source for upgrade status**. kaspaexplained.com’s `/sources` page records the same lore lag (checked there 10 September 2026). I re-read `/lore` on 16 September 2026; the lag was still there.

### kaspaexplained.com — page by page

| Page | What it said | Verdict |
| --- | --- | --- |
| `/status` | Toccata live; Crescendo live; DAGKnight research; vProgs roadmap; “100 BPS” research; sources checked 14 Sep 2026 | Matches release + live DAA |
| `/what-is-kaspa` | Inclusion ≠ finality; TPS is workload-dependent; covenants live, shared mutable app state not | Matches KIPs + node docs |
| `/sources` | Code/releases settle claims; kaspa.org marketing pages excluded | Method is coherent. Exclusion is slightly too broad: `/build` *is* current. |
| `/skeptical-case` | Seven risks including fee vs subsidy gap | Relevant; numbers on that page are a **22 August 2026** snapshot, not live |

**Correction to kaspaexplained’s source rule, not to its Toccata status.** Refusing *all* kaspa.org marketing pages because lore lagged is understandable after two stale reads. It over-punishes `/build`, which had already caught up. The right rule is: cite kaspa.org only where it agrees with a release tag or a dated API read.

**kaspaexplained limitations that matter**

- Single maintainer. 768 commits is real work; 0 stars/forks means little external review on GitHub.
- Maintainer may hold KAS. Disclosed. Still a conflict.
- Some quantitative demos freeze a date (22 Aug 2026 price/fee row). The site tells you that; a reader who skips the date will quote a dead number.
- Independent ≠ infallible. Status tables are a **secondary index** over GitHub and the API.

---

## Live network snapshot (16 September 2026)

Read from `api.kaspa.org` during this report. Re-fetch before quoting; these are observations, not live widgets.

### `GET https://api.kaspa.org/info/blockdag`

| Field | Value |
| --- | --- |
| networkName | kaspa-mainnet |
| virtualDaaScore | 541172304 |
| tipHashes count | 12 parallel tips at read time |
| difficulty | 1.6933570772922894e+16 |
| pruningPointHash | `ca10808b973dbb29f518cdb627b9b7d4f5368037fd9d9024decf1ef3bb3abbfd` |

The API also returns `blockCount` / `headerCount` of `1393547`. kaspaexplained.com warns not to treat those fields as lifetime network totals. I follow that warning: they are **not** used here as “total blocks ever.”

### `GET https://api.kaspa.org/info/coinsupply`

Values are in **sompi** (1 KAS = 100,000,000 sompi).

| Field | Sompi | KAS |
| --- | --- | --- |
| circulatingSupply | 2770308155945537652 | **27,703,081,559.455** |
| maxSupply | 2870403560500000000 | **28,704,035,605** |

Issued fraction: about **96.5%** of the API max-supply figure. That matches the “nearly fully issued” description used in 2026 market commentary. It is **not** the 19.8B figure still sitting on kaspa.org’s FAQ.

### `GET https://api.kaspa.org/info/blockreward`

`blockreward`: **2.18267645** KAS per block.

At 10 blocks per second that is about 21.83 KAS/s of new coins, before fees. This matches kaspaexplained.com’s 14 September snapshot of the same endpoint (they reported 2.18267645 KAS/block and 27,699,582,519.57 circulating). Two days of emission later, circulating has moved by a few million KAS, which is what the schedule predicts.

### `GET https://api.kaspa.org/info/hashrate`

Raw JSON: `{"hashrate":339821.71774892026}`. The Swagger UI at `/docs` did not yield a unit string in the fetch used for this report. **Do not convert this number to PH/s or TH/s without reading the API schema.** Difficulty from `blockdag` is the less ambiguous security-work proxy in this snapshot.

### Benchmarks that are real vs slogans

| Claim | Status | Notes |
| --- | --- | --- |
| 10 proof-of-work blocks per second | Live since Crescendo (May 2025) | rusty-kaspa README |
| “Instant confirmation” / irreversible at inclusion | Oversell | Inclusion is fast; reversal risk falls with stacked work. kaspaexplained states this; kaspa.org homepage slogan does not |
| ~2,450–3,070 simple-payment TPS capacity | Model, not observed load | From mass limits × 10 BPS, as derived on kaspaexplained from rusty-kaspa mass code. Real TPS is demand + mempool |
| Observed load | Low relative to capacity | kaspaexplained cited ~0.9 TPS baseline from api.kaspa.org on 22 Aug 2026; I did not re-measure TPS for this report |
| 100 BPS / 10 ms blocks | Research / 2027 lore | Appears on kaspa.org `/lore`. No KIP + release. kaspaexplained labels it research |
| Native DeFi / vProgs production | Not shipped | vprogs repo is early development |

**Throughput vs Bitcoin, Ethereum, Solana** is not a single number. Kaspa’s distinctive measured fact is **10 PoW blocks/s with GHOSTDAG ordering**, not “faster than every L1 at every workload.” Solana slots, Ethereum L2s, and Kaspa blocks are different machines. kaspaspeed.com visualizes block-interval comparisons; treat those as pedagogy, not a benchmark suite.

---

## Market context (not a protocol fact)

Third-party aggregators, 15–16 September 2026. Prices move; re-read the source.

| Metric | Approximate reading | Source |
| --- | --- | --- |
| Price | ~$0.033 | CoinGecko-derived pages 15–16 Sep 2026 |
| Market cap | ~$0.90–0.93B | CoinGecko historical 16 Sep 2026 ~$912M |
| Rank | ~#76–#78 | TickerVS / CoinGecko mirrors |
| Circulating (listings) | ~27.7B KAS | Agrees with API order of magnitude |
| Max supply (listings) | ~28.70B KAS | CoinGecko 28,704,026,601 vs API 28,704,035,605 |
| ATH | $0.2074 on 31 July 2024 | CoinGecko |
| Drawdown from ATH | ~84% | Arithmetic from ATH vs ~$0.033 |
| 24h volume | ~$10–13M | CoinGecko 15–16 Sep |

kaspa.org does not need to be a price site. The FAQ pointing at CoinGecko is fine; the frozen 2023 supply on that same FAQ is not.

---

## Unbiased assessment

**kaspa.org strengths**

- Correct public identity for the project: domain since 2021, points at kaspanet, explorer, genesis proof.
- `/build` is a real developer doorway and, as of this check, states Toccata correctly.
- Fair-launch and genesis-proof presentation is specific, not generic “no premine” marketing.
- Wallet and buy routes belong on a homepage. An explainer should not replace them.

**kaspa.org weaknesses**

- Internal contradiction on the most important 2026 upgrade (Toccata).
- FAQ economics are years out of date.
- Homepage slogan compresses inclusion speed into “without the wait,” which readers hear as finality.
- Lore reads as a manifesto. That is allowed for a homepage. It is a bad place to copy dates from.

**kaspaexplained.com strengths**

- Status vocabulary (live / testnet / roadmap / research / wrong) is the right tool for a fast-moving PoW chain with a loud community.
- Ties claims to rusty-kaspa, KIPs, and dated API reads.
- Demos encode protocol constants (GHOSTDAG *k* table cap at 32, mass formulas, confirmation-risk curve) instead of only describing them.
- Publishes the case against itself (`/skeptical-case`): verification cost, security budget, ASIC concentration, demand.
- Correction path exists (GitHub issue template for stale claims).

**kaspaexplained.com weaknesses**

- Not official. Linking it as “the Kaspa site” would be as wrong as treating lore as an activation record.
- Single-maintainer and zero GitHub stars: high diligence, low external review.
- Source ban on kaspa.org marketing is slightly overfit (lore failed; build did not).
- Dense UI; demos are not a phone-first product.
- Holding KAS is a disclosed conflict. Precision of labeling reduces that risk; it does not delete it.

**Neither site**

- Neither is CoinGecko.
- Neither is the node.
- Neither is `docs.kaspa.org`.
- `kaspa.com` is **KaspaCom**, a community marketplace / DeFi hub, not the protocol homepage. Do not conflate it with kaspa.org.

---

## Related URLs

### Protocol and first-party

| URL | Why it belongs |
| --- | --- |
| https://kaspa.org/ | Public homepage |
| https://kaspa.org/lore | Narrative + roadmap (check dates) |
| https://kaspa.org/build | Developer doorway; Toccata stated as live |
| https://kaspa.org/kaspa-faq/ | Integration FAQ; economics stale |
| https://explorer.kaspa.org/ | Canonical explorer linked from the project |
| https://api.kaspa.org/info/blockdag | Live DAG snapshot |
| https://api.kaspa.org/info/coinsupply | Supply in sompi |
| https://api.kaspa.org/info/blockreward | Current subsidy |
| https://api.kaspa.org/docs | REST docs |
| https://docs.kaspa.org/ | Builder docs |
| https://docs.kaspa.org/toccata | Toccata developer guide |
| https://wiki.kaspa.org/ | Community wiki |
| https://wiki.kaspa.org/en/tokenomics | Emission schedule |
| https://github.com/kaspanet | Protocol org |
| https://github.com/kaspanet/rusty-kaspa | Reference node |
| https://github.com/kaspanet/rusty-kaspa/releases | Activation and upgrade record |
| https://github.com/kaspanet/kips | KIPs |
| https://github.com/kaspanet/kccs | Conventions (not consensus) |
| https://github.com/kaspanet/silverscript | Covenant compiler |
| https://github.com/kaspanet/vprogs | Based-app framework (early) |
| https://github.com/kaspanet/docs | Source for docs.kaspa.org |
| https://research.kas.pa/ | Research forum |
| https://qa.kas.pa/ | Research Q&A |
| https://hashd.ag/ | Yonatan Sompolinsky research writing |

### Independent Kaspa explainers and data

| URL | Why it belongs |
| --- | --- |
| https://kaspaexplained.com/ | This comparison’s second site |
| https://kaspaexplained.com/status | Labeled current status |
| https://kaspaexplained.com/sources | Source hierarchy |
| https://kaspaexplained.com/skeptical-case | Risks |
| https://github.com/parker2017code/kaspa-explained | Explainer source |
| https://www.kaspalytics.com/learn/upgrades/crescendo | Crescendo parameters |
| https://www.kaspalytics.com/learn/upgrades/toccata | Toccata parameters |
| https://kaspaspeed.com/ | Live 10 BPS visualization |
| https://kas.fyi/ | Address / holder views |
| https://kaspa.news/ | Community news |
| https://kaspa.stream/resources | Explorer + API notes |

### Ecosystem (not the protocol)

| URL | Why it belongs |
| --- | --- |
| https://www.kaspafoundation.org/ | Kaspa Ecosystem Foundation (KEF) |
| https://kaspa.com/ | **KaspaCom** marketplace / wallet / NFT hub — not kaspa.org |
| https://argent-lang.github.io/ or https://github.com/argent-lang/argent | Covenant language (not release-ready per its README) |

### Research papers (broader than Kaspa branding)

| URL | Why it belongs |
| --- | --- |
| https://eprint.iacr.org/2018/104.pdf | PHANTOM/GHOSTDAG |
| https://eprint.iacr.org/2022/1494.pdf | DAGKnight |
| https://ethereum.org/en/whitepaper/#modified-ghost-implementation | GHOST cited in Ethereum’s white paper |
| https://hashdag.medium.com/kaspa-launch-plan-responding-to-reality-6b4bec449037 | Launch plan |
| https://medium.com/@michaelsuttonil/unveiling-the-crescendo-hard-fork-roadmap-10bps-and-more-6072329e177f | Crescendo roadmap note |
| https://medium.com/@michaelsuttonil/kaspa-covenants-toccata-hard-fork-outlook-a4d81a40900c | Toccata outlook |
| https://github.com/kaspagang/kaspad-py-explorer/blob/main/src/genesis_proof.ipynb | Genesis proof notebook |

### Broader proof-of-work / market context

| URL | Why it belongs |
| --- | --- |
| https://bitcoin.org/bitcoin.pdf | Nakamoto consensus baseline Kaspa generalizes |
| https://www.coingecko.com/en/coins/kaspa | Listing used by both communities |
| https://coinmarketcap.com/currencies/kaspa/ | Markets list |

### Lookalike / caution

Search still surfaces kaspa.org clones and promo pages (example seen in this research: a `kaspakas.org` page recycling kaspa.org layout with a “GET X3 $KAS” pitch). Domain age (kaspa.org since 2021), Cloudflare/AWS hosting, and the kaspanet GitHub org are the practical checks. Do not use a copycat as the official site.

---

## Source list for this report

Primary reads, 16 September 2026 unless noted:

1. https://kaspa.org/
2. https://kaspa.org/lore
3. https://kaspa.org/build
4. https://kaspa.org/kaspa-faq/
5. https://kaspaexplained.com/
6. https://kaspaexplained.com/status (page states sources checked 14 Sep 2026)
7. https://kaspaexplained.com/what-is-kaspa
8. https://kaspaexplained.com/sources (page states kaspa.org lore check 10 Sep 2026)
9. https://kaspaexplained.com/skeptical-case
10. https://github.com/kaspanet/rusty-kaspa
11. https://github.com/kaspanet/rusty-kaspa/releases/tag/v2.0.0
12. https://github.com/kaspanet/rusty-kaspa/releases/tag/v2.0.1
13. https://github.com/parker2017code/kaspa-explained
14. https://api.kaspa.org/info/blockdag
15. https://api.kaspa.org/info/coinsupply
16. https://api.kaspa.org/info/blockreward
17. https://api.kaspa.org/info/hashrate
18. https://docs.kaspa.org/ and https://docs.kaspa.org/toccata
19. https://www.kaspalytics.com/learn/upgrades/crescendo
20. https://www.kaspalytics.com/learn/upgrades/toccata
21. WHOIS for kaspa.org (created 2021-08-14)
22. CoinGecko historical table for KAS, 16 Sep 2026 (~$912M market cap)
23. https://kaspa.com/ (identified as KaspaCom, not the protocol homepage)
24. https://eprint.iacr.org/2018/104.pdf (referenced; not re-derived)

---

## How to re-check this report

```text
# 1. Is Toccata still past activation?
curl -s https://api.kaspa.org/info/blockdag | python -c "import sys,json; d=json.load(sys.stdin); print(d['virtualDaaScore'], int(d['virtualDaaScore'])>=474165565)"

# 2. Supply and reward
curl -s https://api.kaspa.org/info/coinsupply
curl -s https://api.kaspa.org/info/blockreward

# 3. Current node tag
# open https://github.com/kaspanet/rusty-kaspa/releases/latest

# 4. Re-read the two pages that disagreed
# https://kaspa.org/lore
# https://kaspa.org/build
```

If `/lore` is updated to past-tense Toccata, that finding in this report is closed. The method still applies: do not cite a homepage for an activation date without a release tag and a DAA read.

---

*Compiled 16 September 2026. Re-read live sources before repeating any number.*
