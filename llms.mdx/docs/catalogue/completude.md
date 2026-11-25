# La complétude des fiches (/docs/catalogue/completude)

Chaque fiche porte un indicateur de complétude, recalculé à chaque enregistrement.

## Ce que l’on contrôle [#ce-que-lon-contrôle]

| Élément | Condition par défaut |
|---|---|
| Image | Une image mise en avant |
| Caractéristiques | Toutes les caractéristiques « requises » de l’univers sont renseignées |
| Documents | Les types de documents exigés sont présents (par défaut : fiche technique) |

## Dans l’administration [#dans-ladministration]

- La liste des produits a une colonne **Complétude** : une pastille « À compléter » avec la liste de ce qui manque.
- Un filtre au-dessus de la liste isole les fiches incomplètes.

## Régler les critères [#régler-les-critères]

Clé `completeness` de `client.json` :

```json
"completeness": {
  "require_image": true,
  "require_specs": true,
  "require_document_types": ["fiche_technique"]
}
```

Les identifiants de type de document sont `fiche_technique`, `notice`, `fds`, `dop`, `fdes`, `certificat`, `plan`, `garantie`, `autre`.

## Recalculer tout le catalogue [#recalculer-tout-le-catalogue]

Après un changement de critères ou un import massif :

```bash
wp relift completeness
```