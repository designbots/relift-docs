# Tarifs par groupe (/docs/tarifs-commandes/tarifs-par-groupe)

Le prix d’un produit pour un compte pro suit des règles appliquées dans cet ordre :

1. le **prix fixe** du produit pour le groupe ;
2. la remise du groupe pour la **catégorie** du produit ;
3. la remise **générale** du groupe ;
4. les **paliers** dégressifs selon la quantité.

## Où régler [#où-régler]

| Besoin | Où |
|---|---|
| Remise générale, minimum de commande, paliers du groupe | **Relift B2B → Tarifs**, tableau Groupes |
| Remise d’un groupe sur une catégorie | **Relift B2B → Tarifs**, tableau Remises |
| Prix fixe d’un produit pour un groupe | Fiche produit, onglet Général, **Prix par groupe** |
| Paliers propres à un produit | Fiche produit, **Prix dégressifs (pros)** |
| Affichage hors taxes et mention après le prix | **Relift B2B → Tarifs** |

## Paliers [#paliers]

Format : `quantité = remise %`, séparés par des points-virgules, par exemple `10 = 3 % ; 50 = 5 %`. Sur la fiche, une ligne peut aussi donner un prix unitaire HT. Les paliers de la fiche l’emportent sur ceux du groupe ; les paliers s’appliquent aussi aux déclinaisons. Réglage **Prix dégressifs pour** : les comptes pros validés ou tous les acheteurs qui voient les prix.

## Importer des prix fixes [#importer-des-prix-fixes]

Un fichier CSV (séparateur `;` ou `,`) avec trois colonnes : **référence (UGS)**, **identifiant du groupe**, **prix**. Un prix vide supprime le prix fixe. L’en-tête est ignoré.

```csv
sku;groupe;prix
FEN-PVC-1200;installateur;412,50
FEN-PVC-1200;distributeur;380
```

```bash
wp relift prices import prix.csv --dry-run   # vérifie sans rien enregistrer
wp relift prices import prix.csv
wp relift prices show FEN-PVC-1200           # prix public et prix par groupe
```

Les lignes en erreur (groupe inconnu, référence introuvable, prix invalide) sont signalées avec leur numéro. L’import est inscrit au [journal d’activité](/docs/securite/journal-activite).