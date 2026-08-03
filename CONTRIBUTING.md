
# Guide de contribution (CONTRIBUTING.md)

## Definition

Le fichier CONTRIBUTING.md est un document place a la racine d'un depot public. Il explique aux personnes exterieures comment contribuer au projet : signaler un bug, proposer une amelioration, soumettre du code.

Meme pour un projet solo, ce fichier est utile. Il montre que le projet est ouvert aux contributions et donne un cadre clair pour interagir.

## Pourquoi avoir un CONTRIBUTING.md

- Encourager les contributions en supprimant l'incertitude ("Est-ce que je peux contribuer ? Comment ?").
- Definir les regles du jeu avant que la premiere contribution arrive.
- Gagner du temps en evitant de repondre aux memes questions.
- Donner une image professionnelle et structuree du projet.
- Pour un projet solo, cela force a reflechir a la maniere dont on souhaite collaborer.

## Ou placer le fichier

A la racine du projet : `CONTRIBUTING.md`.

GitHub detecte automatiquement ce fichier et affiche un lien "Contributing" en haut du depot, ainsi qu'un bandeau lors de la creation d'une issue ou d'une pull request.

## Modele complet

# Contribuer au projet

Merci de votre interet pour contribuer a ce projet. Ce document definit les regles et les bonnes pratiques pour proposer une contribution.

## Code de conduite

