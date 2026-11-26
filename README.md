# Bifrost K-Finance, US SEC XBRL, Web3/OFAC & ISO 20022 Server (x402 + Remote MCP)

[![Bifrost K-Finance MCP connector](https://glama.ai/mcp/connectors/app.railway.up.bifrost-x402-production/bifrost-kfinance-mcp/badges/score.svg)](https://glama.ai/mcp/connectors/app.railway.up.bifrost-x402-production/bifrost-kfinance-mcp)
[![mcptry](https://mcptry.com/badge/io.github.ballostark-wq/bifrost-kfinance-mcp)](https://mcptry.com/servers/io.github.ballostark-wq/bifrost-kfinance-mcp)
[![MCPRush Tool-List Grade A](https://img.shields.io/badge/MCPRush_Tool--List-Grade_A-16a34a)](https://mcprush.com/to/bifrost-k-finance-x402-alpha-mcp?ref=badge)
[![OX.Radar MCP Security: 0/100 Risk](https://img.shields.io/badge/OX.Radar_Security_Audit-0%2F100_Risk_(Clean)-059669)](https://www.ox.security/ox-radar/mcp/io-github-ballostark-wq-bifrost-kfinance-mcp/)
[![Superstables x402 Live](https://img.shields.io/badge/x402_Bazaar_%26_Superstables-Live_HTTP_402_(20ms)-2563eb)](https://www.superstables.com/s/bifrost-x402-production.up.railway.app)
[![Listed on mcpservers.org](https://mcpservers.org/badge.svg)](https://mcpservers.org/servers/ballostark-wq/bifrost-kfinance-mcp)

[![Bifrost K-Finance & Korea Customs x402 MCP server](https://mcprush.com/badge/bifrost-k-finance-x402-alpha-mcp/card.svg)](https://mcprush.com/to/bifrost-k-finance-x402-alpha-mcp?ref=badge)

Machine-readable **Korea Customs Service HS 2–10 Digit Export/Import Series (with HSK-10 Breakdown & $/kg ASP YoY)**, **FSS OpenDART Corporate Regulatory Disclosures**, **Bank of Korea Macro/FX Yields (ECOS)**, **US SEC EDGAR XBRL Financials & Decoded Form 8-K Filings**, **US-to-Korea AI Supply-Chain Mapping**, **Base/Ethereum/Arbitrum & Solana (`Token-2022`) Pre-Swap Firewall**, **US Treasury OFAC SDN & GLEIF LEI Sanctions Gate**, **HTTPS DoH Domain/Email MX·SPF·DMARC 10-Batch Firewall**, and **Stateless ISO 20022 (`pain.001`, `pacs.008`, `camt.053`, `MT940`) Banking Bridge** — payable per request via **Coinbase x402 (`USDC` on Base Mainnet `eip155:8453`)** with zero API keys, zero subscriptions, and gasless EIP-3009 settlement.

<!-- mcp-name: io.github.ballostark-wq/bifrost-kfinance-mcp -->

## Independent Security & Directory Audits

* **OX.Radar MCP Security Audit (`0 / 100` Risk — No Rules Fired)**: `https://www.ox.security/ox-radar/mcp/io-github-ballostark-wq-bifrost-kfinance-mcp/`
* **MCPRush Independent Tool-List Grade (`Grade A`)**: `https://mcprush.com/ballostark-wq/bifrost-k-finance-x402-alpha-mcp`
* **MCPTRY Verified Quality Score (`99 / 100`)**: `https://mcptry.com/servers/io.github.ballostark-wq/bifrost-kfinance-mcp`
* **Glama Verified Remote Connector**: `https://glama.ai/mcp/connectors/app.railway.up.bifrost-x402-production/bifrost-kfinance-mcp`
* **Superstables Live x402 Uptime & Latency (`HTTP 402 · 20ms`)**: `https://www.superstables.com/s/bifrost-x402-production.up.railway.app`

## Live Discovery & Per-Call Pricing (Base Mainnet USDC)

* **Service Overview (`200 OK`)**: `https://bifrost-x402-production.up.railway.app/`
* **x402 Domain Manifest (`.well-known`)**: `https://bifrost-x402-production.up.railway.app/.well-known/x402`
* **Glama Connector Verification (`.well-known`)**: `https://bifrost-x402-production.up.railway.app/mcp/.well-known/glama.json`
* **Remote MCP Endpoint (Streamable HTTP)**: `https://bifrost-x402-production.up.railway.app/mcp`
* **AI Discovery Guide (`llms.txt`)**: `https://bifrost-x402-production.up.railway.app/llms.txt`
* **Free Customs 3M Sample (REST)**: `https://bifrost-x402-production.up.railway.app/v1/kr-customs-trade-sample`
* **Free EVM Risk Firewall Sample (REST)**: `https://bifrost-x402-production.up.railway.app/v1/evm-risk-sample`
* **Free Solana & OFAC/LEI Sample (REST)**: `https://bifrost-x402-production.up.railway.app/v1/solana-and-sanctions-sample`
* **Free ISO 20022 Spec Sample (REST)**: `https://bifrost-x402-production.up.railway.app/v1/iso20022-sample`
* **OpenAPI Spec**: `https://bifrost-x402-production.up.railway.app/openapi.json`
* **Health & Readiness**: `https://bifrost-x402-production.up.railway.app/health`

| Route / MCP Tool | Price (USDC) | Data Source & Signal Output |
| :--- | :--- | :--- |
| MCP `kr_free_sample_and_x402_guide` | **`$0.00` (Free)** | Instant 3-month Korea Customs export/ASP preview (`AI_MEMORY_HBM`, `POWER_TRANSFORMERS`, `K_BEAUTY_SKINCARE`, `DEFENSE_ARMORED`, etc.) + copy-paste TypeScript/Python `x402` autonomous client snippets. |
| `POST /v1/kr-customs-trade-snapshot` (`kr_customs_trade_snapshot`) | `$0.025` | **Korea Customs Service** 24M monthly export/import series across 6 core K-export themes or any 2–10 digit HS/HSK code, with HSK-10 sub-item share breakdown, unit export ASP (`$/kg`) & ASP YoY%, 3M MA, and mapped KRX tickers. |
| `POST /v1/kr-disclosure-radar` (`kr_disclosure_radar`) | `$0.06` | Live **FSS OpenDART** KRX corporate filings translated into structured English alpha signals (`BUYBACK_BULLISH`, `CONTRACT_WIN_BULLISH`, `RIGHTS_ISSUE_DILUTION_BEARISH`). |
| `POST /v1/kr-catalyst-brief` (`kr_catalyst_brief`) | `$0.08` | Cross-border **US-to-Korea supply-chain mapping** (`NVDA`, `MU`, `MSFT`, `TSLA`, `AAPL`, `LLY`, `LMT`, `AVGO` -> Tier-1 KRX HBM, transformer, CDMO & defense beneficiaries) + daily refreshed Korea export/macro catalyst calendar. |
| `POST /v1/kr-macro-pulse` (`kr_macro_pulse`) | `$0.05` | Live **Bank of Korea ECOS** policy base rate, `USD/KRW` & `JPY/KRW` FX rates, KTB 3Y/10Y sovereign yields, term spread in bps, and exporter FX regime. |
| `POST /v1/us-sec-xbrl-radar` (`us_sec_xbrl_radar`) | `$0.030` | Official **US SEC EDGAR** submissions, decoded Form 8-K material event items, US-GAAP/IFRS XBRL YoY financials, and mapped K-Supply-Chain peers. |
| `POST /v1/evm-token-verdict` (`evm_token_verdict`) | `$0.015` | Pre-swap **Base (8453), Ethereum (1) & Arbitrum (42161) ERC-20 Token Verdict**: detects live honeypot sell blocks, EIP-1967 proxies, `mint`/`blacklist`/`setTax` bytecode selectors, Sourcify verification, and DEX pool liquidity. |
| `POST /v1/evm-spender-firewall` (`evm_spender_firewall`) | `$0.02` | Pre-signature **EVM Approve, Permit2 & Router Spender Firewall**: inspects spender bytecode & calldata for unverified drainers, unlimited `MAX_UINT256` grants, `SELFDESTRUCT`, and proxy traps (`ALLOW / WARN / BLOCK`). |
| `POST /v1/solana-token-verdict` (`solana_token_verdict`) | `$0.015` | Pre-swap **Solana SPL & `Token-2022` Rug & Extension Verdict**: detects `PermanentDelegate` seizure hooks, `TransferHook`/`TransferFee` traps, live mint/freeze authorities, holder clusters, and DEX liquidity (paid in Base USDC). |
| `POST /v1/counterparty-sanctions-lei` (`counterparty_sanctions_lei_check`) | `$0.025` | Pre-payment **US Treasury OFAC SDN, Crypto Wallet & GLEIF LEI Compliance Gate**: screens entities, strong AKAs, and sanctioned wallets plus live GLEIF Level 1/2 parent hierarchy and EU VIES VAT. |
| `POST /v1/domain-email-guard` (`domain_email_guard`) | `$0.015` | 1–10 domain batch **HTTPS DoH MX/Null-MX, SPF/DMARC anti-spoofing, DNSSEC**, disposable mail, and RDAP domain-age firewall. |
| `POST /v1/iso20022-generate-pain001` (`iso20022_generate_pain001`) | `$0.04` | Stateless JSON-to-**ISO 20022 `pain.001.001.09`** XML generator with exact Decimal `CtrlSum`, Swiss SPS 2026 & EPC SEPA structured addresses, IBAN Mod-97, and SCOR/QRR validation (`0 Bytes` retention). |
| `POST /v1/iso20022-audit-and-parse` (`iso20022_audit_and_parse`) | `$0.03` | Deterministic XPath compliance auditor & JSON normalizer for **`pain.001`, `pacs.008`, and `camt.053`** XML (SPS 2026 structured address, IBAN Mod-97, Swiss QR-IBAN/QRR, exact balance reconciliation). |
| `POST /v1/mt940-to-camt053-bridge` (`mt940_to_camt053_bridge`) | `$0.03` | Legacy **SWIFT `MT940` to ISO 20022 `camt.053.001.08`** XML & JSON statement converter with SEPA `:86:` tag extraction and lossless `raw_narrative` preservation. |
| `POST /v1/clean-context` (`clean_context`) | `$0.015` | Deterministic HTML-to-Markdown context cleaner cutting LLM prompt token bloat by 60–85%. |
| `POST /v1/preflight` (`preflight_validate`) | `$0.005` | Pre-execution validator for JSON payloads, required keys, 5-field POSIX cron schedules, regex ReDoS safety, and SSRF-safe HTTPS targets. |

## Zero-Charge Buyer Protections

* **400 before 402**: Malformed JSON or invalid HS/country/IBAN/EOA parameters return `HTTP 400` prior to issuing a payment challenge.
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
* US corporate filings and XBRL facts sourced from **U.S. Securities and Exchange Commission EDGAR** (`data.sec.gov`).
* Sanctions and legal entity records sourced from **U.S. Treasury OFAC SLS** (`ofac.treasury.gov`) and **GLEIF** (`api.gleif.org`).
