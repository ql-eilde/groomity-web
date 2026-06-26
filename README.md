# Groomity — Site vitrine

Landing page marketing de **Groomity**, l'application de prise de rendez-vous pour le toilettage canin.

- Présente l'app aux **propriétaires** (boutons de téléchargement, « Bientôt disponible » tant que les stores ne sont pas en ligne).
- Convertit les **toiletteurs pros** vers le formulaire d'inscription : https://forms.fillout.com/t/wyfCayfUdyus
- Reprend l'UX/UI de l'app (mêmes couleurs, wordmark, composants).

## Stack

Site **100 % statique** : HTML + CSS, zéro build, zéro dépendance.

```
index.html         Page unique (sémantique + SEO + JSON-LD)
style.css          Design system Groomity
robots.txt         Indexation + sitemap
sitemap.xml        URL canonique
site.webmanifest   Manifest PWA léger
assets/            Logo, favicon, apple-touch-icon, og-image
```

## Aperçu en local

Ouvrir `index.html` dans un navigateur, ou servir le dossier :

```bash
python3 -m http.server 8000
# puis http://localhost:8000
```

## Déploiement (Vercel — recommandé)

Le site est statique, donc **aucun build n'est nécessaire**.

1. Sur [vercel.com](https://vercel.com), **Import Project** → ce repo GitHub.
2. Framework Preset : **Other** (ou « No framework »). Build Command : *vide*. Output Directory : `.` (racine).
3. Deploy.
4. Domaine : Vercel → **Settings → Domains** → ajouter `groomity.fr`, puis pointer le DNS chez le registrar (CNAME/A indiqués par Vercel).

Alternative CLI :
```bash
npm i -g vercel
vercel        # préversion
vercel --prod # production
```

> Autres hébergeurs statiques possibles sans modification : Netlify, GitHub Pages, Cloudflare Pages.

## SEO

- Title / meta description optimisés, `canonical` vers `https://groomity.fr/`.
- Open Graph + Twitter Card (partages sociaux).
- Données structurées JSON-LD : `Organization`, `MobileApplication`, `FAQPage`.
- `robots.txt` + `sitemap.xml`.
- Polices système (0 requête réseau), images optimisées, un seul `<h1>`.

## À mettre à jour plus tard

- **Liens stores** : remplacer les boutons « Bientôt disponible » par les vraies URL App Store / Google Play une fois l'app publiée (dans `index.html`, section hero).
- `sitemap.xml` : actualiser `lastmod` à chaque modification de contenu importante.
