# Visibilité des prix et du catalogue (/docs/tarifs-commandes/visibilite)

## Qui voit les prix [#qui-voit-les-prix]

**WooCommerce → Réglages → Relift B2B → Catalogue** (ou `b2b.prices`) :

| Valeur | Effet |
|---|---|
| Les comptes pros validés (`pros`) | Seuls les comptes pros validés et l’équipe voient les prix |
| Toute personne connectée (`logged_in`) | Tout compte connecté voit les prix |
| Tout le monde (`public`) | Prix visibles de tous |

Un prix réservé n’apparaît **nulle part** pour un visiteur non autorisé : ni dans la page, ni dans les données structurées (JSON-LD), ni dans l’API de la boutique (Store API), ni dans le cache de page. Chaque règle est couverte par un test automatique. À la place du prix, la page affiche « Prix pro HT après connexion ».

Les prix des pros s’affichent **hors taxes**, avec la mention HT (réglable).

## Visibilité des produits et des catégories [#visibilité-des-produits-et-des-catégories]

Sur la fiche produit (onglet **Général**) et dans l’écran d’une catégorie, le champ **Visible par** propose : tout le monde, comptes pros validés, ou certains groupes.

- Les règles d’une catégorie s’appliquent à ses sous-catégories et à ses produits.
- Un produit réservé est absent des listes, des catégories, de la recherche, des filtres et de leurs compteurs pour un visiteur non autorisé.

## Prix sur devis [#prix-sur-devis]

Cochez **Prix sur devis** (onglet Général) : aucun prix n’est affiché, même aux pros, le produit n’est pas commandable et le bouton de demande de devis reste proposé. Voir [les demandes de devis](/docs/devis/demandes-de-devis).