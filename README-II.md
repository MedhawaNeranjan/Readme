# 🤖 Quantum AI Crypto Trading Engine — System Information & Architecture Guide

> **Guide**: *Imagine you are running a high-tech mission control room for trading cryptocurrencies. Instead of one human trying to read thousands of charts, news articles, and price tickers every second, a team of specialized AI robots works together as your expert advisors, guarded by an unbreakable digital safety lock.*

---

## 📚 Table of Contents
1. [What is This System? (The Big Picture)](#1-what-is-this-system-the-big-picture)
2. [Key Concepts Made Simple](#2-key-concepts-made-simple)
3. [The "Team of Experts": Multi-Agent AI Architecture](#3-the-team-of-experts-multi-agent-ai-architecture)
4. [The 6-Step Journey of a Trade Signal](#4-the-6-step-journey-of-a-trade-signal)
5. [Multi-Timeframe Analysis (MTFA) Demystified](#5-multi-timeframe-analysis-mtfa-demystified)
6. [The 18 Technical Indicators Explained](#6-the-18-technical-indicators-explained)
7. [10 Macro Patterns & 9 Candlestick Patterns](#7-10-macro-patterns--9-candlestick-patterns)
8. [Smart Money Concepts (SMC / ICT) & Elliott Wave Theory](#8-smart-money-concepts-smc--ict--elliott-wave-theory)
9. [The 20 Deterministic Strategies & Consensus Math](#9-the-20-deterministic-strategies--consensus-math)
10. [The Unbreakable Digital Shield: The 7 Risk Rules](#10-the-unbreakable-digital-shield-the-7-risk-rules)
11. [System Blueprint & Directory Map](#11-system-blueprint--directory-map)
12. [The Web Dashboard, Interactive Trade Placement & User Experience](#12-the-web-dashboard-interactive-trade-placement--user-experience)
13. [Summary Cheat Sheet & FAQ](#13-summary-cheat-sheet--faq)

---

## 1. What is This System? (The Big Picture)

The **Multi-Agent AI Crypto Trading & Market Analysis Engine** is an automated, real-time computer software system written in **Python 3.11+**. Its purpose is to monitor cryptocurrency markets (such as Bitcoin, Ethereum, and Solana) 24/7, analyze real-time market data across multiple time horizons (`15m`, `1h`, `4h`), coordinate specialist AI agents, test strategy consensus, and calculate precise, risk-guarded trade setups.

### 🌟 Real-World Analogy: The Formula 1 Racing Team
Think of this system like a world championship **Formula 1 Racing Team**:
* **The Telemetry Sensors (CCXT, Binance & CoinGecko APIs)** measure the car's tire pressure, engine temperature, track humidity, and lap speed in real time across multiple intervals.
* **The Specialist Engineers (Specialist AI Agents)** each focus on one discipline:
  * *Telemetry Engineer*: Multi-timeframe chart indicators and candlestick formations.
  * *Weather Forecaster*: Breaking news sentiment and macroeconomic catalysts.
  * *Chassis Inspector*: Token fundamental health and developer activity.
  * *Tire & Fuel Strategist*: Futures open interest, funding rates, and liquidation risk.
* **The Chief Race Strategist (Master Trading Coordinator AI)** gathers all specialist reports, reviews the user's risk appetite, and drafts an optimal race and pit-stop strategy.
* **The Chief Safety Inspector (LLM Risk Reviewer AI & Hard Risk Gate)** has the ultimate veto power: if any safety parameter is violated (low fuel, engine overheating, high crash probability), the race plan is **instantly blocked** to protect capital.
* **The Driver's Cockpit Dashboard (FastAPI & WebSockets)** streams live glowing telemetry dials, multi-timeframe cards, and interactive execution buttons to the team boss (you!).

```mermaid
flowchart TD
    A["🌍 Real-Time Market Ingestion<br/>(Binance Spot/Futures via CCXT, CoinGecko, crypto.news)"] --> B["⏱️ Multi-Timeframe Engine<br/>(15m Trigger, 1h Setup, 4h Macro Trend)"]
    B --> C["🤖 Specialist AI Team<br/>(Tech, News, Fundamentals, Derivatives)"]
    C --> D["🎯 20 Strategies Consensus Engine<br/>(Requires 60% Weight & >= 5 Agreeing)"]
    D --> E["🧠 Master Coordinator AI<br/>(Entry, TP, SL, R:R, Position Sizing Math)"]
    E --> F["🕵️ Independent Risk Reviewer<br/>(Devil's Advocate AI Validation)"]
    F --> G["🛡️ Hard Risk Gate Guard<br/>(7 Deterministic Code-Level Safety Rules)"]
    G -->|Passed (All 7 Rules OK)| H["🚀 Executable Signal & Interactive Order Modal"]
    G -->|Blocked (Violations Found)| I["🛑 Blocked Signal (Logs Reasons for Safety)"]
```

---

## 2. Key Concepts Made Simple

Here are simple, clear explanations of key trading and crypto concepts:

| Term | Grade 10 Explanation | Real-Life Comparison |
|---|---|---|
| **Cryptocurrency** | Digital money secured by cryptography (e.g., BTC, ETH, SOL). | Digital tokens or digital gold traded on open global markets. |
| **Spot Market** | Buying the actual underlying coin. You only make a profit if the price goes **UP**. | Buying a physical collector's card and holding it until its price rises. |
| **Perpetual Futures** | A derivatives contract enabling you to profit whether the price goes **UP** (Long) or **DOWN** (Short). | Placing a contract on whether tomorrow's temperature will be higher or lower. |
| **Buy / Long** | Opening a position expecting the market price to **increase**. | Buying inventory before high demand season. |
| **Sell / Short** | Opening a position expecting the market price to **decrease**. | Borrowing a video game to sell at $60, buying it back at $20, and keeping the $40 difference. |
| **Leverage (e.g., 5x, 10x)** | Multiplying your position size using borrowed funds. | Riding a bicycle (1x) vs. driving a turbocharged sports car (10x). Speed multiplies, but mistakes are magnified! |
| **Margin / Bet Amount** | The actual cash amount of your own money placed on a single trade (e.g., $10 USD). | Your stake in a single round of a game. |
| **Position Size** | Total purchasing power of the trade ($\text{Margin} \times \text{Leverage}$). | Putting down a $10 deposit to control a $100 piece of equipment at 10x leverage. |
| **Entry Price** | The exact price at which a trade is opened. | The ticket price when boarding a train. |
| **Take-Profit (TP)** | An automatic order that sells when the price hits your target profit goal. | Ringing the cash register to lock in your winnings. |
| **Stop-Loss (SL)** | An automatic emergency brake that sells if the market drops to a specific level, capping losses. | An airbag in a vehicle that stops a small bump from becoming a catastrophe. |
| **Risk-to-Reward (R:R)** | Comparing how much money you risk losing vs. how much you stand to gain (e.g., 1:2 or 1:3). | Risking $5 of lunch money to potentially gain $15. |
| **Multi-Timeframe Analysis** | Checking 3 different zoom levels (`15m`, `1h`, `4h`) to ensure the big picture and small picture agree. | Checking regional weather, track temperature, and immediate cloud cover before racing. |
| **Liquidation** | In futures trading, if the market moves too far against your position, the exchange closes it to prevent debt. | An automatic game over when your health bar hits zero. |
| **Funding Rate** | Periodic fee exchanged between Long and Short traders to keep futures prices tethered to spot prices. | A balancing fee paid between people betting up vs. down. |
| **Open Interest (OI)** | Total number of outstanding active futures contracts that have not been settled. | Total number of active tickets in play across an arena. |
| **Order Block (OB)** | The last opposing candlestick before a massive institutional price expansion. | The footprint left in the sand by a giant walking on the beach. |
| **Fair Value Gap (FVG)** | A 3-candle price imbalance where price moved so violently that orders were left unfilled. | A sudden gap in a fence that price often returns to fill. |

---

## 3. The "Team of Experts": Multi-Agent AI Architecture

The system splits market analysis across **specialized autonomous AI agents** that operate concurrently before a centralized coordinator synthesizes the final trade plan:

```mermaid
graph LR
    subgraph DataIngestion ["1. Real-Time Data Ingestion"]
        D1["📊 Price Candles (15m, 1h, 4h via CCXT)"]
        D2["📰 News Articles (crypto.news)"]
        D3["🏢 Token Health (CoinGecko)"]
        D4["📈 Derivatives (Funding Rates & OI)"]
    end

    subgraph SpecialistAgents ["2. Specialist AI Agents"]
        A1["💻 Tech Agent<br/>(MTFA, 18 Indicators & 19 Patterns)"]
        A2["📰 News Agent<br/>(Sentiment Analysis)"]
        A3["🪙 Fundamental Agent<br/>(0-100 Quality Score)"]
        A4["⚡ Futures Agent<br/>(Derivatives & Liquidation)"]
    end

    subgraph ConsensusAndCoordination ["3. Consensus & Decision"]
        C1["🎯 20 Strategies Consensus"]
        C2["🧠 Master Coordinator Agent<br/>(Trade Plan & Position Sizing)"]
    end

    subgraph RiskSecurity ["4. Risk & Safety Guard"]
        R1["🕵️ Independent Risk Reviewer"]
        G1["🛡️ 7-Rule Hard Risk Gate"]
    end

    D1 --> A1
    D2 --> A2
    D3 --> A3
    D4 --> A4

    A1 --> C1
    C1 --> C2
    A2 --> C2
    A3 --> C2
    A4 --> C2

    C2 --> R1
    R1 --> G1
```

### 1. 📊 The Technical Analysis Agent (`agents/tech_agent.py`)
* **Role**: The "Chart Scientist".
* **What it does**: Analyzes multi-timeframe candle data (`15m`, `1h`, `4h`), computes 18 mathematical indicators, scans 10 macro chart patterns, detects 9 Japanese candlestick pattern categories, analyzes SMC/ICT order flow, and verifies Elliott Wave impulse legs.
* **Output**: A comprehensive technical breakdown, timeframe metrics, detected patterns, and an overall bias: `BULLISH`, `BEARISH`, or `NEUTRAL`.

### 2. 📰 The Market News & Sentiment Agent (`agents/news_agent.py` & `crawler.py`)
* **Role**: The "News Detective".
* **What it does**: Continuously monitors news feeds (via RSS feeds and sitemaps), stores articles in the Supabase database, and evaluates the sentiment of recent headlines using AI.
* **Why it matters**: A coin might have a perfect technical chart, but breaking negative regulatory news or security exploits could cause an immediate crash. The News Agent flags these catalysts.
* **Output**: A sentiment score from `-1.0` (extreme fear/panic) to `+1.0` (extreme optimism/euphoria) with key headline summaries.

### 3. 🪙 The Fundamental Analysis Agent (`agents/fund_agent.py` & `fundamentals.py`)
* **Role**: The "Tokenomics Auditor".
* **What it does**: Inspects CoinGecko data to score the underlying token's health (0 to 100).
* **Metrics It Evaluates**:
  * **Market Cap Rank**: Is it an established Top 10 giant or a highly volatile micro-cap?
  * **Volume-to-Market Cap Ratio**: Is there genuine trading liquidity?
  * **Fully Diluted Valuation (FDV) Ratio**: Is there significant token unlock inflation ahead?
  * **Developer Commits (GitHub)**: Are software engineers actively building and committing code?
* **Output**: A fundamental score out of 100 with tokenomics insights.

### 4. ⚡ The Futures Derivatives Agent (`agents/futures_agent.py`)
* **Role**: The "Crowd & Liquidity Watcher".
* **What it does**: Analyzes professional derivatives metrics directly from Binance Futures.
* **Key Metrics**:
  * **8-Hour Funding Rate**: Are traders excessively long (paying high funding) or excessively short?
  * **24h Open Interest (OI) Change**: Is fresh institutional capital entering or leaving the market?
  * **Long/Short Account Ratio**: What percentage of market participants are positioned long vs. short?
  * **Estimated Liquidation Distance**: How far away is the liquidation price from the current mark price?
* **Output**: Identifies crowd positioning traps and calculates safe leverage recommendations.

### 5. 🧠 The Master Trading Coordinator (`agents/coordinator.py`)
* **Role**: The "Chief Race Strategist".
* **What it does**: Collates all specialist reports, evaluates the strategy consensus, incorporates user risk settings, and computes exact trade mathematics:
  * **Action**: `BUY_LONG`, `SELL_SHORT`, or `HOLD`
  * **Entry Price, Take-Profit Price, and Stop-Loss Price**
  * **Risk-to-Reward Ratio (R:R)**
  * **Position Sizing Math**: Exact dollar risk at Stop-Loss and exact dollar profit at Take-Profit based on the user's margin bet (e.g., $10 USD).
  * **Safe Leverage Recommendation**: Max safe leverage keeping liquidation ≥ 15% away and safely beyond the Stop-Loss.

### 6. 🕵️ The Independent Risk Reviewer (`agents/risk_reviewer.py`)
* **Role**: The "Devil's Advocate".
* **What it does**: An independent AI agent that inspects the Coordinator's trade draft. It checks for cross-agent contradictions (e.g., "Why initiate a Long if the News Agent detected heavy negative sentiment and Futures funding is extreme?").
* **Output**: Approves or rejects the trade proposal and adjusts the final confidence score.

---

## 4. The 6-Step Journey of a Trade Signal

The lifecycle of how market data transforms into an executable signal in `pipeline.py`:

```mermaid
sequenceDiagram
    autonumber
    actor User as 👤 User / Auto-Scanner
    participant Pipe as ⚙️ Pipeline Engine
    participant Data as 📡 Binance / CoinGecko APIs
    participant Agents as 🤖 Specialist AI Agents
    participant Cons as 🎯 20 Strategies Consensus
    participant Coord as 🧠 AI Coordinator
    participant Rev as 🕵️ Risk Reviewer AI
    participant Gate as 🛡️ Hard Risk Gate
    participant UI as 💻 Live Web Dashboard

    User->>Pipe: Request Analysis (e.g. BTCUSDT, R:R=2.0, Bet=$10, Lev=10x)
    Pipe->>Data: Fetch parallel OHLCV (15m, 1h, 4h) & derivatives metrics
    Data-->>Pipe: Return multi-timeframe candles, funding rates, OI, tokenomics

    par Parallel Agent Execution
        Pipe->>Agents: Run Tech Agent (MTFA, 18 Indicators, Patterns, SMC, Waves)
        Pipe->>Agents: Run News Agent (Recent Headlines & Sentiment)
        Pipe->>Agents: Run Fund Agent (CoinGecko Tokenomics 0-100 Score)
        Pipe->>Agents: Run Futures Agent (Derivatives Risk & OI)
    end
    Agents-->>Pipe: Return 4 Specialist Reports

    Pipe->>Cons: Evaluate 20 Deterministic Strategies
    Cons-->>Pipe: Return Consensus Result (Buy/Sell Weight & Agreement)

    Pipe->>Coord: Synthesize reports into a Trade Plan
    Coord-->>Pipe: Draft Trade Plan (Entry, TP, SL, R:R, Lev, Position Math)

    Pipe->>Rev: Validate Trade Plan independently
    Rev-->>Pipe: Review Approved / Concerns / Adjusted Confidence

    Pipe->>Gate: Test against the 7 Deterministic Hard Risk Rules
    alt All 7 Rules Pass
        Gate-->>Pipe: PASSED (Executable = True, Violations = [])
    else Any Rule Fails
        Gate-->>Pipe: BLOCKED (Executable = False + Violation Descriptions)
    end

    Pipe->>UI: Stream live signal & MTFA details via WebSocket
    UI-->>User: Display glowing card + Place Trade execution modal
```

---

## 5. Multi-Timeframe Analysis (MTFA) Demystified

### Why Look at 3 Timeframes?
Looking at only a single 1-hour chart is like driving while only looking 5 meters in front of your bumper. You might miss a giant storm on the horizon or a sharp nail right under your wheel. 

The system analyzes **3 distinct lenses simultaneously**:

```text
┌────────────────────────────────────────────────────────────────────────────────────────┐
│                        ⏱️ THE 3-TIMEFRAME CONFLUENCE PYRAMID                           │
├──────────────────────┬────────────────────────┬────────────────┬───────────────────────┤
│ Timeframe            │ Role                   │ Weight         │ Trading Function      │
├──────────────────────┼────────────────────────┼────────────────┼───────────────────────┤
│ 4h (Higher TF)       │ Macro Trend Filter     │ 40% Weight     │ Overall market tide   │
│ 1h (Primary TF)      │ Intermediate Setup     │ 40% Weight     │ Core trade geometry   │
│ 15m (Lower TF)       │ Precision Trigger      │ 20% Weight     │ Exact entry timing    │
└──────────────────────┴────────────────────────┴────────────────┴───────────────────────┘
```

### Confluence Status Categories:
1. **`FULL_CONFLUENCE` ($\ge 85\%$ alignment with HTF and LTF confirmation)**:
   * All three timeframes agree in the same direction.
   * **Reward**: Automatically boosts the trade's confidence score by **+10%** (`+0.10`).
2. **`STRONG_CONFLUENCE` ($\ge 65\%$ alignment)**:
   * Clear multi-timeframe directional agreement.
   * **Reward**: Boosts confidence by **+6%** (`+0.06`).
3. **`MODERATE` ($45\% - 64\%$ alignment)**:
   * Mixed or sideways readings across timeframes.
   * **Result**: Neutral (0% adjustment).
4. **`CONFLICTING` ($< 45\%$ alignment)**:
   * Shorter timeframe is fighting against the higher timeframe macro trend.
   * **Penalty**: Incurs an automatic **-10% penalty** (`-0.10`) and attaches a caution warning.

---

## 6. The 18 Technical Indicators Explained

The technical engine computes 18 institutional indicators on every analysis cycle:

| Indicator | Code Function | What it Measures | Interpretation & Signals |
|---|---|---|---|
| **EMA Crossover** | `compute_ema` | Trend direction | Fast EMA (12) crossing above Slow EMA (26) is **BULLISH**; below is **BEARISH**. |
| **SMA** | `compute_sma` | Macro baseline trend | Price above SMA (50) indicates an uptrend; below indicates a downtrend. |
| **RSI** | `compute_rsi` | Momentum & exhaustion | RSI > 70 is Overbought; RSI < 30 is Oversold. Above 50 is bullish momentum. |
| **MACD** | `compute_macd` | Momentum acceleration | MACD line crossing above Signal line or Histogram > 0 is **BULLISH**. |
| **Bollinger Bands** | `compute_bollinger_bands` | Volatility & mean reversion | Price touching lower band signals potential bounce; upper band signals reversal. |
| **Support & Resistance** | `compute_support_resistance` | Key price inflection levels | Computes Pivot Point, S1/S2 support levels, and R1/R2 resistance levels. |
| **RSI Divergence** | `compute_rsi_divergence` | Reversal divergence | Regular Bullish (price lower low + RSI higher low) and Bearish divergence. |
| **Stochastic Oscillator** | `compute_stochastic` | Cycle turning points | %K crossing above %D in oversold zone (<20) is **BULLISH**; >80 is **BEARISH**. |
| **ATR (Average True Range)** | `compute_atr` | Market volatility | Measures average price range per candle for volatility-adjusted stop-loss sizing. |
| **VWAP** | `compute_vwap` | Volume-weighted benchmark | Price above VWAP shows institutional buying premium; below shows discount. |
| **Supertrend** | `compute_supertrend` | Dynamic trend following | ATR-based trailing stop band. Green band under price = **BULLISH**; Red band above = **BEARISH**. |
| **Keltner Channels & Squeeze** | `compute_keltner_channels` | Volatility squeeze breakout | Bollinger Bands narrowing inside Keltner Channel identifies an explosive squeeze breakout. |
| **On-Balance Volume (OBV)** | `compute_obv` | Institutional volume flow | Cumulative volume confirmed against 20 EMA. OBV > 20 EMA signals accumulation. |
| **Ichimoku Cloud** | `compute_ichimoku` | Trend, momentum & cloud support | Price above Kumo Cloud with Tenkan >= Kijun signals strong **BULLISH** trend. |
| **ADX (+DI / -DI)** | `compute_adx` | Trend strength filter | ADX > 25 indicates strong trending market. +DI > -DI is bullish; -DI > +DI is bearish. |
| **Money Flow Index (MFI)** | `compute_mfi` | Volume-weighted RSI | MFI < 20 indicates extreme institutional oversold; MFI > 80 indicates overbought. |
| **Parabolic SAR** | `compute_parabolic_sar` | Trailing stop & reverse | Trailing dots flipping below price indicate **BULLISH** momentum. |
| **Fair Value Gap (FVG)** | `compute_fvg` | 3-candle liquidity imbalance | Identifies unfilled order flow gaps where price expanded with high speed. |

---

## 7. 10 Macro Patterns & 9 Candlestick Patterns

### 10 Macro Chart Patterns
1. **Double Top**: Two consecutive price peaks at similar resistance levels (Bearish reversal).
2. **Double Bottom**: Two consecutive price troughs at similar support levels (Bullish reversal).
3. **Head & Shoulders**: Higher peak (head) flanked by two lower peaks (shoulders) (Bearish reversal).
4. **Inverse Head & Shoulders**: Lower trough (head) flanked by two higher troughs (Bullish reversal).
5. **Ascending Triangle**: Flat resistance ceiling with rising support higher lows (Bullish continuation).
6. **Descending Triangle**: Flat support floor with declining resistance lower highs (Bearish continuation).
7. **Symmetrical Triangle**: Converging support and resistance lines (Breakout imminent).
8. **Rising Wedge**: Converging rising trendlines (Bearish reversal).
9. **Falling Wedge**: Converging falling trendlines (Bullish reversal).
10. **Bull Flag**: Sharp impulsive rally followed by slight downward consolidation (Bullish continuation).

### 9 Japanese Candlestick Patterns
1. **Doji**: Standard Doji (indecision), Dragonfly Doji (bullish rejection), Gravestone Doji (bearish rejection).
2. **Hammer & Hanging Man**: Bullish Hammer (long lower wick after downtrend), Inverted Hammer, Hanging Man, Shooting Star.
3. **Marubozu**: Bullish / Bearish Marubozu (≥90% real candle body showing overwhelming conviction).
4. **Engulfing**: Bullish Engulfing (green body engulfs previous red) / Bearish Engulfing.
5. **Harami**: Bullish / Bearish Harami (small candle body contained inside prior large candle).
6. **Piercing Line & Dark Cloud Cover**: 2-candle patterns with >50% penetration into prior candle body.
7. **Tweezers**: Tweezer Top (matching highs) and Tweezer Bottom (matching lows).
8. **Star Patterns**: Morning Star (3-candle bullish reversal) and Evening Star (3-candle bearish reversal).
9. **Three Soldiers & Crows**: Three White Soldiers (3 strong green candles) and Three Black Crows (3 strong red candles).

---

## 8. Smart Money Concepts (SMC / ICT) & Elliott Wave Theory

### Smart Money Concepts & ICT
The engine implements institutional order-flow mechanics in [`market_structure.py`](file:///c:/Users/acer/Desktop/My%20Project/my-ai-crypto-bot/market_structure.py):
* **Symmetric Swing Pivots**: Confirmed swing highs and swing lows requiring completed candles on both sides.
* **Break of Structure (BOS)**: Price closing beyond previous swing high/low in the direction of the prevailing trend.
* **Change of Character (ChoCH)**: Price closing beyond the opposing swing level, indicating structural trend change.
* **Liquidity Sweeps**: Price briefly piercing a swing extreme to trigger stop-orders before reversing back into range.
* **Order Blocks (OB)**: Tracking active, mitigated, or invalidated institutional supply/demand zones.
* **Optimal Trade Entry (OTE)**: Fibonacci retracement zone between **62% (0.62) and 79% (0.79)** of the dealing range.
* **UTC Kill-Zones**: London Kill-Zone (07:00–10:00 UTC), New York Kill-Zone (12:00–15:00 UTC), Asia Session (00:00–05:00 UTC).

### Deterministic Elliott Wave Theory
Validates 5-wave impulse structures ($1 \to 2 \to 3 \to 4 \to 5$) against Elliott's **3 unbreakable hard rules**:
1. **Rule 1 (Wave 2 Origin)**: Wave 2 never retraces more than 100% of Wave 1 origin.
2. **Rule 2 (Wave 3 Length)**: Wave 3 is never the shortest impulse wave among Waves 1, 3, and 5.
3. **Rule 3 (Wave 4 Overlap)**: Wave 4 never enters the price territory of Wave 1.
4. **Progressive Extremes**: Confirms progressive price extension across Wave 3 and Wave 5.
5. **Fibonacci Projections**: Wave 3 target (1.618x Wave 1), Wave 5 target (0.618x / 1.0x Wave 1), with explicit invalidation price levels.

---

## 9. The 20 Deterministic Strategies & Consensus Math

In [`strategies.py`](file:///c:/Users/acer/Desktop/My%20Project/my-ai-crypto-bot/strategies.py), 20 distinct quantitative strategies are evaluated:

```text
1.  EMA_Crossover         11. SMC_ICT_Confluence
2.  RSI_Reversal          12. Elliott_Wave
3.  MACD_Momentum         13. Supertrend
4.  Bollinger_Bounce      14. Keltner_Squeeze
5.  Trend_Confluence      15. OBV_Flow
6.  Divergence_Breakout   16. Ichimoku_Cloud
7.  Stochastic_Reversal   17. ADX_Trend
8.  ATR_Breakout          18. MFI_Reversal
9.  VWAP_Mean_Reversion   19. Parabolic_SAR
10. Pattern_Breakout      20. FVG_Rebalance
```

### Consensus Engine Voting Mechanism:
1. Each strategy emits a `StrategySignal` (`BUY_LONG`, `SELL_SHORT`, or `HOLD`) with a confidence score (e.g., 0.55 to 0.85).
2. The consensus engine sums total buy confidence weight vs. sell confidence weight vs. hold weight.
3. To trigger an executable action:
   * **Consensus Weight $\ge$ 60%** of total strategy voting weight.
   * **Minimum Agreeing Strategies $\ge$ 5** agreeing on the direction.
4. If the threshold is not met, the consensus action defaults to `HOLD` with `executable = False`.

---

## 10. The Unbreakable Digital Shield: The 7 Risk Rules

Located in [`risk_gate.py`](file:///c:/Users/acer/Desktop/My%20Project/my-ai-crypto-bot/risk_gate.py), the Hard-Risk Gate is a deterministic code-level barrier with **zero AI involvement**:

```text
┌────────────────────────────────────────────────────────────────────────────────────────┐
│                        🛡️ THE 7 HARD-RISK RULES & PROTECTION MATRIX                    │
├────────────────────────────────────────────────────────────────────────────────────────┤
│ RULE 1: Direction Alignment    │ Spot trades cannot be SELL_SHORT. Spot is long-only.  │
├────────────────────────────────┼───────────────────────────────────────────────────────┤
│ RULE 2: RSI Boundary Guard     │ Block BUY_LONG if RSI > 75.0 (prevents buying tops).  │
│                                │ Block SELL_SHORT if RSI < 25.0 (prevents shorting dip)│
├────────────────────────────────┼───────────────────────────────────────────────────────┤
│ RULE 3: Stochastic Guard       │ Block BUY_LONG if %K > 85.0 (overbought rejection).   │
│                                │ Block SELL_SHORT if %K < 15.0 (oversold bounce risk). │
├────────────────────────────────┼───────────────────────────────────────────────────────┤
│ RULE 4: Minimum R:R Threshold  │ Trade MUST achieve at least 1.5:1 (or user target R:R)│
│                                │ reward-to-risk ratio.                                 │
├────────────────────────────────┼───────────────────────────────────────────────────────┤
│ RULE 5: Strict Price Order     │ Longs must satisfy: Stop-Loss < Entry < Take-Profit.  │
│                                │ Shorts must satisfy: Take-Profit < Entry < Stop-Loss. │
├────────────────────────────────┼───────────────────────────────────────────────────────┤
│ RULE 6: Futures Liquidation    │ 6a. Leverage cannot exceed MAX_ALLOWED_LEVERAGE (500x)│
│         & Derivatives Guard    │ 6b. Liquidation price must be >= 15.0% away from entry│
│                                │     and strictly beyond the Stop-Loss price.          │
│                                │ 6c. Block trades betting against extreme funding rate.│
├────────────────────────────────┼───────────────────────────────────────────────────────┤
│ RULE 7: HOLD Safety Guard      │ HOLD decisions are never marked executable.           │
└────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 11. System Blueprint & Directory Map

```text
my-ai-crypto-bot/
├── main.py               # 🚀 Application Launcher & CLI Single-Shot Runner
├── server.py             # 🌐 FastAPI Web Server, Auth APIs, WebSocket Streamer & UI
├── pipeline.py           # 🔄 Master Pipeline Orchestrator (Multi-TF data coordination)
├── risk_gate.py          # 🛡️ Hard-Coded 7-Rule Safety Gate Guard
├── config.py             # ⚙️ Settings, Risk Thresholds, MTFA Config, Monitored Coins
├── models.py             # 📋 Pydantic v2 Data Models, MTFA Reports & Schemas
├── database.py           # 💾 Supabase Cloud Database Manager (Articles & Signals)
├── ccxt_client.py        # 📡 CCXT Binance Market Data Client (Spot, Futures, Parallel TFs)
├── indicators.py         # 📐 18 Indicators, 10 Macro Patterns, 9 Candlestick Detectors, MTFA
├── market_structure.py   # 🏛️ Deterministic SMC/ICT & Elliott Wave Impulse Analyzer
├── fundamentals.py       # 🪙 CoinGecko Scraper & 0-100 Fundamental Health Scorer
├── crawler.py            # 🕷️ Async News Scraper (crypto.news RSS & Sitemap Discovery)
├── strategies.py         # 🎯 20 Deterministic Strategies & Consensus Engine
├── schema.sql            # 🗄️ Supabase PostgreSQL schema definitions
├── requirements.txt      # 📦 Project Python dependencies
├── agents/               # 🤖 Specialist AI Agents
│   ├── __init__.py       # Package init
│   ├── ai_utils.py       # 🧹 Robust JSON Extractor & Prompt Text Cleaner
│   ├── coordinator.py    # 🧠 Master Trading Coordinator Agent
│   ├── tech_agent.py     # 📊 Technical Chart Analysis Agent (MTFA-enabled)
│   ├── news_agent.py     # 📰 News Sentiment Analysis Agent
│   ├── fund_agent.py     # 🪙 Fundamental Quality Agent
│   ├── futures_agent.py  # ⚡ Futures Derivatives Agent
│   └── risk_reviewer.py  # 🕵️ Independent Risk Review Agent
└── tests/                # 🧪 Automated Test Suite
    ├── __init__.py
    └── test_regressions.py # 39 Comprehensive Regression & Unit Tests
```

---

## 12. The Web Dashboard, Interactive Trade Placement & User Experience

The web dashboard (`server.py`) provides an interactive command center directly in your web browser:

1. **🔒 Secure Authentication**: Protected with username and password verification configured via `.env`.
2. **⚡ Real-Time WebSocket Streaming (`/ws`)**: Price movements, scan updates, and multi-timeframe AI trade signals appear automatically without page refreshes.
3. **🎛️ Interactive Risk & Position Sizing Controls**:
   * Set your **Target Minimum Risk-to-Reward Ratio** (e.g., 2.0x, 3.0x).
   * Set your **Margin Bet Amount in USD** (e.g., $10 USD default).
   * Choose your preferred **Leverage** (or let the AI suggest the optimal safe leverage).
4. **🔍 Live Instant Search**: Search any coin among Top 50 monitored pairs with real-time UI filtering.
5. **🎯 Interactive "Place Trade" Execution Modal**:
   * Click **"🎯 Place Trade"** on any actionable card to open the order confirmation modal.
   * View live calculations for **Margin Bet ($)**, **Leverage**, **Position Size ($)**, **Max Risk (-$Risk)**, **Target Profit (+$Profit)**, and **Estimated ROI %**.
   * Inspect individual **15m, 1h, and 4h Timeframe Cards** (Bias, Trend, RSI) and the **Confluence Badge**.
   * Click **"Confirm & Place Trade"** to execute order placement via `POST /api/place-trade` and generate an instant order receipt.
6. **🔬 Deep Dive Inspection Modal**: Click on any signal card to open a multi-tab inspection modal showing indicator breakdowns, tokenomics, news sentiment, and risk reviewer feedback.
7. **📰 News Scraper Control**: Trigger on-demand news crawls directly from the web interface.
8. **🔒 Logout Control**: One-click logout locks the control center.

---

## 13. Summary Cheat Sheet & FAQ

* **What programming language is used?** Python 3.11+ with FastAPI, Pydantic v2, and CCXT.
* **What AI models are supported?** NVIDIA NIM (`nvidia/nemotron-3.5-lightning-30b-a3b` default via OpenAI-compatible SDK) and Anthropic Claude (`claude-sonnet-4-20250514`), with automatic fallback to deterministic math if no API key is set.
* **How does Multi-Timeframe Analysis work?** It evaluates `15m`, `1h`, and `4h` timeframes simultaneously, requiring alignment between the macro trend (4h) and trigger (15m) before applying confidence boosts.
* **Where does market data come from?** Binance (Spot & USD-M Futures) via CCXT, CoinGecko for fundamental metrics, and crypto.news for RSS news feeds.
* **Where is data stored?** Supabase cloud database (`articles` and `signals` tables).
* **How many strategies and tests exist?** 20 distinct quantitative strategies and **39 automated unit & regression tests** in `tests/test_regressions.py`.
* **How do I launch the platform?**
  ```bash
  # 1. Start the Web Dashboard
  python main.py

  # 2. Or run a single analysis in your terminal
  python main.py --cli-only --symbol BTCUSDT --market SPOT
  ```

---
*Created for the Multi-Agent AI Crypto Trading System. Designed to be modular, robust, educational, and mathematically safe!*
