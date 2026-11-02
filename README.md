# Plume — facturation simple et élégante

Application de facturation 100 % front-end (un seul fichier `index.html`, aucune dépendance, aucun serveur).
Saisie magique (« Logo 2 x 450 » + Entrée), facture en aperçu direct, suivi des encaissements, impression en PDF.

## Fonctionnalités
- Factures : brouillon, à payer, en retard (calculé selon l’échéance), payée ; numérotation continue `FAC-AAAA-001`
- Bases de données par catégorie : **Clients**, **Projets**, **Produits et services**, **Factures**, **Paramètres**
- Les clients et projets saisis dans une facture sont créés automatiquement ; le catalogue se pioche en un clic
- Mentions légales micro-entrepreneur (TVA non applicable, art. 293 B du CGI), pénalités de retard
- Export / import JSON de toutes les données, mode sombre automatique, responsive

## Publier sur GitHub Pages
1. Créez un dépôt et déposez-y `index.html` et `README.md`.
2. **Settings → Pages → Deploy from a branch → `main` / `(root)`**.
3. Le site est en ligne sur `https://<utilisateur>.github.io/<depot>/`.

## Où sont les données ?
Dans le `localStorage` du navigateur, une clé par catégorie : `plume.factures`, `plume.clients`, `plume.projets`,
`plume.produits`, `plume.parametres`, `plume.compteur`. Elles ne quittent jamais l’appareil.
Pensez à **exporter une sauvegarde** (Paramètres → Exporter) : vider le navigateur efface les données.

Pour passer à une vraie base (Supabase, Firebase…), remplacez `load()` et `save()` en tête du script : tout le reste lit et écrit via l’objet `db`.

## Avertissement
Vérifiez les mentions obligatoires et vos obligations de facturation (y compris électronique) auprès de votre comptable ou de l’administration.
