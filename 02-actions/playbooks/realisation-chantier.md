# Playbook : chantier → fiche réalisation

_Actions : CONT-01, CONT-02, CONT-10, AUTO-02. Capture sur téléphone (page « Nouveau chantier », prompt 2 bis), relecture ici, validation dans `/admin` ou ici._

## Entrées (terrain)
- 6 à 15 photos : avant, pendant, après, détails techniques. Pas de visages ni de plaques sans accord.
- Note vocale de 1-2 min (Jérôme / chef de chantier) : commune, type de bâtiment, problème de départ, technique et matériaux, durée, contraintes (ABF, hauteur, météo), anecdote.
- Si chantier public / MH : maître d'ouvrage, architecte, accord pour citer.

## Production
1. Sur le chantier, le chef d'équipe ouvre « Nouveau chantier » (PWA) : photos avant/pendant/après, commune, services, type de bâtiment, note vocale. Envoyer → brouillon rédigé par Claude côté Lovable, **uniquement à partir de la saisie**.
2. Revue hebdo ICI : `SELECT … FROM realisations WHERE statut = 'brouillon'` via MCP → copie dans `03-contenus/realisations/<slug>.md`. Contrôle : faits cohérents avec `00-contexte/`, rien d'inventé, lien service + commune, alt des photos.
3. Corrections éventuelles : modifiées ici puis `UPDATE` via MCP.
4. Validation par Nicolas ou Jérôme : bouton « Publier » dans `/admin` (ou `statut: validé` ici, puis `UPDATE … statut = 'publie'` via MCP).
5. Vérifier la page en ligne, loguer dans `04-lovable/publications/`, remplir `publie_le`.
_Chantiers passés sans saisie téléphone : photos + note déposées dans le repo, brouillon rédigé ici, `INSERT` via MCP après validation._
5. Post fiche Google (AUTO-05).
6. Si chantier public : `liens-patrimoine.md`.

## Qualité minimale
- Titre : `<Type de travaux> – <bâtiment> à <commune>`
- ≥ 250 mots de faits réels, ≥ 4 photos avec alt descriptif.
- Lien vers 1 service + 1 commune.
