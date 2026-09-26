# Seigliva

En enkel personlig nettside for `uroh.one`.

Siden er laget som en liten startside for smart hjem, homelab, små prosjekter og diverse notater. Den inneholder foreløpig en enkel forside med seksjoner for smart hjem, prosjekter og litt kort info om siden.

## Status

- Publisert med Cloudflare Pages
- Kildekode ligger på GitHub
- Hoveddomene: <https://uroh.one>
- `www.uroh.one` videresendes til `uroh.one`

## Innhold

```text
index.html              # Forsiden
assets/styles.css       # Styling
assets/favicon.svg      # Enkel S-logo/favicon
404.html                # Enkel 404-side
_headers                # Cloudflare Pages-headere
```

## Teknisk

Dette er en statisk HTML/CSS-side uten byggesteg. Cloudflare Pages publiserer direkte fra `main`-branchen.

Build-oppsett i Cloudflare Pages:

```text
Framework preset: None
Build command: tom
Build output directory: /
```