Ce projet adhere au [Contributor Covenant](https://www.contributor-covenant.org/). En participant, vous acceptez de respecter ce code de conduite. Les comportements inacceptables peuvent etre signales a [email@exemple.com].

## Comment contribuer

Il y a plusieurs facons de contribuer, toutes sont precieuses.

### Signaler un bug

Si vous rencontrez un bug, ouvrez une issue en suivant ces etapes :

1. Verifier que le bug n'a pas deja ete signale dans les [issues existantes](https://github.com/utilisateur/projet/issues).
2. Ouvrir une nouvelle issue avec le titre et la description.
3. Inclure les informations suivantes :
   - Description claire du bug.
   - Etapes detaillees pour reproduire le probleme.
   - Comportement attendu.
   - Comportement observe.
   - Captures d'ecran si pertinent.
   - Environnement (navigateur, systeme d'exploitation, version du projet).

### Proposer une amelioration

Si vous avez une idee de fonctionnalite ou d'amelioration :

1. Verifier que l'idee n'a pas deja ete proposee dans les [issues existantes](https://github.com/utilisateur/projet/issues).
2. Ouvrir une nouvelle issue avec le titre et la description.
3. Inclure les informations suivantes :
   - Description de l'amelioration.
   - Pourquoi elle serait utile.
   - Comment elle pourrait fonctionner (proposition technique si possible).

### Corriger un bug ou ajouter une fonctionnalite

Si vous souhaitez ecrire du code :

1. Commenter l'issue correspondante pour indiquer que vous travaillez dessus. Cela evite les efforts en doublon.
2. Attendre qu'un mainteneur confirme que la contribution est bienvenue.
3. Suivre le processus de developpement decrit ci-dessous.

## Processus de developpement

### 1. Forker le depot

Cliquer sur le bouton "Fork" en haut a droite du depot. Cela cree une copie du projet dans votre compte GitHub.

### 2. Cloner votre fork

```bash
git clone https://github.com/votre-compte/nom-du-projet.git
cd nom-du-projet
```

### 3. Ajouter le depot original comme remote

```bash
git remote add upstream https://github.com/utilisateur-original/nom-du-projet.git
```

Cela permet de maintenir votre fork a jour avec le depot original.

### 4. Creer une branche

```bash
git checkout -b feature/ma-fonctionnalite
```

Utiliser un prefixe clair :
- `feature/` pour une nouvelle fonctionnalite.
- `fix/` pour une correction de bug.
- `docs/` pour la documentation.
- `refactor/` pour du refactoring.

### 5. Developper

- Respecter les conventions de code du projet (ESLint, Prettier).
- Ecrire des tests si le projet en contient.
- Faire des commits atomiques avec des messages conventionnels.

### 6. Tester en local

```bash
npm test
npm run lint
npm run format:check
```

### 7. Mettre a jour votre branche

Avant de soumettre votre travail, synchroniser avec le depot original :

```bash
git fetch upstream
git rebase upstream/main
```

Resoudre les conflits eventuels.

### 8. Pousser votre branche

```bash
git push origin feature/ma-fonctionnalite
```

### 9. Ouvrir une Pull Request

1. Aller sur la page de votre fork sur GitHub.
2. Cliquer sur "Compare & pull request".
3. Remplir le titre et la description de la pull request.
4. Expliquer clairement ce que fait la modification et pourquoi.
5. Referencer l'issue correspondante (ex : "Closes #12").
6. Cliquer sur "Create pull request".

### 10. Revue de code

Un mainteneur examinera votre pull request. Il peut demander des modifications. C'est normal et constructif.

- Repondre aux commentaires.
- Faire les modifications demandees dans votre branche.
- Pousser les modifications : la pull request se met a jour automatiquement.
- Demander une nouvelle revue quand les modifications sont faites.

### 11. Fusion

Quand la pull request est approuvee, un mainteneur la fusionne. Votre contribution fait desormais partie du projet.

## Conventions du projet

### Messages de commit

Ce projet suit la convention [Conventional Commits](https://www.conventionalcommits.org/).

```
<type>(<scope>): <description>
```

Types autorises : `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`.

Exemple : `feat(auth): ajouter la connexion par email`

### Style de code

- Le code est formate avec **Prettier**. Executer `npm run format` avant de commiter.
- Le code est analyse avec **ESLint**. Executer `npm run lint` avant de commiter.
- Les fichiers suivent la configuration `.editorconfig` du projet.
- Les noms de variables et de fonctions sont en anglais.

### Tests

- Les nouvelles fonctionnalites doivent inclure des tests.
- Les corrections de bugs doivent inclure un test qui reproduit le bug.
- Les tests existants doivent continuer de passer.
- Lancer `npm test` avant de soumettre une pull request.

### Documentation

- Les nouvelles fonctionnalites doivent etre documentees dans le README ou dans `docs/`.
- Les changements d'API doivent etre refleter dans `docs/api.md`.
- Le CHANGELOG est mis a jour par les mainteneurs lors d'une nouvelle version.

## Questions

Si vous avez des questions sur le processus de contribution, ouvrez une issue avec le label "question" ou contactez [email@exemple.com].

## Licence

En contribuant a ce projet, vous acceptez que vos contributions soient sous la meme licence que le projet (voir [LICENSE](LICENSE)).

## Remerciements

Toutes les contributions sont valorisees. Merci de prendre le temps d'ameliorer ce projet.


## Modele allege pour projet solo

Si le projet est petit ou que l'on souhaite un fichier plus court :


# Contribuer

Merci de votre interet pour ce projet.

## Signaler un bug

Ouvrir une issue avec :
- Description du bug.
- Etapes pour reproduire.
- Comportement attendu.
- Comportement observe.

## Proposer une amelioration

Ouvrir une issue avec :
- Description de l'amelioration.
- Pourquoi elle est utile.

## Proposer du code

1. Forker le depot.
2. Creer une branche : `feature/ma-fonctionnalite`.
3. Commiter en suivant les [conventions de commits](docs/conventions-commits.md).
4. Pousser la branche.
5. Ouvrir une Pull Request.
6. S'assurer que les tests passent.

## Conventions

- Code formate avec Prettier.
- Messages de commit : `type(scope): description`.
- Tests obligatoires pour les nouvelles fonctionnalites.

## Questions

Ouvrir une issue avec le label "question".


## Personnaliser le modele

Remplacer les elements suivants par les informations reelles du projet :

- `utilisateur/projet` : le chemin du depot GitHub.
- `email@exemple.com` : une adresse de contact valide.
- Les URLs des fichiers de documentation (licence, conventions de commits).
- Les commandes npm specifiques au projet (`npm test`, `npm run lint`).
- Les conventions de style si elles different de Prettier/ESLint.

## Faire reference au CONTRIBUTING.md depuis le README

Ajouter une section dans le README :


## Contribuer

Les contributions sont les bienvenues. Consultez le [guide de contribution](CONTRIBUTING.md) pour savoir comment participer.


## Regles a retenir

1. Toujours avoir un CONTRIBUTING.md si le depot est public.
2. Expliquer les trois manieres de contribuer : signaler un bug, proposer une idee, ecrire du code.
3. Donner les etapes precises pour soumettre du code (fork, branche, commit, PR).
4. Indiquer clairement les conventions du projet (commits, style, tests).
5. Mentionner la licence sous laquelle les contributions sont placees.
6. Garder le fichier a jour. Si les conventions changent, le mettre a jour.
7. Etre accueillant. La premiere phrase donne le ton.
