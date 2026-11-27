# ❄ Snow Forecast

**English** · [Česky](#česky)

A snow forecast for ski resorts worldwide, in a single `index.html` file. No server, no build, no framework.

**Live app:** https://<your-username>.github.io/snow-forecast/

## Features

- Search any resort or place, with autocomplete.
- Top / Mid / Bottom elevation tabs. Elevations are detected from OpenStreetMap pistes and can be edited.
- Per 3-hour / AM / PM / night block: weather, new snow (cm), rain (mm), temperature and wind chill, wind, humidity, freezing level.
- Summary cards for new snow over 3 and 6 days.
- Consensus of three models (ICON, ECMWF, GFS), with model agreement and spread shown in the table.
- Mobile summary view in portrait, full table in landscape and on desktop.
- Your own favourites, saved in your browser. Export and import supported.
- Shareable links to a specific location.
- Optional webcams near the resort (needs a free Windy API key).
- Czech and English interface.

## How the forecast is computed

Data come from the free [Open-Meteo](https://open-meteo.com) API. Temperature, wind and freezing level are interpolated to the chosen elevation from the pressure-level profile. Rain/snow is decided from wet-bulb temperature, and snowfall uses a temperature-dependent snow-to-liquid ratio. Models are combined with lead-time weights (ICON dominates in the first 48 hours), and snow and rain use a weighted median so one outlier model does not dominate.

This is a model forecast. It has not been systematically verified against measurements, so treat the numbers as guidance, especially for snowfall amounts and local effects in valleys.

## Webcams (optional)

Webcams come from Windy.com and need your own free API key:

1. Open https://api.windy.com/keys and sign in.
2. Create a key for the **Webcams API**.
3. Paste it into the Webcams section of the app.

The key is stored only in your browser. Ad blockers may block requests to Windy.

## Privacy

There is no backend and no tracking. Favourites, language, last location and the Windy key are stored in your browser's `localStorage`. The app calls Open-Meteo, OpenStreetMap (Overpass) and, if you add a key, Windy directly from your browser.

## Run locally

Open `index.html` in a browser, or serve the folder with `python -m http.server`.

## Hosting on GitHub Pages

Settings → Pages → Deploy from a branch → `main` / root.

## Data sources

[Open-Meteo](https://open-meteo.com) (forecast, geocoding, elevation) · [OpenStreetMap](https://www.openstreetmap.org) contributors via Overpass · [Windy.com](https://www.windy.com) (webcams)

---

## Česky

Sněhová předpověď pro lyžařská střediska po celém světě v jednom souboru `index.html`. Bez serveru, bez buildu, bez frameworku.

**Živá appka:** https://<tvoje-jméno>.github.io/snow-forecast/

### Funkce

- Vyhledávání libovolného střediska nebo místa s našeptávačem.
- Záložky Vrchol / Střed / Údolí. Výšky se zjišťují ze sjezdovek v OpenStreetMap a jdou ručně upravit.
- Pro každý 3hodinový / ranní / odpolední / noční blok: počasí, nový sníh (cm), déšť (mm), teplota a pocitová teplota, vítr, vlhkost, nulová izoterma.
- Souhrnné karty nového sněhu za 3 a 6 dní.
- Konsenzus tří modelů (ICON, ECMWF, GFS), v tabulce je vidět shoda a rozpětí modelů.
- Na mobilu na výšku přehled po dnech, na šířku a na počítači celá tabulka.
- Vlastní oblíbená střediska uložená v prohlížeči, s exportem a importem.
- Odkazy na konkrétní místo ke sdílení.
- Volitelně webkamery v okolí (potřebují zdarma API klíč od Windy).
- České a anglické rozhraní.

### Jak se předpověď počítá

Data jsou z bezplatného API [Open-Meteo](https://open-meteo.com). Teplota, vítr a nulová izoterma se pro zvolenou výšku dopočítávají z profilu tlakových hladin. Déšť nebo sníh se určuje podle teploty vlhkého teploměru a množství sněhu podle poměru sníh/voda závislého na teplotě. Modely se kombinují s vahami podle předstihu (prvních 48 hodin převládá ICON) a sníh a déšť se berou jako vážený medián, aby jeden odlehlý model nezkreslil výsledek.

Jde o modelovou předpověď. Nebyla systematicky ověřena proti měření, takže ber čísla jako orientační, hlavně u množství sněhu a místních jevů v údolích.

### Webkamery (volitelné)

Webkamery pocházejí z Windy.com a potřebují tvůj vlastní bezplatný API klíč:

1. Otevři https://api.windy.com/keys a přihlas se.
2. Vytvoř klíč pro **Webcams API**.
3. Vlož ho do sekce Webkamery v appce.

Klíč se ukládá jen ve tvém prohlížeči. Blokátory reklam mohou dotazy na Windy blokovat.

### Soukromí

Žádný backend ani sledování. Oblíbené, jazyk, poslední místo a klíč Windy se ukládají do `localStorage` tvého prohlížeče. Appka volá Open-Meteo, OpenStreetMap (Overpass) a po zadání klíče Windy přímo z prohlížeče.

### Spuštění lokálně

Otevři `index.html` v prohlížeči, nebo složku zpřístupni příkazem `python -m http.server`.

### Hostování na GitHub Pages

Settings → Pages → Deploy from a branch → `main` / root.

### Zdroje dat

[Open-Meteo](https://open-meteo.com) (předpověď, geokódování, nadmořská výška) · přispěvatelé [OpenStreetMap](https://www.openstreetmap.org) přes Overpass · [Windy.com](https://www.windy.com) (webkamery)
