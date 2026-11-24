# Architecture du site

_Détail des textes : `03-contenus/pages/contenus-pages-v1.md`. Prompts de construction : `04-lovable/lovable-prompt.md`._

```
/                               Accueil
/monuments-historiques          Couverture MH et patrimoine        ← page pilier patrimoine
/couverture-toiture             Réfection de toiture
/couverture-ardoise             Couverture ardoise
/couverture-tuile               Couverture tuile (dont flamande)
/zinguerie                      Zinguerie, gouttières, chéneaux
/ravalement-facade              Façade, ravalement, brique
/isolation-toiture              Isolation de toiture (RGE)
/fuite-toiture-urgence          Fuite et urgence
/realisations                   Liste des chantiers (filtrable)
/realisations/<slug>            Une fiche par chantier            ← dynamique (base)
/zones-intervention             Page centrale zones
/couvreur-<ville>               Pages ville                       ← dynamique, sous conditions
/guides/<slug>                  Articles conseils                 ← dynamique
/prix/<slug>                    Pages prix                        ← dynamique
/a-propos                       Histoire, équipe, qualifications
/contact                        Devis + coordonnées
/mentions-legales
```

## Règles d'ajout de pages
- **Page ville** : seulement avec au moins 2 chantiers documentés dans la commune (ou 1 chantier patrimoine), du contenu propre à la ville (bâti local, matériaux, contraintes ABF), et des liens vers ces réalisations.
- **Réalisation** : photos réelles + faits validés par le terrain. Pas de plafond.
- **Prix** : fourchettes tirées de vrais devis ECR, page datée, revue tous les 6 mois.
- **Aides** : une seule page, sourcée, revue à chaque loi de finances.

## Maillage interne
- Chaque réalisation → service concerné + ville.
- Chaque page ville → ses réalisations + services.
- Chaque page service → 3 réalisations récentes + page prix associée.
