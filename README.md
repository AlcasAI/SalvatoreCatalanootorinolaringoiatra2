# Dr. Salvatore Catalano — Otorinolaringoiatra

Sito web one-page dello studio del **Dr. Salvatore Catalano**, otorinolaringoiatra a Domodossola (VCO).
Presenta servizi, prestazioni, recensioni, FAQ e contatti, con dati strutturati per la SEO locale.

🔗 **Sito online:** https://alcasai.github.io/salvatorecatalanootorinolaringoiatra2/

## Caratteristiche

- Sito statico **single-page** in HTML/CSS/JavaScript, senza framework né build step.
- **Responsive**, con menu mobile, animazioni allo scroll e sezioni generate dinamicamente in JS.
- **SEO**: meta tag Open Graph/Twitter, dati strutturati [schema.org](https://schema.org) (`Physician` / `MedicalBusiness` + `WebSite`), `sitemap.xml` e `robots.txt`.
- **PWA-ready**: `site.webmanifest` e icone SVG.
- Icone via [Lucide](https://lucide.dev) e font via Google Fonts.

## Struttura del progetto

```
.
├── index.html              # Pagina principale (markup + CSS + JS inline)
├── site.webmanifest        # Manifest PWA
├── robots.txt              # Direttive per i crawler
├── sitemap.xml             # Mappa del sito
├── .nojekyll               # Disabilita l'elaborazione Jekyll su GitHub Pages
├── assets/
│   └── img/                # Immagini, logo e favicon (SVG/JPG)
└── .github/
    └── workflows/
        └── deploy.yml      # Workflow di deploy su GitHub Pages
```

## Anteprima in locale

Trattandosi di un sito statico, è sufficiente un qualsiasi server HTTP locale:

```bash
# Con Python 3
python3 -m http.server 8000
```

Poi apri http://localhost:8000 nel browser.

## Deploy

Il deploy su **GitHub Pages** è automatico tramite GitHub Actions (`.github/workflows/deploy.yml`):

1. Ogni `push` sul branch **`main`** avvia il workflow, che pubblica l'intera root del repository.
2. Il workflow abilita GitHub Pages automaticamente al primo avvio (`actions/configure-pages` con `enablement: true`).
3. In alternativa, il deploy può essere lanciato manualmente da **Actions → Deploy to GitHub Pages → Run workflow**.

Verifica che in **Settings → Pages** la sorgente sia impostata su **GitHub Actions**.

## Manutenzione dei contenuti

I contenuti dinamici (servizi, recensioni, prezzi, FAQ) sono definiti come array JavaScript in fondo a `index.html`
e renderizzati a runtime: per aggiornarli è sufficiente modificare i relativi array.
