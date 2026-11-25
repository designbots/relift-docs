# Importer un catalogue (/docs/catalogue/importer-un-catalogue)

Relift ne remplace pas votre outil d’import : il prépare la fiche pour que l’import remplisse les bons champs, puis contrôle le résultat.

## Les trois voies [#les-trois-voies]

| Besoin | Outil |
|---|---|
| Produits, catégories, images | L’import CSV de WooCommerce (**Catalogue → Produits → Importer**), ou **WP All Import** si vous l’avez installé |
| Champs de la fiche catalogue (caractéristiques, GTIN, conditionnement…) | Le même outil d’import, avec les champs listés ci-dessous |
| Prix fixes par groupe | L’import CSV de Relift, en ligne de commande. Voir [tarifs par groupe](/docs/tarifs-commandes/tarifs-par-groupe) |

<Callout type="warn" title="Extensions payantes">
WP All Import, comme ACF Pro, n’est pas fourni avec Relift. S’il est actif, le menu **Imports** apparaît pour le Responsable catalogue.
</Callout>

## Préparer le fichier [#préparer-le-fichier]

<Steps>
<Step>
### Une ligne par produit [#une-ligne-par-produit]

Chaque produit a une référence (UGS) unique : c’est elle qui permet de remettre à jour un produit sans le dupliquer.
</Step>

<Step>
### Choisir les catégories et la gamme [#choisir-les-catégories-et-la-gamme]

Utilisez les noms exacts des catégories existantes. Pour les gammes, la taxonomie est `rl_gamme`.
</Step>

<Step>
### Renseigner les champs Relift [#renseigner-les-champs-relift]

Voir le tableau suivant.
</Step>

<Step>
### Tester sur quelques lignes [#tester-sur-quelques-lignes]

Importez d’abord une dizaine de produits sur une copie du site, vérifiez les fiches, puis lancez l’import complet.
</Step>
</Steps>

## Champs de la fiche à alimenter [#champs-de-la-fiche-à-alimenter]

Les champs Relift sont des champs ACF : ils s’importent comme des métadonnées de produit.

| Information | Champ |
|---|---|
| Référence fabricant | `rl_ref_fabricant` |
| EAN / GTIN | `rl_gtin` |
| Objet BIM | `rl_bim` |
| Caractéristique de l’univers | `rl_specs_<nom>` (par exemple `rl_specs_longueur`) |
| Conditionnement | `rl_conditionnement` (groupe : quantité, unité, minimum) |
| Documents | `rl_documents` (répéteur : type, fichier ou adresse, version, date) |
| Accessoires compatibles | `rl_compat` |
| Prix fixe pour un groupe | `_rl_price_<groupe>` |
| Quantité minimum, vendu par | `rl_qty_min`, `rl_qty_step` |

Les noms de caractéristiques dépendent de l’[univers](/docs/catalogue/univers) du site. Les sous-champs d’un groupe ou d’un répéteur suivent le stockage standard d’ACF (`<champ>_<sous-champ>`, ligne numérotée pour un répéteur).

<Callout title="Champs pilotés par l’ERP">
Un champ listé dans `sync.locked_fields` est protégé côté serveur : un import qui l’écrit n’a pas à le modifier depuis l’écran produit, il reste piloté par votre ERP. Voir [les réglages](/docs/reglages/client-json).
</Callout>

## Après l’import [#après-limport]

1. Recalculez la complétude : `wp relift completeness`.
2. Filtrez la liste des produits sur « À compléter » : voir [la complétude](/docs/catalogue/completude).
3. Lancez `wp relift doctor` : le contrôle « Fiches » résume l’état du catalogue.
4. Importez les prix par groupe si besoin.

Les imports de prix sont inscrits au [journal d’activité](/docs/securite/journal-activite).