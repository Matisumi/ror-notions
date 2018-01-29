# ror-notions
Repo for THP's ruby ex


La difference entre un site dynamique et un site statique :
----------------------------------------------------------

les sites statiques et dynamiques ont, en apparence, aucune differences ...
Toute la magie du site dynamique repose dans le contenu de la page appelee :

Dans le cas d'un site statique, lorsque l'on appele une page, le serveur nous renvoie une page (qui peut etre simplement composee d'html et de css) deja prete stockee dans le serveur. Elle ne variera pas selon l'utilisateur qui l'appelle

A l'inverse sur un site dynamique, lorsqu'une page est appelee, verra son contenu evoluer en fonction de qui l'appelle et des criteres recus lors de l'appel (IP, logins, form ....).
On pourrait prendre comme exemple facebook, qui, si vous etes connecte, affichera le fil d'actualite correspondant a votre profil ou encore le site THP qui affiche votre nom et votre progression dans le cursus ...



Le MVC
-------

Le MVC est une methode d'organisation de son code, cela consiste a separer son code en trois fichiers ayant chacuns un role :

 - Le controleur
 - Le modele
 - La vue

 [img]

Le controleur : c'est lui qui va recevoir la requete HTTP (HyperText Transfert Protocol) et orchestrer le processus de reponse. Il va prendre les informations recues demander au modele de verifier/recuperer ce qui est demande et renvoyer les informations a la vue

Le modele : Lui il recois les donnees de la requete HTTP que le controleur lui envoie et lui retourne les donnees demandees en echange. c'est lui qui va faire appel a la base de donnee pour ecrire / recuperer des informations qu'il renvoie par la suite au controleur.

La vue : elle c'est l'etape finale, elle ne fait que renvoyer au controleurla page appelee avec les informations que le controleur lui fournis pour que le controleur renvoie le produit final a l'utilisateur.


Les routes
----------

Les routes permettent de renvoyer la page appelee en dechiffrant l'url fourni, elles se configurent dans le fichier config/routes.rb 

La configuration par defaut se fait par la ligne :

1
	
resources :photos

plus d'exemples sur sois net



Les Bases de Donnees
--------------------

Les bases de donnees sont un ensemble d'information stokees et structurees afin de pouvoir etre reutilises ou lues informatiquement.

on peut y effectuer plusieurs type d'operations :

- filtrer : recuperer un groupe de donnees selon des criteres fournis 

- trier : reorganiser les donnees selon un ordre precis determine par des criteres

- repliquer : "cloner" (backup) pour par exemple des raisons de securites ou faciliter le tri d'information prenant en compte un grand nombre de criteres

On a deux formats de bases de donnees : - sous forme de fichiers (ex : SQLite)
 - sous forme de logiciel / service (ex : MySQL, MongoDB ...)

GET & POST
----------

GET et POST sont deux metodes de requetes HTTP.

GET envoie une demande pour une ressource particuliere (via URL)
POST envoie des criteres traites par le seveur qui renvoie ce qui est demandee

Caracteristiques de GET :

- peut etre mis en cache
- est enregistre dans l'historique du navigateur (url)
- peut etre enregistre dans les marques pages
- ne doit pas etre utilise pour envoyer des informations sensibles
- est limite en nombre de caracteres (2048)
- ne doit etre utilise que pour recuperer des donnees
- ne prends en compte que l'ascii

Caracteristiques de POST :

- ne peut pas etre mis en cache
- ne s'affiche pas dans l'historique
- ne se sauvegarde pas en marque page
- n'est pas limite en caractere ni a l'ascii

Le concept de migration
-----------------------

La migration c'est le fait de deplacer des donnees, des fichiers, des applications d'un emplacement A a B d'un fichier A a B d'un format A a B ('fin vous avez compris le concept :p )
Dans le cas de rails, on peut faire appel a ``` ActiveRecord::Migrate```
pour migrer une base de donnee facilement sans avoir a ecrire le sql nous meme 

[tab]

Les relations entre les modeles des BDD
---------------------------------------

*concept non pleinement compris*

Le modèle le plus courant, appelé modèle relationnel, trie les données dans des tables, que l'on appelle aussi des relations, dont chacune se compose de colonnes et de lignes. Chaque colonne contient un attribut de l'entité en question, comme le prix, le code postal ou la date de naissance. L'ensemble des attributs d'une relation est appelé domaine. La clé primaire est constituée par un attribut spécifique ou une combinaison d'attributs. On peut y faire référence dans d'autres tables

[img]


Les fonctions du CRUD
---------------------

Le CRUD est un acronyme pour Create, Read (ou retrieve), Update, Delete 

ce sont les differentes fonctions de base que l'on peut effectuer sur une base de donnee 

- Create cree une nouvelle entree dans la bdd
- Read litteralement 'lis' une donnee dans la bdd
- Update met a jour une donnee 
- Delete supprime une donnee

Ce terme est un jeu de mot en anglais sur l'adjectif crude (en français brut ou rudimentaire).
On peut aussi le trouver ecrit SCRUD (le S signifie search, recherche)
on trouve meme quelques acronymes amusants representant plus ou moins la meme chose:

- BREAD (Browse, Read, Edit, Add, Delete)
- DAVE (Delete, Add, View, Edit)
- CRAP (Create, Retrieve, Alter, Purge)