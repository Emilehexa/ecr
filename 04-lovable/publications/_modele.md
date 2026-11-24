# <AAAA-MM-JJ> <ID> : <titre>

- Action backlog : <ID>
- Source validée : `<chemin du fichier>` (valide_par : <nom>)
- Canal : query_database | send_message | deploy_project
- Statut : envoyé | vérifié | échec

## Envoi
<requête SQL exécutée, ou message envoyé à l'agent Lovable (+ message_id)>

## Résultat
<réponse MCP, diff résumé, URL>

## Vérification
- [ ] Page en ligne, contenu identique au fichier validé
- [ ] Code source HTML contient le contenu (SSR)
- [ ] Checklist technique si changement de code
