# Bank of Jamaica Exchange Rates API — bank-of-jamaica-exchange-rate

[![npm version](https://img.shields.io/npm/v/bank-of-jamaica-exchange-rate.svg)](https://www.npmjs.com/package/bank-of-jamaica-exchange-rate)
[![license](https://img.shields.io/npm/l/bank-of-jamaica-exchange-rate.svg)](https://github.com/AllRates-Today/bank-of-jamaica-exchange-rate/blob/main/LICENSE)
[![zero dependencies](https://img.shields.io/badge/dependencies-0-brightgreen.svg)](https://www.npmjs.com/package/bank-of-jamaica-exchange-rate)
[![TypeScript](https://img.shields.io/badge/TypeScript-types%20included-3178C6.svg)](https://www.typescriptlang.org/)
[![USD/JMD today](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fbojm%3Fsource%3DUSD%26target%3DJMD&query=%24.rate&label=USD%2FJMD%20published%20by%20Bank%20of%20Jamaica&color=0A7E8C&cacheSeconds=3600)](https://allratestoday.com/central-bank-rates-api/bojm/)
[![rate date](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fbojm%3Fsource%3DUSD%26target%3DJMD&query=%24.rate_date&label=rate%20date&color=555&cacheSeconds=3600)](https://allratestoday.com/central-bank-rates-api/bojm/)

**Official Bank of Jamaica (Jamaica) daily exchange rates for Node.js and TypeScript. The published central bank rates behind tax filings, customs valuations, audits, and compliant invoicing — not market estimates, but the numbers Bank of Jamaica itself prints, every business day.**

## 🚀 Why this client?

- 🏛️ **Official published rates** — Bank of Jamaica's own table, with the publisher's own `rate_date` on every response
- 📅 **History back to 2000** — point-in-time tables and daily series for any past date
- 🔀 **Published vs derived, always flagged** — computed inverse/cross pairs carry `derived: true`, never mixed with official prints
- ⚡ **Zero dependencies** — pure ESM + CJS over global `fetch`; Node 18+, Bun, Deno, and edge runtimes
- 🔷 **Type-safe** — full TypeScript definitions shipped with the package
- 🧾 **Compliance-grade metadata** — `rate_type`, publication date, and source disclaimer on every response

> **Official rate, not mid-market:** every value here is a number Bank of Jamaica itself published, fixed once printed and carrying the central bank's own `rate_date` — what filings and audits require. Need the live mid-market rate for pricing or display instead? Use the [mid-market API](https://allratestoday.com/docs/) or [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk). The two can diverge by several percent.

## ⚡ Try it without a key

The latest Bank of Jamaica table is also served keyless, CORS-open and edge-cached, for evaluation, embeds and AI agents:

```bash
curl "https://allratestoday.com/api/open/central-bank/bojm?source=USD&target=JMD"
```

```js
const r = await fetch('https://allratestoday.com/api/open/central-bank/bojm').then((x) => x.json());
console.log(r.rate_date, r.rates.length); // the central bank's latest published table, no key
```

The open endpoint serves the *latest* table only and asks for a visible attribution link. The client below uses the keyed API, which adds point-in-time tables, history, and CSV/XML/Excel output.

## 📈 Latest published table

Today's full Bank of Jamaica table, straight from the central bank's latest publication. On GitHub it is refreshed by [a daily Action](.github/workflows/daily-table.yml) that reads the keyless endpoint above and commits only when the central bank publishes a new table; the copy on npm is as of the package's publish date.

<!-- daily-table:start -->
Published **2026-10-09** by Bank of Jamaica — 246 rates, first 60 shown. Updated 2026-10-09.

| Base | Quote | Type | Rate |
| --- | --- | --- | ---: |
| AED | JMD | buy | 43.14759 |
| AED | JMD | sell | 43.5172 |
| ALL | JMD | buy | 1.93611 |
| ALL | JMD | sell | 1.95269 |
| AOA | JMD | buy | 0.17281 |
| AOA | JMD | sell | 0.17429 |
| ARS | JMD | buy | 0.10431 |
| ARS | JMD | sell | 0.1052 |
| AUD | JMD | buy | 110.33495 |
| AUD | JMD | sell | 111.28011 |
| AWG | JMD | buy | 88.53089 |
| AWG | JMD | sell | 89.28927 |
| AZN | JMD | buy | 93.14933 |
| AZN | JMD | sell | 93.94727 |
| BAM | JMD | buy | 90.81132 |
| BAM | JMD | sell | 91.58924 |
| BBD | JMD | buy | 79.23515 |
| BBD | JMD | sell | 79.9139 |
| BDT | JMD | buy | 1.28524 |
| BDT | JMD | sell | 1.29625 |
| BGN | JMD | buy | 90.81132 |
| BGN | JMD | sell | 91.58924 |
| BHD | JMD | buy | 420.06706 |
| BHD | JMD | sell | 423.66547 |
| BIF | JMD | buy | 0.05282 |
| BIF | JMD | sell | 0.05328 |
| BMD | JMD | buy | 158.4703 |
| BMD | JMD | sell | 159.8278 |
| BND | JMD | buy | 123.70827 |
| BND | JMD | sell | 124.76799 |
| BOB | JMD | buy | 13.37302 |
| BOB | JMD | sell | 13.48758 |
| BRL | JMD | buy | 31.61818 |
| BRL | JMD | sell | 31.88903 |
| BSD | JMD | buy | 158.4703 |
| BSD | JMD | sell | 159.8278 |
| BTN | JMD | buy | 1.63732 |
| BTN | JMD | sell | 1.65135 |
| BWP | JMD | buy | 11.11669 |
| BWP | JMD | sell | 11.21192 |
| BZD | JMD | buy | 79.23515 |
| BZD | JMD | sell | 79.9139 |
| CAD | JMD | buy | 112.347 |
| CAD | JMD | sell | 112.5561 |
| CDF | JMD | buy | 0.06831 |
| CDF | JMD | sell | 0.06889 |
| CHF | JMD | buy | 190.27472 |
| CHF | JMD | sell | 191.90466 |
| CLP | JMD | buy | 0.16159 |
| CLP | JMD | sell | 0.16297 |
| CNY | JMD | buy | 23.63623 |
| CNY | JMD | sell | 23.83871 |
| COP | JMD | buy | 0.04914 |
| COP | JMD | sell | 0.04956 |
| CRC | JMD | buy | 0.34714 |
| CRC | JMD | sell | 0.35012 |
| CUP | JMD | buy | 6.60293 |
| CUP | JMD | sell | 6.65949 |
| CZK | JMD | buy | 7.28507 |
| CZK | JMD | sell | 7.34748 |

[Full table on the Bank of Jamaica rates page](https://allratestoday.com/central-bank-rates-api/bojm/) · Source: [Official rates published by BOJM, served by AllRatesToday](https://allratestoday.com/central-bank-rates-api/bojm/). Rates are as printed by the central bank; AllRatesToday is not affiliated with it.
<!-- daily-table:end -->

## 🔑 Get your API key

Get a free API key at [allratestoday.com/register](https://allratestoday.com/register) — no credit card required. Latest rates are on every plan, including free.

## 📦 Installation

```bash
npm install bank-of-jamaica-exchange-rate
```

```bash
yarn add bank-of-jamaica-exchange-rate
```

```bash
pnpm add bank-of-jamaica-exchange-rate
```

Requires Node 18+ (global `fetch`); also runs on Bun, Deno and edge runtimes. Also published under the org scope as [`@allratestoday/bank-of-jamaica-exchange-rate`](https://www.npmjs.com/package/@allratestoday/bank-of-jamaica-exchange-rate) — same code, same versions.

## 🏁 Quick start

```js
import { getRate } from 'bank-of-jamaica-exchange-rate';

const pair = await getRate('USD', 'JMD', { apiKey: 'art_live_...' });
console.log(pair.rate, pair.rate_date); // the official Bank of Jamaica rate, on the central bank's own date
```

## 📚 API reference

- [Latest pair rate](#latest-pair-rate) — one pair from the latest published table
- [Full published table](#full-published-table) — everything the central bank printed, in one call
- [Table for a date](#table-for-a-date) — the official table for an invoice or filing date
- [Daily time series](#daily-time-series) — one pair across a date range

---

### Latest pair rate

Free plan and up. Pairs the central bank does not print directly are resolved from its table and flagged (see *Published vs derived rates* below).

```js
const pair = await getRate('USD', 'JMD', { apiKey: 'art_live_...' });
```

**Response:**

```javascript
{
  bank: 'bojm',
  name: 'Bank of Jamaica',
  rate_date: '2026-10-08',   // Bank of Jamaica's own publication date
  source: 'USD',
  target: 'JMD',
  rate: 159.7833,
  rate_type: 'sell',
  derived: false,
  method: 'published',
  disclaimer: 'Official rates as published by the named central bank. On weekends/holidays the most recent published rate_date is returned.'
}
```

### Full published table

Free plan and up. The complete table for the latest publication date.

```js
import { getLatestRates } from 'bank-of-jamaica-exchange-rate';

const table = await getLatestRates({ apiKey: 'art_live_...' });
console.log(table.rate_date, table.rates.length);
```

**Response:**

```javascript
{
  bank: 'bojm',
  name: 'Bank of Jamaica',
  rate_date: '2026-10-08',
  rates: [
    { "base": "USD", "quote": "JMD", "type": "sell", "value": 159.7833 },
    { "base": "USD", "quote": "JMD", "type": "buy", "value": 157.7876 },
    // … the rest of the published table (123 currencies vs JMD)
  ],
  disclaimer: '…'
}
```

### Table for a date

Paid plans. The official table for any date since 2000 — weekends and holidays return the most recent published date, flagged via `published_on_requested_date`, which is exactly the in-force rate a filing needs.

```js
import { getRatesForDate } from 'bank-of-jamaica-exchange-rate';

const day = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...' });
// Optionally narrow to one pair:
const one = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...', source: 'USD', target: 'JMD' });
```

**Response:**

```javascript
{
  bank: 'bojm',
  requested_date: '2026-06-30',
  rate_date: '2026-06-30',                // the date actually published
  published_on_requested_date: true,      // false when a weekend/holiday fell back
  rates: [ /* the full table for that date */ ],
  disclaimer: '…'
}
```

### Daily time series

Paid plans. One resolved rate per publication date — ready for charting, revaluation runs, or audit workpapers.

```js
import { getHistory } from 'bank-of-jamaica-exchange-rate';

const series = await getHistory(
  { source: 'USD', target: 'JMD', from: '2026-01-01', to: '2026-10-08' },
  { apiKey: 'art_live_...' }
);
```

**Response:**

```javascript
{
  bank: 'bojm',
  source: 'USD',
  target: 'JMD',
  from: '2026-01-01',
  to: '2026-10-08',
  count: 152,
  rates: [
    // one entry per publication date
    { date: '2026-10-08', rate: 159.7833, rate_type: 'sell', derived: false, method: 'published' },
    // …
  ],
  disclaimer: '…'
}
```

Pass `{ symbol: 'USD' }` instead of `source`/`target` to get the raw published rows for one currency (all rate types, no pair resolution).

---

## 🗺️ Currencies covered

Bank of Jamaica currently publishes rates covering **123 currencies** against the JMD (as of the latest table):

🇦🇪 `AED` · 🇦🇱 `ALL` · 🇦🇴 `AOA` · 🇦🇷 `ARS` · 🇦🇺 `AUD` · 🇦🇼 `AWG` · 🇦🇿 `AZN` · 🇧🇦 `BAM` · 🇧🇧 `BBD` · 🇧🇩 `BDT` · 🇧🇬 `BGN` · 🇧🇭 `BHD` · 🇧🇮 `BIF` · 🇧🇲 `BMD` · 🇧🇳 `BND` · 🇧🇴 `BOB` · 🇧🇷 `BRL` · 🇧🇸 `BSD` · 🇧🇹 `BTN` · 🇧🇼 `BWP` · 🇧🇿 `BZD` · 🇨🇦 `CAD` · 🇨🇩 `CDF` · 🇨🇭 `CHF` · 🇨🇱 `CLP` · 🇨🇳 `CNY` · 🇨🇴 `COP` · 🇨🇷 `CRC` · 🇨🇺 `CUP` · 🇨🇿 `CZK` · 🇩🇰 `DKK` · 🇩🇴 `DOP` · 🇩🇿 `DZD` · 🇪🇬 `EGP` · 🇪🇹 `ETB` · 🇪🇺 `EUR` · 🇫🇯 `FJD` · 🇬🇧 `GBP` · 🇬🇪 `GEL` · 🇬🇭 `GHS` · 🇬🇮 `GIP` · 🇬🇲 `GMD` · 🇬🇳 `GNF` · 🇬🇹 `GTQ` · 🇬🇾 `GYD` · 🇭🇰 `HKD` · 🇭🇳 `HNL` · 🇭🇹 `HTG` · 🇭🇺 `HUF` · 🇮🇩 `IDR` · 🇮🇱 `ILS` · 🇮🇳 `INR` · 🇮🇸 `ISK` · 🇯🇴 `JOD` · 🇯🇵 `JPY` · 🇰🇪 `KES` · 🇰🇬 `KGS` · 🇰🇲 `KMF` · 🇰🇷 `KRW` · 🇰🇼 `KWD` · 🇰🇾 `KYD` · 🇰🇿 `KZT` · 🇱🇧 `LBP` · 🇱🇰 `LKR` · 🇱🇸 `LSL` · 🇲🇦 `MAD` · 🇲🇩 `MDL` · 🇲🇬 `MGA` · 🇲🇰 `MKD` · 🇲🇳 `MNT` · 🇲🇴 `MOP` · 🇲🇺 `MUR` · 🇲🇻 `MVR` · 🇲🇼 `MWK` · 🇲🇽 `MXN` · 🇲🇾 `MYR` · 🇲🇿 `MZN` · 🇳🇦 `NAD` · 🇳🇬 `NGN` · 🇳🇮 `NIO` · 🇳🇴 `NOK` · 🇳🇵 `NPR` · 🇳🇿 `NZD` · 🇴🇲 `OMR` · 🇵🇦 `PAB` · 🇵🇪 `PEN` · 🇵🇬 `PGK` · 🇵🇭 `PHP` · 🇵🇰 `PKR` · 🇵🇱 `PLN` · 🇵🇾 `PYG` · 🇶🇦 `QAR` · 🇷🇴 `RON` · 🇷🇸 `RSD` · 🇷🇺 `RUB` · 🇷🇼 `RWF` · 🇸🇦 `SAR` · 🇸🇧 `SBD` · 🇸🇨 `SCR` · 🇸🇪 `SEK` · 🇸🇬 `SGD` · 🇸🇷 `SRD` · 🇸🇿 `SZL` · 🇹🇭 `THB` · 🇹🇳 `TND` · 🇹🇴 `TOP` · 🇹🇷 `TRY` · 🇹🇹 `TTD` · 🇹🇼 `TWD` · 🇹🇿 `TZS` · 🇺🇦 `UAH` · 🇺🇬 `UGX` · 🇺🇸 `USD` · 🇺🇾 `UYU` · 🇺🇿 `UZS` · 🇻🇳 `VND` · 🇻🇺 `VUV` · 🇼🇸 `WST` · `XCD` · `XPF` · 🇾🇪 `YER` · 🇿🇦 `ZAR` · 🇿🇲 `ZMW`

## 🏛️ Source

The Bank of Jamaica publishes daily indicative buying and selling rates for well over a hundred currencies against the Jamaican dollar, built from authorized dealers' trading. It is the island's official reference in a heavily remittance-driven economy, with the daily series reaching back to 2000.

- Publisher's own page: [Indicative exchange rates](https://boj.org.jm/market/foreign-exchange/indicative-rates/) · [boj.org.jm](https://boj.org.jm)
- Publication: every business day; the exact schedule, freshness status and any current delay are on the [Bank of Jamaica rates page](https://allratestoday.com/central-bank-rates-api/bojm/)
- Values are stored unmodified, with the publisher's own `rate_date` on every row — see the [methodology](https://allratestoday.com/official-rates-methodology/)

## 🧭 Reading the numbers

- `value` is always **quote currency per 1 unit of base currency** (`base: "EUR", quote: "USD", value: 1.15` means 1 EUR = 1.15 USD).
- Bank of Jamaica quotes **JMD per 1 unit of foreign currency** (e.g. `base: "USD", quote: "JMD"` means JMD per one US dollar).
- Need the other way round? Ask `getRate(target, source)` and the API inverts or crosses for you, flagged `derived: true` — never divide a published rate yourself in a compliance workflow.
- `rate_type` tells you which of the central bank's series a row belongs to (`sell` here); some publishers print buy/sell or several fixings for the same pair.

## 🧩 ERP & accounting systems

Loading the official Bank of Jamaica rate into an accounting system is a supported workflow, not a hack. Step-by-step guides with the direction each system expects:

- [Dynamics 365 Business Central](https://allratestoday.com/docs/integrations/business-central/) — built-in Currency Exchange Rate Service, no code
- [Xero](https://allratestoday.com/docs/integrations/xero/) · [QuickBooks Online](https://allratestoday.com/docs/integrations/quickbooks/) · [SAP S/4HANA and ECC](https://allratestoday.com/docs/integrations/sap/) · [Odoo](https://allratestoday.com/docs/integrations/odoo/)

The same keyed endpoints return `?format=csv`, `?format=xml` and `?format=xlsx`, and accept the key as `?api_key=` on the URL for importers that cannot send headers:

```bash
curl "https://allratestoday.com/api/v1/central-bank/bojm/latest?format=xml&api_key=art_live_..."
```

## 🤖 AI agents

- MCP server: `npx -y @allratestoday/central-bank-mcp` (stdio) or the hosted endpoint `https://allratestoday.com/api/mcp` — tools for official rates, history, cross-bank comparison and publication calendars
- Already using the general SDK or MCP server? Since 2026-10-01 [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk) 1.4+ has `officialRates('bojm')` and [`@allratestoday/mcp-server`](https://www.npmjs.com/package/@allratestoday/mcp-server) 0.6+ has a `get_official_rates` tool — both return this source's latest table with no key, so you can add it without a second dependency
- Claude Code plugin (no key): `/plugin marketplace add AllRates-Today/claude-code-plugin` then `/plugin install allratestoday@allratestoday` — bundles both MCP servers plus an `/official-rate bojm ...` command
- Machine-readable site guide: [llms.txt](https://allratestoday.com/llms.txt) · [for-ai-agents](https://allratestoday.com/for-ai-agents/)

## ⚖️ Published vs derived rates

If Bank of Jamaica does not print a pair directly, the API resolves it from the central bank's own table and says so — official and computed values are never confused:

| `method` | `derived` | Meaning |
| --- | --- | --- |
| `published` | `false` | The central bank printed this pair directly |
| `inverse` | `true` | Computed as 1 ÷ the published opposite direction |
| `cross` | `true` | Computed via JMD from two published rates |

## 🛡️ Error handling

Errors are thrown as `Error` with `status` (HTTP code) and `body` (the API's JSON error) attached:

```js
try {
  const pair = await getRate('USD', 'XXX', { apiKey: 'art_live_...' });
} catch (err) {
  console.log(err.message); // human-readable reason
  console.log(err.status);  // e.g. 404
}
```

| Status | Meaning |
| ------ | ------- |
| — | Missing `apiKey` (thrown before any request) |
| `400` | Malformed date or parameters |
| `401` | Invalid API key |
| `403` | Endpoint needs a [paid plan](https://allratestoday.com/pricing/) (historical dates & series) |
| `404` | Pair or date range not covered by Bank of Jamaica |
| `429` | Monthly quota exceeded |

## 🔷 TypeScript

Full definitions ship with the package — no `@types` install:

```ts
import type { LatestRates, PairRate, DatedRates, RateEntry, HistoryQuery, RequestOptions } from 'bank-of-jamaica-exchange-rate';
```

## 📦 CommonJS

```javascript
const { getRate } = require('bank-of-jamaica-exchange-rate');

getRate('USD', 'JMD', { apiKey: 'art_live_...' }).then((pair) => console.log(pair.rate));
```

## 💡 Quota tips

- Rates change once per business day — cache the published table locally and a small monthly quota goes a long way.
- Every request counts toward your AllRatesToday quota, shared across all AllRatesToday endpoints on your key.

## 📖 Methods reference

| Method | Plan | Description |
| ------ | ---- | ----------- |
| `getRate(source, target, { apiKey })` | Free | Latest rate for one pair, resolved from the published table |
| `getLatestRates({ apiKey })` | Free | The central bank's full latest published table |
| `getRatesForDate(date, { apiKey, source?, target? })` | Paid | The official table (or one pair) for a YYYY-MM-DD date |
| `getHistory({ symbol \| source+target, from?, to? }, { apiKey })` | Paid | Daily series since 2000 |

## 📥 Bulk data (no key)

Need the whole archive rather than an API call? The same published tables are mirrored daily as open data:

- Hugging Face: [AllRates/central-bank-exchange-rates](https://huggingface.co/datasets/AllRates/central-bank-exchange-rates) — one CSV per institution (`rates/bojm.csv`)
- Kaggle: [allratestoday/central-bank-exchange-rates](https://www.kaggle.com/datasets/allratestoday/central-bank-exchange-rates)
- CDN JSON: `https://cdn.jsdelivr.net/gh/AllRates-Today/central-bank-exchange-rates@main/data/bojm/latest.json`

## 🔗 Links

- [Bank of Jamaica rates page](https://allratestoday.com/central-bank-rates-api/bojm/) — live table, publication cadence, FAQ
- [All central bank sources](https://allratestoday.com/central-bank-rates-api/)
- [Package docs on the site](https://allratestoday.com/docs/sdk/bank-of-jamaica-exchange-rate/) · [ERP integration guides](https://allratestoday.com/docs/integrations/)
- [API documentation](https://allratestoday.com/docs/#central-bank) · [Interactive reference](https://allratestoday.com/api-reference/) · [Methodology](https://allratestoday.com/official-rates-methodology/)
- [Register (free)](https://allratestoday.com/register) · [Pricing](https://allratestoday.com/pricing/)
- [GitHub](https://github.com/AllRates-Today/bank-of-jamaica-exchange-rate)

## 📜 License

MIT
