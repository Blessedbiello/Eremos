# Eremos - Mirage Agent

![Eremos](docs/banner2.png)

**Phantom Liquidity Hunter - Agent Φ (Mirage)**

Mirage is an Eremos swarm agent designed to detect sophisticated phantom liquidity operations on Solana. Unlike traditional wash trade detection that focuses on simple patterns, Mirage identifies complex circular flows, cross-DEX coordination, and temporal clustering that sophisticated actors use to create the illusion of organic trading volume.

---

<p align="center">
  <img src="docs/therontphd2.png" alt="Agent Mirage" width="155"/><br/>
  <em>Mirage - Agent Φ (Phantom Liquidity Hunter)</em>
</p>

**Meet Mirage - Agent Φ**  
The phantom liquidity hunter. Real-time cross-DEX correlation analysis.  
Exposing sophisticated market manipulation as it happens.

---

## Mirage Detection Features

- **Circular Flow Analysis** - Tracks fund movements through wallet networks and identifies when funds return to origin within 72-hour windows
- **Cross-DEX Correlation** - Real-time monitoring of simultaneous trading patterns across Raydium, Orca, and Jupiter  
- **Temporal Clustering** - Flags coordinated trades occurring within <60 seconds across wallet clusters
- **Wallet Infrastructure Mapping** - Identifies shared fee payers and common funding sources across supposedly independent wallets
- **Persistent Memory** - Maintains 72-hour rolling windows and weeks-long wallet relationship tracking
- **Swarm Intelligence** - Shares wallet cluster data with other Eremos agents for collaborative detection


---

## Example Detection

Mirage detecting phantom liquidity operation in real-time:

```ts
[agent-mirage] → circular flow detected: 100 SOL through wallet A→B→C (Raydium)
[agent-mirage] → correlation spike: 95 SOL through wallet D→E→F (Orca) +47s
[agent-mirage] → shared fee payer identified across clusters
[agent-mirage] → funds returning to origin within 72h window
[agent-mirage] → phantom liquidity confidence (0.94) - emitting signal

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
    estimatedPhantomVolume: "1.2M SOL"
  }
}
```

---

## Detection Methodology

Mirage emits HIGH confidence signals when detecting:
- **Circularity scores >0.8** - Funds returning to origin through complex paths
- **Cross-DEX correlation >0.9** - Synchronized trading across multiple DEXs  
- **Temporal clustering <60s** - Coordinated "independent" trades
- **Shared infrastructure** - Common fee payers across wallet clusters

The agent maintains persistent memory of SPL token account lifecycles and builds real-time correlation matrices to expose sophisticated phantom liquidity operations that traditional tools miss.

---

## Tech Stack

- **Frontend:** Next.js, Tailwind CSS
- **Backend:** Node.js (TypeScript-based agent runner)
- **Language:** TypeScript (typed logic across agents, utils, and infra)
- **Chain Layer:** RPC watchers, mempool filters, native triggers

---

## Getting Started

```bash
git clone https://github.com/EremosCore/Eremos.git
cd Eremos
npm install
```

Set up your environment:

```bash
cp .env.example .env.local
npm run dev
```

---

## Why Mirage Matters

Current wash trade detection tools are designed for 2021-era simple patterns. Modern phantom liquidity operations use:
- **Time delays** to break correlation detection
- **Amount variance** to avoid exact matching  
- **Cross-DEX coordination** to fragment evidence
- **Infrastructure sharing** hidden across wallet clusters

Mirage's continuous observation model with persistent memory can detect these evolved patterns in real-time, protecting users from millions in potential losses to sophisticated market manipulation.

## Key Folders

- `/agents` - Agent templates + logic (including Mirage specifications)
- `/utils` - Shared signal/logging utilities  
- `/types` - TypeScript interfaces + definitions  
- `/scripts` - Bootstrap and dev scripts  
- `/docs` - Swarm structure, architecture, & signal taxonomy

---

## Contributing

We’re open to contributors.  
If you are experienced in TypeScript and like agent-based systems, check `example.ts` and build your own observer.
If you're a designer, artist, or just have ideas that fit the mythos - send us a DM on Twitter. [@EremosCore](https://x.com/EremosCore)

---

## License

MIT © Eremos

---

## Links

- **Twitter/X:** [@EremosCore](https://x.com/EremosCore)
- **Website:** [Eremos.io](https://www.eremos.io/)
- **Whitepaper:** [v1.0 PDF](docs/whitepaper.pdf)

_Maintained by the Eremos Core team 💛._
