# Checklist SEO technique (après chaque déploiement Lovable)

## Indexation
- [ ] `https://ecr-couverture.fr` répond 200 à un robot (`curl -A Googlebot -I`) — l'ancien site Tilda renvoyait 403
- [ ] `robots.txt` présent, n'interdit rien d'utile, pointe vers le sitemap
- [ ] `sitemap.xml` à jour, inclut les pages dynamiques (réalisations, villes, articles)
- [ ] Une URL canonique par page, `www` → racine (ou l'inverse) en 301
- [ ] Le contenu est dans le HTML servi (SSR), pas seulement après JavaScript
- [ ] `/admin` et « Nouveau chantier » non indexables (noindex + auth), absents du sitemap

## Balises
- [ ] Title et meta description uniques par page (voir `03-contenus/pages/`)
- [ ] Un seul H1 par page
- [ ] Attribut `alt` descriptif sur chaque photo (lieu + technique)
- [ ] Open Graph (image chantier réelle)

## Données structurées
- [ ] `RoofingContractor` sur l'accueil (voir `schema-roofingcontractor.json`), valide dans le Rich Results Test
- [ ] `BreadcrumbList` sur les pages profondes
- [ ] Pas de FAQPage pour des gains d'affichage (plus d'effet depuis mai 2026)

## Performance et mobile
- [ ] Images en WebP, dimensionnées
- [ ] Bouton « Appeler » collant sur mobile (`tel:+33328656531`)
- [ ] Core Web Vitals au vert dans Search Console (après 28 jours)

## Conversion et mesure
- [ ] Formulaire devis enregistré en base + email à contact@ecr-couverture.fr
- [ ] Événements suivis : envoi formulaire, clic téléphone, clic email
- [ ] Search Console et Bing Webmaster Tools connectés, sitemap soumis
