# Clés de configuration (/docs/reference/configuration)

Les clés s’écrivent en JSON imbriqué dans `client.json`, ou en notation pointée dans `locked` (`b2b.prices`).

## Identité et univers [#identité-et-univers]

| Clé | Défaut | Effet |
|---|---|---|
| `client.name` | Titre du site | Nom affiché |
| `client.logo` | vide | Logo de la page de connexion |
| `univers` | `atelier` | `lagon`, `solaire`, `canopee`, `atelier`, `mineral` ou `confort` |

## Comptes, prix, commandes (`b2b`) [#comptes-prix-commandes-b2b]

| Clé | Défaut | Effet |
|---|---|---|
| `b2b.plugin` | `relift` | `relift` ou `b2bking` |
| `b2b.prices` | `pros` | `public`, `logged_in` ou `pros` |
| `b2b.enforce_display` | `auto` | Message « Prix réservés » seulement si B2BKing est absent |
| `b2b.signup` | `true` | Inscription pro |
| `b2b.signup_approval` | `manual` | `manual` ou `vies` |
| `b2b.signup_email` | vide | Destinataire des inscriptions |
| `b2b.groups` | 3 groupes | Liste `{slug, label}` |
| `b2b.pricing.tax_display` | `excl` | `excl`, `incl` ou vide (réglage WooCommerce) |
| `b2b.pricing.suffix` | `HT` | Mention après le prix |
| `b2b.pricing.tiers_for` | `pros` | `pros` ou `all` |
| `b2b.pricing.groups.<groupe>` | vide | `discount`, `categories`, `tiers`, `min_order` |
| `b2b.cart_rules` | vide | Franco et remise par seuil |
| `b2b.payment_rules` | vide | Moyens de paiement réservés (`for` : `pros`, `nonpros`, `groups`) |
| `b2b.shipping_rules` | vide | Modes de livraison réservés (`i:<id>` pour un mode d’une zone, `t:<type>` pour toutes les zones) |
| `b2b.quantities_for` | `all` | `all` ou `pros` |
| `b2b.quotes` | `true` | Demandes de devis |
| `b2b.quote_email` | vide | Destinataire des demandes |
| `b2b.quote_page` | `/demande-de-devis/` | Page contenant `[relift_devis_panier]` |
| `b2b.quote_button_auto` | `true` | Bouton ajouté aux fiches WooCommerce |
| `b2b.quote_retention_months` | `36` | Anonymisation des demandes |

Exemple de règles de panier :

```json
"cart_rules": [
  { "type": "franco", "min": 500 },
  { "type": "discount", "min": 1500, "discount": 3, "groups": ["distributeur"], "label": "Remise volume" }
]
```

## Catalogue et synchronisation [#catalogue-et-synchronisation]

| Clé | Défaut | Effet |
|---|---|---|
| `completeness.require_image` | `true` | Image exigée |
| `completeness.require_specs` | `true` | Caractéristiques requises exigées |
| `completeness.require_document_types` | `["fiche_technique"]` | Types de documents exigés |
| `catalogue.facets.enabled` | `true` | Filtres actifs |
| `catalogue.facets.engine` | `auto` | `auto`, `relift`, `bricks` ou `off` |
| `catalogue.facets.auto` | `true` | Filtres avant la liste de produits |
| `catalogue.facets.search` | `true` | Champ « référence, désignation, EAN » |
| `catalogue.facets.attributes` | vide | Attributs proposés |
| `catalogue.facets.max_options` | `12` | Valeurs affichées par filtre |
| `sync.locked_fields` | vide | Champs pilotés par l’ERP : `_regular_price`, `_sale_price`, `_stock`, `_stock_status`, `_sku`, `_weight`, `_length`, `_width`, `_height`, `rl_gtin`, `rl_specs_<nom>`… |
| `schema.enrich_woocommerce` | `true` | Enrichit le JSON-LD Product |

## Automatisation, sécurité, administration [#automatisation-sécurité-administration]

| Clé | Défaut | Effet |
|---|---|---|
| `automation.webhook.url` | vide | Adresse de réception (https en production) |
| `automation.webhook.events` | tous | `quote_created`, `pro_signup`, `pro_approved`, `pro_refused` |
| `security.two_factor.enabled` | `true` | Double authentification proposée |
| `security.two_factor.required_roles` | rôles de l’équipe | Rôles pour qui elle devient obligatoire |
| `security.two_factor.grace_days` | `7` | Délai avant obligation |
| `security.login_alerts` | `team` | `team`, `all` ou `off` |
| `security.passkeys.enabled` | `true` | Clés d’accès |
| `security.passkeys.max_per_user` | `10` | Nombre maximal par personne |
| `security.headers` | `true` | En-têtes de sécurité |
| `security.log_retention_months` | `12` | Conservation du journal |
| `admin.white_label` | `true` | Marque blanche |
| `admin.app_ui` | `true` | Interface Relift (`false` : interface WordPress habillée) |
| `admin.login.*` | — | `title`, `text`, `points`, `image` |
| `support.*` | — | `label`, `email`, `booking_url`, `docs_url` |
| `locked` | vide | Chemins imposés, en lecture seule dans l’administration |