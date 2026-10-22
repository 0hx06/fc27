# ⚽ FC 27 – Ma Gallery

Tracker complet de collection FC 27 Ultimate Team.

Fonctionnalités :
- dashboard avec progression globale et progression par catégorie ;
- cartes visuelles pour les championnats, clubs, promotions et nations ;
- présentation en grille façon galerie avec grandes cartes et logos mis en avant ;
- chaque championnat possède maintenant sa propre interface/section avec uniquement ses clubs ;
- navigation rapide et filtre dédié pour afficher un seul championnat à la fois ;
- vrais logos pour les championnats et les clubs ;
- chargement automatique des autres logos disponibles par championnat via le catalogue ESPN ;
- logo image garanti pour les 178 cartes clubs, avec correspondances spéciales pour les noms FC 27 non standards ;
- vrais blasons/drapeaux pour les nations ;
- icônes de catégorie et de récompense ;
- recherche par nom, catégorie ou condition ;
- filtres « Tout », « À faire », « Terminés » et filtre par catégorie ;
- filtre par note (sans note, D, C, B, A ou S) et tri par nom/progression ;
- bouton de réinitialisation de tous les filtres et raccourci Ctrl/Cmd+K pour la recherche ;
- notes personnelles de D à S pour chaque set ;
- compteurs de notes affichés dans le dashboard ;
- sauvegarde automatique dans le navigateur ;
- export et import JSON de la progression ;
- export CSV compatible avec Excel et Google Sheets ;
- bouton retour en haut pour parcourir rapidement les grandes galeries ;
- synchronisation cloud optionnelle avec Supabase et connexion par lien e-mail ;
- application installable sur téléphone/ordinateur (PWA) avec cache hors ligne ;
- thème sombre optimisé pour mobile ;
- ajout et suppression de sets personnalisés ;
- notifications et confirmations pour les actions importantes.
- catalogue étendu à toutes les équipes des championnats inclus (178 sets clubs au total, sans doublons).

Utilisation :
1. ouvre [fc.html](./fc.html) dans ton navigateur ;
2. coche un set pour le marquer comme terminé ;
3. choisis une note dans le menu D à S ;
4. utilise la recherche et les filtres pour retrouver rapidement un set ;
5. exporte régulièrement ta sauvegarde JSON si tu changes de navigateur ou d’ordinateur.

Sans configuration cloud, les données sont stockées localement dans le navigateur. La synchronisation entre appareils est disponible en configurant Supabase selon [le guide de déploiement](./DEPLOY-SUPABASE.md).

Après publication sur Vercel ou Netlify, le navigateur proposera l’installation de l’application sur l’écran d’accueil. Le service worker permet de rouvrir la galerie même sans connexion ; la synchronisation Supabase reprend dès que le réseau revient.

Les logos sont chargés depuis les CDN publics API-Football et ESPN. Un emoji de secours est affiché automatiquement si un logo distant ne répond pas ou si une équipe n’est pas disponible dans le catalogue.
