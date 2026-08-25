# Polymarket Taker Bot

Automated **taker** system for Polymarket **crypto 5‑minute Up/Down** markets (BTC, SOL & ETH).

This repository is a **public overview only** — strategy source code is **not** published here.  
Live results and bot licensing: contact below.

**Live Polymarket profile:** [polymarket.com/@ohioism](https://polymarket.com/@ohioism)  
**Buy the bot / commercial license:** Telegram [@ohioism](https://t.me/ohioism)
**More Info on Medium:** [medium.com/@ohioism](https://medium.com/@ohioism)  


<video src="https://github.com/user-attachments/assets/538213df-c0a3-4933-a8e4-5317b05bb546" controls width="100%">
  Your browser does not support embedded video.
</video>

---

## What the bot is built for

Polymarket short markets such as *“Will BTC (or ETH) go up or down in the next 5 minutes?”*

- **UP** share ≈ price of “finishes higher”  
- **DN** share ≈ price of “finishes lower”  
- Prices trade roughly between `0` and `1`

Settlement for these crypto windows uses **Chainlink TWAP**, not a random exchange last tick. See [Polymarket Chainlink TWAP docs](https://docs.polymarket.com/market-data/chainlink-twap).

At a high level (no proprietary recipe):

```text
live crypto tape  →  signal event  →  taker buy UP or DN  →  optional pair / flip  →  window settle
```

Exact thresholds, sizing, and risk controls ship only with the **licensed bot**, not in this README repo.

---

## How to read the demo screens

### 1) Signal event → DN entry

<img width="100%" alt="dash-flip" alt="image" src="https://github.com/user-attachments/assets/dc80661f-2d7f-4b3c-887a-baba18057563" />


A **signal event** fires and the system **buys DN** (Down) as a taker.

| Layer | What you are seeing |
|-------|---------------------|
| BTC / book | Underlying move + Polymarket asks in a tradable state |
| Signal chart | Event / probability line crosses the entry condition |
| Position chart | **DN inventory steps up** at the event |
| Trade log | DN open / flip with ask, size, timestamp |

```text
market state changes  →  signal event  →  DN buy  →  inventory & cost update
```

This matches how a live taker bot is audited: **timing, fill, size** on one screen — not a manual random click.

### 2) Pair economics: UP + DN cost under $1 (after fees)

<img width="100%" alt="dash-dn-open" src="https://github.com/user-attachments/assets/3bb78134-5328-4864-aced-290588fdb75f" />

On a binary Up/Down market, **one side pays $1** and the other **$0**. A matched **UP + DN pair** therefore redeems **$1** at settlement, regardless of direction.

```text
locked edge ≈ $1 − (UP cost + DN cost) − fees
```

When **combined pair cost stays below 1 after fees**, the matched size is structurally advantaged at settlement — you bought the full binary payoff under par.

| Check | Why it matters |
|-------|----------------|
| UP ask + DN ask (and your averages) | Watch the **sum**, not only one side |
| Fees / slippage | Can erase a thin edge |
| Unmatched leftover | Still directional until hedged or expired |

This is the professional frame behind many short-window taker books — including profiles that hold **both** Up and Down inside active 5m BTC/ETH windows.

---

## Contact

| | |
|--|--|
| Polymarket | [polymarket.com/@ohioism](https://polymarket.com/@ohioism) |
| Telegram | [@ohioism](https://t.me/ohioism) |

---

## Disclaimer

Trading on Polymarket and crypto markets involves **substantial risk of loss**. Screenshots, videos, and profile stats are illustrative only and are **not** performance guarantees. Nothing here is financial, investment, or trading advice. You are solely responsible for any capital you deploy.
