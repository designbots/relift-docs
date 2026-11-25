# Points d’extension (/docs/reference/points-extension)

Les hooks de Relift commencent tous par `relift/`.

## Configuration et catalogue [#configuration-et-catalogue]

| Hook | Rôle |
|---|---|
| `relift/config` | Modifier la configuration finale |
| `relift/univers` | Adapter l’univers actif |
| `relift/specs/rows` | Lignes de caractéristiques affichées |
| `relift/schema/product` | JSON-LD Product enrichi |
| `relift/completeness/evaluate` | Règles de complétude |
| `relift/sync/locked_fields` | Champs en lecture seule |
| `relift/health/checks` | Contrôles du diagnostic |
| `relift/settings/sections` | Sections de l’écran de réglages |

## Comptes, prix et devis [#comptes-prix-et-devis]

| Hook | Rôle |
|---|---|
| `relift/b2b/can_see_price` | Décision d’afficher un prix |
| `relift/b2b/price_message` | Message affiché à la place du prix |
| `relift/b2b/account_status` | Statut d’un compte |
| `relift/b2b/quote_rate_limit` | Limite d’envoi des devis |
| `relift/b2b/quote_ack_body` | Texte de l’accusé de réception |
| `relift/b2b/quote_created` (action) | Après la création d’une demande |
| `relift/commerce/mail` | Sujet et texte des e-mails de compte |
| `relift/commerce/prices_imported` (action) | Après un import de prix |

## Administration et sécurité [#administration-et-sécurité]

| Hook | Rôle |
|---|---|
| `relift/admin/menu_map` | Carte des menus des rôles client |
| `relift/admin/roles` | Rôles Relift |
| `relift/admin/dashboard/quotes`, `…/pending_accounts`, `…/sync` | Données du tableau de bord |
| `relift/security/headers_list` | En-têtes de sécurité |
| `relift/security/event` (action) | Écrire dans le journal d’activité |

```php
do_action('relift/security/event', 'mon_evenement', $user_id, 'détail');
```