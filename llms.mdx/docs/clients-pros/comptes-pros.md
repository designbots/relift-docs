# Comptes pros (/docs/clients-pros/comptes-pros)

Un **compte pro** ouvre l’accès aux prix et aux conditions réservés aux professionnels, sans extension tierce.

## Inscription [#inscription]

Le formulaire d’inscription pro se trouve sur `wp-login.php?action=relift_pro`. Il est relié depuis l’écran de connexion ; vous pouvez aussi le proposer ailleurs :

- le shortcode `[relift_compte_pro label="Créer un compte pro"]`, masqué aux personnes déjà connectées ;
- la fonction `relift_pro_signup_url()` pour les modèles.

Le formulaire recueille la société, le **SIRET** (14 chiffres, contrôlé), le numéro de TVA intracommunautaire (facultatif, déduit du SIRET si vide et contrôlé auprès du service européen **VIES**), le groupe d’activité, le nom, l’e-mail, le téléphone, le code postal, la ville et un mot de passe. Les messages d’erreur apparaissent à côté du champ concerné.

Réglage : **WooCommerce → Réglages → Relift B2B → Comptes pros** (ou `b2b.signup` dans `client.json`).

## Les trois états [#les-trois-états]

| État | Effet |
|---|---|
| En attente | Le compte est traité comme un visiteur : pas de prix réservés |
| Validé | Accès aux prix, remises et conditions de son groupe |
| Refusé | Pas d’accès aux conditions pros |

## Valider ou refuser [#valider-ou-refuser]

Deux modes, au réglage **Validation des comptes** (`b2b.signup_approval`) :

- **Manuelle** (par défaut) : l’équipe est prévenue par e-mail et valide chaque demande.
- **Automatique** (`vies`) : le compte est activé quand le numéro de TVA est validé par le VIES.

<Steps>
<Step>
### Repérer les demandes [#repérer-les-demandes]

Le tableau de bord signale les comptes à valider ; la liste **Clients pros** propose la vue « Comptes pros à valider ».
</Step>

<Step>
### Décider [#décider]

Sur la ligne du compte : **Valider le compte pro** ou **Refuser**. En lot, cochez plusieurs comptes et choisissez « Valider les comptes pros » ou « Refuser les comptes pros ».
</Step>

<Step>
### Informer [#informer]

Le demandeur reçoit un e-mail d’accusé de réception à l’inscription, puis un e-mail à la décision.
</Step>
</Steps>

L’e-mail d’alerte de l’équipe part à l’adresse **Alertes d’inscription à** (`b2b.signup_email`) ; à défaut, à l’adresse des demandes de devis, puis à l’e-mail d’administration.

## Sur les commandes [#sur-les-commandes]

La société, le SIRET, le numéro de TVA et le groupe du compte pro sont copiés sur chaque commande : ils apparaissent dans l’administration, les e-mails, Mon compte et sont disponibles pour vos connecteurs de facturation.

## B2BKing [#b2bking]

Si votre site utilise déjà B2BKing, `b2b.plugin` vaut `b2bking` : Relift lit alors ses données de compte et reste inactif sur l’inscription et les tarifs.