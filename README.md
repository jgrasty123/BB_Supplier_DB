# BroBasket Supplier Catalog — Internal Sourcing Tool

A searchable database of 32,597 products across all 6 distributors (beer, wine, spirits, RTDs, non-alc).

## Files
- `index.html` — the app
- `data.json` — the product data (must sit in the SAME folder as index.html)

## Use it locally
Because it loads `data.json` via fetch, double-clicking `index.html` may be blocked by browser security on some setups. Easiest local view:
```
cd brobasket-supplier-catalog
python3 -m http.server 8000
# open http://localhost:8000
```
Or just deploy it (below) — no server config needed.

## Deploy to Netlify via GitHub
1. Drop both files into your repo (e.g. a `/supplier-catalog/` folder).
2. Push. Netlify serves it as a static site — no build step.
3. It's plain HTML/JS, so it works as-is. (If you want it gated, put it behind Netlify password protection or a subdomain.)

## Updating the data later
Re-scrape into the same Excel format and send it back — I'll regenerate `data.json`. Schema per supplier tab is preserved in the build script.

## Suppliers & coverage
- SGproof / Southern Glazer's — 12,419
- BreakThru Beverage — 10,008
- SipMarket (Allied) — 4,847
- Skurnik (Wine) — 2,655
- Sunset Distributing — 1,836 (OCR source, names are best-effort/messy)
- Pacific Beverage — 832

## Notes
- ~93% of products have a price; missing prices show "Call for price."
- Categories were inferred from product names for BreakThru (no category column in source). ~11% remain "Uncategorized" — genuinely ambiguous names.
- Sunset Distributing came from a messy OCR-style sheet; its product names have spacing artifacts. Usable for browsing, verify before ordering.
- Prices are distributor wholesale and change often — always confirm on the supplier site.
