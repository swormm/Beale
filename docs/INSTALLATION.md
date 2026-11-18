# Installer une mise à jour Beale

## Vérifier la compatibilité

Ce guide concerne un **M5StickC Plus2 déjà provisionné pour Beale protégé**, disposant du mode Recovery et de la clé de confiance correspondant au firmware de la Release.

Un fichier `.bin` applicatif signé ne suffit pas à installer Beale sur un appareil vierge. Le provisionnement initial concerne aussi le bootloader, le partitionnement et des eFuses irréversibles. Aucun parcours générique de provisionnement initial n’est fourni dans ce dépôt.

Avant une mise à jour, conservez une sauvegarde hors ligne vérifiée du wallet. Ne communiquez jamais votre clé privée, votre PIN ou un dump de flash.

## Mise à jour depuis le navigateur

1. Consultez les notes de la Release et vérifiez le matériel et le profil ciblés.
2. Branchez le M5Stick avec un câble USB de données et fermez les moniteurs série utilisant son port.
3. Maintenez **B au démarrage** jusqu’à voir **BEALE RECOVERY / Mise à jour USB**.
4. Ouvrez [la page firmware](https://app.beale.pro/firmware) dans un navigateur de bureau compatible Web Serial, par exemple Chrome ou Edge.
5. Utilisez le parcours **mise à jour signée** et sélectionnez le port du M5Stick. Si la page propose de choisir un fichier, utilisez le binaire signé de la Release compatible.
6. Attendez la validation et le redémarrage sans débrancher l’appareil.
7. Vérifiez la version affichée sur l’appareil et l’adresse de réception du réseau utilisé.

La version proposée sur le site peut dépendre de son déploiement. Comparez-la à la Release avant de lancer la mise à jour.

**N’utilisez pas un flash brut, un effacement complet ou une commande `--force` comme alternative au parcours Recovery d’un appareil protégé.**

## Vérifier le téléchargement

Les Releases fournissent un fichier `SHA256SUMS.txt`. Sous PowerShell :

```powershell
Get-FileHash .\beale-v3.3-m5stickc-plus2-signed.bin -Algorithm SHA256
```

Comparez le résultat à l’empreinte de la Release. SHA-256 détecte une différence de fichier ; la vérification cryptographique par l’appareil établit la compatibilité avec sa clé de confiance. Une empreinte publiée sur la même page n’est pas une preuve indépendante de provenance.

## Résoudre les problèmes courants

| Symptôme | À vérifier |
| :--- | :--- |
| Aucun port proposé | Câble de données, connexion USB, navigateur compatible et autorisation du port. |
| Port occupé | Fermer le moniteur série, les outils Arduino et les autres onglets connectés. |
| `No response: BEALE OTA READY` | Appareil allumé, bon port, Recovery effectivement affiché et port libre. |
| `ESP_ERR_OTA_VALIDATE_FAILED` | Fichier complet, signature et compatibilité avec cet appareil. Ne pas contourner la validation. |
| Écran Recovery après une mise à jour | Vérifier les notes de la version et les boutons maintenus au démarrage. Un firmware Recovery seul n’est pas le dashboard wallet. |
| Solde absent sur le dashboard | Connexion au M5Stick, réseau choisi et accès au RPC ; un solde absent ne prouve pas une perte de fonds. |

Pour demander de l’aide, indiquez la version, le modèle, le navigateur et le message exact. N’ajoutez ni sauvegarde du wallet ni identifiants de session.
