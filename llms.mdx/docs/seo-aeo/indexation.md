# Indexation et bonnes pratiques (/docs/seo-aeo/indexation)

## Ce que Relift gère [#ce-que-relift-gère]

- **Pages filtrées** : les combinaisons de filtres du catalogue ne sont pas indexées (`noindex, follow`), pour éviter les doublons des pages de catégorie.
- **Plan du site** : les produits et catégories réservés à une audience sont retirés du plan du site WordPress.
- **Pages locales** : une page par ville et catégorie, avec son propre texte. Voir [pages locales](/docs/catalogue/pages-locales).
- **Complétude** : une fiche sans image, caractéristique requise ou document attendu est signalée. Voir [la complétude](/docs/catalogue/completude).

## Extension SEO [#extension-seo]

Relift fonctionne avec SEOPress. Le diagnostic (`wp relift doctor`) contrôle que les balises SEO de Bricks sont désactivées pour éviter les doublons de balises.

## Avant de publier une fiche [#avant-de-publier-une-fiche]

<Steps>
<Step>
### Un titre et une description propres [#un-titre-et-une-description-propres]

Nom du produit, référence fabricant, usage.
</Step>

<Step>
### Des caractéristiques complètes [#des-caractéristiques-complètes]

Elles alimentent les données structurées.
</Step>

<Step>
### Un EAN / GTIN valide [#un-ean--gtin-valide]

8, 12, 13 ou 14 chiffres.
</Step>

<Step>
### Une fiche technique jointe [#une-fiche-technique-jointe]

Un document de type « Fiche technique » au minimum, avec sa version.
</Step>
</Steps>

## Produits réservés [#produits-réservés]

Un produit réservé à une audience n’est ni listé, ni compté, ni présent dans le plan du site pour un visiteur non autorisé : il n’est donc pas trouvable par les moteurs. Ne réservez que ce qui doit l’être.