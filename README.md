# Seigliva

En enkel personlig nettside for `itih.no`.

Siden er laget som en liten startside for smart hjem, homelab, små prosjekter og diverse notater. Den inneholder foreløpig en enkel forside med seksjoner for smart hjem, prosjekter og litt kort info om siden.

## Status

- Klargjort for et separat Cloudflare Pages-prosjekt: `itih-site`
- Kildekode ligger på GitHub, produksjonsbranch: `itih`
- Planlagt hoveddomene: <https://itih.no>
- Domenetilkobling og videresending fra `www.itih.no` til `itih.no` settes opp i Cloudflare etter deploy

## Innhold

```text
index.html              # Forsiden
assets/styles.css       # Styling
assets/favicon.svg      # Enkel S-logo/favicon
404.html                # Enkel 404-side
_headers                # Cloudflare Pages-headere
```

## Teknisk

Dette er en statisk HTML/CSS-side uten byggesteg. Cloudflare Pages publiserer direkte fra `itih`-branchen.

Build-oppsett i Cloudflare Pages:

```text
Framework preset: None
Build command: tom
Build output directory: /
```
