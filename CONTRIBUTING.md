# Règles de travail de l'équipe

## Branches

- `main` contient toujours une version qui fonctionne. **Personne ne pousse directement sur `main`** : la branche est protégée sur GitHub.
- Une branche par user story : `feature/USxx-description-courte`
  - exemples : `feature/US05-docker-compose`, `feature/US06-parser-hdfs`
- Une correction de bug : `fix/description-courte`

```bash
git switch main
git pull
git switch -c feature/US06-parser-hdfs
```

## Messages de commit

Format : `USxx: verbe à l'infinitif + ce qui change`

```
US06: ajouter le parser pour les logs HDFS
US06: tester le parsing sur 10 lignes types
```

Des commits petits et fréquents valent mieux qu'un gros commit en fin de semaine.

## Pull requests

1. Pousser sa branche puis ouvrir une pull request vers `main`.
2. Décrire ce qui change et comment le tester.
3. **Un autre membre relit et approuve** avant la fusion.
4. Fusionner, puis supprimer la branche.

## Definition of Done

Une story est **terminée** seulement si :

- [ ] tous ses critères d'acceptation sont remplis ;
- [ ] le code est sur `main` via une pull request relue ;
- [ ] les tests passent ;
- [ ] c'est documenté ;
- [ ] le Product Owner l'a validée en revue de sprint.

## Interdits

- Aucune donnée, aucun modèle entraîné, aucun mot de passe dans Git.