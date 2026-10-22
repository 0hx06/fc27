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

## 2. Autoriser le lien de connexion

Dans Supabase, ouvre **Authentication > URL Configuration** et ajoute l’URL de ton futur site dans **Site URL** et **Redirect URLs**.

Le bouton cloud utilise une connexion sans mot de passe : l’utilisateur reçoit un lien par e-mail.

## 3. Publier sur Vercel

1. Crée un dépôt GitHub contenant `fc.html`, `supabase-config.js` et `supabase-schema.sql`.
2. Sur [Vercel](https://vercel.com), importe le dépôt.
3. Choisis un projet statique sans commande de build.
4. Renomme `fc.html` en `index.html` si tu veux que la page s’ouvre directement à la racine.
5. Ajoute l’URL Vercel dans les URLs autorisées de Supabase.

## Fonctionnement

- Sans configuration Supabase, l’application reste utilisable en mode local.
- Avec Supabase configuré, le bouton **Connexion** envoie un lien magique par e-mail.
- Après connexion, la progression, les notes et les sets personnalisés sont synchronisés automatiquement.
- Les données locales restent conservées comme sauvegarde de secours.
