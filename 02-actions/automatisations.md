# Automatisations

_Décision du 23/11/2026 : **pas de n8n**. Les fonctions Lovable Cloud sont construites via le MCP (`send_message`) ; le reste tourne en tâches Claude planifiées depuis ce repo. Tout brouillon généré atterrit dans ce repo pour validation avant publication._

| ID | Automatisation | Déclencheur → sortie | Validation humaine | Statut |
|---|---|---|---|---|
| AUTO-01 | Demande d'avis | Chantier réceptionné (formulaire / Sheet / EBP) → SMS ou email J+2, relance J+7, à **tous** les clients | Non | à cadrer |
| AUTO-02 | Chantier → fiche réalisation | Page « Nouveau chantier » (prompt 2 bis) : photos + note vocale → transcription → brouillon Claude en base → relecture `/admin` ou repo | **Oui** | à cadrer |
| AUTO-03 | Réponse aux avis | Nouvel avis Google → réponse suggérée | **Oui** | à cadrer |
| AUTO-04 | Rapport SEO hebdo | API Search Console + indicateurs fiche Google → email | Non | à cadrer |
| AUTO-05 | Posts fiche Google / réseaux | Réalisation publiée → post court | Optionnel | à cadrer |
| AUTO-06 | Veille réglementaire | Mensuelle (service-public, Anah) → alerte « page aides à revoir » | Oui | à cadrer |
| AUTO-07 | Brouillons d'articles | Calendrier éditorial → brief → brouillon Claude à partir des données ECR | **Oui** | à cadrer |

## Fiche de cadrage (à copier pour chaque automatisation)

```
### AUTO-XX : <nom>
- Déclencheur :
- Données d'entrée (où, quel format) :
- Traitement :
- Sortie (où, quel format) :
- Validation humaine (qui, où) :
- Garde-fous (ce qui ne doit jamais arriver) :
- Coût estimé / mois :
- Mesure de succès :
```

## Garde-fous communs
- Aucune publication automatique de contenu rédigé par l'IA sans validation.
- Aucun filtrage des clients pour les demandes d'avis (interdit par Google).
- Aucune contrepartie contre un avis (DGCCRF).
- Les brouillons ne contiennent que des faits présents dans les entrées (photos, note vocale, `00-contexte/entreprise.md`).
