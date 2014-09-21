# HTML5 / CSS3

 22-23 Septembre 2014
 CNFPT

----

## Présentation

**Emmanuelle Helly**

* Intégratrice HTML/CSS depuis 2008
* Plone, Drupal
* emmanuelle.helly@makina-corpus.net

----

# Jour 1 : HTML5 / CSS3

## HTML5

* _Intro : le WorldWideWeb_
* Doctype
* Sémantique
* Formulaires
* Media (figure, audio, video)
* Canvas et SVG
* Drag & Drop
* Localstorage

----

## CSS3

* Mise en forme
* Sélecteurs
* Unités relatives et absolues
* Positionnement
* Mise en page (Grid layout)
* Media-queries
* Transformations
* Effets et animations

----

# Jour 2 : Bootstrap, LessCSS

## BOOTSTRAP 3

* Mise en forme du contenu : texte, tableaux, formulaires, boutons, images et la mise en page
* Mise en page avec la grille adaptative de Bootstrap : pour des sites Responsive Web Design
* Composants Bootstrap : barres de navigation, pagination, boutons, etc.

## LessCSS

* variables
* mixins
* heritages
* pseudo-classes
* importation de fichier

----

# Introduction : le World Wide Web

----

## Composants du WorldWideWeb

* URL (_Uniform Resource Locator_)
* HTML (_HyperText Markup Language_)
* HTTP (_HyperText Transfer Protocol_)

## le W3C

**World Wide Web Consortium**, dirigé par *Tim Berners Lee*

* **389** membres (au 15 septembre 2014)
* Définit les spécifications (HTML, XML, accessibilité, mobile)
* Groupes de travail

