# Prism Market Watch

Prism is a stock and fund watching site with a liquid-glass interface. It follows 14 US stocks, 14 China A-shares, 12 Hong Kong stocks, 9 major indices and 18 funds, with K-line charts, a rule-based technical read for every stock and index, fund analysis, and an interface in English or Chinese. The whole site is one HTML file with no build step and no JavaScript libraries.

> **All market data in this version is simulated.** Prices, volumes, order books, fundamentals and fund figures are generated in the browser for demonstration. None of it reflects real or current market values, and nothing in the site is investment advice.

The hosted copy is at https://claude.ai/artifact/Y4vdcB8doBQoQNVfVVC9dM. It stays private to its owner until they share it.

## Liquid glass

Content panels are frosted glass over a colored wallpaper, so the market behind them shows through as soft light. Floating controls (the top bar, the phone tab bar, pop-ups and the settings panel) use clearer glass with a faint prismatic rim. In Chromium browsers, each floating control gets a displacement map generated for its exact size, so whatever sits behind it bends and splits into color at the edges, like light through a lens. A soft highlight follows the pointer across glass surfaces, and segmented controls slide their selection with a slight stretch.

The default wallpaper, Market, paints the selected stock's recent candles in large blurred shapes behind the glass, so the scene changes color with the stock you are looking at.

## Views

The site has three views: Watch, Markets and Funds. On a desktop you switch between them in the top bar; on a phone, in the tab bar at the bottom of the screen.

### Watch

The watchlist on the left holds stocks and indices. Star an instrument to add it, choose Edit to drag rows into a new order or remove them, and choose Sort to rank the list by today's gainers or losers. The filter above the list switches between your watchlist and the site's full lists of US stocks, A-shares, Hong Kong stocks and indices.

Selecting a stock opens its quote: the price and change, the exchange's session status with a countdown to the next open or close, day and 52-week ranges, and twelve key figures, including turnover rate (换手率), amplitude (振幅), P/E (TTM), P/B and dividend yield. Indices show the trading figures only.

The chart has intraday (分时), daily, weekly and monthly views. The intraday view draws the price line, the average-price line (均价线) and minute-by-minute volume across the whole session, with lunch breaks removed from the time axis for Shanghai, Shenzhen and Hong Kong. The K-line views draw candles (solid, hollow, or a single close line) with moving averages or Bollinger Bands, volume with its 5- and 10-day averages, and a lower pane for MACD, KDJ or RSI. Scroll or pinch to zoom, drag to pan, and hover or tap for a crosshair showing the bar's open, high, low, close, change and volume. Double-click to reset the view, or use the expand button for a full-screen chart.

The side panel has two tabs. Insight holds the preliminary analysis described below. Order book shows five bid and five ask levels with the bid/ask ratio (委比), the spread and a list of recent trades. For an index, it shows market breadth and the day's leaders instead.

On a stock's page, the bell button sets price alerts. Enter a price above or below the current one, and a notice appears in the page when the price crosses it. Each alert fires once.

### Preliminary analysis

Each stock and index gets a technical read built from seven signals on its daily chart.

| Signal | What it checks | Score |
|---|---|---|
| Trend | Whether MA5, MA10, MA20 and MA60 are stacked in order, and where the price sits against MA20 and MA60 | −2 to +2 |
| MACD (12, 26, 9) | A golden or death cross in the last five bars, otherwise DIF against DEA | −2 to +2 |
| RSI (14) | Overbought above 70 or oversold below 30 (stronger beyond 80 and 20), otherwise momentum above 55 or below 45 | −2 to +2 |
| KDJ (9, 3, 3) | J above 100 or below 0, otherwise K against D | −1 to +1 |
| Bollinger (20, 2) | Where the price sits within the bands, plus a note when the bands are at their narrowest in six months | −1 to +1 |
| Volume | Today's volume against the five-day average on an up or down day, adjusted for an unfinished session | −1 to +1 |
| Momentum | Whether the 20-day return is beyond ±5% | −1 to +1 |

The scores add up to a total from −10 to +10, shown on a gauge as Strong sell, Sell, Neutral, Buy or Strong buy. Below the gauge are each signal's reading, a ladder placing the current price among the 20- and 60-day highs and lows, the P/E against a rough market average (25 for the US, 15 for A-shares and 11 for Hong Kong), and a written summary. The rules are deliberately simple, so treat the rating as a starting point rather than a recommendation.

On claude.ai, the Ask Claude button at the bottom of the Insight tab sends the indicators and the last 30 closing prices to Claude and shows a short written analysis as it arrives.

### Markets

Session cards for the United States, China and Hong Kong show each exchange's local time and status (open, lunch break, pre-market, after hours, call auction, closed or weekend), a countdown to the next change, and the main indices with intraday sparklines. Below them, a heatmap sizes each stock by market cap and colors it by today's change, with a switch between the three markets. Next to it are the day's biggest gainers or losers across all markets and the five funds rising most today.

### Funds

