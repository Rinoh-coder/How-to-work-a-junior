```markdown
# Guide Markdown

## Qu'est-ce que Markdown

Markdown est un langage de balisage leger cree par John Gruber en 2004. Il permet d'ecrire du texte structure en utilisant une syntaxe simple et lisible, qui peut ensuite etre convertie en HTML.

L'objectif de Markdown est de permettre d'ecrire du contenu structure sans se preoccupier de la mise en forme complexe. Le texte brut reste parfaitement lisible, meme sans conversion.

Markdown est utilise partout dans le developpement logiciel :
- Fichiers README sur GitHub, GitLab, Bitbucket.
- Documentation de projets.
- Issues et Pull Requests.
- Forums et plateformes de discussion (Reddit, Discord).
- Blogs statiques (Jekyll, Hugo, Next.js).

---

## Pourquoi apprendre Markdown

- C'est le standard de documentation dans le developpement.
- C'est simple : la syntaxe de base s'apprend en dix minutes.
- C'est lisible meme sans conversion.
- C'est le format attendu pour tout depot GitHub.
- C'est un prerequis pour documenter correctement ses projets.

---

## Syntaxe de base

### Titres

Les titres sont crees avec le symbole diese `#`. Le nombre de dieses definit le niveau du titre.

```markdown
# Titre de niveau 1
## Titre de niveau 2
### Titre de niveau 3
#### Titre de niveau 4
##### Titre de niveau 5
###### Titre de niveau 6
```

Il est recommande de laisser un espace entre le `#` et le texte du titre.

### Paragraphes

Un paragraphe est une ligne de texte suivie d'une ligne vide.

```markdown
Ceci est un premier paragraphe.

Ceci est un second paragraphe.
```

Pour faire un saut de ligne simple sans nouveau paragraphe, terminer la ligne par deux espaces.

### Mise en forme du texte

```markdown
*italique* ou _italique_
**gras** ou __gras__
***gras italique*** ou ___gras italique___
~~barré~~
`code en ligne`
```

Rendu :

*italique* ou _italique_
**gras** ou __gras__
***gras italique*** ou ___gras italique___
~~barre~~
`code en ligne`

### Listes non ordonnees

Utiliser `-`, `*` ou `+` suivis d'un espace.

```markdown
- Element 1
- Element 2
  - Sous-element 2.1
  - Sous-element 2.2
- Element 3
```

### Listes ordonnees

Utiliser des chiffres suivis d'un point et d'un espace.

```markdown
1. Premiere etape
2. Deuxieme etape
3. Troisieme etape
   1. Sous-etape 3.1
   2. Sous-etape 3.2
```

### Liens

```markdown
[texte du lien](https://url.com)
```

Exemple :

```markdown
[GitHub](https://github.com)
```

