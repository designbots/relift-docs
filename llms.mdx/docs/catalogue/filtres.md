# Filtres du catalogue (/docs/catalogue/filtres)

Les filtres permettent de chercher par catégorie, gamme, attribut WooCommerce et caractéristique technique (liste ou plage), plus un champ « référence, désignation, EAN ».

## Deux moteurs [#deux-moteurs]

| Moteur | Quand |
|---|---|
| Filtres natifs de Bricks | Prioritaires dès que le thème Bricks est actif (réglage `auto`) |
| Filtres Relift | Solution de secours, avec le shortcode `[relift_filtres]` |

Les filtres se règlent dans **WooCommerce → Réglages → Relift B2B → Catalogue** : activation, moteur, affichage automatique avant la liste de produits (boutique, catégories, gammes), champ de recherche.

## Garanties [#garanties]

- Les compteurs suivent les mêmes règles que la liste : un produit réservé n’est jamais compté.
- Aucun filtre par prix : les prix peuvent être réservés.
- Les adresses filtrées sont partageables et ne sont pas indexées.

## Réglages avancés [#réglages-avancés]

Dans `client.json` : `catalogue.facets.attributes` (attributs proposés) et `catalogue.facets.max_options` (nombre maximal de valeurs affichées par filtre).