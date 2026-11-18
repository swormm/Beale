# Sécurité de Beale

## Signaler une vulnérabilité

Utilisez **Security → Report a vulnerability** sur GitHub si le signalement privé est activé pour ce dépôt. S’il ne l’est pas, demandez un canal privé au mainteneur sans publier les détails exploitables d’une vulnérabilité ni des données sensibles dans une issue publique.

Indiquez le modèle, la version, le profil du firmware, le comportement attendu et les étapes de reproduction sur un appareil de test. Masquez les informations personnelles.

**Ne transmettez jamais :** clé privée Solana, phrase de récupération, clé de signature des firmwares, secret de session Polymarket, dump de flash ou sauvegarde contenant des clés.

## Périmètre des protections

Le profil protégé utilise Secure Boot V2, le chiffrement flash Release et le chiffrement NVS. Leur état dépend du provisionnement réel de l’appareil. Le PIN et les confirmations physiques s’ajoutent à ces protections ; ils ne remplacent pas la protection du navigateur ni la sauvegarde hors ligne.

Le M5Stick n’est pas présenté comme un appareil doté d’un Secure Element dédié. Aucun audit indépendant ou certification n’est revendiqué ici. Un firmware signé n’est pas une preuve d’absence de vulnérabilités.

Le dépôt ne distribue ni clé de signature, ni sauvegarde de wallet, ni code source. Les autorisations et la disponibilité du service Polymarket relèvent également de Polymarket.
