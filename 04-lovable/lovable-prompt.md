# Prompt Lovable : site ECR Couverture – Façade

> Envoyés via le MCP Lovable (`create_project` pour le prompt 1, puis `send_message` pour 2, 2 bis et 3), pas copiés à la main. Projet cible : un **nouveau projet** Lovable. Les projets créés depuis mai 2026 utilisent TanStack Start avec rendu côté serveur, que les moteurs de recherche et les IA lisent sans difficulté. Active **Lovable Cloud** dès le départ, car le site s'appuie sur une base de données. Construis le site en 4 prompts successifs (1, 2, 2 bis, 3), pas d'un seul coup.

---

## PROMPT 1 : structure, design, SEO technique

Construis le site vitrine multi-pages d'**ECR Couverture – Façade**, entreprise familiale de couverture, zinguerie, façade et restauration du patrimoine, installée à Wormhout (Nord) depuis 1981. Le site doit générer des **demandes de devis** et des **appels**. Il s'adresse à deux publics : les particuliers de Flandre et du Dunkerquois, et les maîtres d'ouvrage du patrimoine (mairies, architectes du patrimoine, diocèses).

### Identité visuelle
- Couleurs : doré `#E5A930` (accent et boutons), anthracite `#4A4A4A`, encre `#1A1A1A`, fond blanc cassé `#F8F7F5`.
- Typographies : **Fraunces** pour les titres, **Source Sans 3** pour le texte.
- Ton artisanal, familial et sérieux. Pas de style startup tech, ni d'illustrations génériques ou de photos de stock. Les emplacements photo restent des blocs neutres légendés « photo chantier à venir » tant que les vraies photos manquent.
- Mobile d'abord : la plupart des visiteurs arrivent depuis Google sur téléphone. Un bouton « Appeler » collant en bas d'écran sur mobile, avec un lien `tel:+33328656531`.

### Coordonnées (à reprendre à l'identique partout)
- Nom affiché : **ECR Couverture – Façade**
- Adresse : **2470 Route de Bergues, 59470 Wormhout**
- Téléphone : **03 28 65 65 31**
- Email : **contact@ecr-couverture.fr**
- Nom légal (mentions légales et données structurées uniquement) : Entreprise de Construction et de Restauration (ECR), SAS, SIREN 322 814 252, RCS Dunkerque, siège social 19 place Alphonse Bergerot, 59470 Esquelbecq.

### Arborescence (une vraie URL par page, pas de one-page à ancres)
```
/                                   Accueil
/couverture-toiture                 Réfection et rénovation de toiture
/couverture-ardoise                 Couverture ardoise
/couverture-tuile                   Couverture tuile (dont tuile flamande)
/zinguerie                          Zinguerie, gouttières, chéneaux
/ravalement-facade                  Ravalement et rénovation de façade brique
/isolation-toiture                  Isolation de toiture (RGE)
/fuite-toiture-urgence              Recherche de fuite, réparation, après tempête
/monuments-historiques              Couverture des monuments historiques et du patrimoine
/realisations                       Liste des chantiers (filtrable par service et par commune)
/realisations/[slug]                Fiche chantier
/zones-intervention                 Page centrale des zones
/couvreur-[commune]                 Pages ville (dynamiques, voir prompt 2)
/conseils                           Liste des articles
/conseils/[slug]                    Article
/a-propos                           Histoire, équipe, qualifications
/devis                              Formulaire de devis
/contact
/mentions-legales
```
Navigation principale : Services (menu déroulant), Monuments historiques, Réalisations, Zones, À propos, plus le bouton doré « Demander un devis ». Fil d'Ariane sur toutes les pages internes.

### SEO technique (obligatoire)
- Pour chaque page : `<title>` et meta description **uniques**, un seul `<h1>`, une hiérarchie H2/H3 propre, une URL canonique et des balises Open Graph.
- `lang="fr"`.
- `robots.txt` qui autorise tout le site et pointe vers le sitemap.
- `sitemap.xml` **dynamique** qui inclut les réalisations, les pages ville et les articles publiés depuis la base.
- Images en WebP, chargement différé sous la ligne de flottaison, `width` et `height` explicites, attribut `alt` descriptif (« Réfection couverture ardoise, église Saint-Martin, Wormhout »).
- Données structurées JSON-LD :
  - Sur l'accueil et le contact : `RoofingContractor` avec `name`, `legalName`, `alternateName` (["ECR", "E.C.R.", "ECR Couverture"]), `foundingDate` « 1981 », `address`, `telephone`, `email`, `url`, `geo` (Wormhout), `areaServed` (liste des communes), `identifier` (SIREN), `hasCredential` (Qualibat certificat E-E59856, RGE), `sameAs` (laisser un tableau vide à compléter).
  - `Service` sur chaque page service.
  - `BreadcrumbList` partout.
  - Pas de `FAQPage`, Google l'a abandonné.
  - Pas d'étoiles d'avis auto-attribuées.
