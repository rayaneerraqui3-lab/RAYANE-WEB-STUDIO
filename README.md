# Rayane Web Studio

Application multi-pages Vite + TypeScript avec authentification Google / Gmail obligatoire (`login.html`), messagerie temps réel via Cloud Firestore (`messages.html`), annonces (`annonces.html`) et publications (`publications.html`), sans aucun faux utilisateur pré-rempli.

## Structure du projet

- `login.html` + `src/login-entry.ts` : page d'entrée obligatoire (connexion Google / Gmail, changement de compte, déconnexion)
- `index.html` : fil principal d'annonces et publications
- `messages.html` + `src/messages-entry.ts` : messagerie directe temps réel entre vrais membres connectés (barre latérale rétractable en vue compacte, annuaire `/directory`, texte, J'aime, photo, vidéo, vocal)
- `annonces.html` / `publications.html` : éditeurs d'annonces et de publications
- `recherche.html` : recherche globale (vrais membres inscrits, publications, annonces)
- `parrametre.html` : gestion du compte Google et export du projet VS Code
- `src/lib/firebase-client.ts` : initialisation Firebase Auth & Firestore, synchronisation profil, annuaire et messagerie temps réel
- `src/lib/messages-logic.ts` : logique pure et testable de messagerie (état initial vide, filtres, transitions)
- `firestore.rules` & `firebase-blueprint.json` : règles de sécurité Firestore et schéma de données

## Lancer le projet dans VS Code

1. Ouvrez le dossier `rayane-web-studio` dans **VS Code**.
2. Installez les dépendances :
   ```bash
   npm install
   ```
3. Démarrez le serveur local :
   ```bash
   npm run dev
   ```
4. Ouvrez [http://localhost:3000](http://localhost:3000) (`login.html` s'ouvre automatiquement si vous n'êtes pas encore connecté).

## Scripts utiles

- `npm test` : exécute les tests unitaires (`src/lib/messages-logic.test.ts`)
- `npm run lint` : vérifie les types TypeScript (`tsc --noEmit`)
- `npm run build` : génère le build de production dans `dist/`
