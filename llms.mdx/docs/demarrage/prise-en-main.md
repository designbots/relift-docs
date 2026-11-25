# Prendre en main l’administration (/docs/demarrage/prise-en-main)

L’administration reprend WordPress avec des menus au vocabulaire du catalogue. Les rôles de l’équipe voient uniquement ce qui leur sert ; un administrateur voit toujours tout.

## Les menus [#les-menus]

| Menu | Contenu |
|---|---|
| Tableau de bord | Vue d’ensemble : demandes de devis récentes, comptes pros à valider, état de la synchronisation |
| Catalogue | Produits, catégories, gammes, attributs |
| Documents et médias | Fichiers (fiches techniques, notices, images) |
| Commandes | Commandes WooCommerce, avec société, SIRET, TVA et groupe de l’acheteur |
| Clients pros | Comptes clients, validation des comptes pros |
| Pages du site | Pages WordPress |
| Actualités et guides | Articles |
| Réglages | Écran Relift et réglages WooCommerce « Relift B2B » |
| Mon profil | Votre compte, double authentification, clés d’accès |

<Callout title="Un menu absent ?">
Les menus affichés dépendent de votre rôle. Voir [les rôles de l’équipe](/docs/reglages/roles).
</Callout>

## Tableau de bord, recherche, notifications [#tableau-de-bord-recherche-notifications]

- Le **tableau de bord** regroupe les demandes de devis, les comptes pros en attente et l’état de la synchronisation.
- La **recherche rapide** (Ctrl ou ⌘ + K) retrouve un produit par nom ou référence, ou une demande de devis.
- Le **centre de notifications** (la cloche) rassemble les messages des extensions et de WordPress : mises à jour, réglages à terminer, erreurs. Seules les confirmations d’action restent dans la page.

## Revenir à l’interface WordPress classique [#revenir-à-linterface-wordpress-classique]

Chacun peut revenir à l’interface WordPress habituelle depuis le menu du compte. Pour tout le site, l’option `admin.app_ui` à `false` dans `client.json` désactive l’interface Relift et garde l’interface WordPress habillée aux couleurs du client.