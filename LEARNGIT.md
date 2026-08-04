# Guide pratique de Git et GitHub

## Qu'est-ce que Git

Git est un système de contrôle de version. Il enregistre chaque modification de ton code comme une photographie instantanée. À tout moment, tu peux revenir à une version antérieure, comparer des changements, ou comprendre qui a modifié quoi et pourquoi.

Git fonctionne en local sur ta machine. Tu n'as pas besoin d'Internet pour l'utiliser. Tout l'historique est stocké dans un dossier caché `.git` à la racine de ton projet.

## Qu'est-ce que GitHub

GitHub est une plateforme en ligne qui héberge des dépôts Git. Elle ajoute une interface web, des outils de collaboration, et sert de sauvegarde distante de ton code.

Git et GitHub sont deux choses distinctes. Git est le logiciel, GitHub est le service. Tu peux utiliser Git sans GitHub, mais GitHub est devenu le standard pour partager et collaborer.

---

## Installation et configuration initiale

### Installer Git

Sur Windows, télécharge l'installateur depuis git-scm.com. Sur Mac, Git est préinstallé ou s'installe via les commandes Xcode. Sur Linux, utilise le gestionnaire de paquets de ta distribution.

Pour vérifier l'installation :

```bash
git --version
```

### Configurer ton identité

Cette configuration est à faire une seule fois par machine. Elle associe ton nom et ton email à chaque commit que tu feras.

```bash
git config --global user.name "Ton Nom Complet"
git config --global user.email "ton-email@exemple.com"
```

L'email doit correspondre à celui de ton compte GitHub si tu veux que tes commits soient liés à ton profil.

### Configurer la branche par défaut

Par convention moderne, la branche principale s'appelle `main`.

```bash
git config --global init.defaultBranch main
```

---

## Créer un dépôt local

Quand tu commences un nouveau projet depuis ta machine.

```bash
mkdir mon-projet
cd mon-projet
git init
```

La commande `git init` crée le dossier `.git`. Ton dossier est maintenant un dépôt Git, mais il ne contient encore aucun commit.

Pour vérifier l'état :

```bash
git status
```

Cette commande est la plus utilisée. Elle te dit où tu en es : quels fichiers sont modifiés, lesquels sont prêts à être commités, et sur quelle branche tu travailles.

---

## Le cycle de travail local

Le travail avec Git suit un cycle en trois étapes.

### Étape 1 : Modifier des fichiers

Tu écris du code dans ton éditeur. Git détecte automatiquement les fichiers modifiés, ajoutés ou supprimés.

```bash
git status
```

Affiche les fichiers en rouge : ce sont les fichiers modifiés mais pas encore indexés.

### Étape 2 : Indexer les modifications

L'index est une zone de préparation. Tu choisis précisément ce que tu veux inclure dans le prochain commit.

Pour ajouter un fichier spécifique :

```bash
git add nom-du-fichier.js
```

Pour ajouter tous les fichiers modifiés du dossier courant :

```bash
git add .
```

Pour ajouter de manière interactive, morceau par morceau :

```bash
git add -p
```

Cette dernière commande est puissante. Elle te présente chaque modification et te demande si tu veux l'indexer. Cela permet de faire des commits très précis.

Après un `git add`, refais `git status`. Les fichiers apparaissent maintenant en vert : ils sont indexés, prêts à être commités.

### Étape 3 : Créer un commit

Un commit est une photographie de l'état de ton projet à un instant donné. Chaque commit a un message qui explique ce qui a changé.

```bash
git commit -m "feat(auth): ajouter le formulaire de connexion"
```

Le message suit une convention : un type entre parenthèses, un scope, et une description à l'impératif présent.

Un commit est un point de restauration. Si plus tard tu casses quelque chose, tu peux revenir exactement à ce commit.

---

## Les conventions de messages de commit

Un message de commit suit ce format :

```
type(scope): description
```

Les types sont :
- `feat` : nouvelle fonctionnalité
- `fix` : correction de bug
- `docs` : documentation
- `style` : formatage sans changement fonctionnel
- `refactor` : restructuration du code
- `test` : ajout ou modification de tests
- `chore` : maintenance, dépendances

Le scope est la partie du projet concernée : `auth`, `api`, `ui`, `db`, `config`.

La description répond à la question "Que fait ce commit ?". Elle est à l'impératif présent, en minuscules, sans point final.

Exemples corrects :

```
feat(auth): ajouter la connexion par email
fix(api): corriger le statut HTTP sur erreur de validation
docs(readme): documenter les variables d'environnement
```

Exemples incorrects :

