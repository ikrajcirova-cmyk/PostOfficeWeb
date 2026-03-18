# Kalkulátor poštovného – Česká pošta

A modern, responsive web calculator for Czech Post (Česká pošta) shipping prices.
Prices are valid from **1. 1. 2026** according to official tariff documents.

## Features

- **Balík Do ruky** – parcel delivery to address (sizes S/M/L/XL, discounts, add-ons)
- **Balíkovna – Na adresu** – Balíkovna delivery to address
- **Balíkovna – Výdejní místo** – Balíkovna pickup point delivery
- **Letters** – Obyčejné psaní, Doporučené psaní, Cenné psaní (multiple weights & speeds)
- All add-on services and discounts included

## Running Locally

No build step required. Just open `index.html` in a browser:

```bash
open index.html
```

Or serve with any static server:

```bash
python3 -m http.server 8080
# then open http://localhost:8080
```

## Deployment

### Netlify (recommended – drag & drop)
1. Go to [app.netlify.com](https://app.netlify.com)
2. Drag the `ceska-posta-kalkulacka` folder onto the Netlify dashboard
3. Done — your site is live instantly!

### Vercel
```bash
npx vercel --prod
```

### GitHub Pages
1. Push to a GitHub repository
2. Go to Settings → Pages → Deploy from branch `main` / `root`

## Price Sources

- **Balík Do ruky**: [Ceník Balík Do ruky (PDF, platný od 1. 1. 2026)](https://www.ceskaposta.cz/documents/10192/9355487/Podminky_Cenik_Balik_Do_ruky.pdf)
- **Balíkovna**: [balikovna.cz/cs/poslat-balik](https://www.balikovna.cz/cs/poslat-balik)
- **Listovní zásilky**: [Kompletní ceník ČP (PDF, platný od 1. 1. 2026)](https://www.ceskaposta.cz/documents/10180/282441/kompletni_cenik.pdf)

## Disclaimer

This calculator is for informational purposes only. Always verify the current prices on the official Czech Post website before sending.
