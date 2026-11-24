# Playbook : page ville

_Actions : CONT-12, CONT-23. Production ici ; publication via MCP dans la table `communes`._

## Condition d'entrée (sinon on ne crée pas la page)
- ≥ 2 réalisations publiées dans la commune, **ou** 1 chantier patrimoine.
- Un vrai contenu propre à la ville : bâti dominant, matériaux typiques, secteurs protégés / ABF, exposition (littoral, vent).

## Ordre
Dunkerque → Hazebrouck → Bergues → Cassel → Coudekerque-Branche / Grande-Synthe → Steenvoorde → Hondschoote → Bailleul → Saint-Omer → Gravelines → Bourbourg.

## Production
1. Vérifier la condition d'entrée.
2. Brouillon Claude dans `03-contenus/villes/couvreur-<ville>.md`.
3. Validation Nicolas.
4. Publication via MCP (`INSERT` dans `communes`) + lien depuis `/zones-intervention` et depuis les réalisations de la ville.

## Interdit
Pages clonées avec seulement le nom de la ville qui change (« doorway pages »).
