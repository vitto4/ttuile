<h1 align="center">
  <img alt="Typst" src="https://github.com/vitto4/ttuile/blob/main/assets/ttuile-header.png?raw=true">
</h1>

<p align="center">
  <a href="https://typst.app">
    <img alt="typst" src="https://img.shields.io/badge/Typst-%232f90ba.svg?&logo=Typst&logoColor=white"
  /></a>
  <a href="https://github.com/vitto4/ttuile/blob/main/LICENSE">
    <img alt="MIT" src="https://img.shields.io/github/license/vitto4/ttuile"
  /></a>
  <a href="https://github.com/vitto4/ttuile/releases">
    <img alt="GitHub Release" src="https://img.shields.io/github/v/release/vitto4/ttuile"
  /></a>
</p>

<p align="center"><i>Un template <b>Typst</b> pour faciliter la rédaction de compte-rendus de TP à l'<a href="https://fr.wikipedia.org/wiki/Institut_national_des_sciences_appliqu%C3%A9es_de_Lyon">INSA Lyon</a>.</i></p>

<p align="center">
  <a href="https://github.com/vitto4/ttuile/blob/main/template/main.pdf">
    <img alt="Exemple" src="https://github.com/vitto4/ttuile/blob/main/assets/ttuile-banner.png?raw=true">
  </a>
</p>

> [!NOTE]
> 
> See also the english [README.md](https://github.com/vitto4/ttuile/blob/main/README.md).

## 🧭 Sommaire

1. [Utilisation](#-utilisation)
1. [Documentation](#-documentation)
1. [Notes](#-notes)
1. [Contributions](#-contributions)



## 📎 Utilisation

Ce template est disponible sur _Typst Universe_ : [`@preview/ttuile:0.1.1`](https://typst.app/universe/package/ttuile).

Pour l'utiliser de manière complètement locale, il est nécessaire de placer les fichiers `ttuile.typ` et `logo-insa-lyon.png` à la racine du projet, ou de les uploader dans la _Typst web app_ le cas échéant.

Ces fichiers peuvent être obtenus dans la section [releases](https://github.com/vitto4/ttuile/releases).

Voici ce à quoi la structure résultante devrait ressembler :

```
.
├── ttuile.typ
├── logo-insa-lyon.png
└── main.typ
```

`ttuile.typ` peut être appelé avec les arguments suivants.
`?` signifie que l'argument peut être nul si non applicable.

| Argument | Valeur par défaut | Type | Description |
|:--------:|:-----------------:|:----:|:------------|
| `titre` | `none` | `content?` | Titre du TP. |
| `auteurs` | `none` | `array<str> \| content?` | Le ou les auteurs du rapport. |
| `groupe` | `none` | `content?` | Nom ou numéro du groupe/de la classe. Sera affiché juste après les auteurs. |
| `numero-tp` | `none` | `content?` | Numéro du TP. |
| `numero-poste` | `none` | `content?` | Numéro du poste ou banc de TP. |
| `date` | `none` | `datetime \| content?` | Date à laquelle le TP a été réalisé. |
| `sommaire` | `true` | `bool` | Afficher le sommaire ? |
| `logo` | `image("logo-insa-lyon.png")` | `image?` | Logo de l'école à utiliser. |
| `point-legende` | `false` | `bool` | Imposer que les légendes se finissent avec un point. (encore expérimental, c'est un peu du bricolage ^^) |

Un seul argument positionnel est accepté, étant le corps du rapport.

Le template peut ensuite être utilisé selon la syntaxe suivante :

```typ
// Local import
// #import "ttuile.typ": *

// Universe import
#import "@preview/ttuile:0.1.1": *

#show: ttuile.with(
  titre: [« #lorem(8) »],
  auteurs: (
      "Theresa Tungsten",
      "Jean Dupont",
      "Eugene Deklan",
  ),
  groupe: "TD0",
  numero-tp: 0,
  numero-poste: "0",
  date: datetime.today(),
  // sommaire: false,
  // logo: image("path_to/logo.png"),
  // point-legende: true,
)
```

## 📚 Documentation

Le template `ttuile.typ` expose certaines fonctions, dont le détail est donné dans la _documentation_.

<p align="center">
  <a href="https://github.com/vitto4/ttuile/blob/main/DOC.FR.md">
    Afficher la documentation
  </a>
</p>

Un fichier d'exemple est disponible ici : [`template/main.typ`](https://github.com/vitto4/ttuile/blob/main/template/main.typ)

## 🔖 Notes

- Ce template n'est pas officiel, c'est simplement ma propre version et interprétation de ce qui est décrit dans le document « Consignes générales pour la rédaction de rapports scientifiques au format numérique » (distribué sur moodle).
- La licence MIT ne s'applique ni au `logo-insa-lyon.png`, qui provient des [éléments graphiques fournis par l'INSA](https://www.insa-lyon.fr/fr/elements-graphiques), ni à la marque « INSA ».
<!-- - Trivia : Le nom « ttuile » est l'acronyme de « **T**emplate de (CR de) **T**P **U**niforme à l'**I**NSA **L**yon pour les **É**tudiants. (on est d'accord, c'est pas très français, mais ça fait un joli acronyme) -->

## 🧩 Contributions

Les contributions sont bienvenues ! Il y a des parties où j'ai un peu (beaucoup) bidouillé pour obtenir le résultat attendu (`identificateur-*`, espacement des titres, ...), donc si quelqu'un sait comment le faire proprement, je suis preneur :)