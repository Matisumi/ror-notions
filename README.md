# Demarrer avec Ruby on ![alt text](https://camo.githubusercontent.com/fe28cc8bfdfb725e588eff149961eb3dfe4101fc/68747470733a2f2f75706c6f61642e77696b696d656469612e6f72672f77696b6970656469612f636f6d6d6f6e732f7468756d622f362f36322f527562795f4f6e5f5261696c735f4c6f676f2e7376672f32303070782d527562795f4f6e5f5261696c735f4c6f676f2e7376672e706e67)
<p><em>mes excuses pour mon contenu denue d'accents je tape sur un clavier qwerty</em></p>
<p><em>j'ai essaye d'utiliser mes mots le plus possible j'espere que ca aidera certains</em></p>

<hr>
 
Index
<ol>
	<li><a href="https://github.com/Matisumi/ror-notions#la-difference-entre-un-site-dynamique-et-un-site-statique-">Site statique/dynamique</a></li>
	<li><a href="https://github.com/Matisumi/ror-notions#le-mvc">Le MVC</a></li>
	<li><a href="https://github.com/Matisumi/ror-notions#les-routes">Les routes</a></li>
	<li><a href="https://github.com/Matisumi/ror-notions#les-bases-de-donnees">Les Bases de donnee</a></li>
	<li><a href="https://github.com/Matisumi/ror-notions#get--post">GET / POST</a></li>
	<li><a href="https://github.com/Matisumi/ror-notions#le-concept-de-migration">La migration</a></li>
	<li><a href="https://github.com/Matisumi/ror-notions#les-relations-entre-les-modeles-des-bdd">Les relation entre modeles de BDD</a></li>
	<li><a href="https://github.com/Matisumi/ror-notions#les-fonctions-du-crud">CRUD</a></li>
</ol>

<hr>

La difference entre un site dynamique et un site statique :
----------------------------------------------------------

Les sites statiques et dynamiques n'ont, en apparence, aucune differences ...
Toute la magie du site dynamique repose dans le contenu de la page appelee :

