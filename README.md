# SEO ECR Couverture – Façade

Stratégie SEO et système d'actions pour **ECR Couverture – Façade** (Wormhout, 59), couvreur familial depuis 1981.

Le repo suit une logique simple : **la stratégie dit quoi et pourquoi, le système d'actions dit qui fait quoi, quand, et comment on sait que c'est fait.** Les actions se font ici ; Lovable sert uniquement à publier, via le MCP.

## Structure

```
00-contexte/        Faits sur l'entreprise : la source de vérité
  entreprise.md       Identité, coordonnées canoniques (NAP), qualifications
  audit-2026-11.md    État des lieux au départ
  concurrents.md      Paysage concurrentiel local et patrimoine

01-strategie/       Le quoi et le pourquoi
  strategie-seo.md    Stratégie complète (recherche du 23/11/2026)
  positionnement.md   Les deux marchés, la promesse, ce qu'on ne fait pas
  mots-cles.md        Requêtes cibles par grappe et par priorité
  architecture-site.md Arborescence cible et règles d'ajout de pages
  roadmap.md          Phases, jalons, objectifs

02-actions/         Le système d'actions
  README.md           Comment le système fonctionne (statuts, règles)
  backlog.md          Toutes les actions, avec ID, phase, priorité, statut
  cadence.md          Rituels hebdo / mensuel / trimestriel
  automatisations.md  Ce qui est automatisé, ce qui reste humain
  playbooks/          Procédures répétables, pas à pas

03-contenus/        Production éditoriale
  calendrier-editorial.md
  pages/              Textes des pages fixes
  realisations/       Une fiche par chantier (+ _modele.md)
  articles/           Guides et pages prix (+ _modele.md)
  villes/             Pages ville (+ _modele.md)

04-lovable/         Publication sur Lovable via le MCP
  README.md           Flux : produire ici → valider → publier (MCP) → vérifier
  projet.md           project_id, tables, mapping repo → base
  lovable-prompt.md   Messages de construction initiale du site
  publications/       Log de chaque publication (+ _modele.md)
  checklist-technique.md
  schema-roofingcontractor.json

05-suivi/           Mesure
  kpis.md             Indicateurs, cibles, sources
  baseline.md         Point zéro (à remplir)
  journal.md          Ce qui a été fait, daté
  annuaires.md        Inventaire NAP par annuaire
  rapports/           Rapports mensuels
```

## Règles du repo

1. **Aucun fait inventé.** Tout ce qui est publié vient de `00-contexte/` ou du terrain (photos, devis réels, notes vocales). Les trous sont marqués `[À COMPLÉTER : …]`.
2. **Le terrain fournit les faits, Claude rédige, un humain valide.** Rien n'est publié sans relecture.
3. **Une action = une ligne dans `02-actions/backlog.md`.** Quand elle est faite, on la passe en `fait` et on l'écrit dans `05-suivi/journal.md`.
4. **Les actions se font ici, la publication passe par le MCP Lovable** : contenus dynamiques écrits en base (`query_database`), changements de site envoyés à l'agent Lovable (`send_message`), puis `deploy_project`. Voir `04-lovable/README.md`. Seules les plateformes tierces (fiche Google, annuaires) restent manuelles.
5. **Pas de n8n.** Les automatisations sont codées dans le projet (fonctions Lovable Cloud, tâches Claude planifiées).
6. Langue du repo : français.

## Par où commencer

1. Lire `01-strategie/strategie-seo.md` (15 min).
2. Ouvrir `02-actions/backlog.md` et filtrer sur `P0`.
3. Remplir `05-suivi/baseline.md` avant de toucher à quoi que ce soit, sinon on ne pourra pas mesurer l'effet.
