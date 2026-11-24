# Backlog

_Une ligne par action. Mettre à jour le statut au fil de l'eau._

_Exécution : les actions se font **ici** ; SITE, CONT et AUTO sont ensuite publiées sur Lovable **via le MCP** (`04-lovable/README.md`), loguées dans `04-lovable/publications/`. GBP, CIT, AVIS-01/02 et LIEN se font sur les plateformes tierces._

## Phase 0 : point zéro (semaine 1)

| ID | Action | Prio | Resp. | Playbook | Statut | Date |
|---|---|---|---|---|---|---|
| MES-01 | Récupérer les accès propriétaire de la fiche Google | P0 | Nicolas / Emile | — | à faire | |
| MES-02 | Créer Search Console + Bing Webmaster Tools (domaine ecr-couverture.fr) | P0 | Emile | — | à faire | |
| MES-03 | Remplir la baseline (indicateurs fiche, geogrid 3 requêtes, avis, annuaires) | P0 | Emile / Claude | `playbooks/geogrid.md` | à faire | |
| MES-04 | Ajouter « comment nous avez-vous connus ? » à chaque prise de devis | P0 | Éric | — | à faire | |

## Phase 1 : fondations (mois 0-3)

### Marque et NAP
| ID | Action | Prio | Resp. | Playbook | Statut | Date |
|---|---|---|---|---|---|---|
| MARQ-01 | Valider le nom d'usage unique « ECR Couverture – Façade » + abandon de « Rénovation » | P0 | Nicolas | — | à faire | |
| CIT-01 | Inventorier toutes les fiches existantes (adresses, emails, sites, fax) | P0 | Claude | `playbooks/annuaires-nap.md` | à faire | |
| CIT-02 | Corriger PagesJaunes (catégorie, lien site, NAP) | P1 | Emile | `playbooks/annuaires-nap.md` | à faire | |
| CIT-03 | Créer / corriger Apple Business Connect, Bing Places | P1 | Emile | `playbooks/annuaires-nap.md` | à faire | |
| CIT-04 | Vérifier Qualibat, annuaire RGE France Rénov', CMA, CAPEB/FFB | P1 | Emile | `playbooks/annuaires-nap.md` | à faire | |
| CIT-05 | Nettoyer les annuaires secondaires (Esquelbecq, fax, « carreleur ») | P2 | Claude / Emile | `playbooks/annuaires-nap.md` | à faire | |
| CIT-06 | Rediriger ou supprimer les sites Wix, Solocal, tilda.ws | P1 | Emile | — | à faire | |

### Fiche Google
| ID | Action | Prio | Resp. | Playbook | Statut | Date |
|---|---|---|---|---|---|---|
| GBP-01 | Catégorie principale « Couvreur », supprimer Carreleur et Construction | P0 | Emile | `playbooks/fiche-google.md` | à faire | |
| GBP-02 | Corriger « Rue » → « Route » de Bergues | P0 | Emile | `playbooks/fiche-google.md` | à faire | |
| GBP-03 | Lister tous les services + description | P0 | Claude → Emile | `playbooks/fiche-google.md` | à faire | |
| GBP-04 | Ajouter 20-30 photos réelles de chantiers | P1 | Jérôme → Emile | `playbooks/fiche-google.md` | à faire | |
| GBP-05 | Ajouter le lien vers le nouveau site + horaires + zone desservie | P1 | Emile | `playbooks/fiche-google.md` | à faire | |
| GBP-06 | Publier 1 post / semaine (réalisation récente) | P1 | Claude → Emile | `playbooks/fiche-google.md` | à faire | |

