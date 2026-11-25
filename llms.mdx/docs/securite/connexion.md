# Connexion sécurisée (/docs/securite/connexion)

Réglages : **WooCommerce → Réglages → Relift B2B → Sécurité**.

## Double authentification [#double-authentification]

Code à 6 chiffres d’une application d’authentification (Google Authenticator, Microsoft Authenticator, 1Password, Bitwarden…), avec **codes de secours**.

- Chaque personne l’active dans **Profil → Double authentification** ; les clients dans **Mon compte → Sécurité**.
- Pour les rôles de l’équipe (`security.two_factor.required_roles`), elle devient **obligatoire** après un délai (`grace_days`, 7 jours par défaut) : un bandeau rappelle la date limite, puis l’accès à l’administration est bloqué jusqu’à l’activation.
- Téléphone perdu : `wp relift 2fa reset`.

## Clés d’accès (WebAuthn) [#clés-daccès-webauthn]

Une clé d’accès (empreinte, visage ou clé de sécurité) avec vérification de l’appareil, remplace le mot de passe et le code de la double authentification. Activées par défaut (`security.passkeys.enabled`), jusqu’à 10 par personne. Elles se gèrent dans **Profil → Clés d’accès**, ou **Mon compte → Sécurité** pour les clients, et demandent une connexion en https.

## Alertes de nouvel appareil [#alertes-de-nouvel-appareil]

Un e-mail est envoyé à la personne lors d’une connexion depuis un appareil inconnu. Réglage : comptes de l’équipe (défaut), tous les comptes, ou désactivée.

## Limitation des tentatives [#limitation-des-tentatives]

Toujours active : après 5 échecs pour un même identifiant depuis une même adresse, la connexion est bloquée 15 minutes ; après 20 échecs depuis une même adresse, elle est bloquée 30 minutes.

## Écran de connexion [#écran-de-connexion]

La page de connexion est en écran partagé et personnalisable. Voir [le fichier client.json](/docs/reglages/client-json).