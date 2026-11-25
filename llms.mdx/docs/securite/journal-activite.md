# Journal d’activité (/docs/securite/journal-activite)

Le journal garde la trace des événements qui comptent pour la sécurité et la gestion des comptes.

## Ce qui est enregistré [#ce-qui-est-enregistré]

Connexions et échecs, blocages après trop de tentatives, connexions avec double authentification ou clé d’accès, changements de rôle, validations et refus de comptes pros, modifications de réglages, imports de prix, exports et demandes de devis. Les échecs d’envoi du webhook y figurent aussi.

## Consulter [#consulter]

Menu **Relift → Journal d’activité** (administrateurs), ou en ligne de commande :

```bash
wp relift log list --event=login_failed --limit=50
```

## Conservation [#conservation]

12 mois par défaut (`security.log_retention_months`), puis purge automatique quotidienne. Le journal est inclus dans l’export et l’effacement RGPD de WordPress.

## En-têtes de sécurité [#en-têtes-de-sécurité]

Relift pose des en-têtes de sécurité par défaut (`security.headers`). Mettez-le à `false` si votre serveur Nginx les envoie déjà.