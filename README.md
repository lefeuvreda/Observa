# Observa — prototype ULIS TSLA

Application web statique (PWA) pour **démonstrations avec données entièrement fictives**.

## Fonctionnalités
- Saisie tactile : date, élève fictif, matière, contexte, objectif, six compétences (0 à 3 ou « non observé »), aide et commentaire.
- Historique filtrable et consultation/suppression des observations.
- Profils fictifs et objectifs personnalisés.
- Graphique chronologique, indicateurs et bilan imprimable en PDF.
- Enregistrement dans **IndexedDB**, export CSV/JSON, restauration JSON.
- Fonctionnement hors connexion après premier chargement, sous réserve de mise en cache par le navigateur.

## Publication sur GitHub Pages
1. Créer un **nouveau dépôt**, par exemple `observa-ulis`. Les fichiers du site publiés sur GitHub Pages sont publics, même si certaines configurations de dépôt sont privées.
2. Décompresser le ZIP puis envoyer **les fichiers contenus dans le dossier** (`index.html`, `style.css`, `app.js`, `sw.js`, `manifest.webmanifest`, `icon.svg`) **à la racine** du dépôt, avec éventuellement ce README.
3. Ouvrir **Settings > Pages > Build and deployment**.
4. Sélectionner **Deploy from a branch**, branche `main`, dossier `/(root)`, puis **Save**.
5. Ouvrir `https://VOTRE-PSEUDO.github.io/observa-ulis/` (adapter le nom du dépôt).
6. Sur iPhone/iPad : ouvrir dans Safari, choisir **Partager > Sur l'écran d'accueil**.

## Test local
Vous pouvez ouvrir `index.html` dans un navigateur compatible, mais pour tester le mode hors ligne/PWA, il vaut mieux passer par GitHub Pages ou un petit serveur local (`python3 -m http.server 8000` puis `http://localhost:8000`).

## Sécurité et confidentialité — impératif
**Ne saisissez jamais d'identités, initiales réelles, diagnostics ou observations concernant de véritables élèves dans cette démonstration.** L'application ne dispose pas d'authentification, de chiffrement applicatif, de gestion multi-utilisateur ou de synchronisation. Les données sont uniquement stockées dans le navigateur utilisé et peuvent être supprimées par ses réglages. Les sauvegardes téléchargées sont des fichiers en clair.

Pour un usage professionnel avec données d'élèves, demander l'accord de l'établissement et de son DPO, choisir une infrastructure autorisée, mettre en place des mesures de sécurité adaptées et établir les obligations RGPD applicables. **N'ajoutez pas de données d'élèves au dépôt GitHub**, y compris dans des fichiers de démonstration ou l'historique Git.

## Fonctionnement des graphiques
La moyenne d'autonomie est calculée par date pour les entrées sélectionnées. Les notes « non observé » ne sont pas incluses. La comparaison reste descriptive : activités, objectifs et niveaux d'aide doivent être interprétés.

## Technique
HTML, CSS et JavaScript natifs ; aucune bibliothèque externe, aucune clé API, aucun serveur requis pour le prototype. IndexedDB pour les données locales et Service Worker pour le cache de fichiers du site.
