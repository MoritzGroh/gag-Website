

## GitHub Pages / Jekyll

Die Website ist für den Build mit Jekyll und die Veröffentlichung über GitHub Pages vorbereitet.

### Einmalige Einrichtung

1. Repository auf GitHub pushen.
2. In **Settings → Pages** bei **Build and deployment → Source** die Option **GitHub Actions** auswählen.
3. Danach auf `main` oder `master` pushen. Der Workflow `.github/workflows/deploy.yml` baut die Jekyll-Seite und veröffentlicht sie automatisch.

Der Workflow erkennt automatisch, ob es sich um ein Benutzer-/Organisations-Repository (`<name>.github.io`) oder um ein normales Projekt-Repository handelt und setzt `url` bzw. `baseurl` entsprechend.

### Lokal testen

Voraussetzungen: Ruby, Bundler und Node.js.

```bash
bundle install
npm ci
bundle exec jekyll serve
```

Die fertige Website liegt nach `bundle exec jekyll build` in `_site/`.
