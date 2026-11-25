# Groupes de clients (/docs/clients-pros/groupes)

Un **groupe** rassemble des clients qui ont les mêmes conditions. Le groupe est choisi à l’inscription, puis modifiable par l’équipe sur la fiche du compte.

## Créer ou modifier les groupes [#créer-ou-modifier-les-groupes]

**WooCommerce → Réglages → Relift B2B → Comptes pros**, tableau **Groupes** : un nom affiché et un identifiant (sans accents ni espaces).

```json
"groups": [
  { "slug": "installateur", "label": "Installateur, poseur" },
  { "slug": "distributeur", "label": "Distributeur, négoce" },
  { "slug": "prescripteur", "label": "Architecte, bureau d’études" }
]
```

<Callout type="warn" title="Identifiant stable">
L’identifiant sert dans les règles de prix et de visibilité. Le modifier après coup demande de reprendre ces règles.
</Callout>

## Ce qu’un groupe détermine [#ce-quun-groupe-détermine]

- remise générale et remises par catégorie ;
- paliers dégressifs et minimum de commande ;
- prix fixes par produit ;
- produits et catégories visibles ;
- modes de livraison et de paiement proposés.

Chaque point se règle dans [les tarifs par groupe](/docs/tarifs-commandes/tarifs-par-groupe) et [les règles de commande](/docs/tarifs-commandes/regles-de-commande).