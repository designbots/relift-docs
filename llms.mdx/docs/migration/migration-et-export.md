# Migration et export (/docs/migration/migration-et-export)

## Déplacer la configuration [#déplacer-la-configuration]

La configuration Relift se copie d’un site à l’autre sans toucher au code.

<Steps>
<Step>
### Exporter [#exporter]

Sur le site source : **WooCommerce → Réglages → Relift B2B → Import et export**, bouton d’export. Vous obtenez un fichier JSON.
</Step>

<Step>
### Importer [#importer]

Sur le site cible, collez le contenu dans **Importer des réglages** puis enregistrez.
</Step>

<Step>
### Vérifier [#vérifier]

Lancez `wp relift config` pour afficher la configuration active, puis `wp relift doctor`.
</Step>
</Steps>

Les réglages imposés par `client.json` (liste `locked`) ne sont jamais remplacés. Les réglages actuels de l’administration du site cible sont remplacés par ceux du fichier : exportez-les d’abord pour en garder une copie.

## Déplacer le moteur [#déplacer-le-moteur]

Un site Relift se compose de trois éléments :

| Élément | Où |
|---|---|
| Code | Dossier `mu-plugins/`, identique sur tous les sites |
| Configuration | `client.json` dans `wp-content/relift/` |
| Données | Produits, comptes, commandes et demandes dans la base WordPress |

Copiez le dossier et le fichier de configuration, puis déplacez la base et les médias avec votre outil de migration WordPress habituel. Terminez par `wp relift init` si le site est neuf, puis `wp relift doctor`.

## Exporter vos données [#exporter-vos-données]

| Donnée | Comment |
|---|---|
| Commandes, produits, clients | Exports natifs de WooCommerce et de WordPress |
| Données d’une personne (comptes pros, demandes de devis, journal d’activité) | **Outils → Exporter les données personnelles** |
| Configuration | Export JSON ci-dessus |
| Webhook | Chaque demande de devis et chaque compte pro peuvent être envoyés à vos outils. Voir [le webhook](/docs/integrations/webhook) |

Les exports de données personnelles et les imports de prix sont inscrits au [journal d’activité](/docs/securite/journal-activite).

## Quitter Relift [#quitter-relift]

Les données restent dans WordPress et WooCommerce : produits, commandes et comptes sont des contenus standard. Les champs de la fiche catalogue sont des champs ACF, lisibles par n’importe quel outil d’export.