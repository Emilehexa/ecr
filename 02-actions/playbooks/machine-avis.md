# Playbook : machine à avis

_Actions : AVIS-03 à AVIS-05, AUTO-01. Fonction Cloud + table `chantiers_receptionnes`, construites via MCP (`send_message`)._

## Flux
1. **Devis** : mention « nous vous demanderons votre avis à la fin du chantier » (CNIL).
2. **Réception de chantier** : Virginie (ou le chef de chantier) saisit le chantier « réceptionné » dans le formulaire interne du site (nom, téléphone, email, commune, type de travaux).
3. **Sur place** : le chef de chantier laisse la carte QR code (lien direct vers le formulaire d'avis Google).
4. **J+2** : SMS / email automatique avec le lien.
5. **J+7** : une seule relance si pas d'avis.
6. **Tous les clients, sans filtre.** Pas de question « êtes-vous satisfait ? » avant d'envoyer le lien.

## Interdits
- Contrepartie (remise, cadeau) : DGCCRF, jusqu'à 300 k€ d'amende.
- Faux avis, avis de salariés ou de proches.
- Filtrer les clients satisfaits (« review gating »).

## Message type (SMS)
> Bonjour <Prénom>, merci d'avoir confié votre <toiture/façade> à ECR. Votre avis aide d'autres familles de Flandre à choisir leur couvreur : <lien>. Nicolas Geeraert, ECR Couverture – Façade

## Mesure
Avis reçus / chantiers réceptionnés (cible ≥ 30 %). Suivi mensuel dans `05-suivi/kpis.md`.
