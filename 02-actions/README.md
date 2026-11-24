# Système d'actions

La stratégie (`01-strategie/`) se traduit ici en actions concrètes, suivies jusqu'au résultat.

## Les 4 briques

| Brique | Fichier | Rôle |
|---|---|---|
| Backlog | `backlog.md` | La liste unique de tout ce qu'il y a à faire |
| Playbooks | `playbooks/*.md` | Comment faire une tâche répétable, pas à pas |
| Cadence | `cadence.md` | Quand on regarde quoi (hebdo, mensuel, trimestriel) |
| Automatisations | `automatisations.md` | Ce qui tourne tout seul, ce qui demande une validation |

## Format d'une action

`| ID | Action | Phase | Prio | Responsable | Playbook | Statut | Date |`

- **ID** : préfixe par chantier + numéro (voir ci-dessous). Ne change jamais.
- **Prio** : `P0` bloquant / cette semaine · `P1` ce mois · `P2` plus tard.
- **Statut** : `à faire` → `en cours` → `bloqué (raison)` → `fait`.
- **Responsable** : Emile, Nicolas, Éric, Jérôme, Virginie, Claude.

| Préfixe | Chantier |
|---|---|
| MES | Mesure / baseline |
| GBP | Fiche Google Business Profile |
| AVIS | Avis clients |
| OPS | Process interne (devis, réception) |
| CIT | Annuaires et cohérence NAP |
| SITE | Site Lovable et technique |
| CONT | Contenus (pages, réalisations, articles) |
| LIEN | Liens et mentions tierces |
| MARQ | Marque et réseaux sociaux |
| AUTO | Automatisations |

## Cycle de vie
1. Une idée ou un constat → nouvelle ligne `à faire` dans le backlog.
2. Revue hebdo (`cadence.md`) : on choisit les actions de la semaine.
3. Exécution ici (playbook → contenu dans le repo → validation humaine), puis publication sur Lovable via le MCP et vérification (voir `04-lovable/README.md`).
4. `fait` + ligne dans `05-suivi/journal.md`.
5. Si l'action se répète, on écrit (ou on met à jour) son playbook. Si elle peut tourner seule, elle part dans `automatisations.md`.
