# Bifrost K-Finance & Korea Customs Trade Server (x402 + Remote MCP)

[![Bifrost K-Finance MCP connector](https://glama.ai/mcp/connectors/app.railway.up.bifrost-x402-production/bifrost-kfinance-mcp/badges/score.svg)](https://glama.ai/mcp/connectors/app.railway.up.bifrost-x402-production/bifrost-kfinance-mcp)
[![Listed on mcpservers.org](https://mcpservers.org/badge.svg)](https://mcpservers.org/servers/ballostark-wq/bifrost-kfinance-mcp)

Machine-readable **Korea Customs Service HS 2–10 Digit Export/Import Series (with HSK-10 Breakdown & $/kg ASP YoY)**, **FSS OpenDART Corporate Regulatory Disclosures**, **Bank of Korea Macro/FX Yields (ECOS)**, and **US-to-Korea AI Supply-Chain Mapping** — payable per request via **Coinbase x402 (`USDC` on Base Mainnet `eip155:8453`)** with zero API keys, zero subscriptions, and gasless EIP-3009 settlement.

<!-- mcp-name: io.github.ballostark-wq/bifrost-kfinance-mcp -->

## Live Discovery & Per-Call Pricing (Base Mainnet USDC)

* **Service Overview (`200 OK`)**: `https://bifrost-x402-production.up.railway.app/`
* **x402 Domain Manifest (`.well-known`)**: `https://bifrost-x402-production.up.railway.app/.well-known/x402`
* **Remote MCP Endpoint (Streamable HTTP)**: `https://bifrost-x402-production.up.railway.app/mcp`
* **AI Discovery Guide (`llms.txt`)**: `https://bifrost-x402-production.up.railway.app/llms.txt`
* **Free Customs 3M Sample (REST)**: `https://bifrost-x402-production.up.railway.app/v1/kr-customs-trade-sample`
* **OpenAPI Spec**: `https://bifrost-x402-production.up.railway.app/openapi.json`
* **Health & Readiness**: `https://bifrost-x402-production.up.railway.app/health`

| Route / MCP Tool | Price (USDC) | Data Source & Signal Output |
| :--- | :--- | :--- |
| MCP `kr_free_sample_and_x402_guide` | **`$0.00` (Free)** | Instant 3-month Korea Customs export/ASP preview (`AI_MEMORY_HBM`, `POWER_TRANSFORMERS`, `K_BEAUTY_SKINCARE`, `DEFENSE_ARMORED`, etc.) + copy-paste TypeScript/Python `x402` autonomous client snippets. |
| `POST /v1/kr-customs-trade-snapshot` (`kr_customs_trade_snapshot`) | `$0.025` | **Korea Customs Service** 24M monthly export/import series across 6 core K-export themes or any 2–10 digit HS/HSK code, with HSK-10 sub-item share breakdown, unit export ASP (`$/kg`) & ASP YoY%, 3M MA, and mapped KRX tickers. |
| `POST /v1/kr-disclosure-radar` (`kr_disclosure_radar`) | `$0.06` | Live **FSS OpenDART** KRX corporate filings translated into structured English alpha signals (`BUYBACK_BULLISH`, `CONTRACT_WIN_BULLISH`, `RIGHTS_ISSUE_DILUTION_BEARISH`). |
| `POST /v1/kr-catalyst-brief` (`kr_catalyst_brief`) | `$0.08` | Cross-border **US-to-Korea supply-chain mapping** (`NVDA`, `MU`, `MSFT`, `TSLA`, `AAPL`, `LLY`, `LMT`, `AVGO` -> Tier-1 KRX HBM, transformer, CDMO & defense beneficiaries) + daily refreshed Korea export/macro catalyst calendar. |
| `POST /v1/kr-macro-pulse` (`kr_macro_pulse`) | `$0.05` | Live **Bank of Korea ECOS** policy base rate, `USD/KRW` & `JPY/KRW` FX rates, KTB 3Y/10Y sovereign yields, term spread in bps, and exporter FX regime. |
| `POST /v1/clean-context` (`clean_context`) | `$0.015` | Deterministic HTML-to-Markdown context cleaner cutting LLM prompt token bloat by 60–85%. |
| `POST /v1/preflight` (`preflight_validate`) | `$0.005` | Pre-execution validator for JSON payloads, required keys, 5-field POSIX cron schedules, regex ReDoS safety, and SSRF-safe HTTPS targets. |

## Zero-Charge Buyer Protections

* **400 before 402**: Malformed JSON or invalid HS/country parameters return `HTTP 400` prior to issuing a payment challenge.
* **503 Fail-Closed Settlement**: Upstream public API outages return `HTTP 503` without settling payment (zero synthetic fallback data on paid routes).

## Quick Connect: Remote MCP Configuration

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

## Quick Connect: Autonomous x402 Payment (`@coinbase/cdp-sdk`)

```typescript
import { CdpX402Client } from "@coinbase/cdp-sdk/x402";
import { wrapFetchWithPayment } from "@x402/fetch";

const fetch402 = wrapFetchWithPayment(fetch, new CdpX402Client());
const res = await fetch402("https://bifrost-x402-production.up.railway.app/v1/kr-customs-trade-snapshot", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ theme: "AI_MEMORY_HBM", partner: "US", months: 24 }),
});
console.log(await res.json());
```

## Official Data Attribution

* Trade statistics sourced from **Korea Customs Service OpenAPI** (`data.go.kr/data/15100475`).
* Corporate filings sourced from **Financial Supervisory Service OpenDART** (`opendart.fss.or.kr`).
* Macroeconomic and FX statistics sourced from **Bank of Korea ECOS** (`ecos.bok.or.kr`).
