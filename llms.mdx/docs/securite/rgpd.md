# Données personnelles (RGPD) (/docs/securite/rgpd)

Toute donnée personnelle collectée par Relift a un **export**, un **effacement** et une **durée de conservation**, accessibles par les outils de WordPress (**Outils → Exporter / Effacer les données personnelles**).

| Donnée | Conservation |
|---|---|
| Demandes de devis | 36 mois par défaut, puis anonymisation (`b2b.quote_retention_months`) |
| Comptes pros (société, SIRET, TVA, consentement) | Tant que le compte existe ; effaçable sur demande |
| Journal d’activité | 12 mois par défaut (`security.log_retention_months`) |

## Consentement [#consentement]

Les formulaires de demande de devis et d’inscription recueillent le consentement ; sa date est conservée et transmise dans le webhook.

## Prix réservés [#prix-réservés]

Un prix réservé ne fuite ni dans la page, ni dans les données structurées, ni dans l’API de la boutique, ni dans le cache de page, ni dans le webhook.