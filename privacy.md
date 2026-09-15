# Politique de confidentialité — Cliper

*Dernière mise à jour : 15 septembre 2026*

## Ce qu'est Cliper

Cliper est un outil qui s'installe et s'exécute **sur l'ordinateur de son
utilisateur**. Il découpe des vidéos longues en extraits courts, y incruste des
sous-titres, et permet de programmer leur publication.

Il n'existe aucun serveur Cliper. L'éditeur de Cliper n'héberge rien, ne reçoit
rien et ne peut accéder à aucune donnée d'utilisateur.

## Données collectées par l'éditeur

**Aucune.** Cliper ne comporte ni télémétrie, ni statistiques d'usage, ni
mouchard, ni compte utilisateur.

## Données traitées sur la machine de l'utilisateur

Tout ce qui suit reste dans le dossier d'installation de Cliper, sur le disque
de l'utilisateur :

| Donnée | Usage | Emplacement |
|---|---|---|
| Vidéos téléchargées ou importées | découpe et montage | `data/jobs/` |
| Transcriptions | sous-titres, choix des extraits | `data/jobs/` |
| Extraits montés | fichiers produits | `data/jobs/` |
| Clés d'API renseignées | appels aux services choisis | `.env` (accès restreint au propriétaire) |
| Jeton d'accès TikTok | publier les extraits en votre nom | `data/tiktok.json` (accès restreint au propriétaire) |

L'utilisateur peut tout supprimer à tout moment en effaçant ces fichiers ou le
dossier entier.

## Accès TikTok

Lorsqu'un utilisateur connecte son compte TikTok :

- Cliper reçoit de TikTok un **jeton d'accès** et un **jeton de
  rafraîchissement**, enregistrés uniquement sur la machine de l'utilisateur,
  dans un fichier dont les droits sont restreints à son propriétaire ;
- ces jetons ne sont **jamais transmis à un tiers**, ni à l'éditeur de Cliper ;
- ils servent exclusivement à envoyer, à la demande de l'utilisateur, les
  vidéos qu'il a lui-même produites, avec la légende qu'il a rédigée ;
- la vidéo est envoyée **directement** de l'ordinateur de l'utilisateur vers les
  serveurs de TikTok. Elle ne transite par aucun autre système ;
- Cliper ne lit aucune donnée du compte au-delà du profil de base nécessaire à
  l'affichage de la connexion.

Les droits demandés sont :

- `user.info.basic` — vérifier que la connexion fonctionne ;
- `video.upload` — déposer une vidéo dans les brouillons du compte ;
- `video.publish` — publier une vidéo, uniquement si l'utilisateur l'a activé.

**Révocation.** Le bouton « Déconnecter » de Cliper efface les jetons de la
machine. La révocation peut aussi se faire depuis les réglages du compte TikTok,
dans la gestion des applications autorisées.

## Services tiers

Selon les fonctions qu'il active, l'utilisateur peut faire appel à des services
externes, avec ses propres clés d'API :

- **Groq** — transcription : l'audio de la vidéo leur est envoyé ;
- **Google Gemini** ou tout autre moteur configuré — analyse : le texte de la
  transcription leur est envoyé ;
- **YouTube** — téléchargement d'une vidéo dont l'utilisateur fournit le lien ;
- **TikTok** — publication, comme décrit ci-dessus.

Chacun de ces services applique sa propre politique de confidentialité. Aucun
n'est appelé sans que l'utilisateur ait renseigné la clé correspondante et lancé
l'action.

Un utilisateur qui fait tourner un modèle sur sa propre machine peut se passer
entièrement des services d'analyse externes.

## Mineurs

Cliper n'est pas destiné aux personnes de moins de 13 ans, et ne collecte
sciemment aucune donnée les concernant.

## Modifications

Toute modification de cette politique sera publiée sur cette page, avec sa date.

## Contact

Pour toute question relative à cette politique : haricots.totaux4s@icloud.com
