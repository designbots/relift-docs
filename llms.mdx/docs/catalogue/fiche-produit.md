# La fiche produit (/docs/catalogue/fiche-produit)

Une fiche produit se complète à deux endroits : les onglets WooCommerce habituels (prix, inventaire) et la boîte **Fiche catalogue** de Relift, placée sous la boîte « Essentiel ».

## Créer un produit [#créer-un-produit]

<Steps>
<Step>
### Ouvrir le formulaire [#ouvrir-le-formulaire]

Menu **Catalogue → Ajouter un produit**. Renseignez le titre, la description, l’image mise en avant, la catégorie et, si besoin, la **gamme**.
</Step>

<Step>
### Saisir prix et conditions [#saisir-prix-et-conditions]

Dans la boîte de données produit, onglets **Général** et **Inventaire** : prix public, prix par groupe, prix dégressifs, quantité minimum, visibilité. Détails ci-dessous.
</Step>

<Step>
### Compléter la fiche catalogue [#compléter-la-fiche-catalogue]

Onglets **Caractéristiques**, **Documents**, **Compatibilités**, **Identification** et **Synchronisation**.
</Step>

<Step>
### Vérifier la complétude [#vérifier-la-complétude]

Après l’enregistrement, la colonne « Complétude » de la liste indique « À compléter » avec les éléments manquants. Voir [la complétude](/docs/catalogue/completude).
</Step>
</Steps>

## Onglets de la fiche catalogue [#onglets-de-la-fiche-catalogue]

| Onglet | Contenu |
|---|---|
| Caractéristiques | Valeurs techniques propres à l’univers du site, avec leurs unités. Voir [les univers](/docs/catalogue/univers) |
| Documents | Fiches techniques, notices, FDS, DoP, FDES, certificats, plans, garanties. Voir [les documents](/docs/catalogue/documents) |
| Compatibilités | Accessoires et pièces compatibles, choisis parmi les produits |
| Identification | Référence fabricant, EAN / GTIN, objet BIM, conditionnement |
| Synchronisation | Origine des données et champs pilotés par l’ERP |

### Identification [#identification]

- **Référence fabricant** : à renseigner si elle diffère de l’UGS.
- **EAN / GTIN** : 8, 12, 13 ou 14 chiffres. Il alimente aussi les données structurées de la page.
- **Objet BIM** : adresse du fichier.
- **Conditionnement** : quantité par unité de vente, unité (unité, lot, boîte, carton, palette, m², mètre linéaire, kg, litre) et minimum de commande.

## Réglages commerciaux de la fiche [#réglages-commerciaux-de-la-fiche]

| Où | Champ | Effet |
|---|---|---|
| Général | **Visible par** | Réserve le produit à tout le monde, aux comptes pros, ou à des groupes. Voir [la visibilité](/docs/tarifs-commandes/visibilite) |
| Général | **Prix sur devis** | Aucun prix affiché, même aux pros ; produit non commandable ; bouton de demande de devis conservé |
| Général | **Prix par groupe** | Prix fixe pour un groupe. Voir [les tarifs par groupe](/docs/tarifs-commandes/tarifs-par-groupe) |
| Général | **Prix dégressifs (pros)** | Paliers `quantité = remise %` ou prix unitaire HT. S’appliquent aussi aux déclinaisons |
| Inventaire | **Quantité minimum** et **Vendu par (multiple)** | Règles de quantité. Voir [les règles de commande](/docs/tarifs-commandes/regles-de-commande) |

<Callout title="Champs en lecture seule">
Si votre ERP pilote certains champs (prix, stock, référence…), ils s’affichent grisés avec la mention « Mis à jour par votre ERP » et sont protégés côté serveur. La liste se règle avec `sync.locked_fields`. Voir [les réglages techniques](/docs/reglages/client-json).
</Callout>