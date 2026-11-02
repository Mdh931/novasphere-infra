# Conventions d'équipe NovaSphere

1. Une branche par changement (`feat/...`, `fix/...`, `chore/...`), jamais de commit direct sur `main`.
2. Toute pull request est relue et approuvée par l'autre membre du binôme avant merge sur `main`.
3. Un tag par séance : `v5.<séance>.0` (`v5.1.0` pour S01).
4. `.gitignore` non négociable : `*.tfstate`, `*.tfvars`, `*.pem`, `.env`, inventaires générés.
5. Le state vit uniquement dans le backend S3 `novasphere-tfstate-mbe` avec `use_lockfile = true`.
6. `dynamodb_table` est déprécié par HashiCorp au profit du verrouillage natif S3 : on ne l'utilise pas.
7. Jamais de `terraform force-unlock` sans avoir vérifié (voix ou message) que personne n'a d'opération en cours.
8. Le plan se lit intégralement avant tout `apply`.
9. Avant de quitter la salle : `terraform destroy` ou `./scripts/stop-evening.sh`.
