# Tableau de bord et suivi (/docs/suivi/tableau-de-bord)

Relift ne s’appuie pas sur un outil de mesure d’audience : il fournit le suivi de l’activité commerciale et de la sécurité, dans l’administration.

<Callout title="Mesure d’audience">
Relift n’intègre pas d’outil de mesure d’audience (visites, sources de trafic). Utilisez l’outil de votre choix ; l’ajout se fait dans le thème ou par une extension, avec le consentement des visiteurs.
</Callout>

## Tableau de bord [#tableau-de-bord]

| Bloc | Contenu |
|---|---|
| Demandes de devis | Dernières demandes et leur statut, modifiable sur place |
| Comptes pros à valider | Comptes en attente, avec accès direct à la validation |
| Synchronisation | État des échanges avec votre ERP ou votre outil d’automatisation |
| Assistance | Contact, prise de rendez-vous et guide, selon `support.*` |

## Suivre les demandes [#suivre-les-demandes]

Menu **Demandes de devis** : filtres par statut (Nouvelle, En cours, Devis envoyé, Acceptée, Sans suite) et note interne. Voir [les demandes de devis](/docs/devis/demandes-de-devis).

## Suivre la qualité du catalogue [#suivre-la-qualité-du-catalogue]

La colonne **Complétude** de la liste des produits et la commande `wp relift completeness` indiquent les fiches à compléter. Voir [la complétude](/docs/catalogue/completude).

## Suivre la sécurité [#suivre-la-sécurité]

Le [journal d’activité](/docs/securite/journal-activite) liste connexions, échecs, changements de rôle, validations de comptes, imports et exports.

## Suivre la santé du site [#suivre-la-santé-du-site]

`wp relift doctor` : versions, HTTPS, cache, mises à jour et configuration. Voir [le diagnostic](/docs/reference/diagnostic).

## Recevoir les événements ailleurs [#recevoir-les-événements-ailleurs]

Le [webhook signé](/docs/integrations/webhook) envoie les demandes de devis et les comptes pros vers l’outil de votre choix, pour les compter ou les suivre dans vos propres tableaux.