[w3.org/Consortium](http://www.w3.org/Consortium/)

.fx: larger

----

## Historique

* 1989 : début des travaux de *Tim Berners Lee*, chercheur au CERN, et son équipe. Le principe, l'hypertexte
* 1991 : *Tim Berners Lee* rend le projet **WorldWideWeb** public
* 1993 : création du navigateur **Mosaic**
* 1994 : création du **W3C** par *Tim Berners Lee*
* 1996 : implémentation de **CSS1.0** par **IE**
* 1998 : publication des spécifications **CSS 2.0**
* 1999 : spécifications **HTML4.01**, et début des travaux sur **CSS3**
* 2000 : publication des spécifications pour **XHTML1**. 
* 2006 : publication des recommandations de **XHTML2.0**

Scission au sein du W3C : le **WHATWG** (Web Hypertext Application Technology Working Group) travaille sur un autre standard pour le **HTML**

* 2008 : "First Public Working Draft" du **HTML5** présentée par le **WHATWG**
* 2012 : **HTML5** passe en "Candidate Recommandation"

[fr.wikipedia.org/wiki/World_Wide_Web](http://fr.wikipedia.org/wiki/World_Wide_Web)

.fx: smaller

----

# Les outils de développement

* Éditeur de code : [Notepad++](http://notepad-plus-plus.org/), Sublime Text
* Navigateur : **éviter IE** !! Firefox ou Chrome, et leurs plugins d'inspection de code (voir [Liste de puglins](http://makina-corpus.com/blog/metier/2013/extensions-firefox-pour-le-developpement-web))
* Test et validation
    * [validator.w3.org](http://validator.w3.org/)
    * [opquast.com](http://opquast.com/fr/) pour la qualité du code, l'accessibilité
* Documentation
    * officielle [w3c.org/TR/html5](http://www.w3.org/TR/html5/)
    * compréhensible [developer.mozilla.org](https://developer.mozilla.org/fr/)

----

# Partie 1 : HTML5

----

## Sommaire

* Doctype
* Sémantique
* Formulaires
* Media (figure, audio, video)
* Canvas et SVG
* Drag & Drop
* Localstorage

----

## Le HTML 5 est-il prêt ?

* En "Candidate Recommandation" depuis 2012
* Implémentation variable selon les navigateurs : voir [caniuse.com](http://caniuse.com/)
* Compatible avec IE9, du moins en partie, des outils permettent une "régression en douceur" (graceful degradation)

## DocType

`<!DOCTYPE html>`

... tout simplement

----

# Sémantique

## Balises

* Section : `<article>`, `<aside>`, `<nav>`, `<section>`, `<header>`, `<footer>`
* Grouper : `<figure>`, `<figcaption>`

Code plus clair, page mieux structurée sémantiquement : un meilleur référencement.

<!-- Voir [tinytypo.tetue.net](http://tinytypo.tetue.net/tinytypo.html) -->

--- 

## Structure d'une page

    <body>
        <header>
            <nav data-role="menu">
                <ul>
                ...
                </ul>
            </nav>
        </header>
        <div id="main">
            <aside>
            ...
            </aside>
            <section id="content">
                <article>
                    <figure><img src="__mon__url__" /></figure>
                    <p>Texte</p>
                </article>
            </section>
        </div>
        <footer>
        ...
        </footer>
    </body>

.fx: smaller

----

## Microdatas

Voir [schema.org](http://schema.org/docs/gs.html)

    <div itemscope itemtype="http://schema.org/Person">
        <div itemprop="name"><strong>Emmanuelle Helly</strong></div>
        <div itemscope 
            itemtype="http://schema.org/Organization">
        <a itemprop="url" href="www.ekino.com">
          <span itemprop="name">Makina Corpus</span></a>
        </div>
        <div itemprop="address" itemscope itemtype="http://schema.org/PostalAddress">
          <div itemprop="streetAddress">36 rue Jacques Babinet</div>
          <div>
            <span itemprop="postalCode">31100</span>
            <span itemprop="addressLocality">Toulouse</span>
          </div>
          <div itemprop="addressCountry">France</div>
        </div>
        <div itemprop="telephone">0149687368</div>
    </div>

Autres implémentations : microformats, RDFa

----

# Formulaires

## Nouveaux contrôles

`<input>` de type text, mais aussi :

* tel, url, email, search
* date, time, number, range
* color

## Nouveaux attributs

* placeholder
* pattern
* autocomplete
* min, max, step (pour date, time, number et range)
* list

--- 

## Code

Url avec placeholder

    <input type="url" name="url"   placeholder="Votre site Web" />

Range

    <input type="range" name="range" 
        min="10" max="100" step="5" value="15"/>

Pattern

    <input type="text" name="pattern"   pattern="[a-z]{2}[0-9]{2}" />

Liste

    <input type="text" name="ville" list="villes"/>
    <datalist id="villes">
        <option value="Albi">
        <option value="Cahors">
    </datalist>

.fx: smaller

---

## Exercice

* Créez un formulaire avec les champs suivants : 
    * Nom complet, 
    * Téléphone, 
    * Date de naissance, 
    * Couleur préférée, 
    * Ville (parmi quelques villes)

[Exemple complet](https://github.com/numahell/html5-css3/blob/master/html/forms.html)

----

# Media et Éléments embarqués

## `<embed>` et `<object`>

Pour embarquer des objets flash par exemple.

## `<audio>` et `<video>`

    <audio src="./donjon-crom.mp3" controls></audio>
    <video src="video.ogg" controls 
        poster="video.jpg" width="640" height="480">

Les limites : formats de fichiers différents / navigateurs

* ogg -> Firefox
* webm -> Chrome
* mp4 -> Chrome, IE 

----

## Code

On peut inclure plusieurs formats de media

    <video controls poster="video.jpg" width="640" height="480">
        <source src="video.ogg" />
        <source src="video.avi" />
        <source src="video.mp4" />
    </video>

## Exercice

Essayer la balise `<video>` avec différentes sources, en ouvrant la page dans différents navigateurs.

----

## `<figure>`

Permet d'illustrer et ajouter une légende à une image, un schéma.

    <figure>
      <img src="image.jpg" alt="" />
      <figcaption>Légende de l'image</figcaption>
    </figure>

Peut contenir autre chose que des images : du code ou une vidéo par exemple.

## `<iframe>`

Peut embarquer un autre site, un éditeur de texte riche par example.

----

# Effets et 3D

## CANVAS

* surface de pixels contrôlés en JavaScript, API disponible
* Fonctionnement en "boite noire"

Le "Paint" du web

    <html>
     <head>
      <script type="application/x-javascript">
        function draw() {
         var canvas = document.getElementById("canvas");
         var ctx = canvas.getContext("2d");

         ctx.fillStyle = "rgb(200,0,0)";
         ctx.fillRect (10, 10, 55, 50);
        }
      </script>
     </head>
     <body onload="draw()">
       <canvas id="canvas" width="300" height="300"></canvas>
     </body>
    </html>

.fx: smaller

----

## SVG

Dessiner en 2D vectorielle via XML

* Accès aux éléments d'un SVG depuis le DOM
* CSS applicables
* Peut être chargé depuis un fichier externe ou en ligne dans un document HTML
* L’arbre des données est conservé en mémoire

### Example

    <svg>
      <circle id="circle1" cx="40" cy="40" r="24" />
    </svg>

Voir aussi [css-tricks.com/using-svg](http://css-tricks.com/using-svg/)

----

## WebGL

Un peu plus que bablutiant : de plus en plus de navigateurs le supportent, mais pas toujours les cartes vidéos.

Voir [Les interfaces de demain](http://fr.slideshare.net/makinacorpus/petit-djeuner-html5-et-css3-les-interfaces-de-demain) pour plus de détails.

## Flash ?

Il n’est pas (tout à fait) mort, mais n'est plus supporté par les Iphone et Ipad

----

# Application web en HTML5

## Drag&Drop



## Local Stockage

* App Cache
* LOCALSTORAGE
* INDEXED DB
* Limites & USAGES


## File API


## Server-Sent Events

* Web Sockets



----

# Partie 2 : CSS3

----

# Mise en forme

## Propriétés

* `background-size`, `border-radius`, `box-shadow`, `opacity`, 
* dégradés
* arrière-plan multiples
* transparence pour la couleur de fond

[css3generator.com](http://css3generator.com/)

----

## Font-Face

* [fontsquirrel.com](http://www.fontsquirrel.com/)
* [www.google.com/fonts](http://www.google.com/fonts/)

----

## Extensions spécifiques des navigateurs


----

# Sélecteurs

## Sélecteurs CSS2

Sont maintenant implémentés par les navigateurs modernes

par attribut

    a[attribut~="valeur"]

par élément fils direct

    a > b

par élément frère

    a + b

----

## Sélecteurs CSS3

par attribut

    a[attribut^="valeur"]

par fils premier, dernier ou tous les x éléments

    a:first-child
    a:last-child
    a:nth-child(expression)

négation

    a:not(.class)

première lettre, première ligne

    ::first-letter
    ::first-line

* Un tutoriel : [flukeout.github.io](http://flukeout.github.io/)
* La documentation officielle : [www.w3.org/TR/selectors](http://www.w3.org/TR/selectors/)

.fx: smaller

----

# Unités

## Absolues

px, pt

## Relatives

* em, %
* rem (root em), relative à la taille attibuée au document

----

# Positionnement

## Dans le flux

## Hors du flux



----

# Mise en page

flexbox

----

# Media-queries

* Le responsive webdesign en image
* Orientation et Localisation
* Device api

----

## Transformations



----

# CSS animé

## Transitions / Animations


---- 

# Partie 3 : Bootstrap 3

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

.notes: notse

### Presenter Notes

this is notes

----


# Partie 4 : LessCSS

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

    @nice-blue: #5B83AD;
    @light-blue: @nice-blue + #111;

    #header {
      color: @light-blue;
    }

Résultat :

    #header {
      color: #6c94be;
    }

## imbrication de code

----

# mixins et fonctions


----

# importation de fichier

----

# TP : un thème avec LessCSS et Bootstrap

----

# Questions ?
