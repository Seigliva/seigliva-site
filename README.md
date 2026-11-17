# Seigliva · ITih

Kildekoden til **[itih.no](https://itih.no/)** — en personlig prosjektside for IT i hjemmet, Home Assistant, blueprints og små verktøy.

## Publisert nettside

- **Hovedadresse:** <https://itih.no/>
- **WWW:** <https://www.itih.no/> videresendes permanent (301) til hovedadressen, med sidesti og URL-parametere bevart.
- **Hosting:** Cloudflare Pages, prosjekt `itih-site`.
- **Produksjonsbranch:** `itih`. Push til denne branchen starter automatisk publisering.
- **GitHub-standardbranch:** `main`. Hold denne oppdatert med godkjente endringer fra `itih`, slik at repoets forside viser gjeldende kode og dokumentasjon.
- **Alternativ adresse:** <https://itih-site.pages.dev/>. Cloudflare lager også versjonsspesifikke adresser for hver deployment; del hovedadressen i stedet.
- HTTPS er aktivert, og sidens canonical- og Open Graph-adresse er `https://itih.no/`.

## Innhold

Forsiden presenterer Home Assistant Watch, prosjektshowcase og gjenbrukbare Home Assistant-blueprints.

```text
index.html              # Forside, metadata og prosjektlenker
404.html                # Egen 404-side
assets/styles.css       # Styling
assets/favicon.svg      # S-logo/favicon
assets/ha-watch.svg      # Prosjektikon
_headers                # Sikkerhets- og personvernheadere for Pages
README.md               # Dokumentasjon
```

## Cloudflare Pages-oppsett

Statisk HTML/CSS uten avhengigheter eller byggesteg. Et lite inline-script oppdaterer årstallet i bunnteksten.

| Innstilling | Verdi |
| --- | --- |
| Repository | `Seigliva/seigliva-site` |
| Project name | `itih-site` |
| Production branch | `itih` |
| Framework preset | `None` |
| Build command | Tomt |
| Build output directory | `/` |
| Environment variables | Ingen nødvendig |
| Custom domains | `itih.no`, `www.itih.no` |

WWW-videresendingen administreres i Cloudflare-sonens Redirect Rules, ikke i HTML-koden:

```text
Match: (http.host eq "www.itih.no")
Type: Dynamic
Target: concat("https://itih.no", http.request.uri.path)
Status: 301
Preserve query string: On
```

## Lokal forhåndsvisning

Kjør fra rotmappen i repoet:

```sh
python3 -m http.server 8788 --bind 127.0.0.1
```

Åpne <http://localhost:8788>. Cloudflare-headere og videresendingsregler brukes ikke av den lokale serveren.

## Vedlikehold

- Gjør nettsideendringer på `itih`, kontroller dem lokalt og push for å publisere.
- Kontroller produksjonssiden etter deploy, og synkroniser godkjente endringer til `main`.
- Behold `https://itih.no/` som offentlig hovedadresse i metadata og dokumentasjon.
- Ikke legg inn innloggingshemmeligheter, interne adresser eller private tjenesteendepunkter i dette offentlige repoet.
- Cloudflare publiserer fra repoets rot, så også README er offentlig tilgjengelig som fil. Legg aldri private driftsnotater her.
