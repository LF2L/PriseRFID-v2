# PriseRFID-v2

## Description
Prise de courant connectée contrôlable par carte et badge RFID et à distance.

## Fonctions
* Alimenter la prise en fonction des autorisations
* Comptabiliser le temps de « connexion »
* Mesurer la consommation liée au compte 
* Couper l’alimentation électrique lors de demande délestage 

## Composants
*	Node MCU ESP8266
*	Module RC 522
*	Relai 5v
*	LEDs
*	Résistances
*	Convertisseur 220V AC- 5V DC
*	Câbles 230V
*	Prise électrique 

## Boitiers
*	MDF 3mm

## Echanges d'informations
L'appareil va se connecter à un serveur qui centralise les informations concernant les objets connectés. Il possède entre autre les informations des puces RFID avec les autorisations et les statistiques de consommation (durée et puissance). A l’instar des formulaires de connexion sur le site web, les données d’identification doivent certainement faire l’objet d’un « hashage ».

### Informations récupérées
Pour fonctionner la prise doit uniquement recevoir une autorisation d’alimenter la prise. 

### Informations envoyées
Inversement la seule variable de fonctionnement de la prise connectée est l’UID de la puce RFID.

### Fonctionnement
Lors de la détection de la présence d’une puce RFID, la prise connectée envoie l’information de la carte (préférablement sécurisée) au serveur REST qui centralise les informations dont celles des identifiants UID des puces, des autorisations et des statistiques de consommation. En fonction, des règles de fonctionnement appliquées par le serveur, il renvoie une autorisation d’activer ou non la prise électrique. 
La prise étant connectée au serveur, il est possible de désactiver la prise lors d’une demande de délestage. 

## To do
*	Réaliser les fonctions REST pour la vérification de l’UID dans la BDD et le renvoie de l’autorisation
*	Script de lecture de l’information provenant du serveur. 
