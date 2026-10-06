# Le Bateau de Thibault : application mobile e-commerce

Application mobile de vente de produits de la mer, faite avec Ionic et Angular.
Projet réalisé pendant ma formation (2023) : recréer en application mobile la maquette du site « Le Bateau de Thibault ».

## Fonctionnalités

- **Catalogue** des produits (poissons, coquillages, crustacés) avec filtre par catégorie et page des promotions.
- **Fiche produit** : prix, unité de vente, disponibilité et remise éventuelle.
- **Panier** : ajouter, diminuer ou retirer un produit, vider le panier. Un compteur affiche le nombre d'articles en temps réel.
- **Panier sauvegardé** dans le navigateur (localStorage) : il reste après un rechargement.
- Pages **bateaux**, **recettes**, **restaurants** et **contact**.

## Technologies

- Ionic 6 et Angular 15, TypeScript
- RxJS (`BehaviorSubject` pour le compteur du panier)
- Capacitor 4 pour générer l'application Android

## Ce que j'ai appris

- Construire une interface mobile avec les composants Ionic (onglets, fenêtres modales, listes).
- Partager un état entre plusieurs pages avec un service Angular (`CartService`).
- Mettre à jour l'affichage automatiquement avec un `BehaviorSubject`.
- Générer une application Android à partir d'un projet web avec Capacitor.

## Lancer le projet en local

Prérequis : Node.js 16 ou 18 et la CLI Ionic (`npm install -g @ionic/cli`).

```bash
npm install
ionic serve
```

Pour l'application Android (avec Android Studio installé) :

```bash
ionic build
npx cap sync android
npx cap open android
```

Les produits sont des données d'exemple écrites dans le code (pas de base de données ni d'API).

## Organisation du code

| Dossier | Rôle |
|---|---|
| `src/app/services` | `CartService` (panier et produits) et les autres services |
| `src/app/pages` | La fenêtre modale du panier |
| `src/app/components` | En-tête, pied de page et fenêtre modale réutilisables |
| `src/app/produits`, `product`, `product-list` | Le catalogue et les fiches produit |
| `src/app/bateaux`, `recettes`, `restaurants`, `contact` | Les pages d'information |
| `android` | Le projet Android généré par Capacitor |
