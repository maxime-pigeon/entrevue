# Cours du 25 janvier 2023

Cégep de Maisonneuve<br>
_Maxime Pigeon_

---

<!-- .slide: data-auto-animate -->

# Aperçu du cours

1. Les **conditions** : prendre des décisions dans le code
2. Les **boucles** dans le code
3. Les **fonctions** : des blocs de code réutilisables
4. Introduction aux **évènements**
5. **Devoir** : galerie d'images

--

<!-- .slide: data-auto-animate -->

# Aperçu du cours

**Les fonctions**

1.  Qu'est-ce qu'une fonction ? <!-- .element: class="fragment" -->
1.  À quoi servent les fonctions ? <!-- .element: class="fragment" -->
1.  Définir une fonction <!-- .element: class="fragment" -->
1.  Invoquer une fonction <!-- .element: class="fragment" -->
1.  Portée d'une function <!-- .element: class="fragment" -->

---

# 1. Qu'est-ce qu'une fonction ?

Une fonction est un « sous-programme » qui peut être **invoqué** et qui contient une **suite d'instructions**. Il est généralement possible de passer des **arguments** à une fonction, et une fonction retourne généralement une valeur.

```js []
function carre(nombre) {
  return nombre * nombre;
}
```

--

Vous avez déjà utilisé des _fonctions intégrées_ dans ce cours. Comme par exemple pour afficher un message dans la console Web :

```js []
const message = "Bonjour monde";

console.log(message);
```

--

<!-- .slide: data-auto-animate -->

Autre exemple de _fonction intégrée_.<br>

```js []
const myNumber = Math.random();
```

--

<!-- .slide: data-auto-animate -->

#### Récapitulation

Quel pourrait être le résultat de la _constante_ `myNumber` ?

```js []
const myNumber = Math.random();
```

La fonction `Math.random()` renvoie un nombre flottant aléatoire compris dans l'intervalle `[0, 1[` (ce qui signifie que 0 est compris dans l'intervalle mais que 1 en est exclu).

<!-- .element class="fragment" -->

Notes:
Presque à chaque fois que vous utilisez une structure de JavaScript qui utilise une paire de parenthèses — () — et qui n'est pas une boucle `for`, `while`, ou une déclaration `if`...`else`, vous utilisez une fonction.

Le langage JavaScript a de nombreuses fonctions intégrées qui sont prédéfinies pour vous permettre de faire des choses utiles sans devoir écrire tout le code vous-même.

---

# 2. À quoi servent les fonctions ?

Les fonctions permettent de **simplifier** un programme en le divisant en un ensemble de sous-étapes. En **abstrayant** un programme complexe en plusieurs fonctions, il devient plus simple de le lire le code, de l'utiliser, et de l'entretenir.

Notes:

Un peu comme cette présentation. Les fonctions permettent de structurer un programme.

--

Les fonctions permettent de **réutiliser le code** au lieu de le réécrire. Elles permettent de **stocker dans un bloc** une partie de code qui effectue une tâche. De cette façon, au lieu de ré-écrire l'intégralité de ce code à chaque fois que nous avons besoin d'effectuer cette tâche, nous avons qu'à invoquer la fonction.

--

#### Questions ?

---

<!-- .slide: data-auto-animate -->

# 3. Définir une fonction

Une fonction Javascript est construite avec le mot-clé `function`, suivi de :

1. Le **nom** de la fonction.
2. Une liste de **paramètres** à passer à la fonction, entre parenthèses et séparés par des virgules.
3. Les **instructions** définissant la fonction, entre accolades, `{ }`.

```js []
function nom(param1, param2, param3, etc) {
  //   Instructions
}
```

--

<!-- .slide: data-auto-animate -->

```js []
function nom(param1, param2, param3, etc) {
  //   Instructions
}
```

#### À propos des paramètres

Certaines fonctions nécessitent que l'on définisse des _paramètres_ lorsqu'on les appelle. Ce sont des valeurs qui doivent êtres inclues dans les parenthèses de la fonction pour que celle-ci fonctionne correctement.

--

<!-- .slide: data-auto-animate -->

#### À propos des paramètres

Certaines fonctions nécessitent que l'on définisse des _paramètres_ lorsqu'on les appelle. Ce sont des valeurs qui doivent êtres inclues dans les parenthèses de la fonction pour que celle-ci fonctionne correctement.

```js []
function addition(a, b) {
  return a + b;
}
```

Par exemple, la fonction `addition()` ci-haut prend 2 paramètres.

--

#### Note

Les _paramètres_ sont parfois appelés _arguments_, _propriétés_ ou encore _attributs_.

Notes:

Ces termes se réfèrent à des choses subtilement différentes, mais pour l'instant sachez seulement que ces mots sont parfois utilisés.

---

<!-- .slide: data-auto-animate -->

#### Récapitulation

```js []
function carre(nombre) {
  return nombre * nombre;
}
```

Quel est le nom de la fonction ci-haut ?

**carre** <!-- .element: class="fragment" -->

--

<!-- .slide: data-auto-animate -->

#### Récapitulation

```js []
function carre(nombre) {
  return nombre * nombre;
}
```

Combien de paramètres a-t-elle ?

**1** <!-- .element: class="fragment" -->

--

<!-- .slide: data-auto-animate -->

#### Récapitulation

```js []
function carre(nombre) {
  return nombre * nombre;
}
```

Quels sont ses instructions ?

`return nombre * nombre` <!-- .element: class="fragment" -->

--

Questions ?

---

# 4. Invoquer une fonction

Invoquer la fonction permet d'effectuer les actions des instructions avec les paramètres indiqués. Par exemple, si on définit la fonction `myFunction`, on peut l'appeler de la façon suivante :

```js [5,6]
function myFunction() {
  alert("hello");
}

myFunction();
// appelle la fonction une fois
```

Notes:

Vous êtes probablement au clair avec cela maintenant, mais juste au cas où… pour utiliser une fonction après qu'elle a été définie, vous devez la lancer — ou l'invoquer. Pour ce faire, vous devez inclure le nom de la fonction quelque part dans le code suivi par des parenthèses :

Bien sûr, définir une fonction ne permet pas d'exécuter la fonction. Cela permet de lui donner un nom et de définir ce qui doit être fait lorsque la fonction est appelée.

Maintenant que nous avons vu comment définir une fonction, voyons comment l'appeler.

---

# 5. Portée d'une fonction

On ne peut pas accéder aux variables définies dans une fonction en dehors de cette fonction : ces variables n'existent que dans la portée de la fonction. En revanche, une fonction peut accéder aux différentes variables et fonctions qui appartiennent à la portée dans laquelle elle est définie. Une fonction définie dans une autre fonction peut également accéder à toutes les variables de la fonction « parente » et à toute autre variable accessible depuis la fonction « parente ».

Notes:

<!-- Functions allow us to keep our variable namespace clean (local variables only "live" as long as the function does). In other words, function_1 can use a variable called i, and function_2 can also use a variable called i and there is no confusion. Each variable i only exists when the computer is executing the given function. -->

---
