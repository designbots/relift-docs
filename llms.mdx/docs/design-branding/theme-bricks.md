# Thème et site public (/docs/design-branding/theme-bricks)

Le site public d’un projet Relift se construit avec **Bricks Builder** et le thème enfant de départ Relift. Le thème affiche ; le plugin décide (prix, accès, conditions).

<Callout type="warn" title="Licence Bricks">
Bricks est une extension payante, installée avec votre propre licence. Elle n’est jamais fournie avec Relift.
</Callout>

## Principes [#principes]

- **En-tête et pied de page** sont des **composants** Bricks, placés en première et dernière position de chaque page et modèle.
- Les **modèles** servent aux vues du site : page, produit, catalogue, catégorie, blog, recherche, pages légales, page locale, erreur 404, article.
- Les listes (produits, articles, pages locales) sont des **boucles de requête** modifiables dans l’éditeur.
- Aucune fonction commerciale n’est dans le thème : prix, comptes, panier, devis et visibilité restent dans le plugin.

## Afficher les données Relift [#afficher-les-données-relift]

Les balises dynamiques du groupe « Relift » donnent un prix qui respecte la visibilité, et les champs de la fiche s’insèrent avec `{acf_<champ>}`. Voir [Bricks : balises et boucles](/docs/integrations/bricks).

## Modifier sans tout casser [#modifier-sans-tout-casser]

Les pages et modèles livrés se modifient dans l’éditeur Bricks. Pour les modifications de code du thème, passez par votre équipe technique.

## Typographie et langue [#typographie-et-langue]

Le contenu s’écrit en français avec la typographie française : apostrophe ’, espace insécable avant € et %.