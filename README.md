# Bifrost K-Finance & Agent Utility Server (x402 + Remote MCP)

Real-time **Korean Corporate Regulatory Disclosures (FSS OpenDART)**, **Bank of Korea Macro/FX Yields (ECOS)**, **US-to-Korea Semiconductor/Power-Grid Supply-Chain Alpha**, and **Deterministic Agent Guardrails** — payable per request via **Coinbase x402 (`USDC` on Base Mainnet `eip155:8453`)** with zero API keys, zero subscriptions, and gasless EIP-3009 settlement.

<!-- mcp-name: io.github.ballostark-wq/bifrost-kfinance-mcp -->

## Live Endpoints & Per-Call Pricing (Base Mainnet USDC)

- **Base URL**: `https://bifrost-x402-production.up.railway.app`
- **Remote MCP Endpoint (Streamable HTTP)**: `https://bifrost-x402-production.up.railway.app/mcp`
- **OpenAPI Spec**: `https://bifrost-x402-production.up.railway.app/openapi.json`
- **Health & Live Data Status**: `https://bifrost-x402-production.up.railway.app/health`

| Route / MCP Tool | Price (USDC) | Data Source & Signal Output |
| :--- | :--- | :--- |
| `POST /v1/kr-disclosure-radar` (`kr_disclosure_radar`) | `$0.06` | Live **FSS OpenDART** KRX corporate filings translated into structured English alpha signals (`BUYBACK_BULLISH`, `SUPPLY_CONTRACT_BULLISH`, `DILUTION_BEARISH`). |
| `POST /v1/kr-macro-pulse` (`kr_macro_pulse`) | `$0.05` | Live **Bank of Korea ECOS** policy base rate, `USD/KRW` & `JPY/KRW` FX rates, KTB 3Y/10Y sovereign yields, term spread in bps, and exporter FX regime. |
| `POST /v1/kr-catalyst-brief` (`kr_catalyst_brief`) | `$0.08` | Cross-border **US-to-Korea supply-chain mapping** (`NVDA`, `MU`, `MSFT`, `TSLA`, `AAPL`, `LLY`, `LMT` -> Tier-1 KRX HBM, transformer, CDMO & defense beneficiaries) + daily refreshed Korea export/macro catalyst calendar. |
| `POST /v1/clean-context` (`clean_context`) | `$0.015` | Deterministic HTML-to-Markdown context cleaner cutting LLM prompt token bloat by 60–85%. |
| `POST /v1/preflight` (`preflight_validate`) | `$0.005` | Pre-execution validator for JSON payloads, required keys, 5-field POSIX cron schedules, and SSRF-safe HTTPS targets. |

## Quick Connect: Remote MCP Configuration

### JSON Config (Claude Desktop / Cursor / Windsurf)
```json
{
  "mcpServers": {
    "bifrost-kfinance": {
      "type": "streamable-http",
      "url": "https://bifrost-x402-production.up.railway.app/mcp"
    }
  }
}
```

### TOML Config (OpenAI Codex CLI)
```toml
[mcp_servers.bifrost_kfinance]
url = "https://bifrost-x402-production.up.railway.app/mcp"
```

## Quick Call: Autonomous x402 Python Client (Base Mainnet)

```python
import asyncio
import os
from eth_account import Account
from x402 import x402Client
from x402.http.clients import x402HttpxClient
from x402.mechanisms.evm import EthAccountSigner
from x402.mechanisms.evm.exact import ExactEvmScheme

async def fetch_korea_alpha() -> None:
    signer = EthAccountSigner(Account.from_key(os.environ["EVM_PRIVATE_KEY"]))
    client = x402Client()
    client.register("eip155:8453", ExactEvmScheme(signer))

    async with x402HttpxClient(client, timeout=30.0) as session:
        r = await session.request(
            "POST",
            "https://bifrost-x402-production.up.railway.app/v1/kr-macro-pulse",
            json={"include_yield_curve": True, "fx_pairs": ["USDKRW", "JPYKRW"]},
        )
        print((await r.aread()).decode("utf-8"))

asyncio.get_event_loop().run_until_complete(fetch_korea_alpha())
```

## Data Attribution & Compliance
- Korean corporate filing metadata sourced live from **Financial Supervisory Service OpenDART** (`opendart.fss.or.kr`).
- Korean macroeconomic and FX statistics sourced live from **Bank of Korea ECOS** (`ecos.bok.or.kr`), distributed with explicit source attribution under Bank of Korea statistical terms.
