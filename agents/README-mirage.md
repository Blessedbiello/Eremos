# Mirage Agent - Phantom Liquidity Hunter

**Agent ID:** `agent-mirage`  
**Glyph:** Φ (phi)  
**Role:** `phantom_detector`  
**Watch Type:** `liquidity_manipulation`

## Overview

Mirage is an Eremos swarm agent designed to detect sophisticated phantom liquidity operations on Solana. Unlike traditional wash trade detection that focuses on simple patterns, Mirage identifies complex circular flows, cross-DEX coordination, and temporal clustering that sophisticated actors use to create the illusion of organic trading volume.

## Problem Statement

Modern liquidity manipulation has evolved beyond basic wash trading. Sophisticated actors now:
- Route funds through 3-10 wallets in circular patterns
- Coordinate trades across multiple DEXs (Raydium, Orca, Jupiter)
- Use temporal clustering to mask coordinated behavior
- Vary amounts and timing to evade simple detection

Traditional APIs and static analysis tools cannot detect these patterns because they lack:
- Real-time cross-DEX correlation analysis
- Memory of fund flow relationships over time
- Pattern recognition across multiple wallet clusters

## Detection Methodology

### Core Detection Criteria

1. **Circular Flow Analysis**
   - Tracks fund movements through wallet networks
   - Identifies when funds return to origin within 72-hour windows
   - Calculates circularity scores based on path complexity

2. **Cross-DEX Correlation**
   - Monitors simultaneous trading patterns across major Solana DEXs
   - Detects volume correlation >0.9 between "independent" trades
   - Identifies coordinated market making activities

3. **Temporal Clustering**
   - Flags trades occurring within <60 seconds across wallet clusters
   - Analyzes timing patterns that suggest coordination
   - Detects burst trading activities that correlate with price movements

4. **Wallet Infrastructure Analysis**
   - Maps shared fee payers across supposedly independent wallets
   - Tracks SPL token account lifecycles
   - Identifies common funding sources and drainage patterns

### Signal Emission Triggers

Mirage emits **HIGH confidence** signals when:
- Circularity scores exceed 0.8 (funds returning to origin)
- Cross-DEX volume correlation exceeds 0.9
- Temporal clustering occurs within 60-second windows
- Shared infrastructure detected across wallet clusters

## Technical Implementation

### Memory Management
- **72-hour rolling windows** for pattern detection
- **Persistent wallet relationship tracking** across weeks
- **SPL token account lifecycle history**
- **Cross-DEX transaction correlation storage**

### Real-time Processing
- Continuous monitoring of DEX transactions
- Real-time correlation matrix updates
- Dynamic wallet cluster identification
- Behavioral pattern scoring

### Integration Features
- **Swarm Intelligence**: Shares wallet cluster data with other Eremos agents
- **Collaborative Detection**: Works with Launch Detector to identify manufactured hype
- **Signal Correlation**: Contributes to collective agent confidence scoring

## Example Detection Scenario

```
Timeline: Token XYZ launch day

T+0:00 - Launch Detector flags new token creation
T+0:15 - Mirage detects coordinated wallet funding from common source
T+0:47 - Cross-DEX trades begin: 100 SOL on Raydium, 95 SOL on Orca
T+1:23 - Circular flow detected: funds routing back to origin wallets
T+2:15 - Mirage emits HIGH confidence phantom liquidity signal
T+2:16 - Swarm correlation: Launch + Phantom signals = manufactured hype alert
```

## Signal Format

```typescript
{
  agent: "Mirage",
  type: "phantom_liquidity_detected",
  glyph: "Φ",
  hash: "sig_phantom_abc123",
  timestamp: "2025-01-15T14:30:45Z",
  confidence: 0.94,
  details: {
    circularityScore: 0.87,
    crossDexCorrelation: 0.92,
    temporalCluster: "47s",
    walletClusterSize: 7,
    affectedTokens: ["TokenXYZ"],
    estimatedPhantomVolume: "1.2M SOL"
  }
}
```

## Impact & Use Cases

### For Retail Traders
- **Early Warning System**: Alerts before entering manipulated markets
- **Risk Assessment**: Confidence scores help evaluate token liquidity legitimacy
- **Exit Timing**: Detects when phantom liquidity operations are unwinding

### For Analysts & Researchers
- **Market Intelligence**: Understanding manipulation infrastructure
- **Pattern Documentation**: Building databases of known bad actors
- **Ecosystem Health**: Measuring prevalence of phantom liquidity

### For Protocols & Aggregators
- **Risk Management**: Flagging potentially manipulated markets
- **Routing Optimization**: Avoiding phantom liquidity pools
- **User Protection**: Warning systems for suspicious trading patterns

## Why Mirage Matters

Current wash trade detection tools are designed for 2021-era simple patterns. Modern phantom liquidity operations use:
- **Time delays** to break correlation detection
- **Amount variance** to avoid exact matching
- **Cross-DEX coordination** to fragment evidence
- **Infrastructure sharing** hidden across wallet clusters

Mirage's continuous observation model with persistent memory can detect these evolved patterns in real-time, protecting users from millions in potential losses to sophisticated market manipulation.

## Future Enhancements

- **ML Pattern Recognition**: Advanced behavioral clustering
- **Cross-Chain Correlation**: Ethereum/Solana phantom liquidity bridges
- **Predictive Scoring**: Forecasting phantom liquidity unwind events
- **Integration APIs**: Direct feeds to wallets and trading platforms