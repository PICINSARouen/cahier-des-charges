# Fonctionnalités

## Projet PIC

Il doit être possible de créer des projets et des élèves-ingénieurs en ligne de commande ou via une interface de super-admin. Un projet est composé de :

* un titre (un texte) ;
* un nom de code (un texte) ;
* des élèves-ingénieurs.

Un élève-ingénieur est une partie intéressée du PIC. Une partie intéressée du PIC est composée de :

* un nom (un texte) ;
* un prénom (un texte) ;
* un mot de passe (un *hash*) ;
* une adresse mail (un texte).

Le *hash* doit être sécurisé via un algorithme performant comme BCrypt.

## Documents

Il doit être possible de créer, de mettre à jour et de supprimer des documents sur le logiciel. Un document possède :

* un type (un *type de document*) ;
* un référentiel (un *référentiel*);
* une référence (un texte);
* un rédacteur (une *partie intéressée* du PIC);
* une date de rédaction (une date);
* un vérificateur (une *partie intéressée* du PIC) ;
* une date de vérification (une date) ;
* un validateur (une *partie intéressée* du PIC) ;
* une date de validation (une date) ;
* un archivage (un booléen).

Si ce document nécessite une approbation, il possède un approbateur (une *partie intéressée* du PIC) et une date d'approbation (une date). Si ce document nécessite une diffusion, il possède une date de diffusion (une date).

Il doit être possible de créer des types de documents avec un nom (un texte), une information sur la nécessité d'approbation (un booléen) et de diffusion (un booléen). Cette ressource doit être extensible pour ajouter des fonctionnalités comme la génération automatique des titres des documents ou un référentiel par défaut.

Il est également possible de créer des référentiels avec un nom (un texte).

La visualisation des documents est effectuée par un tableau récapitulatif avec pour chaque référentiel, les types de documents existants et pour chaque type de document existants la liste des documents présents. Chaque ligne de document présent doit faire figurer, en plus de sa référence, les informations de rédaction, de vérification, de validation, d'archivage et si nécessaire, d'approbation et de diffusion. Ces informations doivent être visuelles pour rapidement déterminer où se trouve le document dans le processus de création. Il doit également être possible d'accéder directement au document dans l'archivage FTP.

## Temps de travail et tâches



## Réunions

Le logiciel doit permettre de créer, modifier et supprimer des réunions. Une réunion est composée de :

* un type (un *type de réunion*) ;
* un début (une date et une heure) ;
* une fin (une date et une heure) ;
* une liste de personnes présentes (une liste de *parties intéressées*).

Un type de réunion est un nom (un texte) avec une possibilité de compte-rendu (un *type de document*). Si la réunion est d'un type de réunion nécessitant un compte-rendu, elle doit pouvoir être liée à un document du bon type.

La visualisation des réunions est effectuée par un tableau récapitulatif avec pour chaque semaine et pour chaque date la liste des réunions effectuées. Chaque ligne de réunion doit faire figurer le type de réunion et le temps de la réunion. Si cette réunion nécessite un compte-rendu, il est également nécessaire d'afficher le lien vers l'archivage du compte-rendu ou vers le document dans la liste des documents.

## Cycle correctif

Le logiciel doit être capable de gérer le cycle correctif du PIC respectant la norme ISO 9001.

Lors d'un problème durant le projet, un fait technique doit être émi. Un fait technique est composé de trois parties.

* Description :
    * un numéro de FT (un entier) ;
    * une référence (un texte) ;
    * un auteur (une *partie intéressée*) ;
    * une date d'émission (une date) ;
    * un objet (un texte) ;
    * une gravité (un *niveau de gravité*) ;
    * un type (un *type de FT*) ;
    * une source (une *source de FT*) ;
    * une description (un texte).
* Analyse et corrections :
    * une date d'analyse (une date) ;
    * une liste de participants (une liste de *parties intéressées*) ;
    * une conséquence (un texte) ;
    * une *analyse des causes* ;
    * une liste de *corrections*.
* Analyse à froid :
    * une date d'analyse (une date) ;
    * une liste de participants (une liste de *parties intéressées*) ;
    * une information sur l'efficacité de la correction (un booléen) ;
    * un avis d'efficacité de la correction (un texte) ;

Un niveau de gravité est composé d'un nom (un texte). Un type de FT est composé d'un nom (un texte). Une source de FT est composé d'un nom (un texte). Il n'est pas nécessaire de créer une interface pour modifier ces champs mais il doit être possible d'en ajouter, d'en modifier et d'en supprimer via la base de données.

Une analyse des causes est composée de *pourquoi*. Un pourquoi est composé d'une description (un texte) et de sous *pourquoi*.

Une correction est composée de :

* une description (un texte) ;
* une liste de points à vérifier (liste de textes) ;
* un correcteur (une *partie intéressée*) ;
* une estimation de la durée en secondes (un entier) ;
* une limite de correction (une date) ;
* une date de correction (une date) ;
* une liste d'articles ouverts à la correction (une liste de *documents*) ;
* un vérificateur (une *partie intéressée*) ;
* une date de vérification (une date) ;
* une condition de clôture (un texte) ;
* un auteur de la clôture (une *partie intéressée*) ;
* une date de clôture (une date).
