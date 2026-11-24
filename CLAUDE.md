# Instructions pour les agents

Ce repo porte la stratégie SEO d'ECR Couverture – Façade et son système d'actions. Lire `README.md` d'abord.

## Sources de vérité
- Faits sur l'entreprise : `00-contexte/entreprise.md`. Ne jamais écrire une coordonnée, un numéro de qualification, un effectif ou une date qui n'y figure pas.
- Ce qu'il faut faire : `02-actions/backlog.md`.
- Comment le faire : `02-actions/playbooks/`.

## Règles
- **Ne rien inventer.** Pas de chantier, de prix, d'avis, de témoignage ou de chiffre fictif. Si une info manque, écrire `[À COMPLÉTER : …]`.
- **NAP identique partout** : ECR Couverture – Façade · 2470 Route de Bergues, 59470 Wormhout · 03 28 65 65 31 · contact@ecr-couverture.fr.
- Écrire « qualification Qualibat 3194 (couverture monuments historiques) », jamais « agréé Monuments Historiques ». **Exception décidée par Emile le 24/11/2026** : les mentions « Monuments Historiques / Entreprise agréée » déjà présentes sur le site Lovable sont conservées, ne pas y toucher. Ne pas en ajouter de nouvelles.
- Nom légal : Entreprise de Construction et de **Restauration** (pas « Rénovation »).
- Aides financières (MaPrimeRénov', etc.) : toujours vérifier la règle en vigueur et dater la page. Depuis le 01/09/2026, l'isolation de toiture n'est plus financée par geste (décret 2026-822).
- Pas de page ville sans chantier réel documenté dans la commune (risque « doorway pages »).
- Pas de n8n : automatisations codées dans le projet Lovable ou en tâches Claude.

## Exécution ici, publication via le MCP Lovable
Les actions se font dans ce repo ; Lovable sert uniquement à publier, via les outils `mcp__claude_ai_Lovable__*`. Procédure complète : `04-lovable/README.md`.
- Produire le contenu dans `03-contenus/` en suivant le playbook.
- **Ne publier que ce qui est validé par un humain** : `statut: validé` + `valide_par` dans le repo, ou publié par l'équipe dans `/admin`. Sinon, s'arrêter et demander.
- Réalisations : elles arrivent du terrain en `brouillon` dans la base (page « Nouveau chantier ») ; les récupérer via `query_database` pour relecture ici.
- Contenus dynamiques → `query_database` (SELECT avant UPDATE ; jamais de DELETE/DROP sans accord d'Emile). Code/site → `send_message` (plan_mode pour les gros changements), puis `deploy_project`.
- IDs du projet : `04-lovable/projet.md`. Loguer chaque publication dans `04-lovable/publications/`.
- Pas de code applicatif dans ce repo : le code vit dans Lovable.

## Quand une action est terminée
1. Vérifier la page en ligne.
2. Passer son statut à `fait` dans `02-actions/backlog.md`, avec la date.
3. Ajouter une ligne dans `05-suivi/journal.md`.
4. Si l'action révèle un nouveau fait sur l'entreprise, mettre à jour `00-contexte/entreprise.md`.
