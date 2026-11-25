# Commandes WP-CLI (/docs/integrations/wp-cli)

Les commandes `wp relift` servent aux équipes techniques et aux déploiements. Elles s’exécutent depuis le dossier du site.

## Site et catalogue [#site-et-catalogue]

```bash
wp relift doctor [--format=json]    # santé du site ; code de sortie 1 en cas d’échec
wp relift init                      # initialise un site cloné
wp relift config                    # configuration active
wp relift univers list|show|set     # univers et caractéristiques
wp relift completeness              # recalcule la complétude des fiches
wp relift schema <id>               # JSON-LD Product enrichi d’une fiche
```

## Prix [#prix]

```bash
wp relift prices import prix.csv [--dry-run]
wp relift prices show <sku>
```

Format du fichier : voir [tarifs par groupe](/docs/tarifs-commandes/tarifs-par-groupe).

## Sécurité [#sécurité]

```bash
wp relift log list [--event=<événement>] [--limit=<n>]
wp relift log purge
wp relift 2fa status
wp relift 2fa reset <identifiant, e-mail ou numéro>
```

`2fa reset` sert quand une personne perd son téléphone : elle devra réactiver la double authentification.

<Callout type="warn" title="Catalogue de démonstration">
`wp relift demo install` crée un catalogue d’exemple pour la recette. Ne l’utilisez jamais sur un site de production.
</Callout>