Rendu : [GitHub](https://github.com)

### Liens avec titre (tooltip)

```markdown
[texte du lien](https://url.com "Titre au survol")
```

### Liens de reference

Pratique pour les documents longs avec des liens repetes.

```markdown
[GitHub][1] est une plateforme d'hebergement de code.

[1]: https://github.com
```

### Images

```markdown
![texte alternatif](chemin/vers/image.png)
```

Exemple :

```markdown
![Logo du projet](assets/logo.png)
```

Le texte alternatif s'affiche si l'image ne peut pas etre chargee. Il est aussi utilise par les lecteurs d'ecran pour l'accessibilite.

### Images avec lien

```markdown
[![texte alternatif](chemin/image.png)](https://url.com)
```

---

## Syntaxe avancee

### Citations

Utiliser le symbole `>`.

```markdown
> Ceci est une citation.
```

Citations imbriquees :

```markdown
> Citation de niveau 1.
>> Citation de niveau 2.
>>> Citation de niveau 3.
```

Citations sur plusieurs lignes :

```markdown
> Premiere ligne de la citation.
> Deuxieme ligne de la citation.
>
> Nouveau paragraphe dans la meme citation.
```

### Blocs de code

Utiliser trois accents graves ````` ``` ```` pour ouvrir et fermer un bloc de code. Specifier le langage pour la coloration syntaxique.

````markdown
```javascript
function hello() {
  console.log("Bonjour le monde");
}
```
````

Sans indication de langage :

````markdown
```
Texte en police monospace.
```
````

### Code en ligne

Utiliser un accent grave simple ``` ` ``` pour le code dans une phrase.

```markdown
Utiliser la fonction `console.log()` pour afficher un message.
```

### Lignes horizontales

Trois methodes equivalentes :

```markdown
---

***

___
```

### Tableaux

```markdown
| Colonne 1 | Colonne 2 | Colonne 3 |
|-----------|-----------|-----------|
| Valeur 1  | Valeur 2  | Valeur 3  |
| Valeur 4  | Valeur 5  | Valeur 6  |
```

Les deux-points dans la ligne de separation definissent l'alignement :

```markdown
| Gauche   | Centre   | Droite   |
|:---------|:--------:|---------:|
| aligne   | aligne   | aligne   |
| a gauche | au centre| a droite |
```

### Listes de taches (cases a cocher)

```markdown
- [ ] Tache non terminee
- [x] Tache terminee
- [ ] Autre tache non terminee
```

Rendu :
- [ ] Tache non terminee
- [x] Tache terminee
- [ ] Autre tache non terminee

### Echappement de caracteres

Pour afficher un caractere utilise par la syntaxe Markdown, le preceder d'un antislash `\`.

```markdown
\*ceci n'est pas en italique\*
\# ceci n'est pas un titre
\`ceci n'est pas du code\`
```

### Notes de bas de page

Certaines implementations supportent les notes de bas de page.

```markdown
Voici une phrase avec une note[^1].

[^1]: Contenu de la note de bas de page.
```

---

## Elements specifiques a GitHub Flavored Markdown (GFM)

GitHub utilise une version etendue de Markdown avec des fonctionnalites supplementaires.

### Mentions

```markdown
@utilisateur
```

Rendu : mentionne un utilisateur GitHub, lui envoie une notification.

### References a des issues et pull requests

```markdown
#12
utilisateur/projet#12
```

Rendu : lien cliquable vers l'issue ou la pull request numero 12.

### Emojis

```markdown
:smile: :rocket: :books:
```

Rendu : emojis correspondants (a utiliser avec moderation dans la documentation technique).

### Blocs de code avec diff

```markdown
```diff
- ligne supprimee
+ ligne ajoutee
  ligne inchangee
```
```

### Details repliables

```markdown
<details>
<summary>Titre du bloc repliable</summary>

Contenu cache qui s'affiche au clic.

</details>
```

Utile pour masquer du contenu long ou secondaire (logs, details techniques).

### Liens automatiques

Toute URL ecrite en clair est automatiquement transformee en lien cliquable.

```markdown
https://github.com
```

---

## Bonnes pratiques

### 1. Structurer avec des titres

Toujours commencer un document par un titre de niveau 1, puis utiliser les niveaux suivants pour structurer le contenu de maniere hierarchique.

```markdown
# Titre principal

## Section 1

### Sous-section 1.1

### Sous-section 1.2

## Section 2

### Sous-section 2.1
```

### 2. Laisser des lignes vides

Separer les titres, les paragraphes et les listes par des lignes vides pour ameliorer la lisibilite en texte brut.

### 3. Utiliser des listes pour les enumerations

Toute enumeration gagne a etre presentee sous forme de liste.

Incorrect :
```markdown
Les etapes sont : installer Node.js, cloner le depot, lancer npm install.
```

Correct :
```markdown
Les etapes sont :
- Installer Node.js.
- Cloner le depot.
- Lancer npm install.
```

### 4. Mettre le code en bloc avec le langage

Toujours specifier le langage pour les blocs de code. Cela active la coloration syntaxique sur GitHub.

### 5. Relire en mode rendu

Sur GitHub, utiliser l'onglet "Preview" pour verifier le rendu avant de publier. Dans VS Code, utiliser `Ctrl+Shift+V` pour ouvrir l'apercu.

### 6. Limiter la largeur des lignes

En texte brut, limiter les lignes a 80-100 caracteres. Cela facilite la lecture dans un terminal ou un editeur sans retour a la ligne automatique.

### 7. Utiliser des liens de reference pour les documents longs

Si un lien est utilise plusieurs fois, declarer la reference en bas du document pour eviter les repetitions et faciliter les mises a jour.

---

## Exemple complet

```markdown
# Mon projet

## Description

Ce projet permet de resoudre le probleme de [dispersion des ressources](https://exemple.com).

## Installation

### Prerequis

- [Node.js](https://nodejs.org) version 18 ou superieure.
- [npm](https://npmjs.com) version 9 ou superieure.

### Etapes

1. Cloner le depot :
   ```bash
   git clone https://github.com/utilisateur/projet.git
   ```
2. Installer les dependances :
   ```bash
   cd projet
   npm install
   ```
3. Configurer les variables d'environnement :
   Copier le fichier `.env.example` vers `.env` et remplir les valeurs.

4. Lancer le serveur de developpement :
   ```bash
   npm run dev
   ```

## Utilisation

L'application est accessible a l'adresse `http://localhost:3000`.

### Routes disponibles

| Methode | Endpoint       | Description          |
|---------|----------------|----------------------|
| GET     | `/api/health`  | Verifier l'etat.     |
| POST    | `/api/login`   | Se connecter.        |

## Contribution

Voir [CONTRIBUTING.md](CONTRIBUTING.md).

## Licence

MIT. Voir [LICENSE](LICENSE).
```

---

## Outils utiles

- **VS Code** : apercu integre (`Ctrl+Shift+V`), coloration syntaxique native.
- **Typora** : editeur Markdown wysiwyg.
- **MarkdownLint** : linter pour verifier la syntaxe.
- **Tables Generator** : outil en ligne pour creer des tableaux.

---

## Regles a retenir

1. Un titre de niveau 1 par document.
2. Structurer avec des titres hierarchiques.
3. Separer les elements par des lignes vides.
4. Toujours specifier le langage dans les blocs de code.
5. Utiliser les listes pour les enumerations.
6. Relire en mode rendu avant de publier.
7. La syntaxe de base (titres, listes, liens, code) couvre 90% des besoins.
```