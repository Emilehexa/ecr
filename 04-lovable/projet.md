# Projet Lovable

| Champ | Valeur |
|---|---|
| Workspace | « OLD - Hexa's Lovable » (`to0iLgRi1rH2CM99O22n`), plan free |
| Projet | **Heritage Roof Facade** |
| project_id | `53c1a73a-c6ea-4ad0-aee0-e04ef6db3763` |
| Stack | TanStack Start (SSR) + Lovable Cloud (Postgres) |
| Domaine | ecr-couverture.fr (à brancher, SITE-06) |
| Éditeur | https://lovable.dev/projects/53c1a73a-c6ea-4ad0-aee0-e04ef6db3763 |
| Preview | https://id-preview--53c1a73a-c6ea-4ad0-aee0-e04ef6db3763.lovable.app |
| Publié | non |
| Base activée | non |

## Tables de contenu (créées par SITE-02, voir `lovable-prompt.md` message 2)
Mapping fichier du repo → ligne en base. Le `slug` est la clé commune. `statut` : `brouillon` | `publie`. Photos dans Lovable Cloud Storage (WebP, 2000 px max).

| Table | Source dans le repo | Colonnes (prévues) |
|---|---|---|
| `realisations` | `03-contenus/realisations/*.md` | slug, titre, commune, code_postal, services[], type_batiment, date_chantier, probleme, solution, materiaux, duree, temoignage_client, photos, meta_title, meta_description, statut |
| `communes` | `03-contenus/villes/*.md` | slug, nom, code_postal, intro_specifique, distance_wormhout_km, statut |
| `articles` | `03-contenus/articles/*.md` (dont pages prix : categorie = prix) | slug, titre, categorie, contenu, auteur, date_publication, date_mise_a_jour, meta_title, meta_description, statut |
| `chantiers_receptionnes` | — (à ajouter pour AUTO-01, pas encore dans les prompts) | client, telephone, email, commune, date_reception, avis_demande_j2, relance_j7 |

## Comptes
- `/admin` : un compte par chef d'équipe (prompt 2 bis) + Nicolas, Emile. [À COMPLÉTER : liste]

Vérifier le schéma réel après SITE-02 : `SELECT table_name, column_name FROM information_schema.columns WHERE table_schema = 'public' ORDER BY 1;`
