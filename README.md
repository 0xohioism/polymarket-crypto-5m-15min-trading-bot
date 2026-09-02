# Polymarket Crypto 5, 15 Min Taker Bot

### Live-tested automated execution for BTC, ETH and SOL Up/Down markets

[![Status: Live](https://img.shields.io/badge/status-live-00b386)](https://polymarket.com/@ohioism)
[![Execution: Taker](https://img.shields.io/badge/execution-taker-3b82f6)](https://docs.polymarket.com/trading/fees)
[![Markets: Crypto 5m](https://img.shields.io/badge/markets-BTC%20%7C%20ETH%20%7C%20SOL-111827)](https://polymarket.com/@ohioism)
[![Strategy: Proprietary](https://img.shields.io/badge/strategy-proprietary-8b5cf6)](#public-repository-private-strategy)

This repository is a **public due-diligence overview** of a proprietary automated trading system for Polymarket's short-duration crypto markets. It is not a backtest-only project and it is not presented as a lossless arbitrage bot.

The live account has profitable months, losing days, drawdowns, fees, slippage and unmatched-position risk. Those realities are documented below.

| Purpose | Link |
|---|---|
| Live Polymarket account | [polymarket.com/@ohioism](https://polymarket.com/@ohioism) |
| Public profile wallet | [`0x361528e242bc6cc789ac8da6fd5cb98046178fdf`](https://polymarket.com/profile/0x361528e242bc6cc789ac8da6fd5cb98046178fdf) |
| Commercial license | Telegram [@ohioism](https://t.me/ohioism) |
| Capital or R&D partnership | Telegram [@ohioism](https://t.me/ohioism) |
| Research notes | [medium.com/@ohioism](https://medium.com/@ohioism) |
| Twitter | [x.com/0xohioism](https://x.com/0xohioism/status/2090846151884820872) |

> **No guaranteed returns.** Historical account results are not a promise that another account, configuration, market regime or deployment will produce the same result.

## Live demonstration

<video src="https://github.com/user-attachments/assets/538213df-c0a3-4933-a8e4-5317b05bb546" controls width="100%">
  Your browser does not support embedded video.
</video>

## Execution examples

### Signal-driven DN entry

<img
  width="100%"
  alt="Signal-driven Down taker entry"
  src="https://github.com/user-attachments/assets/5d6dfd7e-3607-447a-8064-8c2aa788d367"
/>

The dashboard connects the complete execution sequence on one screen:

- Underlying price and Polymarket order-book state
- Signal event and probability change
- DN inventory increase
- Executed price, size and timestamp

```text
market update → signal validation → DN taker order → fill reconciliation
```
### Pair economics

<img
  width="100%"
  alt="Matched UP and Down position economics"
  src="https://github.com/user-attachments/assets/3bb78134-5328-4864-aced-290588fdb75f"
/>

<video src="https://github.com/user-attachments/assets/99829a0e-3173-4ce8-8e37-48684c94c200" controls width="100%">
  Your browser does not support embedded video.
</video>

## Verified live record

There are two useful views of the account:

1. **Polymarket's public profile and APIs**, which independently expose the account, trading activity, market count, leaderboard PnL and volume.
2. **Fee-adjusted account analytics**, which reconcile trading PnL, fees and rebates into an estimated net result.

The figures below were captured on **August 25, 2026**. Live endpoints will change as the account continues trading.

### First-party Polymarket proof

| Public metric | Snapshot |
|---|---:|
| Profile created | March 29, 2026 |
| Markets traded | **34,583** |
| Polymarket leaderboard volume | **$5,524,680.55** |
| Polymarket leaderboard PnL | **+$80,803.96** |
| All-time Crypto PnL rank | **#450** |
| All-time Crypto volume rank | **#849** |
| Taker tier | **Gold — Tier 3** |

Verify the data directly:

- [Public Polymarket profile](https://polymarket.com/@ohioism)
- [Polymarket public-profile API](https://gamma-api.polymarket.com/public-profile?address=0x361528e242bc6cc789ac8da6fd5cb98046178fdf)
- [Polymarket total-markets API](https://data-api.polymarket.com/traded?user=0x361528e242bc6cc789ac8da6fd5cb98046178fdf)
- [Polymarket Crypto PnL leaderboard API](https://data-api.polymarket.com/v1/leaderboard?category=CRYPTO&timePeriod=ALL&orderBy=PNL&user=0x361528e242bc6cc789ac8da6fd5cb98046178fdf&limit=1)
- [Polymarket Crypto volume leaderboard API](https://data-api.polymarket.com/v1/leaderboard?category=CRYPTO&timePeriod=ALL&orderBy=VOL&user=0x361528e242bc6cc789ac8da6fd5cb98046178fdf&limit=1)

### Fee-adjusted performance snapshot

<img width="1270" height="763" alt="image" src="https://github.com/user-attachments/assets/994deb3a-3f16-4049-ac3f-12f8e0e79d77" />

| Component | Amount |
|---|---:|
| Trading PnL | **+$80,833** |
| Rebates | **+$7,522** |
| LP income | **+$27** |
| Trading fees | **-$22,664** |
| **Estimated net PnL** | **+$65,718** |
| Total volume | **$5,522,922** |
| Assets at snapshot | **$34,042** |

```text
$80,833 trading PnL
 +$7,522 rebates
     +$27 LP income
 -$22,664 fees
-------------------
 +$65,718 estimated net PnL
```

<img width="367" height="404" alt="image" src="https://github.com/user-attachments/assets/6bf9f0b5-3a4f-4372-b39d-fb1c4f0c2caa" />

#### Why does Polymarket show approximately $80.8k while the dashboard shows $65.7k?

The public Polymarket leaderboard PnL closely matches the dashboard's **trading** component. The dashboard then separately adds rebates and LP income and subtracts recorded fees. For a fee-intensive taker system, the fee-adjusted figure is the more conservative performance number to lead with.

Small differences between the API and screenshots are expected because they were captured at different times, continue to update and may use different rounding or accounting boundaries.

## Monthly results and losing periods

| Period | Net PnL | Positive / negative active days | Active-day hit rate | Best day | Worst day |
|---|---:|---:|---:|---:|---:|
| Apr 27–30, 2026 | **+$1.31k** | 3 / 1 | 75% | +$1.23k | **-$429** |
| May 2026 | **+$7.15k** | 18 / 6 | 75% | +$1.39k | **-$395** |
| Jun 2026 | **+$15.86k** | 22 / 8 | 73% | +$2.18k | **-$985** |
| Jul 2026 | **+$19.76k** | 20 / 11 | 65% | +$4.88k | **-$5.30k** |
| Aug 1–25, 2026 | **+$21.62k** | 19 / 6 | 76% | +$4.41k | **-$1.05k** |
| **Visible sample** | **approximately +$65.7k** | **82 / 32** | **71.9%** | **+$4.88k** | **-$5.30k** |

The hit rate above is calculated from positive and negative **active days**, not individual trades. Zero-activity days are excluded. It should not be interpreted as the probability that any future day or trade will be profitable.

### Drawdown evidence

July was profitable overall, but it contained the most important risk evidence in the sample:

- Worst observed day: **-$5.30k**
- Another large losing day two days later: **-$4.53k**
- Longest visible losing run: **four consecutive negative days**
- Approximate maximum daily-close peak-to-trough drawdown: **$6.47k**, from July 26 to July 29

The drawdown estimate uses rounded daily dashboard values. It is not an intraday maximum-drawdown calculation.

<img width="1233" height="434" alt="image" src="https://github.com/user-attachments/assets/161acf9a-43f5-4559-85c6-fdfff975a218" />

<details>
<summary>View all supplied monthly PnL calendars</summary>

### April 2026

<img width="1235" height="430" alt="image" src="https://github.com/user-attachments/assets/4381efff-cba8-4340-a37f-725165386715" />

### May 2026

<img width="1235" height="495" alt="image" src="https://github.com/user-attachments/assets/05a06d6b-0791-4a0c-ae77-c301afd7dcf7" />

### June 2026

<img width="1230" height="437" alt="image" src="https://github.com/user-attachments/assets/aeeea852-dfdf-43da-a117-d2dc154b9f11" />

### August 2026 through August 25

<img width="1231" height="486" alt="image" src="https://github.com/user-attachments/assets/1f4c2f2a-12d9-4c84-8545-a4fb72b8fa2e" />

</details>

### Additional risk context

- Fees represented approximately **0.41% of total turnover** in the supplied snapshot.
- Net PnL represented approximately **1.19% of cumulative turnover**. This is turnover efficiency, **not return on invested capital**.
- Rebates contributed approximately **11.4% of estimated net PnL**.
- The account remained profitable before rebates in this snapshot, but rebate rules can materially affect future economics.
- Capital deposits, withdrawals and changing account balances prevent a reliable ROI or Sharpe-ratio claim from these screenshots alone.
- These results have not been independently audited. Public account activity is verifiable, but analytics methodology and bot-only attribution should be reviewed during due diligence.

## What the bot trades

The system targets Polymarket markets such as:

> Will BTC, ETH or SOL finish Up or Down during the current five-minute window?

Binary outcome shares trade between approximately `0` and `1`. The winning outcome redeems at `$1`; the losing outcome redeems at `$0`.

The bot combines:

- Live underlying crypto-market data
- Polymarket CLOB order-book data
- Chainlink TWAP observations and market-specific resolution context
- Time remaining, liquidity, spread and execution-cost checks
- Internal signal, exposure and position state

Polymarket currently publishes Chainlink-computed 30-second and 60-second TWAP feeds. The bot does not assume that every market always uses the same window; the active market's rules and current data specification must be treated as authoritative. See the [Polymarket Chainlink TWAP documentation](https://docs.polymarket.com/market-data/chainlink-twap).

At a deliberately high level:

```text
market discovery
      ↓
underlying tape + Chainlink TWAP + CLOB state
      ↓
signal and executable-price validation
      ↓
taker entry on UP or DOWN
      ↓
optional hedge, flip or matched pair
      ↓
position reconciliation and settlement
```

Exact signals, thresholds, sizing rules and production configuration are proprietary.

## Pair economics—without calling it risk-free

A matched UP and DOWN pair in the same binary market redeems for a combined `$1` at settlement. The fee-inclusive economics are:

```text
locked pair edge
≈ $1 - UP acquisition cost - DOWN acquisition cost - fees
```

That edge exists only for the size that is actually matched on both sides below `$1` after costs.

Important failure modes include:

- The first side fills and the hedge does not
- The second side becomes too expensive
- Thin depth creates worse-than-expected execution
- Fees erase a small apparent edge
- Stale or delayed data produces a false signal
- A position remains directional into resolution

The bot therefore cannot be described honestly as a guaranteed or lossless arbitrage system.

## System architecture

| Layer | Responsibility |
|---|---|
| Market discovery | Finds eligible crypto windows and refreshes market metadata |
| Data ingestion | Maintains exchange, Chainlink and Polymarket CLOB feeds with freshness checks |
| Signal engine | Estimates short-horizon direction and executable edge without exposing the proprietary recipe |
| Risk engine | Applies exposure caps, sizing constraints, fee/slippage buffers and uncertainty gates |
| Execution | Submits, monitors and reconciles taker orders asynchronously |
| Position state | Tracks UP/DOWN inventory, average cost, matched size and directional remainder |
| Accounting | Records fills, fees, rebates, settlement and realized PnL |
| Operations | Produces structured logs, alerts, restart recovery and emergency-stop controls |

### Production risk controls

- Per-order and total-exposure caps
- Market-data freshness validation
- Liquidity, spread and minimum-depth checks
- Fee-inclusive expected-value checks
- Slippage, latency and model-uncertainty buffers
- Cooldowns, retry limits and explicit failure handling
- Fill and position reconciliation against Polymarket state
- Detection of unmatched directional inventory
- Configurable circuit breakers and emergency stop
- Paper-only operation for strategy variants that have not passed forward validation

The exact values are deployment-specific and are not published here.

## Activity-level auditability

The system is evaluated from fills and positions, not only from a smooth cumulative chart. The supplied August 24 view shows **267 markets touched**, approximately **$12k traded**, approximately **$12k redeemed**, a **+$911** day and **-$199.46** in fees.

<img width="1221" height="606" alt="image" src="https://github.com/user-attachments/assets/ed85448e-036d-4bba-b737-68b5a8648672" />


The public Polymarket account allows prospective licensees and partners to inspect the underlying market history rather than relying solely on promotional screenshots.

## Public repository, private strategy

This repository intentionally does **not** publish:

- Proprietary signal formulas or feature weights
- Entry, hedge, flip or exit thresholds
- Live sizing and capital-allocation rules
- Private infrastructure, credentials or signing material
- Production source code

The README, public-account proof and demo material are available for evaluation. Commercial implementation details are provided only under an agreed license or partnership process.

## Commercial license

A private commercial license is available for qualified buyers.

The written agreement should define the actual deliverables, including any deployment assistance, configuration, source or executable access, support period, updates, permitted accounts, resale restrictions and IP ownership. Nothing should be assumed from a Telegram conversation alone.

No license includes a promise of profitability. Results depend on capital, configuration, latency, market regime, fee and rebate rules, execution quality and operator discipline.

## Capital and research partnership

I am also looking for serious partners in two areas:

### 1. Dedicated live deployment

A capital or operating partner can work with me on a controlled deployment using:

- A dedicated account and clearly defined capital allocation
- Agreed exposure, loss and drawdown limits
- Transparent fill, fee, rebate and PnL reporting
- A small pilot before any scale-up
- Written profit/loss allocation and termination terms
- A security and custody model agreed before deployment

### 2. New bot research and development

I am open to an engineering or funding partner for additional Polymarket systems, execution research and new market strategies. New ideas should move through research, paper trading, forward validation and limited canary capital before production scale.

Potential R&D work includes:

- Improved execution and inventory control
- Cash-flow-adjusted performance reporting
- Automated drawdown and regime monitoring
- Additional crypto windows and strategy families
- Safer live experimentation and version comparison

### Suggested due-diligence process

1. Inspect the public account and first-party API results.
2. Review the fee-adjusted PnL reconciliation and losing periods.
3. Observe a live or recorded execution demonstration.
4. Define capital, deployment, custody and reporting requirements.
5. Agree written risk, commercial and IP terms.
6. Start with a controlled pilot rather than immediate scale.

## Security

- The only Telegram contact listed by this repository is [@ohioism](https://t.me/ohioism).
- Do not send funds based only on screenshots or direct messages.
- Never send a seed phrase or private key through Telegram, email or a shared document.
- Verify the public account, wallet, deliverables and written terms before payment or capital deployment.
- Watch for impersonators using similar usernames.

## Disclaimer

Trading prediction markets and crypto-linked products involves substantial risk of loss. Historical PnL, volume, hit rate and drawdown figures are descriptive only and are not guarantees of future performance.

This repository is not financial, investment, tax or legal advice and is not a public securities offering. Availability of Polymarket and any commercial arrangement depends on platform rules, user eligibility and applicable law in each jurisdiction. Prospective buyers and partners are responsible for their own legal, technical and financial due diligence.

## Contact

| Channel | Link |
|---|---|
| Polymarket | [@ohioism](https://polymarket.com/@ohioism) |
| Telegram | [@ohioism](https://t.me/ohioism) |
| Medium | [@ohioism](https://medium.com/@ohioism) |

When contacting me, please state whether you are interested in a **commercial license**, a **capital partnership**, or **new-bot R&D**.
