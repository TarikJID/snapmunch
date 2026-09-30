# PRD — [Nom à définir] — App food lifestyle façon BeReal

## 1. Vision produit
Une app mobile où chaque utilisateur poste, une à plusieurs fois par jour, une photo simultanée
(caméra avant + arrière) de son repas et de lui-même en train de le vivre. L'objectif : capturer
l'instant "bouffe" de façon authentique et non retouchée, dans un cercle d'amis privé, avec une
mécanique de notification aléatoire inspirée de BeReal.

## 2. Problème résolu
- Les gens adorent partager leurs repas mais Instagram pousse vers du contenu retouché,
  planifié, orienté esthétique.
- BeReal capture l'instant mais n'a pas de thématique forte ni d'utilité de suivi.
- Aucune app ne combine authenticité + réflexe alimentaire + lien social fort autour de la bouffe.

## 3. Utilisateur cible (V1)
- 18-30 ans, déjà utilisateur ou ex-utilisateur de BeReal
- Vit en coloc, en groupe d'amis soudé, ou en famille proche
- Poste déjà régulièrement de la bouffe sur Instagram/Stories
- Cible de lancement : petits groupes fermés (coloc, promo, équipe sportive) plutôt que grand public

## 4. Proposition de valeur
- Authenticité (pas de filtre, pas de retouche, capture forcée en 2 min)
- Rituel quotidien léger et amusant, pas chronophage
- Journal alimentaire visuel personnel en bonus (utilité au-delà du social)

## 5. Fonctionnalités — Scope V1 (MVP)

### P0 — indispensable pour lancer
- [ ] Auth simple (numéro de téléphone ou email)
- [ ] Ajout d'amis / groupes privés fermés
- [ ] Notification quotidienne à horaire aléatoire dans une fenêtre définie par l'utilisateur
      (ex : entre 12h-14h ou 19h-21h)
- [ ] Capture dual-camera simultanée (avant + arrière), sans filtre, fenêtre de 2 min
- [ ] Publication automatique sur le feed du groupe après capture
- [ ] Feed chronologique des posts des amis du jour
- [ ] Réactions simples (emoji) sur les posts des amis
- [ ] Indicateur "en retard" si post après la fenêtre (comme BeReal)

### P1 — pour la rétention
- [ ] Streak individuel (jours consécutifs de participation)
- [ ] Historique personnel type "journal des repas" (calendrier des posts passés)
- [ ] Mode "table" : plusieurs personnes taguées sur un même repas
- [ ] Notifications de rappel si non posté dans la fenêtre

### P2 — plus tard, pas en V1
- [ ] Découverte géolocalisée des repas postés près de soi
- [ ] Classement amical hebdomadaire ("meilleure bouffe de la semaine")
- [ ] Partenariats restaurants / visibilité locale
- [ ] Version web / partage externe des posts

## 6. Hors scope (explicitement non traité en V1)
- Pas de retouche photo, pas de filtres
- Pas de feed public / découverte d'inconnus
- Pas de version Android en V1 (iOS only pour le MVP)
- Pas de monétisation en V1

## 7. Parcours utilisateur principal
1. L'utilisateur ouvre l'app pour la première fois → onboarding rapide (nom, photo de profil, ajout d'amis)
2. Il rejoint ou crée un groupe privé (ex : "Coloc", "Team foot")
3. Chaque jour, il reçoit une notification aléatoire dans sa fenêtre horaire
4. Il a 2 minutes pour capturer sa photo dual-camera
5. La photo est publiée automatiquement dans le feed du/des groupe(s) dont il fait partie
6. Il consulte le feed du jour et réagit aux posts de ses amis

## 8. Stack technique envisagée
- iOS natif — SwiftUI (accès caméra dual simultané plus fiable qu'en cross-platform)
- Backend — Supabase ou Firebase (auth, storage photos, base de données feed/groupes)
- Notifications push — APNs via le backend choisi
- Pas de backend custom en V1 pour limiter la complexité

## 9. Métriques de succès (V1)
- Taux de participation quotidienne au sein des groupes actifs (% de membres qui postent/jour)
- Rétention à J7 et J30
- Taille moyenne des groupes actifs
- Streak moyen par utilisateur actif

## 10. Risques / inconnues à trancher
- Cold start : comment amorcer les premiers groupes actifs sans démarchage actif ?
- La fenêtre de capture (2 min) est-elle adaptée au format repas (on ne mange pas toujours "au bon moment") ?
- Faut-il plusieurs notifications/jour (repas) ou une seule comme BeReal ?
- Nom et identité de marque à définir

## 11. Prochaines étapes (à traiter avec Claude Code)
- [ ] Définir le nom de l'app et l'identité visuelle
- [ ] Spec technique détaillée de la capture dual-camera sur iOS
- [ ] Modèle de données (users, groups, posts, reactions)
- [ ] Maquettes des écrans principaux (onboarding, capture, feed)
- [ ] Choix définitif du backend (Supabase vs Firebase)
