# Commit Signing

Om 100% te kunnen garanderen dat jouw commit ook echt jouw commit is, is het van belang je commits te signen. Dit kan met behulp van GPG keys, die je instelt op zowel de client als server (github.com). Dan krijgen zaken als [Git blame someone else](https://github.com/jayphelps/git-blame-someone-else) geen kans.

Github heeft zelf tutorials gepubliceerd om dit te doen. Dit zijn:

- [Signing commits](https://docs.github.com/en/authentication/managing-commit-signature-verification/signing-commits)
- [Telling Git about your GPG key](https://docs.github.com/en/authentication/managing-commit-signature-verification/telling-git-about-your-signing-key)
- [Adding a new GPG key to your GitHub account](https://docs.github.com/en/authentication/managing-commit-signature-verification/adding-a-new-gpg-key-to-your-github-account)
  
Met deze guides moet je een heel eind komen. Best practices die ik zelf hanteer:

- Geen globale git config, maar per repo door flag `--global` weg te laten.
  - Pro: Je kunt een apart emailadres gebruiken voor ieder project. (`git config user.email`). Bijv. 1 voor werk, 1 voor privé, 1 voor onderwijsactiviteiten.
  - Pro: Je kunt een aparte GPG key gebruiken voor ieder project. (`git config user.signingkey`). Handig als je ook meerdere e-mailadressen gebruikt; zie hieronder.
  - Con: Helaas moet je wel voor iedere nieuwe `git clone` deze instellingen opnieuw zetten. Voordeel van geen globale config is dat je verplicht bent om dit in te stellen (je krijgt een prompt). Als je wel een globale config hebt kun je dit nog wel eens vergeten, en dan heb je potentieel al commits in je history staan onder verkeerde email/key. History rewrites zijn nooit zo fantastisch.

- Koppel het e-mailadres dat je gebruikt voor git ook aan je GPG key. Gebruik je meerdere e-mailadressen? Maak dan een key aan per e-mailadres.
