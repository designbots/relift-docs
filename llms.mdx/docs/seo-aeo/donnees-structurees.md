# Données structurées (/docs/seo-aeo/donnees-structurees)

Les moteurs de recherche et les moteurs de réponse lisent mieux une page dont les informations sont déclarées proprement. Relift enrichit le JSON-LD **Product** de WooCommerce à partir de la fiche catalogue (`schema.enrich_woocommerce`, actif par défaut).

## Ce qui est ajouté [#ce-qui-est-ajouté]

| Donnée | Source |
|---|---|
| `mpn` | Référence fabricant |
| `gtin8`, `gtin12`, `gtin13`, `gtin14` | EAN / GTIN |
| `additionalProperty` | Caractéristiques techniques, avec leurs unités |
| `subjectOf` | Documents (fiche technique, notice, FDS…) |
| `isRelatedTo` | Accessoires compatibles d’un produit |
| `isAccessoryOrSparePartFor` | Sur l’accessoire, calculé par relation inverse |

Seul ce qui est saisi sur la fiche est publié.

## Prix réservés [#prix-réservés]

Un prix réservé n’apparaît pas dans le JSON-LD : les offres sont retirées pour un visiteur non autorisé. Voir [la visibilité](/docs/tarifs-commandes/visibilite).

## Contrôler le résultat [#contrôler-le-résultat]

```bash
wp relift schema <id-du-produit>
```

La commande affiche le JSON-LD Product enrichi d’une fiche. Vous pouvez aussi le tester avec les outils de validation des moteurs de recherche.

## Pages locales [#pages-locales]

Les [pages locales](/docs/catalogue/pages-locales) publient des données WebPage, FAQPage et LocalBusiness qui décrivent uniquement ce qui est écrit sur la page.

<Callout title="Aucune promesse de classement">
Relift fournit des données propres et lisibles. Il ne garantit ni classement, ni citation par des moteurs de réponse : le travail porte sur la qualité et la lisibilité des données.
</Callout>