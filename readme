# Linera Microchain Visual Debugger

[![Rust](https://img.shields.io/badge/Rust-1.80%2B-brightorange?logo=rust)](https://www.rust-lang.org/)
[![Linera](https://img.shields.io/badge/Linera-Testnet%20Conway-blue?logo=linera)](https://linera.io/)
[![Hackathon](https://img.shields.io/badge/Linera%20Buildathon-Wave%201-green)](https://linera.io/buildathon)
[![License: Apache-2.0](https://img.shields.io/badge/License-Apache%202.0-yellow)](https://opensource.org/licenses/Apache-2.0)

> **A real-time debugging dashboard for Linera microchains** – Think Wireshark meets GraphQL explorer, built for the agentic Web. Visualize tx flows, chain forks, and cross-chain chaos in sub-second style. Cut debug hell from hours to minutes. 🚀

## The Problem
Linera's microchain magic (parallel user-owned chains, instant finality) is a dev dream for scalable Web3 apps like prediction markets or AI agents. But debugging? It's a nightmare: manual `linera query` spam, invisible race conditions across chains, and no easy way to trace root-chain security handshakes. In a hackathon crunch, that's lost time you can't afford.

## Enter Microchain Visual Debugger
This tool hooks into `linera-service` logs and GraphQL endpoints to deliver a live, interactive dashboard. Watch transactions ripple across microchains like a network graph, spot forks before they fork your sanity, and hot-reload app params without redeploys. Perfect for prototyping agentic flows where AI oracles need on-chain truth serum—fast.

### Key Features
- **Real-Time Visualization**: Graph tx flows, chain states, and cross-microchain messages. See parallelism shine (or snag) live.
- **Issue Surfacing**: Auto-detect race conditions, storage overflows, or consensus drifts. No more "it works on my machine" excuses.
- **Smart Queries**: One-click GraphQL generation for state diffs—e.g., "Show me oracle updates on Chain A vs. B."
- **Hot-Reload Magic**: Tweak Wasm app params mid-session; redeploy in seconds via CLI integration.
- **VS Code Extension**: Seamless sidebar integration for in-IDE debugging—query, visualize, fix, repeat.
- **Local + Testnet Ready**: Works with `linera net up` or Conway faucet chains. Export reports for team shares.

Built for the [Linera Buildathon](https://linera.io/buildathon) – Wave 1 MVP: Core dashboard + tx graphing. Scaling to AI-debug in later waves for that $50K pool. 🎯

### How It Works (High-Level)
1. **CLI Collector**: `mcdbg collect --service linera-service` tails logs and queries GraphQL for chain data.
2. **Backend Processor**: Rust crate parses events into a graph model (using petgraph for nodes/edges).
3. **Frontend Dashboard**: Svelte (or Tauri for desktop) renders interactive viz—zoom into txs, filter by chain ID, replay forks.
4. **Linera Hooks**: Leverages microchains' independence for isolated views + root-chain oversight for audits. Sub-second updates via WebSockets.

![Demo Sneak Peek](https://via.placeholder.com/800x400?text=Microchain+Graph+Demo)  
*(Coming soon: Animated tx flow across 3 microchains)*

## Tech Stack
- **Backend/CLI**: Rust + linera-sdk (Wasm hooks) + tokio (async log tailing) + petgraph (viz models)
- **Frontend**: Svelte + D3.js (graphs) or Tauri (desktop bundle)
- **Data**: GraphQL subscriptions + RocksDB snapshots for local replay
- **Extensibility**: VS Code API for plugin; open for oracle/AI integrations (e.g., debug Polymarket-style predictions)

## Quickstart
Assuming Linera Testnet Conway is running (`linera wallet init --faucet https://faucet.testnet-conway.linera.net`):

1. Clone & Build:
   ```bash
   git clone https://github.com/nanle/linera-microchain-debugger.git
   cd linera-microchain-debugger
   cargo build --release

2. Start Dashboard:
    ```bash
    cargo run -- collect --port 8080  # Hooks to your linera-service
    Open http://localhost:3000 – boom, live viz!

## ROADMAP
### Phase 1
1. CLI log collector + basic GraphQL query parser.
2. Svelte dashboard with static tx graph (D3.js nodes/edges).
3. Testnet integration: Hook to Conway faucet chain; demo counter app debug.
4. GitHub repo + demo video (under 2 mins) for Akindo submission.

### Phase 2
1. Real-time WebSocket subscriptions for live tx updates (sub-second viz).
2. Auto-issue detection: Race condition alerts + storage viz.
3. Hot-reload CLI: Param tweaks without full redeploy.
4. Local sim support: Integrate linera net up for offline testing.
5. Basic export: PNG/SVG graphs + JSON state dumps.

### Phase 3
1. VS Code extension: Sidebar panel for in-IDE graph + query gen.
2. Cross-chain message tracing: Highlight root-valley interactions.
3. Prediction market templates: Pre-built oracles for odds debugging.
4. Perf metrics: Latency heatmaps + scalability sims (100+ microchains).
5. CI/CD: GitHub Actions for testnet deploys.

### Phase 4
1. Agentic AI layer: Anomaly detection via simple ML (e.g., torch for pattern spotting in tx flows).
2. Multi-user collab: Shared sessions for team debugging (WebRTC?).
3. Desktop app: Tauri bundle for offline use.
4. Docs overhaul: Tutorials for common Linera pitfalls (e.g., Wasm storage limits).
5. Mainnet prep: Valley chain audits + security scans.