```
Ajout du formulaire        (pas de type, pas à l'impératif)
fix                        (pas de description)
feat: connexion            (pas de scope)
```

---

## Lier un dépôt local à GitHub

Si tu as créé un dépôt local d'abord et que tu veux le pousser sur GitHub.

### Étape 1 : Créer un dépôt vide sur GitHub

Va sur GitHub, clique sur "New repository". Donne un nom, ne coche rien (pas de README, pas de .gitignore, pas de licence). Clique sur "Create repository".

GitHub affiche alors l'URL de ton dépôt : `https://github.com/ton-compte/mon-projet.git`.

### Étape 2 : Lier le remote

Dans ton terminal, ajoute le dépôt distant comme remote nommé `origin` :

```bash
git remote add origin https://github.com/ton-compte/mon-projet.git
```

Vérifie que le remote est bien configuré :

```bash
git remote -v
```

### Étape 3 : Pousser le code

```bash
git push -u origin main
```

L'option `-u` crée un lien entre ta branche locale `main` et la branche distante `origin/main`. Après cela, un simple `git push` suffira.

---

## Cloner un dépôt existant

Quand le dépôt existe déjà sur GitHub et que tu veux le récupérer sur ta machine.

```bash
git clone https://github.com/ton-compte/mon-projet.git
```

Cette commande fait tout automatiquement : elle télécharge le code, l'historique complet, et configure le remote `origin`. Entre dans le dossier créé et commence à travailler.

```bash
cd mon-projet
```

---

## Les branches

Une branche est une ligne de développement indépendante. Elle te permet de travailler sur une fonctionnalité sans toucher au code stable.

### Pourquoi utiliser des branches même en solo

Sans branches, tout ton code est sur une seule ligne. Si tu commences une fonctionnalité et qu'un bug urgent apparaît, tu es coincé.

Avec des branches, chaque fonctionnalité est isolée. Tu peux passer de l'une à l'autre sans mélanger le code. Et l'historique est beaucoup plus lisible.

### Les branches principales

Deux branches existent en permanence :
- `main` : le code stable, prêt à être déployé. On ne code jamais directement dessus.
- `develop` : la branche d'intégration. Tout le travail en cours atterrit ici.

### Créer une branche

Avant de créer une branche, assure-toi d'être sur `develop` et d'avoir la dernière version :

```bash
git checkout develop
git pull origin develop
```

Crée la branche et bascule dessus :

```bash
git checkout -b feature/authentification
```

Le nom suit la convention `type/nom-descriptif`. Les types sont `feature`, `fix`, `chore`, `docs`, `refactor`.

### Travailler sur une branche

Tu fais tes modifications, tes commits, exactement comme sur `main`. Mais tout reste isolé sur cette branche.

```bash
git add -p
git commit -m "feat(auth): ajouter le modèle utilisateur"
```

### Pousser la branche sur GitHub

```bash
git push -u origin feature/authentification
```

Pousse régulièrement, même si la fonctionnalité n'est pas terminée. Cela sauvegarde ton travail et te permet d'y accéder depuis une autre machine.

### Fusionner la branche

Quand la fonctionnalité est terminée et testée, fusionne-la dans `develop`.

```bash
git checkout develop
git pull origin develop
git merge --no-ff feature/authentification
```

L'option `--no-ff` crée un commit de fusion visible dans l'historique. Cela laisse une trace explicite qui dit "la fonctionnalité X a été intégrée".

### Supprimer la branche

Après la fusion, nettoie.

```bash
git branch -d feature/authentification
git push origin --delete feature/authentification
```

Une branche fusionnée doit être supprimée. Elle a rempli son rôle.

---

## Récupérer les mises à jour du distant

Si tu travailles sur plusieurs machines ou si quelqu'un d'autre a poussé du code, récupère les changements.

```bash
git pull origin develop
```

Cette commande fait deux choses : elle télécharge les nouveaux commits du distant (`fetch`) et elle les fusionne dans ta branche locale (`merge`).

Fais toujours un `git pull` en début de session de travail pour partir de la version la plus récente.

---

## Annuler des modifications

### Annuler des modifications locales non commitées

Tu as modifié un fichier et tu veux revenir à la dernière version commitée.

```bash
git checkout -- nom-du-fichier.js
```

Cette commande est irréversible. Les modifications non commitées sont définitivement perdues.

### Annuler un fichier déjà indexé

Tu as fait `git add` mais tu n'as pas encore commité. Tu veux retirer le fichier de l'index.

```bash
git reset HEAD nom-du-fichier.js
```

Le fichier redevient non indexé, mais les modifications sont conservées.

### Annuler le dernier commit

