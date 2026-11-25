# Demandes de devis (/docs/devis/demandes-de-devis)

## Côté visiteur [#côté-visiteur]

Le visiteur ajoute des produits à un **panier de devis**, gardé dans son navigateur (les pages restent donc en cache), puis envoie sa demande depuis la page de devis.

<Steps>
<Step>
### Créer la page [#créer-la-page]

Une page contenant le shortcode `[relift_devis_panier]`, par défaut à l’adresse `/demande-de-devis/` (réglage `b2b.quote_page`).
</Step>

<Step>
### Placer les boutons [#placer-les-boutons]

Sur les fiches WooCommerce, le bouton « Ajouter au devis » s’ajoute automatiquement (`b2b.quote_button_auto`). Dans Bricks, utilisez l’élément Shortcode avec `[relift_devis_bouton]` et `[relift_devis_compteur]`.
</Step>
</Steps>

L’envoi est protégé : champ piège, délai minimal, 5 demandes par heure et par adresse. Le formulaire recueille le consentement et n’affiche jamais de prix réservé.

## Côté équipe [#côté-équipe]

Menu **Demandes de devis** : chaque demande est une fiche avec société, produits, date de réception, **statut** et **note interne**.

| Statut | Sens |
|---|---|
| Nouvelle | Pas encore traitée |
| En cours | Prise en charge |
| Devis envoyé | Réponse envoyée au client |
| Acceptée | Le client accepte |
| Sans suite | Clôturée |

Le statut se change sur la fiche ou depuis l’écran « Demandes de devis » du tableau de bord. Les demandes sont visibles par les rôles Commercial et Responsable catalogue.

## E-mails [#e-mails]

À chaque demande, deux e-mails partent : un à l’équipe (adresse `b2b.quote_email`, ou e-mail d’administration si vide) et un accusé de réception au demandeur.

## Données personnelles [#données-personnelles]

Les demandes sont incluses dans l’export et l’effacement RGPD de WordPress. Au-delà de `b2b.quote_retention_months` (36 mois par défaut), les coordonnées sont anonymisées.

## Brancher un CRM [#brancher-un-crm]

Chaque nouvelle demande peut être envoyée à un outil d’automatisation : voir [le webhook signé](/docs/integrations/webhook).