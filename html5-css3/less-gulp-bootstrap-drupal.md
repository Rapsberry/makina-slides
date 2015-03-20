# Drupal Bootstrap / Less et Gulp

 23 mars 2015
 

----

## Présentation

**Emmanuelle Helly**

* Intégratrice HTML/CSS depuis 2008
* Plone, Drupal
* emmanuelle.helly@makina-corpus.net

----

# Programme

## Bootstrap

* Mise en forme du contenu
* Mise en page avec la grille adaptative de Bootstrap : pour des sites Responsive Web Design
* Composants Bootstrap

## Less

* variables
* mixins
* heritages
* pseudo-classes
* importation de fichier

---- 

## Thème Drupal bootstrap

* Arborescence du thème

## Gulp

* Installation de nodejs
* Installation des modules nécessaires
* Tâches de Gulp

----

# Framework Bootstrap

----

## Sommaire

* Mise en forme CSS
* La grille bootstrap
* Composants

----

##  Mise en forme CSS

[getbootstrap.com/css](http://getbootstrap.com/css/)

* Typography (alignement, blockquotes, lists)
* Tables
* Formulaires
* Boutons
* Images

----

##  La grille bootstrap

* Le principe
* colonnes imbriquées
* offset
* ordre des colonnes

----

##  Composants

* Glyphicons
* Menus déroulants
* Navigation
* Breadcrumb, pagination, label, badges
* Media (groupe d'image + texte)
* Vignettes

### Presenter Notes

this is notes

----


# LessCSS

----

## Sommaire

* variables
* imbrication de code
* mixins
* importation de fichier

## Installer LessCSS

* Dans windows : [winless.org](http://winless.org/)
* Pour utiliser plus de fonctionnalités de nodejs : [nodejs.org](http://nodejs.org/download/)

----

# Les bases

## variables

    !css
    @nice-blue: #5B83AD;
    @light-blue: @nice-blue + #111;

    #header {
      color: @light-blue;
    }

Résultat :

    !css
    #header {
      color: #6c94be;
    }

Un gain de temps inestimable pour l'intégration front-end

----

## imbrication de code

    !css
    #header {
      color: black;
      .navigation {
        font-size: 12px;
      }
      .logo {
        width: 300px;
      }
    }

----

# Mixins et fonctions

    !css
    .a, #b {
      color: red;
    }
    .mixin-class {
      .a();
    }
    .mixin-id {
      #b();
    }

Résultat :

    !css
    .a, #b {
      color: red;
    }
    .mixin-class {
      color: red;
    }
    .mixin-id {
      color: red;
    }

----

# Import de fichier

    !css
    @import (option) "fichier";

Les options

* `reference`: importe en tant que fichier less sans l'inclure dans la sortie css. Très utilisé pour les fichiers de fonctions less.
* `inline`: inclue le fichier sans le compiler
* `less`: traite le fichier en tant que less, quelque soit l'extension
* `css`: traite le fichier en tant que css
* `once`: n'importe le fichier qu'une seule fois (comportement par défaut)
* `multiple`: importe le fichier plusieurs fois


----

# Drupal bootstrap

----

## Arborescence type d'un thème

### Dans le profil 

    !console
    mon_profil_drupal/
    ├── mon_profil_drupal.drush.inc
    ├── mon_profil_drupal.info
    ├── mon_profil_drupal.install
    ├── mon_profil_drupal.make
    ├── mon_profil_drupal.profile
    ├── modules
    ├── themes
    │   └── mon_theme
    └── translations


----

### Arborescence du thème

    !console
    mon_theme
    ├── bootstrap -> ../../../../sites/all/libraries/bootstrap/
    ├── css
    ├── fonts
    ├── img
    ├── js
    ├── less
    └── templates
        ├── block
        ├── bootstrap
        ├── node
        ├── system
        └── views

----

### Arborescence des fichiers less

    !console
    less
    ├── nodes
    │   ├── news.less
    │   └── event.less
    ├── objects
    │   ├── forms.less
    │   └── tables.less
    ├── pages
    │   └── register.less
    ├── views
    │   ├── recherche.less
    │   └── views.less
    ├── bootstrap.less
    ├── content.less
    ├── fonts.less
    ├── footer.less
    ├── header.less
    ├── mixins.less
    ├── overrides.less
    ├── style.less
    └── variables.less

----

## Les fichiers less

* bootstrap.less importe les feuilles de styles bootstrap
* style.less importe les feuilles de styles du projet


----

# Environnement Gulp

----

## À quoi ça sert ?

Gulp sera utilisé pour :

* générer les fichiers css à partir de style.less et bootstrap.less, à chaque modification d'un fichier
* minifier les fichiers css et js (optionnel, dans ce cas on n'utilise pas les fonctions de minification de Drupal)

----

## Installation de l'environnement

* install nodejs
* installation des modules
* préparation du fichier Gulpfile.js


## Utilisation

    !console
    gulp watch

----

# Questions ?