Si le commit n'a pas encore été poussé sur le distant :

```bash
git reset --soft HEAD~1
```

Cela annule le commit mais garde les modifications dans ton répertoire de travail. Tu peux les modifier et refaire un commit propre.

Si le commit a déjà été poussé, ne l'annule pas. Fais plutôt un nouveau commit qui corrige le précédent.

---

## Consulter l'historique

Voir la liste des commits :

```bash
git log --oneline
```

Affiche un résumé : chaque commit sur une ligne avec son hash raccourci et son message.

Voir l'historique avec le graphe des branches :

```bash
git log --oneline --graph --all
```

Cette vue est essentielle pour comprendre la structure du projet.

Voir ce qu'un commit a modifié :

```bash
git show abc123
```

Voir qui a modifié quoi dans un fichier :

```bash
git blame nom-du-fichier.js
```

---

## Les tags

Un tag est une étiquette posée sur un commit pour marquer une version.

Créer un tag annoté :

```bash
git tag -a v1.0.0 -m "MVP : authentification et catalogue"
```

Pousser le tag :

```bash
git push origin v1.0.0
```

Les tags servent à retrouver facilement l'état du code au moment d'une livraison. Utilise le versionnement sémantique : `MAJEUR.MINEUR.CORRECTIF`.

---

## Ignorer des fichiers

Le fichier `.gitignore` liste les fichiers et dossiers que Git doit ignorer. Place-le à la racine du projet.

Exemple pour un projet Node.js :

```
node_modules/
.env
dist/
build/
*.log
```

Ne rédige jamais un `.gitignore` à la main. Utilise gitignore.io, sélectionne ton langage, et copie le résultat.

---

## Résoudre un conflit

Un conflit survient quand deux branches ont modifié la même partie d'un même fichier. Git ne peut pas décider quelle version garder.

Git marque le conflit dans le fichier :

```
<<<<<<< HEAD
const email = document.querySelector('#email');
=======
const emailInput = document.getElementById('email');
>>>>>>> feature/ma-branche
```

La section entre `<<<<<<< HEAD` et `=======` est le code de la branche courante. La section entre `=======` et `>>>>>>>` est le code de la branche fusionnée.

Pour résoudre :
1. Ouvre le fichier.
2. Choisis quelle version garder, ou combine les deux.
3. Supprime les marqueurs `<<<<<<<`, `=======`, `>>>>>>>`.
4. Fais `git add` du fichier résolu.
5. Fais `git commit` pour terminer la fusion.

Pour annuler une fusion conflictuelle :

```bash
git merge --abort
```

---

## Le workflow quotidien résumé

```bash
# Début de session : se placer sur develop et mettre à jour
git checkout develop
git pull origin develop

# Créer une branche pour la fonctionnalité du jour
git checkout -b feature/ma-tache

# Travailler : cycle modification, indexation, commit
git add -p
git commit -m "feat(scope): description"

# Pousser la branche en fin de session
git push -u origin feature/ma-tache

# Quand la fonctionnalité est terminée : fusionner dans develop
git checkout develop
git pull origin develop
git merge --no-ff feature/ma-tache
git push origin develop

# Nettoyer
git branch -d feature/ma-tache
git push origin --delete feature/ma-tache
```

---

## Les commandes essentielles en résumé

| Commande | Action |
|----------|--------|
| `git status` | Voir l'état du dépôt |
| `git add -p` | Indexer les modifications de manière sélective |
| `git commit -m "message"` | Créer un commit |
| `git push origin main` | Pousser sur le distant |
| `git pull origin main` | Récupérer les mises à jour |
| `git checkout -b branche` | Créer et basculer sur une branche |
| `git merge --no-ff branche` | Fusionner une branche |
| `git log --oneline` | Voir l'historique |
| `git diff` | Voir les modifications non indexées |
| `git reset HEAD fichier` | Désindexer un fichier |
| `git checkout -- fichier` | Annuler les modifications d'un fichier |
| `git tag -a v1.0.0 -m "message"` | Créer un tag de version |

---

## Règles absolues

Ne code jamais directement sur `main`. C'est la branche de livraison.

Fais un commit par action logique. Si ton message contient "et", fais deux commits.

Pousse ton code chaque jour. Le code non poussé est du code qui n'existe pas.

Écris des messages de commit qui seront compréhensibles dans six mois.

Supprime les branches après les avoir fusionnées. Un dépôt propre est un dépôt où l'on se repère.

Ne modifie jamais un commit déjà poussé. Si tu as fait une erreur, fais un nouveau commit correctif.

Vérifie toujours avec `git status` avant et après chaque commande importante.