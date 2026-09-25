# Seigliva

En enkel personlig statisk nettside laget for GitHub + Cloudflare Pages.

## Filer

- `index.html` — selve siden
- `assets/styles.css` — styling
- `assets/favicon.svg` — enkelt ikon
- `_headers` — anbefalte sikkerhetsheadere for Cloudflare Pages

## Lokal testing

```bash
python3 -m http.server 8788
```

Åpne deretter <http://localhost:8788>.

## Publisering med Cloudflare Pages

1. Opprett et GitHub-repo, f.eks. `seigliva-site`.
2. Push disse filene til repoet.
3. I Cloudflare: **Workers & Pages → Create application → Pages**.
4. Koble til GitHub-repoet.
5. Build settings:
   - Framework preset: `None`
   - Build command: la stå tom
   - Build output directory: `/`
6. Legg til custom domain, f.eks. `dittdomene.no` og `www.dittdomene.no`.

