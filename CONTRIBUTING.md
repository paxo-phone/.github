# Conventions de nommage C++

Ce document décrit les différentes conventions de nommages utilisées en c++ dans le développement du du projet Paxo. Toute contribution souhaitant être incorporé au présent code devra respecter ces conventions mise en place pour :
- Éviter les conflits de noms
- Favoriser la cohérence du code
- Améliorer la lisibilité du code
- Simplifier la maintenance du code

De manière générale, préférer l'explicite à l'efficace. La lisibilité doit être priorisée.
Les abréviations sont, de fait, à éviter absolument.

Éviter les instructions dépassant les limites de l'écran. Préférer dans ce cas un retour à la ligne.

Les noms relatifs aux éléments de code doivent être écrits en langue anglaise.

- [Variables](#variables)
- [Énumérations](#énumérations)
- [Classes \& Structures](#classes--structures)
- [Fonctions](#fonctions)
- [Préprocesseur](#préprocesseur)
- [Constantes](#constantes)
- [Blocs](#blocs)
- [Commentaires](#commentaires)
- [Fichiers](#fichiers)
- [Espaces de noms (namespace)](#espaces-de-noms-namespace)


## Variables

Dans le nom d'une variable, chaque mot doit débuter par une majuscule, excepté le premier, les majuscule jouant le rôle de séparateurs (ex. `contactsCount`, `currentScene` etc.)

Les underscore ('_') sont à proscrire.

Le type des variables doit être le plus explicite possible et adapté à la donnée stockée.

Le mot clé `auto` est à proscrire.

L'instruction `using` doit être utilisée à la place de `typedef`.

Les nom triviaux `i, j, k` doivent être limités à de rares cas où leur rôle est parfaitement explicite (ex. boucles). 

## Énumérations

Le nom d'une énumération doit être un nom commun.

Chaque mot doit débuter par une majuscule, y compris le premier, les majuscules jouant le rôle de séparateurs (ex. `TokenType`, `Color`, etc.).

Les underscores ('_') doivent être proscrits.

Les membres de l'énumération doivent être écrits en majuscule et utiliser l'underscore ('_') comme séparateur.

## Classes & Structures

Le nom d'une classe doit être un nom commun.

Chaque mot doit débuter par une majuscule, y compris le premier, les majuscules jouant le rôle de séparateurs (ex. `Book`, `TimeManager`, `EventHandler`, etc.)

Les underscores ('_') doivent être proscrits.

Les attributs doivent être systématiquements privés pour garantir une encapsulation totale.

Les attributs doivent débuter par `m_` et suivre les conventions de nommage des variables énoncées précédemment (ex. `m_width`, `m_backgroundColor`, etc.)

Les mots clés `private` et `public` doivent être précédés d'une tabulation. Les attributs et méthodes de la classe doivent être précédés de deux tabulations.

```c++
class Object
{
    public:
        ...
    private:
        ...
};
```
 
Les méthodes pour accéder aux attributs (les *getters*) doivent débuter par `get` suivit du nom de l'attribut débutant par une majuscule (ex. `getWidth`, `getBackgroundColor`, etc.)

les méthodes pour modifier les attributs (les *setters*) doivent débuter par `set` suivit du nom de l'attribut débutant par une majuscule (ex. `setWidth`, `setBackgroundColor`, etc.)

L'accès aux attributs de l'objet doit systématiquement se faire à travers l'objet `this`.

## Fonctions

Les noms des fonctions doivent systématiquement débuter par un verbe.

Chaque mot doit débuter par une lettre majuscule, excepté le premier, les majuscules jouant le rôle de séparateurs (`callPhoneNumber`, `getContactsCount`, etc.)

Si aucun argument n'est nécessaire à la fonction, le préciser clairement en plaçant le mot clé `void` entre parenthèses.

```c++
void callSomething(void) {
    return;
}
```

## Préprocesseur

Les instructions utilisées pour éviter la duplication lors de l'inclusion doivent suivre la syntaxe suivante :

```cpp
#ifndef __NOM_FICHIER__
#define __NOM_FICHIER__

...

#endif /* __NOM_FICHIER__ */
```

## Constantes

Les constantes doivent être écrites en majuscule en séparant les mots par des '_' (ex. `SCREEN_WIDTH`, `OBJECTS_COUNT`, etc.)

## Blocs

Supprimer les accolades dans le cas d'une instruction unique.

Le contenu d'un bloc doit être précédé d'une tabulation supplémentaire par rapport à son parent.

Les accolades ouvrant et fermant le bloc doivent être précédées d'un retour à la ligne.

```
entry 
{
    ...
}
```

Éviter au maximum l'instruction `goto`.

## Commentaires

Toute fonction, méthode, classe, structure, énumération ou fichier doit être précisément décrit par un commentaire. 

Les commentaires doivent être écrit en langue *française* suivant la syntaxe Doxygen suivante :

- Commentaires multilignes 
```cpp
/**
 * ...
 */
```
- Commentaires sur une ligne
```cpp
... //< ...
```

## Fichiers

Le nom des fichiers doit être écrit en minuscule et en utilisant l'underscore ('_') comme séparateur (ex. `file_stream.cpp`, 'http_client.hpp', etc.)

Les prototypes des fonctions doivent être écrit dans les fichiers d'en tête, leurs implémentations dans le `cpp` correspondant.

Les fichiers d'en tête c++ doivent utiliser l'extension `.hpp`.

Les fichiers sources c++ doivent utiliser l'extension `.cpp`.

Les fichiers d'en tête c doivent utiliser l'extension `.h`. 

Les fichiers sources c doivent utiliser l'extension `.c`.

## Espaces de noms (namespace)

L'utilisation des espaces de nom est largement recommandé.

Le nom d'un espace de nom doit être en minuscules, les mots étant séparés par des underscores (`_`) (ex. `gui`, `http`, etc.)
