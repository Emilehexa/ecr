# Audit du projet Lovable « Heritage Roof Facade » (23/11/2026)

_Lecture seule via MCP, commit `bebf8bb`. Aucune modification faite._

## État
- TanStack Start (SSR) : OK pour le SEO, pas besoin de nouveau projet → SITE-01 = reprise de ce projet.
- **One-page** (`src/routes/index.tsx`, navigation par ancres). Une seule URL indexable.
- Base de données **non activée**. Knowledge du projet vide.
- Non publié. Workspace en plan free.
- Design existant (Zilla Slab + Barlow, doré/anthracite) : à garder.

## Problèmes trouvés
| # | Problème | Où | Gravité |
|---|---|---|---|
| 1 | « Entreprise agréée Monuments Historiques » (n'existe pas : c'est la qualification Qualibat 3194) | bandeau, carte MH, FAQ, footer | Élevée (fausse affirmation) |
| 2 | Faits non vérifiés dans la FAQ : urgence 24-48 h, devis sous 7 jours ouvrés, validité 3 mois, acompte, « certifications renouvelées chaque année après audit » | FAQ | Élevée |
| 3 | « éligibles à MaPrimeRénov' / CEE » sans réserve (isolation de toiture plus financée par geste depuis 01/09/2026) | FAQ, pilier « Certifiés » | Élevée |
| 4 | Réalisations : 6 images avec légendes (« Clocher classé — Flandre intérieure »…) : vraies photos ECR ou images générées ? | section Réalisations | Élevée si fictives |
| 5 | Formulaire non branché (`TODO`), affiche « merci » sans rien envoyer | Contact | Bloquant |
| 6 | `<html lang="en">`, page 404 en anglais | `__root.tsx` | Moyenne |
| 7 | Zone « tout le Nord-Pas-de-Calais », Lille, Arras : contraire au positionnement (Flandre + Dunkerquois) | hero, zone, FAQ, title | Moyenne |
| 8 | Pas de données structurées, pas de sitemap, robots.txt sans sitemap, pas de canonical, pas d'og:image | technique | Moyenne |
| 9 | « Mentions légales » pointe vers `#top` (page inexistante) | footer | Moyenne (obligation légale) |
| 10 | Horaires « lundi-vendredi 8h-18h », « rappel sous 48 h » non vérifiés | Contact | Faible |
| 11 | Coquille : « réputation sur la série » (→ « le sérieux ») | À propos | Faible |
| 12 | Nom « ECR Couverture-Façade » (tiret court) vs canonique « ECR Couverture – Façade » | title, footer | Faible |

## Changements proposés (par lots, chacun soumis à validation)
Voir le message de proposition dans la conversation du 23/11/2026 ; décisions à reporter ici.
