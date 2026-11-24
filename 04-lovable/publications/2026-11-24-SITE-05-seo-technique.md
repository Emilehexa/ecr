# 2026-11-24 SITE-05 : SEO technique + corrections de texte

- Action backlog : SITE-05 (+ corrections validées par Emile le 24/11)
- Canal : send_message
- Message Lovable : `main:user#00000000000020#usr:3T6DA4VR` → commit `88e17b46`
- Coût : 5 crédits
- Statut : vérifié (code), non publié

## Fait
- `lang="fr"`, pages 404 et erreur en français
- `src/lib/site.ts` : SITE_URL, `pageHead()` (canonical, og:*, twitter:image), `businessSchema` (RoofingContractor, conforme à `schema-roofingcontractor.json`)
- JSON-LD sur `/`, sitemap dynamique `/sitemap.xml` (routes marquées `staticData.sitemap`), robots.txt → sitemap
- Page `/mentions-legales` (capital, TVA, hébergeur en `[À COMPLÉTER]`)
- Header / footer factorisés dans `src/components/site-shell.tsx`
- Textes : MaPrimeRénov' / CEE / aides retirés ; « sous 7 jours ouvrés » retiré ; zone Dunkerquois + 1 h ; « sérieux » ; « Route de Bergues » ; nom « ECR Couverture – Façade »

## Vérification
- [x] Diff lu : `index.tsx`, `__root.tsx`, `site.ts`, `mentions-legales.tsx`, `robots.txt`
- [ ] `public/og-image.jpg` : annoncé par Lovable, non visible dans le diff (binaire) → à contrôler sur la preview
- [ ] Rendu HTML : preview protégée (401), à revérifier après publication
- Non modifié volontairement : « Monuments Historiques / Entreprise agréée », reste de la FAQ, formulaire

## Reste ouvert
- `[À COMPLÉTER]` mentions légales : capital social, n° TVA, hébergeur
