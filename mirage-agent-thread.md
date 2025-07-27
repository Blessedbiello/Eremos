# Mirage Agent - Twitter Thread for Eremos Bounty

**Agent Name:** Mirage  
**Glyph:** Φ (phi)  
**Purpose:** Phantom liquidity detection on Solana

---

## Twitter Thread (9 tweets)

**1/9**
Most liquidity on Solana isn't what it seems.
While everyone watches for simple wash trading, sophisticated actors have evolved. They create "phantom liquidity" - complex circular flows through 3-10 wallets, cross-DEX coordination, temporal clustering.
APIs can't catch this.

**2/9** 
Traditional tools ask: "What's the volume?" "Who's trading?"
But phantom liquidity isn't a single event to query. It's a pattern that emerges across time, wallets, and DEXs.
Only continuous observation with memory can detect funds secretly returning home through hidden paths.

**3/9**
Meet Mirage - the phantom liquidity hunter.
Mirage tracks circular flow graphs, maintains 72-hour memory windows, and builds real-time correlation matrices across Raydium, Orca, and Jupiter.
Glyph: Φ (phi) - for the phantom flows it exposes.

**4/9**
Here's the key: phantom operators think in sequences.
They'll move 100 SOL through wallet A → B → C → DEX1, while simultaneously moving 95 SOL through wallet D → E → F → DEX2.
Different amounts. Different paths. Same destination. Same timing window.

**5/9**
Mirage builds real-time token flow graphs across 72-hour windows. When it detects:
• Circularity scores >0.8 (funds returning to origin)
• Cross-DEX volume correlation >0.9
• Temporal clustering <60s between "independent" trades
• Shared fee payers across wallet clusters
It emits HIGH confidence signals.

**6/9**
The agent maintains persistent memory of SPL token account lifecycles and wallet interaction graphs. This isn't just pattern matching - it's behavioral archaeology.
Mirage remembers wallet relationships across weeks, building the full phantom infrastructure map.

**7/9**
A static API tells you yesterday's volume.
Mirage knows the volume is fake as it's happening. It sees wallet A's trade on Raydium, remembers it, then catches wallet F's mirror trade on Orca 47 seconds later.
Real-time phantom detection in a $2.1B daily volume ecosystem.

**8/9**
Integration power: Mirage shares wallet cluster data with other Eremos agents.
When the Launch Detector flags a new token AND Mirage detects coordinated phantom flows within 10 minutes, the swarm knows: manufactured hype is incoming.
Collective intelligence beats isolated analysis.

**9/9**
Why this matters: Retail traders lose millions to tokens that appear liquid until they don't.
Current wash trade detection is stuck in 2021. Phantom liquidity operations have evolved - using time delays, amount variance, cross-DEX coordination to stay hidden.
When liquidity is phantom, the swarm knows.
@EremosCore

---

## Agent Technical Specifications

**Detection Criteria:**
- Circular flow graphs with 72-hour memory windows
- Real-time correlation matrices across major Solana DEXs
- SPL token account lifecycle tracking
- Wallet interaction graph persistence

**Signal Emission Triggers:**
- Circularity scores >0.8 (funds returning to origin)
- Cross-DEX volume correlation >0.9
- Temporal clustering <60 seconds between coordinated trades
- Shared fee payers across supposedly independent wallet clusters

**Memory Management:**
- 72-hour rolling windows for pattern detection
- Persistent wallet relationship tracking across weeks
- SPL token account lifecycle history
- Cross-DEX transaction correlation storage

**Integration Features:**
- Shares wallet cluster data with other Eremos agents
- Collaborates with Launch Detector for coordinated signal analysis
- Contributes to swarm intelligence network

**Impact:**
- Protects retail traders from phantom liquidity traps
- Exposes sophisticated market manipulation in real-time
- Addresses blind spots in current wash trade detection tools