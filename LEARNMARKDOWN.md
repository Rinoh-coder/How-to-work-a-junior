# Cours complet de Markdown pour développeur

## Qu'est-ce que Markdown

Markdown est un langage de balisage léger. Tu écris du texte avec des symboles simples, et ce texte est ensuite converti en HTML. Contrairement au HTML où les balises rendent le texte brut illisible, le Markdown reste parfaitement compréhensible sans conversion.

Pour un développeur, Markdown est le format standard pour écrire toute documentation : README, documentation technique, messages de commit, issues, pull requests, wikis, et même des articles de blog via des générateurs statiques.

L'avantage principal : tu écris ta documentation dans le même éditeur que ton code, tu la versionnes avec Git, et elle s'affiche formatée automatiquement sur GitHub, GitLab ou n'importe quelle plateforme de code.

---

## Les titres

Un titre se crée avec un ou plusieurs dièses suivis d'un espace. Le nombre de dièses détermine le niveau du titre, de 1 à 6.

```
# Titre de niveau 1
## Titre de niveau 2
### Titre de niveau 3
```

Une seule règle à retenir : un seul titre de niveau 1 par document. C'est le titre principal. Ensuite, les niveaux 2 structurent les grandes sections, les niveaux 3 les sous-sections. Au-delà de trois niveaux, ton document est probablement trop complexe et mérite d'être découpé.

Exemple concret :

```
# Documentation de l'API

## Authentification

### Inscription
### Connexion
### Mot de passe oublié

## Utilisateurs

### Récupérer son profil
### Modifier son profil
```

---

## Les paragraphes et retours à la ligne

Un paragraphe est une suite de texte suivie d'une ligne vide. Si tu ne mets pas de ligne vide, le texte reste dans le même paragraphe même si tu passes à la ligne dans ton éditeur.

```
Ceci est le premier paragraphe.
Il continue sur cette ligne car il n'y a pas de ligne vide.

Ceci est le deuxième paragraphe car il y a une ligne vide avant.
```

Pour un simple retour à la ligne sans nouveau paragraphe, termine la ligne par deux espaces. Cette syntaxe est peu visible donc beaucoup d'éditeurs et de plateformes acceptent aussi un simple saut de ligne, mais la norme stricte demande les deux espaces.

---

## La mise en forme du texte

Le gras et l'italique se font avec des astérisques ou des tirets bas. La convention universelle pour un développeur est d'utiliser les astérisques, car ils sont plus visibles dans le code.

```
*italique*
**gras**
***gras et italique***
~~texte barré~~
`code en ligne`
```

Exemple concret dans une documentation :

```
La fonction **doit** être appelée avant l'initialisation.
Le paramètre *timeout* est optionnel.
Utilise `console.log()` pour déboguer.
La méthode ~~`oldMethod()`~~ est dépréciée, utilise `newMethod()`.
```

La fonction **doit** être appelée avant l'initialisation.
Le paramètre *timeout* est optionnel.
Utilise `console.log()` pour déboguer.
La méthode ~~`oldMethod()`~~ est dépréciée, utilise `newMethod()`.

Le code en ligne avec un seul accent grave est fondamental pour un développeur : toute mention de variable, fonction, commande ou chemin de fichier doit être en code en ligne.

---

## Les listes

### Liste non ordonnée

Utilise un tiret suivi d'un espace. C'est la convention standard en développement.

```
- Premier élément
- Deuxième élément
- Troisième élément
```

### Liste ordonnée

Utilise un chiffre suivi d'un point et d'un espace. Tu peux écrire `1.` partout, la numérotation sera automatique à la conversion. C'est un énorme avantage : tu peux réorganiser ta liste sans renuméroter.

```
1. Installer les dépendances
1. Configurer l'environnement
1. Lancer le serveur
```

### Listes imbriquées

Ajoute deux espaces devant l'élément pour créer un sous-niveau.

```
- Étape 1
  - Sous-étape 1.1
  - Sous-étape 1.2
- Étape 2
  1. Première action
  1. Deuxième action
```

Exemple concret dans un README :

```
## Installation

- Installer Node.js version 18 ou supérieure
- Cloner le dépôt
- Installer les dépendances
  1. Lancer `npm install`
  1. Vérifier qu'aucune erreur n'apparaît
  1. Lancer `npm run dev`
```