### Avis
| ID | Action | Prio | Resp. | Playbook | Statut | Date |
|---|---|---|---|---|---|---|
| AVIS-01 | Répondre à tous les avis Google existants | P0 | Claude → Nicolas | `playbooks/reponse-avis.md` | à faire | |
| AVIS-02 | Répondre aux 4 avis PagesJaunes | P0 | Claude → Nicolas | `playbooks/reponse-avis.md` | à faire | |
| AVIS-03 | Mettre en place la demande d'avis à la réception (QR + SMS J+2 + relance J+7) | P0 | Emile | `playbooks/machine-avis.md` | à faire | |
| AVIS-04 | Imprimer les cartes QR code pour les chefs de chantier | P1 | Emile | `playbooks/machine-avis.md` | à faire | |
| AVIS-05 | Mention CNIL de la sollicitation d'avis dans les devis | P1 | Éric | `playbooks/machine-avis.md` | à faire | |
| OPS-01 | Engagement de délai d'envoi des devis + suivi (cause n°1 des avis négatifs) | P0 | Nicolas / Éric | — | à faire | |

### Site
| ID | Action | Prio | Resp. | Playbook | Statut | Date |
|---|---|---|---|---|---|---|
| SITE-01 | Reprise du projet existant « Heritage Roof Facade » (pas de nouveau projet) ; `04-lovable/projet.md` rempli | P0 | Claude | `04-lovable/audit-heritage-roof-facade.md` | fait | 2026-11-23 |
| SITE-02 | Prompt 2 : tables `realisations`, `communes`, `articles` en SSR + `/admin` de relecture | P0 | Claude | `04-lovable/lovable-prompt.md` | à faire | |
| SITE-02b | Prompt 2 bis : page « Nouveau chantier » (PWA téléphone, photos, note vocale transcrite, brouillon Claude) + comptes chefs d'équipe | P0 | Claude | `04-lovable/lovable-prompt.md` | à faire | |
| SITE-03 | Message 3 : textes des pages v1 (après SITE-04) | P0 | Claude | `03-contenus/pages/contenus-pages-v1.md` | à faire | |
| SITE-04 | Compléter tous les `[À COMPLÉTER]` des textes | P0 | Nicolas / Éric | — | à faire | |
| SITE-05 | Schema `RoofingContractor` + sitemap, canonical, og:image, lang fr, mentions légales | P0 | Claude | `04-lovable/schema-roofingcontractor.json` | fait (non publié) | 2026-11-24 |
| SITE-06 | Domaine ecr-couverture.fr branché, quitter Tilda | P0 | Emile | `04-lovable/checklist-technique.md` | à faire | |
| SITE-07 | Sitemap soumis, Search Console connectée | P0 | Emile | `04-lovable/checklist-technique.md` | à faire | |
| SITE-08 | Formulaire devis branché, envoi au secrétariat [adresse à confirmer] + suivi des conversions | P0 | Claude | `04-lovable/checklist-technique.md` | à faire | |
| SITE-09 | Mentions légales : page créée, compléter capital, TVA, hébergeur | P1 | Nicolas | — | en cours | 2026-11-24 |

### Contenus de lancement
| ID | Action | Prio | Resp. | Playbook | Statut | Date |
|---|---|---|---|---|---|---|
| CONT-01 | Réalisation : Église Saint-Martin de Wormhout | P0 | Jérôme → Claude → Nicolas | `playbooks/realisation-chantier.md` | à faire | |
| CONT-02 | 5 premières réalisations (photos disponibles) | P1 | Jérôme → Claude | `playbooks/realisation-chantier.md` | à faire | |
| CONT-03 | Télécharger le certificat Qualibat sur `/a-propos` et `/monuments-historiques` | P1 | Emile | — | à faire | |

### Corrections du site existant
| ID | Action | Prio | Resp. | Playbook | Statut | Date |
|---|---|---|---|---|---|---|
| SITE-10 | Supprimer entièrement la FAQ (section + liens de navigation) — décision Emile 24/11 | P0 | Claude | — | bloqué (crédits Lovable épuisés) | 2026-11-24 |

## Phase 2 : créneau patrimoine (mois 2-6)

