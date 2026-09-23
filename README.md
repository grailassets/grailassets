<div align="center">

<img src="grail-logo.png" alt="Grail" width="96" />

# Grail

### The shelf lies. The till doesn't.

Every tokenized asset, priced by what actually fills at your size.
Grail puts the headline valuation and the executable size on the same card, then stamps it green or grey.

![Chain](https://img.shields.io/badge/Robinhood%20Chain-4663-0B3D2E?style=flat-square)
![Ticker](https://img.shields.io/badge/%24GRAIL-fair%20launch-C9A227?style=flat-square)
![Custody](https://img.shields.io/badge/custody-none-111111?style=flat-square)
![Stamp](https://img.shields.io/badge/stamp-never%20for%20sale-B03A2E?style=flat-square)

[Website](https://grailassets.shop) · [App](https://app.grailassets.shop) · [Docs](https://grailassets.shop/docs) · [X / Twitter](https://x.com/grailassets) · [GitHub](https://github.com/grailassets)

</div>

---

## What is Grail

That token says $2.5B market cap. Its pool holds $260. Both numbers are true, and only one of them is something you can act on. Grail is a marketplace for tokenized assets that counts only what you can actually buy: every listing is probed live against real pools at your order size, then carries a stamp that no issuer, partner or holder can purchase.

- **Executable size, not market cap.** The number beside every listing is what fills at ≤ 2% impact.
- **Three states, no fourth.** 🟢 OPEN, 🟡 THIN, ⚪ WATCH-ONLY. No "coming soon".
- **Measured at the block.** Every curve carries the block height it was probed at.
- **Graded in public.** Realised fills are scored against quotes, and the misses are published.
- **Non-custodial.** No deposit address exists, so there is nothing to drain.

---

## Core Mechanics

| Mechanic | What it does |
|---|---|
| **"What does this buy?"** | Type a number, see nine real objects it buys, each with its own stamp |
| **Five-point probe** | Simulates fills at $100 / $500 / $2k / $10k / $50k through the best route |
| **Max clean size** | The knee of the fill curve, where impact crosses 2% |
| **The stamp** | A pure function of probe output, versioned, never sold |
| **The scoreboard** | Realised vs quoted delta per asset, bad rows included |
| **Buyback & burn** | 50% of all revenue buys $GRAIL on the open market and burns it weekly |

---

## Probe to Stamp

```
  INDEX ──► ROUTE ──► PROBE ──► CURVE ──► STAMP ──► PUBLISH ──► GRADE
    │         │         │         │         │          │          │
  assets,   every     5 sizes   knee at   🟢 🟡 ⚪   stamp +    realised
  pools     venue,    at the    2%        from data  curve +    vs quoted,
  from      multi-    pinned    impact    alone      block +    in bps,
  chain     hop       block                          route      public
```

---

## Repository Layout

| Repository | Role | What it contains |
|---|---|---|
| [`grail-crucible`](documents/grail-crucible) | Engine | Route planner, five-point probe ladder, curve builder and the versioned stamp function |
| [`grail-canon`](documents/grail-canon) | Documentation | Thesis, stamp methodology with changelog, $GRAIL token paper, threat model |
| [`grail-wire`](documents/grail-wire) | Public API | v1 query contract for stamps, curves, probes and scoreboard, plus embedding rules |
| [`grail-storefront`](documents/grail-storefront) | Web app | Front-door calculator, markets, listing pages, watchlist, method and scoreboard pages |
| [`grail-ledger`](documents/grail-ledger) | Grader & burns | Realised-vs-quoted grader, public scoreboard, weekly buyback and burn record |

### Marketing collateral

| Folder | Contents |
|---|---|
| [`Article/`](Article) | Long-form pieces for Medium and X Articles |
| [`Caption/`](Caption) | Launch and ongoing post captions, long and short form |

---

## Token at a Glance

| Parameter | Value |
|---|---|
| Ticker | $GRAIL |
| Chain | Robinhood Chain (EVM, chainId 4663) |
| Supply | 1,000,000,000 |
| Distribution | 100% fair launch, no team allocation |
| Presale / private round | None |
| Liquidity | Burned at launch, verifiable on-chain |
| Mint function | None |
| Revenue split | 50% treasury · 50% buyback & burn |

| Tier | Hold | Probe cap | API / day | Routing fee |
|---|---|---|---|---|
| Free | 0 | $500 | 20 | 0.30% |
| Bronze | 10,000 | $10,000 | 200 | 0.30% |
| Silver | 100,000 | Unlimited | 2,000 | 0.225% |
| Gold | 1,000,000 | Unlimited | 25,000 | 0.225% |

Holding 100,000 $GRAIL replaces the $29 monthly Pro subscription. No tier buys a better stamp, an earlier stamp or any influence over one.

---

## Tech Stack

| Layer | Choice |
|---|---|
| Chain | Robinhood Chain (EVM, chainId 4663) |
| Web | Next.js 16, React 19, Tailwind CSS 4 |
| Probe | Closed-form pool-state math, block-pinned simulation for multi-hop |
| Workers | Indexer, Prober, Grader, Burner |
| Storage | Managed encrypted Postgres with row-level access policies |
| Security | Non-custodial, fail-closed paid routes, non-root containers, no keys on servers |

---

## Roadmap

| Phase | Window | Milestone |
|---|---|---|
| 1. The Probe | Weeks 1 to 3 | Route planner, five-point ladder, stamp function v1, ~20 assets |
| 2. The Front Door | Weeks 3 to 5 | Calculator, share cards, markets, listing pages, method page |
| 3. Execution | Weeks 5 to 8 | Self-custody swaps, grader, public scoreboard, watchlist alerts |
| 4. The Token | Weeks 8 to 10 | Fair launch, tiers, fee relief, first weekly burn |
| 5. The Catalogue | Months 3 to 6 | Issuer dossiers, query API settlement, split-order planner |
| 6. Beyond One Chain | Months 6 to 12 | Per-chain routes, cross-venue comparison, embeddable stamp widget |

---

## ⚠️ Scam Warning

- There is **no presale**, **no private round** and **no whitelist**. Anyone offering one is running a scam.
- The team will **never DM you first**, ask for your seed phrase, or ask you to "verify" a wallet.
- The contract address is published **only** on [grailassets.shop](https://grailassets.shop) and [@grailassets](https://x.com/grailassets). Anything sent to you by a stranger is a scam.
- Grail never takes deposits. Any site asking you to send funds to a "Grail address" is fake.

---

## Reference Links

| Resource | Link |
|---|---|
| Website | [grailassets.shop](https://grailassets.shop) |
| App | [app.grailassets.shop](https://app.grailassets.shop) |
| Docs | [grailassets.shop/docs](https://grailassets.shop/docs) |
| X / Twitter | [@grailassets](https://x.com/grailassets) |
| GitHub | [github.com/grailassets](https://github.com/grailassets) |

---

<div align="center">
<sub>
Grail publishes market-structure measurements and routing tools. It does not offer financial, investment, legal or tax advice, and nothing here is a recommendation to buy or sell any asset.
Grail is non-custodial and never holds user funds. Probe results are point-in-time measurements at a stated block height, and realised fills may differ from quoted curves.
$GRAIL is a utility token for access tiers and fee relief. It is not a security, not a claim on revenue or assets, and not a promise of any return. Digital assets carry risk, including total loss.
</sub>
</div>
