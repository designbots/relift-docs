# Diagnostic du site (/docs/reference/diagnostic)

```bash
wp relift doctor
```

Chaque contrôle renvoie un identifiant, un libellé, un statut (**ok**, **warning**, **error**) et un message. Le code de sortie vaut 1 en cas d’erreur ; `--format=json` produit une sortie lisible par une machine.

| Contrôle | Ce qu’il vérifie |
|---|---|
| PHP, WordPress, WooCommerce | Versions minimales |
| Stockage des commandes (HPOS) | Activé |
| ACF Pro | Présent pour les champs de la fiche |
| Bricks | Présent, avec ses balises SEO désactivées si SEOPress est utilisé |
| SEOPress | Détection |
| B2BKing | Présent si la configuration l’attend |
| Configuration client, dossier de configuration | Fichier valide, dossier non lisible depuis le web |
| Univers | Univers actif et nombre de caractéristiques |
| Fiches | Complétude du catalogue |
| Filtres du catalogue | Moteur actif |
| Automatisation | Secret et adresse du webhook |
| Journal d’activité | Table et purge planifiée |
| HTTPS | Site servi en https |
| Mémoire PHP, cache objet | Réglages du serveur |
| Mode débogage, affichage des erreurs, éditeur de fichiers | Réglages de production |
| Mises à jour | Mises à jour en attente |
| Catalogue de démonstration | Absent d’un site de production |

## Ajouter un contrôle [#ajouter-un-contrôle]

Les équipes techniques peuvent ajouter leurs propres contrôles avec le filtre `relift/health/checks`.