# Vérification NEXORIA (gratuit, GitHub Pages)

Site statique : aucun serveur à payer. Le QR code du certificat pointe vers `https://<compte>.github.io/<dépôt>/?code=NX-…`.

## Mise en ligne (une fois)
1. Crée un dépôt public sur GitHub, par exemple `nexoria-verif`.
2. Mets-y ces trois fichiers : `index.html`, `verifications.json`, `README.md`.
3. Dans le dépôt : Settings → Pages → Source : « Deploy from a branch », branche `main`, dossier `/ (root)`.
4. L'adresse est alors `https://<ton-compte>.github.io/nexoria-verif/`.
5. Indique cette adresse à l'équipe pour générer les PDF (option `--verif-base` du générateur).

## Ajouter ou valider un document
Dans `verifications.json`, ajoute une entrée par document, après contrôle humain :
- `code` : le code imprimé sur le certificat ;
- `statut` : `valide` une fois le document contrôlé, sinon `en_attente` ;
- `mis_a_jour` : la date de la modification.

Puis « Commit changes » sur GitHub. La page est mise à jour en une minute environ.

## Règles
- Ne passe jamais un document en `valide` sans contrôle humain.
- Supprime les entrées de test avant la mise en service.
- La page n'affiche ni le nom de l'élève ni l'établissement, pour protéger les données personnelles.