---

## Les liens

Un lien se crée avec le texte entre crochets et l'URL entre parenthèses, sans espace entre les deux.

```
[texte affiché](https://url.com)
```

Exemple :

```
Consulte la [documentation officielle](https://nodejs.org/docs).
```

Pour un lien avec un titre au survol :

```
[texte affiché](https://url.com "Titre qui apparaît au survol")
```

### Liens de référence

Pour les documents longs avec des liens répétés, utilise des références. Cela rend le texte brut plus lisible et facilite la maintenance.

```
Le projet utilise [Node.js][node] et [Express][express] pour le backend.

[node]: https://nodejs.org
[express]: https://expressjs.com
```

Si le même lien est utilisé plusieurs fois dans un long document, tu changes l'URL une seule fois dans la référence, et toutes les occurrences sont mises à jour.

---

## Les images

Une image utilise la même syntaxe qu'un lien, précédée d'un point d'exclamation.

```
![texte alternatif](chemin/vers/image.png)
```

Le texte alternatif est obligatoire. Il s'affiche si l'image ne charge pas et il est utilisé par les lecteurs d'écran pour l'accessibilité.

Exemple concret :

```
![Schéma de l'architecture du projet](docs/architecture.png)
```

Pour une image cliquable qui renvoie vers un lien, combine les deux syntaxes :

```
[![Schéma de l'architecture](docs/architecture.png)](https://mon-site.com)
```

---

## Les blocs de code

C'est la fonctionnalité la plus importante pour un développeur. Un bloc de code se crée avec trois accents graves sur la ligne d'ouverture et trois sur la ligne de fermeture. Juste après les trois accents d'ouverture, tu précises le langage pour activer la coloration syntaxique.

```
```javascript
function hello(name) {
  return `Bonjour ${name}`;
}
```
```

Le nom du langage est toujours en minuscules. GitHub supporte des dizaines de langages.

Exemple concret dans une documentation d'API :

```
Voici un exemple de requête :

```bash
curl -X POST https://api.example.com/login \
  -H "Content-Type: application/json" \
  -d '{"email": "user@example.com", "password": "secret"}'
```

La réponse attendue :

```json
{
  "token": "eyJhbGciOiJIUzI1NiIs...",
  "user": {
    "id": "abc123",
    "email": "user@example.com"
  }
}
```
```

Ne jamais omettre le langage. Sans lui, pas de coloration syntaxique, et le bloc de code est bien moins lisible.

---

## Les citations

Une citation se crée avec le symbole supérieur à en début de ligne.

```
> Ceci est une citation.
```

Pour une citation sur plusieurs paragraphes, mets le symbole sur chaque ligne, y compris les lignes vides.

```
> Premier paragraphe de la citation.
>
> Deuxième paragraphe de la même citation.
```

Exemple concret :

```
> La documentation est une lettre d'amour que l'on écrit à son futur soi-même.
>
> -- Damian Conway
```

---

## Les tableaux

Un tableau se crée avec des barres verticales pour les colonnes et des tirets pour la ligne de séparation entre l'en-tête et le corps.

```
| Nom | Version | Statut |
|-----|---------|--------|
| Node.js | 20.x | Actif |
| Express | 4.18 | Actif |
```

Les deux-points sur la ligne de séparation définissent l'alignement :

```
| Gauche   | Centre   | Droite   |
|:---------|:--------:|---------:|
| texte    | texte    | texte    |
```

Exemple concret pour une documentation d'API :

```
| Méthode | Endpoint | Authentification |
|---------|----------|-----------------|
| GET | /api/users | Token requis |
| POST | /api/auth/login | Aucune |
| DELETE | /api/users/:id | Admin requis |
```

Pour des tableaux complexes avec des cellules fusionnées ou des mises en forme avancées, utilise du HTML directement. Markdown le permet.

---

## Les listes de tâches

Propores à GitHub, les listes de tâches créent des cases à cocher. Un espace dans les crochets pour une case vide, un `x` pour une case cochée.

```
- [ ] Tâche à faire
- [x] Tâche terminée
- [ ] Autre tâche à faire
```

