# Vérifications Lumen V1.2

Réalisées le **19 octobre 2026** sur une machine de test jetable, plus une session XFCE isolée pour l’affichage. **Rien n’a été installé sur le PC de l’utilisateur.**

## Testé réellement

| Contrôle | Résultat |
|---|---|
| Construction du paquet `lumen-release_1.2.0_all.deb` à partir du paquet 1.1.0 scellé | Réussi ; tous les anciens fichiers de langue, curseur et mise à jour sont conservés |
| Signature du dépôt avec la clé Lumen | `Good signature`, empreinte `EDEF2384E284EE81BA30859935FF6549F7CAE0C4` |
| Installation réelle sur un disque Lumen V1.1 démarré (noyau et initramfs d’origine, hors ISO) | `install ok installed`, version **1.2.0** |
| Sauvegarde avant modification | `/var/backups/lumen/before-lumen-1.2.0-*.tar.gz`, droits 0600 |
| `dpkg --audit` après installation | Aucun problème signalé |
| Version après **redémarrage** | `{"version": "1.2", "configured": true}` conservé |
| Fichiers du modèle utilisateur : libellé « Applications », Super+Espace → Spotlight, Super+A → menu complet, barre 42 px | Présents |
| Thème et dock installés | `gtk.css` Liquid Glass, `TopRoundness=24` |
| Migration utilisateur `migrate-v12-session` | Sauvegarde `v1.2-*`, horodatage écrit, seconde exécution sans effet |
| Applications et fond d’écran existants | Firefox, XFCE, Plank, Thunar, Terminal toujours installés ; fond d’écran d’origine intact |
| Curseur | Toujours `default`, taille 32 |
| Fenêtre **Mises à jour** simplifiée | Rendu réel : un état, un bouton principal, « Détails » replié |
| **Spotlight** | Fenêtre réelle, recherche d’applications et de réglages, tuiles Wi-Fi/Son/Batterie, navigation clavier, fermeture |
| Temps d’ouverture de Spotlight | **129–146 ms** entre la commande `--toggle` et la fenêtre prête (démon préchargé, pas de relance de GTK) |
| Second appui sur le raccourci | La fenêtre se referme, le démon reste actif |
| Menu Applications | Fenêtre réelle, catégories, recherche, compteur d’applications |
| Barre et dock | Capturés dans une véritable session XFCE ; dock flottant, barre en verre |

Captures : `tests/shots/01-desktop.png`, `02-updates.png`, `03-spotlight.png`, `04-applications.png` du projet.

## Non testé / limites

- Le **flou d’arrière-plan** dépend du compositeur. Le test d’affichage utilisait le backend `xrender`, où `dual_kawase` n’est pas disponible ; le flou réel s’active avec le backend GLX sur matériel compatible. Les surfaces restent translucides et lisibles sans flou.
- Le rendu a été vérifié dans XFCE sous Xvfb, **pas** sur un GPU physique. Aucune mesure de performance graphique réelle n’est fournie.
- La session graphique du disque de test n’a pas démarré automatiquement après redémarrage (démarrage direct du noyau, sans gestionnaire de connexion) : la persistance de la version a été vérifiée, l’affichage a été validé séparément.
- L’installateur Calamares n’a pas été refait et n’a pas été retesté dans cette étape.
- Toutes les applications tierces n’ont pas été inspectées une par une : le thème GTK s’applique aux applications natives, avec leurs propres variations.
- Aucune coupure d’alimentation pendant `dpkg` n’a été simulée.

## Paquet publié

```text
repo/lumen-release_1.2.0_all.deb
```

L’empreinte SHA-256 exacte figure dans `SHA256SUMS`, généré avec les index du dépôt.
