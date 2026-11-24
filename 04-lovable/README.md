# Lovable : publication via le MCP

**Les actions se font ici, dans ce repo.** Lovable ne sert qu'à publier, via le MCP Lovable (`mcp__claude_ai_Lovable__*`). Personne ne copie-colle de prompt dans l'éditeur.

Deux flux, selon l'origine du contenu :

**A. Contenus rédigés ici** (articles, prix, pages ville, pages fixes, modifs du site)
```
backlog.md (action)
   → production ICI dans 03-contenus/ (statut: brouillon)
   → validation humaine ICI (statut: validé, valide_par)
   → publication via MCP (query_database ou send_message)
   → vérification → log publications/ → backlog fait + journal.md
```

**B. Réalisations venues du terrain** (prompt 2 bis : page « Nouveau chantier » sur téléphone)
```
chef d'équipe : photos + note vocale → ligne `realisations` statut brouillon (rédigée par Claude côté Lovable)
   → ICI : je récupère les brouillons (SELECT via MCP) dans 03-contenus/realisations/<slug>.md
   → relecture / enrichissement ici (maillage, cohérence avec 00-contexte)
   → validation : Nicolas ou Jérôme, dans /admin (bouton Publier) ou ici (statut: validé)
   → si corrigé ici : UPDATE via MCP, puis statut publie
   → vérification → log publications/ → journal.md
```

## Projet cible
Voir `projet.md` (project_id, workspace_id, domaine, tables). À remplir à la création du projet (SITE-01).

## Deux canaux de publication

| Canal | Outil MCP | Pour quoi | Pourquoi |
|---|---|---|---|
| **Données** | `query_database` (INSERT / UPDATE) | Contenus dynamiques : `realisations`, `communes`, `articles` | Direct, déterministe, ne consomme pas de crédits agent, le texte publié = le texte validé |
| **Code** | `send_message` (+ `get_diff`, `get_message`) | Structure, design, pages fixes, schema, SEO technique, fonctions Cloud (AUTO-*) | Seul l'agent Lovable modifie le code |
| Mise en ligne | `deploy_project` | Après un changement de code | Une URL retournée ne prouve pas que c'est en ligne : vérifier |

Les contenus en base s'affichent sans redéploiement (rendu SSR depuis la base). Les changements de code demandent `deploy_project`.

## Règles
- **Rien n'est publié sans validation humaine** : `statut: validé` + `valide_par` dans le repo, ou clic « Publier » dans `/admin` (flux B).
- Le repo est la source de vérité pour le flux A. Pour le flux B, la base est la source : le repo en garde une copie synchronisée (`publie_le`), mise à jour à chaque revue hebdo.
- `send_message` : gros changement → `plan_mode: true` d'abord, puis exécution. Toujours rappeler le NAP et les règles de `CLAUDE.md`. Préciser ce qui ne doit pas changer.
- `query_database` : écritures en production. Un SELECT avant chaque UPDATE ; jamais de DELETE / DROP sans accord explicite d'Emile.
- Si Lovable renvoie `awaiting_input` : montrer la demande à Emile, ne pas relancer un `send_message` par-dessus.
- Chaque publication est loguée dans `publications/` (modèle : `publications/_modele.md`).

## Fichiers
- `projet.md` : identifiants du projet et schéma des tables.
- `lovable-prompt.md` : les messages de construction (prompts 1, 2, 2 bis, 3 → SITE-01, SITE-02, SITE-02b, SITE-03).
- `publications/` : log de chaque envoi (message ou requête, résultat, vérification).
- `checklist-technique.md`, `schema-roofingcontractor.json`.
