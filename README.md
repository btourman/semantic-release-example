## Comment lancer semantic-release sans CI
- Créer un token github qui possède les droits "repos" à minima
- Lancer la commande `GITHUB_TOKEN=***** npx semantic-release --no-ci`

## Comment éviter que semantic-release essaie d'envoyer une version sur npm
- Dans le `package.json`, ajouter `"private": true,`

## Comment spécifier sur quels branches peut s'exécuter semantic-release
- Dans le fichier `.releaserc`, spécifier les branches avec `"branches": ["main"]`

## Commment générer automatiquement un changelog
- Dans le fichier `.releaserc`, ajouter le plugin `"@semantic-release/changelog"`. Bien le mettre avant `""@semantic-release/git"` pour qu'il soit push sur le repo
```
"plugins": [
    "@semantic-release/commit-analyzer",
    "@semantic-release/release-notes-generator",
    "@semantic-release/npm",
    "@semantic-release/changelog",
    "@semantic-release/git",
    "@semantic-release/github"
  ]
```