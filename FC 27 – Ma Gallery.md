# ⚽ FC 27 – Ma Gallery

Tracker complet de collection FC 27 Ultimate Team.

Fonctionnalités :
- dashboard avec progression globale et progression par catégorie ;
- cartes visuelles pour les championnats, clubs, promotions et nations ;
- présentation en grille façon galerie avec grandes cartes et logos mis en avant ;
- chaque championnat possède maintenant sa propre interface/section avec uniquement ses clubs ;
- navigation rapide et filtre dédié pour afficher un seul championnat à la fois ;
- vrais logos pour les championnats et les clubs ;
- carte statique de logos clubs incluse dans le projet pour éviter les erreurs CORS ;
- logo image garanti pour les 178 cartes clubs, avec correspondances spéciales pour les noms FC 27 non standards ;
- vrais blasons/drapeaux pour les nations ;
- icônes de catégorie et de récompense ;
- recherche par nom, catégorie ou condition ;
- filtres « Tout », « À faire », « Terminés » et filtre par catégorie ;
- filtre par note (sans note, D, C, B, A ou S) et tri par nom/progression ;
- bouton de réinitialisation de tous les filtres et raccourci Ctrl/Cmd+K pour la recherche ;
- notes personnelles de D à S pour chaque set ;
- compteurs de notes affichés dans le dashboard ;
- sauvegarde cloud obligatoire après connexion Supabase ;
- export et import JSON de la progression ;
- export CSV compatible avec Excel et Google Sheets ;
- bouton retour en haut pour parcourir rapidement les grandes galeries ;
- synchronisation cloud avec Supabase et connexion par pseudo + mot de passe ;
- application installable sur téléphone/ordinateur (PWA) avec cache hors ligne ;
- thème sombre optimisé pour mobile ;
- ajout et suppression de sets personnalisés ;
- notifications et confirmations pour les actions importantes.
- catalogue étendu à toutes les équipes des championnats inclus (178 sets clubs au total, sans doublons).

Utilisation :
1. configure Supabase selon [le guide de déploiement](./DEPLOY-SUPABASE.md) ;
2. ouvre le site et crée un compte avec un pseudo et un mot de passe ;
3. coche un set pour le marquer comme terminé ;
4. choisis une note dans le menu D à S ;
5. utilise la recherche et les filtres pour retrouver rapidement un set ;
6. exporte une copie JSON si tu veux une sauvegarde manuelle supplémentaire.

La connexion est nécessaire pour enregistrer les changements. Les données ne sont pas stockées dans le navigateur : elles sont isolées par utilisateur dans Supabase et disponibles sur tous tes appareils.

Après publication sur Vercel ou Netlify, le navigateur proposera l’installation de l’application sur l’écran d’accueil. Le service worker permet de rouvrir la galerie même sans connexion ; la synchronisation Supabase reprend dès que le réseau revient.

Les logos sont chargés depuis les CDN publics API-Football et ESPN. Un emoji de secours est affiché automatiquement si un logo distant ne répond pas ou si une équipe n’est pas disponible dans le catalogue.
