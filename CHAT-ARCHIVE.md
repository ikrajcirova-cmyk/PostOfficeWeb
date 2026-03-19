# Chat Archive – Česká pošta Kalkulátor
**Datum:** 18. března 2026  
**Projekt:** `/Users/iveta.krajcirova/Extra/ceska-posta-kalkulacka/`  
**GitHub:** https://github.com/ikrajcirova-cmyk/Seminar

---

## Co bylo postaveno

### 1. Kalkulátor poštovného (`index.html`)
Webová aplikace pro výpočet ceny zásilek České pošty.

**Podporované služby:**
| Služba | Cena od |
|---|---|
| Balík Do ruky S (≤35 cm) | 129 Kč |
| Balík Do ruky M (≤50 cm) | 159 Kč |
| Balík Do ruky L (≤100 cm) | 209 Kč |
| Balík Do ruky XL (≤200 cm) | 359 Kč |
| Balíkovna – Na adresu | 115 Kč / 105 Kč (s účtem) |
| Balíkovna – Výdejní místo | 85 Kč / 75 Kč (s účtem) |
| Obyčejné psaní | od 31 Kč |
| Doporučené psaní | od 77 Kč |
| Cenné psaní | od 82 Kč |

**Zdroje dat:** Oficiální ceník ČP platný od 1. 1. 2026

---

### 2. Stránka počasí (`weather.html`)
Stránka pro zobrazení aktuálního počasí v České republice.

**Funkce:**
- Vyhledávání jakéhokoliv města/obce v ČR přes **Nominatim API** (OpenStreetMap)
- Rychlý výběr 8 největších měst
- Interaktivní mapa (Leaflet.js + OpenStreetMap)
- Zobrazení: teplota, pocitová teplota, vlhkost, vítr, viditelnost, srážky, oblačnost, tlak, UV index
- Data z **Open-Meteo API** (aktualizace každou hodinu)
- Automatické načtení počasí v Praze při otevření stránky
- Klávesové ovládání výsledků vyhledávání (↑ ↓ Enter Escape)

---

## Průběh konverzace

### Krok 1 – Sběr dat
- Stažení a zpracování oficiálního ceníku ČP (PDF) platného od 1. 1. 2026
- Ceník Balík Do ruky, Balíkovna, listovní zásilky

### Krok 2 – Výstavba kalkulátoru
- Vytvořen `index.html` jako statická webová stránka (bez Node.js)
- Technologie: HTML + Tailwind CSS (CDN) + vanilla JavaScript
- Živý výpočet ceny při každé změně vstupu

### Krok 3 – Úpravy designu
- **Změna barvy:** Červená → Modrá → Pastelová modrá (`#7eafc8`)
- **Header:** Barevný pozadí → Bílý čistý header se subtilním okrajem
- Pastelová paleta: primární `#7eafc8`, tmavší `#5a93af`, pozadí `#eaf4f9`

### Krok 4 – GitHub
- Inicializace git repozitáře
- Oprava git konfigurace (email byl nastaven jako jméno → opraveno na `ikrajcirova-cmyk@users.noreply.github.com`)
- Přepsání všech commitů správným emailem (`git filter-branch`)
- Push do: https://github.com/ikrajcirova-cmyk/Seminar

### Krok 5 – Stránka počasí
- Vytvořen `weather.html` s hardcoded seznamem 50 měst
- Přidán link "⛅ Počasí" do headeru kalkulátoru
- **Upgrade:** Nahrazení hardcoded seznamu živým **Nominatim API** vyhledáváním
  - Pokrývá všech 6 000+ obcí v ČR
  - Debounce 350ms při psaní
  - Zobrazení "Hledám…" při čekání na API
  - Keyboard navigace ve výsledcích

---

## Technický stack

| Část | Technologie |
|---|---|
| Frontend | HTML5, Tailwind CSS (CDN), vanilla JavaScript |
| Mapa | Leaflet.js 1.9.4 + OpenStreetMap tiles |
| Vyhledávání měst | Nominatim API (OpenStreetMap) – zdarma, bez klíče |
| Data počasí | Open-Meteo API – zdarma, bez klíče |
| Fonty | Google Fonts – Inter |
| Verzování | Git + GitHub |

---

## Struktura projektu

```
ceska-posta-kalkulacka/
├── index.html          # Kalkulátor poštovného
├── weather.html        # Počasí v ČR
├── README.md           # Dokumentace projektu
└── CHAT-ARCHIVE.md     # Tento soubor
```

---

## Deployment

Projekt je statická webová stránka – žádný build krok není potřeba.

**Lokálně:**
```bash
open index.html
# nebo
python3 -m http.server 8080
```

**Online (Netlify Drop):**
1. Jdi na https://app.netlify.com/drop
2. Přetáhni složku `ceska-posta-kalkulacka` na stránku
3. Stránka je okamžitě živá

**GitHub:** https://github.com/ikrajcirova-cmyk/Seminar  
Repozitář je **privátní** – GitHub Pages není dostupné na free plánu pro privátní repozitáře.

---

## Plánované vylepšení (neimplementováno)

- [ ] **Mapy.cz integrace** – nahrazení OpenStreetMap za Mapy.cz tiles
  - Vyžaduje API klíč z https://developer.mapy.com (zdarma)
  - Kliknutí na mapu → automatické zjištění města + načtení počasí
  - Mapy.cz Suggest API pro lepší autocomplete
- [ ] Předpověď počasí na 7 dní
- [ ] Oblíbená města (localStorage)
- [ ] Tmavý režim

---

## Zdroje a reference

- Ceník Balík Do ruky: https://www.ceskaposta.cz/documents/10192/9355487/Podminky_Cenik_Balik_Do_ruky.pdf
- Kompletní ceník ČP: https://www.ceskaposta.cz/documents/10180/282441/kompletni_cenik.pdf
- Balíkovna ceny: https://www.balikovna.cz/cs/poslat-balik
- Open-Meteo API: https://open-meteo.com
- Nominatim API: https://nominatim.openstreetmap.org
- Mapy.cz developer: https://developer.mapy.com
