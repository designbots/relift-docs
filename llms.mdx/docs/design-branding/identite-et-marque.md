# Identité et marque (/docs/design-branding/identite-et-marque)

L’administration de votre site porte le nom de votre société, pas celui de WordPress. Tout se règle dans `client.json`.

## Marque blanche [#marque-blanche]

`admin.white_label` (actif par défaut) remplace les repères WordPress : page de connexion, apparence de l’administration, barre d’administration, pied de page et titre des onglets. Le pied de page affiche « Relift Catalogue » et son numéro de version.

Mettez la valeur à `false` pour revenir à l’administration WordPress d’origine.

## Nom et logo [#nom-et-logo]

```json
"client": {
  "name": "Exemple Menuiseries",
  "logo": "https://exemple.fr/wp-content/uploads/logo.svg"
}
```

Le nom s’affiche sur la page de connexion ; le logo y figure aussi, ainsi que dans l’interface Relift.

## Écran de connexion [#écran-de-connexion]

La page de connexion est en écran partagé : formulaire d’un côté, message de l’autre.

```json
"admin": {
  "login": {
    "title": "Votre catalogue B2B, toujours à jour",
    "text": "Gérez vos produits, vos documents et vos demandes de devis depuis un seul espace.",
    "points": ["Fiches produit complètes", "Devis suivis de bout en bout", "Comptes pros et prix réservés"],
    "image": ""
  }
}
```

`points` accepte 3 ou 4 arguments. Sans `image`, l’écran montre une capture du tableau de bord.

## Assistance [#assistance]

Le bloc d’assistance du tableau de bord se règle avec `support` : libellé, e-mail, lien de prise de rendez-vous et lien vers votre guide.

## Interface d’administration [#interface-dadministration]

L’interface Relift (barre supérieure, recherche Ctrl ou ⌘ + K, notifications) est active par défaut. `admin.app_ui` à `false` garde l’interface WordPress habillée.