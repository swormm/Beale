# Versions Beale

## 3.3 — Confirmations Polymarket adaptées à l’écran

- Taille de texte ajustée à la largeur disponible sur le M5Stick.
- Identifiants longs affichés sur plusieurs lignes dans les confirmations concernées.
- Libellés IOC et FOK plus explicites.
- Prix et quantités conservés en entier dans les écrans d’ordre.

Compilation et signature RSA vérifiées pendant la préparation. La vérification du rendu sur un appareil physique reste distincte de ces contrôles.

## 3.2 — Connexion Polymarket mémorisée

- Conservation des identifiants de session dans la NVS chiffrée du profil protégé.
- Reprise après confirmation et PIN sur l’appareil, sans nouvelle liaison Phantom tant que l’autorisation reste valide.
- Autorisation de sept jours avec renouvellement à expiration.
- Déconnexion explicite, révocation ciblée et effacement local de la liaison.
- Possibilité de lier à nouveau le même compte ou un autre.

## 3.1 — Polymarket sur le M5Stick

- Page dédiée à la valeur du compte et au PnL non réalisé.
- Consultation de jusqu’à huit positions, avec un total incluant toutes les positions.
- Synchronisation depuis le dashboard et indication des données anciennes.

Ces notes décrivent les évolutions du projet. La présence d’une version ici ne signifie pas que son binaire est proposé dans une Release publique.
