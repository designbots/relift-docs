# Écrans de réglage (/docs/reglages/reglages-admin)

Les réglages B2B se modifient dans **WooCommerce → Réglages → Relift B2B**. Le menu **Réglages** (Relift) regroupe les réglages du site, du support et de la marque blanche.

## Les sections [#les-sections]

| Section | Ce que vous y réglez |
|---|---|
| Comptes pros | Inscription, validation (manuelle ou VIES), destinataire des alertes, groupes |
| Tarifs | Affichage HT, mention, groupes (remise, minimum, paliers), remises par catégorie |
| Panier et livraison | Règles de franco et de remise, règles de quantité, modes de livraison réservés |
| Paiement | Moyens de paiement réservés, paiement à échéance |
| Catalogue | Qui voit les prix, demandes de devis, webhook, recherche et filtres, visibilité |
| Sécurité | Double authentification, alertes de connexion, clés d’accès |
| Import et export | Copier la configuration d’un site à l’autre |

## D’où vient une valeur [#doù-vient-une-valeur]

Relift lit chaque réglage dans cet ordre, du plus faible au plus fort :

1. les valeurs par défaut du moteur ;
2. le fichier `client.json` ;
3. les réglages saisis dans l’administration ;
4. le filtre `relift/config` (pour les équipes techniques).

Pour imposer une valeur depuis le fichier, listez son chemin dans `"locked"` : elle s’affiche alors en **lecture seule** dans l’administration. Les listes (groupes, règles) remplacent entièrement la valeur précédente.

## Import et export [#import-et-export]

Section **Import et export** : exportez la configuration d’un site au format JSON, collez-la sur un autre site puis enregistrez. Les réglages imposés par `client.json` ne sont jamais remplacés. L’option **Réinitialiser** efface les réglages saisis dans l’administration et revient aux valeurs de `client.json`.

<Callout type="warn" title="Avant d’importer">
Les réglages actuels de l’administration sont remplacés par ceux du fichier collé. Exportez d’abord le site cible pour garder une copie.
</Callout>