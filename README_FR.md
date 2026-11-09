# AFRICA DIGITAL MONEY — version paiement MTN par QR avec validation manuelle

Cette version est une boutique web exécutable avec catalogue, formulaire de commande, QR fourni par le propriétaire, base SQLite et tableau de bord administrateur. Une commande reste `PENDING` jusqu'à ce que l'administrateur vérifie réellement le paiement dans MTN puis clique sur « Confirmer payé ».

## Limite essentielle sur le QR
L'image intégrée est recadrée depuis la capture d'écran fournie. La capture indique « Mon Code QR », mais ne prouve pas que ce code est un QR marchand MoMo. MTN décrit le QR marchand comme lié à un Merchant ID et un nom marchand. Faites confirmer par MTN que ce QR personnel peut recevoir des paiements de clients pour une activité commerciale avant de publier le site. Ne prétendez pas que les paiements sont automatiques.

## Installation et lancement
- Installer Node.js 20+ sur un ordinateur ou serveur.
- Décompresser le ZIP.
- Copier `.env.example` en `.env` et définir un mot de passe administrateur long et unique.
- Lancer `npm install`, puis `npm start`.
- Ouvrir `http://localhost:3000`.
- Tableau de bord : `http://localhost:3000/admin` (identifiants dans `.env`).
- Pour un vrai site public, déployer sur un hébergeur Node.js avec HTTPS et stockage persistant. Ne pas utiliser le serveur de développement sur un hébergement éphémère.

## Personnalisation avant lancement
- Modifier `products.json` avec les vrais noms, descriptions et prix.
- Placer chaque PDF dans `private-products/` avec le nom de fichier défini dans `products.json`.
- Le téléchargement est accessible uniquement après validation manuelle du statut.
- Confirmer le bénéficiaire du QR et les conditions MTN. Si MTN exige un compte marchand, il faudra l'obtenir. La page MTN Côte d'Ivoire indique pour l'acceptation marchande une fiche de souscription, un RCCM et des pièces d'identité : https://www.mtn.ci/momo/business/.

## Sécurité
- Le code QR n'est pas un mécanisme de confirmation de paiement.
- Le vendeur doit vérifier le crédit reçu dans son application MTN avant de valider une commande.
- Ne jamais demander au client son PIN ou son OTP.
- Changer impérativement le mot de passe administrateur avant toute mise en ligne.
- Ajouter sauvegardes, limitation de débit, HTTPS, journalisation et tests de sécurité avant usage commercial.