Exemple concret dans un fichier de suivi :

```
## Fonctionnalités à implémenter

- [x] Authentification par email
- [x] Inscription utilisateur
- [ ] Récupération de mot de passe
- [ ] Authentification par Google
- [ ] Interface d'administration
```

---

## Les lignes horizontales

Trois tirets seuls sur une ligne. Laisse une ligne vide avant et après.

```
---

```

---

## Le HTML intégré

Quand Markdown ne permet pas de faire quelque chose, tu peux écrire du HTML directement. C'est particulièrement utile pour les tableaux complexes, les iframes, ou les blocs repliables.

Exemple de bloc repliable avec GitHub Flavored Markdown :

```
<details>
<summary>Cliquer pour voir les logs</summary>

```
Erreur: connexion refusée
  at Server.js:42
  at Object.connect
```

</details>
```

---

## L'échappement des caractères

Si tu veux afficher un caractère qui a une signification en Markdown sans qu'il soit interprété, précède-le d'un antislash.

```
\*ceci n'est pas de l'italique\*
\# ceci n'est pas un titre
```

---

## Structure type d'un fichier README

Voici un exemple complet qui illustre l'utilisation combinée de toutes les syntaxes dans un contexte réel :

```
# Mon API de Gestion de Tâches

API RESTful pour gérer des listes de tâches collaboratives.

## Installation

### Prérequis

- [Node.js](https://nodejs.org) version **18** ou supérieure
- [PostgreSQL](https://postgresql.org) version **15** ou supérieure

### Étapes

1. Cloner le dépôt
   ```bash
   git clone https://github.com/utilisateur/task-api.git
   cd task-api
   ```
1. Installer les dépendances
   ```bash
   npm install
   ```
1. Configurer l'environnement
   ```bash
   cp .env.example .env
   # Modifier .env avec vos valeurs
   ```
1. Lancer le serveur
   ```bash
   npm run dev
   ```

## Utilisation

### Créer une tâche

```bash
curl -X POST http://localhost:3000/api/tasks \
  -H "Content-Type: application/json" \
  -d '{"title": "Apprendre Markdown", "priority": "haute"}'
```

Réponse :

```json
{
  "id": "task_42",
  "title": "Apprendre Markdown",
  "priority": "haute",
  "status": "à faire",
  "createdAt": "2024-01-15T10:30:00Z"
}
```

### Codes d'erreur

| Code | Signification |
|------|---------------|
| 400 | Requête invalide |
| 401 | Non authentifié |
| 404 | Ressource non trouvée |

## Documentation

- [Référence complète de l'API](docs/api.md)
- [Guide de contribution](CONTRIBUTING.md)

## Licence

MIT. Voir [LICENSE](LICENSE).
```

---

## Les conventions pour un développeur

Utilise toujours le tiret pour les listes non ordonnées, jamais l'astérisque. Le tiret est sans ambiguïté.

Spécifie toujours le langage après les trois accents graves d'ouverture. Un bloc de code sans langage perd la moitié de son utilité.

Écris tout nom technique en code en ligne : fonction `getUser`, fichier `.env`, commande `npm install`. C'est une règle non négociable en documentation technique.

Structure toujours avec des titres. Un document sans titre est un mur de texte.

Relis toujours le rendu avant de publier. Dans VS Code, Ctrl Shift V ouvre l'aperçu. Sur GitHub, utilise l'onglet Preview.

Limite la largeur des lignes à environ 80 caractères dans ton éditeur. Cela rend le texte brut lisible dans un terminal, dans un diff Git, ou dans un éditeur sans retour à la ligne.

---

## Ce qu'il faut retenir

La syntaxe de base couvre 90% des besoins : titres, paragraphes, listes, liens, images, code. Tu peux l'apprendre en dix minutes et la maîtriser en une semaine d'utilisation quotidienne.

Le bloc de code avec langage et le code en ligne sont les deux syntaxes les plus importantes pour un développeur. Ce sont elles qui font la différence entre une documentation amateur et une documentation professionnelle.

Markdown est un outil d'écriture, pas de mise en page. Si tu passes plus de temps à formater qu'à écrire, tu utilises Markdown de travers. Le contenu prime sur la forme.