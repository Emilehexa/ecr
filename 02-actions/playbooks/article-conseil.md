# Playbook : article conseil / page prix

_Actions : CONT-20 à CONT-24, AUTO-07. Production ici ; publication via MCP dans la table `articles`._

## Entrées
- Sujet issu de `03-contenus/calendrier-editorial.md`.
- Données ECR : fourchettes de prix tirées de **vrais devis** (Éric), photos, retours terrain.
- Pour la réglementation et les aides : sources officielles datées (service-public.fr, Anah, Légifrance).

## Production
1. Brief (requête cible, intention, page liée) dans le calendrier.
2. Brouillon Claude dans `03-contenus/articles/<slug>.md`.
3. Vérification des chiffres par Éric / Nicolas, des règles par une source officielle.
4. Publication via MCP (`INSERT`/`UPDATE` dans `articles`), avec date de mise à jour visible.

## Règles
- Prix : toujours en fourchette, avec ce qui fait varier le prix, date de relevé.
- Aides : ne jamais affirmer une aide sans source datée. Rappel : isolation de toiture plus financée par geste depuis le 01/09/2026.
- Chaque article renvoie vers 1 page service et 1 à 3 réalisations.
