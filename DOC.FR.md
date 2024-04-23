# 📚 Documentation

### `ttuile`

C'est la fonction principale, le point d'entrée du template. Elle doit être appelée en début de document, comme décrit dans [README.FR.md > Utilisation](https://github.com/vitto4/ttuile/blob/main/README.FR.md#-utilisation).

Si le compte rendu n'est pas réalisé pour l'INSA Lyon, le logo peut être remplacé ou supprimé avec l'argument `chemin-logo`.

### `annexe`

Fonction utilisée pour définir un objet `annexe`. Cet objet - étant un `dictionary` - sera ensuite utilisé par la fonction `afficher-annexes`.

| Argument | Valeur par défaut | Type | Description |
|:--------:|:-----------------:|:----:|:------------|
| `titre` | - | `content` | Titre de l'annexe. |
| `reference` | `none` | `label` | Label/référence à utiliser dans le corps du rapport pour se référer à l'annexe. |

Un seul argument positionnel est accepté, étant le corps de l'annexe.

**Exemple :**

```typ
#let Annexe-1 = annexe(
  titre: [Titre de l'annexe],
  reference: <référence-à-utiliser>,
)[
  Corps de l'annexe, du texte, des images, des titres, ...
]
```

La `reference` peut ensuite s'utiliser normalement dans le reste du rapport : `@référence-à-utiliser`.

**Remarque :**
- Comme les titres des annexes sont en réalité des titres de niveau `1` stylisés pour l'occasion, il n'est actuellement possible d'utiliser que des titres de niveau `2` ou plus dans le corps des annexes.

### `afficher-annexes`

Cette fonction prend en argument une liste d'objets `annexe` définis à l'aide de la fonction `annexe`, et les affiche avec une mise en page appropriée.

| Argument | Valeur par défaut | Type | Description |
|:--------:|:-----------------:|:----:|:------------|
| `annexes` | `none` | `list<dictionary>` | Liste de dictionnaires générés avec la fonction `annexe`. |
| `table` | `true` | `bool` | Permet d'afficher ou de masquer la table des annexes. |
| `saut-page-apres-table` | `false` | `bool` | Force un saut de page immédiatement après l'éventuelle table des annexes. |

**Exemple :**

```typ
#afficher-annexes(
  annexes: (Annexe-1, Annexe-2,),
  table: true,
  saut-page-apres-table: false,
)
```

### `equation-anonyme`

Simple raccourci pour afficher une équation sans la numéroter.

**Exemple :**

```typ
#equation-anonyme(
  $
  "Une équation"
  $
)
```

### `figure-emboitee`

Fait en sorte que la légende de la figure n'en dépasse pas la largeur.

```typ
figure-emboitee(
  figure(
    image("img.png"),
    caption: [Une figure.]
  )
  reference: <référence-à-utiliser>,
)
```