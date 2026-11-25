# Le fichier client.json (/docs/reglages/client-json)

`client.json` décrit un site client. Il se trouve dans `wp-content/relift/` (ou dans le dossier défini par `RELIFT_CONFIG_DIR`) et n’est pas versionné avec le code.

```json
{
  "client": { "name": "Exemple Menuiseries" },
  "univers": "atelier",
  "b2b": { "prices": "pros", "signup": true, "signup_approval": "manual" },
  "locked": ["b2b.prices"]
}
```

## Clés principales [#clés-principales]

| Clé | Rôle |
|---|---|
| `client.name`, `client.logo` | Nom du site, logo de la page de connexion |
| `univers` | Filière : décide des caractéristiques de la fiche |
| `b2b.*` | Comptes pros, prix, groupes, règles de commande, devis |
| `security.*` | Double authentification, alertes, clés d’accès, journal |
| `support.*` | Libellé, e-mail, lien de rendez-vous et guide affichés au client |
| `sync.locked_fields` | Champs pilotés par l’ERP, en lecture seule |
| `completeness.*` | Ce qui rend une fiche complète |
| `catalogue.facets.*` | Recherche paramétrique |
| `automation.webhook.*` | Webhook sortant signé |
| `admin.*` | Marque blanche, interface, page de connexion |
| `locked` | Chemins imposés, en lecture seule dans l’administration |

La liste complète, avec valeurs par défaut, est dans [la référence de configuration](/docs/reference/configuration).

## Marque et écran de connexion [#marque-et-écran-de-connexion]

`admin.white_label` active la marque blanche. `admin.login.*` personnalise l’écran de connexion : `title`, `text`, `points` (3 ou 4 arguments) et `image` ; sans image, l’écran montre une capture du tableau de bord.

## Après une modification [#après-une-modification]

Le fichier est relu à chaque chargement. Les listes remplacent les valeurs précédentes, les objets sont fusionnés.

<Callout title="Sécurité du dossier">
Le dossier de configuration ne doit pas être lisible depuis le web. Voir [l’installation](/docs/demarrage/installation).
</Callout>