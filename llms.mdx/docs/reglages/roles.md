# Rôles de l’équipe (/docs/reglages/roles)

Relift ajoute des rôles qui correspondent aux métiers d’un catalogue B2B. Le client n’a jamais le rôle Administrateur Relift.

| Rôle | Accès |
|---|---|
| Administrateur Relift | Tout |
| Responsable catalogue | Catalogue, médias, commandes, pages, actualités, comptes clients, imports |
| Commercial | Commandes, comptes clients, demandes de devis |
| Rédacteur | Actualités et guides, médias |
| Synchronisation | Compte technique pour l’outil d’automatisation (mots de passe d’application autorisés) |

## Garde-fous [#garde-fous]

Un utilisateur qui n’est pas administrateur ne peut modifier, promouvoir ou supprimer que des comptes clients, et ne peut pas changer son propre rôle. Les changements de rôle sont inscrits au [journal d’activité](/docs/securite/journal-activite).

## Droits complémentaires [#droits-complémentaires]

| Droit | Usage |
|---|---|
| `relift_content` | À accorder dans Bricks → Réglages → Accès au builder |
| `relift_import` | Imports |
| `relift_api` | Accès technique |
| `relift_manage` | Gestion Relift |

## Menus selon le rôle [#menus-selon-le-rôle]

Les rôles de l’équipe voient des menus au vocabulaire du catalogue ; ce qui n’est pas utile à leur métier est masqué, jamais supprimé. Voir [prendre en main l’administration](/docs/demarrage/prise-en-main).