Dans le cas d'un site statique, lorsque l'on appelle une page, le serveur nous renvoie une page (qui peut etre simplement composee d'html et de css) deja prete stockee dans le serveur. Elle ne variera pas selon l'utilisateur qui l'appelle

A l'inverse sur un site dynamique, lorsqu'une page est appelee, verra son contenu evoluer en fonction de qui l'appelle et des criteres recus lors de l'appel (IP, logins, form ....).
On pourrait prendre comme exemple facebook, qui, si vous etes connecte, affichera le fil d'actualite correspondant a votre profil ou encore le site THP qui affiche votre nom et votre progression dans le cursus ...

<p align="center"><img src ="https://svennd.be/wp-content/uploads/2015/07/25436088-1.png" /></p>

<hr>

Le MVC
-------

Le MVC est une methode d'organisation de son code, cela consiste a separer son code en trois fichiers ayant chacuns un role :

 - Le controleur
 - Le modele
 - La vue

<p align="center"><img  src="http://www.script-tutorials.com/demos/497/MVC.png" /></p>

__Le controleur__ : c'est lui qui va recevoir la requete HTTP (HyperText Transfert Protocol) et orchestrer le processus de reponse. Il va prendre les informations recues demander au modele de verifier/recuperer ce qui est demande et renvoyer les informations a la vue

__Le modele__ : Lui il recois les donnees de la requete HTTP que le controleur lui envoie et lui retourne les donnees demandees en echange. c'est lui qui va faire appel a la base de donnee pour ecrire / recuperer des informations qu'il renvoie par la suite au controleur.

__La vue__ : elle c'est l'etape finale, elle ne fait que renvoyer au controleurla page appelee avec les informations que le controleur lui fournis pour que le controleur renvoie le produit final a l'utilisateur.

<hr>

Les routes
----------

Les routes permettent de renvoyer la page appelee en dechiffrant l'url fourni, elles se configurent dans le fichier config/routes.rb 

La configuration par defaut se fait par la ligne :


	resources :photos

plus d'exemples sur [sois net](https://www.sois-net.fr/routes-ruby-on-rails/)


<hr>

Les Bases de Donnees
--------------------

Les bases de donnees sont un ensemble d'information stokees et structurees afin de pouvoir etre reutilises ou lues informatiquement.

on peut y effectuer plusieurs type d'operations :

- __filtrer__ : recuperer un groupe de donnees selon des criteres fournis 

- __trier__ : reorganiser les donnees selon un ordre precis determine par des criteres

- __repliquer__ : "cloner" (backup) pour par exemple des raisons de securites ou faciliter le tri d'information prenant en compte un grand nombre de criteres

On a deux formats de bases de donnees : 
 - sous forme de fichiers (ex : SQLite)
 - sous forme de logiciel / service (ex : MySQL, MongoDB ...)

 <hr>

GET & POST
----------

GET et POST sont deux metodes de requetes HTTP.

GET envoie une demande pour une ressource particuliere (via URL)
POST envoie des criteres traites par le seveur qui renvoie ce qui est demandee

__Caracteristiques de GET__ :

- peut etre mis en cache
- est enregistre dans l'historique du navigateur (url)
- peut etre enregistre dans les marques pages
- ne doit pas etre utilise pour envoyer des informations sensibles
- est limite en nombre de caracteres (2048)
- ne doit etre utilise que pour recuperer des donnees
- ne prends en compte que l'ascii

__Caracteristiques de POST__ :

- ne peut pas etre mis en cache
- ne s'affiche pas dans l'historique
- ne se sauvegarde pas en marque page
- n'est pas limite en caractere ni a l'ascii

<hr>

Le concept de migration
-----------------------

La migration c'est le fait de deplacer des donnees, des fichiers, des applications d'un emplacement __A__ a __B__ d'un fichier __A__ a __B__ d'un format __A__ a __B__
<p> ('fin vous avez compris le concept :p )</p>
Dans le cas de rails, on peut faire appel a 
		<code>ActiveRecord::Migrate</code>
pour migrer une base de donnee facilement sans avoir a ecrire le sql nous meme 
<br >

<hr>

Les relations entre les modeles des BDD
---------------------------------------

*concept non pleinement compris*

Le modèle le plus courant, appelé modèle relationnel, trie les données dans des tables, que l'on appelle aussi des relations, dont chacune se compose de colonnes et de lignes. Chaque colonne contient un attribut de l'entité en question, comme le prix, le code postal ou la date de naissance. L'ensemble des attributs d'une relation est appelé domaine. La clé primaire est constituée par un attribut spécifique ou une combinaison d'attributs. On peut y faire référence dans d'autres tables

<p align="center"><img height="600px" width="300px" src="https://d2slcw3kip6qmk.cloudfront.net/marketing/pages/chart/seo/database/discovery/relational-model.svg" /></p>

<hr>


Les fonctions du CRUD
---------------------

<p>Le <strong>CRUD</strong> est un acronyme pour <strong>C</strong>reate, <strong>R</strong>ead (ou retrieve), <strong>U</strong>pdate, <strong>D</strong>elete </p>

ce sont les differentes fonctions de base que l'on peut effectuer sur une base de donnee 

- __Create__ cree une nouvelle entree dans la bdd
- __Read__ litteralement 'lis' une donnee dans la bdd
- __Update__ met a jour une donnee 
- __Delete__ supprime une donnee

Ce terme est un jeu de mot en anglais sur l'adjectif crude (en français brut ou rudimentaire).
On peut aussi le trouver ecrit __SCRUD__ (le S signifie search, recherche)
on trouve meme quelques acronymes amusants representant plus ou moins la meme chose:

- __BREAD__ (Browse, Read, Edit, Add, Delete)
- __DAVE__ (Delete, Add, View, Edit)
- __CRAP__ (Create, Retrieve, Alter, Purge)

<hr>

<p align="center"><img src="https://cdn-images-1.medium.com/max/1200/1*iIiiKaJKg8k9aRU8iWxCxA.jpeg" /></p>