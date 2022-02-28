# Fonctionnement général

Le widget Isogeo fonctionne pour le générateur d'applications web SIG Web AppBuilder for ArcGIS et potentiellement ses dérivés (comme _arcOpole Builder_)

Il s'ajoute comme tout autre widget aux applications webs au moment de leur configuration par l'administrateur de la plateforme Portal ou ArcGIS Online. Il est parfaitement intégré à l'interface des applications.

Depuis la version 10.6 du Portal, il peut même être intégré directement à celui-ci, ce qui rend possible l'ajout du widget à chaque création d'une application Web AppBuilder dans Portal.

Une fois en place, il permet à l'utilisateur final de [chercher une donnée](/usage/search.md) via une recherche libre, quelques filtres techniques (formats, ressources associées), sémantiques (mots-clés, thèmes INSPIRE, groupes de travail) et géographiques (filtre depuis la carte), des tris (Nom et date de mise à jour de la donnée). 

Il est ensuite possible d’ajouter la donnée via les liens de visualisation documentés (Esri Map, Esri Feature, Esri Tiled Map, WMS en WGS84) et de [consulter la métadonnée](/usage/metadata.md) dans une fenêtre spécifique.

---

## Prérequis

### Isogeo

* au moins un groupe de travail Isogeo dans un abonnement payant ;
* au moins un catalogue contenant au moins une métadonnée de service, partagé à l'application ;
* des clés d'authentification oAuth2 auprès de l'API Isogeo ;

### Serveur

* Serveur Web configuré (Apache, IIS...)
* Certificat SSL valide
* [PHP](https://secure.php.net/) installé et son extension cURL activée (à vérfier avec un phpinfo)

### Logiciels

* ArcGIS Server > 10.3
* Portal for ArcGIS > 10.6
* Application générée avec le WebAppBuilder dans Portal ou déployée sur un serveur Web
* Utilisateur nommé Esri administrateur du Portal ou ayant les droits de création d'une extension d'application Web AppBuilder (nécéssaire pour l'installation)
* Services cartographiques publiés sur ArcGIS Server et recensés dans Isogeo

### Réseau

Les URL(s) suivantes doivent être accessibles sur le serveur pour garantir la communication entre le widget et l'API Isogeo.

* https://id.api.isogeo.com/*
* https://v1.api.isogeo.com/*

Pour tester la communication, ouvrez les url(s) suivantes dans un navigateur sur le serveur web concerné.

* https://v1.api.isogeo.com/about
* https://id.api.isogeo.com/about  

 Dans les deux cas, la version de l'API devrait s'afficher en JSON.

### Arcopole Builder

Le widget est également compatible avec [_arcOpole Builder_](https://www.arcopole.fr/generateur-applications-arcopole-builder.aspx).