The fund list holds eight Chinese mutual funds (hybrid, index, QDII and bond funds), seven US ETFs (including a bond ETF and a gold ETF) and three Hong Kong ETFs. Filter it by region and type, and sort it by today's change or by 1-month, 1-year or 3-year return. The star on a fund's page adds it to the Mine list.

A mutual fund's page shows the official NAV (单位净值) with its date, today's estimated NAV (估算净值) based on its benchmark's move, the accumulated NAV (累计净值) and the 1-year return. An ETF's page shows its live price, 1- and 3-year returns and fund size. The NAV chart runs from one month to the full history and can plot the fund against its benchmark as percentage returns. Below the chart are returns by period against the benchmark, the top holdings (linked to their stock pages when the stock is in the site), an asset allocation chart and the fund's profile.

The side panel rates the fund from one to five stars by its 1-year Sharpe ratio. It lists the 3-year annualized return, volatility, maximum drawdown, Sharpe ratio, beta, alpha, share of up months and rank among comparable funds, followed by a written summary. The regular investing (定投) calculator replays a fixed weekly or monthly purchase over one to three years of the fund's history and compares the result with investing the same total on the first day.

### Search

The search box finds stocks, indices and funds by ticker, code, English or Chinese name, or pinyin initials. For example, GZMT finds 贵州茅台 and TXKG finds 腾讯控股. Results show current prices and a star for adding each one to a list.

## Settings

Settings open from the sliders button in the top bar, or from the last tab on a phone. Changes apply immediately.

Appearance settings cover the theme (auto, light or dark), the wallpaper, the glass blur and tint, liquid refraction and ambient motion. The four wallpapers are Market, which paints the selected chart behind the glass; Prism, a band of dispersed light; Ocean; and Graphite.

Market colors set whether rising prices are red, the Chinese convention, or green. On a first visit, a browser set to Chinese gets the Chinese interface with red for rising prices, and any other browser gets English with green.

Chart settings cover the candle style, the four moving-average periods (2 to 250 days), the main overlay, the lower indicator and the volume bars. Layout settings hide the index strip or the insight panel and tighten the list rows. Data settings pause the simulation, change its speed, and reset the lists or every setting.

## Keyboard and touch

| Input | Action |
|---|---|
| `/` | Focus the search box |
| `↑` `↓` in search | Move through results; `Enter` opens one and `Esc` clears the search |
| `↑` `↓` in the Watch view | Select the previous or next instrument |
| `←` `→` on a focused chart | Move the crosshair one bar |
| `+` `−` on a focused chart | Zoom in or out |
| `Esc` | Close settings, the alert pop-up or the full-screen chart |
| Double-click on the chart | Reset the chart view |
| Drag or pinch on the chart | Pan or zoom the K-line chart |
| Tap on the chart | Pin the crosshair; tap again to clear it |

## How the simulation works

Every instrument gets about four years of daily history (1,000 trading days) from a random generator seeded by its symbol, so the history is identical on every load. Returns have clustered volatility and trend phases, and each stock moves partly with its market's main index (the S&P 500, the SSE Composite or the Hang Seng), so markets tend to rise and fall together. Each path is scaled to end at a reference price. The reference prices, market caps, P/E ratios and fund figures are rough demo values, not current data.

Exchange rules are modeled where they show on screen. A-shares stop at the ±10% daily limit, or ±20% for ChiNext and STAR Market codes starting with 300, 301 or 688. Hong Kong prices move in the exchange's tick sizes. Intraday charts follow each exchange's trading hours and lunch breaks in its own time zone. Public holidays are ignored.

While the page is open, prices update every 0.9, 1.6 or 2.6 seconds depending on the speed setting, whether or not the real market is open. The Simulated button in the top bar pauses and resumes them. Mutual fund estimates and ETF prices follow their benchmark index through a beta plus a small fund-specific drift, while the bond fund, the bond ETF and the gold ETF follow their own paths.

## Saving and privacy

The watchlist, fund list, price alerts and settings are saved in the browser. On claude.ai, they are also saved to each viewer's Claude account in storage only that viewer can read, so they carry across devices. When the two copies differ, the most recent change wins. Viewers who can only view a shared copy keep their changes in the browser. The selected stock and fund are remembered in the browser only.

The Ask Claude buttons appear only on claude.ai. The first use asks the viewer for permission, and each answer counts toward the viewer's own Claude usage. A request contains the simulated prices and indicators shown on the page and nothing about the viewer.

The page loads one outside resource, the Manrope typeface from Google Fonts. Where Google Fonts is blocked, as is common in mainland China, the page uses system fonts instead.

## Running it yourself

The site is one self-contained file, `prism-market-watch.html`. Open it in a browser, or serve it from any static host. For a quick local server, run this in the folder that holds the file:

```sh
python3 -m http.server 8000
```

Then open `http://localhost:8000/prism-market-watch.html`.

Outside claude.ai, account sync and Ask Claude turn themselves off, and everything else works the same, saving to the browser.

The site needs a browser from about 2023 or later, because it uses CSS `color-mix()`, `backdrop-filter` and individual transform properties. Liquid refraction works only in Chromium browsers such as Chrome and Edge; Safari and Firefox show frosted glass instead. The page follows the system's reduce-motion setting.