| ID | Action | Prio | Resp. | Playbook | Statut | Date |
|---|---|---|---|---|---|---|
| CONT-10 | ≥ 5 fiches chantier patrimoine (églises, beffrois, bâtiments classés) | P1 | Jérôme → Claude | `playbooks/realisation-chantier.md` | à faire | |
| CONT-11 | Liste des marchés publics réalisés (28) sur la page MH | P1 | Claude | — | à faire | |
| CONT-12 | Pages « couvreur monuments historiques » Flandre / Dunkerquois / Audomarois | P2 | Claude → Nicolas | `playbooks/page-ville.md` | à faire | |
| CIT-10 | Inscription Groupement MH + Artisans du Patrimoine | P1 | Nicolas | `playbooks/annuaires-nap.md` | à faire | |
| LIEN-01 | Après chaque chantier public : kit photos + texte à la mairie | P1 | Emile | `playbooks/liens-patrimoine.md` | à faire | |
| LIEN-02 | Fondation du patrimoine : proposer les chantiers soutenus | P2 | Emile | `playbooks/liens-patrimoine.md` | à faire | |
| LIEN-03 | La Voix du Nord / presse locale : 1 sujet par grand chantier | P2 | Emile | `playbooks/liens-patrimoine.md` | à faire | |

## Phase 3 : croissance grand public (mois 3-12)

| ID | Action | Prio | Resp. | Playbook | Statut | Date |
|---|---|---|---|---|---|---|
| CONT-20 | Pages prix (toiture m², ardoise, zinc, démoussage, façade brique) à partir des devis réels | P1 | Éric → Claude | `playbooks/article-conseil.md` | à faire | |
| CONT-21 | Page urgence / tempête / assurance | P1 | Claude → Nicolas | `playbooks/article-conseil.md` | à faire | |
| CONT-22 | Page aides unique, sourcée, datée | P2 | Claude → Nicolas | `playbooks/article-conseil.md` | à faire | |
| CONT-23 | Pages ville, une par une (Dunkerque → Hazebrouck → Bergues → Cassel → …) | P1 | Claude | `playbooks/page-ville.md` | à faire | |
| CONT-24 | 2 articles conseils / mois | P1 | Claude → Nicolas | `playbooks/article-conseil.md` | à faire | |

## Phase 4 : marque et autorité (mois 6-18)

| ID | Action | Prio | Resp. | Playbook | Statut | Date |
|---|---|---|---|---|---|---|
| MARQ-03 | Créer la page LinkedIn entreprise | P2 | Emile | — | à faire | |
| MARQ-04 | Réactiver Facebook (repost des réalisations) | P2 | Claude → Emile | — | à faire | |
| MARQ-05 | Fiche Wikidata (sources officielles) | P2 | Emile | — | à faire | |

## Automatisations

| ID | Action | Prio | Resp. | Playbook | Statut | Date |
|---|---|---|---|---|---|---|
| AUTO-01 | Demande d'avis automatique (réception → SMS/email J+2, J+7) | P0 | Emile | `automatisations.md` | à faire | |
| AUTO-02 | Photos + note vocale → brouillon de fiche réalisation (couvert par SITE-02b) | P1 | Emile | `automatisations.md` | à faire | |
| AUTO-03 | Nouvel avis → réponse suggérée | P1 | Emile | `automatisations.md` | à faire | |
| AUTO-04 | Rapport SEO hebdo (Search Console + fiche Google) | P1 | Emile | `automatisations.md` | à faire | |
| AUTO-05 | Réalisation publiée → post fiche Google + réseaux | P2 | Emile | `automatisations.md` | à faire | |
| AUTO-06 | Veille réglementaire mensuelle (aides) | P2 | Emile | `automatisations.md` | à faire | |
| AUTO-07 | Brouillons d'articles depuis le calendrier éditorial | P2 | Emile | `automatisations.md` | à faire | |

## Échéances
| ID | Action | Date limite | Statut |
|---|---|---|---|
| OPS-10 | Vérifier le renouvellement Qualibat E-E59856 | 15/12/2026 | à faire |
| OPS-11 | Revoir la page aides après la loi de finances 2027 | 31/01/2027 | à faire |