- Pas de texte caché, pas de listes de villes en bas de page.

### Conversion
- Formulaire de devis enregistré en base, table `demandes_devis` : nom, téléphone, email, commune, type de travaux (liste des services), message, photos facultatives, page d'origine, source déclarée (« Comment nous avez-vous connus ? » : Google, bouche-à-oreille, PagesJaunes, réseaux sociaux, autre).
- Envoi d'une notification email à contact@ecr-couverture.fr à chaque demande.
- Le numéro de téléphone est cliquable partout.

---

## PROMPT 2 : contenus dynamiques (alimentés automatiquement plus tard)

Crée dans Lovable Cloud les tables suivantes. Les pages correspondantes sont **rendues côté serveur** à partir de ces tables : chaque nouvelle ligne publiée devient une page indexable **sans republier le site**.

**`realisations`** : id, slug, titre, commune, code_postal, services (tableau parmi les slugs de service), type_batiment (maison, immeuble, église, monument classé, bâtiment public…), date_chantier, probleme, solution, materiaux, duree, temoignage_client (facultatif), photos (tableau d'URL avec légende et type avant/pendant/après), meta_title, meta_description, statut (`brouillon` | `publie`), created_at.
- Page `/realisations/[slug]` : galerie avant/après, encadré des caractéristiques (commune, matériaux, durée), texte, liens vers le service concerné et la page de la commune, puis un appel « Un projet similaire ? Demandez un devis ».

**`communes`** : slug, nom, code_postal, intro_specifique (texte propre à la commune : habitat, contraintes locales), distance_wormhout_km, statut.
- Page `/couvreur-[slug]` : affichée **seulement si la commune a au moins un chantier publié**. Elle montre l'intro spécifique, les chantiers de la commune, les services, le délai d'intervention et l'appel au devis. On ne génère jamais de page ville sans contenu propre.

**`articles`** : slug, titre, categorie (prix, guide, urgence, réglementation, patrimoine), contenu (markdown), auteur, date_publication, date_mise_a_jour, meta_title, meta_description, statut.
- Les pages articles affichent l'auteur et les deux dates.

**Mini back-office** `/admin`, protégé par authentification et réservé à l'équipe ECR : liste des brouillons de réalisations et d'articles, aperçu, boutons « Publier » et « Modifier ». C'est l'étape de validation humaine obligatoire.

Les automatisations (fonctions serveur) écrivent directement dans ces tables avec une clé de service côté serveur, jamais exposée au client.

---

## PROMPT 2 bis : « Nouveau chantier » depuis le téléphone

Ajoute dans `/admin` une page **« Nouveau chantier »** pensée pour un chef d'équipe sur son téléphone, sur le chantier, en moins de 2 minutes :
- **Photos** : bouton qui ouvre l'appareil photo ou la galerie, envoi de plusieurs photos à la fois. Pour chaque photo, un choix rapide avant / pendant / après. Les photos sont compressées côté client (WebP, 2000 px max) puis stockées dans Lovable Cloud Storage.
- **Commune** : liste avec recherche, alimentée par la table `communes`, avec possibilité d'en ajouter une.
- **Services** : cases à cocher, parmi les slugs des services.
- **Type de bâtiment** : liste.
- **« Racontez le chantier »** : champ texte **avec bouton micro**. On enregistre une note vocale, transcrite automatiquement (fonction serveur de transcription). On y décrit le problème, ce qui a été fait, les matériaux et les difficultés.
- **Bouton « Envoyer »** : crée une ligne `realisations` avec statut `brouillon`, puis déclenche une fonction serveur qui appelle l'API Claude pour rédiger le titre, le texte (problème, solution, matériaux), la meta title, la meta description et les légendes `alt` des photos, **uniquement à partir des informations saisies**, sans rien inventer.

Le brouillon apparaît ensuite dans la liste `/admin` pour relecture, puis on clique sur « Publier ».

Le bouton « Nouveau chantier » est accessible depuis l'écran d'accueil du téléphone (PWA, « Ajouter à l'écran d'accueil »). Il faut des comptes simples, un par chef d'équipe.

---

## PROMPT 3 : textes des pages

Remplace les textes provisoires par le contenu fourni dans `contenus-pages.md` (rédigé séparément). Ne modifie pas les faits : qualifications, dates, coordonnées.

---

## Après publication
1. Brancher le domaine **ecr-couverture.fr** sur Lovable (Settings → Domains). Couper l'ancien site Tilda.
2. Onglet SEO & AI de Lovable : lancer la revue, connecter **Google Search Console**, envoyer le sitemap.
3. Ajouter le site dans **Bing Webmaster Tools** (import possible depuis Google Search Console).
4. Mettre l'URL du site sur la fiche Google, Facebook et PagesJaunes.
