# Installer le moteur (/docs/demarrage/installation)

Relift est livré comme un jeu d’extensions « must-use » (`mu-plugins`) qui se déploie tel quel sur chaque site. Les différences entre clients passent par la configuration, jamais par une copie du code.

## Prérequis [#prérequis]

- PHP 8.1 (8.2 recommandé) et WordPress 6.6 ou plus.
- WooCommerce avec le stockage des commandes haute performance (HPOS).
- ACF Pro pour les champs de la fiche catalogue.
- Bricks Builder si vous utilisez le thème enfant Relift (balises dynamiques et filtres natifs).

<Callout type="warn" title="Licences">
Bricks, ACF Pro et les autres extensions payantes ne sont jamais fournis avec Relift : vous les installez avec vos propres licences.
</Callout>

## Mise en place [#mise-en-place]

<Steps>
<Step>
### Copier les extensions [#copier-les-extensions]

Copiez le contenu du dossier `mu-plugins/` dans `wp-content/mu-plugins/`. Le fichier `relift-loader.php` charge ensuite les extensions dans le bon ordre.
</Step>

<Step>
### Ajouter la configuration du client [#ajouter-la-configuration-du-client]

Copiez `config/client.example.json` vers `wp-content/relift/client.json`, puis adaptez-le : nom du site, univers, groupes de clients, règles de prix. Pour un autre emplacement, définissez `RELIFT_CONFIG_DIR` dans `wp-config.php`.

Bloquez l’accès web à ce dossier, par exemple avec la règle Nginx `location ^~ /wp-content/relift/ { deny all; }`.
</Step>

<Step>
### Initialiser le site [#initialiser-le-site]

```bash
wp relift init
```

La commande renseigne le nom du site, crée les rôles, règle WooCommerce sans suggestions et calcule la complétude des fiches.
</Step>

<Step>
### Lancer le diagnostic [#lancer-le-diagnostic]

```bash
wp relift doctor
```

Chaque contrôle est affiché avec un statut : OK, avertissement ou erreur. Tout doit être OK ou expliqué. La liste des contrôles est détaillée dans [le diagnostic du site](/docs/reference/diagnostic).
</Step>
</Steps>

## Mises à jour [#mises-à-jour]

Seul le dossier `mu-plugins/` est envoyé à chaque version ; `client.json` reste sur le serveur du client. Le numéro de version installé figure dans le diagnostic.