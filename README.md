A persistent, recoverable three-step on-chain workflow for the Pharos Agent Arena Saga Executor task. The demo approves valueless SGT, locks it in a saga escrow, and deposits it into a controlled test vault for the original owner. Separate forced-failure modes preserve normal preflight protection and provide an explicitly opt-in, receipt-verified Atlantic demonstration that mines a controlled status-0x0 deposit before compensation.

Live demo: https://pharos-saga-executor.shoupeorg.workers.dev/

Safety and network
Network: Pharos Atlantic Testnet
Chain ID: 688689
Explorer: https://atlantic.pharosscan.xyz/
Official network reference: https://docs.pharos.xyz/getting-started/network/atlantic-testnet
Official MCP source: https://github.com/PharosNetwork/pharos-mcp
Official Skill guide: https://docs.pharos.xyz/tooling-and-infrastructure/pharos-skill-engine-guide
Test token: valueless SGT; no mainnet assets or user wallet are used.
The dedicated signer is a Cloudflare Worker secret. The application exposes only its public address.
The public hosted MCP endpoint is mainnet-configured. For Atlantic, this project embeds an unmodified compiled copy of the official pharos-mcp server and RPC adapter and creates an in-memory MCP client/server transport configured with the official Atlantic RPC. Application chain operations call MCP tools only; there is no application-level direct-RPC fallback. viem signs locally on the server, and only the signed raw bytes are submitted through MCP send_raw_transaction.
