# Publier FC 27 Gallery avec synchronisation

## 1. Créer le projet Supabase

1. Crée un projet sur [Supabase](https://supabase.com).
2. Ouvre **SQL Editor** et exécute le contenu de `supabase-schema.sql`.
3. Dans **Project Settings > API**, copie :
   - **Project URL** ;
   - la clé publique **anon**.
4. Colle ces valeurs dans `supabase-config.js` :

```js
window.FC27_SUPABASE_CONFIG = {
    url: 'https://TON-PROJET.supabase.co',
    anonKey: 'TA_CLE_ANON_PUBLIQUE'
};
```

La clé `anon` peut être présente dans le navigateur. Ne mets jamais la clé `service_role` dans ce fichier.

## 2. Configurer la connexion pseudo + mot de passe

Dans **Authentication > Providers > Email**, active la connexion e-mail/mot de passe et désactive la confirmation d’e-mail pour ce projet. Le site transforme chaque pseudo en identifiant technique interne (`pseudo@fc27.app`) ; l’utilisateur ne voit et ne saisit que son pseudo.

Les pseudos sont insensibles à la casse et doivent contenir uniquement des lettres, chiffres, `_` ou `-`. Les mots de passe sont traités directement par Supabase Auth et ne sont jamais écrits dans `user_gallery_state`.

## 3. Autoriser le site

Dans Supabase, ouvre **Authentication > URL Configuration** et ajoute l’URL de ton site dans **Site URL** et **Redirect URLs**.

## 4. Publier sur Vercel

1. Crée un dépôt GitHub contenant `fc.html`, `supabase-config.js` et `supabase-schema.sql`.
2. Sur [Vercel](https://vercel.com), importe le dépôt.
3. Choisis un projet statique sans commande de build.
4. Renomme `fc.html` en `index.html` si tu veux que la page s’ouvre directement à la racine.
5. Ajoute l’URL Vercel dans les URLs autorisées de Supabase.

## Fonctionnement

- La connexion Supabase est obligatoire pour enregistrer une progression : aucune modification n’est sauvegardée dans `localStorage`.
- Tant que Supabase n’est pas configuré, la galerie reste consultable mais les actions de progression demandent de configurer puis d’utiliser un compte.
- Avec Supabase configuré, le bouton **Connexion** permet de créer un compte ou de se connecter avec un pseudo et un mot de passe.
- Après connexion, la progression, les notes et les sets personnalisés sont synchronisés automatiquement.
- Les données locales restent conservées comme sauvegarde de secours.
