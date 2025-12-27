---
title: "🧰 Expressing a Swing Trade: Equity vs Bull Call Spreads"
date: 2025-12-27 15:30:00 0100
categories: [Trading Tools]
tags: [options, swing-trading, risk-management]
image:
  path: /assets/img/2025/december/banner-equity-vs-bull-call-spread.png
  lqtip:
---

### Introduction
There are many ways to express a swing trade in the market.  
The most common — and often the first — is simply buying shares and managing risk with a stop-loss.

As traders evolve, questions around **capital efficiency**, **risk definition**, and **portfolio construction** naturally arise. This is often where options enter the conversation — sometimes with curiosity, sometimes with hesitation.

In this post, I’ll walk through **one specific swing trade on $TGT** and compare two ways of expressing the *same trade idea*:
- A traditional **equity swing trade**
- A **long-dated bull call spread**

The goal is not to promote one approach over the other, but to understand **what actually changes** when you switch instruments while keeping the thesis intact.

---

### The Trade Idea (Same Thesis, Same Levels)

![$TGT equity swing trade](/assets/img/2025/december/tgt-equity.png)
*$TGT – Monthly order block, entry, stop-loss and target*

This is a higher-timeframe mean reversion setup:
- Monthly bullish order block acting as demand
- Liquidity sweep below prior lows
- Acceptance back above the area of interest
- Clear upside target into the next monthly supply zone

**Key levels**
- Entry: ~99.55  
- Stop: ~83.44  
- Target: ~125  
- Time horizon: 6–12 months  

This is not a momentum trade.  
It is a **structure-based swing** designed to give price time to work.

---

### Option 1 – The Equity Swing Trade

The most straightforward way to express this idea is by buying shares.

**Trade structure**
- Buy ~93 shares
- Capital deployed: ~$8,800

**Risk**
- Defined by the stop-loss
- Approximate risk: ~$1,500

**Reward**
- If price reaches 125
- Approximate profit: ~$2,370
- Risk-to-reward: ~1.6R

**Why equity works well**
- No time decay
- Very forgiving if price moves slowly
- Simple to manage and easy to understand

**Trade-off**
- Large capital commitment
- Open-ended gap risk
- Harder to scale across multiple positions

Equity trades are **robust and intuitive**, but capital-heavy.

---

### Option 2 – The Long-Dated Bull Call Spread

Instead of buying shares, we can express the same idea using options:
- Buy a call near current price
- Sell a call at the predefined target
- Use a long-dated expiry (LEAP-style)

This approach fits naturally with the trade plan, as the exit level is already defined in advance.

---

### 12-Month Bull Call Spread

![$TGT bull call spread 12 months](/assets/img/2025/december/tgt-options-12m.png)
*$TGT – 12-month bull call spread*

**Structure**
- Buy 95 Call  
- Sell 125 Call  
- Expiry: ~12 months  

**Risk**
- Capital at risk: ~$1,185 (fully defined)

**Reward**
- Max profit: ~$1,700
- Risk-to-reward: ~1.4R

**What this structure does**
- Replaces ~$8,800 of equity exposure with ~$1,200 of defined risk
- Preserves the same directional thesis
- Eliminates tail risk beyond the premium paid

**What it does not do**
- It does not materially improve R:R
- It does not add explosive upside

The **primary benefit here is capital efficiency**, not higher expectancy.

---

### 6-Month Bull Call Spread

![$TGT bull call spread 6 months](/assets/img/2025/december/tgt-options-6m.png)
*$TGT – 6-month bull call spread*

Using the same strikes with a shorter expiry:
- Lower capital required
- Higher potential R:R
- Less forgiveness if price takes longer to develop

This version improves returns **at the cost of time flexibility**.

---

### Equity vs Long-Dated Bull Call Spread

| Feature | Equity | 12M Bull Call Spread |
|------|------|----------------------|
| Capital used | High | Low |
| Risk | Stop-based | Fully defined |
| Time decay | None | Minimal |
| R:R | Higher | Slightly lower |
| Time forgiveness | High | High |
| Capital efficiency | Low | Very high |

> Long-dated bull call spreads are not about maximizing returns — they are about optimizing capital usage.

---

### The Right Mental Model

Equity and LEAP-style spreads are not competing ideas.  
They are **tools designed for different constraints**.

- Equity excels when capital is abundant and simplicity is preferred
- Long-dated bull call spreads excel when capital efficiency and defined risk matter

For this $TGT setup:
- The thesis does not change
- The levels do not change
- Only the **balance-sheet behavior** changes

---

### Summary

In this post, I compared two ways of expressing the *same swing trade idea*:
- A traditional equity position
- A long-dated bull call spread

Using options — particularly long-dated spreads — is not about leverage or aggression. It’s about **capital efficiency, risk definition, and portfolio flexibility**.

In a future post, I’ll break down:
- When *not* to use options
- How I decide between equity and options on a trade-by-trade basis
- How I manage exits on option spreads before price reaches the target

---
Hope you found this breakdown useful.  
If you trade both equity and options — or are considering the transition — I’d love to hear how you approach these decisions. 👇

{% include comments.html %}
