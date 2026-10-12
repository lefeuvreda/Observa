# Observa ULIS TSLA — banque de compétences

Application web statique PWA **de démonstration**, utilisable sur ordinateur, tablette et mobile.

## Fonctions

- Banque de **521 objectifs observables** avec identifiant stable, discipline et domaine, champ de recherche et export CSV.
- Matières : français, mathématiques, histoire, géographie, EMC, physique-chimie, SVT, technologie, langues vivantes, EPS, arts plastiques, éducation musicale, histoire des arts et compétences transversales.
- Formulaire d'observation en contexte : élève fictif, date, discipline, contexte, activité, objectifs personnalisés, 15 domaines généraux, et compétences disciplinaires multiples.
- Pour chaque compétence : cotation de 0 à 4, aide, modalité (oral, manuscrit, numérique, manipulation…), temps en minutes et observations factuelles.
- Historique, détails, synthèse par compétence dans le bilan ESS, export JSON/CSV et import de l'ancien format JSON v1.
- Stockage dans IndexedDB, sans serveur et sans synchronisation.

**Important :** les indicateurs constituent une déclinaison pédagogique opérationnelle des enseignements et du socle commun, **pas** une transcription officielle exhaustive de chaque programme. Les niveaux d'exigence se définissent en fonction du programme applicable à la classe et du profil de l'élève.

## Installation GitHub Pages

Déposez les fichiers **contenus** dans le dossier à la racine du dépôt : `index.html`, `app.js`, `competences.js`, `style.css`, `sw.js`, `manifest.webmanifest`, `icon.svg`. Conservez éventuellement `README.md`. Activez Settings → Pages → Deploy from a branch → `main` → `/(root)`.

Pour le développement local, utilisez un serveur HTTP, par exemple `python3 -m http.server 8000` lancé dans ce dossier.

## Mise à jour et compatibilité

L'application conserve le nom de sa base IndexedDB `observa-ulis-demo` et le format d'export JSON `observa-ulis-v1`. Les anciens enregistrements sans tableau `competences` demeurent valables. **Exporter une sauvegarde JSON depuis l'ancienne version avant tout remplacement** ; ne pas vider les données du navigateur. Vérifier que le nouveau fichier `competences.js` est bien publié. Le service worker change de cache pour servir la nouvelle version.

## Confidentialité

**Ne stockez aucune donnée réelle ou directement/indirectement identifiable d'élève dans cette version.** Aucune authentification, gestion des autorisations ou chiffrement applicatif ne protège les données enregistrées dans le navigateur ; les fichiers exportés sont en clair. GitHub Pages ne constitue pas un hébergement sécurisé pour ce registre nominatif. Pour un usage en établissement, définir les traitements avec la direction et le DPO et mettre en place une infrastructure autorisée avec droits d'accès, sauvegardes et sécurisation adaptés.
