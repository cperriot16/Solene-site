# Guide de mise en ligne — Site Solène Le Mazou

Ce dossier contient le nouveau site, prêt à héberger en parallèle du WordPress
actuel. Suivez ces étapes dans l'ordre.

## Fichiers du dossier

- `index.html` — le site (design, structure)
- `content.json` — les textes et prix modifiables (édités via /admin)
- `admin/` — l'interface d'administration pour Solène
- `images/` — dossier où atterriront les photos qu'elle ajoutera via l'admin

## Étape 1 — Créer un compte GitHub (si vous n'en avez pas)

Allez sur github.com, créez un compte gratuit. GitHub stocke le code du site
et garde l'historique de toutes les modifications (utile si jamais une
modification doit être annulée).

## Étape 2 — Créer un dépôt et y déposer les fichiers

1. Sur GitHub, cliquez sur "New repository", nommez-le par exemple
   `solene-site`.
2. Glissez-déposez tous les fichiers de ce dossier dans le dépôt (via
   l'interface web GitHub : "Add file" > "Upload files").

## Étape 3 — Déployer sur Netlify

1. Créez un compte gratuit sur netlify.com (vous pouvez vous connecter
   directement avec votre compte GitHub).
2. Cliquez sur "Add new site" > "Import an existing project" > choisissez
   votre dépôt GitHub `solene-site`.
3. Laissez les réglages par défaut et cliquez sur "Deploy".
4. Netlify vous donne une adresse temporaire du type
   `solene-site-xyz.netlify.app` — le site est en ligne, visible par vous
   seuls pour l'instant (personne ne le trouvera sans le lien).

## Étape 4 — Activer l'administration pour Solène

1. Dans Netlify, allez dans "Site configuration" > "Identity" > "Enable
   Identity".
2. Toujours dans Identity, allez dans "Registration" et choisissez
   "Invite only" (pour que seule Solène puisse créer un compte).
3. Allez dans "Services" > "Git Gateway" et cliquez sur "Enable Git
   Gateway".
4. Retournez dans Identity > "Invite users", entrez l'email de Solène.
   Elle recevra un email pour définir son mot de passe.

## Étape 5 — Solène peut maintenant éditer le site

Elle se rend sur `solene-site-xyz.netlify.app/admin`, se connecte avec
l'email et le mot de passe définis à l'étape précédente, et peut modifier
textes et prix depuis un formulaire simple. Chaque "Enregistrer" déclenche
automatiquement une mise à jour du site, visible en 1 à 2 minutes.

## Étape 6 — Quand tout est validé : brancher le vrai domaine

1. Dans Netlify, "Domain management" > "Add a domain" > entrez
   `solenelemazou.fr`.
2. Netlify vous donne des informations DNS à reporter chez le registrar
   actuel du domaine (souvent indiqué dans l'espace client WordPress /
   hébergeur).
3. Une fois le changement DNS propagé (quelques heures), le nouveau site
   remplace l'ancien WordPress sur l'adresse officielle.
4. Vous pouvez alors résilier l'hébergement WordPress si vous le souhaitez.

## Pour le flux Instagram

Indépendant de tout ceci : créez un compte sur behold.so, connectez le
compte Instagram Business, copiez l'identifiant du widget fourni, et
remplacez `YOUR-WIDGET-ID` dans `index.html` (recherchez `behold-widget`)
par cet identifiant.
