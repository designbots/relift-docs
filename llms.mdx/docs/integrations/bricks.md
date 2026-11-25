# Bricks : balises et boucles (/docs/integrations/bricks)

Relift s’intègre à Bricks Builder **sans shortcode** pour l’affichage du catalogue : tout se règle dans l’éditeur, par des éléments Bricks et des données dynamiques.

## Balises du groupe « Relift » [#balises-du-groupe--relift-]

Disponibles dans le sélecteur de données dynamiques, dans les modèles, les composants et les boucles de requête :

| Balise | Résultat |
|---|---|
| `{rl_prix_carte}` | « dès 1 234 € HT » si le visiteur voit les prix, sinon « Prix pro HT après connexion » |
| `{rl_prix_ht}` | Le montant HT seul, vide si le prix est réservé |
| `{rl_prix_visible}` | `1` si le prix est visible, vide sinon : à utiliser dans les conditions d’élément |

La décision d’afficher un prix reste prise par le plugin : le thème affiche, il ne décide pas.

## Balises natives de Bricks utiles au catalogue [#balises-natives-de-bricks-utiles-au-catalogue]

- `{post_terms_<taxonomie>}` pour toute taxonomie (gammes `rl_gamme`, catégories, attributs `pa_*`) ; ajoutez `:plain` pour du texte sans lien ;
- `{acf_<champ>}` pour tout champ ACF (caractéristiques, documents, références) ;
- `{post_title}`, `{post_url}`, `{featured_image}`, `{post_excerpt}`.

## Boucles de requête [#boucles-de-requête]

Dans Bricks, la **carte** porte la boucle de requête : Bricks répète l’élément porteur. Les produits, articles, réalisations, témoignages et pages locales se listent ainsi. Les produits réservés sont exclus des boucles, des compteurs et des filtres pour les visiteurs non autorisés.

## Shortcodes conservés [#shortcodes-conservés]

Quelques fonctions restent des shortcodes, à placer dans l’élément Shortcode de Bricks : `[relift_devis_bouton]`, `[relift_devis_compteur]`, `[relift_devis_panier]`, `[relift_compte_pro]`, `[relift_filtres]`.

## Aides pour les modèles PHP [#aides-pour-les-modèles-php]

`relift_spec_rows()`, `relift_documents()`, `relift_config()` et `relift_can_see_price()`.