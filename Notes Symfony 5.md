Symfony 5

Guide du cours

Table of Contents {#table-of-contents .TOC-Heading}
=================

[1. Configuration de base : Netbeans, Composer et XDebug
6](#configuration-de-base-composer-git-et-xdebug)

[2. Création d\'un projet de base contenant Symfony 5
7](#configuration-de-base-visual-studio-code)

[3. Accès au projet en Apache. Configuration des Virtual Hosts
8](#symfony-avec-apache.-configuration-des-virtual-hosts)

[3.1. Création d\'un serveur virtuel (virtual host) en Windows
8](#création-dun-serveur-virtuel-virtual-host-en-windows)

[3.2. Création d\'un serveur virtuel (virtual host) en OSX
10](#création-dun-serveur-virtuel-virtual-host-en-osx)

[4. Routing 12](#routing)

[4.1. Les routes et la réécriture des URLs
12](#les-routes-et-la-réécriture-des-urls)

[4.2. Les routes contenant de paramètres
16](#les-routes-contenant-de-paramètres)

[4.3. Les contraintes dans les routes
18](#les-contraintes-dans-les-routes)

[4.4. Les valeurs par défaut pour les paramètres du routing
19](#les-valeurs-par-défaut-pour-les-paramètres-du-routing)

[5. Controllers et actions 20](#controllers-et-actions)

[5.1. Procédure de création manuelle d\'un controller
20](#procédure-de-création-manuelle-dun-controller)

[5.2. L\'objet Response 22](#lobjet-response)

[5.3. L\'objet Request 23](#lobjet-request)

[5.4. Types de réponses d\'un controller: render, redirect,
redirectToRoute et forward
24](#types-de-réponses-dun-controller-render-redirect-redirecttoroute-et-forward)

[5.4.1. Redirect 24](#redirect)

[5.4.2. RedirectToRoute 25](#redirecttoroute)

[5.4.3. Forward 26](#_Toc4669735)

[5.4.4. Render 27](#render)

[5.5. Génération automatique d\'un controller
27](#création-dun-controller-avec-lassistant)

[6. Les environnements de développement et production
28](#les-environnements-de-développement-et-production)

[6.1. Le Web Profiler 29](#_Toc4669739)

[6.2. Afficher le contenu des variables avec dump
29](#afficher-le-contenu-des-variables-avec-dump)

[7. Gestion basique d\'erreurs 30](#gestion-basique-derreurs)

[7.1. Modifier la réponse http du serveur
30](#modifier-la-réponse-http-du-serveur)

[7.2. Lancer une exception 31](#lancer-une-exception)

[8. Les Vues. Le moteur de templates TWIG
32](#les-vues.-le-moteur-de-templates-twig)

[8.1. Création d\'un template en utilisant Twig 32](#_Toc4669745)

[8.2. Les variables 33](#les-variables)

[Exercices : 34](#exercices)

[8.2.1. Les conditions 35](#_Toc4669748)

[8.2.2. Les boucles 36](#les-boucles)

[8.2.3. Les filtres 38](#les-filtres)

[8.3. Héritage de templates en TWIG (I)
39](#héritage-de-templates-en-twig-i)

[8.4. Création de Templates en TWIG (II) 41](#_Toc4669752)

[9. Les Services 43](#incruster-une-action-du-controller-dans-une-vue)

[9.1. Utilisations des services inclus dans Symfony
43](#utilisations-des-services-inclus-dans-symfony)

[9.2. Création de nos propres services
46](#création-de-nos-propres-services)

[9.3. Le fichier /config/services.yaml 48](#_Toc4669756)

[10. Le modèle : création d\'entités et de la BD 49](#cookies)

[10.1. Présentation de Doctrine 49](#présentation-de-doctrine)

[10.2. Configuration de Doctrine et des paramètres de la BD
50](#configuration-de-doctrine-et-des-paramètres-de-la-bd)

[10.3. Création des entités et mise à jour de la BD
51](#création-des-entités-et-mise-à-jour-de-la-bd)

[10.4. Rajouter/effacer des propriétés d\'une entité
52](#rajoutereffacer-des-propriétés-dune-entité)

[11. Le modèle : Implémentation des relations
53](#le-modèle-les-relations)

[11.1. Implémentation d\'une relation Many-To-One
53](#relation-many-to-one)

[11.2. Explication du code généré par l\'assistant
57](#explication-du-code-généré-par-lassistant)

[11.3. Implémentation d\'une relation Many-To-Many
60](#relation-many-to-many)

[11.4. Implémentation d\'une relation One-To-One
62](#relation-one-to-one)

[11.5. Implémentation d\'une relation récursive (self-association)
63](#relation-récursive-self-association)

[11.5.1. Relation récursive d\'un à plusieurs
63](#relation-récursive-dun-à-plusieurs)

[11.5.2. Relation récursive de plusieurs à plusieurs
64](#relation-récursive-de-plusieurs-à-plusieurs)

[12. Le modèle : Accès à la BD avec Doctrine
66](#le-modèle-accès-à-la-bd-avec-doctrine)

[12.1. SELECT 66](#select)

[12.2. INSERT et UPDATE 69](#insert-et-update)

[12.2.1. INSERT 69](#insert)

[12.2.2. UPDATE 70](#update)

[12.2.3. DELETE 70](#delete)

[13. Persistance 71](#le-modèle-persistance)

[13.1. Transitivité en Cascade 74](#transitivité-en-cascade)

[13.2. Encapsulation 77](#encapsulation)

[14. Héritage de classes et implémentation dans la BD
79](#héritage-de-classes-et-implémentation-dans-la-bd)

[14.1. Single Table Inheritance 80](#single-table-inheritance)

[14.2. Class Table Inheritance 82](#class-table-inheritance)

[15. Accès à la BD avec DQL 83](#accès-à-la-bd-avec-dql)

[15.1. SELECT 84](#select-1)

[15.1.1. Requête qui renvoi un array d\'arrays
84](#requête-qui-renvoi-un-array-darrays)

[15.1.2. Requête qui renvoi un array d\'objets
85](#requête-qui-renvoi-un-array-dobjets)

[15.1.3. Regular Joins et Fetch Joins 86](#regular-joins-et-fetch-joins)

[15.2. UPDATE 89](#update-1)

[15.3. Exercices DQL 89](#exercices-dql)

[16. Accès à la BD avec DQL en utilisant les classes Repositoires
91](#accès-à-la-bd-avec-dql-en-utilisant-les-classes-repositoires)

[17. Accès à la BD avec Query Builder
93](#accès-à-la-bd-avec-query-builder)

[18. Formulaires en Symfony 96](#formulaires-en-symfony)

[18.1. Création une classe de formulaire
96](#création-une-classe-de-formulaire)

[18.2. Création d\'un formulaire associé à une entité
99](#création-dun-formulaire-associé-à-une-entité)

[18.3. Types des champs du formulaire
100](#types-des-champs-du-formulaire)

[18.4. Propriétés des champs du formulaire
101](#propriétés-des-champs-du-formulaire)

[18.5. Méthode et Action 103](#méthode-et-action)

[18.1. Boutons dans les formulaires (bonnes pratiques)
107](#boutons-dans-les-formulaires-bonnes-pratiques)

[18.1. Rendu du formulaire dans la vue
108](#rendu-du-formulaire-dans-la-vue)

[18.2. Résumé : création et personnalisation de base d\'un formulaire
109](#résumé-création-et-personnalisation-de-base-dun-formulaire)

[18.3. Traitement des données du formulaire (explication de base)
110](#traitement-des-données-du-formulaire-explication-de-base)

[18.4. Bonnes pratiques pour créer de formulaires en Symfony
113](#bonnes-pratiques-pour-créer-de-formulaires-en-symfony)

[18.5. Style des formulaires 114](#style-des-formulaires)

[18.6. Objets associés dans un formulaire
115](#formulaires-concernant-plusieurs-entités)

[19. Upload de fichiers en utilisant un formulaire 117](#_Toc4669804)

[19.1. Stockage dans le serveur d\'une seule image pour chaque entité
117](#stockage-dans-le-serveur-dune-seule-image-pour-chaque-entité)

[19.2. Problèmes dans l\'upload 120](#problèmes-dans-lupload)

[20. AJAX en Symfony 122](#ajax-en-symfony)

[20.1. Exemple d\'appel AJAX
122](#exemple-dappel-ajax-avec-un-formulaire)

[20.2. Utilisation de blocs dans twig avec AJAX
124](#utilisation-de-blocs-dans-twig-avec-ajax)

[20.3. Renvoie d\'un array d\'objets en JSON (ex: Autocomplete)
127](#renvoi-dun-array-dobjets-en-json)

[21. Doctrine Fixtures 129](#doctrine-fixtures)

[22. Authentification : inscription et login/password
131](#authentification-inscription-et-loginpassword)

[22.1. Configuration de la sécurité et création d\'un formulaire de
login
131](#configuration-de-la-sécurité-et-création-dun-formulaire-de-login)

[22.2. Création d\'un formulaire d\'inscription
135](#création-dun-formulaire-dinscription)

[23. Logout 136](#logout)

[24. Accès à l\'objet User 137](#accès-à-lobjet-user)

[25. Envoi du mail (Swift Mailer) 138](#envoi-du-mail-swift-mailer)

[Annexe 1 : Création rapide d\'un projet
141](#annexe-1-création-rapide-dun-projet)

[1. Création de la structure du projet
141](#création-de-la-structure-du-projet)

[2. Création d\'un controller 141](#création-dun-controller)

[3. Création du modèle 141](#création-du-modèle)

[4. Création des templates (vues) 142](#création-des-templates-vues)

[Annexe 2 : Application Demo 144](#annexe-2-application-demo)

Configuration de base : Composer, Git et XDebug
===============================================

-   Installez **Composer** (voir guide)

-   Installez **Git**

-   Installez **XDebug** (voir guide)

-   Changez la configuration dans php.ini pour activer XDebug :

\[XDebug\]

zend\_extension =
\"C:\\xampp\\php\\ext\\php\_xdebug-2.5.5-7.1-vc14.dll\"

xdebug.remote\_host = \"127.0.0.1\"

xdebug.remote\_enable = 1

xdebug.remote\_handler = \"dbgp\"

xdebug.idekey = netbeans-xdebug

xdebug.profiler\_append = 0

xdebug.profiler\_enable = 0

xdebug.profiler\_enable\_trigger = 0

xdebug.profiler\_output\_dir = \"c:/xampp/tmp/xdebug\"

xdebug.profiler\_output\_name = \"cachegrind.out.%t-%s\"

xdebug.remote\_autostart = 0

xdebug.remote\_connect\_back = 0

xdebug.remote\_host = \"127.0.0.1\"

xdebug.remote\_port = 9000

xdebug.remote\_handler = \"dbgp\"

xdebug.remote\_mode = req

xdebug.remote\_log = \"c:/xampp/tmp/xdebug/xdebug\_remot.log\"

xdebug.show\_local\_vars = 9

xdebug.trace\_output\_dir = \"c:/xampp/tmp\"

Configuration de base : Visual Studio Code
==========================================

1.  Installez [Visual Studio
    Code](https://code.visualstudio.com/download)

2.  Installez ces extensions :

    -   [Intelephense](https://marketplace.visualstudio.com/items?itemName=bmewburn.vscode-intelephense-client)

    -   [PHP NameSpace
        Resolver](https://marketplace.visualstudio.com/items?itemName=MehediDracula.php-namespace-resolver)

Installation de Symfony et création d\'un projet de base
========================================================

-   Téléchargez l'exécutable **d'installation** de Symfony :

<https://symfony.com/download>

> Lancez le fichier que vous venez de télécharger et qui installera
> l'exécutable **symfony.exe** dans le dossier que vous-même pouvez
> spécifier. Ce fichier exécutable permet de lancer un certain ensemble
> d'actions concernant le framework (ex : créer un projet Symfony).
> Voyons un exemple :

-   Créez le **squelette** d'une application web. Allez dans votre
    dossier htdocs (ou le dossier de votre choix) et lancez l'exécutable
    de Symfony (qui se trouve dans le path) avec les paramètres
    suivants :

symfony new \--full Projet1Symfony5

Cette ligne créera un dossier contenant la structure d'un projet de base
Symfony.

**Note** : si vous ne voulez pas installer Symfony vous pouvez toujours
créer vos projets en utilisant composer directement

> composer create-project symfony/website-skeleton Projet1Symfony5

-   Lancez le **serveur web interne** de Symfony depuis la console (on
    utilisera Apache plus tard). Allez dans le dossier de votre projet
    et tapez :

symfony server:start

Vous pouvez toujours utiliser Apache comme serveur, mais pour la phase
de développement c'est plus simple d'utiliser le serveur déjà inclus
dans Symfony. Testez le bon fonctionnement du serveur en regardant les
messages sur la console et en tapant l'adresse suivante dans le
navigateur :

http://localhost:8000/

Installation de packages dans un projet Symfony Flex
====================================================

**Symfony Flex** est un plug-in Composer installé **par défaut lors de
la création d\'une nouvelle application Symfony** et automatisant les
tâches les plus courantes des applications Symfony. Flex modifie le
comportement de base de *require*, *update* et *remove.* Beaucoup de
packages crées para la l de Symfony l un *recipe (« recette ») ***: un
ensemble d'instructions pour installer et activer un package dans un
projet Symfony**. On peut, en plus, rajouter Flex dans un projet Symfony
existant d'une version précédente (qui n'aie pas Flex). Plus de
documentation ici :

[https://symfony.com/doc/current/setup.html\#creating-symfony-applications](https://symfony.com/doc/current/setup.html%23creating-symfony-applications)

Symfony avec Apache. Configuration des Virtual Hosts
====================================================

Considérez qu\'on a une application web qui se trouve dans le dossier

C:/xampp/htdocs/Symfony5/projet1symfony/web

Normalement on devrait saisir cette URL pour y accéder :

localhost/Symfony4/projet1symfony/web

Nous devons savoir qu\'Apache permet d\'utiliser la technique de
réécriture d\'URL. Cela nous permettra, par exemple, d\'avoir un projet
qui se trouve dans

C:/xampp/htdocs/Symfony4/projet1symfony/web

Et en accéder en utilisant tout simplement cette URL :

projet1symfony.localhost

Nous devons configurer cette correspondance dans le fichier
/xampp/apache/conf/extra/**httpd-vhosts.conf**. Le nom vhosts vient du
fait qu\'on est en train de créer un **serveur virtuel**.

C\'est Apache qui transforme une URL dans autre, mais toujours selon nos
règles.

Création d\'un serveur virtuel (virtual host) en Windows
--------------------------------------------------------

**Pour créer et utiliser un serveur virtual suivez ces pas** :

1.  Activez d\'abord la réécriture de l\'URL dans la configuration
    d\'Apache ainsi que la lecture des serveurs virtuels dans
    httpd-vhosts. Juste ouvrez le fichier
    **c:\\xampp\\apache\\conf\\httpd.conf** et effacez les commentaires
    de ces deux lignes (si elles sont commentées)

LoadModule rewrite\_module modules/mod\_rewrite.so

Include conf/extra/httpd-vhosts.conf

2.  Modifiez (ou créez) le fichier
    **c:\\xampp\\apache\\conf\\extra\\vhosts.conf** en rajoutant :

\<VirtualHost \*:80\>

ServerName projet1Symfony.localhost

DocumentRoot \"C:\\xampp\\htdocs\\Symfony4\\projet1Symfony\\public\"

\<Directory \"C:\\xampp\\htdocs\\Symfony4\\projet1Symfony\\public\"\>

AllowOverride All

Order Allow,Deny

Allow from All

\</Directory\>

\</VirtualHost\>

Pour chaque nouveau projet vous devez rajouter la première section en
modifiant le ServerName, DocumentRoot et Directory.

Pour pouvoir continuer à utiliser le serveur **localhost** normalement
vous devez rajouter sa **configuration** :

\<VirtualHost \*:80\>

ServerName localhost

DocumentRoot \"C:/xampp/htdocs\"

\<Directory \"C:/xampp/htdocs\"\>

AllowOverride All

Require all granted

\</Directory\>

\</VirtualHost\>

3.  Installez l\'apache-pack qui créera les règles d\'écriture d\'url
    pour le projet (Apache en aura besoin). Dans le dossier du projet,
    tapez :

composer require symfony/apache-pack

(Répondez \"y\" pour accepter l\'installation)

4.  Rajoutez dans le fichier **hosts** de
    c:\\Windows\\System32\\drivers\\etc\\hosts:

127.0.0.1 projet1Symfony.localhost

(Vous devez démarrer notepad comme administrateur)

5.  Redémarrez le serveur Apache et allez sur le site :

http://projet1symfony.localhost/

Une page de bienvenue devrait s\'afficher

#### Exercice : création d\'un projet contenant l\'application skeleton

Créez un deuxième projet projet2Symfony selon la procédure précédente

Création d\'un serveur virtuel (virtual host) en OSX
----------------------------------------------------

1.  Activez la lecture de httpd-vhosts dans le fichier httpd.conf:
    ouvrez **xampp** et cliquez sur le bouton Config pour ouvrir ce
    fichier de configuration d\'Apache.

Note: Le fichier se trouve dans Applications/xampp/xamppfiles/etc

Une fois le fichier ouvert, effacez les commentaires de ces deux lignes
(si elles sont commentées)

Include conf/extra/httpd-vhosts.conf

Activez aussi la réécriture de l\'URL dans la configuration d\'Apache e

LoadModule rewrite\_module modules/mod\_rewrite.so

2.  Modifiez (ou créez) le fichier
    **/Applications/XAMPP/xamppfiles/etc/extra/httpd-vhosts.conf** en
    rajoutant :

\<VirtualHost \*:80\>

ServerName projet1Symfony.localhost

DocumentRoot
\"**/Applications/XAMPP/xamppfiles/htdocs/Symfony4/projet1Symfony/public**\"

\<Directory
\"**/Applications/XAMPP/xamppfiles/htdocs/Symfony4/projet1Symfony/public**\"\>

AllowOverride All

Order Allow,Deny

Allow from All

\</Directory\>

\</VirtualHost\>

Pour chaque nouveau projet vous devez rajouter la première section en
modifiant le ServerName, DocumentRoot et Directory.

Pour pouvoir continuer à utiliser le serveur **localhost** normalement
vous devez rajouter sa **configuration** :

\<VirtualHost \*:80\>

ServerName localhost

DocumentRoot \"**/Applications/XAMPP/xamppfiles/htdocs**\"

\<Directory \"**/Applications/XAMPP/xamppfiles/htdocs**\"\>

AllowOverride All

Require all granted

\</Directory\>

\</VirtualHost\>

3.  Dans le dossier de votre projet, installez l\'apache-pack qui créera
    les règles d\'écriture d\'url pour le projet (Apache en aura
    besoin). Dans le dossier du projet, tapez :

php composer.phar require symfony/apache-pack

(Répondez \"y\" pour accepter l\'installation)

4.  Rajoutez dans cette ligne dans le fichier **hosts** :

127.0.0.1 projet1Symfony.localhost localhost

Pour éditer le fichier hosts :

1.  Ouvrez la console

2.  Tapez cd /

3.  Tapez sudo nano etc/hosts

4.  Tapez votre mot de passe

5.  Rajoutez la ligne indiquée

6.  Enregistrez le fichier avec CONTROL-O et puis Enter, sortez du
    logiciel avec CONTROL-X et puis Enter

 

Routing
=======

**Objectif** : comprendre l\'utilité et le fonctionnement de base des
routes dans un framework (Symfony) et être capable de créer des routes
vers les actions des controllers

Les routes et la réécriture des URLs
------------------------------------

Une **route** nous **sert à accéder à une ressource** de l\'application
(une action, une page, une image). Pour accéder aux ressources d\'une
application web de base **nous sommes habitués à saisir une page PHP
dans l**\'**URL** (avec de paramètres, éventuellement) **qui corresponde
à un fichier qui existe dans le serveur**.

**Exemples :**

> page\>.php
>
> <http://localhost/appAgenda/pages/afficherContacts.php>
>
> <http://localhost/videoClub/films/rechercherFilm.php>?nom=Alien&genre=Scifi&tutu=blablabla

Dans de vraies applications, et pas seulement pour soigner l\'esthétique
mais aussi pour faciliter la saisie et pour la sécurité, nous avons
besoin de créer des URLs plus simples. En général nous voulons taper une
URL sur le navigateur et charger un fichier qui ne corresponde pas
forcement à ce qu\'on tape sur l\'URL.

**Exemple :** pour charger la page

http://netflox.localhost/recherche.php?prix=5000&category=four

Nous voulons juste taper :

http://netflox.localhost/recherche/5000/4

Pour ce faire, on utilise une technique qui s\'appelle **réécriture
d\'URL**.

**Nous allons définir toutes les routes nous-mêmes**. Une route
indiquera la correspondance entre ce qu\'on tape dans le navigateur et
le code qui sera lancé (dans notre cas une action d\'un controller) .

Pour définir une route nous pouvons utiliser quatre systèmes :
**annotations, YAML, XML ou du code PHP.**

Ici on suivra les conseils des bonnes pratiques de Symfony et on
utilisera des **annotations**. Pour utiliser des annotations on doit
d'abord rajouter au projet le package qui permet leur manipulation :

composer require annotations

Nous allons créer maintenant un **controller** à la main contenant une
route créée avec une annotation :

*// src/Controller/ExemplesRoutingController.php*

\<?php

**namespace** App\\Controller;

*// importation de quelques librairies dont on a besoin dans le
controller*

**use**
Symfony\\Bundle\\FrameworkBundle\\Controller\\AbstractController;

**use** Symfony\\Component\\Routing\\Annotation\\Route;

**use** Symfony\\Component\\HttpFoundation\\Response;

*// classe contenant le code du controller (les actions)*

**class** ExemplesRoutingController **extends** AbstractController{

/\*\*

\* \@Route(\"/exemples/accueil\");

\*/

**public** **function** afficherMessageAccueil ()

{

**return** **new** Response(

\'\<html\>\<body\>Je suis une action du controller
ExemplesRoutingController.\</body\>\</html\>\'

);

}

}

C\'est l\'annotation **\@Route** qui détermine la correspondance entre
ce qu\'on tape dans l\'url :

http://projet1symfony.localhost**/exemples/accueil**

et l\'action à lancer (la méthode qui se trouve juste après
l\'annotation)

**afficherMessageAccueil**

Une route indiquera alors une **action à lancer (méthode d\'une classe)
qui se trouve dans un controller (la classe, dans un fichier .php)**

Vous pouvez afficher toutes les routes de votre projet en tapant dans la
console cette ligne :

php bin/console debug:route

L'outil **bin/console** vous permette de générer des bases de données à
partir des entités, d'obtenir information du debugging et de plein
d'autres opérations

**Note : observez que le contenu de la route ne doit pas forcement
contenir le nom du controller. Ici le controller s\'appelle
ExemplesRoutesController mais dans la route on indique uniquement
\"exemples\"**

**Concernant le nom de l'action, dans les exemples successifs la route
correspondra au nom de l\'action et le camel case sera transformé selon
le critère ci-dessous :**

**public** **function** monAction1() \"/exemples/mon/action1\"

Dans le controller ci-dessus on a juste envoyé du code HTML directement
au client en utilisant l\'objet **Response** (en détail plus tard) avec
un string contenant du HTML, mais... et si on veut créer toute une page
HTML? On ne va pas mettre tout le code dans l\'action du controller ! on
utilisera alors les **vues**.

Chaque action dans un controller a souvent une vue associé (le \"rendu\"
de la page) qui contiendra le code HTML, JavaScript, CSS ou même du
PHP). On étudiera les vues plus tard.

La structure complète du controller, ainsi que l\'objet **Response**,
seront expliqués plus tard, il faut juste savoir que le premier nous
sert à envoyer une réponse directement au navigateur **sans passer par
une vue**.

**\
**

*Exercices*

1.  #### Créez une nouvelle action monAction1 qui affiche le message \"Ce controller est en charge du répertoire de l\'application et je suis juste une action à l\'intérieur\"

2.  #### Créez une nouvelle action monAction2 qui affiche la date actuelle. Le path pour la route peut (ou pas) correspondre au nom de l\'action, c\'est à vous de choisir selon les circonstances et votre critère

Les routes contenant de paramètres
----------------------------------

**Objectif** : créer une action qui puisse accéder aux paramètres
envoyés dans l\'URL de la même façon qu\'on fait en utilisant \$\_GET
dans un code PHP normal

Nous avons déjà mentionné que, grâce à la réécriture des URLs nous
n\'utiliserons plus le format habituel de passage de paramètres dans
l\'URL :

http://netflox.localhost/recherche.php?prix=5000&category=four

Cette route aura ce format à partir de maintenant :

<http://netflox.localhost/recherche/5000/four>

On va configurer de routes pour pouvoir accéder facilement à ces
paramètres.

En général le format de routes sera :

**param1\>/\<valeur param2\>**

Voici un autre exemple :

[http://jamazon.localhost/produits/add/**5000**/galaxy-s25](http://jamazon.localhost/produits/add/5000/galaxy-s25)

Cette ligne appelle l\'action **add** du controller **produits** et lui
envoie les valeurs des deux variables. Voici un exemple pratique.

**Exemple :** Créer une action qui reçoit deux paramètres pour pouvoir
l\'appeler dans la route.

Le but est de créer une action \"afficherContact\" qui reçoit un prénom
et une profession

[http://projet1symfony.localhost/exemples/afficherContact/Marie/formatrice](http://projet1symfony.localhost/repertoire/afficherContact/Marie/formatrice)

et affiche un message de \"Je suis \<nom\>,\<profession\>\". Pour ce
faire, l\'action doit obtenir les valeurs reçues dans l\'URL en
utilisant un nouvel objet **Request** (au lieu de l\'array \$\_GET ou
\$\_POST qu\'on utilise si on n\'est pas dans le contexte d\'un
framework)

**\
**

**Procédure :**

1.  **Créez une route** qui permette à l\'action de recevoir deux
    paramètres

/\*\*

\* \@Route(\"/exemples/afficher/contact/{prenom}/{profession}\")

\*/

2.  **Créez l\'action** afficherAction dans le controller **Exemples**

// rajoutez cette ligne pour importer l\'objet Request

**use** Symfony\\Component\\HttpFoundation\\Request;

// L\'objet Request rajouté dans la signature de l\'action contiendra
les données

// de la requête faite au serveur. En ce qui nous concerne maintenant,
il

// contiendra les valeurs des paramètres de l\'URL. L\'objet Request
sera étudié

// plus tard.

/\*\*

\* \@Route(\"/exemples/afficher/contact/{prenom}/{profession}\")

\*/

**public** **function** afficherContact(Request \$objetRequest){

**echo** \"Je suis dans le controller, action \'afficher\'\";

// on obtient les valeurs des paramètres de l\'url,

// on fait appel à la méthode get de l\'objet Request

\$lePrenom = \$objetRequest-\>get (\"prenom\");

\$laProfession = \$objetRequest-\>get (\"profession\");

**return** **new** Response (\"\<br\>Le prénom dans l\'URL est:
\".\$lePrenom. \"\<br\>La profession dans l\'URL est:
\".\$laProfession);

}

3.  **Créez l\'a vue** associée à l\'action

Dans ce cas nous n\'avons pas une vue, on renvoie la réponse HTML
directement au client en utilisant l\'objet Response

4.  **Lancez l\'action** en tapant l\'URL

[http://projet1symfony.localhost/exemples/afficher/Marie/formatrice](http://projet1symfony.localhost/agenda/afficher/Marie/formatrice)

#### Exercices : création d\'actions contenant de paramètres

1.  #### Créez une nouvelle action afficheTVAC qui reçoit un prix et affiche le prix TVAC 

2.  #### Créez une autre action qui reçoit trois valeurs et affiche la moyenne 

Les contraintes dans les routes 
-------------------------------

Nous pouvons limiter les caractères qui peuvent apparaitre dans les
paramètres d\'une route (pour limiter la saisie dans la barre d\'adresse
du navigateur, par exemple).

**Exemple :** dans l\'action suivant nous voulons forcer le paramètre
**âge** à contenir uniquement un ou plusieurs caractères uniquement
numériques et pas de lettres

/\*\*

\* \@Route(\"/exemples/bienvenue/age/{age}\",
**requirements={\"age\"=\"\\d+\"}**)

\*/

**public** **function** bienvenueAge (Request \$objRequest){

**return** **new** Response (\"Bienvenue au site, vous avez
\".\$objRequest-\>get (\"age\").\" ans\");

}

On a utilisé la balise **requirements** et on rajoute une expression
régulière (ici **\\d+**). Si vous voulez commencer à créer des
expressions régulières pour vos propres routes, vous pouvez utiliser ce
résumé :

<http://jkorpela.fi/perl/regexp.html>

Nous pouvons aussi choisir un autre format ou on n\'utilisera pas la
balise **requirements**. On rajouter l\'expression régulière dans de
balises **\<\>** :

// Requirements sans balise \"requirements\"

/\*\*

\* \@Route(\"/exemples/bienvenue/age/no/balise/{age\<\\d+\>}\")

\*/

**public** **function** bienvenueAgeNoBalise (Request \$objRequest){

**return** **new** Response (\"Bienvenue au site, vous avez
\".\$objRequest-\>get (\"age\") .\" ans\");

}

Si vous ne respectez le format, Symfony affichera une erreur de page
introuvable. Pour le moment nous sommes en mode de **développement
(dev)** et Symfony nous montrera l\'erreur dans le **Symfony Profiler**
(outil de Symfony pour faciliter le debugging, expliqué plus tard).
Quand on changera au mode **production (prod)** on verra juste un simple
message d\'erreur 404 -- page introuvable.

#### Exercices : création de contraintes dans les paramètres des routes

En utilisant la documentation sur les expressions régulières :

1.  Créez une action \"afficheVille\" qui reçoit le nom d\'une ville. Le
    nom doit contenir uniquement de lettres ou de chiffres mais pas
    d\'autres caractères (voir \$, %, \^ etc...)

2.  Modifiez l\'action précédant pour que le paramètre \"ville\" puis
    avoir une taille maximale de 15 caractères

3.  Créez une action de votre choix contenant de restrictions pour
    le/les paramètres

Les valeurs par défaut pour les paramètres du routing
-----------------------------------------------------

Nous pouvons facilement établir une valeur par défaut pour nos
paramètres en rajoutant **?** et puis la valeur dans l\'annotation.

**Exemple :** donner une valeur par défaut au paramètre TVA de l\'action
qui calcule la TVA

/\*\*

\* \@Route
(\"/exemples/affiche/prix/defaut/tvac/{prix}/{**tauxTVA?21**}\")

\*/

**public** **function** affichePrixDefautTvac(Request \$objetRequest)

{

\$prix = \$objetRequest-\>get(\"prix\");

\$tauxTVA = \$objetRequest-\>get(\"tauxTVA\");

**return** **new** Response(\"\<br\>Le produit coûte \".\$prix. \"
euros, \"

.(\$prix \* (1 + \$tauxTVA / 100)). \" TVAC\");

}

#### Exercice : utilisation de valeurs par défaut

Créez une action \"afficheMessage\" qui affiche un message un certain
nombre de fois à l\'utilisateur. Le message est reçu dans l\'url, ainsi
que le nombre de fois. Si le nombre de fois n\'est pas indiqué,
l\'action l\'affichera 10 fois. Le paramètre qui contienne le nombre de
fois doit être numérique

Pour avoir plus information sur la gestion de routes, allez sur la
documentation de Symfony :

<https://symfony.com/doc/current/routing.html>

Paramètres optionnels
---------------------

> Vous pouvez créer une route contenant des paramètres optionnels. Il
> **suffit de rajouter \'?\' après le nom du paramètre**.

Exemple :

/\*\*

\* \@Route (\"/exemples/affiche/prix/opt/tvac/{prix}/{**tauxTVA?**}\")

\*/

**public** **function** afficheOptPrixTaux (Request \$objetRequest){

\$prix = \$objetRequest-\>get (\"prix\");

\$tauxTVA = \$objetRequest-\>get (\"tauxTVA\");

**if** (!**isset** (\$tauxTVA)){

\$tauxTVA = 21;

}

**return** **new** Response (\"\<br\>Le produit coûte \".\$prix. \"
euros, \"

.(\$prix \* (1 + \$tauxTVA / 100)). \" TVAC\");

}

Les valeurs alternatives pour les paramètres
--------------------------------------------

> Vous pouvez obliger à un paramètre à avoir une valeur parmi un
> ensemble de valeurs de votre choix en utilisant l'opérateur OR dans la
> route.
>
> Exemple : le paramètre \"disponibilité\" peut prendre trois valeurs
> (et en plus il est optionnel !)

/\*\*

\* \@Route
(\"/exemples/affiche/disponibilite/{disponibilite**\<oui\|non\|en
attente\>?**}\")

\*/

**public** **function** afficheDisponibilite(Request \$objRequest)

{

**return** **new** Response(\"Le produit est \" .
\$objRequest-\>get(\"disponibilite\"));

}

**\
**

Controllers et actions
======================

Le controller contient une méthode pour chaque action à effectuer dans
l\'application.

Une action peut faire, en gros, deux taches différentes :

a)  **Générer un contenu et l\'envoyer au client en utilisant une vue**
    (ex. : afficher la météo de Bruxelles en se connectant à un serveur
    de météo et envoyer les données obtenues à une vue que les
    affichera)

b)  **Rediriger vers une autre action**

Procédure de création manuelle d\'un controller
-----------------------------------------------

1.  **Créez la classe vide du controller dans le Namespace
    App\\Controller**

**Exemple** : **ContactsController**. La classe doit se trouver dans le
NameSpace qui lui correspond

**namespace** App\\Controller;

**class** ContactsController **extends** AbstractController{

// ici les actions

}

2.  **Importez la classe AbstractController car votre controller
    héritera cette classe (extends)**. Si vous allez utiliser les
    classes **Response** et **Request** importez-les aussi. Importez la
    classe **Annotations** pour pouvoir créer les routes

**namespace** App\\Controller;

**use** Symfony\\Component\\HttpFoundation\\Response;

**use** Symfony\\Component\\HttpFoundation\\Request;

**use** Symfony\\Component\\Routing\\Annotation\\Route;

**use**
Symfony\\Bundle\\FrameworkBundle\\Controller\\AbstractController;

**class** ContactsController **extends** AbstractController{

// ici les actions

}**\
**

3.  **Créez l\'action de votre choix dans le controller (dans la
    classe)**

**public function afficherTous (){**

\$noms = \[\'Lucy\', \'Juan\', \'Salima\', \'Mar\', \'Lupita\',
\'Marie\'\];

\$strNoms = **implode** (\",\", \$noms);

**return** **new** Response (\$strNoms);

**}**

4.  **Rajoutez la route vers l\'action que vous venez de créer dans une
    annotation**

/\*\*

\* \@Route (\"/contacts/afficher/tous\")

\*/

5.  **Lancez l\'action**

<http://localhost:8000/contacts/afficherTous>

Le code final du controller sera :

\<?php

**namespace** App\\Controller;

**use** Symfony\\Component\\HttpFoundation\\Response;

**use** Symfony\\Component\\HttpFoundation\\Request;

**use** Symfony\\Component\\Routing\\Annotation\\Route;

**use**
Symfony\\Bundle\\FrameworkBundle\\Controller\\AbstractController;

**class** ContactsController **extends** AbstractController{

/\*\*

\* \@Route (\"/contacts/afficher/tous\")

\*/

**public** **function** afficherTous (){

\$noms = \[\'Lucy\', \'Juan\', \'Salima\', \'Mar\', \'Lupita\',
\'Marie\'\];

\$strNoms = **implode** (\",\", \$noms);

**return** **new** Response (\$strNoms);

}

}

#### Exercice : Créez deux controllers Exercice1Controller et Exercice2Controller. Créez deux actions pour chaque controller. Créez aussi des actions qui contiennent de paramètres.

L\'objet Response
-----------------

Dans les exemples précédents, les actions **gêneraient** **un contenu
HTML manuellement et l\'envoyaient au navigateur en utilisant un objet
de la classe Response**

Un objet **Response** contient toutes les propriétés et les méthodes
pour **définir la réponse au client** (en plus du contenu HTML), mais
ici on va se concentrer sur les plus basiques et indispensables :

-   Le **content** (contenu envoyé au client : un **code HTML**, un
    **contenu JSON**...) et

-   Les **headers** (entêtes http pour indiquer, entre autre, le type de
    réponse qu\'on envoie au client -- **HTML, JSON**...). Voici un
    exemple dans une action :

#### Exemple : création d\'une action qui utilise l\'objet Response (ExemplesReponsesController.php)

N\'oubliez pas de rajouter la route !!

/\*\*

\* \@Route (\"/contacts/message/response\")

\*/

**public** **function** messageResponse(){

\$contenu = \"\<h1\>Je vais être le contenu d\'un objet
Response\</h1\>\";

\$reponse = **new** Response ();

\$reponse-\>setExpires(**new** \\DateTime(\'2025/3/8\'));

\$reponse-\>headers-\>set (\'Content-Type\',\'text/html\');

\$reponse-\>setContent(\$contenu);

**return** \$reponse;

}

L\'objet Request
----------------

Quand on fait appel à une action du controller on est en train de
**faire une requête au controller** (rien à voir avec les requêtes de BD
!). Les informations concernant cette requête (ex : les valeurs des
paramètres dans la URL) sont accessibles via l\'objet **Request**.

L\'objet **Request** nous permet d\'accéder aux variables super-globales
telles que **\$\_POST**, **\$\_GET**, **\$\_SERVER**, **\$\_FILES**.
Regardez cette documentation pour savoir comment accéder à chaque
variable :

<https://symfony.com/doc/current/components/http_foundation.html>

Pour qu\'une action puisse accéder à l\'objet Request **on** **doit
juste rajouter un paramètre du type Request dans la signature de
l\'action (injecter l\'objet Request)**.

#### Exemple : Utilisation de l\'objet Request

Créez l\'action suivante dans le controller ContactsController (rajoutez
la route !) et lancez-la dans le navigateur

// L\'objet Request rajouté dans la signature de l\'action contiendra
les données

// de la requête faite au serveur. En ce qui nous concerne maintenant,
il

// contiendra les valeurs des paramètres de l\'URL.

/\*\*

\* \@Route (\"/contacts/message/request/{prenom}/{profession}\")

\*/

**public** **function** messageRequest (Request \$objetRequest){

**echo** \"Je suis dans le controller, action \'afficher\'\";

// on obtient les valeurs des paramètres de l\'url,

// on fait appel à la méthode get de l\'objet Request

\$lePrenom = \$objetRequest-\>get (\"prenom\");

\$laProfession = \$objetRequest-\>get (\"profession\");

**return** **new** Response (\"\<br\>Le prénom dans l\'URL est:
\".\$lePrenom. \"\<br\>La profession dans l\'URL est:
\".\$laProfession);

}

Par la suite on verra comment créer de vues qui reçoivent de données
depuis le controller.

Types de réponses d\'un controller: render, redirect, redirectToRoute et forward
--------------------------------------------------------------------------------

Une action dans un controller peut générer du HTML, JSON, XML, le
téléchargement d\'un fichier, une redirection vers une autre action, une
erreur 404 ou plein d\'autres résultats : tout dépend de nos besoins.
Parmi les actions principales on a :

**render** permet d\'afficher une vue

**redirect** permet de rediriger le navigateur vers une autre adresse,
sans ou avec de paramètres

**redirectToRoute** permet de lancer une action mais en utilisant le nom
(**name**) d\'une route. On va voir des exemples dans ce chapitre

**forward** permet de déléguer l\'action (pas d\'erreur http)

Note : Pour comprendre le fonctionnement de ces réponses, on va créer
des actions dans un nouveau controller ExemplesReponsesController

### Redirect

La méthode redirect nous permet d\'appeler une autre action dans un
autre controller ou rediriger vers une autre adresse web

#### **Exemple :** redirection vers une autre adresse avec de paramètres

// cette action reçoit un titre de film et réalise une redirection vers
imdb

// pour chercher le film

/\*\*

\* \@Route (\"/exemples/reponses/exemple/redirect/{titreFilm}\")

\*/

**public** **function** exempleRedirect(Request \$req)

{

\$titreFilm = \$req-\>get(\"titreFilm\");

\$url = \"http://www.imdb.com/find?ref\_=nv\_sr\_fn&q=\".\$titreFilm;

// maintenant on appelle une autre action

**return** \$this-\>redirect(\$url);

}

### RedirectToRoute

Pareil que \"Redirect\" mais au lieu de spécifier la route complète on
utilisera sa propriété **name**. Nous pouvons envoyer de paramètres à la
nouvelle route.

#### **Exemple** : Redirection vers une nouvelle sans paramètres

// Cette action est juste un exemple qui montre comment une action peut

// rediriger vers une autre en utilisant la propriété \"name\"

/\*\*

\* \@Route (\"/exemples/reponses/redirection/avec/name\")

\*/

**public** **function** redirectionAvecName(Request \$req)

{

// faire quoi qui ce soit ici\....

// et rediriger après vers une autre route en lui envoyant de paramètres

**return** \$this-\>redirectToRoute(\"spaghettiCarbonara\");

}

/\*\*

\* \@Route (\"/exemples/reponses/action/avec/name\",
name=\"spaghettiCarbonara\");

\*/

**public** **function** actionAvecName(Request \$req)

{

**return** **new** Response(\"Je suis une action qui a été appelée par
une \"

. \"autre, je porte un nom\");

}

**\
**

#### **Exemple** : Redirection vers une nouvelle route avec de paramètres (l\'action reçoit de paramètres dans l\'URL)

// Cette action est juste un exemple qui montre comment une action peut

// rediriger vers une autre en utilisant sa propriété \"name\".

// Cette action envoie paramètres

// sous la forme d\'un array à la route cible

// Cette action est juste un exemple qui montre comment une action peut

// rediriger vers une autre en utilisant sa propriété \"name\".

// Cette action envoie paramètres

// sous la forme d\'un array à la route cible

/\*\*

\* \@Route (\"/exemples/reponses/redirection/avec/name/params\")

\*/

**public** **function** redirectionAvecNameParams(Request \$req)

{

// faire quoi qui ce soit ici\....

// et rediriger après vers une autre route

**return** \$this-\>redirectToRoute(\"spaghettiBolognese\",
\[\'type\'=\>\'bio\',

\'prix\'=\>\'10\'\]);

}

/\*\*

\* \@Route
(\"/exemples/reponses/action/avec/name/params/{type}/{prix}\",
name=\"spaghettiBolognese\");

\*/

**public** **function** actionAvecNameParams(Request \$req)

{

\$type = \$req-\>get(\"type\");

\$prix = \$req-\>get(\"prix\");

**return** **new** Response(\"Je suis une action qui a été appelée par
une \"

. \"autre, je porte un nom et je reçoit des valeurs: \".\$type.\"
\".\$prix);

}

[]{#_Toc4669735 .anchor}

### Forward

Forward nous permet d\'appeler une autre action d\'un autre controller

#### **Exemple** : Appel à une autre action d\'un autre controller

Ici on a créé l\'action \"forwardExemple\" (n\'oubliez pas la route !)
dans le controller

// Exemple de forward

// utilisation de forward pour appeler une action du controller Contacts

/\*\*

\* \@Route (\"/exemples/reponses/forward/exemple\")

\*/

**public** **function** forwardExemple()

{

**return** \$this-\>forward(

\'App\\Controller\\ContactsController:afficherTous\',

\[\'prix\' =\> 400,\'tauxTva\' =\> 10\]

);

}

### Render

La méthode **render** prend le nom de la vue (.twig) et optionnellement
une variable contenant de données. L\'idée est de passer de données du
controller à la vue.

Par exemple : le controller accède à une BD, obtient un array ou des
objets contenant les données d\'un tableau et l\'envoie à la vue pour
qu\'elle puisse les afficher.

On va étudier cette méthode plus tard dans la section [Les Vues. Le
moteur de templates Twig](#les-vues.-le-moteur-de-templates-twig).

Création d\'un controller avec l\'assistant
-------------------------------------------

> Vous pouvez utiliser la commande
>
> php bin/console make:controller \<nom du nouveau controller\>
>
> pour générer automatiquement le squelette d\'un controller.
>
> Symfony génère le fichier du controller, une action route ainsi
> qu\'une vue associée. Testez-le par vous-mêmes.

Gestion basique d\'erreurs
==========================

Pour gérer proprement les erreurs dans une application Web nous avons
plusieurs possibilités :

-   **Créer de vues personnalisées pour les erreurs de base (500, 404
    etc...) en utilisant les conventions de Symfony**

-   **Modifier la réponse HTTP** du serveur (ex: envoyer une réponse de
    404 -- Not Found quand on le souhaite, même si la page existe)

-   **Lancer une exception** du système ou une personnalisée

Créer une vue pour chaque erreur à gérer en utilisant les conventions de Symfony
--------------------------------------------------------------------------------

> Cette méthode s\'applique dans l\'environnement de **prod**, car dans
> l\'environnement de **dev** le Symfony Profiler est activé. Changez
> alors **dev** en **prod** dans le fichier **.env**. Une fois le
> changement est fait :

1.  Créez cette **structure de dossiers** dans le dossier **templates**

> ![](media/image1.png){width="1.6166666666666667in" height="0.7275in"}

2.  Créez **une vue pour chaque erreur à gérer** (.html.twig) suivant la
    convention **errorXXX.html.twig dans le dossier Exception**

> **Exemple :** error500.html.twig

3.  Créez le **contenu personnalisé de la vue** pour chaque erreur que
    vous voulez traiter

**\
**

#### Exemple : gestion de l\'erreur 500

Voici un exemple de gestion de l\'erreur 500. L\'action
**exempleActionProvoqueErreur** du controller
**ExemplesErreursController** provoque une erreur 500 :

/\*\*

\* \@Route(\"/exemple/action/provoque/erreur\")

\*/

**public** **function** exempleActionProvoqueErreur()

{

// Decommentez la ligne suivante:

\$b = aa;

}

Créez alors un fichier **erreur500.html.twig** dans le dossier
**Exception** contenant un texte (par exemple : \"Erreur interne !\").
Relancez l\'action pour que le nouveau message d\'erreur s\'affiche. Si
vous obtenez l\'erreur original au lieu de la vue que vous avez créé,
nettoyez la cache depuis la console et relancez l\'action. Pour nettoyer
la cache

php bin/console cache:clear

#### Exercice : traitez l\'erreur 404 en utilisant ce système

Modifier la réponse http du serveur
-----------------------------------

Voici un exemple de comment envoyer un code d\'erreur au navigateur en
modifiant la réponse HTTP

**class** ExemplesErreursController **extends** AbstractController

{

/\*\*

\* \@Route(\"/erreurs/erreur/pas/trouve\", name=\"exemples\_erreurs\")

\*/

// réponse HTTP modifiée : dans cet exemple, on renvoie au

// navigateur une réponse \"404: NOT FOUND\"

// si la variable de session \"login\" n\'existe pas. Décommentez la
ligne du \"set\"

// pour établir sa valeur une première fois, puis

// commentez la ligne et relancez le code

**public** **function** erreurPasTrouveAction(Request \$req){

\$session = \$req-\>getSession();

\$session-\>set (\"login\",\"Marie\");

\$reponse = **new** Response();

**if** (\$session-\>get(\"login\") == **null**){

\$reponse-\>setStatusCode(Response::HTTP\_NOT\_FOUND);

\$reponse-\>setContent(\"Page non trouvée!\");

// autre exemple:

// \$reponse-\>setStatusCode(Response::HTTP\_BAD\_GATEWAY);

}

**else** {

\$reponse-\>setContent(\"Bienvenu \" . \$session-\>get(\"login\"));

}

**return** (\$reponse);

}

}

Lancer une exception
--------------------

Au lieu de rediriger vers une autre page du site on peut carrément
lancer une exception. C\'est à nous de voir qu\'est-ce que nous convient
selon les besoins du projet.

/\*\*

\* \@Route(\"/erreurs/erreur/pas/trouve/avec/exception\")

\*/

**public** **function** errorPasTrouveAvecExceptionAction(Request
\$req){

\$session = \$req-\>getSession();

//\$session-\>set (\"login\",\"on lance cette ligne une seule fois\");

\$reponse = **new** Response();

**if** (\$session-\>get(\"login\")!=**null**){

**throw** \$this-\>createNotFoundException (\"Non trouvée\");

}

**else** {

\$reponse-\>setContent(\"Bienvenu \" . \$session-\>get(\"login\"));

}

**return** (\$reponse);

}

Les Vues. Le moteur de templates TWIG
=====================================

En Symfony nous pourrions générer les vues en utilisant du HTML et PHP
purs, mais l\'utilisation de TWIG comme **moteur de templates** nous
facilitera vraiment la tâche. **Un moteur de templates sert à générer
les vues à partir d\'un fichier de base (template).** On part du
principe que tout ce qui concerne la présentation (les vues) se trouvera
dans les templates (jamais dans le controller !).

Le moteur TWIG est un **composant** de Symfony mais on pourrait
l\'utiliser dans n\'importe quel projet ailleurs.

Les principaux avantages de TWIG sont :

1.  Il masque le langage de programmation des vues : il n\'y a pas du
    PHP dans les templates !

2.  Il fournit une bonne interface avec les contrôleurs

3.  Il nous permet de créer des hiérarchies de templates (en détail plus
    tard)

4.  On peut le lier avec modèle en utilisant **Doctrine** (en détail
    plus tard)

5.  On peut utiliser un squelette twig avec d\'autres langages de
    programmation (ex : python)

Quand on lance la méthode **render** depuis un controller, Symfony
parcourra le fichier **.twig** correspondant et générera un objet
Response à partir de ce fichier. Cet objet génère le HTML qui sera
renvoyé au serveur.

Attention : les fichiers .twig utilisent la notation snake case. Ex: Le
template pour une action mangeonsDuChocolat sera un fichier portant le
nom mangeons\_du\_chocolat.html.twig

Notes de base sur Twig :

<https://twig.symfony.com/doc/3.x/>

La documentation complete sur les vues en Symfony se trouve ici :

<https://symfony.com/doc/current/templates.html>

[]{#_Toc4669745 .anchor}

Création d\'un template en utilisant Twig
-----------------------------------------

On va créer une vue en utilisant Twig. La vue reçoit un tableau qui a
été créé dans le controller et l\'affichera. Normalement le controller
accédera à une base de données, mais pour simplifier notre exemple on
crée juste un tableau. Faisons un exemple en partant de zéro :

1.  **Créez un controller** ExemplesTwig en utilisant

php bin/console make:controller ExemplesTwig

Notes : L\'assistant créera le fichier du controller dans
src/Controller, ainsi qu\'un dossier exemples\_twig dans le dossier
**Templates**. Ce dossier contiendra toutes les vues liées aux actions
de ce controller. Par défaut il y aura déjà une action **index** et une
vue **index.html.twig**

Vous pouvez faire appel à cette action pour afficher la vue en tapant la
route dans le navigateur :

http://localhost:8000/exemples/twig

2.  Créez une **action** exemple1 dans ce controller. Dans l\'action
    vous devez indiquer à Symfony de renvoyer au navigateur le rendu de
    la vue qu\'on va créer :

> /\*\*
>
> \* \@Route (\"exemplesTwig/exemple1\", name=\"exemple1Twig\")
>
> \*/
>
> **public** **function** exemple1 (){
>
> **return** \$this-\>render (\'exemples\_twig/exemple\_1.html.twig\');
>
> }

3.  Créez la vue : un **template twig** contenant portant le nom
    exemple\_1.html.twig dans Templates

{% **extends** \'base.html.twig\' %}

{% block body %}

**Bonjour! je suis un template!**

{% endblock %}

Conservez cette structure de blocs dans vos twigs et remplissez à chaque
fois le contenu du block body. On étudiera plus tard comment utiliser
les blocs pour enrichir la structure d\'un template twig. Lancez la page
juste pour tester si tout est en ordre, puis continuez la lecture.

#### Exercice : Créez une deuxième action affichePays et un template qui affiche \"vive la Belgique\"

Les variables
-------------

Twig peut utiliser des **variables**, ce qui nous permet d\'accéder
d\'une façon très simple aux données générés dans le controller. Pour
accéder une variable nous devons utiliser cette notation :

> {{ nom }}

Pour accéder aux propriétés d\'un objet on utilisera cette notation :

> {{ client.nom }}

Ces variables proviennent du controller. Voyons un exemple. Créez cette
action dans le controller :

**public** **function** afficheVille()

{

// nous créons une structure de données

\$vars = \[\'nom\' =\> \'Bruxelles\',

\'population\' =\> 1500000,

\'pays\' =\> \'Belgique\'\];

// render reçoit l\'array associatif et renvoie l\'objet Response

// on accédera à cette array depuis la vue

**return** \$this-\>render (\'exemples\_twig/affiche\_ville.html.twig\',
\$vars);

}

Nous venons de rajouter un paramètre à l\'appel **render**. Cela nous
permet d\'envoyer de valeurs à la vue. Le format est **d\'un array
associatif dont les clés deviennent de variables** accessibles dans le
twig

Modifions maintenant notre template twig. **Notez que pour accéder aux
variables on a juste utilisé les clés de l\'array**

Le nom de la ville est:

{{ nom }}

La population est:

{{ population }}

Cette ville se trouve dans ce pays:

{{ pays }}

Nous avons envoyé un array associatif. Si on avait juste une valeur
simple à envoyer c\'est très simple :

**return** \$this-\>render (\'exemples\_twig/blablabla.html.twig\',

\[\'cinema\'=\> \'Aventura\'\]);

Si on veut envoyer un array indexé il faudra lui \"donner\" une clé pour
qu\'il soit accessible dans le fichier twig. Par exemple :

\$lesStagiaires = \[\'Lucie\',\'Salima\',\'Doris\'\];

Render enverra un array associatif contenant une clé dont la valeur
correspond à cet array :

\$vars = \[\'lesStagiaires\' =\> \$lesStagiaires \]

Dans le fichier twig on pourra accéder en utilisant la notation normale
d\'array :

{{ lesStagiaires\[0\] }}

{{ lesStagiaires \[1\] }}

{{ lesStagiaires \[2\] }}

Pour les objets **c\'est exactement la même chose mais on utilisera la
notation de \".\"** dans le fichier twig pour pouvoir accéder ses
propriétés (pas la flèche de PHP!)

#### Exercices :

1.  Créez une nouvelle action afficheTvacTwig qui reçoit une valeur
    d\'un prix dans l\'URL et une valeur de TVA et calcule le prix Tvac.
    Créez un twig qui affiche \"Le prix TVAC est xxx\"

2.  Créez une nouvelle version de l\'exercice précédent qui puisse
    afficher \"Le prix xxxx euros avec le taux de TVA de xxxx % est x
    xxx\"

3.  Créez une nouvelle action qui affiche un array de trois villes
    belges. Les villes sont fixées et se trouvent dans la vue, ne sont
    pas envoyées par le controller à la vue

4.  Créez une nouvelle version de l\'exercice précédent où la liste de
    villes est envoyée depuis le controller à la vue dans un array

5.  Créez une nouvelle version de l\'exercice 4. Cette fois l\'action
    reçoit la langue d\'affichage dans l\'URL (FR ou NL). La
    discrimination par langue se réalise dans le controller

6.  Affichez la date actuelle dans la vue. Utilisez la classe DateTime
    et envoyez l\'objet à la vue. Dans la vue, utilisez la méthode
    **format** de la classe DateTime pour afficher la date proprement

[]{#_Toc4669748 .anchor}

### Les conditions

Le langage de TWIG inclut aussi les **conditions**. Voici un exemple:

{% **if** age \> 18 **and** age \< 60 %}

\<p\>Pas de réduction\</p\>

{% **endif** %}

Voici la documentation pour avoir plus de détails :

<https://twig.symfony.com/doc/2.x/tags/if.html>

#### 

#### Exercices :

1)  Créez une action qui reçoit un prix dans l\'URL. Créez une action
    qui reçoit le prix et le multiplie par deux. Vérifiez dans la vue
    que le prix ne dépasse pas 100 euros en utilisant une condition

2)  Trouvez dans la documentation des exemples d\'utilisation des
    conditions dans twig. Faites deux vues qui utilisent des conditions
    (if et elseif)

### Les boucles

Nous pouvons aussi créer **de boucles du type \"foreach\" sur des
éléments Iterables** (**arrays**, par exemple). Son utilisation est
assez simple :

1.  Créez l\'élément à parcourir dans une action et renvoyez-le à la vue

2.  Utilisez la syntaxe **for -- in** dans la vue pour parcourir
    l\'élément

#### Exemple : création d\'un array dans le controller et affichage dans la vue en utilisant une boucle

1.  Voici l\'action. On a créé un array associatif

/\*\*

\* \@Route(\"/exemples/twig/boucles/exemple1\")

\*/

**public** **function** exemple1 (){

\$vars = \[

\'ville\' =\> \[\'nom\' =\> \'Bruxelles\',

\'population\' =\> 1500000,

\'pays\' =\> \'Belgique\'

\]

\];

**return** \$this-\>render
(\'exemples\_twig\_boucles/exemple\_1.html.twig\', \$vars);

}

2.  Voici le contenu de la vue

**Les données dans l\'array sont :**

\<table\>

**{% for cle, valeur in ville %}**

\<tr\>\<td\>**{{ cle }}**\</td\>\<td\>**{{ valeur }}**\</td\>\</tr\>

**{% endfor %}**

\</table\>

Si nous avons besoin de **parcourir un objet on doit le transformer en
array**. Cette conversion crée un array associatif dont les **clés**
sont les **propriétés de l\'objet** et les **valeurs** sont les
**valeurs de ces propriétés**. Voici un exemple :

#### Exemple : parcourir un objet avec une boucle dans la vue

Nous créons un objet Film et on le renvoie à la vue. Nous devons
convertir cet objet en array :

**\
**

Pour lancer ce code la classe livre doit exister (juste pour cet
exemple, créez la classe juste après la classe du controller :

**class** Film

{

**public** \$titre;

**public** \$auteur;

**function** **\_\_construct**(\$titre, \$auteur) {

\$this-\>titre = \$titre;

\$this-\>auteur = \$auteur;

}

}

#### Exercices :

1)  Créez une nouvelle classe Film et une action qui renvoie un objet de
    cette classe à la vue. Affichez son contenu dans une vue dans un
    tableau HTML

2)  Créez une nouvelle action contenant un array d\'objets (Films).
    Envoyez-le à la vue et affichez le contenu de chaque Film dans un
    tableau HTML

### Les filtres

Un filtre est une action sur lune variable telle que mettre la variable
en majuscules, enlever les espaces, enlever les caractères spéciaux,
renvoyer la taille d\'un string ou un array\...

La syntaxe des filtres est :

{{ variable \| filtre }}

Cette expression renvoie le résultat d\'appliquer le filtre à la
variable, par exemple :

{{ titre \| lower }}

Affichera le titre en minuscules. Vous pouvez une liste **de filtres**
[ici](https://twig.symfony.com/doc/2.x/filters/index.html)

Voici un exemple de vue qu\'utilise de filtres.

#### Exemple 1 : action qui renvoie un array, vue qu\'utilise un filtre pour mettre en majuscules la première lettre de chaque propriété de l\'array

/\*\*

\* \@Route(\"/exemples/twig/filtres/exemple1\",
name=\"exemples\_twig\_filtres\")

\*/

**public** **function** exemple1()

{

\$ville = \[\'nom\' =\> \'Bruxelles\',

\'population\' =\> 1500000,

\'pays\' =\> \'Belgique\'

\];

**return**
\$this-\>render(\'exemples\_twig\_filtres/exemple\_1.html.twig\', \[

\'controller\_name\' =\> \'ExemplesTwigFiltresController\',

\'ville\' =\> \$ville

\]);

}

**Les données dans l\'array sont:**

\<table\>

**{% for cle, valeur in ville %}**

\<!\-- capitalize renvoie la variable en majuscules \--\>

\<tr\>\<td\>**{{ cle \| capitalize }}**\</td\>\<td\>**{{ valeur
}}**\</td\>\</tr\>

**{% endfor %}**

\</table\>

**{% if ville \| length \> 1 %}**

**Le tableau n\'est pas vide**

**{% endif %}**

#### Exemple 2 : Action qui renvoie un array à la vue. Utilisation du filtre \"join\"

Le filtre \"join\" crée une chaine de caractères contenant tous les
éléments d\'un array séparés par un \"séparateur\" choisi par
nous-mêmes. Voici un exemple où on enchaine les filtres \"join\" et
\"upper\" :

Les données dans l\'array sont:

{% **if** ville \| length \> 1 %}

Le tableau n\'est pas vide, voici son contenu

{{ ville \| **join** (\" - \") \| upper }}

{% **endif** %}

Héritage de templates en TWIG (I)
---------------------------------

Pour les sites qui contiennent un ensemble de pages qui partagent le
même contenu (ex: header, nav et footer) le moteur de TWIG possède un
**système d\'héritage** qui nous permet de créer une sorte de master
page qui contiendra des blocs variables.

Voici un exemple d\'utilisation :

#### Exemple : création d\'un squelette de master page et inclusion du contenu dans sa section main

1.  **Créez un template twig contenant le squelette d\'une master page :
    master\_page\_1.html.twig**

\<html\>

\<head\>\</head\>

\<body\>

\<header\>

\<h1\>**Voici le header de la page**\</h1\>

\</header\>

\<main\>

\<!\-- on indique que un bloc \"contenuPrincipal\" sera incrusté
ici\--\>

{% **block** contenuPrincipal %}{% **endblock** %}

\</main\>

\<footer\>

\<nav\>

\<ul\>

\<li\>**Option footer 1**\</li\>

\<li\>**Option footer 2**\</li\>

\</ul\>

\</nav\>

\</footer\>

\</body\>

\</html\>

2.  **Créez deux templates pour les contenus** (ex:
    *contenu\_1\_master\_page\_1.html.twig* et
    *contenu\_2\_master\_page\_1.html.twig*) **qui héritent** de
    *master\_page\_1.html.twig* **en utilisant extends**. Délimitez le
    contenu de votre vue par les directives block .

*contenu\_1\_master\_page\_1.html.twig*

{% **extends** \"exemples\_twig\_heritage/master\_page\_1.html.twig\" %}

{% **block** contenuPrincipal %}

Je voudrais manger de champignons dans le contenu 1 !

{% **endblock** %}

*contenu\_2\_master\_page\_1.html.twig*

{% **extends** \"exemples\_twig\_heritage/master\_page\_1.html.twig \"
%}

{% **block** contenuPrincipal %}

Je voudrais manger de carottes dans le contenu 2 !

{% **endblock** %}

3.  Créez **les actions** (et les **routes**) qui rendront cette vue et
    lancez chacune dans votre navigateur. Vous observerez que le contenu
    de cette vue sera incrusté dans la page.

/\*\*

\* \@Route(\"/exemples/twig/heritage/contenu1/master/page1\")

\*/

**public** **function** contenu1MasterPage1()

{

**return**
\$this-\>render(\'exemples\_twig\_heritage/contenu\_1\_master\_page\_1.html.twig\');

}

/\*\*

\* \@Route(\"/exemples/twig/heritage/contenu2/master/page1\")

\*/

**public** **function** contenu2MasterPage1()

{

**return**
\$this-\>render(\'exemples\_twig\_heritage/contenu\_2\_master\_page\_1.html.twig\');

}

**Important** : **extends** doit être la première balise d\'un template

#### Exercice : codez un nouveau template vous-mêmes qui hérite de la master page que vous venez de créer. Cette nouvelle vue reçoit un array contenant les infos d\'un livre de son action associée et l\'affiche dans le contenu de la master page

[]{#_Toc4669752 .anchor}

Création de Templates en TWIG (II)
----------------------------------

Nous pouvons simplifier encore la structure de la page si on utilise la
directive **include**, qui nous permet d\'inclure le contenu d\'autres
fichiers twigs où on le souhaite.

Voici un exemple :

#### Exemple : simplification de la master page en utilisant include pour importer le header et le footer

1.  **Creéz une nouvelle master page master\_page\_2.html.twig**

\<html\>

\<head\>

\<body\>

\<header\>

**{% include \"header.html.twig\" %}**

\</header\>

\<main\>

**{% block contenuPrincipal %}{% endblock %}**

\</main\>

\<footer\>

**{% include \"footer.html.twig\" %}**

\</footer\>

\</body\>

\</html\>

2.  Créez les twigs **header.html.twig** et **footer.html.twig** dans le
    dossier de la master page

**header.html.twig :**

\<h1\>**Je suis le header**\</h1\>

**footer.html.twig**

\<nav\>

\<ul\>

\<li\>**Option footer 1**\</li\>

\<li\>**Option footer 2**\</li\>

\</ul\>

\</nav\>

3.  Créez les actions et les routes

/\*\*

\* \@Route(\"/exemples/twig/heritage/contenu1/master/page1\")

\*/

**public** **function** contenu1MasterPage2()

{

**return**
\$this-\>render(\'exemples\_twig\_heritage/contenu\_1\_master\_page\_2.html.twig\');

}

/\*\*

\* \@Route(\"/exemples/twig/heritage/contenu2/master/page2\")

\*/

**public** **function** contenu2MasterPage2()

{

**return**
\$this-\>render(\'exemples\_twig\_heritage/contenu\_2\_master\_page\_2.html.twig\');

}

> Notez que les includes ne doivent pas servir uniquement à la création
> d\'une master page. Nous pouvons utiliser cet outil dans n\'importe
> quelle fichier twig. Cela nous permet d\'inclure des fragments de la
> page qui se trouvent dans d\'autres fichiers et qui deviennent ainsi
> partageables par toutes les vues.

#### Exercice : créez une master page en utilisant twig. La master page contiendra une barre de navigation contenant trois liens. Chaque lien appelle une action d\'un controller

Aidez-vous de cette documentation :

<https://symfony.com/doc/current/templates.html#linking-to-pages>

Vider un bloc hérité d\'un template
-----------------------------------

> Dans certaines pages il se peut qu\'on hérite d\'un template qui
> contienne une section qui ne nous intéresse pas (ex : la barre de
> navigation du contenu du site dans une page de login). La solution à
> ce problème est simple : on doit déclarer le bloc dans notre page et
> le laisser vide.

#### Exemple : on hérite un menu d\'un template base qu\'on ne souhaite pas avoir dans notre template login

Il suffira d\'inclure (dans la page qui hérite le template)

{% block menu %}{% endblock %}

Et le block sera vide.

Incruster une action du controller dans une vue
-----------------------------------------------

Considérez le cas générique d\'un site où plusieurs vues qui, en plus de
son propre contenu, contiennent une section (un div, par exemple) qui
charge un contenu d\'une BD (ex : latest news, dernières offres,
information dernière minute etc...).

Voici un exemple : Vue1 et Vue 2 ont une section dynamique commune (le
code est dans *ExempleControllerDansVueController.php*, actions
*afficheVue1* et *afficheVue2*)

![](media/image2.png){width="4.483333333333333in"
height="2.6260083114610673in"}

![](media/image3.png){width="4.641666666666667in"
height="2.7278379265091863in"}

**Le code pour charger le contenu de cette section dans chacune de ces
pages devra alors se répéter dans chaque action du controller, ce qui
casse le principe du DRY.** On pourrait se dire d\'utiliser **include**,
mais le problème est que le contenu doit être généré par une action, il
ne suffit pas d\'inclure un autre template !

On peut résoudre ce problème assez facilement : on peut **incruster
(embed) l\'appel d\'un controller dans chaque template et créer une
seule action**. Cette action (*genererContenuDynamique*) n\'a pas de
route car elle sera uniquement utilisée depuis les templates.

On aura alors :

-   Une **action pour générer chaque template**

-   Une **action sans route pour générer le contenu de la section
    > commune**

-   Un **appel à cette action dans chaque template** là où on veut
    > réaliser le rendu (\'embed\' le controller)

L\'appel au controller depuis la vue se fait de cette manière :

\<div id=\'container2\'\>

{\#on incruste le controller ici\#}

{{ render (controller (

\'App\\\\Controller\\\\ExempleControllerDansVueEmbedController::sectionNouvellesDynamique\',{
\'nombreNouvelles\':3 }

))

}}

\</div\>

Observez que si on utilise la syntaxe \"**::\"** on doit échapper les
back slash. On peut aussi envoyer de paramètres à l\'action.

Vous avez un exemple fonctionnel et commenté dans
ExempleControllerDansVueEmbedController.php et les templates associés.

#### Exercice :

Créez un site contenant deux pages. Dans les deux pages on doit avoir
une section commune qui affiche une blague aléatoire sur Chuck Norris.
Utilisez cette api : https://api.chucknorris.io/

Pour faire appel à une API depuis Symfony, installez le client http :

composer require symfony/http-client

Si l\'API n\'a pas d\'authentification, il suffit d\'utiliser la syntaxe
qui suit.

\$client = HttpClient::create();

\$response = \$client-\>request (\'GET\',
\'<https://api.chucknorris.io/jokes/random>\');

Pour savoir plus sur l\'appels aux Apis dans Symfony :

<https://symfony.com/doc/current/components/http_client.html#making-requests>

Regardez aussi la section \"Processing réponses\". Utilisez **dump**
pour vérifier ce que vous obtenez.

 

Les environnements de développement et production
=================================================

Dans un projet Symfony nous pouvons choisir **l\'environnement de
travail**. Les choix possibles sont **prod, dev** et **test**. Tant
Symfony comme les \"packages\" de tiers contient de fichiers de
configuration qui déterminent son comportement selon le mode de travail.
Ces fichiers varient selon le mode de travail qu\'on choisit.

Si nous choisissons le mode **dev** (par défaut) Symfony chargera le
module **web\_profiler,** qui facilite le debugging de l\'application en
affichant plein d\'information sur notre application (entre autre les
erreurs de toute sorte : typographie, connexion de bases de données,
pages introuvable...). En mode **prod** le web profiler ne sera pas
chargé car nous ne voulons pas donner au client plus d\'informations que
nécessaire (ex : le nom de la base de données).

Nous pouvons aussi avoir de modules (packages) de tiers ou faites par
nous-mêmes dont la configuration change selon nous soyons dans le mode
**dev**, **prod** ou **test** :

![](media/image4.png){width="1.8583333333333334in"
height="2.908695319335083in"}

Observez que nous avons, par exemple, trois fichiers de configuration
pour **monolog** (génération de messages de logging dans le serveur).
Les logs seront générés d\'une façon différente selon le mode où on se
trouve. Il y a d\'autres packages qui sont désactivés dans un mode et
actives dans d\'autres.

(La localisation de ces fichiers est définie dans src/kernel.php)

**Vous pouvez changer d\'environnement en modifiant le fichier *.env*
qui se trouve dans la racine du projet (APP\_ENV peut être prod, dev ou
test)**

\#\#\#\> symfony/framework-bundle \#\#\#

APP\_ENV=dev

Le **kernel** de Symfony - code qui est en charge de recevoir les
requêtes de l\'utilisateur et envoyer une réponse au navigateur - agira
d\'une façon ou l\'autre selon la valeur de APP\_ENV. **Le kernel
chargera tous les services** qui correspondent au mode choisi, ainsi que
leur **configuration** (qui varie entre dev, prod et test).

Dans la page index.php on peut observer la manière dont le kernel est
créé.

Dans le fichier **config/bundles.php** vous pouvez voir quels sont les
services disponibles pour chaque mode.

Les fichiers .env et .env.local
-------------------------------

Par défaut Symfony lit le contenu du fichier **.env**. Si vous utilisez
un système de versions (GIT) ce fichier sera pris en compte. Si on veut
développer localement (avec les paramètres de BD locaux et toute le
reste de la configuration) on a l\'option de créer un fichier
**.env.local**. Ce fichier peut être un copie modifiée du fichier
**.env** ou, par exemple, on choisit la valeur **dev** pour
**APP\_DEV**.

Ce fichier

-   Est prioritaire sur le fichier **.env** mais ...

-   **est ignoré par GIT** (voir git.ignore dans le projet)

Ce mécanisme nous permet de travailler avec une configuration
particulière en local qui ne sera pas copié dans le serveur de
production (car uniquement **.env** se trouvera dans le serveur).

Vous pouvez utiliser aussi :

composer install \--no-dev \--optimize-autoloader

qui effacera les packages qui ne sont pas nécessaires en production.

[]{#_Toc4669739 .anchor}

Le Web Profiler
---------------

Comme nous avons mentionné ci-dessus, le **web profiler est un outil de
debugging** de Symfony. Si vous activez le mode **dev** et vous chargez
une page, la barre du debugger du **web** **profiler** sera affichée
**en bas de la fenêtre du navigateur** :

![](media/image5.png){width="4.975in" height="0.3290682414698163in"}

Le profiler vous permet d\'afficher beaucoup d\'information concernant
la requête qui a été faite au serveur. Pour que le profiler soit visible
on doit envoyer une page complète HTML depuis le controller. Il ne
suffit de faire \"return Response\". Le twig devra hériter du template
de base ou avoir ses propres balises html et body.

Afficher le contenu des variables avec dump
-------------------------------------------

Vous pouvez afficher le contenu des variables dans les vues et les
controllers grâce à la fonction **dump**.

Exemple :

**dump (\$livre)**

Cette fonction affiche le contenu complet de la variable d\'une façon
très complète. Utilisez-la au lieu de **var\_dump** à partir de
maintenant.

![](media/image6.png){width="2.5in" height="1.4035083114610674in"}

Les Services
============

Une application WEB utilise une **énorme quantité d\'objets pour
réaliser plein de fonctionnalités : connecter à une BD, envoyer un mail,
connecter avec une API à un autre site, écrire/lire de fichiers dans le
disque, etc\...**

Certains parmi ces objets seront définis par nous (en créant de
classes), certains se trouvent déjà dans la structure du framework et
d\'autres seront importés dans le projet.

Très **souvent on veut accéder à un de ces objets (qui réalise une
certaine fonctionnalité) depuis de différents lieus dans notre projet**.
On veut, par exemple, connecter à une BD depuis plein d\'actions qui ne
se trouvent même pas dans le même controller. Cela implique qu\'on
devrait avoir une sorte de structure de \"includes\" ou de \"autoload\"
qui nous permettent de réaliser ces actions facilement.

Symfony (et plein d\'autres frameworks) **fournit un système qui nous
permet d\'accéder facilement à ces objets qu\'on utilise dans plusieurs
emplacements de notre projet** : **le** **Service Container**.

En fait, un objet qui sera utilisé de manière générale depuis n\'importe
quelle localisation dans notre projet portera le nom de **Service**.
Pour cette raison, On va parler du \"service mailer\", du \"service
logger\", du \"service DB\" ou du \"service maps\".

Utilisations des services inclus dans Symfony
---------------------------------------------

**Symfony** **contient plein de services** **par défaut** même si pour
le moment nous ne les avons pas vraiment utilisés (au moins consciemment
!). Allez dans la console (dans le dossier de votre projet actuel) pour
afficher tous les services actifs ainsi que la description de leur
fonctionnalité :

php bin/console debug:autowiring \| more

(note : la commande \|more permet d\'arrêter l\'affichage à chaque page.
Ça n\'a rien à voir avec Symfony, c\'est un vieil outil de la console.
Tapez sur enter pour continuer à afficher le reste de services)

Nous pouvons utiliser ces services ainsi que rajouter nos propres
services (nous devons faire le code, bien sûr !)

La documentation sur les services et leur utilisation se trouve ici :

<https://symfony.com/doc/current/service_container.html>

Pour passer à la pratique, utilisons déjà un des services fournis par
Symfony. Commençons par utiliser un service qui nous permet de créer de
fichiers de **logs.**

#### Exemple : Utilisation du **service** Logger dans un controller

1.  **Créez un controller** ExemplesServicesController avec l\'assistant

2.  **Rajoutez une action** **utiliseLogger** (ignorez ou effacez
    l\'action index et sa vue)

3.  **Dans le prototype de l\'action, rajoutez un paramètre de la classe
    LoggerInterface** (n\'oubliez pas le **use**). Ceci **indiquera au
    Service Container** qu\'il doit **injecter un objet Logger dans
    notre action** (rappelez-vous de l\'injection de dépendances !!)
    pour qu\'il soit utilisable à l\'intérieur

4.  **Utilisez normalement le service.** Il n'y a pas besoin de créer
    une instance, car on la reçoit en paramètre ! Ici on montre deux
    exemples de base: info et error

Voici le code final du controller :

**namespace** App\\Controller;

**use**
Symfony\\Bundle\\FrameworkBundle\\Controller\\AbstractController;

**use** Symfony\\Component\\Routing\\Annotation\\Route;

**use** Psr\\**Log**\\LoggerInterface;

**use** Symfony\\Component\\HttpFoundation\\Response;

**class** ExemplesServicesController **extends** AbstractController

{

/\*\*

\* \@Route (\"/exemples/services/utilise/logger\")

\*/

**public** **function** utiliseLogger(LoggerInterface \$monLogger){

\$monLogger-\>info (\"On utilise le logger, c\'est super!\");

\$monLogger-\>error (\"Hey! une erreur s\'est produite!\");

**return** **new** Response (\"J\'ai fait mon boulot de logger ce qu\'il
faut!\");

}

}

Pour vérifier que le log a été effectué, ouvrez le fichier
*/var/log/dev.log* de votre projet

On aurait pu rajouter d\'autres services si on avait eu besoin dans le
prototype de l\'action. Il suffit de les séparer par virgules. Cette
\"magie\" est réalisé grâce au système de **autowire** de Symfony, dont
la configuration se trouve dans **config/services.yaml**

Si vous avez besoin de réaliser du logging dans votre application, vous
avez plus d\'info sur le sujet ici :

<https://symfony.com/doc/current/logging.html>

#### Exercice :

Symfony contient un service qui nous permet de gérer la session,
**SessionInterface**. Appliquez la même procédure que dans l\'exemple
précédant pour l\'obtenir. Dans votre action, créez une variable de
session et affichez sa valeur. Le mécanisme de base de la session est
simple : pour créer une variable de session on utilise la méthode set
(clé, valeur) et pour la lire on utilise la méthode get (clé) de
l\'objet Session

Création de nos propres services
--------------------------------

Nous avons mentionné **qu\'on peut transformer nos propres objets en
services**. Pour ce faire, on doit juste créer notre classe dans le
dossier **/src/Services** (à créer s\'il n\'existe pas encore) et suivre
la même procédure que dans les exemples précédents.

#### Exemple : Nous voulons un service permettant d\'obtenir toutes les permutations possibles des éléments d\'un array de noms (permutations = combinaisons où l'ordre compte)

1.  **Créez le dossier** **/src/Services** (s\'il n\'existe pas déjà)
    qui contiendra tous nos services

/src/Services

2.  **Créez la classe qui réalise la fonctionnalité à l\'intérieur de ce
    dossier (le service!)**

Voici un code possible, où la méthode *permutations* reçoit un array et
renvoie un autre contenant le résultat :

// src/Services/Statistiques.php

**namespace** App\\Services;

**class** Statistiques {

// calcule toutes les permutations possibles de valeurs d\'un array

/\*\*

\*

\* \@param type \$items

\* \@param type \$perms

\* \@return type array (toutes les permutations - comibinaisons

\* ou l\'ordre compte)

\*/

**function** permutations(\$items, \$perms = **array**( )) {

**if** (**empty**(\$items)) {

\$return = **array**(\$perms);

} **else** {

\$return = **array**();

**for** (\$i = **count**(\$items) - 1; \$i \>= 0; \--\$i) {

\$newitems = \$items;

\$newperms = \$perms;

**list**(\$foo) = **array\_splice**(\$newitems, \$i, 1);

**array\_unshift**(\$newperms, \$foo);

\$return = **array\_merge**(\$return, \$this-\>permutations(\$newitems,
\$newperms));

}

}

**return** \$return;

}

}

3.  Créez une action dans un controller (ici *ExemplesPropreService*)
    pour utiliser votre service, tel qu\'on a fait dans les sections
    précédentes. Symfony le reconnaitra directement !

// src/Controller/ExemplesPropreServiceController

**use** App\\Services\\Statistiques;

**class** ExemplesPropreServiceController **extends** AbstractController

{

/\*\*

\* \@Route (\"/exemples/propre/service/utilise/statistiques\");

\*/

**public** **function** utiliseStatistiques (**Statistiques
\$mesStats**){

\$arrayNoms = \[\'Lucas\',\'Jean\',\'Norah\'\];

\$permutationsNoms = \$mesStats-\>permutations(\$arrayNoms);

**return** \$this-\>render
(\'exemples\_propre\_service/utilise\_statistiques.html.twig\',
\[\'permutationsNoms\'=\> \$permutationsNoms\]);

}

}

#### Exercice : Créez à partir de zéro un service qui dit bonjour et une action pour montrer son fonctionnement

Injecter les services dans le controller
----------------------------------------

Nous pouvons injecter de services directement dans le controller en
utilisant son constructeur. Voici un exemple équivalent au code
précédant.

#### Exemple : injection d\'un service dans le constructeur

// src/Controller/ExemplesPropreServiceInjectionController.php

**class** ExemplesPropreServiceInjectionController **extends**
AbstractController

{

**private** \$mesStats;

// on injecte le service diréctement dans le constructeur du controller

**public** **function** **\_\_construct (Statistiques \$mesStats)**{

\$this-\>mesStats = \$mesStats;

}

/\*\*

\* \@Route
(\"/exemples/propre/service/injection/utilise/statistiques\");

\*/

**public** **function** utiliseStatistiques (){

\$arrayNoms = \[\'Lucas\',\'Jean\',\'Norah\'\];

\$permutationsNoms = \$this-\>mesStats-\>permutations(\$arrayNoms);

**return** \$this-\>render
(\'exemples\_propre\_service\_injection/utilise\_statistiques.html.twig\',
\[\'permutationsNoms\'=\> \$permutationsNoms\]);

}

}

Cette méthode devient indispensable quand **on veut utiliser un service
dans un autre service, car la seule méthode où on pourra l\'injecter
sera dans le constructeur !** On montre un exemple ci-dessous de ce cas
de figure.

[]{#_Toc4669756 .anchor}

Injection de paramètres dans le service (I)
-------------------------------------------

Nous pouvons rajouter de paramètres aux services en utilisant
*services.yaml*. Dans ce fichier on configure la manière dont les
services deviendront accessibles dans nos controllers.

#### Exemple : un service Bonjour qui affiche \"bonjour à tous\" dans la langue parametrée dans services.yaml

D\'abord on doit créer le service. Si on veut que le service soit
paramétré **on rajoute un paramètre dans le constructeur** **et on le
stocke dans une propriété** (on peut avoir autant de paramètres qu\'on
veut) :

// App/Services/Bonjour.php

**namespace** App\\Services;

**class** Bonjour {

**private** \$langue;

**public** **function** **\_\_construct** (\$langue){

\$this-\>langue = \$langue;

}

// service contenant un paramètre

**public** **function** obtenirMessage (){

// array fake\... juste pour essayer le service

\$messages = \[\'fr\' =\> \'Bonjour à tous!!\',

\'en\' =\> \'Hello everybody!!\'

\];

// on obtient le paramètre du propre service

\$langue = \$this-\>langue;

**return** (\$messages\[\$langue\]);

}

}

On doit définir le parametre dans *services.yaml* :

App\\Services\\Bonjour:

arguments:

\$langue: \'fr\'**namespace** App\\Services;

Finalement on peut utiliser le service dans un controller. Ici on a
injecté le service dans le controller en suivant la méthode de la
section precedante :

// src/Controller/ExemplesServicesParamsController.php

**class** ExemplesServicesParamsController **extends**
AbstractController

{

**private** \$bonjour;

// on utilise la méthode d\'injection du service dans le controller

**public** **function** **\_\_construct** (Bonjour \$bonjour){

\$this-\>bonjour = \$bonjour;

}

/\*\*

\* \@Route (\"/exemples/propre/service/params\");

\*/

**public** **function** utiliseBonjour(){

**return** **new** Response (\$this-\>bonjour-\>obtenirMessage());

}

}

> Si on veut qu\'un paramètre soit utilisé par tous les services on a
> qu\'a le rajouter à la section ***parameters*** qui se trouve tout en
> haut du fichier *services.yaml*

Utiliser un service dans un autre service
-----------------------------------------

Si nous voulons utiliser un service dans un autre service on peut
uniquement les injecter dans le constructeur (on ne peut pas injecter
l\'objet Logger dans une autre méthode, tel que \"permutations\"). **Si
on veut utiliser un service dans un autre on est obligé de les injecter
dans le constructeur. Ce n\'est pas possible de les injecter dans une
autre méthode.** C\'est uniquement dans le controller où on peut
injecter les services dans n\'importe quelle méthode.

#### **Exemple :** utiliser Logger dans le service Statistiques

// src/Services/StatistiquesLog.php

**namespace** App\\Services;

**use** Psr\\**Log**\\LoggerInterface;

**class** StatistiquesLog {

**private** \$logger;

// injection dans le constructeur

**function** **\_\_construct** (**LoggerInterface** \$logger){

\$this-\>logger = \$logger;

}

**function** permutations(\$items, \$perms = **array**( )) {

**if** (**empty**(\$items)) {

\$res = **array**(\$perms);

} **else** {

\$res = **array**();

**for** (\$i = **count**(\$items) - 1; \$i \>= 0; \--\$i) {

\$newitems = \$items;

\$newperms = \$perms;

**list**(\$foo) = **array\_splice**(\$newitems, \$i, 1);

**array\_unshift**(\$newperms, \$foo);

\$res = **array\_merge**(\$res, \$this-\>permutations(\$newitems,
\$newperms));

}

}

// on utilise le service de log

**\$this-\>logger-\>info** (\"De permutations ont été calculées\");

**return** \$res;

}

}

// src/Controller/ExemplesServiceUtiliseService.php

**class** ExemplesServiceUtiliseService **extends** AbstractController

{

**private** \$mesStats;

// Le service StatistiquesLog utilise Logger

**public** **function** **\_\_construct** (StatistiquesLog \$mesStats){

\$this-\>mesStats = \$mesStats;

}

/\*\*

\* \@Route (\"/exemples/propre/service/utilise/service\");

\*/

**public** **function** utiliseStatistiques (){

\$arrayNoms = \[\'Lucas\',\'Jean\',\'Norah\'\];

// calculera les permutations et créera une ligne de log

\$permutationsNoms = \$this-\>mesStats-\>permutations(\$arrayNoms);

**return** \$this-\>render
(\'exemples\_service\_utilise\_service/utilise\_statistiques.html.twig\',
\[\'permutationsNoms\'=\> \$permutationsNoms\]);

}

}

Injection de paramètres dans le service (II)
--------------------------------------------

> Dans certains cas **nous utilisons un service dans un autre et le
> premier doit être paramétré**.

#### **Exemple :** rajouter l\'envoi d\'un mail dans notre service de Statistiques

Le service StatistiquesLogMail envoie un mail en plus de créer une ligne
de log quand on fait appel à la fonction de permutations.

Installez d\'abord le service de mail (on le configura plus tard) :

composer require symfony/swiftmailer-bundle

Dans ce cas, le service a besoin d\'un ou plusieurs paramètres pour être
configuré (ici on va considérer le paramètre **\$adresse** le
destinataire du mail qui sera, par défaut, \"yoyo\@touloulou.com\")

Voici notre service, qui inclut maintenant l\'envoi d\'un mail. On a dû
injecter le Mailer dans le constructeur et on a décidé d\'envoyer
l\'adresse mail en paramètre.

// src/Services/StatistiquesLogMail.php

**namespace** App\\Services;

**use** Psr\\**Log**\\LoggerInterface;

**use** Swift\_Mailer;

**class** StatistiquesLogMail {

**private** \$logger;

**private** \$mailer;

**private** \$adresse;

**function** **\_\_construct** (LoggerInterface \$logger,
**Swift\_Mailer \$mailer**, \$**adresse**){

\$this-\>logger = \$logger;

\$this-\>mailer = \$mailer;

**\$this-\>adresse = \$adresse; // spécifiée dans services.yaml,porte le
même nom**

}

**function** permutations(\$items, \$perms = **array**( )) {

.

.

.

// on utilise le service de log

\$this-\>logger-\>info (\"De permutations ont été calculées\");

// on envoie un mail

\$message = (**new** \\Swift\_Message)

-\>setTo (**\$this-\>adresse**);

// on doit envoyer ici le mail après avoir configuré le service

// https://symfony.com/doc/current/email.html\#configuration

// dump (\$message);

// die();

**return** \$res;

}

}

mais **cette solution ne suffit pas. Inclure le paramètre parmi les
paramètres du constructeur provoque cette erreur :**

![](media/image7.png){width="6.383333333333334in"
height="0.6798611111111111in"}

**C\'est tout à fait logique, car quand on fait appel à notre service
depuis le controller on n\'indique pas ce paramètre extra.** **Le
service principal est juste injecté dans le constructeur sans
paramètres** :

// /src/controller/ExemplesPropreServiceInjectionParamsController.php

**class** ExemplesPropreServiceInjectionParamsController **extends**
AbstractController

{

**private** \$mesStats;

// on injecte le service diréctement dans le constructeur du controller,

// sans paramètres!

**public function \_\_construct (StatistiquesLogMail \$mesStats)**{

\$this-\>mesStats = \$mesStats;

}

.

.

.

}

**Comment fixer alors l\'adresse du mail si on ne peut pas l\'envoyer en
paramètre au service lors sa création ?**

Nous pouvons configurer de paramètres particulières de nos services dans
le fichier **services.yaml** :

\# add more service definitions when explicit configuration is needed

\# please note that last definitions always \*replace\* previous ones

App\\Services\\StatistiquesLogMail:

arguments:

\$adresse: \"yoyo\@gmail.com\"

**Le paramètre doit porter le même nom que celui qu\'on a rajouté dans
le constructeur, autrement on obtient une erreur.**

Si on voulait changer l\'adresse on peut toujours créer de méthodes pour
ce faire dans notre service, rien nous empêche de créer une méthode pour
ce faire dans notre service. On vient d\'arranger le problème d\'avoir
la valeur lors la création du service. En plus, le code reste plus
propre car les paramètres de tous nos services seront centralisés dans
**services.yaml**

Cookies
=======

Créer de cookies dans Symfony est très simple avec la classe Cookie. On
doit :

1)  Créer l\'objet **Cookie** dans une action (spécifier son nom, sa
    valeur et le moment d\'expiration)

2)  Créer un objet **Response**

3)  Attacher le cookie à l\'objet Réponse avec **setCookie**

4)  Envoyer la réponse au client avec **send**

Voici un exemple complet : la première action crée le cookie. La
deuxième action lit la valeur du cookie et l\'efface. Juste pour pouvoir
afficher sa valeur on l\'envoie à une vue. Vous pouvez aussi afficher la
valeur de la cookie en utilisant la console du navigateur (onglet
Stockage dans Firefox).

// src/Controller/CookiesController.php

**class** CookiesController **extends** AbstractController

{

/\*\*

\* \@Route(\"/cookies/creer/cookie\")

\*/

**public** **function** creerCookie()

{

\$cookie = **new** Cookie(

\'unCookie\',

\'chocolat\',

**time**() + (50 \* 24 \* 60 \* 60)); // le temps est exprimé en

// secondes, ici 50 jours à partir de cet instant

\$reponse = **new** Response();

\$reponse-\>headers-\>**setCookie** (\$cookie); // rattache la cookie

//aux en-têtes http

\$reponse-\>send();

// return \$reponse;

**return** \$this-\>render (\'cookies/creer\_cookie.html.twig\');

}

/\*\*

\* \@Route(\"/cookies/afficher/effacer/cookie\")

\*/

**public** **function** afficherEffacerCookie (Request \$req){

\$valeur = \$req-\>cookies-\>get (\'unCookie\'); // on stocke avant
d\'effacer

// pour l\'envoyer à la vue

\$res = **new** Response();

\$res-\>headers-\>clearCookie(\'unCookie\');

\$res-\>send();

**return** \$this-\>render
(\'cookies/afficher\_effacer\_cookie.html.twig\', \[\'valeurCookie\' =\>
\$valeur\]);

}

}

Session
=======

Nous pouvons créer des variables de session juste en injectant un objet
SessionInterface dans une action grâce aux méthodes **set** et **get**.
On peut effacer la valeur d\'une variable de session en utilisant
**remove** ou la totalité de la session en utilisant **clear**. La
méthode **has** nous permet de savoir si une variable existe dans la
session.

Voici un exemple complet :

// src/Controller/SessionController.php

**class** SessionController **extends** AbstractController

{

/\*\*

\* \@Route(\"/session/creer/session\")

\*/

**public** **function** creerSession(SessionInterface \$s)

{

\$s-\>**set**(\'nom\', \'Pepita\');

**return** \$this-\>render (\'session/creer\_session.html.twig\');

}

/\*\*

\* \@Route(\"/session/afficher/session\")

\*/

**public** **function** afficherSession (SessionInterface \$s){

**if** (\$s-\>**has**(\'nom\')){

// on peut l\'obtenir et l\'envoyer à la vue

\$val = \$s-\>**get** (\'nom\');

**return** \$this-\>render (\'session/afficher\_session.html.twig\',
\[\'valeurSession\'=\>\$val\]);

}

**else** {

**return** **new** Response (\"Le nom n\'a pas été stocké dans la
session\");

}

}

/\*\*

\* \@Route(\"/session/effacer/variable/session\")

\*/

**public** **function** effacerVariableSession (SessionInterface \$s){

**\$s-\>remove**(\'nom\'); // efface la variable de session

// **\$s-\>clear();** efface la totalité de la session!

**return** \$this-\>render
(\'session/effacer\_variable\_session.html.twig\');

}

}

Obtenir de données du GET et POST
=================================

Pour obtenir de données d\'une requête **GET** ou **POST** on utilise :

\$request-\>query-\>get (\"cleParametre\");

#### Exemple : obtention de valeurs des paramètres de l\'URL ou requête GET

Cette action lira les valeurs d\'une requête GET contenant de paramètres
dans la URL :

<http://localhost:8000/exemple/get?nom=frigo&categorie=cuisine>

// src/Controller/GetPostController.php

**class** GetPostController **extends** AbstractController

{

/\*\*

\* \@Route(\"/exemple/get\", name=\"get\")

\*/

**public** **function** exempleGet(Request \$req)

{

\$nom = \$req-\>query-\>get (\"nom\");

\$categorie = \$req-\>query-\>get (\"categorie\");

// dump (\$req-\>query);

// die();

**return** **new** Response (\"nom :\" . \$nom . \"\<br\>categorie: \" .
\$categorie . \"\<br\>\");

}

}

Observez **la différence entre obtenir un paramètre tu GET et obtenir un
paramètre du router : dans les cas du GET on obtient d\'abord le
\"query\" (ParameterBag) contenant tous les paramètres.**

Pour obtenir les données directement du POST on utilise :

\$request-\>request-\>get (\"cleParametre\");

Le modèle : création d\'entités et de la BD
===========================================

Dans une application web, les classes qui contiennent les données de
l\'application s\'appellent **entités** (les classes de notre diagramme
de classes) et on doit les définir.

Présentation de Doctrine
------------------------

Pour créer la structure de données d\'une application web on va utiliser
un ensemble de librairies de PHP qui s\'appelle **Doctrine**. Doctrine
est constitué d\'un **ORM** (Objet Relational Mapping) et d\'un **DBAL**
(Database Abstraction Layer).

**L\'ORM** permet de créer une **correspondance entre les classes** de
notre application (qui est orientée objet) et **une base de données**
(constitué de tableaux)

Ex: notre classe *Evenement* sera représentée dans la BD avec un tableau
*evenement*

Le **DBAL** est un ensemble de librairies basées sur PDO qui facilite
l\'accès à la BD, tant à sa structure comme aux données.

Ex: on peut utiliser une méthode *select()* qui nous renverra des
données de la BD sous la forme d\'objets et pas d\'array. On ne doit
plus faire une requête à la main \"SELECT \* FROM ....\" dans les
requêtes les plus habituelles

**Documentation de Doctrine :
<https://symfony.com/doc/current/doctrine.html>**

L\'utilisation de base de Doctrine est simple. On doit réaliser trois
étapes :

1.  Définir les propriétés et les relations de **chaque entité** en
    utilisant des annotations, XML, YAML ou PHP

Ex. : définir les propriétés des entité *Realisateur* et *Film* et le
type de lien existant entre elles (un à plusieurs, plusieurs à
plusieurs, un à un...)

2.  Demander à Doctrine de **créer le code PHP de base de ces entités**
    (nos classes, set et get inclus)

3.  Demander à Doctrine de **créer la base de données contenant ces
    entités** et ses relations

La bonne nouvelle est que les pas 2 et 3 se font automatiquement !
Doctrine génère le code des classes, les tableaux dans la BD, les
relations... et en plus en peut tout mettre à jour juste en changeant
les fichiers de définition des entités !

Une fois crée le code des entités et le schéma de la BD, nous pouvons
accéder en utilisant un objet gestionnaire de Doctrine (entity manager).
Doctrine fournit les méthodes pour pouvoir **obtenir les données de la
BD sous forme d\'objets** (au lieu d\'arrays associatifs) et **stocker
des objets dans la BD** (qui seront stockés sous la forme d\'un
enregistrement, une ligne dans un tableau).

On va voir comment faire tout ça par la suite dans un nouveau projet
**ProjetModelSymfony**

symfony new \--full ProjetModelSymfony

Créez un controller ExemplesModele vous-mêmes et une action de
bienvenue. Suivez le guide rapide du création d\'un projet (Annexe 1)
pour le faire.

Documentation de Doctrine liée à Symfony :

<https://symfony.com/doc/current/doctrine.html>

<http://docs.doctrine-project.org/projects/doctrine-orm/en/latest/reference/working-with-objects.html>

Configuration de Doctrine et des paramètres de la BD
----------------------------------------------------

1.  **Rajoutez** les librairies de **Doctrine** à votre projet

> composer require symfony/orm-pack
>
> composer require symfony/maker-bundle \--dev

2.  **Adaptez les paramètres de la BD** dans **le fichier .env** à votre
    serveur et nom de base de données

> DATABASE\_URL=mysql://db\_user:db\_password\@127.0.0.1:3306/db\_name
>
> On va créer une base de données **bibliotheque**. Dans notre cas le
> password est vide, alors on obtient :
>
> DATABASE\_URL=mysql://root:\@127.0.0.1:3306/**bibliotheque**
>
> Si vous engagez les services d\'un hébergeur vous devez mettre ici ses
> paramètres de connexion

3.  **Créez la BD** **vide** depuis la console (dans le dossier de votre
    projet)

> php bin/console doctrine:database:create

Création des entités et mise à jour de la BD
--------------------------------------------

On va créer une première entité et générer son code.

1.  **Lancez l\'assistant de création d\'entités :**

> php bin/console make:entity
>
> L\'assistant nous demandera le **nom de l\'entité** (*Livre*) et **ses
> propriétés** (*titre, prix, description, datePublication*). D\'abord
> il demande pour le nom de la propriété et puis pour le type. Les types
> de base (affichables en tapant \"?\") sont *string (255), decimal (8
> ,2), text (400), datetime.* Pour certains types il nous demande aussi
> la taille.
>
> L\'assistant créera les fichiers */Entity/Livre.php* (la classe !) et
> */Repository/LivreRepository.php*. **Si vous ratez la création de
> l\'entité** sortez de l\'assistant (CTRL-C), effacez les fichiers
> */Entity/Livre.php* et */Repository/LivreRepository.php* et
> recommencez.
>
> Ouvrez le fichier Livre.php et observez qu\'il s\'agit d\'une classe
> normale qui représente un livre et qui **contient des annotations qui
> décrivent certains de caractéristiques des champs**. **Ces annotations
> seront utilisées par Doctrine pour générer automatiquement la base de
> données selon les types de notre choix**. Pour plus d\'information sur
> les types de doctrine, allez sur :
>
> <http://docs.doctrine-project.org/projects/doctrine-dbal/en/latest/reference/types.html>
>
> L\'assistant est juste un outil pour nous faciliter la tâche mais vous
> pouvez très bien créer/éditer les fichiers par vous-mêmes
> (rajouter/effacer des champs)

2.  **Réaliser la migration de la BD**

La BD est actuellement vide. Nous voulons que Doctrine crée un tableau
\"Livre\" à partir de notre entité. De manière plus générale, **nous
voulons que Doctrine mette à jour la BD pour qu\'elle reflète les
changements dans nos entités** **(nom des entités, types des champs,
relations, etc...). Ces mises à jours, assez habituelles dans un projet,
s\'appellent migrations.**

Nous allons réaliser cette procédure en deux étapes très simples :

1)  **Créer ou mettre à jour un historique de migrations** (tableau dans
    la BD) et un fichier qui contient le code pour mettre à jour la BD
    (dans src/Migrations)

> php bin/console make:migration

2)  **Mettre à jour la BD en lançant ce code** (ceci créera déjà notre
    tableau \"Livre\")

> php bin/console doctrine:migrations:migrate

**Note :** Si vous le souhaitez, vous pouvez aussi créez les entités par
vous-mêmes à la main, ou utiliser d\'autres systèmes de notations au
lieu des annotations tel que XML

<https://www.doctrine-project.org/projects/doctrine-orm/en/latest/reference/basic-mapping.html>

Rajouter/effacer des propriétés d\'une entité
---------------------------------------------

Nous pouvons modifier nos entités facilement. Nous pouvons éditer le
fichier à notre aise ou lancer à nouveau make:entity si on veut juste
rajouter de nouvelles propriétés. Si on édite le fichier de l\'entité
(ici Livre.php) **à la main, on doit absolument créer les getters,
setters et annotations pour les nouvelles propriétés**.

Dans tous les cas vous devez toujours **migrer la BD** en lançant les
deux commandes déjà mentionnées :

php bin/console make:migration

php bin/console doctrine:migrations:migrate

**Si on crée une propriété à la main**, cette commande créera les
getters et les setters pour nous

php bin/console make:entity --regenerate

**Important :** n\'oubliez pas de rajouter le namespace au nom de la
classe **(ex : App\\Entity\\Livre)**

**Si on efface une propriété il ne faut pas oublier d\'effacer aussi ses
get et set, Symfony ne le fera pas automatiquement**

On peut utiliser aussi la commande :

php bin/console make:entity \--overwrite

si on veut recréer tous les getters et les setters pour toutes les
propriétés!

#### Exercices :

1)  Créez une nouvelle propriété *isbn* et migrez la BD

2)  Créez une nouvelle propriété *dateEdition* et migrez la BD.
    Supprimez-le et assurez-vous que la BD est toujours cohérente avec
    votre code

3)  Créez l\'entité Client (nom, prénom, email) et Exemplaire (état)

4)  Créez l\'entité Auteur (nom, nationalité)

Le modèle : les relations 
=========================

Nous sommes capables maintenant de générer les tableaux qui
correspondent à nos entités. Cette section est consacrée à
l\'implémentation des relations d\'un schéma.

Vous trouverez les exemples décrits ci-dessous dans les projets
**projetModelSymfony** et **projetRelationsSymfony** (regardez le code
des entités !)

Documentation:
<https://symfony.com/doc/current/doctrine/associations.html>

Relation Many-To-One
--------------------

Considérons ce schéma Merise (MCD - base de données relationnelles) :

![](media/image8.png){width="4.976733377077865in"
height="1.4166666666666667in"}

Qui équivaut à ce schéma UML (POO) :

![](media/image9.png){width="4.564660979877515in"
height="1.6574070428696412in"}

La transformation de ce modèle nous donne, si on la réalise à la main :

-   Dans la BD : Un tableau Livre qui ne change pas + un tableau
    Exemplaire qui contient une colonne id (qu\'on va appeler
    *livre\_id* pour faciliter la lecture)

-   Dans le code : Une classe Livre qui ne change pas (ou qui a un array
    d\'Exemplaires si la relation est bidirectionnelle) + une classe
    Exemplaire qui contient un objet Livre

**Nous pouvons créer le code et modifier la BD à la main mais Doctrine
va le faire pour nous**.

**Objectif :**

Implémenter la partie correspondante aux associations dans le code des
entités et créer les relations dans la BD

**Procédure :**

1.  **Rajoutez une propriété Many-to-One dans l\'entité correspondante
    en utilisant l\'assistant** (ici c\'est l\'entité *Exemplaire*)

> La propriété est du type **relation**, **ManyToOne.**
>
> Dans ce cas, la propriété s\'appellera ***livre*** et sera un objet de
> la classe Livre*.* On souhaite aussi rajouter une propriété et de
> méthodes dans Livre pour créer une association bidirectionnelle (pas
> seulement pouvoir obtenir le Livre qui correspond à un exemplaire mais
> aussi tous les exemplaires d\'un livre !). Cette propriété
> s\'appellera **exemplaires** et sera une collection qui contient tous
> les exemplaires d\'un livre.

![](media/image10.png){width="6.383333333333334in"
height="5.1402777777777775in"}

![](media/image11.png){width="6.383333333333334in"
height="2.0236111111111112in"}

C\'est fait ! Nos entités sont mises à jour (explication dans la section
suivante)

**\
**

2.  **Migrez** la BD pour que les relations soient créées dans la BD

php bin/console make:migration

php bin/console doctrine:migrations:migrate

![](media/image12.png){width="6.383333333333334in"
height="0.38819444444444445in"}

3.  **Vérifiez** que la BD a été mise à jour

> Observez les changements dans le/les tableaux !

Explication du code généré par l\'assistant
-------------------------------------------

> Les opérations réalisées ont généré ce code dans les entités
> *Exemplaire* et *Livre*. Dans **Exemplaire.php** :

.

.

.

/\*\*

\* \@ORM\\ManyToOne(targetEntity=\"App\\Entity\\Livre\",
inversedBy=\"exemplaires\")

\*/

**private** \$livre;

.

.

.

**public** **function** getLivre(): ?Livre

{

**return** \$this-\>livre;

}

**public** **function** setLivre(?Livre \$livre): self

{

\$this-\>livre = \$livre;

**return** \$this;

}

et dans **Livre.php** :

/\*\*

\* \@ORM\\OneToMany(targetEntity=\"App\\Entity\\Exemplaire\",
mappedBy=\"livre\")

\*/

**private** \$exemplaires;

.

.

.

/\*\*

\* \@return Collection\|Exemplaire\[\]

\*/

**public** **function** getExemplaires(): Collection

{

**return** \$this-\>exemplaires;

}

**public** **function** addExemplaire(Exemplaire \$exemplaire): self

{

**if** (!\$this-\>exemplaires-\>contains(\$exemplaire)) {

\$this-\>exemplaires\[\] = \$exemplaire;

\$exemplaire-\>setLivre(\$this);

}

**return** \$this;

}

**public** **function** removeExemplaire(Exemplaire \$exemplaire): self

{

**if** (\$this-\>exemplaires-\>contains(\$exemplaire)) {

\$this-\>exemplaires-\>removeElement(\$exemplaire);

// set the owning side to null (unless already changed)

**if** (\$exemplaire-\>getLivre() === \$this) {

\$exemplaire-\>setLivre(**null**);

}

}

**return** \$this;

}

**Note importante** : ce code est la seule chose qui change dans la
classe originale. Si vous **avez fait des erreurs** pendant la création
des associations avec l\'assistant, vous devez **effacer ces lignes et
recommencez la création** des associations (pas créer les entités depuis
zéro !)

**On a créé une association bidirectionnelle de Many-to-One.** Observez
que dans Livre il y aura une collection d\'exemplaires et que dans
Exemplaire aura un objet Livre. **Doctrine a généré** :

-   Les **annotations** pour indiquer le type d\'association entre les
    deux classes (on utilise *inversedBy* du côté *plusieurs* et
    *mappedBy* du coté *un*)

-   Les **méthodes** get et set pour accéder aux objets des deux côtés
    de l\'association. Dans le cas de la collection, de méthodes pour
    rajouter un élément à la collection et pour l\'effacer de la
    collection.

> Notez que Doctrine efface la \"s\" quand il crée les méthodes ! Notre
> propriété s\'appelle **exemplaires** mais les méthodes crées
> s\'appellent par exemple removeExemplaire au lieu de removeExemplaires
> !

Observez aussi que **les méthodes spécifient les types de retour**.
**Collection** est une interface de PHP qui assure que les objets qui
l\'implémentent soient Countables, Transversables et qu\'on puisse les
encoder en JSON avec json\_encode.

**self** est une manière d\'accéder au nom de la classe (ça aurait pu
être remplacé par le nom de la classe dans chaque cas où il apparait
dans le code)

**Le code est généré, ainsi que les tableaux et les relations.**

Dans la base de données il y aura une colonne *livre\_id* dans
Exemplaire. Le tableau Livre par contre ne changera pas car on ne peut
pas mettre une collection d\'exemplaires dans une BD relationnelle ! ;)

**\
**

#### Exercices :

1)  On va considérer qu\'un Client de la bibliothèque a une Adresse
    (rue, numero, codePostal, ville, pays) et qu\'une adresse peut
    correspondre à plusieurs clients. Créez la classe Client pour
    représenter les clients et la classe Adresse pour représenter
    l\'adresse de chaque client. Implémentez-la en utilisant Doctrine
    tel qu\'on vient de faire

2)  Implementez ce diagramme

![](media/image13.png){width="6.383333333333334in" height="4.1625in"}

3)  Prenez des exemples du cours d\'UML et implémentez les entités avec
    Doctrine dans un nouveau projet. Si vous êtes en train de planifier
    un projet pour vous, prenez plusieurs entités de votre schéma et
    implémentez-les avec Doctrine. Implementez les associations aussi

Relation Many-To-Many
---------------------

Considérez le schéma MCD suivant :

![](media/image14.png){width="5.147684820647419in"
height="1.380738188976378in"}

Équivalent à ce schéma UML :

![](media/image15.png){width="4.683333333333334in"
height="2.508928258967629in"}

Nous sommes dans une association de plusieurs à plusieurs qui contient
d\'attributs d\'association. Symfony a son propre mécanisme pour
implémenter ces associations (\<many-to-many\>), toutefois on ne
l\'utilisera pas ce mécanisme **parce qu\'il ne permet pas d\'inclure
d\'attributs dans l\'association !**

Mais la solution est simple : on peut transformer l\'association dans
deux associations de one-to-many :

![](media/image16.png){width="5.055555555555555in"
height="1.3044969378827647in"}

#### Exercice : implémentez vous-même ce modèle pour avoir la relation entre les Clients et les exemplaires !

Si vous êtes toujours intéressé à implémenter une association de
plusieurs à plusieurs **sans attributs**, suivez les exemples de la
documentation de Doctrine :

<https://www.doctrine-project.org/projects/doctrine-orm/en/latest/reference/association-mapping.html#many-to-many-bidirectional>

Voici un exemple :

Imaginons qu\'on a juste besoin de connaitre qui sont les clients qui
ont emprunté un exemplaire et vice-versa. Nous aurions ce schéma :

![](media/image17.png){width="4.462962598425197in"
height="1.2751323272090989in"}

1.  Créez les entités Client et Exemplaire **dans un autre projet** pour
    ne pas détruire votre schéma !

2.  Suivez la même procédure que pour les relations Many-to-One mais
    choisissez Many-to-Many

Observez les changements dans le code des entités ainsi que dans le
schéma de la BD

Relation One-To-One 
-------------------

Ces types de relations sont moins fréquentes, mais si vous avez besoin
de les réaliser la documentation se trouve ici :

<https://www.doctrine-project.org/projects/doctrine-orm/en/latest/reference/association-mapping.html#one-to-many-bidirectional>

**L\'implémentation en soit est facile. Voici un exemple :**

Considérez par exemple qu\'un client peut avoir un avatar (un fichier
d\'image) et qu\'un avatar appartient à un seul client. On ne veut pas
stocker les fichiers dans le tableau client, on veut carrément une autre
entité.

1.  Créez l\'entité Avatar

2.  Suivez la même procédure que pour les relations Many-to-One mais
    choisissez One-To-One

Observez les changements dans le code des entités ainsi que dans le
schéma de la BD

Relation récursive (self-association)
-------------------------------------

### Relation récursive d\'un à plusieurs

Nous pouvons aussi implémenter une entité qui a une référence à
soi-même. L\'exemple le plus typique est celui des parents-enfants ou
chef-employé. On peut modéliser ce cas en utilisant une relation
one-to-many dans la même entité.

Considérons un magasin qui organise les produits en catégories. Une
catégorie peut avoir des sous-catégories mais une sous-catégorie
appartient uniquement à une catégorie.

![](media/image18.png){width="2.65in" height="1.8806452318460192in"}

1.  Créez l\'entité Categorie

2.  Créez une propriété **sousCategories** du type relation (OneToMany).
    La propriété complementaire sera categorieParent

Observez les changements dans le code des entités ainsi que dans le
schéma de la BD

![](media/image19.png){width="1.6083333333333334in"
height="0.8976738845144357in"}

On obtient un seul tableau dans la BD et un champ extra qui indique la
relation (à cause du one-to-many).

Dans le code PHP (Habitant.php) on obtient deux listes, une pour les
sous-catégories et une autre pour les catégories-parent. Aucun tableau
extra sera généré.

### Relation récursive de plusieurs à plusieurs

> Si la relation est de **plusieurs à plusieurs sans attributs** (ex. :
> une Personne supervise plusieurs Personnes et elle est à son tour
> Supervisé par d\'autres Personnes), on peut utiliser une **relation
> many-to-many** (si on n\'a pas d\'attributs dans la relation.
>
> ![](media/image20.png){width="2.4166666666666665in"
> height="1.833332239720035in"}

1.  Créez l\'entité Employe

2.  Créez une propriété **supervises** (attention au pluriel) du type
    relation (ManyToMany). La propriété complementaire sera
    **superviseurs**

3.  Observez le code et le schéma généré

> ![](media/image21.png){width="3.5490201224846896in"
> height="0.5478740157480315in"}

**\
**

**Si la relation avait eu des attributs**, on aurait créé deux entités
(Personne et Supervision) nous-mêmes et on aurait appliqué la méthode de
many-to-one.

Voici un exemple (on rajoute le suffixe MMA pour ne pas écraser les
autres entités).

1.  Créez l\'entité PersonneMMA

2.  Créez l\'entité SupervisionMMA

3.  Créez une propriété dans SupervisionMMA du type relation qui porte
    le nom **superviseur** et pointe vers l\'entité **PersonneMMA**
    (ManyToOne). La propriété complementaire sera
    **supervisionsSuperviseur**

4.  Créez une propriété dans SupervisionMMA du type relation qui porte
    le nom **supervise** et pointe vers l\'entité **PersonneMMA**
    (ManyToOne). La propriété complementaire sera
    **supervisionsSupervise**

5.  Observez le code et le schéma généré

![](media/image22.png){width="3.7916666666666665in"
height="0.8925295275590551in"}

Sur les associations récursives :

<http://www.tomjewett.com/dbdesign/dbdesign.php?page=recursive.php>

Le modèle : accès à la BD avec Doctrine
=======================================

Documentation: <https://symfony.com/doc/3.3/doctrine.html>

SELECT
------

Créez à la main quelques enregistrements dans la base de données
(Bibliotheque, table Livres) car nous allons réaliser quelques requêtes
de sélection.

Pour pouvoir réaliser un Select dans la BD nous pouvons utiliser les
**méthodes de base de Doctrine** associés à notre Entité. Quand on crée
une entité, sa classe **Repository** est créée aussi (ex : Client.php et
ClientRepository.php sont générées).

Cette classe contient **de méthodes capables de réaliser de requêtes
hérités de \\Doctrine\\ORM\\EntityRepository**.

Par défaut il existe les méthodes suivantes (hérités) :

-   find : sélection par id. Renvoie un objet

-   findBy : sélection avec de critères (dans un array associatif).
    Renvoie un array d\'objets

-   findOneBy : pareil que findBy mais elle renvoie que le premier
    enregistrement. Renvoie un objet

-   findAll : Renvoie un array d\'objets contenant tous les éléments du
    tableau

Voici un exemple d\'utilisation de chaque méthode (actions dans le
controller). Créez vous-mêmes les vues et les routes.

// SELECT: findOneBy

**namespace** App\\Controller;

**use**
Symfony\\Bundle\\FrameworkBundle\\Controller\\AbstractController;

**use** Symfony\\Component\\Routing\\Annotation\\Route;

**use** App\\Entity\\Livre; // nous permet d\'écrire Livre::class

**class** ExemplesModeleController **extends** AbstractController

{

> /\*\*
>
> \* \@Route (\"/exemples/modele/exemple/find/one/by\")
>
> \*/
>
> **public** **function** exempleFindOneBy (){
>
> // obtenir le entity manager
>
> \$em = \$this-\>getDoctrine()-\>getManager();
>
> // obtenir le repository
>
> \$rep = \$em-\>getRepository(Livre::**class**);
>
> // on obtient l\'objet, le filtre est envoyé sous la forme d\'un array
>
> \$livre = \$rep-\>findOneBy (**array**(\'titre\'=\>\'Life and
> Fate\'));
>
> // on stocke le résultat dans un array associatif
>
> // pour l\'envoyer à la vue comme d\'habitude
>
> \$vars = \[\'unLivre\'=\> \$livre\];
>
> // on renvoie l\'objet à la vue, rien ne change ici
>
> **return** \$this-\>render
> (\"exemples\_modele/exemple\_find\_one\_by.html.twig\", \$vars);
>
> }

}

L\'objet \$em est un objet de la classe EntityManager. Le ***entity
manager* gère le CRUD des entités** dans la BD. Tel qu\'on l\'a
mentionné ci-dessus, l\'objet repository (ici \$rep) possède de méthodes
qui nous facilitent ce CRUD. Par défaut nous disposons de l\'ensemble de
méthodes de base mentionné mais **on peut rajouter d\'autres méthodes
dans nos repository pour réaliser des requêtes plus complexes**.

// SELECT: find (chercher par id)

/\*\*

\* \@Route (\"exemples/modele/exemple/find\")

\*/

**public** **function** exempleFind (){

\$em = \$this-\>getDoctrine()-\>getManager();

\$rep = \$em-\>getRepository(Livre::**class**);

\$livre = \$rep-\>find(2);

\$vars = \[\'unLivre\' =\> \$livre\];

**return**
\$this-\>render(\"exemples\_modele/exemple\_find.html.twig\",\$vars);

}

// SELECT: findBy (chercher par un ou plusieurs champs, filtre array)

/\*\*

\* \@Route (\"exemples/modele/exemple/find/by\")

\*/

**public** **function** exempleFindBy (){

\$em = \$this-\>getDoctrine()-\>getManager();

\$rep = \$em-\>getRepository(Livre::**class**);

// notez que findBy renverra toujours un array même s\'il trouve

// qu\'un objet

\$livres = \$rep-\>findBy(**array** (\'prix\'=\>\'18\',

\'datePublication\'=\>**new** \\DateTime(\'1960-1-1\')));

\$vars = \[\'livres\' =\> \$livres\];

**return**
\$this-\>render(\"exemples\_modele/exemple\_find\_by.html.twig\",\$vars);

}

// SELECT: findAll (chercher par un ou plusieurs champs, filtre array)

/\*\*

\* \@Route (\"exemples/modele/exemple/find/all\")

\*/

**public** **function** exempleFindAll (){

\$em = \$this-\>getDoctrine()-\>getManager();

\$rep = \$em-\>getRepository(Livre::**class**);

// notez que findBy renverra toujours un array même s\'il trouve

// qu\'un objet

\$livres = \$rep-\>findAll();

\$vars = \[\'livres\' =\> \$livres\];

**return**
\$this-\>render(\"exemples\_modele/exemple\_find\_all.html.twig\",\$vars);

}

Créez de vues qui reçoivent ces objets en sachant que pour accéder aux
propriétés des objets depuis la vue vous pouvez utiliser la notation
d\'objet (.)

**{{ livre.titre }}**

#### Exercices : 

1)  Créez une méthode qui obtient la liste de tous les clients
    (remplissez la BD d\'abord ;))

2)  Créez une méthode qui obtient tous les clients qui s\'appellent
    Marie Dupont

3)  Créez une méthode qui obtient le client qui porte l\'id numéro 3
    dans la BD

INSERT et UPDATE
----------------

Quand on crée un objet (ex : Livre) il n\'a aucune relation avec la BD:
il est dans les **domaine des objets**. Si on lance la méthode
**persist** sur cet objet, **l\'objet sera lié au domaine de la BD**
mais aucune requête sera lancée pour le moment, l\'objet ne sera pas
encore dans la BD. Nous pouvons alors :

1.  Créer un objet

2.  Lancer **persist** pour lier l\'objet avec la BD (on ne modifie pas
    la BD encore!)

3.  Modifier le contenu de l\'objet

4.  Lancer **flush** pour l\'enregistrer/mettre à jour dans la BD

L\'opération **flush applique dans la BD les changements qu\'on a
réalisés dans le domaine des objets** (ex : obtenir un livre de la BD,
le modifier dans le domaine des objets et le réenregistrer dans la BD).

Les méthodes **persist** et **flush** n\'appartiennent pas à la classe
Repository, ils font partie du Entity Manager de Doctrine. On discutera
ces deux méthodes dans un contexte plus global (unité de travail) dans
la section \"Persistence\" plus bas dans ce tutoriel.

Voyons quelques exemples d\'insertion et mise à jour à continuation.

### INSERT

// INSERT LIVRE

### UPDATE

// UPDATE

/\*\*

\* \@Route (\"exemples/modele/exemple/update\")

\*/

**public** **function** exempleUpdate (){

\$em = \$this-\>getDoctrine()-\>getManager();

// on obtient d\'abord un livre

\$unLivre =
\$em-\>getRepository(Livre::**class**)-\>findOneBy(**array**(\"titre\"=\>\"Vie
et destin\"));

\$unLivre-\>setTitre (\"Toto est content\");

// pas besoin de persist

// quand on obtient un objet de la BD

// \$em-\>persist (\$unLivre);

\$em-\>**flush**();

**return** \$this-\>render
(\"exemples\_modele/exemple\_update.html.twig\");

}

### DELETE

// DELETE

/\*\*

\* \@Route (\"exemples/modele/exemple/delete\")

\*/

**public** **function** exempleDelete (){

\$em = \$this-\>getDoctrine()-\>getManager();

\$unLivre =
\$em-\>getRepository(Livre::**class**)-\>findOneBy(**array**(\"titre\"=\>\"1989\"));

// pas besoin de persist

// quand on obtient un objet de la BD

// \$em-\>persist (\$unLivre);

\$em-\>remove (\$unLivre);

\$em-\>**flush**();

**return** \$this-\>render
(\"exemples\_modele/exemple\_delete.html.twig\");

}

#### Exercices :

#### 

1.  Créez une méthode qui efface un client de la BD

2.  Créez une méthode qui insère deux Livres

3.  Pour nous faciliter la création des entités et ne pas devoir
    affecter les propriétés avec les méthodes Set, modifiez les
    constructeurs de vos entités pour qu\'il puissent recevoir un array
    contenant les paramètres pour construire chaque entité. Créez une
    méthode hydrate pour chaque entité. Cette méthode sera appelée si le
    constructeur reçoit un array de couples propriété-valeur (voir le
    cours d\'hydratation).

Le modèle : persistance
=======================

Les actions qu\'on réalise sur les entités (modification, mise à
jour...) sont regroupées dans une **unité de travail (Unit of Work)**.

L\'unité de travail contient l\'état de tous les objets et réalise de
requêtes à la BD. Elle est en charge de maintenir la **cohérence entre
le modèle et la BD**

Documentation :

<http://doctrine-orm.readthedocs.io/en/latest/reference/unitofwork.html>

**L\'unité de travail fonctionne de la manière suivante** :

-   La méthode **persist** (\$objet) **rajoute une entité à l\'unité de
    travail** (si elle n\'y était pas présente déjà).

Ex : quand on vient de créer un Livre avec **new.**

L\'entité devient \"gérée\" (**\"managed\"**)

-   Quand **on fait un select de la BD, les entités obtenues se trouvent
    directement dans l\'unité** **de** **travail** et on n\'a pas besoin
    de faire **persist**. Par contre, si on crée une entité juste avec
    **new**, elle fera partie de l\'unité de travail uniquement quand on
    lancera **persist**

-   Si on veut **enlever une entité de l\'unité de travail** et la
    rendre indépendante, on utilise **detach**. L\'objet devient
    indépendant de l\'entity manager et les modifications n\'auront pas
    d\'effet sur la BD même si on lance **flush**

-   **persist** rajoute une entité à l\'unité de travail et rend cette
    instance \"gérée\" (c\'est-à-dire que les futures mises à jour de
    l\'entité seront suivies et la BD sera modifié quand on fera
    **flush**).

-   **merge** crée une **nouvelle entité**. L\'entité que vous
    transmettez en paramètre ne sera pas gérée, mais uniquement la
    nouvelle. On n\'a pas besoin de l\'appliquer **persist** pour que
    ses modifications soient appliquées à la BD (il suffira de faire
    **flush**) car elle est déjà geree

-   **refresh** recharge le contenu de l\'entité de la BD

-   Chaque fois qu\'on appelle **flush**, Doctrine vérifie l\'unité de
    travail et synchronise les objets avec la BD (change la BD en
    fonction du contenu des objets qui se trouvent dans l\'unité de
    travail).

// DETACH

/\*\*

\* \@Route (\"/exemples/modele/exemple/detach\")

\*/

**public** **function** exempleDetach (){

\$em = \$this-\>getDoctrine()-\>getManager();

\$livre =
\$em-\>getRepository(Livre::**class**)-\>findOneBy(**array**(\"titre\"=\>\"Life
and Fate\"));

\$livre-\>setTitre(\"Totorito\");

\$em-\>detach(\$livre);

// ce flush ne fera rien, l\'éntité a été détachée de l\'unité du
travail

\$em-\>**flush**();

dump (\$livre);

**die**();

**return** \$this-\>render
(\"exemplesModele/exemple\_detach.html.twig\");

}

// MERGE

/\*\*

\* \@Route (\"/exemples/modele/exemple/merge\")

\*/

**public** **function** exempleMergeEntite (){

\$em = \$this-\>getDoctrine()-\>getManager();

\$livre = **new** Livre ();

\$livre-\>setTitre (\"Pizza pizza\");

// on crée une copie de l\'entité. Cette copie sera gérée

// dans l\'unité mais pas le livre original

\$nouveauLivre = \$em-\>merge (\$livre);

\$livre-\>setTitre (\"Tururu\"); // ne changera pas dans la BD

//quand on fera flush plus bas

// ce livre changera, cette copie est déjà dans l\'unité de travail.

// observez qu\'il n\'y aura pas un \"persist\"

\$nouveauLivre-\>setTitre (\"Nonono\");

\$nouveauLivre-\>setPrix (40);

\$nouveauLivre-\>setDescription (\"Super\");

\$nouveauLivre-\>setDatePublication (**new** \\DateTime);

// ce flush mettra à jour la BD pour \"nouveauLivre\"

\$em-\>**flush**();

**return** \$this-\>render
(\"exemples\_modele/exemple\_merge.html.twig\");

}

// REFRESH

/\*\*

\* \@Route (\"/exemples/modele/exemple/refresh\")

\*/

**public** **function** exempleRefresh (){

\$em = \$this-\>getDoctrine()-\>getManager();

\$unLivre =
\$em-\>getRepository(Livre::**class**)-\>findOneBy(**array**(\"titre\"=\>\"Life
and fate\"));

\$unLivre-\>setTitre (\"La vie est belle\");

// dump (\$unLivre);

// recharge le livre de la BD, il y aura le titre original

\$em-\>refresh(\$unLivre);

// dump (\$unLivre);

// die();

\$em-\>persist (\$unLivre);

// rien ne change dans la BD

\$em-\>**flush**();

**return** \$this-\>render
(\"exemples\_modele/exemple\_refresh.html.twig\");

}

Transitivité en Cascade 
-----------------------

Quand nous avons des associations entre les entités, nous avons la
possibilité d\'indiquer à Symfony **de propager l\'opération réalisé sur
une entité en cascade sur les entités associées**.

**Exemple** : on efface un livre et on provoque l\'effacement de tous
ses exemplaires en cascade

Nous avons plusieurs possibilités :

> **cascade-persist** : Si on a une entité qui contient de références à
> d\'autres entités, et nous modifions/rajoutons ces dernières, nous
> allons devoir faire uniquement **persist** sur la première et Doctrine
> fera persist sur toutes les entités associées.
>
> Exemple : nous obtenons un Livre auquel on rajoute des exemplaires. Si
> nous faisons **persist** sur le Livre, l\'opération sera transmise en
> cascade à tous les exemplaires. Autrement on devrait lancer
> **persist** sur chaque exemplaire.
>
> **cascade-remove** : Si on efface une entité, l\'effacement sera
> propagé en cascade.
>
> Si l\'entité n\'a pas eu un **persist**, elle n\'est pas effacée de la
> BD mais ses entités associées le seront.
>
> Si on a enlevé l\'entité de l\'unité de travail (clear), remove
> enverra une exception.
>
> **cascade-detach:** le détachement se transmet en cascade
>
> **cascade-merge:** pareil que la précédente mais pour **merge**
>
> **cascade-refresh** : pareil que la précédente mais pour **refresh**
>
> **cascade-all** : Implique toutes les opérations précédentes. Peut
> dégrader la performance.

#### Exemple : Réalisation d\'un INSERT des objets d\'une relation One-to-Many sans cascade-persist

Observez cet exemple où on crée un Livre et plusieurs Exemplaires, et on
stocke le tout dans la BD (créez un nouveau controller et importez les
classes Livre et Exemplaires) :

**class** ExemplesCascadeController **extends** AbstractController

{

/\*\*

\* \@Route(\"/exemples/cascade/exemple/sans/encapsulation\")

\*/

**public** **function** exempleSansEncapsulation (){

\$em = \$this-\>getDoctrine()-\>getManager();

// on crée un livre

\$livre = **new** Livre();

\$livre-\>setTitre(\"Confesión de un asesino\");

\$livre-\>setPrix (20);

\$livre-\>setDescription(\"Roman\");

\$livre-\>setDatePublication(**new** \\DateTime(\"1968:10:10
00:00:00\"));

// on crée deux exemplaires de ce Livre

\$exemplaire1 = **new** Exemplaire();

\$exemplaire1-\>setEtat(\"tache de chocolat\");

\$exemplaire2 = **new** Exemplaire();

\$exemplaire2-\>setEtat(\"très vieux\");

\$livre-\>addExemplaire(\$exemplaire1);

\$livre-\>addExemplaire(\$exemplaire2);

// Observez que l\'exemplaire fait référence à son livre

// grâce au code généré par l\'assistant dans \"addExemplaire\"

// car on a choisi de créer une association bidirectionnelle!

//dump (\$exemplaire1-\>getLivre());

//die();

// nous n\'avons pas besoin d\'indiquer nous-mêmes qui est

// le livre de chaque exemplaire!

// \$exemplaire1-\>setLivre(\$livre); // pas besoin

// \$exemplaire2-\>setLivre(\$livre); // pas besoin

\$em-\>persist(\$livre);

\$em-\>**flush**();

**return** \$this-\>render
(\"exemples\_cascade/exemple\_sans\_encapsulation.html.twig\");

}

}

Normalement le code devrait insérer un Livre et deux Exemplaires dans la
BD, et puis mettre à jour la clé étrangère (livre\_id) de chaque
exemplaire.

Mais si vous le lancez-vous obtenez :

![](media/image23.png){width="6.383333333333334in"
height="2.1638888888888888in"}

Symfony remarque qu\'on n\'a pas fait **persist** des objets associés
(les Exemplaires du Livre qu\'on vient de créer). Pour que le mécanisme
fonctionne, nous avons deux possibilités :

-   Lancer **persist** pour les exemplaires avant de lancer le persist
    du Livre (pas pratique)

> \$em-\>persist(\$exemplaire1);
>
> \$em-\>persist(\$exemplaire2);
>
> \$em-\>persist(\$livre);
>
> .
>
> .
>
> .

-   Spécifier que **la persistance doit se réaliser en cascade** dans
    l\'annotation de l\'association **(fichier de l\'entité). Modifiez
    le fichier de l\'entité Livre.php**

/\*\*

\* \@ORM\\OneToMany(targetEntity=\"App\\Entity\\Exemplaire\",
mappedBy=\"livre\",

\* **cascade={\"persist\"}**)

\*/

**private** \$exemplaires;

**IMPORTANT : Observez que les deux côtes de la relation sont mises à
jour dans la méthode addExemplaire :**

1.  **L\'exemplaire est rajouté à la liste d\'exemplaires dans Livre**

2.  **La propriété Livre est affecté dans l\'objet exemplaire. Cela
    permet que quand on réalisera la migration dans la BD, le livre\_id
    sera mis à jour sans devoir le faire à la main !**

#### Exercices :

1.  Effacez un livre et provoquez que les exemplaires soient effacés
    automatiquement. Modifiez la configuration de cascade pour que
    l\'opération soit réalisée correctement (exerciceCascadeRemove)

2.  Créez une méthode qui rajoute deux clients et une adresse. Faites
    bien attention au sens de cette association (côté Many et côté One).
    Modifiez les attributs de cascade pour pouvoir faire le persist

3.  Créez une méthode qui cherche un client dans la BD et puis
    l\'efface, y incluses toutes ses adresses

Encapsulation 
-------------

Le code de l\'exemple précédant crée un Livre, puis crée deux
exemplaires et pour finir stocke le tout dans la BD.

**La méthode utilisée fonctionne mais on peut l\'améliorer** :

Pour le moment on doit toujours créer les objets Livre et Exemplaire
dans l\'action principale. On doit alors **connaitre l\'existence et
importer toutes ces classes dans le controller !**

On peut aller plus loin en utilisant le concept d\'**encapsulation**.
L\'encapsulation es un principe de la programmation orienté objet qui,
entre autre, propose de **cacher la visibilité des objets ou des parties
d\'un objet**. Dans ce cas on veut permettre au développeur de rajouter
des exemplaires sans que le controller aie besoin de connaitre
l\'existence de la classe Exemplaire.

Le mécanisme est très simple : **au lieu de créer l\'objet** exemplaire
**dans l\'action du controller et l\'envoyer à la méthode qui le
rajoute** **au livre** (addExemplaire dans Livre), **on créera**
l\'exemplaire **à l\'intérieur d\'une nouvelle méthode de Livre**. Cette
méthode du livre sera **appelée depuis l\'action, qui l\'enverra les
données nécessaires pour créer l\'objet** exemplaire **mais pas l\'objet
en soi**. Voici un exemple, observez les différences avec l\'exemple
précédant :

Nouvelle méthode dans Livre.php :

// rajouté pour permettre l\'encapsulation

**public** **function** addExemplaireNoClass (\$etat, \$emplacement){

\$exemplaire = **new** \\App\\Entity\\Exemplaire();

\$exemplaire-\>setEtat(\$etat);

\$this-\>addExemplaire(\$exemplaire);

}

Nous n\'avons plus besoin de la classe Exemplaire dans l\'action
principale et en plus son code sera simplifié :

/\*\*

\*
\@Route(\"/exemples/encapsulation/rajouter/livre/exemplaires/encapsulation\")

\*/

**public** **function** rajouterLivreExemplairesEncapsulation (){

\$em = \$this-\>getDoctrine()-\>getManager();

// on crée un livre

\$livre = **new** Livre();

\$livre-\>setTitre(\"Currucucu Paloma\");

\$livre-\>setPrix (20);

\$livre-\>setDescription(\"Roman\");

\$livre-\>setDatePublication(**new** \\DateTime(\"1968:10:10
00:00:00\"));

// on ne crée pas ici les exemplaires. On envoie les données

// necessaires pour créer les objets Exemplaire à la nouvelle méthode

// de l\'entité Livre

// Cette méthode mettra à jour les deux côtés de la relation

// car elle fait appel à addExemplaire

\$livre-\>addExemplaireNoClass(\"tache de chocolat\", \"15A\");

\$livre-\>addExemplaireNoClass(\"très vieux\", \"13B\");

\$em-\>persist(\$livre);

\$em-\>**flush**();

**return** \$this-\>render
(\"exemples\_encapsulation/rajouter\_livre\_exemplaires\_encapsulation.html.twig\");

}

Comparez ce code avec celui de \"rajouterSansEncapsulation\"...

Héritage de classes et implémentation dans la BD
================================================

#### Exemple : Les clients et les auteurs d\'une application sont tous de personnes. Implementons ce modèle en code et dans la BD

![](media/image24.png){width="3.058333333333333in"
height="2.7319499125109363in"}

Note : cr

Nous pouvons approcher ce problème de deux formes différentes :

1.  **Single Table Inheritance** : On crée un seul tableau contenant les
    propriétés des trois entités. Dans le code il y a trois entités mais
    dans la BD il y a qu\'une. Pour savoir si une ligne dans le tableau
    correspond à une entité ou une autre on rajoutera une colonne
    \"discriminatrice\" qui indiquera le type de la ligne. Simple,
    rapide et sans jointures.

2.  **Class Table Inheritance** : On crée un tableau pour chaque entité.
    Plus lourd, pas toujours stable. Chaque query, même les très
    simples, demanderont la réalisation d\'une jointure.

Single Table Inheritance
------------------------

L\'héritage de table unique (Single Table inheritance) est une stratégie
de mappage d\'héritage dans laquelle toutes les classes d\'une
hiérarchie sont mappées vers une seule table de base de données. Afin de
distinguer quelle ligne du tableau représente quel type dans la
hiérarchie, une colonne dite \"discriminator\" est utilisée.

1)  **Créez les entités** enfants et parent : ClientH, AuteurH et
    PersonneH

2)  Rajoutez **extends** *PersonneH* dans les définitions des classes
    filles pour indiquer à Doctrine la présence d\'un héritage

3)  **Rajoutez les annotations** **InheritanceType,
    DiscriminatorColumn** et **DiscriminatorMap** à la classe **parent**

> **InheritanceType** indique le type d\'héritage. Ici c\'est Single
> Table
>
> **DiscriminatorColumn** indique le nom de la colonne qui contiendra la
> valeur qui nous indique à quelle classe fille correspond la ligne (ici
> \"auteurH\" ou \"clientH\")
>
> **DiscriminatorMap** indique les valeurs concretes de la colonne
> indiquée dans DiscriminatorColumn

/\*\*

\*
\@ORM\\Entity(repositoryClass=\"App\\Repository\\PersonneHRepository\")

\* @**InheritanceType**(\"SINGLE\_TABLE\")

\* @**DiscriminatorColumn**(name=\"discr\",type=\"string\")

\*
@**DiscriminatorMap**({\"personneH\"=\"PersonneH\",\"auteurH\"=\"AuteurH\",\"clientH\"=\"ClientH\"})

\*/

**class** PersonneH

{

.

.

.

}

4)  **Migrez la BD** et observez le résultat dans PHPMyAdmin

> ![](media/image25.png){width="3.591666666666667in"
> height="0.2952055993000875in"}

Bien que nous avons trois entités au total, la méthode de Single Table
crée une seule table contenant une colonne (discr) qui indiquera a
quelle classe fille correspond la ligne (dans notre cas le colonne
contient \"auteurH\" ou \"personneH\")

Les **régles** à suivre sont :

-   \@InheritanceType et \@DiscriminatorColumn doivent être spécifiés
    dans la classe la plus haute appartenant à la hiérarchie des entités
    mappées

-   \@DiscriminatorMap indique le type d\'une ligne. Ici, une valeur de
    \"personneH\" identifie une ligne comme étant de type PersonneH et
    \"auteurH\" identifie une ligne comme étant de type AuteurH.

On peut maintenant faire le CRUD de nos entités ...

#### Exemple : insérer un Client et un Auteur dans la base de de données

**class** ExemplesHeritageController **extends** AbstractController

{

/\*\*

\* \@Route(\"/exemples/heritage/inserer/client/auteur\")

\*/

**public** **function** insererClientAuteur(){

\$em = \$this-\>getDoctrine()-\>getManager();

// créer l\'objet

\$client = **new** ClientH();

\$client-\>setNom(\"López\");

\$client-\>setPrenom(\"Jean\");

\$client-\>setEmail (\"jean.lopez\@lala.de\");

\$client-\>setNumero(200);

\$auteur = **new** AuteurH();

\$auteur-\>setNom(\"Lucas\");

\$auteur-\>setPrenom(\"George\");

\$auteur-\>setNationalite(\"USA\");

// lier les objets avec la BD

\$em-\>persist(\$client);

\$em-\>persist(\$auteur);

// écrire les objets dans la BD

\$em-\>**flush**();

**return** **new** Response (\"Ok, objets insérés\");

}

}

Nous devons uniquement créer un Client et l\'insérer, Doctrine remplira
tant le tableau parent avec la colonne discriminateur ! Les valeurs qui
ne concernent pas chaque entité respective seront *NULL* bien évidemment

![](media/image26.png){width="6.383333333333334in"
height="0.5444444444444444in"}

Class Table Inheritance
-----------------------

> Nous n\'allons pas developper cette méthode maintenant mais vous avez
> la documentation ici :

<https://www.doctrine-project.org/projects/doctrine-orm/en/2.6/reference/inheritance-mapping.html#class-table-inheritance>

Accès à la BD avec DQL
======================

Nous avons vu comment réaliser de requêtes CRUD simples, mais dans un
projet réel nous allons devoir lancer de requêtes assez plus complexes,
tels que de regroupements (GROUP BY), de jointures de tableaux (JOIN) ou
même de sous-requêtes.

Pour ce faire, on peut utiliser :

1.  Du **SQL pur en PHP** (tel qu\'on a fait jusqu\'à maintenant)

2.  **DQL**: Doctrine Query Language, similaire à SQL

3.  **QueryBuilder**: une API qui nous permet de créer la requête en
    utilisant uniquement la POO

On va nous concentrer sur les méthodes 2 et 3. Dans cette section
concrètement on va étudier la méthode numéro 2: DQL.

**Documentation de DQL:**

<http://docs.doctrine-project.org/projects/doctrine-orm/en/latest/reference/dql-doctrine-query-language.html>

Exemples : projetDQLSymfony

**DQL utilise des objets, pas de tableaux**. Nos requêtes doivent être
basées sur notre modèle de classes. Ça implique qu\'on ne peut pas, par
exemple, faire une jointure de deux tableaux qui n\'ont pas de relation
dans le modèle de classes.

Nous pouvons réaliser des requêtes de SELECT, UPDATE et DELETE. Pour les
INSERTS on doit utiliser la méthode déjà expliquée de persistance (créer
l\'objet, le rendre persistant et le stocker dans la BD en lançant
flush).

Passons aux exemples d\'utilisation pour mieux comprendre.

SELECT
------

### Requête qui renvoi un array d\'arrays

// Exemple de SELECT uniquement des titres des livres

// qui coutent plus de 15 euros en DQL,

// on obtient un array de strings, pas d\'objets

/\*\*

\* \@Route (\"/exemples/d/q/l/exemple/select/array/arrays\")

\*/

**public** **function** exempleSelectArrayArrays (){

\$em = \$this-\>getDoctrine()-\>getManager();

\$query = \$em-\>createQuery (\"SELECT livre.titre, livre.prix FROM
App\\Entity\\Livre livre WHERE livre.prix\>15\");

\$resultat = \$query-\>getResult();

\$vars = \[\'livres\'=\> \$resultat\];

**return** \$this-\>render
(\"exemples\_dql/exemple\_select\_array\_arrays.html.twig\", \$vars);

}

-   \"livre\" est un **alias** pour la classe Livre. Toutes **les
    entités de cette classe qui satisfont la requête seront incluses**
    dans le résultat de la requête.

-   **FROM est toujours suivi d\'une classe** d\'entitée (chemin
    complet)

-   **L\'expression** \"livre.titre\" est juste un \"chemin\" qui
    **permet d\'atteindre des objets et de propriétés** dans la requête

/![](media/image27.png){width="2.642195975503062in"
height="3.752083333333333in"}

### Requête qui renvoi un array d\'objets

// SELECT des Livres complets en DQL,

// on obtient un array d\'objets!

/\*\*

\* \@Route (\"/exemples/d/q/l/exemple/select/array/objets\")

\*/

**public** **function** exempleSelectArrayObjets (){

\$em = \$this-\>getDoctrine()-\>getManager();

// avec cette requête on obtient un array d\'objets

\$query = \$em-\>createQuery (\'SELECT livre FROM App\\Entity\\Livre
livre WHERE livre.prix \>15\');

\$resultat = \$query-\>getResult();

\$vars = \[\'livres\'=\> \$resultat\];

**return** \$this-\>render
(\"exemples\_dql/exemple\_select\_array\_arrays.html.twig\", \$vars);

}

![](media/image28.png){width="3.1060608048993874in"
height="1.2401268591426071in"}

### Regular Joins et Fetch Joins

> Nous pouvons naviguer dans la hiérarchie d\'objets de Doctrine tel
> qu\'on l\'a fait jusqu\'à maintenant...

**Exemple** : obtenir un entité Livre de la BD et, une fois on l\'a dans
une variable, obtenir les Exemplaires de ce Livre pour après obtenir les
Emprunts.

Tel qu\'on a déjà vérifié, Doctrine utilise une technique qui porte le
nom de **lazy-loading**. Pour résumer son fonctionnement : **si une
entité** (ex. : Livre) **est associée à d\'entités d\'une autre classe**
(ex. : Exemplaires dans Livre), **Doctrine réalisera les requêtes à la
BD uniquement quand on accédera au contenu de ces dernières entités en
PHP** (accéder aux exemplaires du Livre pour les afficher, par exemple).
Autrement l\'objet (ou liste d\'objets) contenu dans l\'entité (ex. :
Exemplaires dans Livre) apparaitra vide (ou contenant un id, mais jamais
complet)

Ce comportement est très logique car si à chaque fois qu\'on accède à
une entité on doit charger toutes ses entités associés la surcharge du
système peut être énorme (ex. : obtenir un Livre et devoir charger tous
ses Exemplaires, Emprunts, Clients etc...)

Quand on utilise du DQL contenant de jointures nous allons avoir deux
possibilités : faire la requête pour qu\'elle utilise le lazy-loading ou
forcer la charge des entités associées.

Voyons les deux cas de figure :

**Regular Join (collection d\'Exemplaires vide) :**

// Regular Join

/\*\*

\* \@Route (\"/exemples/d/q/l/exemple/regular/join\")

\*/

**public** **function** exempleRegularJoin(){

\$em = \$this-\>getDoctrine()-\>getManager();

\$query = \$em-\>createQuery (\'SELECT livre FROM App\\Entity\\Livre
livre JOIN livre.exemplaires exemplaires\');

\$resultats = \$query-\>getResult();

// observez que les exemplaires sont vides

\$resultat = \$query-\>getResult();

// observez que les exemplaires sont remplis dans le dump de la vue

\$vars = \[\'livres\'=\> \$resultat\];

**return** \$this-\>render
(\"exemples\_dql/exemple\_regular\_join.html.twig\", \$vars);

}

![](media/image29.png){width="3.1917115048118987in"
height="2.8833333333333333in"}

**Fetch Join (collection d\'Exemplaires remplie) :**

// Fetch Join

/\*\*

\* \@Route (\"/exemples/d/q/l/exemple/fetch/join\")

\*/

**public** **function** exempleFetchJoin(){

\$em = \$this-\>getDoctrine()-\>getManager();

// si on indique juste \"SELECT livre\" on obtient les objets de cette
entité

\$query = \$em-\>createQuery (\'SELECT livre, exemplaires FROM
App\\Entity\\Livre livre JOIN livre.exemplaires exemplaires\');

\$resultat = \$query-\>getResult();

// observez que les exemplaires sont remplis dans le dump de la vue

\$vars = \[\'livres\'=\> \$resultat\];

**return** \$this-\>render
(\"exemples\_dql/exemple\_fetch\_join.html.twig\", \$vars);

}

![](media/image30.png){width="3.6in" height="3.623077427821522in"}

UPDATE
------

Exemple de UPDATE en DQL : réduire le prix d\'un livre

// UPDATE

/\*\*

\* \@Route (\"/exemples/d/q/l/exemple/update\")

\*/

**public** **function** exempleUpdate (){

\$em = \$this-\>getDoctrine()-\>getManager();

\$query = \$em-\>createQuery (\'UPDATE App\\Entity\\Livre l SET l.prix =
l.prix - :montant WHERE l.titre = :titre\');

// pour simplifier on fixe de valeurs pour le montant à déduire et le
livre à changer (ISBN)

\$montant = 0.5;

\$ISBN = \"The Aleph\";

\$query-\>setParameter (\'montant\',\$montant);

\$query-\>setParameter (\'titre\',\$ISBN);

\$query-\>execute(); // pas getResult!

**return** \$this-\>render
(\"exemples\_dql/exemple\_update.html.twig\");

}

**Important :** Les instructions DQL UPDATE sont portées directement
dans une simple instruction UPDATE de la BD. Ça implique que les entités
qui sont déjà chargées dans le contexte de persistance ne seront PAS
synchronisées avec le nouvel état de la base de données mise à jour.
Dans certains cas, quand vous utilisez du DQL il est recommandé
d\'appeler la méthode **clear** du EntityManager pour d\'extraire les
nouvelles instances de toute entité affectée.

Exercices DQL
-------------

En utilisant DQL :

1)  Obtenez les clients

2)  Obtenez les emprunts (isolés)

3)  Obtenez les emprunts de tous les clients (seulement le nom du client
    et les dates de retour)

4)  Obtenez l\'état de tous les emprunts de tous les clients (affichez
    le nom, prénom du client ainsi que l\'état de l\'exemplaire)

5)  Obtenez la liste de livres empruntés par tous les clients : nom du
    client, prénom du client et titre du livre

6)  Obtenez la liste des livres empruntés par un client de votre choix :
    nom du client, prénom du client et titre du livre

7)  Obtenez la liste de livres qui coutent plus qu\'une valeur reçue en
    paramètre dans l\'URL

8)  Obtenez tous les livres qui contient un texte dans le titre reçu
    comme paramètre dans l\'URL

9)  Obtenez tous les emprunts réalisés pendant la prémiere quinzaine de
    février en utilisant DQL. On veut afficher le titre du livre, la
    date de l\'emprunt et le nom et le prénom du client

> **Note** : Les fonctions DAY, MONTH et YEAR ne sont pas acceptées par
> défaut dans DQL pour pouvoir garder le langage independant du type de
> BD. Vous allez avoir besoin d\'enregistrer de fonctions de date dans
> symfony en rajoutant des extensions de doctrine. Essayez de suivre par
> vous-mêmes la documentation !
>
> <https://github.com/oroinc/doctrine-extensions>

10) **Exercez-vous** en réalisant toute sorte de requêtes, essayez les
    possibilités de Doctrine :

<https://www.doctrine-project.org/projects/doctrine-orm/en/2.6/reference/dql-doctrine-query-language.html>

11) **Extra** : Créez de vues pour afficher convenablement tous ces
    résultats. Vous allez mieux apprendre coment parcourir les
    structures de données

Accès à la BD avec DQL en utilisant les classes Repositoires
============================================================

Tel qu\'on a déjà mentionné dans la section \"Selection\", quand on crée
une entité sa classe Repository est créée aussi. Cette classe contient
les méthodes par défaut qu\'on a déjà utilisés (find, findBy, findOneBy,
etc...). On va maintenant rajouter **de méthodes faits par nous capables
de réaliser de requêtes plus complexes**.

Le but est de simplifier les actions du controller qui, au lieu de
devoir contenir la logique de requêtes complexes, appelleront aux
actions des repositoires.

#### Exemple : Créez une méthode dans la classe Repository de Livre et l\'utiliser depuis une action du controller (au lieu d\'utiliser DQL depuis le controller lui-même)

1.  **Créez la méthode du repository pour nous faciliter la tâche**

Observez que :

-   La méthode renvoie le résultat de la requête, pas de vue bien
    évidemment

-   **Pour obtenir l\'Entity Manager dans les classes Repository** on
    utilise

> **\$this-\>getEntityManager()**. Nous ne sommes pas dans le controller
> !

// obtenir les livres entre deux prix

**public** **function** livresEntreDeuxPrixDQL (\$pmin, \$pmax){

\$em = \$this-\>getEntityManager();

// avec cette requête on obtient un array

\$query = \$em-\>createQuery (\'SELECT livre FROM App\\Entity\\Livre
livre WHERE livre.prix \>= :pmin AND \'.

\'livre.prix \<= :pmax\');

\$query-\>setParameter (\'pmin\', \$pmin);

\$query-\>setParameter (\'pmax\', \$pmax);

\$resultat = \$query-\>getResult();

// cette méthode renvoie le résultat de la requête

**return** \$resultat;

}

**\
**

2.  **Utilisez la méthode depuis le controller**

Observez qu\'il n\'y a pratiquement rien à faire dans l\'action...

/\*\*

\* \@Route
(\"/exemples/d/q/l/repositories/utilise/repo/livres/entre/deux/prix/{prixMin}/{prixMax}\")

\*/

**function** utiliseRepoLivresEntreDeuxPrix (Request \$req){

\$prixMin = \$req-\>get(\"prixMin\");

\$prixMax = \$req-\>get(\"prixMax\");

\$em = \$this-\>getDoctrine()-\>getManager();

\$livresRepo = \$em-\>getRepository(Livre::**class**);

\$livres = \$livresRepo-\>livresEntreDeuxPrixDQL(\$prixMin, \$prixMax);

dump (\$livres);

**die**();

// return new Response \.....

}

#### Exercices : 

1.  Faites une action où vous créez une adresse et plusieurs clients. Le
    tout sera stocké dans la BD

2.  Rajoutez une adresse à un client existant

3.  Créez une méthode qui utilise DQL dans la classe Repository de
    l\'entité Adresse pour vous faciliter la tâche d\'obtenir les
    adresses d\'une certaine ville

Accès à la BD avec Query Builder
================================

**Query Builder est une API qui permet de générer des requêtes de
séléction complexes qui renvoient des objets** (requêtes de
regroupement, jointures, sous-requêtes...) et pas juste des arrays.

On pourra réaliser les fonctions de DQL mais en utilisant une notation
completement orientée objet (avec ses avantages et ses inconvenients)

Un Objet **QueryBuilder est accéssible depuis une classe**
**Repository**.

QueryBuilder fournit les méthodes suivantes qu\'on combinera selon nos
besoins concrètes :

> ![](media/image31.png){width="3.3375in" height="1.5400721784776903in"}

La documumentation de QueryBuilder se trouve ici :

[http://docs.doctrine-project.org/projects/doctrine-dbal/en/latest/reference/query-builder.html\#](http://docs.doctrine-project.org/projects/doctrine-dbal/en/latest/reference/query-builder.html)

À continuation on va réaliser un exemple pratique, on commencera par une
requête simple.

Commencez par la création d\'un controller portant le nom
UtiliseQueryBuilderController

#### Exemple : utiliser QueryBuilder pour construire une requête capable d\'obtenir le nombre de Livres dont le prix se trouve entre un minimum et un maximum

1.  **Créez la méthode du repositoire** (LivreRepository.php) **capable
    de realiser la requête avec Query Builder**

// QUERYBUILDER: obtenir les livres entre deux prix

// obtenir les livres entre deux prix, version QueryBuilder

**public** **function** getEntreDeuxPrix (\$min, \$max){

\$qb = \$this-\>createQueryBuilder(\"u\"); // u est un nom générique

\$query = \$qb-\>select(\'u\')

-\>where(\'u.prix \>= :min\')

-\>andWhere(\'u.prix \<= :max\')

-\>setParameter(\'min\', \$min)

-\>setParameter(\'max\', \$max)

-\>getQuery();

\$res = \$query-\>getResult();

//var\_dump (\$res);

**return** \$res;

}

Notez que l\'API nous permet de réaliser l\'ensemble de la requête sans
utiliser ni du SQL pur ni du DQL. Sachez quand-même que QueryBuilder
utilise le langage DQL comme langage sous-jacent.

2.  **Créez une action dans le controller qu\'utilise cette méthode** et
    envoyez la réponse au client (new Response) pour qu\'il l\'affiche

/\*\*

\* \@Route
(\"/exemples/query/builder/utilise/repo/livres/entre/deux/prix/{prixMin}/{prixMax}\")

\*/

**function** utiliseRepoLivresEntreDeuxPrix (Request \$req){

\$prixMin = \$req-\>get(\"prixMin\");

\$prixMax = \$req-\>get(\"prixMax\");

\$em = \$this-\>getDoctrine()-\>getManager();

\$livresRepo = \$em-\>getRepository(Livre::**class**);

\$livres = \$livresRepo-\>livresEntreDeuxPrixDQL(\$prixMin, \$prixMax);

dump (\$livres);

**die**();

// return new Response \.....

}

####  

#### Exemple : obtenir un Client dont on connait l\'email de la BD avec QueryBuilder

1.  **Créez des données dans la BD**

-   Créez une nouvelle Personne dans la BD. Pour la
    \"discrimination-column\", tapez \"client\"

-   Créez un nouveau Client qui sera cette Personne (utilisez l\'id de
    la Personne qui vous venez d\'encoder)

-   Créez la méthode getByEmail dans le repositoire de l\'entité Client
    (ClientRepository.php) :

2.  **Créez la méthode du repositoire capable de realiser la requête
    avec Query Builder**

// QUERYBUILDER: obtenir les clients par mail, version QueryBuilder

**public** **function** getParEmail (\$email){

\$qb = \$this-\>createQueryBuilder(\"u\");

\$query = \$qb-\>select(\'u\')

-\>where (\'u.email = :email\')

-\>setParameter(\'email\', \$email)

-\>getQuery();

\$resultat = \$query-\>getSingleResult();

**return** \$resultat;

}

3.  **Créez une action dans le controller qu\'utilise cette méthode** et
    envoyez la réponse au client (new Response) pour qu\'il l\'affiche

/\*\*

\* \@Route (\"/exemples/query/builder/trouver/client/par/mail/{email}\")

\*/

**public** **function** trouverClientParMail(Request \$req){

\$em = \$this-\>getDoctrine()-\>getManager();

\$rep = \$em-\>getRepository(Client::**class**);

// on fait appel à la méthode du Repository

\$objetClient = \$rep-\>getParEmail(\$req-\>get (\"email\"));

// on affiche les données du Client, on a obtenu un objet

dump (\$objetClient);

**die** ();

// return new Response \.....

}

Formulaires en Symfony
======================

Un formulaire est un ensemble d\'éléments HTML dont leur contenu est
envoyé au serveur (**action**) en exécutant un **submit**. Le serveur
reçoit une requête **POST** qui contient les contenus des éléments du
formulaire. En PHP, ces contenus sont accessibles à partir de la
variable \$\_POST.

En Symfony, un formulaire est une interface qui correspond souvent à un
modèle.

Exemple : Si on crée un formulaire pour insérer un Client, il sera
associé à l\'entité Client

On va mieux comprendre avec un exemple pratique.

Création une classe de formulaire 
---------------------------------

Créons un **formulaire lié à une entité du modèle** (Aeroport).

Créez d\'abord un **nouveau projet** (ex : projetFormulaires) contenant
un controller (ex : **FormulairesController**). Rajoutez une entité
Aeroport (nom, code) et créez la BD (ex: formulairesbd) et saisissez
quelques données.

#### Exemple : création d\'une classe de formulaire 

On va créer un formulaire pour l\'entité Aeroport qui contiendra deux
champs de texte (nom et code). Le bouton de submit sera rajouté à
posteriori.

1.  Rajoutez les **classes** qui gèrent les **formulaires** en Symfony
    **dans le projet** (cette action doit se faire une seule fois para
    projet!)

composer require symfony/form

2.  **Créez le dossier src/Form et un fichier qui contiendra la classe
    qui définira le formulaire** (pour l\'entité Aeroport on crée le
    fichier Aeroport**Type**.php)

Cette définition est une classe, une représentation abstraite de notre
formulaire, mais il n\'y a pas du HTML à l\'intérieur.

Voici le code :

\<?php

**namespace** App\\Form;

**use** Symfony\\Component\\Form\\AbstractType;

**use** Symfony\\Component\\Form\\FormBuilderInterface;

**use** Symfony\\Component\\Form\\Extension\\Core\\Type\\TextType;

**class** AeroportType **extends** AbstractType {

**public** **function** buildForm (FormBuilderInterface \$builder,
**array** \$options){

\$builder-\>add (\'nom\', TextType::**class**)

-\>add (\'code\', TextType::**class**);

}

}

La classe qui représente le formulaire doit hériter de **AbstractType**,
et possède une méthode **buildForm** qui est en charge de générer
l\'objet formulaire. Cette méthode reçoit un objet qui implémente la
classe FormBuilderInterface (il est injecté par Symfony, nous ne créons
pas cet objet par nous-mêmes), en plus d\'un array d\'options qui nous
permettrait de personnaliser le formulaire.

En général, vous allez utiliser la méthode **add** de cet objet pour
rajouter les champs du formulaire. Vous devez, pour chaque champ,
indiquer le **name** (premier paramètre) ainsi que le **type**. Symfony
possède un vaste nombre de types déjà définis qui correspondent aux type
HTML, mais on peut en plus définir nos propres types pour atteindre un
niveau de complexité assez élevé.

Voici la liste de types inclus dans Symfony :

<https://symfony.com/doc/current/forms.html#built-in-field-types>

Étudiez par vous-mêmes les types et son fonctionnement, dans ce cours
c\'est impossible de les parcourir tous vu le temps dont on dispose.

3.  **Dans une nouvelle action, créez une instance du formulaire** en
    utilisant la méthode **createForm** du controller.

Dans cette action on utilisera la méthode **createForm** pour créer une
instance du formulaire (on indique le type qu\'on vient de définir).
Puis on utilise la méthode **createView** pour générer le code HTML qui
sera envoyé à la vue. Voici le code :

**namespace** App\\Controller;

**use**
Symfony\\Bundle\\FrameworkBundle\\Controller\\AbstractController;

**use** Symfony\\Component\\Routing\\Annotation\\Route;

// la classe du Formulaire

**use** App\\Form\\AeroportType;

**class** ExemplesFormulairesController **extends** AbstractController

{

/\*\*

\* \@Route (\"/exemples/formulaires/exemple/aeroport\");

\*/

**public** **function** exempleAeroport (){

// on crée le formulaire du type souhaité

\$formulaireAeroport = \$this-\>createForm (AeroportType::**class**);

// on envoie un objet FormView à la vue pour qu\'elle puisse

// faire le rendu, pas le formulaire en soi

\$vars = \[\'unFormulaire\'=\>\$formulaireAeroport-\>createView()\];

**return** \$this-\>render
(\'/exemples\_formulaires/exemple\_aeroport.html.twig\',\$vars);

}

}

4.  **Créez la vue et appelez la foncti**on **form** **de twig** en lui
    envoyant l\'objet **FormView** qu\'on vient de recevoir du
    controller

Il y a plusieurs manières de rendre le formulaire :

<https://symfony.com/doc/current/forms.html#rendering-the-form>

On peut rendre le formulaire complète ou par parties, en utilisant un
thème (Bootstrap, Foundation, etc...) ou pas.

{{ form\_start (unFormulaire) }}

{{ form\_widget (unFormulaire) }}

{{ form\_end (unFormulaire)}}

form\_start et form\_end générent les balises du début et fin du
formulaire et form\_widget génère tous les contrôles.

Création d\'un formulaire associé à une entité
----------------------------------------------

Vous pouvez créer un formulaire pré-rempli avec les données d\'une
entité. Pour ce faire, il suffit de créer l\'entité avant et l\'envoyer
comme deuxième paramètre à la méthode **createForm**. Voici un exemple :

/\*\*

\* \@Route (\"/exemples/formulaires/exemple/aeroport/rempli\");

\*/

**public** **function** exempleAeroportRempli (){

\$unAeroport = **new** Aeroport ();

\$unAeroport-\>setNom(\"Sevilla Santa Justa\");

\$unAeroport-\>setCode(\"SVQ\");

// etc\....

// on crée le formulaire du type souhaité

\$formulaireAeroport = \$this-\>createForm (AeroportType::**class**,
**\$unAeroport**);

// on envoie un objet FormView à la vue pour qu\'elle puisse

// faire le rendu, pas le formulaire en soi

\$vars = \[\'unFormulaire\' =\> \$formulaireAeroport-\>createView()\];

**return** \$this-\>render
(\'/exemples\_formulaires/exemple\_aeroport.html.twig\',\$vars);

}

Types des champs du formulaire
------------------------------

On va modifier le formulaire en rajoutant le type de chaque widget.
Rajoutez les proprietés **dateMiseEnService, heureMiseEnService** et
**description** dans l\'entité et dans le formulaire (n\'oubliez pas les
**use**). Faites aussi la migration !

**public** **function** buildForm(FormBuilderInterface \$builder,
**array** \$options)

{

\$builder-\>add(\'code\', TextType::**class**)

-\>add(\'nom\', TextType::**class**)

-\>add(\'dateMiseEnService\', DateType::**class**)

-\>add(\'heureMiseEnService\', TimeType::**class**)

-\>add(\'description\', TextareaType::**class**)

}

Nous n\'allons pas rajouter un bouton de submit dans la classe du
formulaire **car ce n\'est pas une bonne pratique.**

Affichez à nouveau la vue et observez le résultat :

![](media/image32.png){width="2.201388888888889in"
height="1.6921128608923885in"}

#### Exercice : créez l\'action et la vue nécessaires pour afficher ce formulaire! 

Propriétés des champs du formulaire
-----------------------------------

Chaque type de données correspond à une classe qui hérite de la classe
**FormType**. Chaque champ d\'un formulaire à un **objet (widget)
associé qui générera son code HTML (selon son type).** Chaque champ a
**un ensemble de propriétés HTML héritées de ses parents** (ex:
\"label\" ou \"placeholder\") **ainsi qu\'un ensemble d\'options**
**propres** (ex: \"preferred\_choices\" pour le type LanguageType).

#### Exemple : rajout des options dans les champs du formulaire 

On va créer un formulaire plus personnalisé que le précédent pour
l\'entité Livre. Rajoutez les entités Exemplaire et Livre (vous pouvez
les copier d\'un autre projet, mais effacez les relations avec les
autres entités tel que Categorie). Pour Livre, rajoutez les champs
**nombrePages**, **langue** et **format**

**Créez un formulaire** basé sur Livre (prenez comme exemple celui de
l\'entité Aeroport) et **rajoutez les types pour chaque champ** qui
puissent vous convenir le plus.

**Toutes les informations nécessaires sur les types se trouvent ici :**

<https://symfony.com/doc/current/reference/forms/types.html>

Voici le code d\'exemple:

**public** **function** buildForm(FormBuilderInterface \$builder,
**array** \$options)

{

\$builder-\>add(\'ISBN\', TextType::**class**)

-\>add(\'titre\', TextareaType::**class**)

-\>add(\'prix\', MoneyType::**class**)

-\>add(\'description\', TextareaType::**class**)

-\>add(\'datePublication\', DateType::**class**,\[

\'label\' =\> \'Date de publication\'

\])

-\>add(\'nombrePages\', IntegerType::**class**, \[

\'label\' =\> \'Nombre de pages\',

\'required\' =\> **false**

\])

-\>add(\'langue\', LanguageType::**class**, \[

\'label\' =\> \'Langue du livre\',

\'preferred\_choices\' =\> \[\'es\',\'fr\',\'it\'\]

\])

-\>add (\'format\', ChoiceType::**class**, \[

\'choices\' =\> \[

\'eBook\' =\> \'ebook\',

\'papier\' =\> \'papier\'

\],

// les combinaisons de ces paramètres détermineront le type de

// liste de choix : liste, liste déroulante, checkbox ou

// radiobuttons

\'expanded\' =\> **false**,

\'multiple\' =\> **true**

\]);

}

Avant de créer une action pour générer ce formulaire on va rajouter la
méthode et l\'action dans la section suivante.

Méthode et Action
-----------------

Pour finir le formulaire, on peut spécifier l\'action à réaliser pour le
submit (même avant créer le bouton) ainsi que la méthode (GET ou POST).
Nous avons deux possibilités :

1)  Définir l\'action **dans la classe du formulaire**. C\'est facile
    mais on ne pourra utiliser le formulaire pour exécuter d\'autres
    actions !

**Important :** Cette méthode est à éviter mais elle facilite la
compréhension des bonnes pratiques

**public** **function** buildForm(FormBuilderInterface \$builder,
**array** \$options)

{

\$builder-\>add(\'ISBN\', TextType::**class**)

-\>add(\'titre\', TextareaType::**class**)

-\>add(\'prix\', MoneyType::**class**)

-\>add(\'description\', TextareaType::**class**)

-\>add(\'datePublication\', DateType::**class**,\[

\'label\' =\> \'Date de publication\'

\])

-\>add(\'nombrePages\', IntegerType::**class**, \[

\'label\' =\> \'Nombre de pages\',

\'required\' =\> **false**

\])

-\>add(\'langue\', LanguageType::**class**, \[

\'label\' =\> \'Langue du livre\',

\'preferred\_choices\' =\> \[\'es\',\'fr\',\'it\'\]

\])

-\>add (\'format\', ChoiceType::**class**, \[

\'choices\' =\> \[

\'eBook\' =\> \'ebook\',

\'papier\' =\> \'papier\'

\],

// les combinaisons de ces paramètres détermineront le type de

// liste de choix : liste, liste déroulante, checkbox ou

// radiobuttons

\'expanded\' =\> **false**,

\'multiple\' =\> **false**

\])

**-\>setMethod(\'POST\')**

**-\>setAction(\'traitementFormulaireLivre\');;**

}

**\
**

2)  **Définir l\'action et la méthode dans le controller** lors de la
    création de l\'objet formulaire. Cette option est **plus souple**
    car elle nous permet de réutiliser le formulaire pour lancer
    d\'autres actions :

**Dans la classe du formulaire il n\'y a pas d\'action ni de méthode :**

**class** LivreType **extends** AbstractType {

**public** **function** buildForm(FormBuilderInterface \$builder,
**array** \$options)

{

\$builder-\>add(\'ISBN\', TextType::**class**)

-\>add(\'titre\', TextareaType::**class**)

-\>add(\'prix\', MoneyType::**class**)

-\>add(\'description\', TextareaType::**class**)

-\>add(\'datePublication\', DateType::**class**,\[

\'label\' =\> \'Date de publication\'

\])

-\>add(\'nombrePages\', IntegerType::**class**, \[

\'label\' =\> \'Nombre de pages\',

\'required\' =\> **false**

\])

-\>add(\'langue\', LanguageType::**class**, \[

\'label\' =\> \'Langue du livre\',

\'preferred\_choices\' =\> \[\'es\',\'fr\',\'it\'\]

\])

-\>add (\'format\', ChoiceType::**class**, \[

\'choices\' =\> \[

\'eBook\' =\> \'ebook\',

\'papier\' =\> \'papier\'

\],

\'expanded\' =\> **false**,

\'multiple\' =\> **true**

\])

}

}

/\*\*

\* \@Route (\"/exemples/formulaires/exemple/livre\");

\*/

**public** **function** exempleLivre (){

\$livre = **new** Livre();

\$formulaireLivre = \$this-\>createForm (LivreType::**class**, \$livre,
**array**(

**\'action\' =\> \$this-\>generateUrl(\"rajouter\_livre\"), // name de
la route!**

// si on n\'utilise pas le name d\'une route

// \'action\' =\> \"/exemples/formulaires/livre/rajouter\",

**\'method\' =\> \'POST\'**

));

\$vars = \[\'unFormulaire\'=\>\$formulaireLivre-\>createView()\];

**return** \$this-\>render
(\'/exemples\_formulaires/exemple\_livre.html.twig\',\$vars);

}

Nous utiliserons un array de paramètres et la méthode **generateUrl**
pour générer le code HTML qui correspond à une route qui porte un
\"name\". Si la route n\'a pas de \"name\" on peut juste mettre un path,
mais c\'est moins souple car la modification d\'un path dans le routing
impliquera modifier une par une toutes les appels à cette action.

Voici le code complet du controller, ici on a une route avec \"name\"
(rajouter\_livre) :

\<?php

**namespace** App\\Controller;

**use**
Symfony\\Bundle\\FrameworkBundle\\Controller\\AbstractController;

**use** Symfony\\Component\\Routing\\Annotation\\Route;

// les entités de base

**use** App\\Entity\\Aeroport;

**use** App\\Entity\\Livre;

// les classes des Formulaires

**use** App\\Form\\AeroportType;

**use** App\\Form\\LivreType;

**class** ExemplesFormulairesController **extends** AbstractController

{

/\*\*

\* \@Route (\"/exemples/formulaires/exemple/aeroport\");

\*/

**public** **function** exempleAeroport (){

// on crée le formulaire du type souhaité

\$formulaireAeroport = \$this-\>createForm (AeroportType::**class**);

// on envoie un objet FormView à la vue pour qu\'elle puisse

// faire le rendu, pas le formulaire en soi

\$vars = \[\'unFormulaire\'=\>\$formulaireAeroport-\>createView()\];

**return** \$this-\>render
(\'/exemples\_formulaires/exemple\_aeroport.html.twig\',\$vars);

}

/\*\*

\* \@Route (\"/exemples/formulaires/exemple/livre\");

\*/

**public** **function** exempleLivre (){

\$livre = **new** Livre();

\$formulaireLivre = \$this-\>createForm (LivreType::**class**, \$livre,
**array**(

\'action\' =\> \$this-\>generateUrl(\"rajouter\_livre\"), // name de la
route!

// si on n\'utilise pas le name d\'une route

// \'action\' =\> \"/exemples/formulaires/livre/rajouter\",

\'method\' =\> \'POST\'

));

\$vars = \[\'unFormulaire\'=\>\$formulaireLivre-\>createView()\];

**return** \$this-\>render
(\'/exemples\_formulaires/exemple\_livre.html.twig\',\$vars);

}

/\*\*

\* \@Route (\"/exemples/formulaires/exemple/livre/rajouter\",
name=\"rajouter\_livre\");

\*/

**public** **function** rajouterLivre(){

dump (\"je rajoute un livre\");

**die**();

}

}

Boutons dans les formulaires (bonnes pratiques)
-----------------------------------------------

Si on veut reutiliser un même formulaire pour réaliser plusieurs actions
(ex : mettre à jour un livre ou rajouter un livre) on ne doit pas créer
les boutons dans la classe du formulaire mais dans la vue
correspondante. Si on le crée dans la classe on sera coincés car
l\'étiquette du bouton sera fixée (on casse le principe de réutilisation
du code!).

On ne doit pas non plus rajouter le bouton dans le controller mais on
serait en train de mélanger présentation (ex : la classe du bouton) avec
la logique (on casse le principe de \"separation of concerns\"!).

La **meilleure option est de créer le bouton de submit en HTML dans la
vue**. Voici un exemple :

{{ form\_start (formulaireLivre) }}

{{ form\_widget (formulaireLivre) }}

\<input type=\"submit\" **class**=\"btn\" value=\"Envoyer\" /\>

{{ form\_end (formulaireLivre) }}

Cette méthode nous permet de reutiliser le formulaire pour plein
d\'actions, on devra juste créer les boutons dans chaque vue.

#### Exercice : Créez des boutons de submit dans les vues qui rendent les formulaires des exemples précédents

###   {#section-5 .list-paragraph}

Rendu du formulaire dans la vue
-------------------------------

Au moment de générer un formulaire dans un fichier twig on peut utiliser
:

**{{ form (formulaireAeroport) }}**

Pour rendre la totalité du formulaire d\'un coup. Mais on peut
controller plus la génération du formulaire en utilisant :

**{{ form\_start (nomDuFormulaire) }}**

Rend la balise de début du formulaire, y compris l\'attribut enctype
correct lors de l\'utilisation des téléchargements de fichiers.

**{{ form\_widget (nomChampFormulaire) }}**

Rend un champ, ce qui inclut l\'élément du champ lui-même, une étiquette
et tous les messages d\'erreur de validation pour le champ (si on a
défini de validations)

**{{ form\_end (nomDuFormulaire) }}**

Rend l\'étiquette de fin du formulaire et tous les champs qui n\'ont pas
encore été rendus, dans le cas où vous avez rendu chaque champ
vous-même. Ceci est utile pour ne pas devoir rendre à la main les champs
cachés.

**Exemple :**

{{ form\_start (formulaireAeroport) }}

{{ form\_widget (formulaireAeroport.nom) }}

{{ form\_widget (formulaireAeroport.description) }}

{{ form\_end (formulaireAeroport) }}

Résumé : création et personnalisation de base d\'un formulaire
--------------------------------------------------------------

Pour créer un formulaire :

1.  Créez le **squelette** du formulaire

2.  **Rajoutez les champs (\"widgets\") et leurs types** selon vos
    besoins

3.  **Personnalisez** le widget avec des **propriétés**

4.  Définissiez l\'**action** et la **méthode** du formulaire

5.  Créez une **action qui génère le formulaire**

6.  **Définissez l\'action et la méthode du formulaire dans l\'action du
    controller**

7.  **Renvoyez un objet** FormView à la **vue**

8.  **Rendez le FormView** dans la vue en appelant les méthodes
    \"helper\" **form\_xx**

9.  **Rajouter les boutons de submit dans la vue**

**\
**

Traitement des données du formulaire (explication de base)
----------------------------------------------------------

Pour **recevoir et traiter** les données introduites dans un formulaire
nous devons créer une action dans un controller. L\'action traitera la
requête (reçoit un objet **Request**).

Voici un exemple complet et son explication.

#### Exemple : Rendu et réception d\'un formulaire 

Cette action peut être appelé dans deux cas de figure :

a)  On **appele l\'action para une premiere fois, le formulaire doit
    être rendu** (affiché dans la vue)

b)  On **appele l\'action en cliquant sur un bouton submit** et on doit
    traiter le contenu reçu (dans ce cas on va juste afficher un objet
    crée à partir du contenu du formulaire)

Dans les deux cas de figure on crée une entité et un objet formulaire.
Pour savoir si on se trouve dans le cas a) ou b) on doit **vérifier
l\'objet Request**. Dans le cas a) l\'objet sera vide car on n\'a pas
fait submit et dans le cas b) l\'objet Request contiendra les données du
formulaire, on doit prendre ces données et remplir l\'entité vide qu\'on
a créé tout au debut pour, par exemple, faire un CRUD

Pour analyser l\'objet Request on utiliser la méthode **handleRequest**,
auquel on envoie l\'objet Request injecté dans l\'action. Les méthodes
**isSubmitted** et **isValid** nous indiquerons si le formulaire a été
submitted (on a cliqué sur le bouton) et si les données du formulaire
sont valides (en principe on recevra toujours **true** car on n\'a fait
aucune règle de validation).

Il faut remarquer qu\'on aura normalement au moins **deux templates** :
un pour le rendu du formulaire et l\'autre pour afficher le résultat du
traitement du formulaire.

Voici le code qui implémente ce qu\'on vient de décrire : le controller,
les templates et la classe du formulaire.

1.  **Controller :**

/\*\*

\* \@Route (\"/exemples/formulaires/traitement/exemple/livre\",name =
\"exemple\_livre\");

\*/

// dans la même action on réalise le rendu et la réception

**public** **function** exempleLivre (Request \$req){

// 1. Création d\'une entité vide

\$livre = **new** Livre();

// 2. Création du formulaire du type souhaité

\$formulaireLivre = \$this-\>createForm (LivreType::**class**, \$livre,

\[\'action\'=\> \$this-\>generateUrl (\"exemple\_livre\"),

\'method\'=\>\'POST\'\]);

// 3. Analyse de l\'objet Request

\$formulaireLivre-\>handleRequest(\$req);

// 4. Vérification: on vient d\'un submit ou pas?

// si oui, on traite le formulaire et on remplit l\'entité

**if** (\$formulaireLivre-\>isSubmitted() &&
\$formulaireLivre-\>isValid()){

// Remplissage de l\'entité avec les données du formulaire

\$livre = \$formulaireLivre-\>getData();

// Rendu d\'une vue où on affiche les données

// Normalement on faire CRUD ici ou une autre opération\...

**return** \$this-\>render
(\'/exemples\_formulaires\_traitement/traitement\_formulaire\_livre.html.twig\',

\[\'livre\'=\> \$livre\]);

}

// si non, on doit juste faire le rendu du formulaire

**else** {

**return** \$this-\>render
(\'/exemples\_formulaires\_traitement/affichage\_formulaire\_livre.html.twig\',

\[\'formulaireLivre\'=\> \$formulaireLivre-\>createView()\]);

}

}

2.  **Templates (un pour afficher le formulaire et l\'autre pour
    afficher le résultat du traitement)**

{\# affichage\_formulaire\_livre.html.twig \#}

{{ form\_start (formulaireLivre) }}

{{ form\_widget (formulaireLivre) }}

\<input type=\"submit\" **class**=\"btn\" value=\"Envoyer\" /\>

{{ form\_end (formulaireLivre) }}

{\# traitement\_formulaire\_livre.html.twig \#}

{{ dump (livre) }}

3.  **Classe du formulaire**

**class** LivreType **extends** AbstractType {

**public** **function** buildForm(FormBuilderInterface \$builder,
**array** \$options)

{

\$builder-\>add(\'ISBN\', TextType::**class**)

-\>add(\'titre\', TextareaType::**class**)

-\>add(\'prix\', MoneyType::**class**)

-\>add(\'description\', TextareaType::**class**)

-\>add(\'datePublication\', DateType::**class**,\[

\'label\' =\> \'Date de publication\'

\])

-\>add(\'nombrePages\', IntegerType::**class**, \[

\'label\' =\> \'Nombre de pages\',

\'required\' =\> **false**

\])

-\>add(\'langue\', LanguageType::**class**, \[

\'label\' =\> \'Langue du livre\',

\'preferred\_choices\' =\> \[\'es\',\'fr\',\'it\'\]

\])

-\>add (\'format\', ChoiceType::**class**, \[

\'choices\' =\> \[

\'eBook\' =\> \'ebook\',

\'papier\' =\> \'papier\'

\],

// les combinaisons de ces paramètres détermineront

// le type de

// liste de choix : liste, liste déroulante, checkbox ou

// radiobuttons

\'expanded\' =\> **false**,

\'multiple\' =\> **true**

\]);

//-\>add(\'Envoyer\', SubmitType::class);

}

}

**Résumé : Traitement de données d\'un formulaire dans une action d\'un
controller**

1.  Créez une **entité vide**

2.  Créez **une instance du formulaire**

3.  Faites appel à **handleRequest pour traiter la requête** **et faire
    submit** du Form. HandleRequest remplit les champs de l\'objet
    formulaire à partir de l\'objet Request **si on a fait submit**.
    Dans ce cas, on peut obtenir ces données avec **getData** et les
    affecter à l\'entité crée dans 1).

Une fois l\'entité a été créé à partir des données on peut faire
n\'importe quelle action (CRUD ou une autre).

Si on arrive à l\'action sans avoir faire un submit (exemple : tapez
l\'URL de l\'action dans le navigateur) ou les données ne sont pas
valides (isSubmitted ou isValid renvoient faux), on doit juste envoyer
le formulaire à la vue pour réaliser le rendu.

#### Exercices : traitez toutes les données du formulaire que vous avez créés dans l\'exercice précédant

Bonnes pratiques pour créer de formulaires en Symfony
-----------------------------------------------------

1.  **Ne rajoutez de boutons aux formulaires dans les classes des
    formulaires ni dans les controllers**, mais dans les templates.

> Exemple : Si vous créez un formulaire pour insérer un client dans la
> BD et vous créez un bouton \"insérer\" dans la classe du formulaire,
> ce formulaire ne pourra plus être utilisé pour par exemple mettre à
> jour le client... bien qu\'il s\'agit du même formulaire pour les deux
> actions ! Rajouter les boutons dans les controllers est aussi une
> mauvaise idée car vous allez mélanger logique et présentation
> (\"vues\"). Il nous reste alors que les rajouter dans les fichiers
> twigs (en HTML)

2.  Utilisez **une même action pour créer le formulaire et le traiter**

3.  Pour définir l\'action et la méthode (différente, par exemple, pour
    un update et un delete), vous pouvez envoyer de paramètres à
    **form\_start** dans le fichier twig

> {{ **form\_start**(form, {**\'action\': path(\'rajouter\'),
> \'method\': \'POST\'**}) }}
>
> **Attention :** Le **path** sera le **name** d\'une route

Style des formulaires
---------------------

> Vous pouvez appliquer du style aux formulaires en utilisant du CSS.
> Symfony inclut plusieurs templates. Plus d\'information ici :

<https://symfony.com/doc/current/form/form_themes.html#symfony-builtin-forms>

Formulaires concernant plusieurs entités
----------------------------------------

Considérons que les Genres sont aussi des entités de la BD (un Genre a
un nom et une description). Comment faire si on veut créer un formulaire
pour insérer un livre et choisir au même temps son genre dans le
formulaire ? Le genre est un objet (entité) !

La solution est **d\'utiliser** **le** **type** **EntityType**, qui nous
permettra **d\'envoyer une entité** de notre choix **dans le
formulaire**.

<https://symfony.com/doc/current/reference/forms/types/entity.html>

Créez une nouvelle entité Genre (contenant **nom** et **description**)
et **une association d\'un a plusieurs avec Livre** (on va considérer
qu\'un livre à juste un genre). **Ici on veut pouvoir envoyer une entité
Genre pour pouvoir l\'incruster dans l\'entité Livre.**

Créons une classe de formulaire **LivreGenreType** à partir de
**LivreType** et faisons les modifications nécessaires (explication
après le code) :

**class** LivreGenreType **extends** AbstractType {

**public** **function** buildForm(FormBuilderInterface \$builder,
**array** \$options)

{

\$builder-\>add(\'ISBN\', TextType::**class**)

-\>add(\'titre\', TextareaType::**class**)

-\>add(\'prix\', MoneyType::**class**)

-\>add(\'description\', TextareaType::**class**)

-\>add(\'datePublication\', DateType::**class**,\[

\'label\' =\> \'Date de publication\'

\])

-\>add(\'nombrePages\', IntegerType::**class**, \[

\'label\' =\> \'Nombre de pages\',

\'required\' =\> **false**

\])

-\>add(\'langue\', LanguageType::**class**, \[

\'label\' =\> \'Langue du livre\',

\'preferred\_choices\' =\> \[\'es\',\'fr\',\'it\'\]

\])

-\>add (\'format\', ChoiceType::**class**, \[

\'choices\' =\> \[

\'eBook\' =\> \'ebook\',

\'papier\' =\> \'papier\'

\],

\'expanded\' =\> **false**,

\'multiple\' =\> **true**

\])

**-\>add (\'genre\', EntityType::class, \[**

**\'class\' =\> Genre::class,**

**\'query\_builder\' =\> function (GenreRepository \$er){**

**return**

> **\$er-\>createQueryBuilder(\'u\')-\>orderBy (\'u.nom\',\'DESC\');**

**},**

> // on affiche ici les noms et les descriptions en majuscules,
>
> // mais c\'est à vous de choisir la façon de l\'afficher

**\'choice\_label\' =\> function (\$x){**

**return strtoupper(\$x-\>getNom() . \"-\". \$x-\>getDescription());**

**}**

**\]);**

}

}

**Explication :**

1.  On rajoute un champ du type EntityType qui portera le nom du champ
    de l\'association

2.  On spécifie la classe de cet Entité (ici, \"Genre\")

3.  Dans la clé **query\_builder**, on crée une fonction qui, en
    utilisant un QueryBuilder, **renvoie** un ensemble d\'objets
    \"Genre\" (voir la section consacrée au QueryBuilder)

4.  Chaque objet contenu dans la requête sera passé à fonction spécifiée
    dans **choice\_label**. Le contenu renvoyé par cette fonction
    s\'affichera comme option dans la liste déroulante.

Voici le code du **Controller** :

**class** ExemplesFormulairesObjetsController **extends**
AbstractController

{

/\*\*

\* \@Route (\"/exemples/formulaires/objets/traitement/livre/genre\");

\*/

// dans la même action on réalise le rendu et la réception

**public** **function** exempleLivre (Request \$req){

// 1. Création d\'une entité vide

\$livre = **new** Livre();

// 2. Création du formulaire du type souhaité

\$formulaireLivre = \$this-\>createForm (LivreGenreType::**class**);

// 3. Analyse de l\'objet Request

\$formulaireLivre-\>handleRequest(\$req);

// 4. Vérification: on vient d\'un submit ou pas?

// si oui, on traite le formulaire et on remplit l\'entité

**if** (\$formulaireLivre-\>isSubmitted() &&
\$formulaireLivre-\>isValid()){

// Remplissage de l\'entité avec les données du formulaire

\$livre = \$formulaireLivre-\>getData();

// Rendu d\'une vue où on affiche les données

// Normalement on faire CRUD ici ou une autre opération\...

**return** \$this-\>render
(\'/exemples\_formulaires\_objets/traitement\_formulaire\_livre.html.twig\',

\[\'livre\'=\> \$livre\]);

}

// si non, on doit juste faire le rendu du formulaire

**else** {

**return** \$this-\>render
(\'/exemples\_formulaires\_objets/affichage\_formulaire\_livre.html.twig\',

\[\'formulaireLivre\'=\> \$formulaireLivre-\>createView()\]);

}

}

}

Voici le code des **templates** :

{\# affichage\_formulaire\_livre.html.twig \#}

{{ form\_start (formulaireLivre) }}

{{ form\_widget (formulaireLivre) }}

\<input type=\"submit\" **class**=\"btn\" value=\"Envoyer\" /\>

{{ form\_end (formulaireLivre) }}

{\# traitement\_formulaire\_livre.html.twig \#}

{{ dump (livre) }}

[]{#_Toc4669804 .anchor}

Upload de fichiers en utilisant un formulaire
=============================================

Dans cette section on propose une méthode pour pouvoir faire upload de
fichiers du client au serveur en utilisant un formulaire crée par
Symfony.

La documentation pour ce faire se trouve ici :

<https://symfony.com/doc/current/controller/upload_file.html>

Mais nous allons développer nos propres exemples.

Stockage dans le serveur d\'une seule image pour chaque entité 
--------------------------------------------------------------

**Objectif :** Pouvoir faire upload d\'une image pour chaque entité dans
la BD.

On va créer une entité (Pays) et un formulaire qui nous permettra de
faire upload d\'une image associée à cette entité (une image pour chaque
pays). Notre action stockera le nom du pays et le lien vers l\'image
dans la BD, ainsi que le fichier en soi dans un dossier du serveur.

**Procédure :**

1.  **Créez l\'entité** (Pays, contenant le **nom** du pays et un champ
    **lienImage** pour stocker **le lien** de l\'image. Les deux sont du
    type string)

**Important: effacez la specification des types (paramètres et retour)
dans les méthodes set et get de lienImage**

2.  Générez les entités et mettez à jour le schéma de la BD

3.  **Créez la classe du formulaire** pour cette entité (PaysType.php).
    Pour le champ **uneImage, choisissez FileType**, et rajoutez un
    bouton de submit.

**namespace** App\\Form;

**use** Symfony\\Component\\Form\\AbstractType;

**use** Symfony\\Component\\Form\\Extension\\Core\\Type\\TextType;

**use** Symfony\\Component\\Form\\Extension\\Core\\Type\\**FileType**;

**use** Symfony\\Component\\Form\\FormBuilderInterface;

**class** PaysType **extends** AbstractType

{

**public** **function** buildForm (FormBuilderInterface \$builder,
**array** \$options)

{

\$builder-\>add(\'nom\', TextType::**class**)

-\>add(\'lienImage\', **FileType**::**class** , **array**
(\'label\'=\>\"Sélectionner l\'image du pays\"));

}

}

4.  Créez **un fichier twig capable d\'afficher ce formulaire**

{\# affichage\_formulaire upload.html.twig \#}

{{ form\_start (formulaire) }}

{{ form\_widget (formulaire) }}

\<input type=\"submit\" **class**=\"btn\" value=\"Envoyer\" /\>

{{ form\_end (formulaire) }}

5.  Créez **une action qui traite les données envoyées par le
    formulaire**

Cette action doit :

-   **Créer un objet formulaire** (PaysType) **associé à une entité
    vide** (\$pays de la classe Pays)

-   **Gérer la requête :** HandleRequest remplira les propriétés de
    l\'entité (hydrate)

-   **Vérifier que le formulaire a été envoyé** (isSubmitted) **et si
    les données sont valables** (isValid).

-   **Obtenir le fichier** (**objet UploadedFile**, pas un string) **de
    l\'entité** associée au formulaire

    -   **Obtenir un nom de fichier unique** pour le stocker dans le
        serveur (si on utilise le nom original il pourrait y avoir plein
        de doublons !)

    -   **Stocker le fichier dans le serveur**

-   **Affecter la propriété contenant le fichier dans l\'entité et lui
    donner le nom unique qu\'on vient d\'obtenir**

-   **Stocker l\'objet dans la BD**

Voici le code de l\'action :

**namespace** App\\Controller;

**use**
Symfony\\Bundle\\FrameworkBundle\\Controller\\AbstractController;

**use** Symfony\\Component\\Routing\\Annotation\\Route;

**use** Symfony\\Component\\HttpFoundation\\Request;

**use** App\\Entity\\Pays;

**use** App\\Form\\PaysType;

**use** Symfony\\Component\\HttpFoundation\\Response;

**class** ExemplesFormulaireUploadController **extends**
AbstractController

{

/\*\*

\* \@Route (\"/exemples/formulaire/upload/exemple\");

\*/

**public** **function** exemple (Request \$request){

// créer une nouvelle entité vide

\$pays = **new** Pays();

// créer un formulaire associé à cette entité

\$formulairePays = \$this-\>createForm (PaysType::**class**, \$pays);

// gérer la requête (et hydrater l\'entité)

\$formulairePays-\>handleRequest(\$request);

// vérifier que le formulaire a été envoyé (isSubmitted)

// et que les données sont valides

**if** (\$formulairePays-\>isSubmitted() &&
\$formulairePays-\>isValid()){

// obtenir le fichier (pas un \"string\" mais un

// objet de la class UploadedFile)

\$fichier = \$pays-\>getLienImage();

// obtenir un nom de fichier unique

// pour éviter les doublons dans le dossier

\$nomFichierServeur =
**md5**(**uniqid**()).\".\".\$fichier-\>guessExtension();

// stocker le fichier dans le serveur (on peut indiquer un dossier)

\$fichier-\>move (\"dossierFichiers\", \$nomFichierServeur);

// affecter le nom du fichier de l\'entité. Ça sera le nom qu\'on

// aura dans la BD (un string, pas un objet UploadedFile cette fois)

\$pays-\>setLienImage(\$nomFichierServeur);

// stocker l\'objet dans la BD, ou faire update

\$em = \$this-\>getDoctrine()-\>getManager();

\$em-\>persist(\$pays);

\$em-\>**flush**();

**return** **new** Response (\"fichier uploaded et BD mise à jour!\");

}

**else** {

**return** \$this-\>render
(\"/exemples\_formulaires\_upload/affichage.html.twig\",

\[\'formulaire\'=\> \$formulairePays-\>createView()\]);

}

}

}

Problèmes dans l\'upload
------------------------

Nous pouvons avoir de problèmes liés à certaines limites concernant la
taille des fichiers qu\'on peut charger dans le serveur.

1.  Dans **php.ini**, **upload\_max\_filesize** spécifie la taille
    maximale accepté par le module de php

; Maximum allowed size for uploaded files.

; [http://php.net/upload-max-filesize]{.underline}

**upload\_max\_filesize**=20M

2.  Dans **php.ini**, **post\_max\_size** indique la taille maximale
    d\'un formulaire envoyé en POST (avec ou sans le champ d\'upload)

; Maximum size of POST data that PHP will accept.

; Its value may be 0 to disable the limit. It is ignored if POST data
reading

; is disabled through enable\_post\_data\_reading.

; [http://php.net/post-max-size]{.underline}

**post\_max\_size**=20M

Notez que, en ce qui concerne l\'upload d\'un fichier, ça ne vous sert à
rien de changer le premier paramètre sans changer le deuxième car il
faut que le serveur admette un post contenant un fichier d\'au moins la
taille permise par **upload\_max\_filesize.**

Si on a un formulaire avec un champ d\'upload, la taille du POST sera,
en gros, celle du fichier envoyé plus celle de tous les autres champs du
formulaire.

Après avoir augmenté la valeur de ces deux paramètres on ne doit plus
avoir de problèmes, mais si ce n\'est pas le cas il faut considérer
aussi les paramètres suivants :

3.  Dans certains cas il faut considérer aussi la limite pour la taille
    du fichier **.php** qu\'on peut charger (en **php.ini**)

; Maximum amount of memory a script may consume (128MB)

; [http://php.net/memory-limit]{.underline}

memory\_limit=128M

4.  Il peut avoir aussi un problème si la connexion du client est lente
    et l\'upload prend plus du temps spécifié dans **max\_input\_time**
    (**php.ini**). Ce paramètre indique le temps maximum permis pour
    analyser les données du POST ou GET: c\'est le temps qui passe entre
    l\'appel au script PHP et le début de son exécution. Dans la
    configuration de XAMPP la valeur est -1, il n\'y a pas de limite de
    temps.

AJAX en Symfony
===============

**Objectif** : utiliser AJAX dans un template Twig

Créez un controller **ExemplesAjaxFormDataController** (code original
dans le projet **projetFormulaires**). Ce controller contiendra
uniquement quelques exemples d\'appel Ajax. Plus tard on réalisera des
exemples plus pratiques basés sur la BD du projet.

Exemple d\'appel AJAX avec un formulaire
----------------------------------------

> Dans cet exemple on envoie de données en utilisant AJAX **sans
> utiliser un formulaire**. Nous avons juste les contrôles. Dans la
> section suivante on utilisera un formulaire complet

1.  **Créez une vue contenant du code AJAX**

> Exemple : on tapera un nom dans l\'input et, quand on clique sur le
> bouton, un message de bienvenue sera affiché dans le div. Analysez
> vous-même le code.
>
> Attention aux **names** des contrôles car on les utilisera dans le
> traitement de l\'action dans le controller!!
```html
javascript
<form id=**\"leFormulaire\"** method=**\"POST\"**\>
<input type=**\"text\"** id=**\"inputNom\"** name=**\"nom\"** /\>
<input type=**\"submit\"** id=**\"envoyerNom\"**
value=**\"Envoyer\"**/\>
</form\>
<div id=**\"divMessage\"**\>\</div\>
```
```javascript
<script>
envoyerNom.addEventListener **(**\"click\"**,** ***function***
**(**event**){**

// on annule l\'effet du submit

event.preventDefault**();**

***var*** xhr **=** ***new*** XMLHttpRequest **();**

// on crée un formulaire à partir de celui du DOM

***var*** formulaire **=** ***new*** FormData **(**leFormulaire**);** //
accès direct, on peut aussi utiliser getElementById

xhr.onreadystatechange **=** ***function*** **(){**

console.log **(**xhr.status**);**

***if*** **(**xhr.readyState **==** 4**){**

***if*** **(**xhr.status **==** 200**){**

// transformer le string JSON envoyé par le serveur

// comme réponse en objet JavasScript

***var*** reponse **=** JSON.parse **(**xhr.responseText**);**

divMessage.innerHTML **=** reponse.message**;**

console.log **(**reponse**);**

console.log **(*typeof*(**reponse**));**

**}**

// s\'il y a une erreur:

***else*** **{**

// effacer en production!

console.log **(**xhr.reponseText**);**

**}**

**}**

**}**

xhr.open
**(**\'POST\'**,**\'/exemples/ajax/form/data/exemple1/traitement\'**);**

// on envoie l\'objet formulaire

xhr.send **(**formulaire**);**

// xhr.setRequestHeader(\"Content-type\",
\"application/x-www-form-urlencoded\");

//xhr.send (\"nom=\" + inputNom.value);

**});**

\</script\>

2.  Créez l\'action **exemple1Affichage**, qui renvoie le rendu de la
    vue exemple1\_affichage.html

/\*\*

\* \@Route (\"/exemples/ajax/form/data/exemple1/affichage\");

\*/

**public** **function** exemple1Affichage (){

**return** \$this-\>render
(\"/exemples\_ajax\_form\_data/exemple1\_affichage.html.twig\");

}

3.  Créez l\'action **exempleTraitementAjax** qui traite la pétition
    AJAX

/\*\*

\* \@Route (\"/exemples/ajax/form/data/exemple1/traitement\");

\*/

// action qui traite la commande AJAX, elle n\'a pas une vue associée

**public** **function** exemple1Traitement (Request \$requeteAjax){

\$valeurNom = \$requeteAjax-\>get (\'nom\');

\$arrayReponse = \[\'message\' =\> \'Bienvenu, \' . \$valeurNom\];

**return** **new** JsonResponse (\$arrayReponse);

}

Utilisation de blocs dans twig avec AJAX
----------------------------------------

Il s\'agit juste d\'une combinaison de master page + AJAX, rien de
nouveau.

1.  Créez un template master\_page.html.twig contenant une section pour
    nos vues. Créez un block pour le contenu et un autre pour le JS

\<html\>

\<body\>

\<header\>

**Voici la section header**

\</header\>

\<main\>

**Voici la section main**

**{% block contenuMain %}{% endblock %}**

\</main\>

\<footer\>

**Voici la section footer**

\</footer\>

\</body\>

**{% block javascripts %}{% endblock %}**

\</html\>

2.  **Créez une vue** exemple1\_affichage\_master\_page.html.twig **qui
    hérite du template** master\_page.html.twig

{% **extends** \'/exemples\_ajax/master\_page.html.twig\' %}

{% block contenuMain %}

Nom\<input type=\"text\" id=\"inputNom\" /\>

\<button id=\"envoyerNom\"\>Envoyer\</button\>

\<div id=\"divMessage\"\>\</div\>

{% endblock %}

3.  Rajoutez le code Ajax dans un bloc **javascripts** dans la même vue,
    le code doit faire appel à une action dans le controller qui gére la
    petition Ajax.

{% block javascripts %}

envoyerNom.addEventListener (\"click\", **function** (event){

**var** xhr = **new** XMLHttpRequest ();

xhr.onreadystatechange = **function** (){

**if** (xhr.readyState == 4){

**if** (xhr.status == 200){

// transformer le string JSON envoyé par le serveur

// comme réponse en objet JavasScript

**var** reponse = JSON.parse (xhr.responseText);

divMessage.innerHTML = reponse.message;

console.log (reponse);

console.log (typeof(reponse));

}

// s\'il y a une erreur:

**else** {

// effacer en production!

console.log (xhr.reponseText);

}

}

}

xhr.open (\'POST\',\'/exemples/ajax/exemple1/traitement/master/page\');

xhr.setRequestHeader(\"Content-type\",
\"application/x-www-form-urlencoded\");

xhr.send (\"nom=\" + inputNom.value);

});

{% endblock %}

Notez que dans le code Ajax on doit réaliser l\'opération pertinente
avec les données reçues du serveur (ex : afficher dans un div)

4.  Créez l\'action qui affiche la vue qu\'on vient de créer

/\*\*

\* \@Route (\"/exemples/ajax/exemple1/affichage/master/page\");

\*/

**public** **function** exemple1AffichageMasterPage (){

**return** \$this-\>render
(\"/exemples\_ajax/exemple1\_affichage\_master\_page.html.twig\");

}

5.  Créez l\'action qui traite la demande AJAX

Dans cette action, renvoyez votre réponse JSON. Pour ce faire, au lieu
d\'envoyer un objet Response ou le rendu d\'une vue, vous allez utiliser
un objet JSonResponse. Par exemple :

/\*\*

\* \@Route (\"/exemples/ajax/exemple1/traitement/master/page\");

\*/

// action qui traite la commande AJAX, elle n\'a pas une vue associée

**public** **function** exemple1TraitementMasterPage (Request
\$requeteAjax){

\$valeurNom = \$requeteAjax-\>get (\'nom\');

\$arrayReponse = \[\'message\' =\> \'Bienvenu, \' . \$valeurNom\];

**return** **new** JsonResponse (\$arrayReponse);

}

Pour finir, sachez que les fichiers .**js** et .**css** sont considérés
comme des \"assets\" en Symfony. Pour pouvoir en rajouter dans notre
projet vous devez créer les dossiers **public/assets/js** et
**public/assets/css** respectivement et y placer vos fichiers. Dans vos
vues, inclure les fichiers est simple :

\<script src=**\"{{ asset(\'/assets/js/monFichier.js\')
}}\"**\>\</script\>

\<link rel=**\"stylesheet\"** href=**\"{{
asset(\'/assets/css/monCss.css\') }}\"** /\>

Vous avez des exemples dans le projet **projetFormulaires (controller
ExemplesAjaxController)**

#### Exercice 1 : faites un jeu de deviner un chiffre en utilisant Ajax en Symfony (utilisez le controller AjaxExemples)

#### Exercice 2 : créez une autre master page et deux vues qui en héritent. La première contient le jeu que vous venez de réaliser et la deuxième contient trois boutons. Chaque bouton affiche la photo d\'un animal sans recharger la page.

Renvoi d\'un array d\'objets en JSON
------------------------------------

**Exemple** : obtenir une liste de livres et les afficher dans un div,
style recherche de google (les résultats s\'affichent dans un div au fur
et à mesure selon le contenu de l\'input change)

**Code :**

-   **Projet** projetFormulaires

-   **Controller** ExemplesAjax, actions exempleRenvoiEntite et
    exempleRenvoiEntiteTraitement

-   **Vue** exemple\_renvoi\_entite.html.twig

Dans la vue, en utilisant l\'event keyup on détecte chaque pulsation de
la personne dans l\'input et en envoie une requête contenant le text qui
se trouve dans l\'input.

Du côté serveur on doit chercher tous les livres qui contiennent le text
de l\'input dans le titre et **envoyer une réponse JSON**.

Considérons cette requête en DQL pour obtenir les livres :

\$query = \$em-\>createQuery (\"SELECT livre FROM App\\Entity\\Livre
livre WHERE\".

\" livre.titre LIKE :titre\");

\$query-\>setParameter (\'titre\', \'%\'.\$titre.\'%\');

\$resultat = \$query-\>**getResult**();

On obtient un array d\'objets entités où chaque entité contiendra aussi
les relations avec les autres entités ainsi que d\'autres objets comme
propriétés. Si on fait un dump dans le serveur :

![](media/image33.png){width="3.634615048118985in"
height="3.3108584864391952in"}

Si on applique JSON.Parse sur la réponse envoyée par le serveur on
obtient une sorte de représentation de l\'entité complète, ce qui ne
nous convient pas :

![](media/image34.png){width="4.541666666666667in"
height="2.6577755905511813in"}

La **solution est de générer un array à partir du résultat de la requête
DQL en utilisant la fonction getArrayResult au lieu de getResult** dans
le controller :

\$query = \$em-\>createQuery (\"SELECT livre FROM App\\Entity\\Livre
livre WHERE\".

\" livre.titre LIKE :titre\");

\$query-\>setParameter (\'titre\', \'%\'.\$titre.\'%\');

\$resultat = \$query-\>getArrayResult();

Ça nous permet d\'obtenir un simple array d\'arrays dont les propriétés
sont accessibles facilement (voir le code du twig).

![](media/image35.png){width="3.9652777777777777in"
height="2.5166918197725283in"}

Doctrine Fixtures
=================

> Doctrine fournit un outil qui nous permet **d\'encoder de données dans
> la base de données d\'une façon semi-automatique**, ce qui est très
> **utile pendant les périodes de développement et de test de
> l\'application**.

Le fonctionnement est simple : **si on veut encoder de données pour une
classe d\'entité** existante (ex : Livres) on **demande à Doctrine de
créer une class Fixture** (ex : LivresFixtures) qui contient au moins
une **méthode load**. Dans cette méthode (à remplir par nous)
**contiendra le code qui insère** les données dans la BD. Puis on
appelle cette fonction et les données seront stockés dans la BD.

Ce système a plusieurs avantages :

-   On peut appeler la méthode génératrice autant de fois qu\'on veut

-   Le code qui crée les données de la BD se trouve localisé

-   On peut générer les données pour toutes les entités du projet avec
    une seule commande (si on a créé la Fixture pour chaque entité, bien
    sûr).

Toute la documentation sur les fixtures se trouve ici :

<https://symfony.com/doc/master/bundles/DoctrineFixturesBundle/index.html>

mais on va développer un exemple simple et associé à une classe
d\'entité qui nous servira plus tard.

#### Exemple : Création d\'une fixture 

On va créer et lancer une fixture pour l\'entité **Pays** dans le projet
**projetFormulaires**. Si l\'entité n\'existe pas, créez la d\'abord
(Pays: nom et lienImage). Suivez cette procédure :

a.  Installez le **support** pour les **fixtures**

> composer require \--dev doctrine/doctrine-fixtures-bundle

b.  **Créez la classe fixture** (nom: PaysFixture)

> php bin/console make:fixture

c.  **Editez** la function **load** pour qu\'elle stocke de Pays. Voir
    cet exemple :

**namespace** App\\DataFixtures;

**use** Doctrine\\Bundle\\FixturesBundle\\Fixture;

**use** Doctrine\\Common\\Persistence\\ObjectManager;

**use** App\\Entity\\Pays;

**class** PaysFixtures **extends** Fixture

{

// load créera et stockera 20 pays dans la BD

**public** **function** load(ObjectManager \$manager)

{

**for** (\$i = 0; \$i \< 20; \$i++){

\$pays = **new** Pays ();

\$pays-\>setNom (\"Belgique\" . \$i);

\$pays-\>setLienImage (\"belgique\" . \$i . \".jpg\");

\$manager-\>persist(\$pays);

}

\$manager-\>**flush**();

}

}

d.  **Lancez les fixtures**

> php bin/console doctrine:fixtures:load \--append
>
> \--append permet de lancer la fixture sans effacer les données
> existantes dans les tableaux. Si vous l\'enlevez vous effacerez le
> contenu de votre BD (Symfony vous previent quand-même)
>
> Ici on a qu\'une fixture mais on pourrait avoir plein.

e.  Vérifiez que les données sont insérées dans la BD

#### Exercices :

1.  Créez une classe Fixture qui permette de rajouter automatiquement
    des objets d\'une classe de votre choix

Authentification : inscription et login/password
================================================

> On va créer un projet (projetLoginPass) contenant :

1.  Un formulaire de login/password traditionnel

2.  Un formulaire d\'inscription pour rajouter des utilisateurs dans la
    BD

**Important :** Vous devez avoir au moins la version 10.2 de MariaDB.
Pour mettre à jour votre version de MariaDB pour xampp suivez les
instructions qui se trouvent ici **dans sa totalité** :

<https://stackoverflow.com/questions/44027926/update-xampp-from-maria-db-10-1-to-10-2>

Configuration de la sécurité et création d\'un formulaire de login
------------------------------------------------------------------

> On va réaliser une configuration de base de la sécurité pour pouvoir
> créer un formulaire d\'inscription/login standard. Pour des options
> plus avancés (ex : changez d\'utilisateur sans devoir se déconnecter
> de l\'application) consultez la documentation ici :
>
> <https://symfony.com/doc/current/security.html>
>
> <https://symfony.com/doc/current/security/form_login_setup.html>
>
> La procédure à suivre doit :

1.  **Installer le support de sécurité dans le projet**

2.  **Créer** **une** **entité** **User** avec l\'assistant

3.  **Créer** (avec l\'assistant)

    -   Un **controller** pour le **login** et une route

    -   Un **template pour afficher le formulaire** de login

    -   Un **Guard Authenticator**, **classe** qui **traite les
        informations** du formulaire de login

```{=html}
<!-- -->
```
4.  **Encoder des utilisateurs et de passwords dans la BD**

5.  **Vérifier** le bon fonctionnement en tapant un couple login/pass
    valable

> Réalisez la procédure en détail :

1.  **Installer le support de sécurité dans le projet**

composer require symfony/security-bundle

2.  **Créer** **une** **entité** **User** avec l\'assistant avec
    make:user (pas make:entity!)

php bin/console make:user

Cette commande crée l\'entité, qui **doit** implémenter l\'interface
[UserInterface](https://github.com/symfony/symfony/blob/4.2/src/Symfony/Component/Security/Core/User/UserInterface.php)

> (Faites la migration pour que la BD soit mise à jour!)
>
> L\'assistant vous demandera :

-   Le nom de la classe (on choisira User)

-   Si vous voulez stocker de données dans la BD avec Doctrine (oui!)

-   La propriété qu\'on utilisera pour réaliser le login (on choisira
    email)

-   Si on souhaite hasher les passwords (oui!)

> Ouvrez **src/Entity/User.php** et regardez le code. Vous pouvez par
> après rajouter d\'autres propriétés ou méthodes si vous le souhaitez.
>
> L\'assistant aura modifié aussi le fichier **security.yaml** (dans
> **config/packages**) selon les informations qu\'on vient de fournir.

3.  **Créer le controller, le template et un Guard Authenticator
    (assistant)** :

    -   Un **controller** pour le **login** et **une** **route**

    -   Un **template pour afficher le formulaire** de login

    -   Un **Guard Authenticator**, **classe** qui **traite les
        informations** du formulaire de login

Ces trois pas se font avec une seule commande :

> php bin/console make:auth

Pour les questions posées par l\'assistant on choisira :

-   **L\'option** **1** pour que Symfony crée un formulaire et pas le
    système d\'authentification vide

-   **FormulaireLoginAuthenticator** comme nomme de la classe

-   **SecuriteController** comme nom du controller

> Cette action met aussi à jour le fichier de configuration
> config/packages/**security.yaml**, observez-le par vous-mêmes.
>
> Observez que le controller et le template ont été créés. Vous pouvez
> accéder à la vue contenant le formulaire de login en tapant la route
> de l\'action **login** du controller.

4.  **Encoder des utilisateurs et de passwords dans la BD**

Créez une fixture pour la classe User (voir chapitre précédant sur le
Doctrine Fixtures)

Doc: <https://symfony.com/doc/current/security.html> (2c)

> Dans ce cas, la fonction **load** devra créer un utilisateur, fixer
> ses attributs et le stocker dans la BD. Nous devons utiliser un
> service pour encoder le password avant d\'appeler à setPassword. Le
> service est injecté dans le constructeur de la classe (dependency
> injection par constructeur!!).
>
> Voici un code possible pour la Fixture **UserFixtures.php** :

**namespace** App\\DataFixtures;

**use** Doctrine\\Bundle\\FixturesBundle\\Fixture;

**use** Doctrine\\Common\\Persistence\\ObjectManager;

**use** App\\Entity\\User;

**use**
Symfony\\Component\\Security\\Core\\Encoder\\UserPasswordEncoderInterface;

**class** UserFixtures **extends** Fixture

{

**private** \$passwordEncoder;

**public** **function** **\_\_construct**(UserPasswordEncoderInterface
\$passwordEncoder)

{

\$this-\>passwordEncoder = \$passwordEncoder;

}

**public** **function** load(ObjectManager \$manager)

{

**for** (\$i = 0; \$i \< 10 ; \$i++){

\$user = **new** User();

\$user-\>setEmail (\"user\".\$i.\"\@lala.com\");

\$user-\>setPassword(\$this-\>passwordEncoder-\>encodePassword(

\$user,

\'lepassword\'.\$i

));

\$manager-\>persist (\$user);

}

\$manager-\>**flush**();

}

}

N\'oubliez pas de lancer la fixture avec :

> php bin/console doctrine:fixtures:load

**Note** : Si vous voulez obtenir en console le hash d\'un password
concret tapez :

php bin/console security:encode-password

et puis tapez le password. Vous pouvez par après le copier-coller dans
la table (colonne password)

5.  **Vérifier** le bon fonctionnement en tapant un couple login/pass
    valable

> Allez sur la page de login et tapez un couple login/pass valable. Si
> tout va bien vous allez obtenir une Exception car dans votre
> controller Authenticator (**FormulaireLoginAuthenticator**) vous
> n\'avez pas spécifié une Response pour le serveur (méthode
> **onAuthenticationSuccess**)
>
> Si le couple login/pass n\'est pas correcte, la variable **error**
> reçue **par la vue** aura la valeur true dans. Dans ce template il y a
> même un appel AJAX qui mettra dans un div un message sur l\'erreur qui
> s\'est produite (ex: mail inexistant, invalid credentials si le
> password n\'est pas correcte...).
>
> On peut choisir par nous-mêmes quoi faire s\'il y a un erreur, il
> suffit de vérifier la valeur de cette variable et agir consequemment
> (afficher un message d\'erreur, rédiriger vers un autre site etc...).
> On peut aussi juste établir une traduction pour les messages d\'erreur
> de base de Symfony, car par défaut ils seront en anglais!

1.  Changer la variable **locale** de **en** à **fr** dans
    **config/services.yaml**

2.  Créez un fichier contenant les traductions des messages selon le
    **locale** (voir **translations/security.fr.xlf** dans
    **projetLoginPass**)

> Maintenant, à chaque fois qu\'un service de Symfony renvoie un message
> il lira le fichier de traductions. Nous avons qu\'à rajouter la
> traduction de chaque message en francáis.
>
> Le service de traduction merite d\'une section à part qu\'on ne
> traitera pas dans ce tuto.
>
> <https://symfony.com/doc/current/translation.html> (voir la section
> **Basic Translation**).

Création d\'un formulaire d\'inscription
----------------------------------------

> Vous pouvez créer un formulaire d\'inscription automatiquement et le
> personnaliser après en suivant les instructions de cette documentation
> :
>
> <https://symfony.com/doc/current/doctrine/registration_form.html>
>
> Si vous n\'avez pas réalisé les opérations du chapitre précédente,
> suivez au moins les pas 1,2,3 pour configurer la sécurité dans
> Symfony, créer l\'entité User et le Guard Authenticator.
>
> Voici la continuation de la procédure, qui créera un formulaire
> d\'inscription :

a.  Lancez, dans la console :

php bin/console make:registration-form

> L\'assistant créera :

-   Une classe formulaire (**RegistrationFormType**)

-   Un controller qui crée l\'objet formulaire et le renvoie à la vue

-   Un template qui affiche le formulaire

> A ce stade de la formation vous savez comment éditer le formulaire
> pour l\'adapter à vos besoins.

Logout
======

Les outils de sécurité de Symfony nous permettent d\'implémenter le
logout très facilement :

1)  Rajoutez dans **config/packages/security.yaml** une section qui
    **indique le path à saisir dans l\'URL** **quand on veut réaliser un
    logout** et **la route de l\'action qui sera lancée après avoir fait
    le logout**. \"Faire le logout\" est, en gros, effacer l\'objet User
    de la session. Symfony s\'en chargera de le faire sans votre
    intervention

> **main**:

anonymous: **true**

guard:

authenticators:

\- App\\Security\\FormulaireLoginAuthenticator

**logout:**

**path: /logout**

**target: /page\_logout**

**Important: Respectez l\'indentation dans les fichiers .yaml. Elle est
faite avec des espaces!**

2)  Rajoutez une route dans le fichier **config/packages/routes.yaml**
    (pas routing.yaml!!)

> \#index:
>
> \# path: /
>
> \# controller: App\\Controller\\DefaultController::index
>
> **logout:**
>
> **path: /logout**

3)  Créez l\'action à lancer après le logout (ici **\"**pageLogout\")

> /\*\*
>
> \* \@Route (\"/page\_logout\")
>
> \*/
>
> **public** **function** logout (){
>
> **return** **new** Response (\"Salut! vous n\'êtes plus logué\");
>
> }

Le code \"projetLoginPass\" contient cette fonctionnalité. L\'action
cible se trouve dans SecurityController.

/\*\*

\* \@Route (\"/page\_logout\")

\*/

**public** **function** logout (){

// normalement on fera un render d\'un template

**return** **new** Response (\"Salut! vous n\'êtes plus logué\");

}

Accès à l\'objet User
=====================

Une fois l\'utilisateur est logué vous pouvez obtenir son objet **User**
associé :

1.  Dans le controller

\$this-\>getUser()

2.  Dans la vue

app.user

Les deux méthodes renvoient l\'objet User représentant l\'utilisateur
qui es connecté ou **null** si personne n\'a fait login.

L\'objet User contient **toutes les propriétés et on peut les accéder en
utilisant les gets et sets**.

Par exemple :

{{ dump (app.user) }}

Ces deux instructions donnent les même résultat car app.user.username
est juste un raccourci de Symfony pour user.getUsername()

{{ dump (app.user.getUsername()) }}

{{ dump (app.user.username) }}

Des actions d\'exemple se trouvent dans le projet \"projetLoginPass\",
controller SecurityController

Envoi du mail (Swift Mailer)
============================

> Doc: <https://symfony.com/doc/current/email.html>
>
> Doc sur Gmail et cloud:
> <https://symfony.com/doc/current/email.html#email-using-gmail>

Par défaut, Symfony utilise le module Swift Mailer pour envoyer des
mails (**projetFormulaires**).

#### Exemple : envoi d\'un mail en utilisant Swift Mailer :

1)  Rajoutez **Swift** **Mailer** à votre projet

composer require symfony/swiftmailer-bundle

2)  Le fichier **packages/swiftmailer.yaml** sera mis à jour mais on
    doit configurer les détails de la connexion dans le fichier **.env**

Le format de la connexion le plus habituel est :

MAILER\_URL=smtp://localhost:25?encryption=ssl&auth\_mode=login&username=&password=

Si vous ne disposez pas d\'un serveur mail et vous voulez envoyer des
emails en utilisant Gmail, Symfony permet de le faire en utilisant ce
format :

**MAILER\_URL=gmail://user:password\@localhost**

Exemple :

MAILER\_URL=gmail://developinterface3:Gaucheret3!\@localhost

**Note** : le mot **gmail** n\'est pas un protocole en soi. C\'est juste
un raccourci pour que Swift Mailer utilise le protocole smtp,
sécurisation ssl, login comme méthode d\'authentification et le serveur
smtp.gmail.com

3)  Créez un **controller** contenant une action qui envoie le mail et
    les vues :

**contenu\_mail.html.twig** : le contenu du mail en soi

**envoyer\_mail.html.twig** : la vue à rendre par l\'action (style
\"mail envoyé\" ou autre)

**class** MailController **extends** AbstractController

{

/\*\*

\* \@Route(\"/mail/envoyer/mail\", name=\"envoyer\_mail\")

\*/

**public** **function** envoyerMail(\\Swift\_Mailer \$mailer)

{

\$message = (**new** \\Swift\_Message (\'Hello mail\'))

-\>setFrom (\'developinterface3\@gmail.com\')

-\>setTo (\'developinterface3\@gmail.com\')

-\>setBody (

\$this-\>renderView (

\'mail/contenu\_mail.html.twig\'

),

\'text/html\'

);

\$mailer-\>send(\$message);

**return** \$this-\>render(\'mail/envoyer\_mail.html.twig\');

}

}

4)  

Annexe 1 : Création rapide d\'un projet {#annexe-1-création-rapide-dun-projet .list-paragraph}
=======================================

Voici un schéma de base de comment créer un projet en Symfony :

Création de la structure du projet
----------------------------------

1.  Installez un projet de base contenant Symfony (utiliser Composer)

composer create-project symfony/**website-skeleton** \<nom du projet\>

2.  Créez le virtual host pour apache

3.  Modifiez le fichier hosts de Windows

4.  Vérifiez que le virtual host fonctionne en tapant l\'URL dans le
    navigateur

5.  Installez l\'apache-pack dans votre projet pour établir les régles
    d\'écriture de URL

composer require symfony/apache-pack

> Accepter l\'installation de la \"recette\" (\"recipe\")

6.  Créez le projet dans un IDE (Netbeans, PHPStorm). Choisissez la
    dérniere version disponible de PHP

Création d\'un controller
-------------------------

Vous pouvez créer un controller à la main ou bien utiliser l\'assistant

php bin/console make:controller

Création du modèle
------------------

1.  Créer les entités et les relations entre les entités

> php bin/console make:entity

2.  Configurez la BD dans le fichier **.env** selon vos paramètres de
    phpmyadmin

3.  Rajoutez Doctrine au projet

composer require symfony/orm-pack

composer require symfony/maker-bundle \--dev

4.  Configurez la connexion à la BD dans le fichier **.env**

5.  Lancez la création de la BD

php bin/console doctrine:database:create

6.  Migréz les entités (Doctrine mettra à jour la BD)

php bin/console make:migration

> php bin/console doctrine:migrations:migrate

Création des templates (vues)
-----------------------------

> Créer vos vues dans src/templates. Créez un dossier pour chaque
> controller et utilisez la notation snake case pour nommer les vues

Annexe 2 : Application Demo {#annexe-2-application-demo .list-paragraph}
===========================

Les developpeurs de Symfony fournissent une application demo qui est un
exemple de comment developper une application Symfony en suivant de
bonnes pratiques.

Pour l\'installer, il suffit de l\'installer avec composer:

> composer create-project symfony/symfony-demo symfony-demo
