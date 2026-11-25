# Webhook signé (/docs/integrations/webhook)

Relift peut notifier un outil d’automatisation (Make, Boost.space, n8n, votre CRM) à chaque événement important. L’envoi est un `POST` JSON signé, parti à la fin de la requête pour ne pas ralentir le visiteur.

## Activer [#activer]

<Steps>
<Step>
### Définir le secret [#définir-le-secret]

Dans `wp-config.php`, jamais dans un dépôt ni un e-mail :

```php
define('RELIFT_WEBHOOK_SECRET', 'une-longue-valeur-aléatoire');
```
</Step>

<Step>
### Renseigner l’adresse [#renseigner-ladresse]

**Relift B2B → Catalogue → Automatisation** (ou `automation.webhook.url`). En production, l’adresse doit commencer par `https://`.
</Step>

<Step>
### Choisir les événements [#choisir-les-événements]

Cochez les événements voulus (`automation.webhook.events`).
</Step>
</Steps>

Sans secret, **aucun envoi n’est fait** et l’échec est inscrit au journal d’activité.

## Événements [#événements]

| Événement | Quand |
|---|---|
| `quote_created` | Demande de devis reçue |
| `pro_signup` | Demande de compte pro |
| `pro_approved` | Compte pro validé |
| `pro_refused` | Compte pro refusé |

## Contenu [#contenu]

```json
{
  "event": "quote_created",
  "site": "https://exemple.fr",
  "sent_at": "2026-11-25T13:00:00+00:00",
  "data": {
    "quote_id": 123,
    "contact": { "company": "…", "name": "…", "email": "…", "phone": "…" },
    "lines": [ { "sku": "…", "name": "…", "qty": 2 } ],
    "consent_at": "…",
    "source": "…"
  }
}
```

Le contenu est volontairement minimal : **aucun prix** (ils peuvent être réservés), les coordonnées de la personne et la date de son consentement. Pour les événements `pro_*`, `data` contient `user_id`, `contact`, `group`, `status` et `consent_at`.

## Vérifier la signature [#vérifier-la-signature]

Chaque envoi porte deux en-têtes : `X-Relift-Event` et `X-Relift-Signature`, de la forme `t=<horodatage>,v1=<signature>`. La signature est un HMAC-SHA256 de `<horodatage>.<corps brut>` avec votre secret.

```php
$entete = $_SERVER['HTTP_X_RELIFT_SIGNATURE'] ?? '';
parse_str(str_replace(',', '&', $entete), $p);   // t, v1
$corps = file_get_contents('php://input');
$attendu = hash_hmac('sha256', $p['t'] . '.' . $corps, $secret);
if (!hash_equals($attendu, $p['v1'] ?? '') || abs(time() - (int) $p['t']) > 300) {
    http_response_code(401); exit;
}
```

Refusez les envois dont l’horodatage est trop ancien. Répondez avec un code `2xx` pour confirmer la réception : tout autre code est inscrit au journal d’activité.