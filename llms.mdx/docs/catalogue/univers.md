# Les univers (/docs/catalogue/univers)

Un **univers** décide des caractéristiques que la fiche propose. Il se choisit une fois pour le site, avec la clé `univers` de `client.json`.

| Clé | Nom | Filière | Caractéristiques |
|---|---|---|---|
| `lagon` | Lagon | Piscine et spa | 10 |
| `solaire` | Solaire | Terrasse et extérieur | 9 |
| `canopee` | Canopée | Paysage | 8 |
| `atelier` | Atelier | Menuiserie et fermetures | 10 |
| `mineral` | Minéral | Isolation et enveloppe | 7 |
| `confort` | Confort | Chauffage et sanitaire | 8 |

Chaque caractéristique a un nom, une unité (mm, m³, kW…) et un indicateur « requise ». Les caractéristiques requises comptent dans la [complétude](/docs/catalogue/completude).

## Afficher l’univers actif [#afficher-lunivers-actif]

```bash
wp relift univers list
wp relift univers show
```

## Adapter un univers à un client [#adapter-un-univers-à-un-client]

Un univers peut être surchargé pour un client : déposez un fichier `<clé>.json` dans le dossier `univers/` de `RELIFT_CONFIG_DIR`. Le fichier suit la structure des univers livrés (nom, filière, couleur d’accent, liste de caractéristiques).

## Données structurées [#données-structurées]

Les caractéristiques saisies sont ajoutées au JSON-LD Product de WooCommerce (`additionalProperty`, avec leurs unités), ainsi que la référence fabricant (`mpn`), le GTIN et les documents (`subjectOf`). Les accessoires compatibles alimentent `isRelatedTo` et `isAccessoryOrSparePartFor`. Seul ce qui est saisi sur la fiche est publié.