## Connecting real data

A page published on claude.ai can't contact outside websites, so real prices need a self-hosted copy and a data source. The simplest route is a small local server that the page polls every few seconds. AkShare, a free and open-source Python library, can supply quotes and forward-adjusted K-line history for A-shares, Hong Kong stocks and US stocks, plus NAV history for Chinese funds. For streaming US prices, Finnhub's free plan offers real-time quotes and a WebSocket feed with a free API key.

The rest of the page reads prices from a few shared objects, so only the simulation needs replacing.

| Replace | With |
|---|---|
| `genSeries()` inside `buildAll()` | Real daily bars, oldest first, as `{t: 'YYYY-MM-DD', o, h, l, c, v}`, and today's minute points as `{p, v, a}` (price, volume, running average price). Pass them to `storeQuote(instrument, {bars, pts})`, which fills `Q` and `HIST`. |
| `buildFund()` | The NAV series in `FH[id] = {dates, vals}` and the current values in `FQ[id]`. |
| `tickQuote()` inside `tick()` | Code that writes the latest price, high, low and volume into `Q[symbol]` and the last bar and minute point in `HIST[symbol]`, then returns `true` when the price changed. |

Charts, indicators, analysis, alerts and the heatmap all update from those objects without further changes. The order book and trade list would stay illustrative, because live order books need paid Level-2 data.

Free data has limits. It is often delayed, with Hong Kong quotes commonly 15 minutes behind, and providers cap how often you can ask. AkShare collects data from public finance websites, so it can stop working when those sites change. Showing market data on a public or commercial site usually requires a licensed feed.

## Adding instruments

Stocks are declared near the top of the script with `stk()`:

```js
// symbol, market, exchange, English name, Chinese name, pinyin initials, sector,
// reference price, annual volatility, market cap (billions, local currency),
// P/E, P/B, dividend yield %, daily turnover rate %, extras
stk('AAPL','US','NASDAQ','Apple','苹果','PG','tech',254.6,.27,3780,38.6,57,.41,.55);
```

Symbols use the suffixes `.SH`, `.SZ` and `.HK` for Shanghai, Shenzhen and Hong Kong. Sector keys are defined in `SECTORS`. The optional extras object takes `lot` (the Hong Kong board lot), `rho` (how closely the stock follows its market index), `drift` (annual drift) and `seed`. Indices use `idx()` with a reference level, volatility and typical daily volume, and one index per market is marked `main`.

Funds are declared with `fnd()`, which takes these fields:

| Field | Meaning |
|---|---|
| `id`, `m`, `type` | Code, region (`CN`, `US` or `HK`) and type (`hybrid`, `index`, `qdii`, `bond`, `etf` or `commodity`) |
| `kind` | `mf` for a mutual fund with a daily NAV and an intraday estimate, or `etf` for a fund with a live price; defaults to `mf` |
| `en`, `zh`, `py`, `co` | English and Chinese names, pinyin initials, and the fund company as `[English, Chinese]` |
| `bench`, `beta`, `alpha`, `idio` | Benchmark index symbol and how closely the fund follows it; for a fund with no benchmark, set `bench: null` and give a `drift` |
| `ref`, `fee`, `aum`, `inc`, `risk` | Latest NAV or price, fees, size in billions, inception date, and risk level from 1 to 5 |
| `alloc`, `hold` | Asset allocation in percent, and top holdings: `H_(symbol, weight)` for instruments in the site, `X_(englishName, chineseName, weight)` for others |

The default lists are `DEFAULT_WATCH` and `DEFAULT_FWATCH`, and every interface string lives in `STR.en` and `STR.zh`.

## Code layout

The file holds the stylesheet, the page markup and one script, which runs in four parts.

| Part | Contents |
|---|---|
| Data | Markets and trading hours (`MKT`), instruments (`U`), funds (`FUNDS`), default lists and interface strings (`STR`) |
| Engine | Seeded random numbers, exchange clocks, history and tick simulation, indicators (MA, EMA, MACD, RSI, KDJ, Bollinger, ATR), weekly and monthly aggregation, the technical analysis, fund metrics, the regular-investing replay and number formatting |
| Charts | The canvas K-line and intraday chart (`KChart`), the NAV chart (`LineChart`), and SVG sparklines, gauge, donut and treemap |
| App | State and saving, refraction maps for the floating controls, rendering for each view, live updates, search, alerts, settings and start-up |

Colors are tokens on `:root`. The dark set applies when the system prefers dark mode and the light theme isn't chosen, or whenever the dark theme is chosen.

## Known limitations

Market data is simulated, as described above, and the session clocks ignore public holidays. The order book and trade list are illustrative. Price alerts only notify inside the open page. Liquid refraction works only in Chromium browsers, and on computers without graphics acceleration, Chromium may draw large background blurs weaker than intended. The settings panel doesn't yet keep keyboard focus inside it while it is open.

## Disclaimer

Company, index and fund names appear only to make the demo recognizable. The prices, fundamentals, fees, fund sizes and holdings attached to them are illustrative and differ from the real figures. Nothing in this site is investment advice.
